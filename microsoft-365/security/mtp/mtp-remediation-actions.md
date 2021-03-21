---
title: Microsoft 365 Defender의 수정 작업
description: Microsoft 365 Defender에서 자동화된 조사를 따르는 수정 작업의 개요를 얻습니다.
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: m365-security
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
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928631"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="78f59-104">Microsoft 365 Defender의 수정 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="78f59-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="78f59-105">**Applies to:**</span></span>
- <span data-ttu-id="78f59-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78f59-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="78f59-107">수정 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-107">Remediation actions</span></span>

<span data-ttu-id="78f59-108">Microsoft 365 Defender에서 자동화된 조사가 진행되는 동안 및 이후에 악의적 또는 의심스러운 항목에 대한 수정 작업이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="78f59-109">일부 종류의 수정 작업은 끝점이라고도 하는 장치에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="78f59-110">기타 수정 작업은 전자 메일 콘텐츠에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="78f59-111">재구성 작업을 수행, 승인 또는 거부한 후에 자동화된 조사가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78f59-112">재구성 작업이 자동으로 수행될지 승인에만 수행될지는 자동화 수준과 같은 특정 설정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="78f59-113">자세한 내용은 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="78f59-114">Microsoft 365 Defender에서 자동화된 조사 및 응답 기능 구성</span><span class="sxs-lookup"><span data-stu-id="78f59-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="78f59-115">장치에서 위협을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="78f59-115">How threats are remediated on devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="78f59-116">전자 메일 및 공동 작업 콘텐츠에 & 수정 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="78f59-117">다음 표에는 Microsoft 365 Defender에서 현재 지원되는 수정 작업이 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="78f59-118">장치(끝점) 수정 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="78f59-119">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="78f59-120">- 조사 패키지 수집</span><span class="sxs-lookup"><span data-stu-id="78f59-120">- Collect investigation package</span></span> <br/><span data-ttu-id="78f59-121">- 장치 격리(이 작업은 실행을 엽니다.)</span><span class="sxs-lookup"><span data-stu-id="78f59-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="78f59-122">- 컴퓨터 오프보드</span><span class="sxs-lookup"><span data-stu-id="78f59-122">- Offboard machine</span></span> <br/><span data-ttu-id="78f59-123">- 릴리스 코드 실행</span><span class="sxs-lookup"><span data-stu-id="78f59-123">- Release code execution</span></span> <br/><span data-ttu-id="78f59-124">- 릴리스</span><span class="sxs-lookup"><span data-stu-id="78f59-124">- Release from quarantine</span></span> <br/><span data-ttu-id="78f59-125">- 샘플 요청</span><span class="sxs-lookup"><span data-stu-id="78f59-125">- Request sample</span></span> <br/><span data-ttu-id="78f59-126">- 코드 실행 제한(이 작업은 실행을 실행 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="78f59-127">- 바이러스 백신 검사 실행</span><span class="sxs-lookup"><span data-stu-id="78f59-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="78f59-128">- 중지 및 검사</span><span class="sxs-lookup"><span data-stu-id="78f59-128">- Stop and quarantine</span></span>      |<span data-ttu-id="78f59-129">- 차단 URL(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="78f59-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="78f59-130">- 전자 메일 메시지 또는 클러스터를 소프트 삭제</span><span class="sxs-lookup"><span data-stu-id="78f59-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="78f59-131">- 전자 메일 검지</span><span class="sxs-lookup"><span data-stu-id="78f59-131">- Quarantine email</span></span><br/><span data-ttu-id="78f59-132">- 전자 메일 첨부 파일 Quarantine</span><span class="sxs-lookup"><span data-stu-id="78f59-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="78f59-133">- 외부 메일 전달 끄기</span><span class="sxs-lookup"><span data-stu-id="78f59-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="78f59-134">승인 보류 중이든 이미 완료 상태이든 재구성 작업은 관리 센터에서 볼 [수 있습니다.](./mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="78f59-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](./mtp-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="78f59-135">자동화된 조사를 따르는 수정 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="78f59-136">자동화된 조사가 완료되면 관련된 모든 증거에 대한 판결에 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="78f59-137">판정에 따라 수정 작업이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="78f59-138">경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="78f59-139">자동화된 조사 및 응답이 구성된 방식에 [따라 모두 에 따라 다를 수 있습니다.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="78f59-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="78f59-140">도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="78f59-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="78f59-141">의견</span><span class="sxs-lookup"><span data-stu-id="78f59-141">Verdict</span></span>    | <span data-ttu-id="78f59-142">영역</span><span class="sxs-lookup"><span data-stu-id="78f59-142">Area</span></span>    | <span data-ttu-id="78f59-143">결과</span><span class="sxs-lookup"><span data-stu-id="78f59-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="78f59-144">악성</span><span class="sxs-lookup"><span data-stu-id="78f59-144">Malicious</span></span>    | <span data-ttu-id="78f59-145">장치 (끝점)</span><span class="sxs-lookup"><span data-stu-id="78f59-145">Devices (endpoints)</span></span>    | <span data-ttu-id="78f59-146">재구성 작업이 자동으로 수행됩니다(조직의 장치 그룹이 전체 - 자동으로 위협 수정으로 설정되어 있는 **경우)** [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="78f59-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="78f59-147">악성</span><span class="sxs-lookup"><span data-stu-id="78f59-147">Malicious</span></span>    | <span data-ttu-id="78f59-148">전자 메일 콘텐츠 (Url 또는 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="78f59-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="78f59-149">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="78f59-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="78f59-150">피싱</span><span class="sxs-lookup"><span data-stu-id="78f59-150">Suspicious</span></span>    | <span data-ttu-id="78f59-151">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="78f59-151">Devices or email content</span></span> | <span data-ttu-id="78f59-152">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="78f59-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="78f59-153">위협을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="78f59-153">No threats found</span></span>    | <span data-ttu-id="78f59-154">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="78f59-154">Devices or email content</span></span>    | <span data-ttu-id="78f59-155">재구성 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="78f59-156">수동으로 수행한 수정 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="78f59-157">자동화된 조사를 따르는 수정 작업 외에도 보안 운영 팀은 특정 수정 작업을 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="78f59-158">여기에는 다음 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f59-158">These include the following actions:</span></span>

- <span data-ttu-id="78f59-159">장치 고리 또는 파일 검지와 같은 수동 장치 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="78f59-160">수동 전자 메일 작업(예: 전자 메일 메시지 소프트 삭제)</span><span class="sxs-lookup"><span data-stu-id="78f59-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="78f59-161">[장치 또는 전자](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) 메일에 대한 고급 헌팅 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-161">[Advanced hunting](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="78f59-162">[전자](../office-365-security/threat-explorer.md) 메일을 정크 메일로 이동, 소프트 삭제 전자 메일 또는 하드 삭제 전자 메일과 같은 전자 메일 콘텐츠에 대한 탐색기 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="78f59-163">파일 [삭제,](/windows/security/threat-protection/microsoft-defender-atp/live-response) 프로세스 중지, 예약된 작업 제거와 같은 수동 실시간 응답 작업</span><span class="sxs-lookup"><span data-stu-id="78f59-163">Manual [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="78f59-164">[Microsoft Defender for Endpoint API를](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)사용하여 실시간 응답 작업(예: 장치 차단, 바이러스 백신 검사 실행, 파일에 대한 정보 수집)</span><span class="sxs-lookup"><span data-stu-id="78f59-164">Live response action with [Microsoft Defender for Endpoint APIs](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="78f59-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="78f59-165">Next steps</span></span>

- [<span data-ttu-id="78f59-166">알림 센터 방문</span><span class="sxs-lookup"><span data-stu-id="78f59-166">Visit the Action center</span></span>](./mtp-action-center.md)
- [<span data-ttu-id="78f59-167">수정 작업 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="78f59-167">View and manage remediation actions</span></span>](./mtp-autoir-actions.md)
- [<span data-ttu-id="78f59-168">자동화된 조사 및 응답 기능에서 가짓 긍정/부정 처리</span><span class="sxs-lookup"><span data-stu-id="78f59-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)