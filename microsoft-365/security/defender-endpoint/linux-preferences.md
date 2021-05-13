---
title: Linux에서 끝점용 Microsoft Defender에 대한 기본 설정 설정
ms.reviewer: ''
description: 엔터프라이즈에서 Linux에서 끝점에 대한 Microsoft Defender를 구성하는 방법을 설명 합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, linux, 설치, 배포, 제거, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 29505a6e975fdfa2283efe3391c615e40e678164
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346381"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="39811-104">Linux에서 끝점용 Microsoft Defender에 대한 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="39811-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="39811-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="39811-105">**Applies to:**</span></span>
- [<span data-ttu-id="39811-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="39811-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="39811-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39811-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="39811-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="39811-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="39811-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="39811-110">이 항목에는 엔터프라이즈 환경에서 Linux에서 끝점용 Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="39811-111">명령줄에서 디바이스에서 제품을 구성하는 데 관심이 있는 경우 리소스를 [참조하세요.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="39811-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="39811-112">엔터프라이즈 환경에서 Linux의 끝점용 Defender는 구성 프로필을 통해 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="39811-113">이 프로필은 선택한 관리 도구에서 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="39811-114">엔터프라이즈에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="39811-115">즉, 기업의 사용자는 이 구성 프로필을 통해 설정된 기본 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="39811-116">이 문서에서는 이 프로필의 구조(시작하는 데 사용할 수 있는 권장 프로필 포함)와 프로필 배포 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="39811-117">구성 프로필 구조</span><span class="sxs-lookup"><span data-stu-id="39811-117">Configuration profile structure</span></span>

<span data-ttu-id="39811-118">구성 프로필은 키(기본 설정의 이름을 나타임)로 식별되는 항목과 기본 설정의 특성에 따라 값이 이어지는 .json 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="39811-119">값은 숫자 값과 같이 단순하거나 중첩된 기본 설정 목록과 같은 복잡한 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="39811-120">일반적으로 구성 관리 도구를 사용하여 위치에 이름이 있는 파일을 ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="39811-121">구성 프로필의 최상위 수준에는 제품 수준 기본 설정 및 제품의 하위 항목에 대한 항목이 포함되어 있으며, 이 내용은 다음 섹션에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="39811-122">바이러스 백신 엔진 기본 설정</span><span class="sxs-lookup"><span data-stu-id="39811-122">Antivirus engine preferences</span></span>

<span data-ttu-id="39811-123">구성 *프로필의 antivirusEngine* 섹션은 제품의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-124">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-124">**Key**</span></span> | <span data-ttu-id="39811-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="39811-125">antivirusEngine</span></span> |
| <span data-ttu-id="39811-126">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-126">**Data type**</span></span> | <span data-ttu-id="39811-127">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="39811-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="39811-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-128">**Comments**</span></span> | <span data-ttu-id="39811-129">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39811-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="39811-130">실시간 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="39811-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="39811-131">실시간 보호(액세스할 때 파일 검색)를 사용할지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-132">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-132">**Key**</span></span> | <span data-ttu-id="39811-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="39811-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="39811-134">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-134">**Data type**</span></span> | <span data-ttu-id="39811-135">부울</span><span class="sxs-lookup"><span data-stu-id="39811-135">Boolean</span></span> |
| <span data-ttu-id="39811-136">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-136">**Possible values**</span></span> | <span data-ttu-id="39811-137">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-137">true (default)</span></span> <br/> <span data-ttu-id="39811-138">false</span><span class="sxs-lookup"><span data-stu-id="39811-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="39811-139">수동 모드 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="39811-139">Enable / disable passive mode</span></span>

<span data-ttu-id="39811-140">바이러스 백신 엔진이 수동 모드에서 실행될지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="39811-141">수동 모드:</span><span class="sxs-lookup"><span data-stu-id="39811-141">In passive mode:</span></span>
- <span data-ttu-id="39811-142">실시간 보호가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="39811-143">On-demand scanning is turned on.</span><span class="sxs-lookup"><span data-stu-id="39811-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="39811-144">자동 위협 수정이 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="39811-145">보안 인텔리전스 업데이트가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="39811-146">상태 메뉴 아이콘이 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="39811-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-147">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-147">**Key**</span></span> | <span data-ttu-id="39811-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="39811-148">passiveMode</span></span> |
| <span data-ttu-id="39811-149">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-149">**Data type**</span></span> | <span data-ttu-id="39811-150">부울</span><span class="sxs-lookup"><span data-stu-id="39811-150">Boolean</span></span> |
| <span data-ttu-id="39811-151">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-151">**Possible values**</span></span> | <span data-ttu-id="39811-152">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-152">false (default)</span></span> <br/> <span data-ttu-id="39811-153">true</span><span class="sxs-lookup"><span data-stu-id="39811-153">true</span></span> |
| <span data-ttu-id="39811-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-154">**Comments**</span></span> | <span data-ttu-id="39811-155">Endpoint 버전 100.67.60 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="39811-156">제외 병합 정책</span><span class="sxs-lookup"><span data-stu-id="39811-156">Exclusion merge policy</span></span>

<span data-ttu-id="39811-157">제외에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="39811-158">관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()만 조합할 `merge` 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="39811-159">이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-160">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-160">**Key**</span></span> | <span data-ttu-id="39811-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="39811-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="39811-162">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-162">**Data type**</span></span> | <span data-ttu-id="39811-163">String</span><span class="sxs-lookup"><span data-stu-id="39811-163">String</span></span> |
| <span data-ttu-id="39811-164">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-164">**Possible values**</span></span> | <span data-ttu-id="39811-165">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-165">merge (default)</span></span> <br/> <span data-ttu-id="39811-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="39811-166">admin_only</span></span> |
| <span data-ttu-id="39811-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-167">**Comments**</span></span> | <span data-ttu-id="39811-168">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="39811-169">제외 검사</span><span class="sxs-lookup"><span data-stu-id="39811-169">Scan exclusions</span></span>

<span data-ttu-id="39811-170">검사에서 제외된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="39811-171">제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="39811-172">제외는 항목 배열로 지정됩니다. 관리자는 필요한 수의 요소를 순서에 따라 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-173">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-173">**Key**</span></span> | <span data-ttu-id="39811-174">제외</span><span class="sxs-lookup"><span data-stu-id="39811-174">exclusions</span></span> |
| <span data-ttu-id="39811-175">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-175">**Data type**</span></span> | <span data-ttu-id="39811-176">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="39811-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="39811-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-177">**Comments**</span></span> | <span data-ttu-id="39811-178">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39811-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="39811-179">**제외 유형**</span><span class="sxs-lookup"><span data-stu-id="39811-179">**Type of exclusion**</span></span>

<span data-ttu-id="39811-180">검색에서 제외된 콘텐츠의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-181">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-181">**Key**</span></span> | <span data-ttu-id="39811-182">$type</span><span class="sxs-lookup"><span data-stu-id="39811-182">$type</span></span> |
| <span data-ttu-id="39811-183">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-183">**Data type**</span></span> | <span data-ttu-id="39811-184">String</span><span class="sxs-lookup"><span data-stu-id="39811-184">String</span></span> |
| <span data-ttu-id="39811-185">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-185">**Possible values**</span></span> | <span data-ttu-id="39811-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="39811-186">excludedPath</span></span> <br/> <span data-ttu-id="39811-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="39811-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="39811-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="39811-188">excludedFileName</span></span> |
|||

<span data-ttu-id="39811-189">**제외된 콘텐츠의 경로**</span><span class="sxs-lookup"><span data-stu-id="39811-189">**Path to excluded content**</span></span>

<span data-ttu-id="39811-190">전체 파일 경로로 검색에서 콘텐츠를 제외하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-191">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-191">**Key**</span></span> | <span data-ttu-id="39811-192">path</span><span class="sxs-lookup"><span data-stu-id="39811-192">path</span></span> |
| <span data-ttu-id="39811-193">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-193">**Data type**</span></span> | <span data-ttu-id="39811-194">String</span><span class="sxs-lookup"><span data-stu-id="39811-194">String</span></span> |
| <span data-ttu-id="39811-195">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-195">**Possible values**</span></span> | <span data-ttu-id="39811-196">유효한 경로</span><span class="sxs-lookup"><span data-stu-id="39811-196">valid paths</span></span> |
| <span data-ttu-id="39811-197">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-197">**Comments**</span></span> | <span data-ttu-id="39811-198">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="39811-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="39811-199">**경로 유형(파일/디렉터리)**</span><span class="sxs-lookup"><span data-stu-id="39811-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="39811-200">path *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="39811-200">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="39811-201">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-201">**Key**</span></span> | <span data-ttu-id="39811-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="39811-202">isDirectory</span></span> |
| <span data-ttu-id="39811-203">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-203">**Data type**</span></span> | <span data-ttu-id="39811-204">부울</span><span class="sxs-lookup"><span data-stu-id="39811-204">Boolean</span></span> |
| <span data-ttu-id="39811-205">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-205">**Possible values**</span></span> | <span data-ttu-id="39811-206">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-206">false (default)</span></span> <br/> <span data-ttu-id="39811-207">true</span><span class="sxs-lookup"><span data-stu-id="39811-207">true</span></span> |
| <span data-ttu-id="39811-208">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-208">**Comments**</span></span> | <span data-ttu-id="39811-209">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="39811-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="39811-210">**검사에서 제외된 파일 확장명**</span><span class="sxs-lookup"><span data-stu-id="39811-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="39811-211">파일 확장명에 의해 검색에서 콘텐츠를 제외하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-212">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-212">**Key**</span></span> | <span data-ttu-id="39811-213">extension</span><span class="sxs-lookup"><span data-stu-id="39811-213">extension</span></span> |
| <span data-ttu-id="39811-214">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-214">**Data type**</span></span> | <span data-ttu-id="39811-215">String</span><span class="sxs-lookup"><span data-stu-id="39811-215">String</span></span> |
| <span data-ttu-id="39811-216">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-216">**Possible values**</span></span> | <span data-ttu-id="39811-217">유효한 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="39811-217">valid file extensions</span></span> |
| <span data-ttu-id="39811-218">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-218">**Comments**</span></span> | <span data-ttu-id="39811-219">제외된  *$type FileExtension만 적용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="39811-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="39811-220">**검사에서 제외된 프로세스**</span><span class="sxs-lookup"><span data-stu-id="39811-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="39811-221">모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="39811-222">프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-223">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-223">**Key**</span></span> | <span data-ttu-id="39811-224">name</span><span class="sxs-lookup"><span data-stu-id="39811-224">name</span></span> |
| <span data-ttu-id="39811-225">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-225">**Data type**</span></span> | <span data-ttu-id="39811-226">String</span><span class="sxs-lookup"><span data-stu-id="39811-226">String</span></span> |
| <span data-ttu-id="39811-227">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-227">**Possible values**</span></span> | <span data-ttu-id="39811-228">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="39811-228">any string</span></span> |
| <span data-ttu-id="39811-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-229">**Comments**</span></span> | <span data-ttu-id="39811-230">*excludedFileName이 $type만 적용할 수 있습니다.* </span><span class="sxs-lookup"><span data-stu-id="39811-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="39811-231">허용되는 위협</span><span class="sxs-lookup"><span data-stu-id="39811-231">Allowed threats</span></span>

<span data-ttu-id="39811-232">제품에서 차단되지 않고 대신 실행할 수 있는 위협 목록(해당 이름으로 식별)입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-233">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-233">**Key**</span></span> | <span data-ttu-id="39811-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="39811-234">allowedThreats</span></span> |
| <span data-ttu-id="39811-235">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-235">**Data type**</span></span> | <span data-ttu-id="39811-236">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="39811-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="39811-237">위협 작업 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-237">Disallowed threat actions</span></span>

<span data-ttu-id="39811-238">위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="39811-239">이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-240">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-240">**Key**</span></span> | <span data-ttu-id="39811-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="39811-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="39811-242">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-242">**Data type**</span></span> | <span data-ttu-id="39811-243">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="39811-243">Array of strings</span></span> |
| <span data-ttu-id="39811-244">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-244">**Possible values**</span></span> | <span data-ttu-id="39811-245">allow (restricts users from allow threats)</span><span class="sxs-lookup"><span data-stu-id="39811-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="39811-246">restore(사용자가 검지에서 위협을 복원하는 것을 제한함)</span><span class="sxs-lookup"><span data-stu-id="39811-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="39811-247">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-247">**Comments**</span></span> | <span data-ttu-id="39811-248">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="39811-249">위협 유형 설정</span><span class="sxs-lookup"><span data-stu-id="39811-249">Threat type settings</span></span>

<span data-ttu-id="39811-250">바이러스 *백신 엔진의 threatTypeSettings* 기본 설정은 특정 위협 유형이 제품에서 처리되는 방법을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-251">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-251">**Key**</span></span> | <span data-ttu-id="39811-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="39811-252">threatTypeSettings</span></span> |
| <span data-ttu-id="39811-253">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-253">**Data type**</span></span> | <span data-ttu-id="39811-254">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="39811-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="39811-255">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-255">**Comments**</span></span> | <span data-ttu-id="39811-256">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39811-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="39811-257">**위협 유형**</span><span class="sxs-lookup"><span data-stu-id="39811-257">**Threat type**</span></span>

<span data-ttu-id="39811-258">동작이 구성된 위협 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-259">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-259">**Key**</span></span> | <span data-ttu-id="39811-260">키</span><span class="sxs-lookup"><span data-stu-id="39811-260">key</span></span> |
| <span data-ttu-id="39811-261">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-261">**Data type**</span></span> | <span data-ttu-id="39811-262">String</span><span class="sxs-lookup"><span data-stu-id="39811-262">String</span></span> |
| <span data-ttu-id="39811-263">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-263">**Possible values**</span></span> | <span data-ttu-id="39811-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="39811-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="39811-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="39811-265">archive_bomb</span></span> |
|||

<span data-ttu-id="39811-266">**수행할 작업**</span><span class="sxs-lookup"><span data-stu-id="39811-266">**Action to take**</span></span>

<span data-ttu-id="39811-267">이전 섹션에 지정된 유형의 위협에 부과될 때 취할 조치입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="39811-268">다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-268">Can be:</span></span>

- <span data-ttu-id="39811-269">**감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="39811-270">**차단:** 이 유형의 위협으로부터 장치가 보호되고 보안 콘솔에 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="39811-271">**Off:** 이 유형의 위협으로부터 장치가 보호되지는 않습니다. 아무것도 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-272">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-272">**Key**</span></span> | <span data-ttu-id="39811-273">값</span><span class="sxs-lookup"><span data-stu-id="39811-273">value</span></span> |
| <span data-ttu-id="39811-274">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-274">**Data type**</span></span> | <span data-ttu-id="39811-275">String</span><span class="sxs-lookup"><span data-stu-id="39811-275">String</span></span> |
| <span data-ttu-id="39811-276">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-276">**Possible values**</span></span> | <span data-ttu-id="39811-277">감사(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-277">audit (default)</span></span> <br/> <span data-ttu-id="39811-278">block</span><span class="sxs-lookup"><span data-stu-id="39811-278">block</span></span> <br/> <span data-ttu-id="39811-279">off</span><span class="sxs-lookup"><span data-stu-id="39811-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="39811-280">위협 유형 설정 병합 정책</span><span class="sxs-lookup"><span data-stu-id="39811-280">Threat type settings merge policy</span></span>

<span data-ttu-id="39811-281">위협 유형 설정에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="39811-282">이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="39811-283">이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-284">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-284">**Key**</span></span> | <span data-ttu-id="39811-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="39811-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="39811-286">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-286">**Data type**</span></span> | <span data-ttu-id="39811-287">String</span><span class="sxs-lookup"><span data-stu-id="39811-287">String</span></span> |
| <span data-ttu-id="39811-288">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-288">**Possible values**</span></span> | <span data-ttu-id="39811-289">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-289">merge (default)</span></span> <br/> <span data-ttu-id="39811-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="39811-290">admin_only</span></span> |
| <span data-ttu-id="39811-291">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-291">**Comments**</span></span> | <span data-ttu-id="39811-292">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="39811-293">바이러스 백신 검사 기록 보존(일)</span><span class="sxs-lookup"><span data-stu-id="39811-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="39811-294">장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="39811-295">이전 검사 결과가 기록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="39811-296">디스크에서 제거된 오래된 고지된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-297">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-297">**Key**</span></span> | <span data-ttu-id="39811-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="39811-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="39811-299">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-299">**Data type**</span></span> | <span data-ttu-id="39811-300">String</span><span class="sxs-lookup"><span data-stu-id="39811-300">String</span></span> |
| <span data-ttu-id="39811-301">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-301">**Possible values**</span></span> | <span data-ttu-id="39811-302">90(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-302">90 (default).</span></span> <span data-ttu-id="39811-303">허용되는 값은 1일에서 180일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="39811-304">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-304">**Comments**</span></span> | <span data-ttu-id="39811-305">Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="39811-306">바이러스 백신 검사 기록의 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="39811-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="39811-307">검사 기록에 유지할 최대 항목 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="39811-308">항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-309">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-309">**Key**</span></span> | <span data-ttu-id="39811-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="39811-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="39811-311">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-311">**Data type**</span></span> | <span data-ttu-id="39811-312">String</span><span class="sxs-lookup"><span data-stu-id="39811-312">String</span></span> |
| <span data-ttu-id="39811-313">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-313">**Possible values**</span></span> | <span data-ttu-id="39811-314">10000(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-314">10000 (default).</span></span> <span data-ttu-id="39811-315">허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="39811-316">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-316">**Comments**</span></span> | <span data-ttu-id="39811-317">Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="39811-318">클라우드 제공 보호 기본 설정</span><span class="sxs-lookup"><span data-stu-id="39811-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="39811-319">구성 *프로필의 cloudService* 항목은 제품의 클라우드 기반 보호 기능을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-320">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-320">**Key**</span></span> | <span data-ttu-id="39811-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="39811-321">cloudService</span></span> |
| <span data-ttu-id="39811-322">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-322">**Data type**</span></span> | <span data-ttu-id="39811-323">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="39811-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="39811-324">**Comments**</span><span class="sxs-lookup"><span data-stu-id="39811-324">**Comments**</span></span> | <span data-ttu-id="39811-325">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39811-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="39811-326">클라우드 제공 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="39811-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="39811-327">장치에서 클라우드 제공 보호를 사용할지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="39811-328">서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-329">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-329">**Key**</span></span> | <span data-ttu-id="39811-330">활성화됨</span><span class="sxs-lookup"><span data-stu-id="39811-330">enabled</span></span> |
| <span data-ttu-id="39811-331">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-331">**Data type**</span></span> | <span data-ttu-id="39811-332">부울</span><span class="sxs-lookup"><span data-stu-id="39811-332">Boolean</span></span> |
| <span data-ttu-id="39811-333">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-333">**Possible values**</span></span> | <span data-ttu-id="39811-334">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-334">true (default)</span></span> <br/> <span data-ttu-id="39811-335">false</span><span class="sxs-lookup"><span data-stu-id="39811-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="39811-336">진단 수집 수준</span><span class="sxs-lookup"><span data-stu-id="39811-336">Diagnostic collection level</span></span>

<span data-ttu-id="39811-337">진단 데이터는 Endpoint용 Defender를 안전하고 최신 상태를 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="39811-338">이 설정은 제품이 Microsoft에 전송한 진단 수준을 결정하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-339">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-339">**Key**</span></span> | <span data-ttu-id="39811-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="39811-340">diagnosticLevel</span></span> |
| <span data-ttu-id="39811-341">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-341">**Data type**</span></span> | <span data-ttu-id="39811-342">String</span><span class="sxs-lookup"><span data-stu-id="39811-342">String</span></span> |
| <span data-ttu-id="39811-343">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-343">**Possible values**</span></span> | <span data-ttu-id="39811-344">선택 사항(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-344">optional (default)</span></span> <br/> <span data-ttu-id="39811-345">필수</span><span class="sxs-lookup"><span data-stu-id="39811-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="39811-346">자동 샘플 제출 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="39811-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="39811-347">의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="39811-348">샘플 제출을 제어하는 세 가지 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="39811-349">**없음:** 의심스러운 샘플이 Microsoft에 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="39811-350">**안전**: PII(개인 식별 정보)를 포함하지 않는 의심스러운 샘플만 자동으로 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="39811-351">이 설정의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="39811-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="39811-352">**모두:** 의심스러운 모든 샘플이 Microsoft에 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-353">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-353">**Key**</span></span> | <span data-ttu-id="39811-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="39811-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="39811-355">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-355">**Data type**</span></span> | <span data-ttu-id="39811-356">String</span><span class="sxs-lookup"><span data-stu-id="39811-356">String</span></span> |
| <span data-ttu-id="39811-357">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-357">**Possible values**</span></span> | <span data-ttu-id="39811-358">없음</span><span class="sxs-lookup"><span data-stu-id="39811-358">none</span></span> <br/> <span data-ttu-id="39811-359">안전(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-359">safe (default)</span></span> <br/> <span data-ttu-id="39811-360">all</span><span class="sxs-lookup"><span data-stu-id="39811-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="39811-361">자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="39811-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="39811-362">보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="39811-363">**키**</span><span class="sxs-lookup"><span data-stu-id="39811-363">**Key**</span></span> | <span data-ttu-id="39811-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="39811-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="39811-365">**Data type**</span><span class="sxs-lookup"><span data-stu-id="39811-365">**Data type**</span></span> | <span data-ttu-id="39811-366">부울</span><span class="sxs-lookup"><span data-stu-id="39811-366">Boolean</span></span> |
| <span data-ttu-id="39811-367">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="39811-367">**Possible values**</span></span> | <span data-ttu-id="39811-368">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="39811-368">true (default)</span></span> <br/> <span data-ttu-id="39811-369">false</span><span class="sxs-lookup"><span data-stu-id="39811-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="39811-370">권장 구성 프로필</span><span class="sxs-lookup"><span data-stu-id="39811-370">Recommended configuration profile</span></span>

<span data-ttu-id="39811-371">시작하려면 엔터프라이즈에서 다음과 같은 구성 프로필을 사용하여 Endpoint용 Defender에서 제공하는 모든 보호 기능을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="39811-372">다음 구성 프로필은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-372">The following configuration profile will:</span></span>

- <span data-ttu-id="39811-373">RTP(실시간 보호) 사용</span><span class="sxs-lookup"><span data-stu-id="39811-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="39811-374">다음 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="39811-375">**잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="39811-376">**보관함(압축률이** 높은 파일)이 제품 로그에 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="39811-377">자동 보안 인텔리전스 업데이트 사용</span><span class="sxs-lookup"><span data-stu-id="39811-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="39811-378">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="39811-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="39811-379">수준에서 자동 샘플 제출 `safe` 사용</span><span class="sxs-lookup"><span data-stu-id="39811-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="39811-380">샘플 프로필</span><span class="sxs-lookup"><span data-stu-id="39811-380">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="39811-381">전체 구성 프로필 예제</span><span class="sxs-lookup"><span data-stu-id="39811-381">Full configuration profile example</span></span>

<span data-ttu-id="39811-382">다음 구성 프로필에는 이 문서에 설명된 모든 설정에 대한 항목이 포함되어 있으며 제품을 보다 잘 제어하려는 고급 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="39811-383">전체 프로필</span><span class="sxs-lookup"><span data-stu-id="39811-383">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="39811-384">구성 프로필 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="39811-384">Configuration profile validation</span></span>

<span data-ttu-id="39811-385">구성 프로필은 유효한 JSON 형식 파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="39811-386">이를 확인하는 데 사용할 수 있는 도구는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="39811-387">예를 들어 장치에 `python` 설치한 경우:</span><span class="sxs-lookup"><span data-stu-id="39811-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="39811-388">JSON이 잘 구성되면 위의 명령은 터미널에 다시 출력하고 의 종료 코드를 `0` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="39811-389">그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39811-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="39811-390">파일의 mdatp_managed.js올바르게 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="39811-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="39811-391">/etc/opt/microsoft/mdatp/managed/mdatp_managed.js제대로 작동하고 있는지 확인하려면 다음 설정 옆에 "[관리]"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="39811-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="39811-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="39811-392">cloud_enabled</span></span>
- <span data-ttu-id="39811-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="39811-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="39811-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="39811-394">passice_mode_enabled</span></span>
- <span data-ttu-id="39811-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="39811-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="39811-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="39811-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="39811-397">이 mdatp_managed.js적용하려면 wdavdaemon을 다시 시작할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="39811-398">구성 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="39811-398">Configuration profile deployment</span></span>

<span data-ttu-id="39811-399">엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 도구를 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="39811-400">Linux의 끝점용 Defender는 */etc/opt/microsoft/mdatp/managed/mdatp_managed.js* 관리되는 구성을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="39811-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
