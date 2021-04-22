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
ms.openlocfilehash: f13734392e4975738a0d60d38e618595b5175667
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934564"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="9f8de-104">macOS의 끝점에 대한 Microsoft Defender 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9f8de-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-105">**Applies to:**</span></span>

- [<span data-ttu-id="9f8de-106">Microsoft Defender for Endpoint(macOS용)</span><span class="sxs-lookup"><span data-stu-id="9f8de-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="9f8de-107">이 문서에는 엔터프라이즈 조직의 macOS에서 끝점용 Microsoft Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="9f8de-108">명령줄 인터페이스를 사용하여 macOS에서 끝점에 대한 Microsoft Defender를 구성하는 데 필요한 리소스는 리소스를 [참조합니다.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="9f8de-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="9f8de-109">요약</span><span class="sxs-lookup"><span data-stu-id="9f8de-109">Summary</span></span>

<span data-ttu-id="9f8de-110">엔터프라이즈 조직에서 macOS의 끝점용 Microsoft Defender는 여러 관리 도구 중 하나를 사용하여 배포되는 구성 프로필을 통해 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="9f8de-111">보안 운영 팀에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="9f8de-112">구성 프로필을 통해 설정된 기본 설정을 변경하려면 에스컬레이터된 권한이 필요하며 관리 권한이 없는 사용자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="9f8de-113">이 문서에서는 구성 프로필의 구조에 대해 설명하고 시작하는 데 사용할 수 있는 권장 프로필을 포함하며 프로필을 배포하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="9f8de-114">구성 프로필 구조</span><span class="sxs-lookup"><span data-stu-id="9f8de-114">Configuration profile structure</span></span>

<span data-ttu-id="9f8de-115">구성 프로필은 키로 식별된 항목(기본 설정 이름을 나타임)으로 구성되는 *.plist* 파일로, 그 다음에 기본 설정의 특성에 따라 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="9f8de-116">값은 숫자 값과 같은 단순하거나 중첩된 기본 설정 목록과 같은 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="9f8de-117">구성 프로필의 레이아웃은 사용하는 관리 콘솔에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="9f8de-118">다음 섹션에는 JAMF 및 Intune에 대한 구성 프로필의 예가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="9f8de-119">구성 프로필의 최상위 수준에는 다음 섹션에서 자세히 설명하는 Microsoft Defender for Endpoint 하위 항목에 대한 제품 수준 기본 설정 및 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="9f8de-120">바이러스 백신 엔진 기본 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-120">Antivirus engine preferences</span></span>

<span data-ttu-id="9f8de-121">구성 *프로필의 antivirusEngine* 섹션은 끝점용 Microsoft Defender의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="9f8de-122">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-122">Section</span></span>|<span data-ttu-id="9f8de-123">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-124">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-125">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-125">**Key**</span></span> | <span data-ttu-id="9f8de-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="9f8de-126">antivirusEngine</span></span> |
| <span data-ttu-id="9f8de-127">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-127">**Data type**</span></span> | <span data-ttu-id="9f8de-128">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="9f8de-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f8de-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-129">**Comments**</span></span> | <span data-ttu-id="9f8de-130">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="9f8de-131">실시간 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="9f8de-132">파일에 액세스할 때 검색하는 실시간 보호를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="9f8de-133">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-133">Section</span></span>|<span data-ttu-id="9f8de-134">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-135">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-136">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-136">**Key**</span></span> | <span data-ttu-id="9f8de-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="9f8de-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="9f8de-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-138">**Data type**</span></span> | <span data-ttu-id="9f8de-139">부울</span><span class="sxs-lookup"><span data-stu-id="9f8de-139">Boolean</span></span> |
| <span data-ttu-id="9f8de-140">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-140">**Possible values**</span></span> | <span data-ttu-id="9f8de-141">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-141">true (default)</span></span> <br/> <span data-ttu-id="9f8de-142">false</span><span class="sxs-lookup"><span data-stu-id="9f8de-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="9f8de-143">수동 모드 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-143">Enable / disable passive mode</span></span>

<span data-ttu-id="9f8de-144">바이러스 백신 엔진이 수동 모드에서 실행되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="9f8de-145">수동 모드에는 다음과 같은 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="9f8de-146">실시간 보호가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="9f8de-147">On-Demand scanning is turned on(요구 시 검사가 켜져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9f8de-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="9f8de-148">자동 위협 수정이 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="9f8de-149">보안 인텔리전스 업데이트가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="9f8de-150">상태 메뉴 아이콘이 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="9f8de-151">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-151">Section</span></span>|<span data-ttu-id="9f8de-152">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-153">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-154">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-154">**Key**</span></span> | <span data-ttu-id="9f8de-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="9f8de-155">passiveMode</span></span> |
| <span data-ttu-id="9f8de-156">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-156">**Data type**</span></span> | <span data-ttu-id="9f8de-157">부울</span><span class="sxs-lookup"><span data-stu-id="9f8de-157">Boolean</span></span> |
| <span data-ttu-id="9f8de-158">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-158">**Possible values**</span></span> | <span data-ttu-id="9f8de-159">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-159">false (default)</span></span> <br/> <span data-ttu-id="9f8de-160">true</span><span class="sxs-lookup"><span data-stu-id="9f8de-160">true</span></span> |
| <span data-ttu-id="9f8de-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-161">**Comments**</span></span> | <span data-ttu-id="9f8de-162">Microsoft Defender for Endpoint 버전 100.67.60 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="9f8de-163">제외 병합 정책</span><span class="sxs-lookup"><span data-stu-id="9f8de-163">Exclusion merge policy</span></span>

<span data-ttu-id="9f8de-164">제외에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="9f8de-165">이는 관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()의 조합일 `merge` 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="9f8de-166">이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="9f8de-167">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-167">Section</span></span>|<span data-ttu-id="9f8de-168">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-169">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-170">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-170">**Key**</span></span> | <span data-ttu-id="9f8de-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9f8de-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="9f8de-172">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-172">**Data type**</span></span> | <span data-ttu-id="9f8de-173">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-173">String</span></span> |
| <span data-ttu-id="9f8de-174">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-174">**Possible values**</span></span> | <span data-ttu-id="9f8de-175">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-175">merge (default)</span></span> <br/> <span data-ttu-id="9f8de-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="9f8de-176">admin_only</span></span> |
| <span data-ttu-id="9f8de-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-177">**Comments**</span></span> | <span data-ttu-id="9f8de-178">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="9f8de-179">제외 검사</span><span class="sxs-lookup"><span data-stu-id="9f8de-179">Scan exclusions</span></span>

<span data-ttu-id="9f8de-180">검사에서 제외된 엔터티를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="9f8de-181">제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="9f8de-182">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-182">Section</span></span>|<span data-ttu-id="9f8de-183">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-184">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-185">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-185">**Key**</span></span> | <span data-ttu-id="9f8de-186">제외</span><span class="sxs-lookup"><span data-stu-id="9f8de-186">exclusions</span></span> |
| <span data-ttu-id="9f8de-187">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-187">**Data type**</span></span> | <span data-ttu-id="9f8de-188">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="9f8de-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f8de-189">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-189">**Comments**</span></span> | <span data-ttu-id="9f8de-190">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="9f8de-191">제외 유형</span><span class="sxs-lookup"><span data-stu-id="9f8de-191">Type of exclusion</span></span>

<span data-ttu-id="9f8de-192">검색에서 제외된 콘텐츠를 유형별로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="9f8de-193">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-193">Section</span></span>|<span data-ttu-id="9f8de-194">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-195">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-196">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-196">**Key**</span></span> | <span data-ttu-id="9f8de-197">$type</span><span class="sxs-lookup"><span data-stu-id="9f8de-197">$type</span></span> |
| <span data-ttu-id="9f8de-198">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-198">**Data type**</span></span> | <span data-ttu-id="9f8de-199">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-199">String</span></span> |
| <span data-ttu-id="9f8de-200">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-200">**Possible values**</span></span> | <span data-ttu-id="9f8de-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="9f8de-201">excludedPath</span></span> <br/> <span data-ttu-id="9f8de-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="9f8de-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="9f8de-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="9f8de-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="9f8de-204">제외된 콘텐츠의 경로</span><span class="sxs-lookup"><span data-stu-id="9f8de-204">Path to excluded content</span></span>

<span data-ttu-id="9f8de-205">전체 파일 경로에서 검사에서 제외된 콘텐츠를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="9f8de-206">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-206">Section</span></span>|<span data-ttu-id="9f8de-207">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-208">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-209">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-209">**Key**</span></span> | <span data-ttu-id="9f8de-210">path</span><span class="sxs-lookup"><span data-stu-id="9f8de-210">path</span></span> |
| <span data-ttu-id="9f8de-211">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-211">**Data type**</span></span> | <span data-ttu-id="9f8de-212">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-212">String</span></span> |
| <span data-ttu-id="9f8de-213">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-213">**Possible values**</span></span> | <span data-ttu-id="9f8de-214">유효한 경로</span><span class="sxs-lookup"><span data-stu-id="9f8de-214">valid paths</span></span> |
| <span data-ttu-id="9f8de-215">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-215">**Comments**</span></span> | <span data-ttu-id="9f8de-216">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="9f8de-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="9f8de-217">경로 유형(파일/디렉터리)</span><span class="sxs-lookup"><span data-stu-id="9f8de-217">Path type (file / directory)</span></span>

<span data-ttu-id="9f8de-218">경로 *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="9f8de-219">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-219">Section</span></span>|<span data-ttu-id="9f8de-220">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-221">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-222">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-222">**Key**</span></span> | <span data-ttu-id="9f8de-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="9f8de-223">isDirectory</span></span> |
| <span data-ttu-id="9f8de-224">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-224">**Data type**</span></span> | <span data-ttu-id="9f8de-225">부울</span><span class="sxs-lookup"><span data-stu-id="9f8de-225">Boolean</span></span> |
| <span data-ttu-id="9f8de-226">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-226">**Possible values**</span></span> | <span data-ttu-id="9f8de-227">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-227">false (default)</span></span> <br/> <span data-ttu-id="9f8de-228">true</span><span class="sxs-lookup"><span data-stu-id="9f8de-228">true</span></span> |
| <span data-ttu-id="9f8de-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-229">**Comments**</span></span> | <span data-ttu-id="9f8de-230">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="9f8de-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="9f8de-231">검사에서 제외된 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="9f8de-231">File extension excluded from the scan</span></span>

<span data-ttu-id="9f8de-232">파일 확장명에 의해 검색되지 않을 콘텐츠를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="9f8de-233">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-233">Section</span></span>|<span data-ttu-id="9f8de-234">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-235">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-236">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-236">**Key**</span></span> | <span data-ttu-id="9f8de-237">extension</span><span class="sxs-lookup"><span data-stu-id="9f8de-237">extension</span></span> |
| <span data-ttu-id="9f8de-238">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-238">**Data type**</span></span> | <span data-ttu-id="9f8de-239">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-239">String</span></span> |
| <span data-ttu-id="9f8de-240">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-240">**Possible values**</span></span> | <span data-ttu-id="9f8de-241">유효한 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="9f8de-241">valid file extensions</span></span> |
| <span data-ttu-id="9f8de-242">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-242">**Comments**</span></span> | <span data-ttu-id="9f8de-243">제외된  *$type FileExtension만 적용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="9f8de-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="9f8de-244">검사에서 제외된 프로세스</span><span class="sxs-lookup"><span data-stu-id="9f8de-244">Process excluded from the scan</span></span>

<span data-ttu-id="9f8de-245">모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="9f8de-246">프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="9f8de-247">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-247">Section</span></span>|<span data-ttu-id="9f8de-248">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-249">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-250">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-250">**Key**</span></span> | <span data-ttu-id="9f8de-251">name</span><span class="sxs-lookup"><span data-stu-id="9f8de-251">name</span></span> |
| <span data-ttu-id="9f8de-252">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-252">**Data type**</span></span> | <span data-ttu-id="9f8de-253">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-253">String</span></span> |
| <span data-ttu-id="9f8de-254">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-254">**Possible values**</span></span> | <span data-ttu-id="9f8de-255">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="9f8de-255">any string</span></span> |
| <span data-ttu-id="9f8de-256">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-256">**Comments**</span></span> | <span data-ttu-id="9f8de-257">*excludedFileName이 $type만 적용할 수 있습니다.* </span><span class="sxs-lookup"><span data-stu-id="9f8de-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="9f8de-258">허용되는 위협</span><span class="sxs-lookup"><span data-stu-id="9f8de-258">Allowed threats</span></span>

<span data-ttu-id="9f8de-259">Mac의 끝점에 대한 Defender에 의해 차단되지 않는 이름으로 위협을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-259">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="9f8de-260">이러한 위협은 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="9f8de-261">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-261">Section</span></span>|<span data-ttu-id="9f8de-262">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-263">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-264">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-264">**Key**</span></span> | <span data-ttu-id="9f8de-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="9f8de-265">allowedThreats</span></span> |
| <span data-ttu-id="9f8de-266">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-266">**Data type**</span></span> | <span data-ttu-id="9f8de-267">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="9f8de-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="9f8de-268">위협 작업 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-268">Disallowed threat actions</span></span>

<span data-ttu-id="9f8de-269">위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="9f8de-270">이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="9f8de-271">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-271">Section</span></span>|<span data-ttu-id="9f8de-272">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-273">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-274">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-274">**Key**</span></span> | <span data-ttu-id="9f8de-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="9f8de-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="9f8de-276">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-276">**Data type**</span></span> | <span data-ttu-id="9f8de-277">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="9f8de-277">Array of strings</span></span> |
| <span data-ttu-id="9f8de-278">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-278">**Possible values**</span></span> | <span data-ttu-id="9f8de-279">allow (restricts users from allow threats)</span><span class="sxs-lookup"><span data-stu-id="9f8de-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="9f8de-280">restore(사용자가 검지에서 위협을 복원하는 것을 제한함)</span><span class="sxs-lookup"><span data-stu-id="9f8de-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="9f8de-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-281">**Comments**</span></span> | <span data-ttu-id="9f8de-282">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="9f8de-283">위협 유형 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-283">Threat type settings</span></span>

<span data-ttu-id="9f8de-284">macOS의 끝점에 대한 Microsoft Defender에서 특정 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9f8de-285">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-285">Section</span></span>|<span data-ttu-id="9f8de-286">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-287">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-288">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-288">**Key**</span></span> | <span data-ttu-id="9f8de-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="9f8de-289">threatTypeSettings</span></span> |
| <span data-ttu-id="9f8de-290">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-290">**Data type**</span></span> | <span data-ttu-id="9f8de-291">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="9f8de-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f8de-292">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-292">**Comments**</span></span> | <span data-ttu-id="9f8de-293">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="9f8de-294">위협 유형</span><span class="sxs-lookup"><span data-stu-id="9f8de-294">Threat type</span></span>

<span data-ttu-id="9f8de-295">위협 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-295">Specify threat types.</span></span>

|<span data-ttu-id="9f8de-296">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-296">Section</span></span>|<span data-ttu-id="9f8de-297">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-298">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-299">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-299">**Key**</span></span> | <span data-ttu-id="9f8de-300">키</span><span class="sxs-lookup"><span data-stu-id="9f8de-300">key</span></span> |
| <span data-ttu-id="9f8de-301">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-301">**Data type**</span></span> | <span data-ttu-id="9f8de-302">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-302">String</span></span> |
| <span data-ttu-id="9f8de-303">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-303">**Possible values**</span></span> | <span data-ttu-id="9f8de-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="9f8de-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="9f8de-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="9f8de-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="9f8de-306">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="9f8de-306">Action to take</span></span>

<span data-ttu-id="9f8de-307">이전 섹션에 지정된 유형의 위협이 감지될 때 취할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="9f8de-308">다음 옵션 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-308">Choose from the following options:</span></span>

- <span data-ttu-id="9f8de-309">**감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="9f8de-310">**차단:** 장치가 이러한 유형의 위협으로부터 보호되고 사용자 인터페이스 및 보안 콘솔에 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="9f8de-311">**Off:** 장치가 이러한 유형의 위협으로부터 보호되지는 않습니다. 아무것도 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="9f8de-312">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-312">Section</span></span>|<span data-ttu-id="9f8de-313">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-314">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-315">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-315">**Key**</span></span> | <span data-ttu-id="9f8de-316">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-316">value</span></span> |
| <span data-ttu-id="9f8de-317">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-317">**Data type**</span></span> | <span data-ttu-id="9f8de-318">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-318">String</span></span> |
| <span data-ttu-id="9f8de-319">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-319">**Possible values**</span></span> | <span data-ttu-id="9f8de-320">감사(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-320">audit (default)</span></span> <br/> <span data-ttu-id="9f8de-321">block</span><span class="sxs-lookup"><span data-stu-id="9f8de-321">block</span></span> <br/> <span data-ttu-id="9f8de-322">off</span><span class="sxs-lookup"><span data-stu-id="9f8de-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="9f8de-323">위협 유형 설정 병합 정책</span><span class="sxs-lookup"><span data-stu-id="9f8de-323">Threat type settings merge policy</span></span>

<span data-ttu-id="9f8de-324">위협 유형 설정에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="9f8de-325">이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="9f8de-326">이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="9f8de-327">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-327">Section</span></span>|<span data-ttu-id="9f8de-328">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-329">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-330">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-330">**Key**</span></span> | <span data-ttu-id="9f8de-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9f8de-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="9f8de-332">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-332">**Data type**</span></span> | <span data-ttu-id="9f8de-333">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-333">String</span></span> |
| <span data-ttu-id="9f8de-334">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-334">**Possible values**</span></span> | <span data-ttu-id="9f8de-335">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-335">merge (default)</span></span> <br/> <span data-ttu-id="9f8de-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="9f8de-336">admin_only</span></span> |
| <span data-ttu-id="9f8de-337">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-337">**Comments**</span></span> | <span data-ttu-id="9f8de-338">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="9f8de-339">바이러스 백신 검사 기록 보존(일)</span><span class="sxs-lookup"><span data-stu-id="9f8de-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="9f8de-340">장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="9f8de-341">이전 검사 결과가 기록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="9f8de-342">디스크에서 제거된 오래된 고지된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="9f8de-343">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-343">Section</span></span>|<span data-ttu-id="9f8de-344">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-345">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-346">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-346">**Key**</span></span> | <span data-ttu-id="9f8de-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="9f8de-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="9f8de-348">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-348">**Data type**</span></span> | <span data-ttu-id="9f8de-349">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-349">String</span></span> |
| <span data-ttu-id="9f8de-350">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-350">**Possible values**</span></span> | <span data-ttu-id="9f8de-351">90(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-351">90 (default).</span></span> <span data-ttu-id="9f8de-352">허용되는 값은 1일에서 180일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="9f8de-353">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-353">**Comments**</span></span> | <span data-ttu-id="9f8de-354">Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="9f8de-355">바이러스 백신 검사 기록의 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="9f8de-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="9f8de-356">검사 기록에 유지할 최대 항목 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="9f8de-357">항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="9f8de-358">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-358">Section</span></span>|<span data-ttu-id="9f8de-359">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-360">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-361">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-361">**Key**</span></span> | <span data-ttu-id="9f8de-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="9f8de-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="9f8de-363">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-363">**Data type**</span></span> | <span data-ttu-id="9f8de-364">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-364">String</span></span> |
| <span data-ttu-id="9f8de-365">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-365">**Possible values**</span></span> | <span data-ttu-id="9f8de-366">10000(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-366">10000 (default).</span></span> <span data-ttu-id="9f8de-367">허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="9f8de-368">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-368">**Comments**</span></span> | <span data-ttu-id="9f8de-369">Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="9f8de-370">클라우드 제공 보호 기본 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="9f8de-371">MacOS의 끝점에 대한 Microsoft Defender의 클라우드 기반 보호 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9f8de-372">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-372">Section</span></span>|<span data-ttu-id="9f8de-373">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-374">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-375">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-375">**Key**</span></span> | <span data-ttu-id="9f8de-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="9f8de-376">cloudService</span></span> |
| <span data-ttu-id="9f8de-377">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-377">**Data type**</span></span> | <span data-ttu-id="9f8de-378">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="9f8de-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f8de-379">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-379">**Comments**</span></span> | <span data-ttu-id="9f8de-380">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="9f8de-381">클라우드 제공 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="9f8de-382">디바이스에서 클라우드 제공 보호를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="9f8de-383">서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="9f8de-384">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-384">Section</span></span>|<span data-ttu-id="9f8de-385">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-386">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-387">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-387">**Key**</span></span> | <span data-ttu-id="9f8de-388">활성화됨</span><span class="sxs-lookup"><span data-stu-id="9f8de-388">enabled</span></span> |
| <span data-ttu-id="9f8de-389">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-389">**Data type**</span></span> | <span data-ttu-id="9f8de-390">부울</span><span class="sxs-lookup"><span data-stu-id="9f8de-390">Boolean</span></span> |
| <span data-ttu-id="9f8de-391">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-391">**Possible values**</span></span> | <span data-ttu-id="9f8de-392">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-392">true (default)</span></span> <br/> <span data-ttu-id="9f8de-393">false</span><span class="sxs-lookup"><span data-stu-id="9f8de-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="9f8de-394">진단 수집 수준</span><span class="sxs-lookup"><span data-stu-id="9f8de-394">Diagnostic collection level</span></span>

<span data-ttu-id="9f8de-395">진단 데이터는 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="9f8de-396">이 설정은 끝점용 Microsoft Defender에서 Microsoft로 전송하는 진단 수준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="9f8de-397">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-397">Section</span></span>|<span data-ttu-id="9f8de-398">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-399">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-400">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-400">**Key**</span></span> | <span data-ttu-id="9f8de-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="9f8de-401">diagnosticLevel</span></span> |
| <span data-ttu-id="9f8de-402">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-402">**Data type**</span></span> | <span data-ttu-id="9f8de-403">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-403">String</span></span> |
| <span data-ttu-id="9f8de-404">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-404">**Possible values**</span></span> | <span data-ttu-id="9f8de-405">선택 사항(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-405">optional (default)</span></span> <br/> <span data-ttu-id="9f8de-406">필수</span><span class="sxs-lookup"><span data-stu-id="9f8de-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="9f8de-407">자동 샘플 제출 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="9f8de-408">의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="9f8de-409">전송된 파일에 개인 정보가 포함될 가능성이 있는 경우 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="9f8de-410">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-410">Section</span></span>|<span data-ttu-id="9f8de-411">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-412">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-413">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-413">**Key**</span></span> | <span data-ttu-id="9f8de-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="9f8de-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="9f8de-415">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-415">**Data type**</span></span> | <span data-ttu-id="9f8de-416">부울</span><span class="sxs-lookup"><span data-stu-id="9f8de-416">Boolean</span></span> |
| <span data-ttu-id="9f8de-417">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-417">**Possible values**</span></span> | <span data-ttu-id="9f8de-418">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-418">true (default)</span></span> <br/> <span data-ttu-id="9f8de-419">false</span><span class="sxs-lookup"><span data-stu-id="9f8de-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="9f8de-420">자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="9f8de-421">보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="9f8de-422">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-422">Section</span></span>|<span data-ttu-id="9f8de-423">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-424">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-424">**Key**</span></span> | <span data-ttu-id="9f8de-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="9f8de-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="9f8de-426">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-426">**Data type**</span></span> | <span data-ttu-id="9f8de-427">부울</span><span class="sxs-lookup"><span data-stu-id="9f8de-427">Boolean</span></span> |
| <span data-ttu-id="9f8de-428">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-428">**Possible values**</span></span> | <span data-ttu-id="9f8de-429">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-429">true (default)</span></span> <br/> <span data-ttu-id="9f8de-430">false</span><span class="sxs-lookup"><span data-stu-id="9f8de-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="9f8de-431">사용자 인터페이스 기본 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-431">User interface preferences</span></span>

<span data-ttu-id="9f8de-432">macOS에서 끝점용 Microsoft Defender의 사용자 인터페이스에 대한 기본 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9f8de-433">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-433">Section</span></span>|<span data-ttu-id="9f8de-434">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-435">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-436">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-436">**Key**</span></span> | <span data-ttu-id="9f8de-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="9f8de-437">userInterface</span></span> |
| <span data-ttu-id="9f8de-438">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-438">**Data type**</span></span> | <span data-ttu-id="9f8de-439">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="9f8de-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f8de-440">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-440">**Comments**</span></span> | <span data-ttu-id="9f8de-441">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="9f8de-442">상태 메뉴 아이콘 표시/숨기기</span><span class="sxs-lookup"><span data-stu-id="9f8de-442">Show / hide status menu icon</span></span>

<span data-ttu-id="9f8de-443">화면의 오른쪽 위 모서리에 상태 메뉴 아이콘을 표시하거나 숨길지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="9f8de-444">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-444">Section</span></span>|<span data-ttu-id="9f8de-445">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-446">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-447">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-447">**Key**</span></span> | <span data-ttu-id="9f8de-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="9f8de-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="9f8de-449">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-449">**Data type**</span></span> | <span data-ttu-id="9f8de-450">부울</span><span class="sxs-lookup"><span data-stu-id="9f8de-450">Boolean</span></span> |
| <span data-ttu-id="9f8de-451">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-451">**Possible values**</span></span> | <span data-ttu-id="9f8de-452">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-452">false (default)</span></span> <br/> <span data-ttu-id="9f8de-453">true</span><span class="sxs-lookup"><span data-stu-id="9f8de-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="9f8de-454">피드백을 보내기 위한 표시/숨기기 옵션</span><span class="sxs-lookup"><span data-stu-id="9f8de-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="9f8de-455">사용자가 로 진행하여 Microsoft에 피드백을 제출할 수 있는지 여부를 `Help`  >  `Send Feedback` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="9f8de-456">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-456">Section</span></span>|<span data-ttu-id="9f8de-457">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-458">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-459">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-459">**Key**</span></span> | <span data-ttu-id="9f8de-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="9f8de-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="9f8de-461">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-461">**Data type**</span></span> | <span data-ttu-id="9f8de-462">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-462">String</span></span> |
| <span data-ttu-id="9f8de-463">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-463">**Possible values**</span></span> | <span data-ttu-id="9f8de-464">사용(기본값)</span><span class="sxs-lookup"><span data-stu-id="9f8de-464">enabled (default)</span></span> <br/> <span data-ttu-id="9f8de-465">비활성화됨</span><span class="sxs-lookup"><span data-stu-id="9f8de-465">disabled</span></span> |
| <span data-ttu-id="9f8de-466">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-466">**Comments**</span></span> | <span data-ttu-id="9f8de-467">끝점 버전 101.19.61 이상용 Microsoft Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="9f8de-468">끝점 검색 및 응답 기본 설정</span><span class="sxs-lookup"><span data-stu-id="9f8de-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="9f8de-469">macOS의 끝점에 대한 Microsoft Defender의 끝점 검색 및 응답(EDR) 구성 요소의 기본 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9f8de-470">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-470">Section</span></span>|<span data-ttu-id="9f8de-471">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-472">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-473">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-473">**Key**</span></span> | <span data-ttu-id="9f8de-474">edr</span><span class="sxs-lookup"><span data-stu-id="9f8de-474">edr</span></span> |
| <span data-ttu-id="9f8de-475">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-475">**Data type**</span></span> | <span data-ttu-id="9f8de-476">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="9f8de-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f8de-477">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-477">**Comments**</span></span> | <span data-ttu-id="9f8de-478">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="9f8de-479">장치 태그</span><span class="sxs-lookup"><span data-stu-id="9f8de-479">Device tags</span></span>

<span data-ttu-id="9f8de-480">태그 이름 및 해당 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="9f8de-481">GROUP 태그는 지정된 값으로 디바이스에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="9f8de-482">태그는 장치 페이지 아래에 있는 포털에 반영되어 디바이스 필터링 및 그룹화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="9f8de-483">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-483">Section</span></span>|<span data-ttu-id="9f8de-484">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-485">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-486">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-486">**Key**</span></span> | <span data-ttu-id="9f8de-487">tags</span><span class="sxs-lookup"><span data-stu-id="9f8de-487">tags</span></span> |
| <span data-ttu-id="9f8de-488">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-488">**Data type**</span></span> | <span data-ttu-id="9f8de-489">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="9f8de-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9f8de-490">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9f8de-490">**Comments**</span></span> | <span data-ttu-id="9f8de-491">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="9f8de-492">태그 유형</span><span class="sxs-lookup"><span data-stu-id="9f8de-492">Type of tag</span></span>

<span data-ttu-id="9f8de-493">태그 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-493">Specifies the type of tag</span></span>

|<span data-ttu-id="9f8de-494">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-494">Section</span></span>|<span data-ttu-id="9f8de-495">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-496">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-497">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-497">**Key**</span></span> | <span data-ttu-id="9f8de-498">키</span><span class="sxs-lookup"><span data-stu-id="9f8de-498">key</span></span> |
| <span data-ttu-id="9f8de-499">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-499">**Data type**</span></span> | <span data-ttu-id="9f8de-500">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-500">String</span></span> |
| <span data-ttu-id="9f8de-501">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="9f8de-502">태그 값</span><span class="sxs-lookup"><span data-stu-id="9f8de-502">Value of tag</span></span>

<span data-ttu-id="9f8de-503">태그 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-503">Specifies the value of tag</span></span>

|<span data-ttu-id="9f8de-504">섹션</span><span class="sxs-lookup"><span data-stu-id="9f8de-504">Section</span></span>|<span data-ttu-id="9f8de-505">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9f8de-506">**도메인**</span><span class="sxs-lookup"><span data-stu-id="9f8de-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9f8de-507">**키**</span><span class="sxs-lookup"><span data-stu-id="9f8de-507">**Key**</span></span> | <span data-ttu-id="9f8de-508">값</span><span class="sxs-lookup"><span data-stu-id="9f8de-508">value</span></span> |
| <span data-ttu-id="9f8de-509">**Data type**</span><span class="sxs-lookup"><span data-stu-id="9f8de-509">**Data type**</span></span> | <span data-ttu-id="9f8de-510">String</span><span class="sxs-lookup"><span data-stu-id="9f8de-510">String</span></span> |
| <span data-ttu-id="9f8de-511">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="9f8de-511">**Possible values**</span></span> | <span data-ttu-id="9f8de-512">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="9f8de-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="9f8de-513">태그 유형당 하나의 값만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="9f8de-514">태그 유형은 고유하며 동일한 구성 프로필에서 반복하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="9f8de-515">권장 구성 프로필</span><span class="sxs-lookup"><span data-stu-id="9f8de-515">Recommended configuration profile</span></span>

<span data-ttu-id="9f8de-516">시작하려면 엔터프라이즈에서 Microsoft Defender for Endpoint에서 제공하는 모든 보호 기능을 활용하기 위해 다음 구성을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="9f8de-517">다음 구성 프로필(또는 JAMF의 경우 사용자 지정 설정 구성 프로필에 업로드할 수 있는 속성 목록)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="9f8de-518">RTP(실시간 보호) 사용</span><span class="sxs-lookup"><span data-stu-id="9f8de-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="9f8de-519">다음 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="9f8de-520">**잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="9f8de-521">**보관함(압축률이** 높은 파일)이 끝점 로그에 대한 Microsoft Defender에 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="9f8de-522">자동 보안 인텔리전스 업데이트 사용</span><span class="sxs-lookup"><span data-stu-id="9f8de-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="9f8de-523">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="9f8de-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="9f8de-524">자동 샘플 제출 사용</span><span class="sxs-lookup"><span data-stu-id="9f8de-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9f8de-525">JAMF 구성 프로필의 속성 목록</span><span class="sxs-lookup"><span data-stu-id="9f8de-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="9f8de-526">Intune 프로필</span><span class="sxs-lookup"><span data-stu-id="9f8de-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="9f8de-527">전체 구성 프로필 예제</span><span class="sxs-lookup"><span data-stu-id="9f8de-527">Full configuration profile example</span></span>

<span data-ttu-id="9f8de-528">다음 템플릿은 이 문서에 설명된 모든 설정에 대한 항목을 포함하며 macOS에서 끝점용 Microsoft Defender를 더 많이 제어하려는 고급 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9f8de-529">JAMF 구성 프로필의 속성 목록</span><span class="sxs-lookup"><span data-stu-id="9f8de-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="9f8de-530">Intune 프로필</span><span class="sxs-lookup"><span data-stu-id="9f8de-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="9f8de-531">속성 목록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9f8de-531">Property list validation</span></span>

<span data-ttu-id="9f8de-532">속성 목록은 유효한 *.plist 파일입니다.*</span><span class="sxs-lookup"><span data-stu-id="9f8de-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="9f8de-533">다음을 실행하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="9f8de-534">파일이 잘 형식이면 위의 명령은 의 종료 코드를 `OK` 출력하고 `0` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="9f8de-535">그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="9f8de-536">구성 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="9f8de-536">Configuration profile deployment</span></span>

<span data-ttu-id="9f8de-537">엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 콘솔을 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="9f8de-538">다음 섹션에서는 JAMF 및 Intune을 사용하여 이 프로필을 배포하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="9f8de-539">JAMF 배포</span><span class="sxs-lookup"><span data-stu-id="9f8de-539">JAMF deployment</span></span>

<span data-ttu-id="9f8de-540">JAMF 콘솔에서 컴퓨터 구성 프로필을 열고 사용할 구성 프로필로 이동한 다음  >  사용자 지정 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f8de-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="9f8de-541">기본 설정 도메인으로 항목을 만들고 앞에서 생성한 `com.microsoft.wdav` *.plist를* 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="9f8de-542">올바른 기본 설정 도메인( )을 입력해야 합니다. 그렇지 않으면 끝점용 Microsoft Defender에서 기본 설정이 `com.microsoft.wdav` 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="9f8de-543">Intune 배포</span><span class="sxs-lookup"><span data-stu-id="9f8de-543">Intune deployment</span></span>

1. <span data-ttu-id="9f8de-544">장치 **구성 관리를**  >  **니다.**</span><span class="sxs-lookup"><span data-stu-id="9f8de-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="9f8de-545">프로필 **만들기**  >  **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f8de-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="9f8de-546">프로필 이름을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8de-546">Choose a name for the profile.</span></span> <span data-ttu-id="9f8de-547">**Platform=macOS를** **프로필 유형=사용자 지정으로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f8de-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="9f8de-548">구성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-548">Select Configure.</span></span>

3. <span data-ttu-id="9f8de-549">앞에서 생성한 .plist를 로 `com.microsoft.wdav.xml` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="9f8de-550">사용자 `com.microsoft.wdav` 지정 구성 프로필 이름으로 **를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f8de-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="9f8de-551">구성 프로필을 열고 파일을 `com.microsoft.wdav.xml` 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="9f8de-552">이 파일은 3단계에서 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="9f8de-553">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-553">Select **OK**.</span></span>

7. <span data-ttu-id="9f8de-554">배정   >  **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f8de-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="9f8de-555">포함 **탭에서** 모든 사용자 및 모든 & **할당을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f8de-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="9f8de-556">올바른 사용자 지정 구성 프로필 이름을 입력해야 합니다. 그렇지 않으면 이러한 기본 설정이 끝점용 Microsoft Defender에서 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8de-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="9f8de-557">리소스</span><span class="sxs-lookup"><span data-stu-id="9f8de-557">Resources</span></span>

- [<span data-ttu-id="9f8de-558">구성 프로필 참조(Apple 개발자 문서)</span><span class="sxs-lookup"><span data-stu-id="9f8de-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
