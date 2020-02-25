---
title: Microsoft Threat Protection의 자동화 된 조사에 따라 수정 작업 수행
description: Microsoft Threat Protection의 자동화 된 조사를 따르는 업데이트 관리 작업에 대 한 개요를 확인 하세요.
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266054"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="5b740-104">Microsoft Threat Protection의 자동화 된 조사에 따라 수정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="5b740-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="5b740-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5b740-105">**Applies to:**</span></span>
- <span data-ttu-id="5b740-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="5b740-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="5b740-107">수정 작업</span><span class="sxs-lookup"><span data-stu-id="5b740-107">Remediation actions</span></span>

<span data-ttu-id="5b740-108">Microsoft Threat Protection에 대 한 자동화 된 조사 중 및 후에는 악성 또는 의심 스러운 항목에 대 한 재구성 작업이 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="5b740-109">일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="5b740-110">전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="5b740-111">자동화 된 조사 작업을 수행, 승인 또는 거부 한 후에 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="5b740-112">다음 표에서는 현재 Microsoft Threat Protection에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="5b740-113">장치 (끝점) 재구성 작업</span><span class="sxs-lookup"><span data-stu-id="5b740-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="5b740-114">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="5b740-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="5b740-115">파일 격리</span><span class="sxs-lookup"><span data-stu-id="5b740-115">Quarantine file</span></span><br/><span data-ttu-id="5b740-116">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="5b740-116">Remove registry key</span></span><br/><span data-ttu-id="5b740-117">프로세스 중단</span><span class="sxs-lookup"><span data-stu-id="5b740-117">Kill process</span></span> <br/><span data-ttu-id="5b740-118">서비스 중지</span><span class="sxs-lookup"><span data-stu-id="5b740-118">Stop service</span></span> <br/><span data-ttu-id="5b740-119">드라이버 해제</span><span class="sxs-lookup"><span data-stu-id="5b740-119">Disable driver</span></span> <br/><span data-ttu-id="5b740-120">예약된 작업 제거</span><span class="sxs-lookup"><span data-stu-id="5b740-120">Remove scheduled task</span></span>      |<span data-ttu-id="5b740-121">전자 메일 메시지 또는 클러스터의 일시 삭제</span><span class="sxs-lookup"><span data-stu-id="5b740-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="5b740-122">차단 URL(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="5b740-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="5b740-123">외부 메일 전달 해제</span><span class="sxs-lookup"><span data-stu-id="5b740-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="5b740-124">승인 보류 중 이거나 이미 완료 되었는지 여부에 관계 없이 수정 작업은 [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="5b740-125">자동화 된 조사 후 Verdicts 및 결과</span><span class="sxs-lookup"><span data-stu-id="5b740-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="5b740-126">자동화 조사가 완료 되면 관련된 모든 증명정보에 따라 결과가 도출되고 재구성 작업이 식별됩니다.  </span><span class="sxs-lookup"><span data-stu-id="5b740-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="5b740-127">경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="5b740-128">도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="5b740-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="5b740-129">의견</span><span class="sxs-lookup"><span data-stu-id="5b740-129">Verdict</span></span>    |<span data-ttu-id="5b740-130">영역</span><span class="sxs-lookup"><span data-stu-id="5b740-130">Area</span></span>   |<span data-ttu-id="5b740-131">결과</span><span class="sxs-lookup"><span data-stu-id="5b740-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="5b740-132">악성</span><span class="sxs-lookup"><span data-stu-id="5b740-132">Malicious</span></span>  |<span data-ttu-id="5b740-133">장치 (끝점)</span><span class="sxs-lookup"><span data-stu-id="5b740-133">Devices (endpoints)</span></span>    |<span data-ttu-id="5b740-134">재구성 작업이 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="5b740-135">악성</span><span class="sxs-lookup"><span data-stu-id="5b740-135">Malicious</span></span>  |<span data-ttu-id="5b740-136">전자 메일 콘텐츠 (Url 또는 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="5b740-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="5b740-137">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="5b740-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="5b740-138">피싱</span><span class="sxs-lookup"><span data-stu-id="5b740-138">Suspicious</span></span> |<span data-ttu-id="5b740-139">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="5b740-139">Devices or email content</span></span> |<span data-ttu-id="5b740-140">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="5b740-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="5b740-141">정리</span><span class="sxs-lookup"><span data-stu-id="5b740-141">Clean</span></span>  |<span data-ttu-id="5b740-142">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="5b740-142">Devices or email content</span></span>   |<span data-ttu-id="5b740-143">재구성 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="5b740-144">활동 센터에서 대기 중인 작업 검토</span><span class="sxs-lookup"><span data-stu-id="5b740-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="5b740-145">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="5b740-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="5b740-146">가양성 [/네거티브를 보고](mtp-autoir-report-false-positives-negatives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b740-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b740-147">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5b740-147">Next steps</span></span>

- [<span data-ttu-id="5b740-148">작업 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="5b740-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="5b740-149">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="5b740-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
