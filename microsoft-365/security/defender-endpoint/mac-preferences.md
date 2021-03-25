---
title: Mac용 Microsoft Defender ATP에 대한 기본 설정 설정
description: 엔터프라이즈 조직에서 Mac용 Microsoft Defender ATP를 구성합니다.
keywords: microsoft, defender, atp, mac, 관리, 기본 설정, 엔터프라이즈, intune, jamf, macos, 카탈로니아, mojave, high sierra
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076932"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="d469e-104">Mac용 끝점용 Microsoft Defender에 대한 기본 설정 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d469e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d469e-105">**Applies to:**</span></span>

- [<span data-ttu-id="d469e-106">Mac용 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d469e-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="d469e-107">이 문서에는 엔터프라이즈 조직에서 Mac용 끝점용 Microsoft Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="d469e-108">명령줄 인터페이스를 사용하여 Mac용 끝점에 대한 Microsoft Defender를 구성하기 위해 리소스 를 [참조합니다.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="d469e-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="d469e-109">요약</span><span class="sxs-lookup"><span data-stu-id="d469e-109">Summary</span></span>

<span data-ttu-id="d469e-110">엔터프라이즈 조직에서 Mac용 끝점용 Microsoft Defender는 여러 관리 도구 중 하나를 사용하여 배포되는 구성 프로필을 통해 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="d469e-111">보안 운영 팀에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="d469e-112">구성 프로필을 통해 설정된 기본 설정을 변경하려면 에스컬레이터된 권한이 필요하며 관리 권한이 없는 사용자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="d469e-113">이 문서에서는 구성 프로필의 구조에 대해 설명하고 시작하는 데 사용할 수 있는 권장 프로필을 포함하며 프로필을 배포하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="d469e-114">구성 프로필 구조</span><span class="sxs-lookup"><span data-stu-id="d469e-114">Configuration profile structure</span></span>

<span data-ttu-id="d469e-115">구성 프로필은 키로 식별된 항목(기본 설정 이름을 나타임)으로 구성되는 *.plist* 파일로, 그 다음에 기본 설정의 특성에 따라 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="d469e-116">값은 숫자 값과 같은 단순하거나 중첩된 기본 설정 목록과 같은 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="d469e-117">구성 프로필의 레이아웃은 사용하는 관리 콘솔에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="d469e-118">다음 섹션에는 JAMF 및 Intune에 대한 구성 프로필의 예가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="d469e-119">구성 프로필의 최상위 수준에는 다음 섹션에서 자세히 설명하는 Microsoft Defender for Endpoint 하위 항목에 대한 제품 수준 기본 설정 및 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="d469e-120">바이러스 백신 엔진 기본 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-120">Antivirus engine preferences</span></span>

<span data-ttu-id="d469e-121">구성 *프로필의 antivirusEngine* 섹션은 끝점용 Microsoft Defender의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-122">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-123">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-123">**Key**</span></span> | <span data-ttu-id="d469e-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="d469e-124">antivirusEngine</span></span> |
| <span data-ttu-id="d469e-125">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-125">**Data type**</span></span> | <span data-ttu-id="d469e-126">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="d469e-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d469e-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-127">**Comments**</span></span> | <span data-ttu-id="d469e-128">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="d469e-129">실시간 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="d469e-130">파일에 액세스할 때 검색하는 실시간 보호를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-131">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-132">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-132">**Key**</span></span> | <span data-ttu-id="d469e-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="d469e-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="d469e-134">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-134">**Data type**</span></span> | <span data-ttu-id="d469e-135">부울</span><span class="sxs-lookup"><span data-stu-id="d469e-135">Boolean</span></span> |
| <span data-ttu-id="d469e-136">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-136">**Possible values**</span></span> | <span data-ttu-id="d469e-137">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-137">true (default)</span></span> <br/> <span data-ttu-id="d469e-138">false</span><span class="sxs-lookup"><span data-stu-id="d469e-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="d469e-139">수동 모드 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-139">Enable / disable passive mode</span></span>

<span data-ttu-id="d469e-140">바이러스 백신 엔진이 수동 모드에서 실행되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="d469e-141">수동 모드에는 다음과 같은 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="d469e-142">실시간 보호가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="d469e-143">On-Demand scanning is turned on(요구 시 검사가 켜져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="d469e-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="d469e-144">자동 위협 수정이 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="d469e-145">보안 인텔리전스 업데이트가 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="d469e-146">상태 메뉴 아이콘이 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-147">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-148">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-148">**Key**</span></span> | <span data-ttu-id="d469e-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="d469e-149">passiveMode</span></span> |
| <span data-ttu-id="d469e-150">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-150">**Data type**</span></span> | <span data-ttu-id="d469e-151">부울</span><span class="sxs-lookup"><span data-stu-id="d469e-151">Boolean</span></span> |
| <span data-ttu-id="d469e-152">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-152">**Possible values**</span></span> | <span data-ttu-id="d469e-153">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-153">false (default)</span></span> <br/> <span data-ttu-id="d469e-154">true</span><span class="sxs-lookup"><span data-stu-id="d469e-154">true</span></span> |
| <span data-ttu-id="d469e-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-155">**Comments**</span></span> | <span data-ttu-id="d469e-156">Microsoft Defender for Endpoint 버전 100.67.60 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="d469e-157">제외 병합 정책</span><span class="sxs-lookup"><span data-stu-id="d469e-157">Exclusion merge policy</span></span>

<span data-ttu-id="d469e-158">제외에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="d469e-159">이는 관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()의 조합일 `merge` 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="d469e-160">이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-161">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-162">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-162">**Key**</span></span> | <span data-ttu-id="d469e-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d469e-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="d469e-164">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-164">**Data type**</span></span> | <span data-ttu-id="d469e-165">String</span><span class="sxs-lookup"><span data-stu-id="d469e-165">String</span></span> |
| <span data-ttu-id="d469e-166">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-166">**Possible values**</span></span> | <span data-ttu-id="d469e-167">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-167">merge (default)</span></span> <br/> <span data-ttu-id="d469e-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="d469e-168">admin_only</span></span> |
| <span data-ttu-id="d469e-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-169">**Comments**</span></span> | <span data-ttu-id="d469e-170">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="d469e-171">제외 검사</span><span class="sxs-lookup"><span data-stu-id="d469e-171">Scan exclusions</span></span>

<span data-ttu-id="d469e-172">검사에서 제외된 엔터티를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="d469e-173">제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-174">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-175">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-175">**Key**</span></span> | <span data-ttu-id="d469e-176">제외</span><span class="sxs-lookup"><span data-stu-id="d469e-176">exclusions</span></span> |
| <span data-ttu-id="d469e-177">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-177">**Data type**</span></span> | <span data-ttu-id="d469e-178">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="d469e-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d469e-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-179">**Comments**</span></span> | <span data-ttu-id="d469e-180">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="d469e-181">제외 유형</span><span class="sxs-lookup"><span data-stu-id="d469e-181">Type of exclusion</span></span>

<span data-ttu-id="d469e-182">검색에서 제외된 콘텐츠를 유형별로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-183">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-184">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-184">**Key**</span></span> | <span data-ttu-id="d469e-185">$type</span><span class="sxs-lookup"><span data-stu-id="d469e-185">$type</span></span> |
| <span data-ttu-id="d469e-186">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-186">**Data type**</span></span> | <span data-ttu-id="d469e-187">String</span><span class="sxs-lookup"><span data-stu-id="d469e-187">String</span></span> |
| <span data-ttu-id="d469e-188">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-188">**Possible values**</span></span> | <span data-ttu-id="d469e-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="d469e-189">excludedPath</span></span> <br/> <span data-ttu-id="d469e-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="d469e-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="d469e-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="d469e-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="d469e-192">제외된 콘텐츠의 경로</span><span class="sxs-lookup"><span data-stu-id="d469e-192">Path to excluded content</span></span>

<span data-ttu-id="d469e-193">전체 파일 경로에서 검사에서 제외된 콘텐츠를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-194">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-195">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-195">**Key**</span></span> | <span data-ttu-id="d469e-196">path</span><span class="sxs-lookup"><span data-stu-id="d469e-196">path</span></span> |
| <span data-ttu-id="d469e-197">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-197">**Data type**</span></span> | <span data-ttu-id="d469e-198">String</span><span class="sxs-lookup"><span data-stu-id="d469e-198">String</span></span> |
| <span data-ttu-id="d469e-199">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-199">**Possible values**</span></span> | <span data-ttu-id="d469e-200">유효한 경로</span><span class="sxs-lookup"><span data-stu-id="d469e-200">valid paths</span></span> |
| <span data-ttu-id="d469e-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-201">**Comments**</span></span> | <span data-ttu-id="d469e-202">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="d469e-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="d469e-203">경로 유형(파일/디렉터리)</span><span class="sxs-lookup"><span data-stu-id="d469e-203">Path type (file / directory)</span></span>

<span data-ttu-id="d469e-204">경로 *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="d469e-205">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-206">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-206">**Key**</span></span> | <span data-ttu-id="d469e-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="d469e-207">isDirectory</span></span> |
| <span data-ttu-id="d469e-208">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-208">**Data type**</span></span> | <span data-ttu-id="d469e-209">부울</span><span class="sxs-lookup"><span data-stu-id="d469e-209">Boolean</span></span> |
| <span data-ttu-id="d469e-210">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-210">**Possible values**</span></span> | <span data-ttu-id="d469e-211">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-211">false (default)</span></span> <br/> <span data-ttu-id="d469e-212">true</span><span class="sxs-lookup"><span data-stu-id="d469e-212">true</span></span> |
| <span data-ttu-id="d469e-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-213">**Comments**</span></span> | <span data-ttu-id="d469e-214">제외된 *$type* 적용 *가능*</span><span class="sxs-lookup"><span data-stu-id="d469e-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="d469e-215">검사에서 제외된 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="d469e-215">File extension excluded from the scan</span></span>

<span data-ttu-id="d469e-216">파일 확장명에 의해 검색되지 않을 콘텐츠를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-217">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-218">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-218">**Key**</span></span> | <span data-ttu-id="d469e-219">extension</span><span class="sxs-lookup"><span data-stu-id="d469e-219">extension</span></span> |
| <span data-ttu-id="d469e-220">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-220">**Data type**</span></span> | <span data-ttu-id="d469e-221">String</span><span class="sxs-lookup"><span data-stu-id="d469e-221">String</span></span> |
| <span data-ttu-id="d469e-222">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-222">**Possible values**</span></span> | <span data-ttu-id="d469e-223">유효한 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="d469e-223">valid file extensions</span></span> |
| <span data-ttu-id="d469e-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-224">**Comments**</span></span> | <span data-ttu-id="d469e-225">제외된  *$type FileExtension만 적용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="d469e-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="d469e-226">검사에서 제외된 프로세스</span><span class="sxs-lookup"><span data-stu-id="d469e-226">Process excluded from the scan</span></span>

<span data-ttu-id="d469e-227">모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="d469e-228">프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-229">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-230">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-230">**Key**</span></span> | <span data-ttu-id="d469e-231">name</span><span class="sxs-lookup"><span data-stu-id="d469e-231">name</span></span> |
| <span data-ttu-id="d469e-232">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-232">**Data type**</span></span> | <span data-ttu-id="d469e-233">String</span><span class="sxs-lookup"><span data-stu-id="d469e-233">String</span></span> |
| <span data-ttu-id="d469e-234">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-234">**Possible values**</span></span> | <span data-ttu-id="d469e-235">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="d469e-235">any string</span></span> |
| <span data-ttu-id="d469e-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-236">**Comments**</span></span> | <span data-ttu-id="d469e-237">*excludedFileName이 $type만 적용할 수 있습니다.* </span><span class="sxs-lookup"><span data-stu-id="d469e-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="d469e-238">허용되는 위협</span><span class="sxs-lookup"><span data-stu-id="d469e-238">Allowed threats</span></span>

<span data-ttu-id="d469e-239">Mac용 끝점용 Defender에 의해 차단되지 않는 이름으로 위협을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="d469e-240">이러한 위협은 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-241">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-242">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-242">**Key**</span></span> | <span data-ttu-id="d469e-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="d469e-243">allowedThreats</span></span> |
| <span data-ttu-id="d469e-244">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-244">**Data type**</span></span> | <span data-ttu-id="d469e-245">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="d469e-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="d469e-246">위협 작업 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-246">Disallowed threat actions</span></span>

<span data-ttu-id="d469e-247">위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="d469e-248">이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-249">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-250">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-250">**Key**</span></span> | <span data-ttu-id="d469e-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="d469e-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="d469e-252">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-252">**Data type**</span></span> | <span data-ttu-id="d469e-253">문자열 배열</span><span class="sxs-lookup"><span data-stu-id="d469e-253">Array of strings</span></span> |
| <span data-ttu-id="d469e-254">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-254">**Possible values**</span></span> | <span data-ttu-id="d469e-255">allow (restricts users from allow threats)</span><span class="sxs-lookup"><span data-stu-id="d469e-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="d469e-256">restore(사용자가 검지에서 위협을 복원하는 것을 제한함)</span><span class="sxs-lookup"><span data-stu-id="d469e-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="d469e-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-257">**Comments**</span></span> | <span data-ttu-id="d469e-258">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="d469e-259">위협 유형 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-259">Threat type settings</span></span>

<span data-ttu-id="d469e-260">Mac용 끝점용 Microsoft Defender에서 특정 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-261">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-262">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-262">**Key**</span></span> | <span data-ttu-id="d469e-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="d469e-263">threatTypeSettings</span></span> |
| <span data-ttu-id="d469e-264">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-264">**Data type**</span></span> | <span data-ttu-id="d469e-265">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="d469e-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d469e-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-266">**Comments**</span></span> | <span data-ttu-id="d469e-267">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="d469e-268">위협 유형</span><span class="sxs-lookup"><span data-stu-id="d469e-268">Threat type</span></span>

<span data-ttu-id="d469e-269">위협 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-270">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-271">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-271">**Key**</span></span> | <span data-ttu-id="d469e-272">키</span><span class="sxs-lookup"><span data-stu-id="d469e-272">key</span></span> |
| <span data-ttu-id="d469e-273">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-273">**Data type**</span></span> | <span data-ttu-id="d469e-274">String</span><span class="sxs-lookup"><span data-stu-id="d469e-274">String</span></span> |
| <span data-ttu-id="d469e-275">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-275">**Possible values**</span></span> | <span data-ttu-id="d469e-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="d469e-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="d469e-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="d469e-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="d469e-278">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="d469e-278">Action to take</span></span>

<span data-ttu-id="d469e-279">이전 섹션에 지정된 유형의 위협이 감지될 때 취할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="d469e-280">다음 옵션 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-280">Choose from the following options:</span></span>

- <span data-ttu-id="d469e-281">**감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="d469e-282">**차단:** 장치가 이러한 유형의 위협으로부터 보호되고 사용자 인터페이스 및 보안 콘솔에 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="d469e-283">**Off:** 장치가 이러한 유형의 위협으로부터 보호되지는 않습니다. 아무것도 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-284">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-285">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-285">**Key**</span></span> | <span data-ttu-id="d469e-286">값</span><span class="sxs-lookup"><span data-stu-id="d469e-286">value</span></span> |
| <span data-ttu-id="d469e-287">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-287">**Data type**</span></span> | <span data-ttu-id="d469e-288">String</span><span class="sxs-lookup"><span data-stu-id="d469e-288">String</span></span> |
| <span data-ttu-id="d469e-289">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-289">**Possible values**</span></span> | <span data-ttu-id="d469e-290">감사(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-290">audit (default)</span></span> <br/> <span data-ttu-id="d469e-291">block</span><span class="sxs-lookup"><span data-stu-id="d469e-291">block</span></span> <br/> <span data-ttu-id="d469e-292">off</span><span class="sxs-lookup"><span data-stu-id="d469e-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="d469e-293">위협 유형 설정 병합 정책</span><span class="sxs-lookup"><span data-stu-id="d469e-293">Threat type settings merge policy</span></span>

<span data-ttu-id="d469e-294">위협 유형 설정에 대한 병합 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="d469e-295">이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="d469e-296">이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-297">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-298">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-298">**Key**</span></span> | <span data-ttu-id="d469e-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d469e-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="d469e-300">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-300">**Data type**</span></span> | <span data-ttu-id="d469e-301">String</span><span class="sxs-lookup"><span data-stu-id="d469e-301">String</span></span> |
| <span data-ttu-id="d469e-302">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-302">**Possible values**</span></span> | <span data-ttu-id="d469e-303">병합(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-303">merge (default)</span></span> <br/> <span data-ttu-id="d469e-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="d469e-304">admin_only</span></span> |
| <span data-ttu-id="d469e-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-305">**Comments**</span></span> | <span data-ttu-id="d469e-306">끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="d469e-307">바이러스 백신 검사 기록 보존(일)</span><span class="sxs-lookup"><span data-stu-id="d469e-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="d469e-308">장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="d469e-309">이전 검사 결과가 기록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="d469e-310">디스크에서 제거된 오래된 고지된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-311">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-312">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-312">**Key**</span></span> | <span data-ttu-id="d469e-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="d469e-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="d469e-314">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-314">**Data type**</span></span> | <span data-ttu-id="d469e-315">String</span><span class="sxs-lookup"><span data-stu-id="d469e-315">String</span></span> |
| <span data-ttu-id="d469e-316">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-316">**Possible values**</span></span> | <span data-ttu-id="d469e-317">90(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-317">90 (default).</span></span> <span data-ttu-id="d469e-318">허용되는 값은 1일에서 180일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="d469e-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-319">**Comments**</span></span> | <span data-ttu-id="d469e-320">Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="d469e-321">바이러스 백신 검사 기록의 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="d469e-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="d469e-322">검사 기록에 유지할 최대 항목 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="d469e-323">항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-324">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-325">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-325">**Key**</span></span> | <span data-ttu-id="d469e-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="d469e-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="d469e-327">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-327">**Data type**</span></span> | <span data-ttu-id="d469e-328">String</span><span class="sxs-lookup"><span data-stu-id="d469e-328">String</span></span> |
| <span data-ttu-id="d469e-329">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-329">**Possible values**</span></span> | <span data-ttu-id="d469e-330">10000(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-330">10000 (default).</span></span> <span data-ttu-id="d469e-331">허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="d469e-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-332">**Comments**</span></span> | <span data-ttu-id="d469e-333">Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="d469e-334">클라우드 제공 보호 기본 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="d469e-335">Mac용 끝점용 Microsoft Defender의 클라우드 기반 보호 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-336">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-337">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-337">**Key**</span></span> | <span data-ttu-id="d469e-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="d469e-338">cloudService</span></span> |
| <span data-ttu-id="d469e-339">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-339">**Data type**</span></span> | <span data-ttu-id="d469e-340">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="d469e-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d469e-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-341">**Comments**</span></span> | <span data-ttu-id="d469e-342">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="d469e-343">클라우드 제공 보호 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="d469e-344">디바이스에서 클라우드 제공 보호를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="d469e-345">서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-346">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-347">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-347">**Key**</span></span> | <span data-ttu-id="d469e-348">활성화됨</span><span class="sxs-lookup"><span data-stu-id="d469e-348">enabled</span></span> |
| <span data-ttu-id="d469e-349">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-349">**Data type**</span></span> | <span data-ttu-id="d469e-350">부울</span><span class="sxs-lookup"><span data-stu-id="d469e-350">Boolean</span></span> |
| <span data-ttu-id="d469e-351">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-351">**Possible values**</span></span> | <span data-ttu-id="d469e-352">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-352">true (default)</span></span> <br/> <span data-ttu-id="d469e-353">false</span><span class="sxs-lookup"><span data-stu-id="d469e-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="d469e-354">진단 수집 수준</span><span class="sxs-lookup"><span data-stu-id="d469e-354">Diagnostic collection level</span></span>

<span data-ttu-id="d469e-355">진단 데이터는 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="d469e-356">이 설정은 끝점용 Microsoft Defender에서 Microsoft로 전송하는 진단 수준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-357">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-358">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-358">**Key**</span></span> | <span data-ttu-id="d469e-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="d469e-359">diagnosticLevel</span></span> |
| <span data-ttu-id="d469e-360">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-360">**Data type**</span></span> | <span data-ttu-id="d469e-361">String</span><span class="sxs-lookup"><span data-stu-id="d469e-361">String</span></span> |
| <span data-ttu-id="d469e-362">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-362">**Possible values**</span></span> | <span data-ttu-id="d469e-363">선택 사항(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-363">optional (default)</span></span> <br/> <span data-ttu-id="d469e-364">필수</span><span class="sxs-lookup"><span data-stu-id="d469e-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="d469e-365">자동 샘플 제출 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="d469e-366">의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="d469e-367">전송된 파일에 개인 정보가 포함될 가능성이 있는 경우 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-368">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-369">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-369">**Key**</span></span> | <span data-ttu-id="d469e-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="d469e-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="d469e-371">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-371">**Data type**</span></span> | <span data-ttu-id="d469e-372">부울</span><span class="sxs-lookup"><span data-stu-id="d469e-372">Boolean</span></span> |
| <span data-ttu-id="d469e-373">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-373">**Possible values**</span></span> | <span data-ttu-id="d469e-374">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-374">true (default)</span></span> <br/> <span data-ttu-id="d469e-375">false</span><span class="sxs-lookup"><span data-stu-id="d469e-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="d469e-376">자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="d469e-377">보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-378">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-378">**Key**</span></span> | <span data-ttu-id="d469e-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="d469e-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="d469e-380">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-380">**Data type**</span></span> | <span data-ttu-id="d469e-381">부울</span><span class="sxs-lookup"><span data-stu-id="d469e-381">Boolean</span></span> |
| <span data-ttu-id="d469e-382">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-382">**Possible values**</span></span> | <span data-ttu-id="d469e-383">true(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-383">true (default)</span></span> <br/> <span data-ttu-id="d469e-384">false</span><span class="sxs-lookup"><span data-stu-id="d469e-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="d469e-385">사용자 인터페이스 기본 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-385">User interface preferences</span></span>

<span data-ttu-id="d469e-386">Mac용 끝점용 Microsoft Defender의 사용자 인터페이스에 대한 기본 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-387">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-388">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-388">**Key**</span></span> | <span data-ttu-id="d469e-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="d469e-389">userInterface</span></span> |
| <span data-ttu-id="d469e-390">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-390">**Data type**</span></span> | <span data-ttu-id="d469e-391">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="d469e-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d469e-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-392">**Comments**</span></span> | <span data-ttu-id="d469e-393">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="d469e-394">상태 메뉴 아이콘 표시/숨기기</span><span class="sxs-lookup"><span data-stu-id="d469e-394">Show / hide status menu icon</span></span>

<span data-ttu-id="d469e-395">화면의 오른쪽 위 모서리에 상태 메뉴 아이콘을 표시하거나 숨길지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-396">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-397">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-397">**Key**</span></span> | <span data-ttu-id="d469e-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="d469e-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="d469e-399">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-399">**Data type**</span></span> | <span data-ttu-id="d469e-400">부울</span><span class="sxs-lookup"><span data-stu-id="d469e-400">Boolean</span></span> |
| <span data-ttu-id="d469e-401">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-401">**Possible values**</span></span> | <span data-ttu-id="d469e-402">false(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-402">false (default)</span></span> <br/> <span data-ttu-id="d469e-403">true</span><span class="sxs-lookup"><span data-stu-id="d469e-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="d469e-404">피드백을 보내기 위한 표시/숨기기 옵션</span><span class="sxs-lookup"><span data-stu-id="d469e-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="d469e-405">사용자가 로 진행하여 Microsoft에 피드백을 제출할 수 있는지 여부를 `Help`  >  `Send Feedback` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-406">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-407">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-407">**Key**</span></span> | <span data-ttu-id="d469e-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="d469e-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="d469e-409">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-409">**Data type**</span></span> | <span data-ttu-id="d469e-410">String</span><span class="sxs-lookup"><span data-stu-id="d469e-410">String</span></span> |
| <span data-ttu-id="d469e-411">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-411">**Possible values**</span></span> | <span data-ttu-id="d469e-412">사용(기본값)</span><span class="sxs-lookup"><span data-stu-id="d469e-412">enabled (default)</span></span> <br/> <span data-ttu-id="d469e-413">비활성화됨</span><span class="sxs-lookup"><span data-stu-id="d469e-413">disabled</span></span> |
| <span data-ttu-id="d469e-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-414">**Comments**</span></span> | <span data-ttu-id="d469e-415">끝점 버전 101.19.61 이상용 Microsoft Defender에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="d469e-416">끝점 검색 및 응답 기본 설정</span><span class="sxs-lookup"><span data-stu-id="d469e-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="d469e-417">Mac용 끝점용 Microsoft Defender의 끝점 검색 및 응답(EDR) 구성 요소의 기본 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-418">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-419">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-419">**Key**</span></span> | <span data-ttu-id="d469e-420">edr</span><span class="sxs-lookup"><span data-stu-id="d469e-420">edr</span></span> |
| <span data-ttu-id="d469e-421">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-421">**Data type**</span></span> | <span data-ttu-id="d469e-422">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="d469e-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d469e-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-423">**Comments**</span></span> | <span data-ttu-id="d469e-424">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="d469e-425">장치 태그</span><span class="sxs-lookup"><span data-stu-id="d469e-425">Device tags</span></span>

<span data-ttu-id="d469e-426">태그 이름 및 해당 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="d469e-427">GROUP 태그는 지정된 값으로 디바이스에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="d469e-428">태그는 장치 페이지 아래에 있는 포털에 반영되어 디바이스 필터링 및 그룹화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-429">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-430">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-430">**Key**</span></span> | <span data-ttu-id="d469e-431">tags</span><span class="sxs-lookup"><span data-stu-id="d469e-431">tags</span></span> |
| <span data-ttu-id="d469e-432">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-432">**Data type**</span></span> | <span data-ttu-id="d469e-433">사전(중첩된 기본 설정)</span><span class="sxs-lookup"><span data-stu-id="d469e-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d469e-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d469e-434">**Comments**</span></span> | <span data-ttu-id="d469e-435">사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="d469e-436">태그 유형</span><span class="sxs-lookup"><span data-stu-id="d469e-436">Type of tag</span></span>

<span data-ttu-id="d469e-437">태그 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-438">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-439">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-439">**Key**</span></span> | <span data-ttu-id="d469e-440">키</span><span class="sxs-lookup"><span data-stu-id="d469e-440">key</span></span> |
| <span data-ttu-id="d469e-441">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-441">**Data type**</span></span> | <span data-ttu-id="d469e-442">String</span><span class="sxs-lookup"><span data-stu-id="d469e-442">String</span></span> |
| <span data-ttu-id="d469e-443">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="d469e-444">태그 값</span><span class="sxs-lookup"><span data-stu-id="d469e-444">Value of tag</span></span>

<span data-ttu-id="d469e-445">태그 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="d469e-446">**도메인**</span><span class="sxs-lookup"><span data-stu-id="d469e-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="d469e-447">**키**</span><span class="sxs-lookup"><span data-stu-id="d469e-447">**Key**</span></span> | <span data-ttu-id="d469e-448">값</span><span class="sxs-lookup"><span data-stu-id="d469e-448">value</span></span> |
| <span data-ttu-id="d469e-449">**Data type**</span><span class="sxs-lookup"><span data-stu-id="d469e-449">**Data type**</span></span> | <span data-ttu-id="d469e-450">String</span><span class="sxs-lookup"><span data-stu-id="d469e-450">String</span></span> |
| <span data-ttu-id="d469e-451">**사용 가능한 값:**</span><span class="sxs-lookup"><span data-stu-id="d469e-451">**Possible values**</span></span> | <span data-ttu-id="d469e-452">모든 문자열</span><span class="sxs-lookup"><span data-stu-id="d469e-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="d469e-453">태그 유형당 하나의 값만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="d469e-454">태그 유형은 고유하며 동일한 구성 프로필에서 반복하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="d469e-455">권장 구성 프로필</span><span class="sxs-lookup"><span data-stu-id="d469e-455">Recommended configuration profile</span></span>

<span data-ttu-id="d469e-456">시작하려면 엔터프라이즈에서 Microsoft Defender for Endpoint에서 제공하는 모든 보호 기능을 활용하기 위해 다음 구성을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="d469e-457">다음 구성 프로필(또는 JAMF의 경우 사용자 지정 설정 구성 프로필에 업로드할 수 있는 속성 목록)은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="d469e-458">RTP(실시간 보호) 사용</span><span class="sxs-lookup"><span data-stu-id="d469e-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="d469e-459">다음 위협 유형을 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="d469e-460">**잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="d469e-461">**보관함(압축률이** 높은 파일)이 끝점 로그에 대한 Microsoft Defender에 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="d469e-462">자동 보안 인텔리전스 업데이트 사용</span><span class="sxs-lookup"><span data-stu-id="d469e-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="d469e-463">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="d469e-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="d469e-464">자동 샘플 제출 사용</span><span class="sxs-lookup"><span data-stu-id="d469e-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="d469e-465">JAMF 구성 프로필의 속성 목록</span><span class="sxs-lookup"><span data-stu-id="d469e-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="d469e-466">Intune 프로필</span><span class="sxs-lookup"><span data-stu-id="d469e-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="d469e-467">전체 구성 프로필 예제</span><span class="sxs-lookup"><span data-stu-id="d469e-467">Full configuration profile example</span></span>

<span data-ttu-id="d469e-468">다음 템플릿은 이 문서에 설명된 모든 설정에 대한 항목을 포함하며 Mac용 끝점용 Microsoft Defender를 더 많이 제어하려는 고급 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="d469e-469">JAMF 구성 프로필의 속성 목록</span><span class="sxs-lookup"><span data-stu-id="d469e-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="d469e-470">Intune 프로필</span><span class="sxs-lookup"><span data-stu-id="d469e-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="d469e-471">속성 목록 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d469e-471">Property list validation</span></span>

<span data-ttu-id="d469e-472">속성 목록은 유효한 *.plist 파일입니다.*</span><span class="sxs-lookup"><span data-stu-id="d469e-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="d469e-473">다음을 실행하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="d469e-474">파일이 잘 형식이면 위의 명령은 의 종료 코드를 `OK` 출력하고 `0` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="d469e-475">그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="d469e-476">구성 프로필 배포</span><span class="sxs-lookup"><span data-stu-id="d469e-476">Configuration profile deployment</span></span>

<span data-ttu-id="d469e-477">엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 콘솔을 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="d469e-478">다음 섹션에서는 JAMF 및 Intune을 사용하여 이 프로필을 배포하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="d469e-479">JAMF 배포</span><span class="sxs-lookup"><span data-stu-id="d469e-479">JAMF deployment</span></span>

<span data-ttu-id="d469e-480">JAMF 콘솔에서 컴퓨터 구성 프로필을 열고 사용할 구성 프로필로 이동한 다음  >  사용자 지정 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d469e-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="d469e-481">기본 설정 도메인으로 항목을 만들고 앞에서 생성한 `com.microsoft.wdav` *.plist를* 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="d469e-482">올바른 기본 설정 도메인( )을 입력해야 합니다. 그렇지 않으면 끝점용 Microsoft Defender에서 기본 설정이 `com.microsoft.wdav` 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="d469e-483">Intune 배포</span><span class="sxs-lookup"><span data-stu-id="d469e-483">Intune deployment</span></span>

1. <span data-ttu-id="d469e-484">장치 **구성 관리를**  >  **니다.**</span><span class="sxs-lookup"><span data-stu-id="d469e-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="d469e-485">프로필 **만들기**  >  **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d469e-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="d469e-486">프로필 이름을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="d469e-486">Choose a name for the profile.</span></span> <span data-ttu-id="d469e-487">**Platform=macOS를** **프로필 유형=사용자 지정으로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="d469e-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="d469e-488">구성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-488">Select Configure.</span></span>

3. <span data-ttu-id="d469e-489">앞에서 생성한 .plist를 로 `com.microsoft.wdav.xml` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="d469e-490">사용자 `com.microsoft.wdav` 지정 구성 프로필 이름으로 **를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="d469e-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="d469e-491">구성 프로필을 열고 파일을 `com.microsoft.wdav.xml` 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="d469e-492">이 파일은 3단계에서 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="d469e-493">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-493">Select **OK**.</span></span>

7. <span data-ttu-id="d469e-494">배정   >  **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d469e-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="d469e-495">포함 **탭에서** 모든 사용자 및 모든 & **할당을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d469e-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="d469e-496">올바른 사용자 지정 구성 프로필 이름을 입력해야 합니다. 그렇지 않으면 이러한 기본 설정이 끝점용 Microsoft Defender에서 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d469e-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="d469e-497">리소스</span><span class="sxs-lookup"><span data-stu-id="d469e-497">Resources</span></span>

- [<span data-ttu-id="d469e-498">구성 프로필 참조(Apple 개발자 문서)</span><span class="sxs-lookup"><span data-stu-id="d469e-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
