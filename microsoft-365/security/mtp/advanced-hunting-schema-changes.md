---
title: Microsoft 365 Defender 고급 헌팅의 이름 변경 사항
description: 고급 헌팅chema에서 이름 변경 테이블 및 열 추적 및 검토
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066872"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="15fc6-104">고급 헌팅 스마 - 이름 변경</span><span class="sxs-lookup"><span data-stu-id="15fc6-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15fc6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="15fc6-105">**Applies to:**</span></span>
- <span data-ttu-id="15fc6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="15fc6-107">고급 [헌팅 스마는](advanced-hunting-schema-tables.md) 정기적으로 업데이트되어 새 테이블과 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="15fc6-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="15fc6-108">사용자 환경을 개선하기 위해 기존 열 이름을 바꾸거나 바꾸는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15fc6-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="15fc6-109">이 문서를 참조하여 쿼리에 영향을 줄 수 있는 이름 변경 내용을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="15fc6-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="15fc6-110">사용자 지정 검색 규칙에 사용되는 쿼리를 포함하여 보안 센터에 저장된 쿼리에 이름 변경 내용이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="15fc6-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="15fc6-111">이러한 쿼리를 수동으로 업데이트할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15fc6-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="15fc6-112">그러나 다음 쿼리를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fc6-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="15fc6-113">API를 사용하여 실행된 쿼리</span><span class="sxs-lookup"><span data-stu-id="15fc6-113">Queries that are run using the API</span></span>
- <span data-ttu-id="15fc6-114">보안 센터 외부에 저장된 쿼리</span><span class="sxs-lookup"><span data-stu-id="15fc6-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="15fc6-115">2020년 12월</span><span class="sxs-lookup"><span data-stu-id="15fc6-115">December 2020</span></span>

| <span data-ttu-id="15fc6-116">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="15fc6-116">Table name</span></span> | <span data-ttu-id="15fc6-117">원래 열 이름</span><span class="sxs-lookup"><span data-stu-id="15fc6-117">Original column name</span></span> | <span data-ttu-id="15fc6-118">새 열 이름</span><span class="sxs-lookup"><span data-stu-id="15fc6-118">New column name</span></span> | <span data-ttu-id="15fc6-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="15fc6-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="15fc6-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="15fc6-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="15fc6-121">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="15fc6-121">Customer feedback</span></span> |
| [<span data-ttu-id="15fc6-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="15fc6-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="15fc6-123">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="15fc6-123">Customer feedback</span></span> |
| [<span data-ttu-id="15fc6-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="15fc6-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="15fc6-125">고객 피드백</span><span class="sxs-lookup"><span data-stu-id="15fc6-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="15fc6-126">2021년 1월</span><span class="sxs-lookup"><span data-stu-id="15fc6-126">January 2021</span></span>

| <span data-ttu-id="15fc6-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="15fc6-127">Column name</span></span> | <span data-ttu-id="15fc6-128">원래 값 이름</span><span class="sxs-lookup"><span data-stu-id="15fc6-128">Original value name</span></span> | <span data-ttu-id="15fc6-129">새 값 이름</span><span class="sxs-lookup"><span data-stu-id="15fc6-129">New value name</span></span> | <span data-ttu-id="15fc6-130">변경 이유</span><span class="sxs-lookup"><span data-stu-id="15fc6-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="15fc6-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="15fc6-131">MCAS</span></span> |    <span data-ttu-id="15fc6-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="15fc6-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="15fc6-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="15fc6-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="15fc6-135">EDR</span><span class="sxs-lookup"><span data-stu-id="15fc6-135">EDR</span></span>| <span data-ttu-id="15fc6-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="15fc6-137">WindowsDefenderAv</span></span> | <span data-ttu-id="15fc6-138">바이러스 검사</span><span class="sxs-lookup"><span data-stu-id="15fc6-138">Antivirus</span></span> | <span data-ttu-id="15fc6-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="15fc6-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="15fc6-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="15fc6-141">SmartScreen</span></span> | <span data-ttu-id="15fc6-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="15fc6-143">CustomerTI</span></span> |  <span data-ttu-id="15fc6-144">사용자 지정 TI</span><span class="sxs-lookup"><span data-stu-id="15fc6-144">Custom TI</span></span> | <span data-ttu-id="15fc6-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="15fc6-146">OfficeATP</span></span> | <span data-ttu-id="15fc6-147">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="15fc6-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-149">MTP</span><span class="sxs-lookup"><span data-stu-id="15fc6-149">MTP</span></span>   | <span data-ttu-id="15fc6-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="15fc6-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="15fc6-152">AzureATP</span></span> |    <span data-ttu-id="15fc6-153">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="15fc6-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="15fc6-155">CustomDetection</span></span>   | <span data-ttu-id="15fc6-156">사용자 지정 검색</span><span class="sxs-lookup"><span data-stu-id="15fc6-156">Custom detection</span></span> | <span data-ttu-id="15fc6-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="15fc6-158">AutomatedInvestigation</span></span> |<span data-ttu-id="15fc6-159">자동화된 조사</span><span class="sxs-lookup"><span data-stu-id="15fc6-159">Automated investigation</span></span> | <span data-ttu-id="15fc6-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="15fc6-161">ThreatExperts</span></span> | <span data-ttu-id="15fc6-162">Microsoft 위협 전문가</span><span class="sxs-lookup"><span data-stu-id="15fc6-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="15fc6-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="15fc6-164">제3자 TI</span><span class="sxs-lookup"><span data-stu-id="15fc6-164">3rd party TI</span></span> | <span data-ttu-id="15fc6-165">제3자 센서</span><span class="sxs-lookup"><span data-stu-id="15fc6-165">3rd Party sensors</span></span> | <span data-ttu-id="15fc6-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="15fc6-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="15fc6-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="15fc6-168">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="15fc6-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="15fc6-170">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="15fc6-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="15fc6-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="15fc6-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="15fc6-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="15fc6-173">Office 365 ATP</span></span>  |<span data-ttu-id="15fc6-174">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="15fc6-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="15fc6-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="15fc6-176">Azure ATP</span></span>    |<span data-ttu-id="15fc6-177">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15fc6-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="15fc6-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="15fc6-178">Rebranding</span></span> |

<span data-ttu-id="15fc6-179">`DetectionSource` 는 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15fc6-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="15fc6-180">`ServiceSource` 은 [AlertEvidence](advanced-hunting-alertevidence-table.md) 및 [AlertInfo 테이블에서](advanced-hunting-alertinfo-table.md) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15fc6-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="15fc6-181">관련 항목</span><span class="sxs-lookup"><span data-stu-id="15fc6-181">Related topics</span></span>
- [<span data-ttu-id="15fc6-182">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="15fc6-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="15fc6-183">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="15fc6-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)