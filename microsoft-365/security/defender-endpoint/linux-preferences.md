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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289496"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="aa039-104">Linux에서 끝점용 Microsoft Defender에 대한 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aa039-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="aa039-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa039-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aa039-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa039-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa039-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aa039-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="aa039-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aa039-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="aa039-110">이 항목에는 엔터프라이즈 환경에서 Linux에서 끝점용 Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="aa039-111">명령줄에서 디바이스에서 제품을 구성하는 데 관심이 있는 경우 리소스를 [참조하세요.](linux-resources.md#configure-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="aa039-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="aa039-112">엔터프라이즈 환경에서 Linux의 끝점용 Defender는 구성 프로필을 통해 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="aa039-113">이 프로필은 선택한 관리 도구에서 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="aa039-114">엔터프라이즈에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="aa039-115">즉, 기업의 사용자는 이 구성 프로필을 통해 설정된 기본 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="aa039-116">이 문서에서는 이 프로필의 구조(시작하는 데 사용할 수 있는 권장 프로필 포함)와 프로필 배포 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="aa039-117">구성 프로필 구조</span><span class="sxs-lookup"><span data-stu-id="aa039-117">Configuration profile structure</span></span>

<span data-ttu-id="aa039-118">구성 프로필은 키(기본 설정의 이름을 나타임)로 식별되는 항목과 기본 설정의 특성에 따라 값이 이어지는 .json 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="aa039-119">값은 숫자 값과 같이 단순하거나 중첩된 기본 설정 목록과 같은 복잡한 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="aa039-120">일반적으로 구성 관리 도구를 사용하여 위치에 이름이 있는 파일을 ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="aa039-121">구성 프로필의 최상위 수준에는 제품 수준 기본 설정 및 제품의 하위 항목에 대한 항목이 포함되어 있으며, 이 내용은 다음 섹션에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="aa039-122">바이러스 백신 엔진 기본 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-122">Antivirus engine preferences</span></span>

<span data-ttu-id="aa039-123">구성 *프로필의 antivirusEngine* 섹션은 제품의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="aa039-124">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-124">Description</span></span>|<span data-ttu-id="aa039-125">값</span><span class="sxs-lookup"><span data-stu-id="aa039-125">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-126">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-126">**Key**</span></span>|<span data-ttu-id="aa039-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="aa039-127">antivirusEngine</span></span>|
|<span data-ttu-id="aa039-128">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-128">**Data type**</span></span>|<span data-ttu-id="aa039-129">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="aa039-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="aa039-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-130">**Comments**</span></span>|<span data-ttu-id="aa039-131">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa039-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="aa039-132">실시간 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="aa039-133">실시간 보호(액세스할 때 파일 검색)를 사용할지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="aa039-134">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-134">Description</span></span>|<span data-ttu-id="aa039-135">값</span><span class="sxs-lookup"><span data-stu-id="aa039-135">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-136">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-136">**Key**</span></span>|<span data-ttu-id="aa039-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="aa039-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="aa039-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-138">**Data type**</span></span>|<span data-ttu-id="aa039-139">부울</span><span class="sxs-lookup"><span data-stu-id="aa039-139">Boolean</span></span>|
|<span data-ttu-id="aa039-140">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-140">**Possible values**</span></span>|<span data-ttu-id="aa039-141">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-141">true (default)</span></span> <p> <span data-ttu-id="aa039-142">false</span><span class="sxs-lookup"><span data-stu-id="aa039-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="aa039-143">수동 모드 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-143">Enable / disable passive mode</span></span>

<span data-ttu-id="aa039-144">바이러스 백신 엔진이 수동 모드에서 실행될지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="aa039-145">수동 모드:</span><span class="sxs-lookup"><span data-stu-id="aa039-145">In passive mode:</span></span>

- <span data-ttu-id="aa039-146">실시간 보호가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="aa039-147">On-demand scanning is turned on.</span><span class="sxs-lookup"><span data-stu-id="aa039-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="aa039-148">자동 위협 수정이 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="aa039-149">보안 인텔리전스 업데이트가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="aa039-150">상태 메뉴 아이콘이 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="aa039-151">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-151">Description</span></span>|<span data-ttu-id="aa039-152">값</span><span class="sxs-lookup"><span data-stu-id="aa039-152">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-153">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-153">**Key**</span></span>|<span data-ttu-id="aa039-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="aa039-154">passiveMode</span></span>|
|<span data-ttu-id="aa039-155">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-155">**Data type**</span></span>|<span data-ttu-id="aa039-156">부울</span><span class="sxs-lookup"><span data-stu-id="aa039-156">Boolean</span></span>|
|<span data-ttu-id="aa039-157">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-157">**Possible values**</span></span>|<span data-ttu-id="aa039-158">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-158">false (default)</span></span> <p> <span data-ttu-id="aa039-159">true</span><span class="sxs-lookup"><span data-stu-id="aa039-159">true</span></span>|
|<span data-ttu-id="aa039-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-160">**Comments**</span></span>|<span data-ttu-id="aa039-161">Endpoint 버전 100.67.60 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="aa039-162">제외 병합 정책</span><span class="sxs-lookup"><span data-stu-id="aa039-162">Exclusion merge policy</span></span>

<span data-ttu-id="aa039-163">제외에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="aa039-164">관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()만 조합할 `merge` 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="aa039-165">이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="aa039-166">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-166">Description</span></span>|<span data-ttu-id="aa039-167">값</span><span class="sxs-lookup"><span data-stu-id="aa039-167">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-168">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-168">**Key**</span></span>|<span data-ttu-id="aa039-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="aa039-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="aa039-170">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-170">**Data type**</span></span>|<span data-ttu-id="aa039-171">String</span><span class="sxs-lookup"><span data-stu-id="aa039-171">String</span></span>|
|<span data-ttu-id="aa039-172">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-172">**Possible values**</span></span>|<span data-ttu-id="aa039-173">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-173">merge (default)</span></span> <p> <span data-ttu-id="aa039-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="aa039-174">admin_only</span></span>|
|<span data-ttu-id="aa039-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-175">**Comments**</span></span>|<span data-ttu-id="aa039-176">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="aa039-177">제외 검사</span><span class="sxs-lookup"><span data-stu-id="aa039-177">Scan exclusions</span></span>

<span data-ttu-id="aa039-178">검사에서 제외된 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="aa039-179">제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="aa039-180">제외는 항목 배열로 지정됩니다. 관리자는 필요한 수의 요소를 순서에 따라 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="aa039-181">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-181">Description</span></span>|<span data-ttu-id="aa039-182">값</span><span class="sxs-lookup"><span data-stu-id="aa039-182">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-183">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-183">**Key**</span></span>|<span data-ttu-id="aa039-184">제외</span><span class="sxs-lookup"><span data-stu-id="aa039-184">exclusions</span></span>|
|<span data-ttu-id="aa039-185">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-185">**Data type**</span></span>|<span data-ttu-id="aa039-186">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="aa039-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="aa039-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-187">**Comments**</span></span>|<span data-ttu-id="aa039-188">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa039-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="aa039-189">제외 유형</span><span class="sxs-lookup"><span data-stu-id="aa039-189">Type of exclusion</span></span>

<span data-ttu-id="aa039-190">검색에서 제외된 콘텐츠의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="aa039-191">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-191">Description</span></span>|<span data-ttu-id="aa039-192">값</span><span class="sxs-lookup"><span data-stu-id="aa039-192">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-193">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-193">**Key**</span></span>|<span data-ttu-id="aa039-194">$type</span><span class="sxs-lookup"><span data-stu-id="aa039-194">$type</span></span>|
|<span data-ttu-id="aa039-195">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-195">**Data type**</span></span>|<span data-ttu-id="aa039-196">String</span><span class="sxs-lookup"><span data-stu-id="aa039-196">String</span></span>|
|<span data-ttu-id="aa039-197">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-197">**Possible values**</span></span>|<span data-ttu-id="aa039-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="aa039-198">excludedPath</span></span> <p> <span data-ttu-id="aa039-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="aa039-199">excludedFileExtension</span></span> <p> <span data-ttu-id="aa039-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="aa039-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="aa039-201">제외된 콘텐츠의 경로</span><span class="sxs-lookup"><span data-stu-id="aa039-201">Path to excluded content</span></span>

<span data-ttu-id="aa039-202">전체 파일 경로로 검색에서 콘텐츠를 제외하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="aa039-203">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-203">Description</span></span>|<span data-ttu-id="aa039-204">값</span><span class="sxs-lookup"><span data-stu-id="aa039-204">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-205">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-205">**Key**</span></span>|<span data-ttu-id="aa039-206">path</span><span class="sxs-lookup"><span data-stu-id="aa039-206">path</span></span>|
|<span data-ttu-id="aa039-207">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-207">**Data type**</span></span>|<span data-ttu-id="aa039-208">String</span><span class="sxs-lookup"><span data-stu-id="aa039-208">String</span></span>|
|<span data-ttu-id="aa039-209">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-209">**Possible values**</span></span>|<span data-ttu-id="aa039-210">유효한 경로</span><span class="sxs-lookup"><span data-stu-id="aa039-210">valid paths</span></span>|
|<span data-ttu-id="aa039-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-211">**Comments**</span></span>|<span data-ttu-id="aa039-212">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="aa039-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="aa039-213">경로 유형(파일/디렉터리)</span><span class="sxs-lookup"><span data-stu-id="aa039-213">Path type (file / directory)</span></span>

<span data-ttu-id="aa039-214">path *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="aa039-215">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-215">Description</span></span>|<span data-ttu-id="aa039-216">값</span><span class="sxs-lookup"><span data-stu-id="aa039-216">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-217">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-217">**Key**</span></span>|<span data-ttu-id="aa039-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="aa039-218">isDirectory</span></span>|
|<span data-ttu-id="aa039-219">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-219">**Data type**</span></span>|<span data-ttu-id="aa039-220">부울</span><span class="sxs-lookup"><span data-stu-id="aa039-220">Boolean</span></span>|
|<span data-ttu-id="aa039-221">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-221">**Possible values**</span></span>|<span data-ttu-id="aa039-222">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-222">false (default)</span></span> <p> <span data-ttu-id="aa039-223">true</span><span class="sxs-lookup"><span data-stu-id="aa039-223">true</span></span>|
|<span data-ttu-id="aa039-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-224">**Comments**</span></span>|<span data-ttu-id="aa039-225">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="aa039-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="aa039-226">검사에서 제외된 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="aa039-226">File extension excluded from the scan</span></span>

<span data-ttu-id="aa039-227">파일 확장명에 의해 검색에서 콘텐츠를 제외하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="aa039-228">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-228">Description</span></span>|<span data-ttu-id="aa039-229">값</span><span class="sxs-lookup"><span data-stu-id="aa039-229">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-230">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-230">**Key**</span></span>|<span data-ttu-id="aa039-231">extension</span><span class="sxs-lookup"><span data-stu-id="aa039-231">extension</span></span>|
|<span data-ttu-id="aa039-232">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-232">**Data type**</span></span>|<span data-ttu-id="aa039-233">String</span><span class="sxs-lookup"><span data-stu-id="aa039-233">String</span></span>|
|<span data-ttu-id="aa039-234">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-234">**Possible values**</span></span>|<span data-ttu-id="aa039-235">유효한 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="aa039-235">valid file extensions</span></span>|
|<span data-ttu-id="aa039-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-236">**Comments**</span></span>|<span data-ttu-id="aa039-237">제외된  *$type FileExtension만 적용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="aa039-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="aa039-238">검사에서 제외된 프로세스\*</span><span class="sxs-lookup"><span data-stu-id="aa039-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="aa039-239">모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="aa039-240">프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="aa039-241">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-241">Description</span></span>|<span data-ttu-id="aa039-242">값</span><span class="sxs-lookup"><span data-stu-id="aa039-242">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-243">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-243">**Key**</span></span>|<span data-ttu-id="aa039-244">name</span><span class="sxs-lookup"><span data-stu-id="aa039-244">name</span></span>|
|<span data-ttu-id="aa039-245">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-245">**Data type**</span></span>|<span data-ttu-id="aa039-246">String</span><span class="sxs-lookup"><span data-stu-id="aa039-246">String</span></span>|
|<span data-ttu-id="aa039-247">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-247">**Possible values**</span></span>|<span data-ttu-id="aa039-248">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="aa039-248">any string</span></span>|
|<span data-ttu-id="aa039-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-249">**Comments**</span></span>|<span data-ttu-id="aa039-250">*excludedFileName이 $type만 적용할 수 있습니다.* </span><span class="sxs-lookup"><span data-stu-id="aa039-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="aa039-251">허용되는 위협</span><span class="sxs-lookup"><span data-stu-id="aa039-251">Allowed threats</span></span>

<span data-ttu-id="aa039-252">제품에서 차단되지 않고 대신 실행할 수 있는 위협 목록(해당 이름으로 식별)입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="aa039-253">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-253">Description</span></span>|<span data-ttu-id="aa039-254">값</span><span class="sxs-lookup"><span data-stu-id="aa039-254">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-255">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-255">**Key**</span></span>|<span data-ttu-id="aa039-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="aa039-256">allowedThreats</span></span>|
|<span data-ttu-id="aa039-257">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-257">**Data type**</span></span>|<span data-ttu-id="aa039-258">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="aa039-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="aa039-259">위협 작업 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-259">Disallowed threat actions</span></span>

<span data-ttu-id="aa039-260">위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="aa039-261">이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="aa039-262">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-262">Description</span></span>|<span data-ttu-id="aa039-263">값</span><span class="sxs-lookup"><span data-stu-id="aa039-263">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-264">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-264">**Key**</span></span>|<span data-ttu-id="aa039-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="aa039-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="aa039-266">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-266">**Data type**</span></span>|<span data-ttu-id="aa039-267">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="aa039-267">Array of strings</span></span>|
|<span data-ttu-id="aa039-268">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-268">**Possible values**</span></span>|<span data-ttu-id="aa039-269">allow (restricts users from allow threats)</span><span class="sxs-lookup"><span data-stu-id="aa039-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="aa039-270">restore(사용자가 검지에서 위협을 복원하는 것을 제한함)</span><span class="sxs-lookup"><span data-stu-id="aa039-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="aa039-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-271">**Comments**</span></span>|<span data-ttu-id="aa039-272">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="aa039-273">위협 유형 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-273">Threat type settings</span></span>

<span data-ttu-id="aa039-274">바이러스 *백신 엔진의 threatTypeSettings* 기본 설정은 특정 위협 유형이 제품에서 처리되는 방법을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="aa039-275">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-275">Description</span></span>|<span data-ttu-id="aa039-276">값</span><span class="sxs-lookup"><span data-stu-id="aa039-276">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-277">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-277">**Key**</span></span>|<span data-ttu-id="aa039-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="aa039-278">threatTypeSettings</span></span>|
|<span data-ttu-id="aa039-279">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-279">**Data type**</span></span>|<span data-ttu-id="aa039-280">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="aa039-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="aa039-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-281">**Comments**</span></span>|<span data-ttu-id="aa039-282">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa039-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="aa039-283">위협 유형</span><span class="sxs-lookup"><span data-stu-id="aa039-283">Threat type</span></span>

<span data-ttu-id="aa039-284">동작이 구성된 위협 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="aa039-285">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-285">Description</span></span>|<span data-ttu-id="aa039-286">값</span><span class="sxs-lookup"><span data-stu-id="aa039-286">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-287">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-287">**Key**</span></span>|<span data-ttu-id="aa039-288">키</span><span class="sxs-lookup"><span data-stu-id="aa039-288">key</span></span>|
|<span data-ttu-id="aa039-289">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-289">**Data type**</span></span>|<span data-ttu-id="aa039-290">String</span><span class="sxs-lookup"><span data-stu-id="aa039-290">String</span></span>|
|<span data-ttu-id="aa039-291">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-291">**Possible values**</span></span>|<span data-ttu-id="aa039-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="aa039-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="aa039-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="aa039-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="aa039-294">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="aa039-294">Action to take</span></span>

<span data-ttu-id="aa039-295">이전 섹션에 지정된 유형의 위협에 부과될 때 취할 조치입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="aa039-296">다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-296">Can be:</span></span>

- <span data-ttu-id="aa039-297">**감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="aa039-298">**차단:** 이 유형의 위협으로부터 장치가 보호되고 보안 콘솔에 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="aa039-299">**Off:** 이 유형의 위협으로부터 장치가 보호되지는 않습니다. 아무것도 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="aa039-300">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-300">Description</span></span>|<span data-ttu-id="aa039-301">값</span><span class="sxs-lookup"><span data-stu-id="aa039-301">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-302">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-302">**Key**</span></span>|<span data-ttu-id="aa039-303">값</span><span class="sxs-lookup"><span data-stu-id="aa039-303">value</span></span>|
|<span data-ttu-id="aa039-304">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-304">**Data type**</span></span>|<span data-ttu-id="aa039-305">String</span><span class="sxs-lookup"><span data-stu-id="aa039-305">String</span></span>|
|<span data-ttu-id="aa039-306">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-306">**Possible values**</span></span>|<span data-ttu-id="aa039-307">감사(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-307">audit (default)</span></span> <p> <span data-ttu-id="aa039-308">block</span><span class="sxs-lookup"><span data-stu-id="aa039-308">block</span></span> <p> <span data-ttu-id="aa039-309">off</span><span class="sxs-lookup"><span data-stu-id="aa039-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="aa039-310">위협 유형 설정 병합 정책</span><span class="sxs-lookup"><span data-stu-id="aa039-310">Threat type settings merge policy</span></span>

<span data-ttu-id="aa039-311">위협 유형 설정에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="aa039-312">이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="aa039-313">이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="aa039-314">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-314">Description</span></span>|<span data-ttu-id="aa039-315">값</span><span class="sxs-lookup"><span data-stu-id="aa039-315">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-316">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-316">**Key**</span></span>|<span data-ttu-id="aa039-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="aa039-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="aa039-318">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-318">**Data type**</span></span>|<span data-ttu-id="aa039-319">String</span><span class="sxs-lookup"><span data-stu-id="aa039-319">String</span></span>|
|<span data-ttu-id="aa039-320">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-320">**Possible values**</span></span>|<span data-ttu-id="aa039-321">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-321">merge (default)</span></span> <p> <span data-ttu-id="aa039-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="aa039-322">admin_only</span></span>|
|<span data-ttu-id="aa039-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-323">**Comments**</span></span>|<span data-ttu-id="aa039-324">Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="aa039-325">바이러스 백신 검사 기록 보존(일)</span><span class="sxs-lookup"><span data-stu-id="aa039-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="aa039-326">장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="aa039-327">이전 검사 결과가 기록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="aa039-328">디스크에서 제거된 오래된 고지된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="aa039-329">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-329">Description</span></span>|<span data-ttu-id="aa039-330">값</span><span class="sxs-lookup"><span data-stu-id="aa039-330">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-331">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-331">**Key**</span></span>|<span data-ttu-id="aa039-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="aa039-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="aa039-333">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-333">**Data type**</span></span>|<span data-ttu-id="aa039-334">String</span><span class="sxs-lookup"><span data-stu-id="aa039-334">String</span></span>|
|<span data-ttu-id="aa039-335">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-335">**Possible values**</span></span>|<span data-ttu-id="aa039-336">90(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-336">90 (default).</span></span> <span data-ttu-id="aa039-337">허용되는 값은 1일에서 180일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="aa039-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-338">**Comments**</span></span>|<span data-ttu-id="aa039-339">Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="aa039-340">바이러스 백신 검사 기록의 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="aa039-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="aa039-341">검사 기록에 유지할 최대 항목 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="aa039-342">항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="aa039-343">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-343">Description</span></span>|<span data-ttu-id="aa039-344">값</span><span class="sxs-lookup"><span data-stu-id="aa039-344">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-345">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-345">**Key**</span></span>|<span data-ttu-id="aa039-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="aa039-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="aa039-347">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-347">**Data type**</span></span>|<span data-ttu-id="aa039-348">String</span><span class="sxs-lookup"><span data-stu-id="aa039-348">String</span></span>|
|<span data-ttu-id="aa039-349">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-349">**Possible values**</span></span>|<span data-ttu-id="aa039-350">10000(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-350">10000 (default).</span></span> <span data-ttu-id="aa039-351">허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="aa039-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-352">**Comments**</span></span>|<span data-ttu-id="aa039-353">Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="aa039-354">클라우드 제공 보호 기본 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="aa039-355">구성 *프로필의 cloudService* 항목은 제품의 클라우드 기반 보호 기능을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="aa039-356">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-356">Description</span></span>|<span data-ttu-id="aa039-357">값</span><span class="sxs-lookup"><span data-stu-id="aa039-357">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-358">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-358">**Key**</span></span>|<span data-ttu-id="aa039-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="aa039-359">cloudService</span></span>|
|<span data-ttu-id="aa039-360">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-360">**Data type**</span></span>|<span data-ttu-id="aa039-361">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="aa039-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="aa039-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="aa039-362">**Comments**</span></span>|<span data-ttu-id="aa039-363">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa039-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="aa039-364">클라우드 제공 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="aa039-365">장치에서 클라우드 제공 보호를 사용할지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="aa039-366">서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="aa039-367">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-367">Description</span></span>|<span data-ttu-id="aa039-368">값</span><span class="sxs-lookup"><span data-stu-id="aa039-368">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-369">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-369">**Key**</span></span>|<span data-ttu-id="aa039-370">활성화됨</span><span class="sxs-lookup"><span data-stu-id="aa039-370">enabled</span></span>|
|<span data-ttu-id="aa039-371">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-371">**Data type**</span></span>|<span data-ttu-id="aa039-372">부울</span><span class="sxs-lookup"><span data-stu-id="aa039-372">Boolean</span></span>|
|<span data-ttu-id="aa039-373">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-373">**Possible values**</span></span>|<span data-ttu-id="aa039-374">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-374">true (default)</span></span> <p> <span data-ttu-id="aa039-375">false</span><span class="sxs-lookup"><span data-stu-id="aa039-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="aa039-376">진단 수집 수준</span><span class="sxs-lookup"><span data-stu-id="aa039-376">Diagnostic collection level</span></span>

<span data-ttu-id="aa039-377">진단 데이터는 Endpoint용 Defender를 안전하고 최신 상태를 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="aa039-378">이 설정은 제품이 Microsoft에 전송한 진단 수준을 결정하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="aa039-379">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-379">Description</span></span>|<span data-ttu-id="aa039-380">값</span><span class="sxs-lookup"><span data-stu-id="aa039-380">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-381">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-381">**Key**</span></span>|<span data-ttu-id="aa039-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="aa039-382">diagnosticLevel</span></span>|
|<span data-ttu-id="aa039-383">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-383">**Data type**</span></span>|<span data-ttu-id="aa039-384">String</span><span class="sxs-lookup"><span data-stu-id="aa039-384">String</span></span>|
|<span data-ttu-id="aa039-385">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-385">**Possible values**</span></span>|<span data-ttu-id="aa039-386">선택 사항(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-386">optional (default)</span></span> <p> <span data-ttu-id="aa039-387">필수</span><span class="sxs-lookup"><span data-stu-id="aa039-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="aa039-388">자동 샘플 제출 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="aa039-389">의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="aa039-390">샘플 제출을 제어하는 세 가지 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="aa039-391">**없음:** 의심스러운 샘플이 Microsoft에 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="aa039-392">**금고**: PII(개인 식별 정보)를 포함하지 않는 의심스러운 샘플만 자동으로 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="aa039-393">이 설정의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="aa039-394">**모두:** 의심스러운 모든 샘플이 Microsoft에 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="aa039-395">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-395">Description</span></span>|<span data-ttu-id="aa039-396">값</span><span class="sxs-lookup"><span data-stu-id="aa039-396">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-397">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-397">**Key**</span></span>|<span data-ttu-id="aa039-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="aa039-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="aa039-399">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-399">**Data type**</span></span>|<span data-ttu-id="aa039-400">String</span><span class="sxs-lookup"><span data-stu-id="aa039-400">String</span></span>|
|<span data-ttu-id="aa039-401">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-401">**Possible values**</span></span>|<span data-ttu-id="aa039-402">없음</span><span class="sxs-lookup"><span data-stu-id="aa039-402">none</span></span> <p> <span data-ttu-id="aa039-403">안전(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-403">safe (default)</span></span> <p> <span data-ttu-id="aa039-404">all</span><span class="sxs-lookup"><span data-stu-id="aa039-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="aa039-405">자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="aa039-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="aa039-406">보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="aa039-407">설명</span><span class="sxs-lookup"><span data-stu-id="aa039-407">Description</span></span>|<span data-ttu-id="aa039-408">값</span><span class="sxs-lookup"><span data-stu-id="aa039-408">Value</span></span>|
|---|---|
|<span data-ttu-id="aa039-409">**키**</span><span class="sxs-lookup"><span data-stu-id="aa039-409">**Key**</span></span>|<span data-ttu-id="aa039-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="aa039-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="aa039-411">**Data type**</span><span class="sxs-lookup"><span data-stu-id="aa039-411">**Data type**</span></span>|<span data-ttu-id="aa039-412">부울</span><span class="sxs-lookup"><span data-stu-id="aa039-412">Boolean</span></span>|
|<span data-ttu-id="aa039-413">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="aa039-413">**Possible values**</span></span>|<span data-ttu-id="aa039-414">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="aa039-414">true (default)</span></span> <p> <span data-ttu-id="aa039-415">false</span><span class="sxs-lookup"><span data-stu-id="aa039-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="aa039-416">권장 구성 프로필</span><span class="sxs-lookup"><span data-stu-id="aa039-416">Recommended configuration profile</span></span>

<span data-ttu-id="aa039-417">시작하려면 엔터프라이즈에서 다음과 같은 구성 프로필을 사용하여 Endpoint용 Defender에서 제공하는 모든 보호 기능을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="aa039-418">다음 구성 프로필은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-418">The following configuration profile will:</span></span>

- <span data-ttu-id="aa039-419">RTP(실시간 보호) 사용</span><span class="sxs-lookup"><span data-stu-id="aa039-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="aa039-420">다음 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="aa039-421">**잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="aa039-422">**보관함(압축률이** 높은 파일)이 제품 로그에 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="aa039-423">자동 보안 인텔리전스 업데이트 사용</span><span class="sxs-lookup"><span data-stu-id="aa039-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="aa039-424">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="aa039-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="aa039-425">수준에서 자동 샘플 제출 `safe` 사용</span><span class="sxs-lookup"><span data-stu-id="aa039-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="aa039-426">샘플 프로필</span><span class="sxs-lookup"><span data-stu-id="aa039-426">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="aa039-427">전체 구성 프로필 예제</span><span class="sxs-lookup"><span data-stu-id="aa039-427">Full configuration profile example</span></span>

<span data-ttu-id="aa039-428">다음 구성 프로필에는 이 문서에 설명된 모든 설정에 대한 항목이 포함되어 있으며 제품을 보다 잘 제어하려는 고급 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="aa039-429">전체 프로필</span><span class="sxs-lookup"><span data-stu-id="aa039-429">Full profile</span></span>

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
            "extension":".pdf"
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

## <a name="configuration-profile-validation"></a><span data-ttu-id="aa039-430">구성 프로필 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="aa039-430">Configuration profile validation</span></span>

<span data-ttu-id="aa039-431">구성 프로필은 유효한 JSON 형식 파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="aa039-432">이를 확인하는 데 사용할 수 있는 도구는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="aa039-433">예를 들어 장치에 `python` 설치한 경우:</span><span class="sxs-lookup"><span data-stu-id="aa039-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="aa039-434">JSON이 잘 구성되면 위의 명령은 터미널에 다시 출력하고 의 종료 코드를 `0` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="aa039-435">그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="aa039-436">파일의 mdatp_managed.js올바르게 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="aa039-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="aa039-437">/etc/opt/microsoft/mdatp/managed/mdatp_managed.js제대로 작동하고 있는지 확인하려면 다음 설정 옆에 "[관리]"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="aa039-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="aa039-438">cloud_enabled</span></span>
- <span data-ttu-id="aa039-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="aa039-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="aa039-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="aa039-440">passive_mode_enabled</span></span>
- <span data-ttu-id="aa039-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="aa039-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="aa039-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="aa039-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="aa039-443">이 mdatp_managed.js적용하려면 wdavdaemon을 다시 시작할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="aa039-444">구성 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="aa039-444">Configuration profile deployment</span></span>

<span data-ttu-id="aa039-445">엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 도구를 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="aa039-446">Linux의 끝점용 Defender는 */etc/opt/microsoft/mdatp/managed/mdatp_managed.js* 관리되는 구성을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="aa039-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
