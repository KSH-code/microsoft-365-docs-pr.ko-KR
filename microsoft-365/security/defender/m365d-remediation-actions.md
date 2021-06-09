---
title: Defender의 Microsoft 365 조치
description: Defender에서 자동화된 조사를 따르는 수정 Microsoft 365 개요를 얻습니다.
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c8d3838194c25ba49b2611dc355b21e228291b01
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842533"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="0aac0-104">Defender의 Microsoft 365 조치</span><span class="sxs-lookup"><span data-stu-id="0aac0-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0aac0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0aac0-105">**Applies to:**</span></span>
- <span data-ttu-id="0aac0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0aac0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0aac0-107">Microsoft 365 자동화된 조사가 진행되는 동안 및 이후에 악의적 또는 의심스러운 항목에 대해 수정 작업이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="0aac0-108">일부 종류의 수정 작업은 끝점이라고도 하는 장치에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="0aac0-109">기타 수정 작업은 전자 메일 콘텐츠에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="0aac0-110">재구성 작업을 수행, 승인 또는 거부한 후에 자동화된 조사가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0aac0-111">재구성 작업이 자동으로 수행될지 승인에만 수행될지는 자동화 수준과 같은 특정 설정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="0aac0-112">자세한 내용은 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="0aac0-113">Defender에서 자동화된 조사 및 대응 Microsoft 365 구성</span><span class="sxs-lookup"><span data-stu-id="0aac0-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="0aac0-114">장치에서 위협을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="0aac0-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="0aac0-115">전자 메일 및 공동 작업 콘텐츠에 & 수정 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="0aac0-116">다음 표에는 현재 Defender에서 지원되는 수정 Microsoft 365 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="0aac0-117">장치(끝점) 수정 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="0aac0-118">전자 메일 수정 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="0aac0-119">- 조사 패키지 수집</span><span class="sxs-lookup"><span data-stu-id="0aac0-119">- Collect investigation package</span></span> <br/><span data-ttu-id="0aac0-120">- 장치 격리(이 작업은 실행을 엽니다.)</span><span class="sxs-lookup"><span data-stu-id="0aac0-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="0aac0-121">- 컴퓨터 오프보드</span><span class="sxs-lookup"><span data-stu-id="0aac0-121">- Offboard machine</span></span> <br/><span data-ttu-id="0aac0-122">- 릴리스 코드 실행</span><span class="sxs-lookup"><span data-stu-id="0aac0-122">- Release code execution</span></span> <br/><span data-ttu-id="0aac0-123">- 릴리스</span><span class="sxs-lookup"><span data-stu-id="0aac0-123">- Release from quarantine</span></span> <br/><span data-ttu-id="0aac0-124">- 샘플 요청</span><span class="sxs-lookup"><span data-stu-id="0aac0-124">- Request sample</span></span> <br/><span data-ttu-id="0aac0-125">- 코드 실행 제한(이 작업은 실행을 실행 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="0aac0-126">- 바이러스 백신 검사 실행</span><span class="sxs-lookup"><span data-stu-id="0aac0-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="0aac0-127">- 중지 및 검사</span><span class="sxs-lookup"><span data-stu-id="0aac0-127">- Stop and quarantine</span></span>      |<span data-ttu-id="0aac0-128">- 차단 URL(클릭 시간)</span><span class="sxs-lookup"><span data-stu-id="0aac0-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="0aac0-129">- 전자 메일 메시지 또는 클러스터를 소프트 삭제</span><span class="sxs-lookup"><span data-stu-id="0aac0-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="0aac0-130">- 전자 메일 검지</span><span class="sxs-lookup"><span data-stu-id="0aac0-130">- Quarantine email</span></span><br/><span data-ttu-id="0aac0-131">- 전자 메일 첨부 파일 Quarantine</span><span class="sxs-lookup"><span data-stu-id="0aac0-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="0aac0-132">- 외부 메일 전달 끄기</span><span class="sxs-lookup"><span data-stu-id="0aac0-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="0aac0-133">승인 보류 중이든 이미 완료 상태든 재구성 작업은 관리 센터 에서 볼 [수 있습니다.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="0aac0-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="0aac0-134">자동화된 조사를 따르는 수정 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="0aac0-135">자동화된 조사가 완료되면 관련된 모든 증거에 대한 판결에 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="0aac0-136">판정에 따라 수정 작업이 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="0aac0-137">경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="0aac0-138">자동화된 조사 및 응답이 구성된 방식에 [따라 모두 에 따라 다를 수 있습니다.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="0aac0-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="0aac0-139">도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="0aac0-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="0aac0-140">의견</span><span class="sxs-lookup"><span data-stu-id="0aac0-140">Verdict</span></span>    | <span data-ttu-id="0aac0-141">영향을 받는 엔터티</span><span class="sxs-lookup"><span data-stu-id="0aac0-141">Affected entities</span></span>    | <span data-ttu-id="0aac0-142">결과</span><span class="sxs-lookup"><span data-stu-id="0aac0-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="0aac0-143">악성</span><span class="sxs-lookup"><span data-stu-id="0aac0-143">Malicious</span></span>    | <span data-ttu-id="0aac0-144">장치 (끝점)</span><span class="sxs-lookup"><span data-stu-id="0aac0-144">Devices (endpoints)</span></span>    | <span data-ttu-id="0aac0-145">재구성 작업이 자동으로 수행됩니다(조직의 장치 그룹이 전체 - 자동으로 위협 수정으로 설정되어 있는 **경우)** [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="0aac0-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="0aac0-146">악성</span><span class="sxs-lookup"><span data-stu-id="0aac0-146">Malicious</span></span>    | <span data-ttu-id="0aac0-147">전자 메일 콘텐츠 (Url 또는 첨부 파일)</span><span class="sxs-lookup"><span data-stu-id="0aac0-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="0aac0-148">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="0aac0-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="0aac0-149">피싱</span><span class="sxs-lookup"><span data-stu-id="0aac0-149">Suspicious</span></span>    | <span data-ttu-id="0aac0-150">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="0aac0-150">Devices or email content</span></span> | <span data-ttu-id="0aac0-151">승인 보류 중인 재구성 활동 </span><span class="sxs-lookup"><span data-stu-id="0aac0-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="0aac0-152">위협을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="0aac0-152">No threats found</span></span>    | <span data-ttu-id="0aac0-153">장치 또는 전자 메일 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="0aac0-153">Devices or email content</span></span>    | <span data-ttu-id="0aac0-154">재구성 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="0aac0-155">수동으로 수행한 수정 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="0aac0-156">자동화된 조사를 따르는 수정 작업 외에도 보안 운영 팀은 특정 수정 작업을 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="0aac0-157">이러한 경계 및 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0aac0-157">These include the following:</span></span>

- <span data-ttu-id="0aac0-158">장치 고리 또는 파일 검지와 같은 수동 장치 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="0aac0-159">수동 전자 메일 작업(예: 전자 메일 메시지 소프트 삭제)</span><span class="sxs-lookup"><span data-stu-id="0aac0-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="0aac0-160">[장치 또는 전자](../defender-endpoint/advanced-hunting-overview.md) 메일에 대한 고급 헌팅 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="0aac0-161">[전자](../office-365-security/threat-explorer.md) 메일 콘텐츠에 대한 탐색기 작업(예: 정크 메일로 이동, 전자 메일 소프트 삭제 또는 하드 삭제 전자 메일)</span><span class="sxs-lookup"><span data-stu-id="0aac0-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="0aac0-162">파일 [삭제,](/windows/security/threat-protection/microsoft-defender-atp/live-response) 프로세스 중지, 예약된 작업 제거와 같은 수동 실시간 응답 작업</span><span class="sxs-lookup"><span data-stu-id="0aac0-162">Manual [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="0aac0-163">[Microsoft Defender for Endpoint API를](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)사용하여 실시간 응답 작업(예: 장치 차단, 바이러스 백신 검사 실행, 파일에 대한 정보 수집)</span><span class="sxs-lookup"><span data-stu-id="0aac0-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="0aac0-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0aac0-164">Next steps</span></span>

- [<span data-ttu-id="0aac0-165">알림 센터 방문</span><span class="sxs-lookup"><span data-stu-id="0aac0-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="0aac0-166">수정 작업 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="0aac0-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="0aac0-167">가짓 긍정 또는 거짓 부정 해결</span><span class="sxs-lookup"><span data-stu-id="0aac0-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
