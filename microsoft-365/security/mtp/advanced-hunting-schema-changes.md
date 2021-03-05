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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cd06286083297d0930270868b99a14f8ddb2f4b2
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461670"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="7b045-104">고급 헌팅 스마 - 이름 변경</span><span class="sxs-lookup"><span data-stu-id="7b045-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7b045-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7b045-105">**Applies to:**</span></span>
- <span data-ttu-id="7b045-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7b045-107">고급 [헌팅 스마는](advanced-hunting-schema-tables.md) 정기적으로 업데이트되어 새 테이블과 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="7b045-108">사용자 환경을 개선하기 위해 기존 열 이름을 바꾸거나 바꾸는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="7b045-109">이 문서를 참조하여 쿼리에 영향을 줄 수 있는 이름 변경 내용을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="7b045-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="7b045-110">사용자 지정 검색 규칙에 사용되는 쿼리를 포함하여 보안 센터에 저장된 쿼리에 이름 변경 내용이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="7b045-111">이러한 쿼리를 수동으로 업데이트할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="7b045-112">그러나 다음 쿼리를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="7b045-113">API를 사용하여 실행된 쿼리</span><span class="sxs-lookup"><span data-stu-id="7b045-113">Queries that are run using the API</span></span>
- <span data-ttu-id="7b045-114">보안 센터 외부에 저장된 쿼리</span><span class="sxs-lookup"><span data-stu-id="7b045-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="7b045-115">2020년 12월</span><span class="sxs-lookup"><span data-stu-id="7b045-115">December 2020</span></span>

| <span data-ttu-id="7b045-116">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-116">Table name</span></span> | <span data-ttu-id="7b045-117">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-117">Original column name</span></span> | <span data-ttu-id="7b045-118">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-118">New column name</span></span> | <span data-ttu-id="7b045-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7b045-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="7b045-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7b045-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="7b045-121">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-121">Customer feedback</span></span> |
| [<span data-ttu-id="7b045-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7b045-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="7b045-123">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-123">Customer feedback</span></span> |
| [<span data-ttu-id="7b045-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7b045-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="7b045-125">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="7b045-126">2021년 1월</span><span class="sxs-lookup"><span data-stu-id="7b045-126">January 2021</span></span>

| <span data-ttu-id="7b045-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-127">Column name</span></span> | <span data-ttu-id="7b045-128">원래 값 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-128">Original value name</span></span> | <span data-ttu-id="7b045-129">새 값 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-129">New value name</span></span> | <span data-ttu-id="7b045-130">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7b045-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="7b045-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="7b045-131">MCAS</span></span> |    <span data-ttu-id="7b045-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7b045-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="7b045-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="7b045-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="7b045-135">EDR</span><span class="sxs-lookup"><span data-stu-id="7b045-135">EDR</span></span>| <span data-ttu-id="7b045-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="7b045-137">WindowsDefenderAv</span></span> | <span data-ttu-id="7b045-138">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="7b045-138">Antivirus</span></span> | <span data-ttu-id="7b045-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="7b045-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="7b045-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="7b045-141">SmartScreen</span></span> | <span data-ttu-id="7b045-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="7b045-143">CustomerTI</span></span> |  <span data-ttu-id="7b045-144">사용자 지정 TI</span><span class="sxs-lookup"><span data-stu-id="7b045-144">Custom TI</span></span> | <span data-ttu-id="7b045-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="7b045-146">OfficeATP</span></span> | <span data-ttu-id="7b045-147">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="7b045-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-149">MTP</span><span class="sxs-lookup"><span data-stu-id="7b045-149">MTP</span></span>   | <span data-ttu-id="7b045-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="7b045-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="7b045-152">AzureATP</span></span> |    <span data-ttu-id="7b045-153">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="7b045-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="7b045-155">CustomDetection</span></span>   | <span data-ttu-id="7b045-156">사용자 지정 검색</span><span class="sxs-lookup"><span data-stu-id="7b045-156">Custom detection</span></span> | <span data-ttu-id="7b045-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="7b045-158">AutomatedInvestigation</span></span> |<span data-ttu-id="7b045-159">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="7b045-159">Automated investigation</span></span> | <span data-ttu-id="7b045-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="7b045-161">ThreatExperts</span></span> | <span data-ttu-id="7b045-162">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="7b045-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="7b045-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="7b045-164">제3자 TI</span><span class="sxs-lookup"><span data-stu-id="7b045-164">3rd party TI</span></span> | <span data-ttu-id="7b045-165">제3자 센서</span><span class="sxs-lookup"><span data-stu-id="7b045-165">3rd Party sensors</span></span> | <span data-ttu-id="7b045-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="7b045-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="7b045-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="7b045-168">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="7b045-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="7b045-170">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="7b045-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="7b045-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="7b045-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="7b045-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="7b045-173">Office 365 ATP</span></span>  |<span data-ttu-id="7b045-174">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="7b045-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="7b045-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="7b045-176">Azure ATP</span></span>    |<span data-ttu-id="7b045-177">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7b045-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="7b045-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="7b045-178">Rebranding</span></span> |

<span data-ttu-id="7b045-179">`DetectionSource` 은 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="7b045-180">`ServiceSource` 은 [AlertEvidence](advanced-hunting-alertevidence-table.md) 및 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="7b045-181">2021년 2월</span><span class="sxs-lookup"><span data-stu-id="7b045-181">February 2021</span></span>

1. <span data-ttu-id="7b045-182">[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) 및 [EmailEvents](advanced-hunting-emailevents-table.md) 테이블에서는 및 열을 더는 사용하지 `MalwareFilterVerdict` `PhishFilterVerdict` `ThreatTypes` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, we deprecated the `MalwareFilterVerdict`and `PhishFilterVerdict` columns and replaced them with the `ThreatTypes` column.</span></span> <span data-ttu-id="7b045-183">또한 및 열을 더는 사용 안 하여 `MalwareDetectionMethod` `PhishDetectionMethod` 열로 `DetectionMethods` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-183">We also deprecated the `MalwareDetectionMethod` and `PhishDetectionMethod` columns and replaced them with the `DetectionMethods` column.</span></span> <span data-ttu-id="7b045-184">이 간소화를 통해 새 열 아래에 추가 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="7b045-185">매핑은 아래에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-185">The mapping is provided below.</span></span>

| <span data-ttu-id="7b045-186">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-186">Table name</span></span> | <span data-ttu-id="7b045-187">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-187">Original column name</span></span> | <span data-ttu-id="7b045-188">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-188">New column name</span></span> | <span data-ttu-id="7b045-189">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7b045-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="7b045-190">추가 검색 방법 포함</span><span class="sxs-lookup"><span data-stu-id="7b045-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="7b045-191">더 많은 위협 유형 포함</span><span class="sxs-lookup"><span data-stu-id="7b045-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="7b045-192">추가 검색 방법 포함</span><span class="sxs-lookup"><span data-stu-id="7b045-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="7b045-193">더 많은 위협 유형 포함</span><span class="sxs-lookup"><span data-stu-id="7b045-193">Include more threat types</span></span> |


2. <span data-ttu-id="7b045-194">및 테이블에 전자 메일 위협에 대한 자세한 정보를 제공하기 위해 `EmailAttachmentInfo` `EmailEvents` `ThreatNames` 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, we added the column `ThreatNames` to give more information about the email threat.</span></span> <span data-ttu-id="7b045-195">이 열에는 스팸 또는 피싱과 같은 값이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="7b045-196">[DeviceInfo](advanced-hunting-deviceinfo-table.md) 테이블에서 고객 의견에 따라 열을 `DeviceObjectId` `AadDeviceId` 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, we replaced the `DeviceObjectId` column with `AadDeviceId` based on customer feedback.</span></span>

4. <span data-ttu-id="7b045-197">[DeviceEvents](advanced-hunting-deviceevents-table.md) 테이블에서 작업 설명을 보다 잘 반영하기 위해 몇 가지 ActionType 이름을 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, we updated several ActionType names to better reflect the description of the action.</span></span> <span data-ttu-id="7b045-198">세부 정보는 아래에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-198">Details can be found below.</span></span>

| <span data-ttu-id="7b045-199">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-199">Table name</span></span> | <span data-ttu-id="7b045-200">Original ActionType 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-200">Original ActionType name</span></span> | <span data-ttu-id="7b045-201">새 ActionType 이름</span><span class="sxs-lookup"><span data-stu-id="7b045-201">New ActionType name</span></span> | <span data-ttu-id="7b045-202">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7b045-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="7b045-203">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="7b045-204">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="7b045-205">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="7b045-206">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-206">Customer feedback</span></span> |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | <span data-ttu-id="7b045-207">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="7b045-207">Customer feedback</span></span> |





## <a name="related-topics"></a><span data-ttu-id="7b045-208">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7b045-208">Related topics</span></span>
- [<span data-ttu-id="7b045-209">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="7b045-209">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7b045-210">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="7b045-210">Understand the schema</span></span>](advanced-hunting-schema-tables.md)