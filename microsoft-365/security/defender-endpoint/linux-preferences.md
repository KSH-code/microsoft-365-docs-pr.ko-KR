---
title: Linux용 Microsoft Defender ATP에 대한 기본 설정 설정
ms.reviewer: ''
description: 엔터프라이즈에서 Linux용 Microsoft Defender ATP를 구성하는 방법에 대해 설명
keywords: microsoft, defender, atp, linux, 설치, 배포, 제거, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8595bae216911350d3f18fcceef729ef020a424
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408168"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="18699-104">Linux용 끝점에 대한 Microsoft Defender 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="18699-104">Set preferences for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="18699-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="18699-105">**Applies to:**</span></span>
- [<span data-ttu-id="18699-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="18699-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="18699-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18699-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="18699-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="18699-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="18699-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="18699-110">이 항목에는 엔터프라이즈 환경에서 Linux용 Endpoint용 Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="18699-111">명령줄에서 디바이스에서 제품을 구성하는 데 관심이 있는 경우 리소스를 [참조하세요.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="18699-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="18699-112">엔터프라이즈 환경에서 Linux용 끝점용 Defender는 구성 프로필을 통해 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="18699-113">이 프로필은 선택한 관리 도구에서 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="18699-114">엔터프라이즈에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="18699-115">즉, 기업의 사용자는 이 구성 프로필을 통해 설정된 기본 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="18699-116">이 문서에서는 이 프로필의 구조(시작하는 데 사용할 수 있는 권장 프로필 포함)와 프로필 배포 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="18699-117">구성 프로필 구조</span><span class="sxs-lookup"><span data-stu-id="18699-117">Configuration profile structure</span></span>

<span data-ttu-id="18699-118">구성 프로필은 키(기본 설정의 이름을 나타임)로 식별되는 항목과 기본 설정의 특성에 따라 값이 이어지는 .json 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="18699-119">값은 숫자 값과 같이 단순하거나 중첩된 기본 설정 목록과 같은 복잡한 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="18699-120">일반적으로 구성 관리 도구를 사용하여 위치에 이름이 있는 파일을 ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="18699-121">구성 프로필의 최상위 수준에는 제품 수준 기본 설정 및 제품의 하위 항목에 대한 항목이 포함되어 있으며, 이 내용은 다음 섹션에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="18699-122">바이러스 백신 엔진 기본 설정</span><span class="sxs-lookup"><span data-stu-id="18699-122">Antivirus engine preferences</span></span>

<span data-ttu-id="18699-123">구성 *프로필의 antivirusEngine* 섹션은 제품의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-124">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-124">**Key**</span></span> | <span data-ttu-id="18699-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="18699-125">antivirusEngine</span></span> |
| <span data-ttu-id="18699-126">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-126">**Data type**</span></span> | <span data-ttu-id="18699-127">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="18699-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="18699-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-128">**Comments**</span></span> | <span data-ttu-id="18699-129">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18699-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="18699-130">실시간 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="18699-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="18699-131">실시간 보호(액세스할 때 파일 검색)를 사용할지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-132">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-132">**Key**</span></span> | <span data-ttu-id="18699-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="18699-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="18699-134">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-134">**Data type**</span></span> | <span data-ttu-id="18699-135">부울</span><span class="sxs-lookup"><span data-stu-id="18699-135">Boolean</span></span> |
| <span data-ttu-id="18699-136">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-136">**Possible values**</span></span> | <span data-ttu-id="18699-137">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-137">true (default)</span></span> <br/> <span data-ttu-id="18699-138">false</span><span class="sxs-lookup"><span data-stu-id="18699-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="18699-139">수동 모드 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="18699-139">Enable / disable passive mode</span></span>

<span data-ttu-id="18699-140">바이러스 백신 엔진이 수동 모드에서 실행될지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="18699-141">수동 모드:</span><span class="sxs-lookup"><span data-stu-id="18699-141">In passive mode:</span></span>
- <span data-ttu-id="18699-142">실시간 보호가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="18699-143">On-demand scanning is turned on.</span><span class="sxs-lookup"><span data-stu-id="18699-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="18699-144">자동 위협 수정이 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="18699-145">보안 인텔리전스 업데이트가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="18699-146">상태 메뉴 아이콘이 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="18699-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-147">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-147">**Key**</span></span> | <span data-ttu-id="18699-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="18699-148">passiveMode</span></span> |
| <span data-ttu-id="18699-149">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-149">**Data type**</span></span> | <span data-ttu-id="18699-150">부울</span><span class="sxs-lookup"><span data-stu-id="18699-150">Boolean</span></span> |
| <span data-ttu-id="18699-151">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-151">**Possible values**</span></span> | <span data-ttu-id="18699-152">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-152">false (default)</span></span> <br/> <span data-ttu-id="18699-153">true</span><span class="sxs-lookup"><span data-stu-id="18699-153">true</span></span> |
| <span data-ttu-id="18699-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-154">**Comments**</span></span> | <span data-ttu-id="18699-155">Endpoint 버전 100.67.60 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="18699-156">제외 병합 정책</span><span class="sxs-lookup"><span data-stu-id="18699-156">Exclusion merge policy</span></span>

<span data-ttu-id="18699-157">제외에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="18699-158">관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()만 조합할 `merge` 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="18699-159">이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-160">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-160">**Key**</span></span> | <span data-ttu-id="18699-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="18699-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="18699-162">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-162">**Data type**</span></span> | <span data-ttu-id="18699-163">String</span><span class="sxs-lookup"><span data-stu-id="18699-163">String</span></span> |
| <span data-ttu-id="18699-164">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-164">**Possible values**</span></span> | <span data-ttu-id="18699-165">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-165">merge (default)</span></span> <br/> <span data-ttu-id="18699-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="18699-166">admin_only</span></span> |
| <span data-ttu-id="18699-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-167">**Comments**</span></span> | <span data-ttu-id="18699-168">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="18699-169">제외 검사</span><span class="sxs-lookup"><span data-stu-id="18699-169">Scan exclusions</span></span>

<span data-ttu-id="18699-170">검사에서 제외된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="18699-171">제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-172">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-172">**Key**</span></span> | <span data-ttu-id="18699-173">제외</span><span class="sxs-lookup"><span data-stu-id="18699-173">exclusions</span></span> |
| <span data-ttu-id="18699-174">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-174">**Data type**</span></span> | <span data-ttu-id="18699-175">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="18699-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="18699-176">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-176">**Comments**</span></span> | <span data-ttu-id="18699-177">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18699-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="18699-178">**제외 유형**</span><span class="sxs-lookup"><span data-stu-id="18699-178">**Type of exclusion**</span></span>

<span data-ttu-id="18699-179">검색에서 제외된 콘텐츠의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-180">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-180">**Key**</span></span> | <span data-ttu-id="18699-181">$type</span><span class="sxs-lookup"><span data-stu-id="18699-181">$type</span></span> |
| <span data-ttu-id="18699-182">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-182">**Data type**</span></span> | <span data-ttu-id="18699-183">String</span><span class="sxs-lookup"><span data-stu-id="18699-183">String</span></span> |
| <span data-ttu-id="18699-184">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-184">**Possible values**</span></span> | <span data-ttu-id="18699-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="18699-185">excludedPath</span></span> <br/> <span data-ttu-id="18699-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="18699-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="18699-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="18699-187">excludedFileName</span></span> |
|||

<span data-ttu-id="18699-188">**제외된 콘텐츠의 경로**</span><span class="sxs-lookup"><span data-stu-id="18699-188">**Path to excluded content**</span></span>

<span data-ttu-id="18699-189">전체 파일 경로로 검색에서 콘텐츠를 제외하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-190">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-190">**Key**</span></span> | <span data-ttu-id="18699-191">path</span><span class="sxs-lookup"><span data-stu-id="18699-191">path</span></span> |
| <span data-ttu-id="18699-192">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-192">**Data type**</span></span> | <span data-ttu-id="18699-193">String</span><span class="sxs-lookup"><span data-stu-id="18699-193">String</span></span> |
| <span data-ttu-id="18699-194">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-194">**Possible values**</span></span> | <span data-ttu-id="18699-195">유효한 경로</span><span class="sxs-lookup"><span data-stu-id="18699-195">valid paths</span></span> |
| <span data-ttu-id="18699-196">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-196">**Comments**</span></span> | <span data-ttu-id="18699-197">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="18699-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="18699-198">**경로 유형(파일/디렉터리)**</span><span class="sxs-lookup"><span data-stu-id="18699-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="18699-199">path *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18699-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="18699-200">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-200">**Key**</span></span> | <span data-ttu-id="18699-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="18699-201">isDirectory</span></span> |
| <span data-ttu-id="18699-202">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-202">**Data type**</span></span> | <span data-ttu-id="18699-203">부울</span><span class="sxs-lookup"><span data-stu-id="18699-203">Boolean</span></span> |
| <span data-ttu-id="18699-204">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-204">**Possible values**</span></span> | <span data-ttu-id="18699-205">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-205">false (default)</span></span> <br/> <span data-ttu-id="18699-206">true</span><span class="sxs-lookup"><span data-stu-id="18699-206">true</span></span> |
| <span data-ttu-id="18699-207">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-207">**Comments**</span></span> | <span data-ttu-id="18699-208">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="18699-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="18699-209">**검사에서 제외된 파일 확장명**</span><span class="sxs-lookup"><span data-stu-id="18699-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="18699-210">파일 확장명에 의해 검색에서 콘텐츠를 제외하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-211">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-211">**Key**</span></span> | <span data-ttu-id="18699-212">extension</span><span class="sxs-lookup"><span data-stu-id="18699-212">extension</span></span> |
| <span data-ttu-id="18699-213">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-213">**Data type**</span></span> | <span data-ttu-id="18699-214">String</span><span class="sxs-lookup"><span data-stu-id="18699-214">String</span></span> |
| <span data-ttu-id="18699-215">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-215">**Possible values**</span></span> | <span data-ttu-id="18699-216">유효한 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="18699-216">valid file extensions</span></span> |
| <span data-ttu-id="18699-217">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-217">**Comments**</span></span> | <span data-ttu-id="18699-218">제외된  *$type FileExtension만 적용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="18699-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="18699-219">**검사에서 제외된 프로세스**</span><span class="sxs-lookup"><span data-stu-id="18699-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="18699-220">모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="18699-221">프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-222">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-222">**Key**</span></span> | <span data-ttu-id="18699-223">name</span><span class="sxs-lookup"><span data-stu-id="18699-223">name</span></span> |
| <span data-ttu-id="18699-224">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-224">**Data type**</span></span> | <span data-ttu-id="18699-225">String</span><span class="sxs-lookup"><span data-stu-id="18699-225">String</span></span> |
| <span data-ttu-id="18699-226">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-226">**Possible values**</span></span> | <span data-ttu-id="18699-227">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="18699-227">any string</span></span> |
| <span data-ttu-id="18699-228">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-228">**Comments**</span></span> | <span data-ttu-id="18699-229">*excludedFileName이 $type만 적용할 수 있습니다.* </span><span class="sxs-lookup"><span data-stu-id="18699-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="18699-230">허용되는 위협</span><span class="sxs-lookup"><span data-stu-id="18699-230">Allowed threats</span></span>

<span data-ttu-id="18699-231">제품에서 차단되지 않고 대신 실행할 수 있는 위협 목록(해당 이름으로 식별)입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-232">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-232">**Key**</span></span> | <span data-ttu-id="18699-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="18699-233">allowedThreats</span></span> |
| <span data-ttu-id="18699-234">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-234">**Data type**</span></span> | <span data-ttu-id="18699-235">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="18699-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="18699-236">위협 작업 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-236">Disallowed threat actions</span></span>

<span data-ttu-id="18699-237">위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="18699-238">이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-239">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-239">**Key**</span></span> | <span data-ttu-id="18699-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="18699-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="18699-241">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-241">**Data type**</span></span> | <span data-ttu-id="18699-242">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="18699-242">Array of strings</span></span> |
| <span data-ttu-id="18699-243">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-243">**Possible values**</span></span> | <span data-ttu-id="18699-244">allow (restricts users from allow threats)</span><span class="sxs-lookup"><span data-stu-id="18699-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="18699-245">restore(사용자가 검지에서 위협을 복원하는 것을 제한함)</span><span class="sxs-lookup"><span data-stu-id="18699-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="18699-246">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-246">**Comments**</span></span> | <span data-ttu-id="18699-247">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="18699-248">위협 유형 설정</span><span class="sxs-lookup"><span data-stu-id="18699-248">Threat type settings</span></span>

<span data-ttu-id="18699-249">바이러스 *백신 엔진의 threatTypeSettings* 기본 설정은 특정 위협 유형이 제품에서 처리되는 방법을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-250">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-250">**Key**</span></span> | <span data-ttu-id="18699-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="18699-251">threatTypeSettings</span></span> |
| <span data-ttu-id="18699-252">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-252">**Data type**</span></span> | <span data-ttu-id="18699-253">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="18699-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="18699-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-254">**Comments**</span></span> | <span data-ttu-id="18699-255">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18699-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="18699-256">**위협 유형**</span><span class="sxs-lookup"><span data-stu-id="18699-256">**Threat type**</span></span>

<span data-ttu-id="18699-257">동작이 구성된 위협 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-258">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-258">**Key**</span></span> | <span data-ttu-id="18699-259">키</span><span class="sxs-lookup"><span data-stu-id="18699-259">key</span></span> |
| <span data-ttu-id="18699-260">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-260">**Data type**</span></span> | <span data-ttu-id="18699-261">String</span><span class="sxs-lookup"><span data-stu-id="18699-261">String</span></span> |
| <span data-ttu-id="18699-262">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-262">**Possible values**</span></span> | <span data-ttu-id="18699-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="18699-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="18699-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="18699-264">archive_bomb</span></span> |
|||

<span data-ttu-id="18699-265">**수행할 작업**</span><span class="sxs-lookup"><span data-stu-id="18699-265">**Action to take**</span></span>

<span data-ttu-id="18699-266">이전 섹션에 지정된 유형의 위협에 부과될 때 취할 조치입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="18699-267">다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-267">Can be:</span></span>

- <span data-ttu-id="18699-268">**감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="18699-269">**차단:** 이 유형의 위협으로부터 장치가 보호되고 보안 콘솔에 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="18699-270">**Off:** 이 유형의 위협으로부터 장치가 보호되지는 않습니다. 아무것도 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-271">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-271">**Key**</span></span> | <span data-ttu-id="18699-272">값</span><span class="sxs-lookup"><span data-stu-id="18699-272">value</span></span> |
| <span data-ttu-id="18699-273">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-273">**Data type**</span></span> | <span data-ttu-id="18699-274">String</span><span class="sxs-lookup"><span data-stu-id="18699-274">String</span></span> |
| <span data-ttu-id="18699-275">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-275">**Possible values**</span></span> | <span data-ttu-id="18699-276">감사(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-276">audit (default)</span></span> <br/> <span data-ttu-id="18699-277">block</span><span class="sxs-lookup"><span data-stu-id="18699-277">block</span></span> <br/> <span data-ttu-id="18699-278">off</span><span class="sxs-lookup"><span data-stu-id="18699-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="18699-279">위협 유형 설정 병합 정책</span><span class="sxs-lookup"><span data-stu-id="18699-279">Threat type settings merge policy</span></span>

<span data-ttu-id="18699-280">위협 유형 설정에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="18699-281">이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="18699-282">이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-283">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-283">**Key**</span></span> | <span data-ttu-id="18699-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="18699-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="18699-285">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-285">**Data type**</span></span> | <span data-ttu-id="18699-286">String</span><span class="sxs-lookup"><span data-stu-id="18699-286">String</span></span> |
| <span data-ttu-id="18699-287">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-287">**Possible values**</span></span> | <span data-ttu-id="18699-288">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-288">merge (default)</span></span> <br/> <span data-ttu-id="18699-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="18699-289">admin_only</span></span> |
| <span data-ttu-id="18699-290">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-290">**Comments**</span></span> | <span data-ttu-id="18699-291">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="18699-292">바이러스 백신 검사 기록 보존(일)</span><span class="sxs-lookup"><span data-stu-id="18699-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="18699-293">장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="18699-294">이전 검사 결과가 기록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="18699-295">디스크에서 제거된 오래된 고지된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-296">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-296">**Key**</span></span> | <span data-ttu-id="18699-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="18699-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="18699-298">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-298">**Data type**</span></span> | <span data-ttu-id="18699-299">String</span><span class="sxs-lookup"><span data-stu-id="18699-299">String</span></span> |
| <span data-ttu-id="18699-300">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-300">**Possible values**</span></span> | <span data-ttu-id="18699-301">90(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-301">90 (default).</span></span> <span data-ttu-id="18699-302">허용되는 값은 1일에서 180일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="18699-303">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-303">**Comments**</span></span> | <span data-ttu-id="18699-304">Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="18699-305">바이러스 백신 검사 기록의 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="18699-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="18699-306">검사 기록에 유지할 최대 항목 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="18699-307">항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-308">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-308">**Key**</span></span> | <span data-ttu-id="18699-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="18699-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="18699-310">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-310">**Data type**</span></span> | <span data-ttu-id="18699-311">String</span><span class="sxs-lookup"><span data-stu-id="18699-311">String</span></span> |
| <span data-ttu-id="18699-312">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-312">**Possible values**</span></span> | <span data-ttu-id="18699-313">10000(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-313">10000 (default).</span></span> <span data-ttu-id="18699-314">허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="18699-315">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-315">**Comments**</span></span> | <span data-ttu-id="18699-316">Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="18699-317">클라우드 제공 보호 기본 설정</span><span class="sxs-lookup"><span data-stu-id="18699-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="18699-318">구성 *프로필의 cloudService* 항목은 제품의 클라우드 기반 보호 기능을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-319">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-319">**Key**</span></span> | <span data-ttu-id="18699-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="18699-320">cloudService</span></span> |
| <span data-ttu-id="18699-321">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-321">**Data type**</span></span> | <span data-ttu-id="18699-322">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="18699-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="18699-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="18699-323">**Comments**</span></span> | <span data-ttu-id="18699-324">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18699-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="18699-325">클라우드 제공 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="18699-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="18699-326">장치에서 클라우드 제공 보호를 사용할지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="18699-327">서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-328">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-328">**Key**</span></span> | <span data-ttu-id="18699-329">활성화됨</span><span class="sxs-lookup"><span data-stu-id="18699-329">enabled</span></span> |
| <span data-ttu-id="18699-330">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-330">**Data type**</span></span> | <span data-ttu-id="18699-331">부울</span><span class="sxs-lookup"><span data-stu-id="18699-331">Boolean</span></span> |
| <span data-ttu-id="18699-332">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-332">**Possible values**</span></span> | <span data-ttu-id="18699-333">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-333">true (default)</span></span> <br/> <span data-ttu-id="18699-334">false</span><span class="sxs-lookup"><span data-stu-id="18699-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="18699-335">진단 수집 수준</span><span class="sxs-lookup"><span data-stu-id="18699-335">Diagnostic collection level</span></span>

<span data-ttu-id="18699-336">진단 데이터는 Endpoint용 Defender를 안전하고 최신 상태를 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="18699-337">이 설정은 제품이 Microsoft에 전송한 진단 수준을 결정하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-338">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-338">**Key**</span></span> | <span data-ttu-id="18699-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="18699-339">diagnosticLevel</span></span> |
| <span data-ttu-id="18699-340">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-340">**Data type**</span></span> | <span data-ttu-id="18699-341">String</span><span class="sxs-lookup"><span data-stu-id="18699-341">String</span></span> |
| <span data-ttu-id="18699-342">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-342">**Possible values**</span></span> | <span data-ttu-id="18699-343">선택 사항(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-343">optional (default)</span></span> <br/> <span data-ttu-id="18699-344">필수</span><span class="sxs-lookup"><span data-stu-id="18699-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="18699-345">자동 샘플 제출 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="18699-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="18699-346">의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="18699-347">샘플 제출을 제어하는 세 가지 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="18699-348">**없음:** 의심스러운 샘플이 Microsoft에 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="18699-349">**안전**: PII(개인 식별 정보)를 포함하지 않는 의심스러운 샘플만 자동으로 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="18699-350">이 설정의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="18699-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="18699-351">**모두:** 의심스러운 모든 샘플이 Microsoft에 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-352">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-352">**Key**</span></span> | <span data-ttu-id="18699-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="18699-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="18699-354">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-354">**Data type**</span></span> | <span data-ttu-id="18699-355">String</span><span class="sxs-lookup"><span data-stu-id="18699-355">String</span></span> |
| <span data-ttu-id="18699-356">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-356">**Possible values**</span></span> | <span data-ttu-id="18699-357">없음</span><span class="sxs-lookup"><span data-stu-id="18699-357">none</span></span> <br/> <span data-ttu-id="18699-358">안전(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-358">safe (default)</span></span> <br/> <span data-ttu-id="18699-359">all</span><span class="sxs-lookup"><span data-stu-id="18699-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="18699-360">자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="18699-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="18699-361">보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="18699-362">**키**</span><span class="sxs-lookup"><span data-stu-id="18699-362">**Key**</span></span> | <span data-ttu-id="18699-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="18699-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="18699-364">**Data type**</span><span class="sxs-lookup"><span data-stu-id="18699-364">**Data type**</span></span> | <span data-ttu-id="18699-365">부울</span><span class="sxs-lookup"><span data-stu-id="18699-365">Boolean</span></span> |
| <span data-ttu-id="18699-366">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="18699-366">**Possible values**</span></span> | <span data-ttu-id="18699-367">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="18699-367">true (default)</span></span> <br/> <span data-ttu-id="18699-368">false</span><span class="sxs-lookup"><span data-stu-id="18699-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="18699-369">권장 구성 프로필</span><span class="sxs-lookup"><span data-stu-id="18699-369">Recommended configuration profile</span></span>

<span data-ttu-id="18699-370">시작하려면 엔터프라이즈에서 다음과 같은 구성 프로필을 사용하여 Endpoint용 Defender에서 제공하는 모든 보호 기능을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="18699-371">다음 구성 프로필은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-371">The following configuration profile will:</span></span>

- <span data-ttu-id="18699-372">RTP(실시간 보호) 사용</span><span class="sxs-lookup"><span data-stu-id="18699-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="18699-373">다음 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="18699-374">**잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="18699-375">**보관함(압축률이** 높은 파일)이 제품 로그에 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="18699-376">자동 보안 인텔리전스 업데이트 사용</span><span class="sxs-lookup"><span data-stu-id="18699-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="18699-377">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="18699-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="18699-378">수준에서 자동 샘플 제출 `safe` 사용</span><span class="sxs-lookup"><span data-stu-id="18699-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="18699-379">샘플 프로필</span><span class="sxs-lookup"><span data-stu-id="18699-379">Sample profile</span></span>

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
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="18699-380">전체 구성 프로필 예제</span><span class="sxs-lookup"><span data-stu-id="18699-380">Full configuration profile example</span></span>

<span data-ttu-id="18699-381">다음 구성 프로필에는 이 문서에 설명된 모든 설정에 대한 항목이 포함되어 있으며 제품을 보다 잘 제어하려는 고급 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="18699-382">전체 프로필</span><span class="sxs-lookup"><span data-stu-id="18699-382">Full profile</span></span>

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
            "path":"/home"
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
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="18699-383">구성 프로필 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="18699-383">Configuration profile validation</span></span>

<span data-ttu-id="18699-384">구성 프로필은 유효한 JSON 형식 파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="18699-385">이를 확인하는 데 사용할 수 있는 도구는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="18699-386">예를 들어 장치에 `python` 설치한 경우:</span><span class="sxs-lookup"><span data-stu-id="18699-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="18699-387">JSON이 잘 구성되면 위의 명령은 터미널에 다시 출력하고 의 종료 코드를 `0` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="18699-388">그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="18699-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="18699-389">파일의 mdatp_managed.js올바르게 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="18699-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="18699-390">/etc/opt/microsoft/mdatp/managed/mdatp_managed.js제대로 작동하고 있는지 확인하려면 다음 설정 옆에 "[관리]"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="18699-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="18699-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="18699-391">cloud_enabled</span></span>
- <span data-ttu-id="18699-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="18699-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="18699-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="18699-393">passice_mode_enabled</span></span>
- <span data-ttu-id="18699-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="18699-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="18699-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="18699-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="18699-396">이 mdatp_managed.js적용하려면 wdavdaemon을 다시 시작할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="18699-397">구성 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="18699-397">Configuration profile deployment</span></span>

<span data-ttu-id="18699-398">엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 도구를 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="18699-399">Linux용 끝점용 Defender는 */etc/opt/microsoft/mdatp/managed/mdatp_managed.js* 관리되는 구성을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="18699-399">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
