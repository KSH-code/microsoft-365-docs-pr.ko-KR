---
title: Microsoft 365 Defender 고급 헌팅 스위마의 이름 변경 사항
description: 고급 헌팅 스위마의 변경 테이블 및 열 이름 변경 추적 및 검토
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 스마 참조, kusto, 표, 데이터, 명명 변경, 이름 변경
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eb6dfa628488239e3953d19d5e78b338e76f50a2
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023788"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="248dd-104">고급 헌팅 스마 - 이름 변경</span><span class="sxs-lookup"><span data-stu-id="248dd-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="248dd-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="248dd-105">**Applies to:**</span></span>
- <span data-ttu-id="248dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="248dd-107">고급 [헌팅 스마는](advanced-hunting-schema-tables.md) 정기적으로 업데이트되어 새 테이블과 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="248dd-108">사용자 환경을 개선하기 위해 기존 열 이름을 바꾸거나 바꾸는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="248dd-109">이 문서를 참조하여 쿼리에 영향을 줄 수 있는 이름 변경 내용을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="248dd-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="248dd-110">사용자 지정 검색 규칙에 사용되는 쿼리를 포함하여 보안 센터에 저장된 쿼리에 이름 변경 내용이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="248dd-111">이러한 쿼리를 수동으로 업데이트할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="248dd-112">그러나 다음 쿼리를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="248dd-113">API를 사용하여 실행된 쿼리</span><span class="sxs-lookup"><span data-stu-id="248dd-113">Queries that are run using the API</span></span>
- <span data-ttu-id="248dd-114">보안 센터 외부에 저장된 쿼리</span><span class="sxs-lookup"><span data-stu-id="248dd-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="248dd-115">2020년 12월</span><span class="sxs-lookup"><span data-stu-id="248dd-115">December 2020</span></span>

| <span data-ttu-id="248dd-116">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-116">Table name</span></span> | <span data-ttu-id="248dd-117">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-117">Original column name</span></span> | <span data-ttu-id="248dd-118">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-118">New column name</span></span> | <span data-ttu-id="248dd-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="248dd-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="248dd-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="248dd-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="248dd-121">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="248dd-121">Customer feedback</span></span> |
| [<span data-ttu-id="248dd-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="248dd-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="248dd-123">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="248dd-123">Customer feedback</span></span> |
| [<span data-ttu-id="248dd-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="248dd-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="248dd-125">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="248dd-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="248dd-126">2021년 1월</span><span class="sxs-lookup"><span data-stu-id="248dd-126">January 2021</span></span>

| <span data-ttu-id="248dd-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-127">Column name</span></span> | <span data-ttu-id="248dd-128">원래 값 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-128">Original value name</span></span> | <span data-ttu-id="248dd-129">새 값 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-129">New value name</span></span> | <span data-ttu-id="248dd-130">변경 이유</span><span class="sxs-lookup"><span data-stu-id="248dd-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="248dd-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="248dd-131">MCAS</span></span> |    <span data-ttu-id="248dd-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="248dd-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="248dd-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="248dd-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="248dd-135">EDR</span><span class="sxs-lookup"><span data-stu-id="248dd-135">EDR</span></span>| <span data-ttu-id="248dd-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="248dd-137">WindowsDefenderAv</span></span> | <span data-ttu-id="248dd-138">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="248dd-138">Antivirus</span></span> | <span data-ttu-id="248dd-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="248dd-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="248dd-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="248dd-141">SmartScreen</span></span> | <span data-ttu-id="248dd-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="248dd-143">CustomerTI</span></span> |  <span data-ttu-id="248dd-144">사용자 지정 TI</span><span class="sxs-lookup"><span data-stu-id="248dd-144">Custom TI</span></span> | <span data-ttu-id="248dd-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="248dd-146">OfficeATP</span></span> | <span data-ttu-id="248dd-147">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="248dd-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-149">MTP</span><span class="sxs-lookup"><span data-stu-id="248dd-149">MTP</span></span>   | <span data-ttu-id="248dd-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="248dd-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="248dd-152">AzureATP</span></span> |    <span data-ttu-id="248dd-153">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="248dd-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="248dd-155">CustomDetection</span></span>   | <span data-ttu-id="248dd-156">사용자 지정 검색</span><span class="sxs-lookup"><span data-stu-id="248dd-156">Custom detection</span></span> | <span data-ttu-id="248dd-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="248dd-158">AutomatedInvestigation</span></span> |<span data-ttu-id="248dd-159">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="248dd-159">Automated investigation</span></span> | <span data-ttu-id="248dd-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="248dd-161">ThreatExperts</span></span> | <span data-ttu-id="248dd-162">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="248dd-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="248dd-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="248dd-164">제3자 TI</span><span class="sxs-lookup"><span data-stu-id="248dd-164">3rd party TI</span></span> | <span data-ttu-id="248dd-165">제3자 센서</span><span class="sxs-lookup"><span data-stu-id="248dd-165">3rd Party sensors</span></span> | <span data-ttu-id="248dd-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="248dd-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="248dd-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="248dd-168">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="248dd-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="248dd-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="248dd-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="248dd-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="248dd-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="248dd-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="248dd-173">Office 365 ATP</span></span>  |<span data-ttu-id="248dd-174">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="248dd-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="248dd-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="248dd-176">Azure ATP</span></span>    |<span data-ttu-id="248dd-177">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="248dd-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="248dd-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="248dd-178">Rebranding</span></span> |

<span data-ttu-id="248dd-179">`DetectionSource` 은 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="248dd-180">`ServiceSource` 은 [AlertEvidence](advanced-hunting-alertevidence-table.md) 및 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="248dd-181">2021년 2월</span><span class="sxs-lookup"><span data-stu-id="248dd-181">February 2021</span></span>

1. <span data-ttu-id="248dd-182">[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) 및 [EmailEvents](advanced-hunting-emailevents-table.md) 테이블에서 및 열이 `MalwareFilterVerdict` `PhishFilterVerdict` 열로 `ThreatTypes` 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="248dd-183">및 `MalwareDetectionMethod` `PhishDetectionMethod` 열도 열로 `DetectionMethods` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="248dd-184">이 간소화를 통해 새 열 아래에 추가 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="248dd-185">매핑은 아래에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-185">The mapping is provided below.</span></span>

| <span data-ttu-id="248dd-186">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-186">Table name</span></span> | <span data-ttu-id="248dd-187">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-187">Original column name</span></span> | <span data-ttu-id="248dd-188">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-188">New column name</span></span> | <span data-ttu-id="248dd-189">변경 이유</span><span class="sxs-lookup"><span data-stu-id="248dd-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="248dd-190">추가 검색 방법 포함</span><span class="sxs-lookup"><span data-stu-id="248dd-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="248dd-191">더 많은 위협 유형 포함</span><span class="sxs-lookup"><span data-stu-id="248dd-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="248dd-192">추가 검색 방법 포함</span><span class="sxs-lookup"><span data-stu-id="248dd-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="248dd-193">더 많은 위협 유형 포함</span><span class="sxs-lookup"><span data-stu-id="248dd-193">Include more threat types</span></span> |


2. <span data-ttu-id="248dd-194">및 테이블에 전자 메일 위협에 대한 자세한 정보를 제공하기 위해 `EmailAttachmentInfo` `EmailEvents` `ThreatNames` 열이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="248dd-195">이 열에는 스팸 또는 피싱과 같은 값이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="248dd-196">[DeviceInfo](advanced-hunting-deviceinfo-table.md) 테이블에서 열은 고객 의견에 따라 `DeviceObjectId` `AadDeviceId` 열로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="248dd-197">[DeviceEvents](advanced-hunting-deviceevents-table.md) 테이블에서는 작업 설명을 보다 잘 반영하기 위해 여러 ActionType 이름이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="248dd-198">변경 내용에 대한 자세한 내용은 아래에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="248dd-199">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-199">Table name</span></span> | <span data-ttu-id="248dd-200">Original ActionType 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-200">Original ActionType name</span></span> | <span data-ttu-id="248dd-201">새 ActionType 이름</span><span class="sxs-lookup"><span data-stu-id="248dd-201">New ActionType name</span></span> | <span data-ttu-id="248dd-202">변경 이유</span><span class="sxs-lookup"><span data-stu-id="248dd-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="248dd-203">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="248dd-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="248dd-204">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="248dd-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="248dd-205">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="248dd-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="248dd-206">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="248dd-206">Customer feedback</span></span> |

## <a name="march-2021"></a><span data-ttu-id="248dd-207">2021년 3월</span><span class="sxs-lookup"><span data-stu-id="248dd-207">March 2021</span></span>

<span data-ttu-id="248dd-208">테이블이 `DeviceTvmSoftwareInventoryVulnerabilities` 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-208">The `DeviceTvmSoftwareInventoryVulnerabilities` table has been deprecated.</span></span> <span data-ttu-id="248dd-209">및 테이블을 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 바꾸는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="248dd-209">Replacing it are the `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables.</span></span>



## <a name="related-topics"></a><span data-ttu-id="248dd-210">관련 항목</span><span class="sxs-lookup"><span data-stu-id="248dd-210">Related topics</span></span>
- [<span data-ttu-id="248dd-211">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="248dd-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="248dd-212">스키마에 대한 이해</span><span class="sxs-lookup"><span data-stu-id="248dd-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)