---
title: Mac의 끝점에 대한 Microsoft Defender 기본 설정 설정
description: 엔터프라이즈 조직에서 Mac의 끝점에 대해 MMicrosoft Defender를 구성합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 관리, 기본 설정, 엔터프라이즈, intune, jamf, macos, 카탈로나, mojave, high sierra
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
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346405"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="44220-104">macOS의 끝점에 대한 Microsoft Defender 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="44220-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44220-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="44220-105">**Applies to:**</span></span>

- [<span data-ttu-id="44220-106">Microsoft Defender for Endpoint(macOS용)</span><span class="sxs-lookup"><span data-stu-id="44220-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="44220-107">이 문서에는 엔터프라이즈 조직의 macOS에서 끝점용 Microsoft Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="44220-108">명령줄 인터페이스를 사용하여 macOS에서 끝점에 대한 Microsoft Defender를 구성하는 데 필요한 리소스는 리소스를 [참조합니다.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="44220-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="44220-109">요약</span><span class="sxs-lookup"><span data-stu-id="44220-109">Summary</span></span>

<span data-ttu-id="44220-110">엔터프라이즈 조직에서 macOS의 끝점용 Microsoft Defender는 여러 관리 도구 중 하나를 사용하여 배포되는 구성 프로필을 통해 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="44220-111">보안 운영 팀에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="44220-112">구성 프로필을 통해 설정된 기본 설정을 변경하려면 에스컬레이터된 권한이 필요하며 관리 권한이 없는 사용자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="44220-113">이 문서에서는 구성 프로필의 구조에 대해 설명하고 시작하는 데 사용할 수 있는 권장 프로필을 포함하며 프로필을 배포하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="44220-114">구성 프로필 구조</span><span class="sxs-lookup"><span data-stu-id="44220-114">Configuration profile structure</span></span>

<span data-ttu-id="44220-115">구성 프로필은 키로 식별된 항목(기본 설정 이름을 나타임)으로 구성되는 *.plist* 파일로, 그 다음에 기본 설정의 특성에 따라 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="44220-116">값은 숫자 값과 같은 단순하거나 중첩된 기본 설정 목록과 같은 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="44220-117">구성 프로필의 레이아웃은 사용하는 관리 콘솔에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="44220-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="44220-118">다음 섹션에는 JAMF 및 Intune에 대한 구성 프로필의 예가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="44220-119">구성 프로필의 최상위 수준에는 다음 섹션에서 자세히 설명하는 Microsoft Defender for Endpoint 하위 항목에 대한 제품 수준 기본 설정 및 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="44220-120">바이러스 백신 엔진 기본 설정</span><span class="sxs-lookup"><span data-stu-id="44220-120">Antivirus engine preferences</span></span>

<span data-ttu-id="44220-121">구성 *프로필의 antivirusEngine* 섹션은 끝점용 Microsoft Defender의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="44220-122">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-122">Section</span></span>|<span data-ttu-id="44220-123">값</span><span class="sxs-lookup"><span data-stu-id="44220-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-124">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-125">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-125">**Key**</span></span> | <span data-ttu-id="44220-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="44220-126">antivirusEngine</span></span> |
| <span data-ttu-id="44220-127">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-127">**Data type**</span></span> | <span data-ttu-id="44220-128">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="44220-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="44220-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-129">**Comments**</span></span> | <span data-ttu-id="44220-130">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="44220-131">실시간 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="44220-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="44220-132">파일에 액세스할 때 검색하는 실시간 보호를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="44220-133">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-133">Section</span></span>|<span data-ttu-id="44220-134">값</span><span class="sxs-lookup"><span data-stu-id="44220-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-135">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-136">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-136">**Key**</span></span> | <span data-ttu-id="44220-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="44220-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="44220-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-138">**Data type**</span></span> | <span data-ttu-id="44220-139">부울</span><span class="sxs-lookup"><span data-stu-id="44220-139">Boolean</span></span> |
| <span data-ttu-id="44220-140">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-140">**Possible values**</span></span> | <span data-ttu-id="44220-141">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-141">true (default)</span></span> <br/> <span data-ttu-id="44220-142">false</span><span class="sxs-lookup"><span data-stu-id="44220-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="44220-143">수동 모드 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="44220-143">Enable / disable passive mode</span></span>

<span data-ttu-id="44220-144">바이러스 백신 엔진이 수동 모드에서 실행되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="44220-145">수동 모드에는 다음과 같은 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="44220-146">실시간 보호가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="44220-147">On-Demand scanning is turned on(요구 시 검사가 켜져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="44220-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="44220-148">자동 위협 수정이 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="44220-149">보안 인텔리전스 업데이트가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="44220-150">상태 메뉴 아이콘이 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="44220-151">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-151">Section</span></span>|<span data-ttu-id="44220-152">값</span><span class="sxs-lookup"><span data-stu-id="44220-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-153">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-154">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-154">**Key**</span></span> | <span data-ttu-id="44220-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="44220-155">passiveMode</span></span> |
| <span data-ttu-id="44220-156">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-156">**Data type**</span></span> | <span data-ttu-id="44220-157">부울</span><span class="sxs-lookup"><span data-stu-id="44220-157">Boolean</span></span> |
| <span data-ttu-id="44220-158">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-158">**Possible values**</span></span> | <span data-ttu-id="44220-159">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-159">false (default)</span></span> <br/> <span data-ttu-id="44220-160">true</span><span class="sxs-lookup"><span data-stu-id="44220-160">true</span></span> |
| <span data-ttu-id="44220-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-161">**Comments**</span></span> | <span data-ttu-id="44220-162">Microsoft Defender for Endpoint 버전 100.67.60 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="44220-163">제외 병합 정책</span><span class="sxs-lookup"><span data-stu-id="44220-163">Exclusion merge policy</span></span>

<span data-ttu-id="44220-164">제외에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="44220-165">이는 관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()의 조합일 `merge` 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="44220-166">이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="44220-167">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-167">Section</span></span>|<span data-ttu-id="44220-168">값</span><span class="sxs-lookup"><span data-stu-id="44220-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-169">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-170">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-170">**Key**</span></span> | <span data-ttu-id="44220-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="44220-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="44220-172">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-172">**Data type**</span></span> | <span data-ttu-id="44220-173">String</span><span class="sxs-lookup"><span data-stu-id="44220-173">String</span></span> |
| <span data-ttu-id="44220-174">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-174">**Possible values**</span></span> | <span data-ttu-id="44220-175">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-175">merge (default)</span></span> <br/> <span data-ttu-id="44220-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="44220-176">admin_only</span></span> |
| <span data-ttu-id="44220-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-177">**Comments**</span></span> | <span data-ttu-id="44220-178">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="44220-179">제외 검사</span><span class="sxs-lookup"><span data-stu-id="44220-179">Scan exclusions</span></span>

<span data-ttu-id="44220-180">검사에서 제외된 엔터티를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="44220-181">제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="44220-182">제외는 항목 배열로 지정됩니다. 관리자는 필요한 수의 요소를 순서에 따라 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="44220-183">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-183">Section</span></span>|<span data-ttu-id="44220-184">값</span><span class="sxs-lookup"><span data-stu-id="44220-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-185">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-186">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-186">**Key**</span></span> | <span data-ttu-id="44220-187">제외</span><span class="sxs-lookup"><span data-stu-id="44220-187">exclusions</span></span> |
| <span data-ttu-id="44220-188">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-188">**Data type**</span></span> | <span data-ttu-id="44220-189">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="44220-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="44220-190">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-190">**Comments**</span></span> | <span data-ttu-id="44220-191">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="44220-192">제외 유형</span><span class="sxs-lookup"><span data-stu-id="44220-192">Type of exclusion</span></span>

<span data-ttu-id="44220-193">검색에서 제외된 콘텐츠를 유형별로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="44220-194">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-194">Section</span></span>|<span data-ttu-id="44220-195">값</span><span class="sxs-lookup"><span data-stu-id="44220-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-196">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-197">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-197">**Key**</span></span> | <span data-ttu-id="44220-198">$type</span><span class="sxs-lookup"><span data-stu-id="44220-198">$type</span></span> |
| <span data-ttu-id="44220-199">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-199">**Data type**</span></span> | <span data-ttu-id="44220-200">String</span><span class="sxs-lookup"><span data-stu-id="44220-200">String</span></span> |
| <span data-ttu-id="44220-201">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-201">**Possible values**</span></span> | <span data-ttu-id="44220-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="44220-202">excludedPath</span></span> <br/> <span data-ttu-id="44220-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="44220-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="44220-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="44220-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="44220-205">제외된 콘텐츠의 경로</span><span class="sxs-lookup"><span data-stu-id="44220-205">Path to excluded content</span></span>

<span data-ttu-id="44220-206">전체 파일 경로에서 검사에서 제외된 콘텐츠를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="44220-207">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-207">Section</span></span>|<span data-ttu-id="44220-208">값</span><span class="sxs-lookup"><span data-stu-id="44220-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-209">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-210">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-210">**Key**</span></span> | <span data-ttu-id="44220-211">path</span><span class="sxs-lookup"><span data-stu-id="44220-211">path</span></span> |
| <span data-ttu-id="44220-212">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-212">**Data type**</span></span> | <span data-ttu-id="44220-213">String</span><span class="sxs-lookup"><span data-stu-id="44220-213">String</span></span> |
| <span data-ttu-id="44220-214">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-214">**Possible values**</span></span> | <span data-ttu-id="44220-215">유효한 경로</span><span class="sxs-lookup"><span data-stu-id="44220-215">valid paths</span></span> |
| <span data-ttu-id="44220-216">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-216">**Comments**</span></span> | <span data-ttu-id="44220-217">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="44220-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="44220-218">지원되는 제외 유형</span><span class="sxs-lookup"><span data-stu-id="44220-218">Supported exclusion types</span></span>

<span data-ttu-id="44220-219">다음 표에는 Mac의 끝점용 Defender에서 지원하는 제외 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="44220-220">제외</span><span class="sxs-lookup"><span data-stu-id="44220-220">Exclusion</span></span> | <span data-ttu-id="44220-221">정의</span><span class="sxs-lookup"><span data-stu-id="44220-221">Definition</span></span> | <span data-ttu-id="44220-222">예</span><span class="sxs-lookup"><span data-stu-id="44220-222">Examples</span></span>
---|---|---
<span data-ttu-id="44220-223">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="44220-223">File extension</span></span> | <span data-ttu-id="44220-224">디바이스의 아무 곳이나 확장명을 사용하여 모든 파일</span><span class="sxs-lookup"><span data-stu-id="44220-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="44220-225">파일</span><span class="sxs-lookup"><span data-stu-id="44220-225">File</span></span> | <span data-ttu-id="44220-226">전체 경로로 식별된 특정 파일</span><span class="sxs-lookup"><span data-stu-id="44220-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="44220-227">폴더</span><span class="sxs-lookup"><span data-stu-id="44220-227">Folder</span></span> | <span data-ttu-id="44220-228">지정된 폴더에 있는 모든 파일(재발성)</span><span class="sxs-lookup"><span data-stu-id="44220-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="44220-229">프로세스</span><span class="sxs-lookup"><span data-stu-id="44220-229">Process</span></span> | <span data-ttu-id="44220-230">전체 경로 또는 파일 이름으로 지정된 특정 프로세스 및 이 프로세스에서 연 모든 파일</span><span class="sxs-lookup"><span data-stu-id="44220-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="44220-231">위의 경로는 기호 링크가 아니라 하드 링크되어야만 성공적으로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="44220-232">를 실행하여 경로가 기호 링크인지 확인할 수 `file <path-name>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="44220-233">파일, 폴더 및 프로세스 제외는 다음 와일드카드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="44220-234">와일드카드</span><span class="sxs-lookup"><span data-stu-id="44220-234">Wildcard</span></span> | <span data-ttu-id="44220-235">설명</span><span class="sxs-lookup"><span data-stu-id="44220-235">Description</span></span> | <span data-ttu-id="44220-236">예제</span><span class="sxs-lookup"><span data-stu-id="44220-236">Example</span></span> | <span data-ttu-id="44220-237">일치</span><span class="sxs-lookup"><span data-stu-id="44220-237">Matches</span></span> | <span data-ttu-id="44220-238">일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="44220-239">none을 포함한 모든 문자와 일치합니다(경로 내에서 이 와일드카드를 사용하는 경우 폴더 하나만 대체).</span><span class="sxs-lookup"><span data-stu-id="44220-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="44220-240">?</span><span class="sxs-lookup"><span data-stu-id="44220-240">?</span></span> | <span data-ttu-id="44220-241">단일 문자와 일치</span><span class="sxs-lookup"><span data-stu-id="44220-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="44220-242">경로 유형(파일/디렉터리)</span><span class="sxs-lookup"><span data-stu-id="44220-242">Path type (file / directory)</span></span>

<span data-ttu-id="44220-243">경로 *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44220-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="44220-244">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-244">Section</span></span>|<span data-ttu-id="44220-245">값</span><span class="sxs-lookup"><span data-stu-id="44220-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-246">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-247">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-247">**Key**</span></span> | <span data-ttu-id="44220-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="44220-248">isDirectory</span></span> |
| <span data-ttu-id="44220-249">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-249">**Data type**</span></span> | <span data-ttu-id="44220-250">부울</span><span class="sxs-lookup"><span data-stu-id="44220-250">Boolean</span></span> |
| <span data-ttu-id="44220-251">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-251">**Possible values**</span></span> | <span data-ttu-id="44220-252">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-252">false (default)</span></span> <br/> <span data-ttu-id="44220-253">true</span><span class="sxs-lookup"><span data-stu-id="44220-253">true</span></span> |
| <span data-ttu-id="44220-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-254">**Comments**</span></span> | <span data-ttu-id="44220-255">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="44220-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="44220-256">검사에서 제외된 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="44220-256">File extension excluded from the scan</span></span>

<span data-ttu-id="44220-257">파일 확장명에 의해 검색되지 않을 콘텐츠를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="44220-258">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-258">Section</span></span>|<span data-ttu-id="44220-259">값</span><span class="sxs-lookup"><span data-stu-id="44220-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-260">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-261">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-261">**Key**</span></span> | <span data-ttu-id="44220-262">extension</span><span class="sxs-lookup"><span data-stu-id="44220-262">extension</span></span> |
| <span data-ttu-id="44220-263">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-263">**Data type**</span></span> | <span data-ttu-id="44220-264">String</span><span class="sxs-lookup"><span data-stu-id="44220-264">String</span></span> |
| <span data-ttu-id="44220-265">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-265">**Possible values**</span></span> | <span data-ttu-id="44220-266">유효한 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="44220-266">valid file extensions</span></span> |
| <span data-ttu-id="44220-267">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-267">**Comments**</span></span> | <span data-ttu-id="44220-268">제외된  *$type FileExtension만 적용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="44220-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="44220-269">검사에서 제외된 프로세스</span><span class="sxs-lookup"><span data-stu-id="44220-269">Process excluded from the scan</span></span>

<span data-ttu-id="44220-270">모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="44220-271">프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="44220-272">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-272">Section</span></span>|<span data-ttu-id="44220-273">값</span><span class="sxs-lookup"><span data-stu-id="44220-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-274">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-275">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-275">**Key**</span></span> | <span data-ttu-id="44220-276">name</span><span class="sxs-lookup"><span data-stu-id="44220-276">name</span></span> |
| <span data-ttu-id="44220-277">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-277">**Data type**</span></span> | <span data-ttu-id="44220-278">String</span><span class="sxs-lookup"><span data-stu-id="44220-278">String</span></span> |
| <span data-ttu-id="44220-279">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-279">**Possible values**</span></span> | <span data-ttu-id="44220-280">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="44220-280">any string</span></span> |
| <span data-ttu-id="44220-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-281">**Comments**</span></span> | <span data-ttu-id="44220-282">*excludedFileName이 $type만 적용할 수 있습니다.* </span><span class="sxs-lookup"><span data-stu-id="44220-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="44220-283">허용되는 위협</span><span class="sxs-lookup"><span data-stu-id="44220-283">Allowed threats</span></span>

<span data-ttu-id="44220-284">Mac의 끝점에 대한 Defender에 의해 차단되지 않는 이름으로 위협을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="44220-285">이러한 위협은 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="44220-286">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-286">Section</span></span>|<span data-ttu-id="44220-287">값</span><span class="sxs-lookup"><span data-stu-id="44220-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-288">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-289">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-289">**Key**</span></span> | <span data-ttu-id="44220-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="44220-290">allowedThreats</span></span> |
| <span data-ttu-id="44220-291">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-291">**Data type**</span></span> | <span data-ttu-id="44220-292">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="44220-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="44220-293">위협 작업 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-293">Disallowed threat actions</span></span>

<span data-ttu-id="44220-294">위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="44220-295">이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="44220-296">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-296">Section</span></span>|<span data-ttu-id="44220-297">값</span><span class="sxs-lookup"><span data-stu-id="44220-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-298">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-299">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-299">**Key**</span></span> | <span data-ttu-id="44220-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="44220-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="44220-301">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-301">**Data type**</span></span> | <span data-ttu-id="44220-302">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="44220-302">Array of strings</span></span> |
| <span data-ttu-id="44220-303">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-303">**Possible values**</span></span> | <span data-ttu-id="44220-304">allow (restricts users from allow threats)</span><span class="sxs-lookup"><span data-stu-id="44220-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="44220-305">restore(사용자가 검지에서 위협을 복원하는 것을 제한함)</span><span class="sxs-lookup"><span data-stu-id="44220-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="44220-306">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-306">**Comments**</span></span> | <span data-ttu-id="44220-307">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="44220-308">위협 유형 설정</span><span class="sxs-lookup"><span data-stu-id="44220-308">Threat type settings</span></span>

<span data-ttu-id="44220-309">macOS의 끝점에 대한 Microsoft Defender에서 특정 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="44220-310">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-310">Section</span></span>|<span data-ttu-id="44220-311">값</span><span class="sxs-lookup"><span data-stu-id="44220-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-312">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-313">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-313">**Key**</span></span> | <span data-ttu-id="44220-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="44220-314">threatTypeSettings</span></span> |
| <span data-ttu-id="44220-315">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-315">**Data type**</span></span> | <span data-ttu-id="44220-316">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="44220-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="44220-317">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-317">**Comments**</span></span> | <span data-ttu-id="44220-318">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="44220-319">위협 유형</span><span class="sxs-lookup"><span data-stu-id="44220-319">Threat type</span></span>

<span data-ttu-id="44220-320">위협 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-320">Specify threat types.</span></span>

|<span data-ttu-id="44220-321">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-321">Section</span></span>|<span data-ttu-id="44220-322">값</span><span class="sxs-lookup"><span data-stu-id="44220-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-323">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-324">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-324">**Key**</span></span> | <span data-ttu-id="44220-325">키</span><span class="sxs-lookup"><span data-stu-id="44220-325">key</span></span> |
| <span data-ttu-id="44220-326">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-326">**Data type**</span></span> | <span data-ttu-id="44220-327">String</span><span class="sxs-lookup"><span data-stu-id="44220-327">String</span></span> |
| <span data-ttu-id="44220-328">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-328">**Possible values**</span></span> | <span data-ttu-id="44220-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="44220-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="44220-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="44220-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="44220-331">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="44220-331">Action to take</span></span>

<span data-ttu-id="44220-332">이전 섹션에 지정된 유형의 위협이 감지될 때 취할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="44220-333">다음 옵션 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-333">Choose from the following options:</span></span>

- <span data-ttu-id="44220-334">**감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="44220-335">**차단:** 장치가 이러한 유형의 위협으로부터 보호되고 사용자 인터페이스 및 보안 콘솔에 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="44220-336">**Off:** 장치가 이러한 유형의 위협으로부터 보호되지는 않습니다. 아무것도 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="44220-337">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-337">Section</span></span>|<span data-ttu-id="44220-338">값</span><span class="sxs-lookup"><span data-stu-id="44220-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-339">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-340">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-340">**Key**</span></span> | <span data-ttu-id="44220-341">값</span><span class="sxs-lookup"><span data-stu-id="44220-341">value</span></span> |
| <span data-ttu-id="44220-342">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-342">**Data type**</span></span> | <span data-ttu-id="44220-343">String</span><span class="sxs-lookup"><span data-stu-id="44220-343">String</span></span> |
| <span data-ttu-id="44220-344">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-344">**Possible values**</span></span> | <span data-ttu-id="44220-345">감사(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-345">audit (default)</span></span> <br/> <span data-ttu-id="44220-346">block</span><span class="sxs-lookup"><span data-stu-id="44220-346">block</span></span> <br/> <span data-ttu-id="44220-347">off</span><span class="sxs-lookup"><span data-stu-id="44220-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="44220-348">위협 유형 설정 병합 정책</span><span class="sxs-lookup"><span data-stu-id="44220-348">Threat type settings merge policy</span></span>

<span data-ttu-id="44220-349">위협 유형 설정에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="44220-350">이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="44220-351">이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="44220-352">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-352">Section</span></span>|<span data-ttu-id="44220-353">값</span><span class="sxs-lookup"><span data-stu-id="44220-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-354">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-355">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-355">**Key**</span></span> | <span data-ttu-id="44220-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="44220-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="44220-357">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-357">**Data type**</span></span> | <span data-ttu-id="44220-358">String</span><span class="sxs-lookup"><span data-stu-id="44220-358">String</span></span> |
| <span data-ttu-id="44220-359">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-359">**Possible values**</span></span> | <span data-ttu-id="44220-360">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-360">merge (default)</span></span> <br/> <span data-ttu-id="44220-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="44220-361">admin_only</span></span> |
| <span data-ttu-id="44220-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-362">**Comments**</span></span> | <span data-ttu-id="44220-363">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="44220-364">바이러스 백신 검사 기록 보존(일)</span><span class="sxs-lookup"><span data-stu-id="44220-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="44220-365">장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="44220-366">이전 검사 결과가 기록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="44220-367">디스크에서 제거된 오래된 고지된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="44220-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="44220-368">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-368">Section</span></span>|<span data-ttu-id="44220-369">값</span><span class="sxs-lookup"><span data-stu-id="44220-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-370">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-371">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-371">**Key**</span></span> | <span data-ttu-id="44220-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="44220-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="44220-373">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-373">**Data type**</span></span> | <span data-ttu-id="44220-374">String</span><span class="sxs-lookup"><span data-stu-id="44220-374">String</span></span> |
| <span data-ttu-id="44220-375">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-375">**Possible values**</span></span> | <span data-ttu-id="44220-376">90(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-376">90 (default).</span></span> <span data-ttu-id="44220-377">허용되는 값은 1일에서 180일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="44220-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="44220-378">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-378">**Comments**</span></span> | <span data-ttu-id="44220-379">Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="44220-380">바이러스 백신 검사 기록의 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="44220-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="44220-381">검사 기록에 유지할 최대 항목 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="44220-382">항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="44220-383">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-383">Section</span></span>|<span data-ttu-id="44220-384">값</span><span class="sxs-lookup"><span data-stu-id="44220-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-385">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-386">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-386">**Key**</span></span> | <span data-ttu-id="44220-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="44220-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="44220-388">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-388">**Data type**</span></span> | <span data-ttu-id="44220-389">String</span><span class="sxs-lookup"><span data-stu-id="44220-389">String</span></span> |
| <span data-ttu-id="44220-390">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-390">**Possible values**</span></span> | <span data-ttu-id="44220-391">10000(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-391">10000 (default).</span></span> <span data-ttu-id="44220-392">허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.</span><span class="sxs-lookup"><span data-stu-id="44220-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="44220-393">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-393">**Comments**</span></span> | <span data-ttu-id="44220-394">Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="44220-395">클라우드 제공 보호 기본 설정</span><span class="sxs-lookup"><span data-stu-id="44220-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="44220-396">MacOS의 끝점에 대한 Microsoft Defender의 클라우드 기반 보호 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="44220-397">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-397">Section</span></span>|<span data-ttu-id="44220-398">값</span><span class="sxs-lookup"><span data-stu-id="44220-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-399">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-400">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-400">**Key**</span></span> | <span data-ttu-id="44220-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="44220-401">cloudService</span></span> |
| <span data-ttu-id="44220-402">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-402">**Data type**</span></span> | <span data-ttu-id="44220-403">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="44220-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="44220-404">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-404">**Comments**</span></span> | <span data-ttu-id="44220-405">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="44220-406">클라우드 제공 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="44220-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="44220-407">디바이스에서 클라우드 제공 보호를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="44220-408">서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="44220-409">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-409">Section</span></span>|<span data-ttu-id="44220-410">값</span><span class="sxs-lookup"><span data-stu-id="44220-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-411">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-412">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-412">**Key**</span></span> | <span data-ttu-id="44220-413">활성화됨</span><span class="sxs-lookup"><span data-stu-id="44220-413">enabled</span></span> |
| <span data-ttu-id="44220-414">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-414">**Data type**</span></span> | <span data-ttu-id="44220-415">부울</span><span class="sxs-lookup"><span data-stu-id="44220-415">Boolean</span></span> |
| <span data-ttu-id="44220-416">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-416">**Possible values**</span></span> | <span data-ttu-id="44220-417">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-417">true (default)</span></span> <br/> <span data-ttu-id="44220-418">false</span><span class="sxs-lookup"><span data-stu-id="44220-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="44220-419">진단 수집 수준</span><span class="sxs-lookup"><span data-stu-id="44220-419">Diagnostic collection level</span></span>

<span data-ttu-id="44220-420">진단 데이터는 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="44220-421">이 설정은 끝점용 Microsoft Defender에서 Microsoft로 전송하는 진단 수준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="44220-422">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-422">Section</span></span>|<span data-ttu-id="44220-423">값</span><span class="sxs-lookup"><span data-stu-id="44220-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-424">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-425">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-425">**Key**</span></span> | <span data-ttu-id="44220-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="44220-426">diagnosticLevel</span></span> |
| <span data-ttu-id="44220-427">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-427">**Data type**</span></span> | <span data-ttu-id="44220-428">String</span><span class="sxs-lookup"><span data-stu-id="44220-428">String</span></span> |
| <span data-ttu-id="44220-429">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-429">**Possible values**</span></span> | <span data-ttu-id="44220-430">선택 사항(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-430">optional (default)</span></span> <br/> <span data-ttu-id="44220-431">필수</span><span class="sxs-lookup"><span data-stu-id="44220-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="44220-432">자동 샘플 제출 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="44220-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="44220-433">의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="44220-434">전송된 파일에 개인 정보가 포함될 가능성이 있는 경우 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="44220-435">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-435">Section</span></span>|<span data-ttu-id="44220-436">값</span><span class="sxs-lookup"><span data-stu-id="44220-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-437">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-438">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-438">**Key**</span></span> | <span data-ttu-id="44220-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="44220-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="44220-440">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-440">**Data type**</span></span> | <span data-ttu-id="44220-441">부울</span><span class="sxs-lookup"><span data-stu-id="44220-441">Boolean</span></span> |
| <span data-ttu-id="44220-442">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-442">**Possible values**</span></span> | <span data-ttu-id="44220-443">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-443">true (default)</span></span> <br/> <span data-ttu-id="44220-444">false</span><span class="sxs-lookup"><span data-stu-id="44220-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="44220-445">자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="44220-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="44220-446">보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="44220-447">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-447">Section</span></span>|<span data-ttu-id="44220-448">값</span><span class="sxs-lookup"><span data-stu-id="44220-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-449">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-449">**Key**</span></span> | <span data-ttu-id="44220-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="44220-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="44220-451">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-451">**Data type**</span></span> | <span data-ttu-id="44220-452">부울</span><span class="sxs-lookup"><span data-stu-id="44220-452">Boolean</span></span> |
| <span data-ttu-id="44220-453">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-453">**Possible values**</span></span> | <span data-ttu-id="44220-454">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-454">true (default)</span></span> <br/> <span data-ttu-id="44220-455">false</span><span class="sxs-lookup"><span data-stu-id="44220-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="44220-456">사용자 인터페이스 기본 설정</span><span class="sxs-lookup"><span data-stu-id="44220-456">User interface preferences</span></span>

<span data-ttu-id="44220-457">macOS에서 끝점용 Microsoft Defender의 사용자 인터페이스에 대한 기본 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="44220-458">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-458">Section</span></span>|<span data-ttu-id="44220-459">값</span><span class="sxs-lookup"><span data-stu-id="44220-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-460">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-461">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-461">**Key**</span></span> | <span data-ttu-id="44220-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="44220-462">userInterface</span></span> |
| <span data-ttu-id="44220-463">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-463">**Data type**</span></span> | <span data-ttu-id="44220-464">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="44220-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="44220-465">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-465">**Comments**</span></span> | <span data-ttu-id="44220-466">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="44220-467">상태 메뉴 아이콘 표시/숨기기</span><span class="sxs-lookup"><span data-stu-id="44220-467">Show / hide status menu icon</span></span>

<span data-ttu-id="44220-468">화면의 오른쪽 위 모서리에 상태 메뉴 아이콘을 표시하거나 숨길지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="44220-469">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-469">Section</span></span>|<span data-ttu-id="44220-470">값</span><span class="sxs-lookup"><span data-stu-id="44220-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-471">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-472">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-472">**Key**</span></span> | <span data-ttu-id="44220-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="44220-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="44220-474">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-474">**Data type**</span></span> | <span data-ttu-id="44220-475">부울</span><span class="sxs-lookup"><span data-stu-id="44220-475">Boolean</span></span> |
| <span data-ttu-id="44220-476">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-476">**Possible values**</span></span> | <span data-ttu-id="44220-477">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-477">false (default)</span></span> <br/> <span data-ttu-id="44220-478">true</span><span class="sxs-lookup"><span data-stu-id="44220-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="44220-479">피드백을 보내기 위한 표시/숨기기 옵션</span><span class="sxs-lookup"><span data-stu-id="44220-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="44220-480">사용자가 로 진행하여 Microsoft에 피드백을 제출할 수 있는지 여부를 `Help`  >  `Send Feedback` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="44220-481">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-481">Section</span></span>|<span data-ttu-id="44220-482">값</span><span class="sxs-lookup"><span data-stu-id="44220-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-483">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-484">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-484">**Key**</span></span> | <span data-ttu-id="44220-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="44220-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="44220-486">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-486">**Data type**</span></span> | <span data-ttu-id="44220-487">String</span><span class="sxs-lookup"><span data-stu-id="44220-487">String</span></span> |
| <span data-ttu-id="44220-488">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-488">**Possible values**</span></span> | <span data-ttu-id="44220-489">사용(기본값)</span><span class="sxs-lookup"><span data-stu-id="44220-489">enabled (default)</span></span> <br/> <span data-ttu-id="44220-490">비활성화됨</span><span class="sxs-lookup"><span data-stu-id="44220-490">disabled</span></span> |
| <span data-ttu-id="44220-491">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-491">**Comments**</span></span> | <span data-ttu-id="44220-492">끝점 버전 101.19.61 이상용 Microsoft Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="44220-493">끝점 검색 및 응답 기본 설정</span><span class="sxs-lookup"><span data-stu-id="44220-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="44220-494">macOS에서 끝점용 Microsoft Defender의 끝점 EDR(검색 및 응답) 구성 요소의 기본 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="44220-495">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-495">Section</span></span>|<span data-ttu-id="44220-496">값</span><span class="sxs-lookup"><span data-stu-id="44220-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-497">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-498">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-498">**Key**</span></span> | <span data-ttu-id="44220-499">edr</span><span class="sxs-lookup"><span data-stu-id="44220-499">edr</span></span> |
| <span data-ttu-id="44220-500">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-500">**Data type**</span></span> | <span data-ttu-id="44220-501">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="44220-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="44220-502">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-502">**Comments**</span></span> | <span data-ttu-id="44220-503">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="44220-504">장치 태그</span><span class="sxs-lookup"><span data-stu-id="44220-504">Device tags</span></span>

<span data-ttu-id="44220-505">태그 이름 및 해당 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="44220-506">GROUP 태그는 지정된 값으로 디바이스에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="44220-507">태그는 장치 페이지 아래에 있는 포털에 반영되어 디바이스 필터링 및 그룹화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="44220-508">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-508">Section</span></span>|<span data-ttu-id="44220-509">값</span><span class="sxs-lookup"><span data-stu-id="44220-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-510">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-511">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-511">**Key**</span></span> | <span data-ttu-id="44220-512">tags</span><span class="sxs-lookup"><span data-stu-id="44220-512">tags</span></span> |
| <span data-ttu-id="44220-513">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-513">**Data type**</span></span> | <span data-ttu-id="44220-514">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="44220-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="44220-515">**Comments**</span><span class="sxs-lookup"><span data-stu-id="44220-515">**Comments**</span></span> | <span data-ttu-id="44220-516">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="44220-517">태그 유형</span><span class="sxs-lookup"><span data-stu-id="44220-517">Type of tag</span></span>

<span data-ttu-id="44220-518">태그 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-518">Specifies the type of tag</span></span>

|<span data-ttu-id="44220-519">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-519">Section</span></span>|<span data-ttu-id="44220-520">값</span><span class="sxs-lookup"><span data-stu-id="44220-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-521">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-522">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-522">**Key**</span></span> | <span data-ttu-id="44220-523">키</span><span class="sxs-lookup"><span data-stu-id="44220-523">key</span></span> |
| <span data-ttu-id="44220-524">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-524">**Data type**</span></span> | <span data-ttu-id="44220-525">String</span><span class="sxs-lookup"><span data-stu-id="44220-525">String</span></span> |
| <span data-ttu-id="44220-526">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="44220-527">태그 값</span><span class="sxs-lookup"><span data-stu-id="44220-527">Value of tag</span></span>

<span data-ttu-id="44220-528">태그 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-528">Specifies the value of tag</span></span>

|<span data-ttu-id="44220-529">섹션</span><span class="sxs-lookup"><span data-stu-id="44220-529">Section</span></span>|<span data-ttu-id="44220-530">값</span><span class="sxs-lookup"><span data-stu-id="44220-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="44220-531">**도메인**</span><span class="sxs-lookup"><span data-stu-id="44220-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="44220-532">**키**</span><span class="sxs-lookup"><span data-stu-id="44220-532">**Key**</span></span> | <span data-ttu-id="44220-533">값</span><span class="sxs-lookup"><span data-stu-id="44220-533">value</span></span> |
| <span data-ttu-id="44220-534">**Data type**</span><span class="sxs-lookup"><span data-stu-id="44220-534">**Data type**</span></span> | <span data-ttu-id="44220-535">String</span><span class="sxs-lookup"><span data-stu-id="44220-535">String</span></span> |
| <span data-ttu-id="44220-536">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="44220-536">**Possible values**</span></span> | <span data-ttu-id="44220-537">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="44220-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="44220-538">태그 유형당 하나의 값만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="44220-539">태그 유형은 고유하며 동일한 구성 프로필에서 반복하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="44220-540">권장 구성 프로필</span><span class="sxs-lookup"><span data-stu-id="44220-540">Recommended configuration profile</span></span>

<span data-ttu-id="44220-541">시작하려면 엔터프라이즈에서 Microsoft Defender for Endpoint에서 제공하는 모든 보호 기능을 활용하기 위해 다음 구성을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="44220-542">다음 구성 프로필(또는 JAMF의 경우 사용자 지정 설정 구성 프로필에 업로드할 수 있는 속성 목록)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="44220-543">RTP(실시간 보호) 사용</span><span class="sxs-lookup"><span data-stu-id="44220-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="44220-544">다음 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="44220-545">**잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="44220-546">**보관함(압축률이** 높은 파일)이 끝점 로그에 대한 Microsoft Defender에 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="44220-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="44220-547">자동 보안 인텔리전스 업데이트 사용</span><span class="sxs-lookup"><span data-stu-id="44220-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="44220-548">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="44220-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="44220-549">자동 샘플 제출 사용</span><span class="sxs-lookup"><span data-stu-id="44220-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="44220-550">JAMF 구성 프로필의 속성 목록</span><span class="sxs-lookup"><span data-stu-id="44220-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="44220-551">Intune 프로필</span><span class="sxs-lookup"><span data-stu-id="44220-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="44220-552">전체 구성 프로필 예제</span><span class="sxs-lookup"><span data-stu-id="44220-552">Full configuration profile example</span></span>

<span data-ttu-id="44220-553">다음 템플릿은 이 문서에 설명된 모든 설정에 대한 항목을 포함하며 macOS에서 끝점용 Microsoft Defender를 더 많이 제어하려는 고급 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="44220-554">JAMF 구성 프로필의 속성 목록</span><span class="sxs-lookup"><span data-stu-id="44220-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="44220-555">Intune 프로필</span><span class="sxs-lookup"><span data-stu-id="44220-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="44220-556">속성 목록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="44220-556">Property list validation</span></span>

<span data-ttu-id="44220-557">속성 목록은 유효한 *.plist 파일입니다.*</span><span class="sxs-lookup"><span data-stu-id="44220-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="44220-558">다음을 실행하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="44220-559">파일이 잘 형식이면 위의 명령은 의 종료 코드를 `OK` 출력하고 `0` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="44220-560">그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="44220-561">구성 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="44220-561">Configuration profile deployment</span></span>

<span data-ttu-id="44220-562">엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 콘솔을 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="44220-563">다음 섹션에서는 JAMF 및 Intune을 사용하여 이 프로필을 배포하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="44220-564">JAMF 배포</span><span class="sxs-lookup"><span data-stu-id="44220-564">JAMF deployment</span></span>

<span data-ttu-id="44220-565">JAMF 콘솔에서 컴퓨터 구성 프로필을 열고 사용할 구성 프로필로 이동한 다음 사용자 지정 프로필을  >   **설정.**</span><span class="sxs-lookup"><span data-stu-id="44220-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="44220-566">기본 설정 도메인으로 항목을 만들고 앞에서 생성한 `com.microsoft.wdav` *.plist를* 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="44220-567">올바른 기본 설정 도메인( )을 입력해야 합니다. 그렇지 않으면 끝점용 Microsoft Defender에서 기본 설정이 `com.microsoft.wdav` 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="44220-568">Intune 배포</span><span class="sxs-lookup"><span data-stu-id="44220-568">Intune deployment</span></span>

1. <span data-ttu-id="44220-569">장치 **구성 관리를**  >  **니다.**</span><span class="sxs-lookup"><span data-stu-id="44220-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="44220-570">프로필 **만들기**  >  **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="44220-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="44220-571">프로필 이름을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="44220-571">Choose a name for the profile.</span></span> <span data-ttu-id="44220-572">**Platform=macOS를** **프로필 유형=사용자 지정으로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="44220-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="44220-573">구성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-573">Select Configure.</span></span>

3. <span data-ttu-id="44220-574">앞에서 생성한 .plist를 로 `com.microsoft.wdav.xml` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="44220-575">사용자 `com.microsoft.wdav` 지정 구성 프로필 이름으로 **를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="44220-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="44220-576">구성 프로필을 열고 파일을 `com.microsoft.wdav.xml` 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="44220-577">이 파일은 3단계에서 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="44220-578">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44220-578">Select **OK**.</span></span>

7. <span data-ttu-id="44220-579">배정   >  **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="44220-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="44220-580">포함 **탭에서** 모든 사용자 및 모든 & **할당을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="44220-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="44220-581">올바른 사용자 지정 구성 프로필 이름을 입력해야 합니다. 그렇지 않으면 이러한 기본 설정이 끝점용 Microsoft Defender에서 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44220-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="44220-582">리소스</span><span class="sxs-lookup"><span data-stu-id="44220-582">Resources</span></span>

- [<span data-ttu-id="44220-583">구성 프로필 참조(Apple 개발자 문서)</span><span class="sxs-lookup"><span data-stu-id="44220-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
