---
title: Microsoft 365 Defender의 자동화 된 조사에 따라 수정 작업 수행
description: Microsoft 365 Defender의 자동화 된 조사를 따르는 업데이트 관리 작업에 대 한 개요를 확인 하세요.
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 71cdf2d1b9a40e9cfbf487ca8596a0c2b09475d1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847215"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-365-defender"></a><span data-ttu-id="8ef6f-104">Microsoft 365 Defender의 자동화 된 조사에 따라 수정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="8ef6f-104">Remediation actions following automated investigations in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8ef6f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8ef6f-105">**Applies to:**</span></span>
- <span data-ttu-id="8ef6f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ef6f-106">Microsoft 365 Defender</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="8ef6f-107">수정 작업</span><span class="sxs-lookup"><span data-stu-id="8ef6f-107">Remediation actions</span></span>

<span data-ttu-id="8ef6f-108">Microsoft 365 Defender에 대 한 자동화 된 조사 중 및 후에는 악성 또는 의심 스러운 항목에 대 한 재구성 작업이 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="8ef6f-109">일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="8ef6f-110">전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="8ef6f-111">자동화 된 조사 작업을 수행, 승인 또는 거부 한 후에 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="8ef6f-112">다음 표에서는 현재 Microsoft 365 Defender에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-112">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="8ef6f-113">장치 (끝점) 재구성 작업</span><span class="sxs-lookup"><span data-stu-id="8ef6f-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="8ef6f-114">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="8ef6f-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="8ef6f-115">-수집 조사 패키지</span><span class="sxs-lookup"><span data-stu-id="8ef6f-115">- Collect investigation package</span></span> <br/><span data-ttu-id="8ef6f-116">-장치 격리 (이 작업을 실행 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8ef6f-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="8ef6f-117">-Offboard 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="8ef6f-117">- Offboard machine</span></span> <br/><span data-ttu-id="8ef6f-118">-릴리스 코드 실행</span><span class="sxs-lookup"><span data-stu-id="8ef6f-118">- Release code execution</span></span> <br/><span data-ttu-id="8ef6f-119">-격리에서 릴리스</span><span class="sxs-lookup"><span data-stu-id="8ef6f-119">- Release from quarantine</span></span> <br/><span data-ttu-id="8ef6f-120">-요청 샘플</span><span class="sxs-lookup"><span data-stu-id="8ef6f-120">- Request sample</span></span> <br/><span data-ttu-id="8ef6f-121">-코드 실행 제한 (이 작업을 실행 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8ef6f-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="8ef6f-122">-바이러스 검사 실행</span><span class="sxs-lookup"><span data-stu-id="8ef6f-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="8ef6f-123">-중지 및 격리</span><span class="sxs-lookup"><span data-stu-id="8ef6f-123">- Stop and quarantine</span></span>      |<span data-ttu-id="8ef6f-124">-블록 URL (시간 클릭)</span><span class="sxs-lookup"><span data-stu-id="8ef6f-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="8ef6f-125">-소프트 삭제 전자 메일 메시지 또는 클러스터</span><span class="sxs-lookup"><span data-stu-id="8ef6f-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="8ef6f-126">-격리 전자 메일</span><span class="sxs-lookup"><span data-stu-id="8ef6f-126">- Quarantine email</span></span><br/><span data-ttu-id="8ef6f-127">-전자 메일 첨부 파일 격리</span><span class="sxs-lookup"><span data-stu-id="8ef6f-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="8ef6f-128">-외부 메일 전달을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="8ef6f-129">보류 중인 승인 또는 이미 완료 되었는지 여부에 관계 없이 관리 작업 [센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="8ef6f-130">재구성 작업의 자동화 된 조사 진행</span><span class="sxs-lookup"><span data-stu-id="8ef6f-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="8ef6f-131">자동 조사가 완료 되 면 관련 된 모든 증거 부분에 대 한 결과에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="8ef6f-132">결과에 따라 재구성 작업이 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="8ef6f-133">경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="8ef6f-134">이 모든 [기능은 자동화 된 조사 및 응답이 구성 되](mtp-configure-auto-investigation-response.md)는 방식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="8ef6f-135">도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="8ef6f-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="8ef6f-136">의견</span><span class="sxs-lookup"><span data-stu-id="8ef6f-136">Verdict</span></span>    |<span data-ttu-id="8ef6f-137">영역</span><span class="sxs-lookup"><span data-stu-id="8ef6f-137">Area</span></span>    |<span data-ttu-id="8ef6f-138">결과</span><span class="sxs-lookup"><span data-stu-id="8ef6f-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="8ef6f-139">악성</span><span class="sxs-lookup"><span data-stu-id="8ef6f-139">Malicious</span></span>    |<span data-ttu-id="8ef6f-140">장치 (끝점)</span><span class="sxs-lookup"><span data-stu-id="8ef6f-140">Devices (endpoints)</span></span>    |<span data-ttu-id="8ef6f-141">관리 작업이 자동으로 수행 됩니다 (조직의 [장치 그룹이](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) **전체 치료 위협으로 자동으로** 설정 된 경우).</span><span class="sxs-lookup"><span data-stu-id="8ef6f-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically** )</span></span>|
|<span data-ttu-id="8ef6f-142">악성</span><span class="sxs-lookup"><span data-stu-id="8ef6f-142">Malicious</span></span>    |<span data-ttu-id="8ef6f-143">전자 메일 콘텐츠 (Url 또는 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="8ef6f-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="8ef6f-144">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="8ef6f-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8ef6f-145">피싱</span><span class="sxs-lookup"><span data-stu-id="8ef6f-145">Suspicious</span></span>    |<span data-ttu-id="8ef6f-146">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8ef6f-146">Devices or email content</span></span> |<span data-ttu-id="8ef6f-147">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="8ef6f-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8ef6f-148">발견 된 위협 없음</span><span class="sxs-lookup"><span data-stu-id="8ef6f-148">No threats found</span></span>    |<span data-ttu-id="8ef6f-149">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="8ef6f-149">Devices or email content</span></span>    |<span data-ttu-id="8ef6f-150">재구성 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="8ef6f-151">재구성 작업이 자동으로 수행 되는지, 승인 된 경우에만 조직의 장치 그룹 정책 등의 특정 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="8ef6f-152">자세한 내용은 다음 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ef6f-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="8ef6f-153">Microsoft 365 Defender에서 자동화 된 조사 및 응답 기능 구성</span><span class="sxs-lookup"><span data-stu-id="8ef6f-153">Configure automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="8ef6f-154">장치에서 위협이 재구성 되는 방식</span><span class="sxs-lookup"><span data-stu-id="8ef6f-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="8ef6f-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8ef6f-155">Next steps</span></span>

- [<span data-ttu-id="8ef6f-156">알림 센터 방문</span><span class="sxs-lookup"><span data-stu-id="8ef6f-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="8ef6f-157">보류 중인 작업 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="8ef6f-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="8ef6f-158">자동화 된 조사 및 응답 기능에서 가양성/네거티브 처리</span><span class="sxs-lookup"><span data-stu-id="8ef6f-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
