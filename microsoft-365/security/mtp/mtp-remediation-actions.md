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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502940"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="6f92b-104">Microsoft Threat Protection의 자동화 된 조사에 따라 수정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="6f92b-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="6f92b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6f92b-105">**Applies to:**</span></span>
- <span data-ttu-id="6f92b-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="6f92b-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="6f92b-107">수정 작업</span><span class="sxs-lookup"><span data-stu-id="6f92b-107">Remediation actions</span></span>

<span data-ttu-id="6f92b-108">Microsoft Threat Protection에 대 한 자동화 된 조사 중 및 후에는 악성 또는 의심 스러운 항목에 대 한 재구성 작업이 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="6f92b-109">일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="6f92b-110">전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="6f92b-111">자동화 된 조사 작업을 수행, 승인 또는 거부 한 후에 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="6f92b-112">다음 표에서는 현재 Microsoft Threat Protection에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="6f92b-113">장치 (끝점) 재구성 작업</span><span class="sxs-lookup"><span data-stu-id="6f92b-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="6f92b-114">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="6f92b-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="6f92b-115">-수집 조사 패키지</span><span class="sxs-lookup"><span data-stu-id="6f92b-115">- Collect investigation package</span></span> <br/><span data-ttu-id="6f92b-116">-장치 격리 (이 작업을 실행 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="6f92b-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="6f92b-117">-Offboard 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="6f92b-117">- Offboard machine</span></span> <br/><span data-ttu-id="6f92b-118">-릴리스 코드 실행</span><span class="sxs-lookup"><span data-stu-id="6f92b-118">- Release code execution</span></span> <br/><span data-ttu-id="6f92b-119">-격리에서 릴리스</span><span class="sxs-lookup"><span data-stu-id="6f92b-119">- Release from quarantine</span></span> <br/><span data-ttu-id="6f92b-120">-요청 샘플</span><span class="sxs-lookup"><span data-stu-id="6f92b-120">- Request sample</span></span> <br/><span data-ttu-id="6f92b-121">-코드 실행 제한 (이 작업을 실행 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="6f92b-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="6f92b-122">-바이러스 검사 실행</span><span class="sxs-lookup"><span data-stu-id="6f92b-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="6f92b-123">-중지 및 격리</span><span class="sxs-lookup"><span data-stu-id="6f92b-123">- Stop and quarantine</span></span>      |<span data-ttu-id="6f92b-124">-블록 URL (시간 클릭)</span><span class="sxs-lookup"><span data-stu-id="6f92b-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="6f92b-125">-소프트 삭제 전자 메일 메시지 또는 클러스터</span><span class="sxs-lookup"><span data-stu-id="6f92b-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="6f92b-126">-격리 전자 메일</span><span class="sxs-lookup"><span data-stu-id="6f92b-126">- Quarantine email</span></span><br/><span data-ttu-id="6f92b-127">-전자 메일 첨부 파일 격리</span><span class="sxs-lookup"><span data-stu-id="6f92b-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="6f92b-128">-외부 메일 전달을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="6f92b-129">승인 보류 중 이거나 이미 완료 되었는지 여부에 관계 없이 수정 작업은 [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="6f92b-130">재구성 작업의 자동화 된 조사 진행</span><span class="sxs-lookup"><span data-stu-id="6f92b-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="6f92b-131">자동화 조사가 완료 되면 관련된 모든 증명정보에 따라 결과가 도출되고 재구성 작업이 식별됩니다.  </span><span class="sxs-lookup"><span data-stu-id="6f92b-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="6f92b-132">경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="6f92b-133">도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="6f92b-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="6f92b-134">의견</span><span class="sxs-lookup"><span data-stu-id="6f92b-134">Verdict</span></span>    |<span data-ttu-id="6f92b-135">영역</span><span class="sxs-lookup"><span data-stu-id="6f92b-135">Area</span></span>    |<span data-ttu-id="6f92b-136">결과</span><span class="sxs-lookup"><span data-stu-id="6f92b-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="6f92b-137">악성</span><span class="sxs-lookup"><span data-stu-id="6f92b-137">Malicious</span></span>    |<span data-ttu-id="6f92b-138">장치 (끝점)</span><span class="sxs-lookup"><span data-stu-id="6f92b-138">Devices (endpoints)</span></span>    |<span data-ttu-id="6f92b-139">재구성 작업이 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="6f92b-140">악성</span><span class="sxs-lookup"><span data-stu-id="6f92b-140">Malicious</span></span>    |<span data-ttu-id="6f92b-141">전자 메일 콘텐츠 (Url 또는 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="6f92b-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="6f92b-142">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="6f92b-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="6f92b-143">피싱</span><span class="sxs-lookup"><span data-stu-id="6f92b-143">Suspicious</span></span>    |<span data-ttu-id="6f92b-144">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6f92b-144">Devices or email content</span></span> |<span data-ttu-id="6f92b-145">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="6f92b-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="6f92b-146">발견 된 위협 없음</span><span class="sxs-lookup"><span data-stu-id="6f92b-146">No threats found</span></span>    |<span data-ttu-id="6f92b-147">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="6f92b-147">Devices or email content</span></span>    |<span data-ttu-id="6f92b-148">재구성 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="6f92b-149">활동 센터에서 대기 중인 작업 검토</span><span class="sxs-lookup"><span data-stu-id="6f92b-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="6f92b-150">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="6f92b-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="6f92b-151">가양성 [/네거티브를 보고](mtp-autoir-report-false-positives-negatives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f92b-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f92b-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6f92b-152">Next steps</span></span>

- [<span data-ttu-id="6f92b-153">작업 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="6f92b-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="6f92b-154">알림 센터에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="6f92b-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
