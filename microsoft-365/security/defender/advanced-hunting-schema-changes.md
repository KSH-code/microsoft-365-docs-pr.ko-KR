---
title: Microsoft 365 Defender 고급 헌팅 스위마의 이름 변경 사항
description: 고급 헌팅 스위마의 변경 테이블 및 열 이름 변경 추적 및 검토
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 데이터, 명명 변경, 이름 변경, 이름 변경, Microsoft Threat Protection
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
ms.openlocfilehash: ab6bdefb457fb31df98d829ee801b72f4c8ae70a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499697"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="3249f-104">고급 헌팅 스마 - 이름 변경</span><span class="sxs-lookup"><span data-stu-id="3249f-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3249f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3249f-105">**Applies to:**</span></span>
- <span data-ttu-id="3249f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3249f-107">고급 [헌팅 스마는](advanced-hunting-schema-tables.md) 정기적으로 업데이트되어 새 테이블과 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="3249f-108">사용자 환경을 개선하기 위해 기존 열 이름을 바꾸거나 바꾸는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="3249f-109">이 문서를 참조하여 쿼리에 영향을 줄 수 있는 이름 변경 내용을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="3249f-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="3249f-110">사용자 지정 검색 규칙에 사용되는 쿼리를 포함하여 보안 센터에 저장된 쿼리에 이름 변경 내용이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="3249f-111">이러한 쿼리를 수동으로 업데이트할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="3249f-112">그러나 다음 쿼리를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="3249f-113">API를 사용하여 실행된 쿼리</span><span class="sxs-lookup"><span data-stu-id="3249f-113">Queries that are run using the API</span></span>
- <span data-ttu-id="3249f-114">보안 센터 외부에 저장된 쿼리</span><span class="sxs-lookup"><span data-stu-id="3249f-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="3249f-115">2020년 12월</span><span class="sxs-lookup"><span data-stu-id="3249f-115">December 2020</span></span>

| <span data-ttu-id="3249f-116">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-116">Table name</span></span> | <span data-ttu-id="3249f-117">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-117">Original column name</span></span> | <span data-ttu-id="3249f-118">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-118">New column name</span></span> | <span data-ttu-id="3249f-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3249f-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="3249f-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="3249f-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="3249f-121">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="3249f-121">Customer feedback</span></span> |
| [<span data-ttu-id="3249f-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="3249f-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="3249f-123">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="3249f-123">Customer feedback</span></span> |
| [<span data-ttu-id="3249f-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="3249f-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="3249f-125">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="3249f-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="3249f-126">2021년 1월</span><span class="sxs-lookup"><span data-stu-id="3249f-126">January 2021</span></span>

| <span data-ttu-id="3249f-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-127">Column name</span></span> | <span data-ttu-id="3249f-128">원래 값 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-128">Original value name</span></span> | <span data-ttu-id="3249f-129">새 값 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-129">New value name</span></span> | <span data-ttu-id="3249f-130">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3249f-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="3249f-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="3249f-131">MCAS</span></span> |    <span data-ttu-id="3249f-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3249f-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="3249f-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="3249f-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="3249f-135">EDR</span><span class="sxs-lookup"><span data-stu-id="3249f-135">EDR</span></span>| <span data-ttu-id="3249f-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="3249f-137">WindowsDefenderAv</span></span> | <span data-ttu-id="3249f-138">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="3249f-138">Antivirus</span></span> | <span data-ttu-id="3249f-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="3249f-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="3249f-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="3249f-141">SmartScreen</span></span> | <span data-ttu-id="3249f-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="3249f-143">CustomerTI</span></span> |  <span data-ttu-id="3249f-144">사용자 지정 TI</span><span class="sxs-lookup"><span data-stu-id="3249f-144">Custom TI</span></span> | <span data-ttu-id="3249f-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="3249f-146">OfficeATP</span></span> | <span data-ttu-id="3249f-147">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="3249f-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-149">MTP</span><span class="sxs-lookup"><span data-stu-id="3249f-149">MTP</span></span>   | <span data-ttu-id="3249f-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="3249f-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="3249f-152">AzureATP</span></span> |    <span data-ttu-id="3249f-153">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="3249f-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="3249f-155">CustomDetection</span></span>   | <span data-ttu-id="3249f-156">사용자 지정 검색</span><span class="sxs-lookup"><span data-stu-id="3249f-156">Custom detection</span></span> | <span data-ttu-id="3249f-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="3249f-158">AutomatedInvestigation</span></span> |<span data-ttu-id="3249f-159">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="3249f-159">Automated investigation</span></span> | <span data-ttu-id="3249f-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="3249f-161">ThreatExperts</span></span> | <span data-ttu-id="3249f-162">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="3249f-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="3249f-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="3249f-164">제3자 TI</span><span class="sxs-lookup"><span data-stu-id="3249f-164">3rd party TI</span></span> | <span data-ttu-id="3249f-165">제3자 센서</span><span class="sxs-lookup"><span data-stu-id="3249f-165">3rd Party sensors</span></span> | <span data-ttu-id="3249f-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="3249f-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3249f-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="3249f-168">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="3249f-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="3249f-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3249f-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="3249f-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="3249f-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="3249f-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="3249f-173">Office 365 ATP</span></span>  |<span data-ttu-id="3249f-174">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="3249f-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="3249f-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="3249f-176">Azure ATP</span></span>    |<span data-ttu-id="3249f-177">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3249f-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="3249f-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="3249f-178">Rebranding</span></span> |

<span data-ttu-id="3249f-179">`DetectionSource` 은 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="3249f-180">`ServiceSource` 은 [AlertEvidence](advanced-hunting-alertevidence-table.md) 및 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="3249f-181">2021년 2월</span><span class="sxs-lookup"><span data-stu-id="3249f-181">February 2021</span></span>

1. <span data-ttu-id="3249f-182">[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) 및 [EmailEvents](advanced-hunting-emailevents-table.md) 테이블에서 및 열이 `MalwareFilterVerdict` `PhishFilterVerdict` 열로 `ThreatTypes` 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="3249f-183">및 `MalwareDetectionMethod` `PhishDetectionMethod` 열도 열로 `DetectionMethods` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="3249f-184">이 간소화를 통해 새 열 아래에 추가 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="3249f-185">매핑은 아래에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-185">The mapping is provided below.</span></span>

| <span data-ttu-id="3249f-186">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-186">Table name</span></span> | <span data-ttu-id="3249f-187">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-187">Original column name</span></span> | <span data-ttu-id="3249f-188">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-188">New column name</span></span> | <span data-ttu-id="3249f-189">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3249f-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="3249f-190">추가 검색 방법 포함</span><span class="sxs-lookup"><span data-stu-id="3249f-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="3249f-191">더 많은 위협 유형 포함</span><span class="sxs-lookup"><span data-stu-id="3249f-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="3249f-192">추가 검색 방법 포함</span><span class="sxs-lookup"><span data-stu-id="3249f-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="3249f-193">더 많은 위협 유형 포함</span><span class="sxs-lookup"><span data-stu-id="3249f-193">Include more threat types</span></span> |


2. <span data-ttu-id="3249f-194">및 테이블에 전자 메일 위협에 대한 자세한 정보를 제공하기 위해 `EmailAttachmentInfo` `EmailEvents` `ThreatNames` 열이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="3249f-195">이 열에는 스팸 또는 피싱과 같은 값이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="3249f-196">[DeviceInfo](advanced-hunting-deviceinfo-table.md) 테이블에서 열은 고객 의견에 따라 `DeviceObjectId` `AadDeviceId` 열로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="3249f-197">[DeviceEvents](advanced-hunting-deviceevents-table.md) 테이블에서는 작업 설명을 보다 잘 반영하기 위해 여러 ActionType 이름이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="3249f-198">변경 내용에 대한 자세한 내용은 아래에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3249f-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="3249f-199">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-199">Table name</span></span> | <span data-ttu-id="3249f-200">Original ActionType 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-200">Original ActionType name</span></span> | <span data-ttu-id="3249f-201">새 ActionType 이름</span><span class="sxs-lookup"><span data-stu-id="3249f-201">New ActionType name</span></span> | <span data-ttu-id="3249f-202">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3249f-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="3249f-203">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="3249f-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="3249f-204">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="3249f-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="3249f-205">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="3249f-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="3249f-206">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="3249f-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="3249f-207">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3249f-207">Related topics</span></span>
- [<span data-ttu-id="3249f-208">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="3249f-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3249f-209">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="3249f-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)