---
title: 클라이언트 동작 차단
description: 클라이언트 동작 차단은 끝점용 Microsoft Defender의 동작 차단 및 포함 기능의 일부입니다.
keywords: 동작 차단, 신속한 보호, 클라이언트 동작, Microsoft Defender ATP, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 48929d0e2b0c932d37cb5d29783712d00b17117f
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904155"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="bae7c-104">클라이언트 동작 차단</span><span class="sxs-lookup"><span data-stu-id="bae7c-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bae7c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bae7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="bae7c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bae7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bae7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bae7c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bae7c-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="bae7c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bae7c-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="bae7c-110">개요</span><span class="sxs-lookup"><span data-stu-id="bae7c-110">Overview</span></span>

<span data-ttu-id="bae7c-111">클라이언트 동작 차단은 끝점용 Defender의 동작 차단 및 포함 기능의 구성 요소입니다. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)</span><span class="sxs-lookup"><span data-stu-id="bae7c-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="bae7c-112">의심스러운 동작이 장치(클라이언트 또는 끝점이라고도 지칭)에서 감지되면 아티팩트(예: 파일 또는 응용 프로그램)가 자동으로 차단, 확인 및 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="클라우드 및 클라이언트 보호":::

<span data-ttu-id="bae7c-114">바이러스 백신 보호는 클라우드 보호와 함께 사용할 때 가장 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="bae7c-115">클라이언트 동작 차단의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="bae7c-115">How client behavioral blocking works</span></span>

<span data-ttu-id="bae7c-116">[Microsoft Defender 바이러스](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 백신은 장치에서 의심스러운 동작, 악성 코드, 파일 없는 및 메모리 내 공격을 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="bae7c-117">의심스러운 동작이 감지되면 Microsoft Defender 바이러스 백신은 의심스러운 동작과 프로세스 트리를 모니터링하여 클라우드 보호 서비스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="bae7c-118">기계 학습은 악성 응용 프로그램과 좋은 동작을 밀리초 내에 차별화하고 각 아티팩트를 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="bae7c-119">거의 실시간으로 아티팩트가 악성으로 발견되는 즉시 디바이스에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="bae7c-120">의심스러운 동작이 감지될 때마다 경고가 [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) 생성되고 Microsoft Defender 보안 센터()에 [https://securitycenter.windows.com](https://securitycenter.windows.com) 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="bae7c-121">클라이언트 동작 차단은 공격이 시작되지 않도록 하는 데 도움이 될 뿐만 아니라 실행을 시작한 공격을 중지하는 데 도움이 될 수 있기 때문에 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="bae7c-122">또한 [피드백](feedback-loop-blocking.md) 루프 차단(동작 차단 및 방지의 또 다른 기능)을 사용하여 조직의 다른 디바이스에서 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="bae7c-123">동작 기반 검색</span><span class="sxs-lookup"><span data-stu-id="bae7c-123">Behavior-based detections</span></span>

<span data-ttu-id="bae7c-124">동작 기반 검색은 MITRE ATT 및 엔터프라이즈용 [CK 매트릭스에&명명됩니다.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="bae7c-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="bae7c-125">이름 규칙은 악의적인 동작이 관찰된 공격 스테이지를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="bae7c-126">전술</span><span class="sxs-lookup"><span data-stu-id="bae7c-126">Tactic</span></span> |   <span data-ttu-id="bae7c-127">검색 위협 이름</span><span class="sxs-lookup"><span data-stu-id="bae7c-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="bae7c-128">초기 액세스</span><span class="sxs-lookup"><span data-stu-id="bae7c-128">Initial Access</span></span> | <span data-ttu-id="bae7c-129">동작:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="bae7c-130">실행</span><span class="sxs-lookup"><span data-stu-id="bae7c-130">Execution</span></span>  | <span data-ttu-id="bae7c-131">동작:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="bae7c-132">지속성</span><span class="sxs-lookup"><span data-stu-id="bae7c-132">Persistence</span></span>    | <span data-ttu-id="bae7c-133">동작:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="bae7c-134">권한 에스컬ation</span><span class="sxs-lookup"><span data-stu-id="bae7c-134">Privilege Escalation</span></span>   | <span data-ttu-id="bae7c-135">동작:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="bae7c-136">방어 공격</span><span class="sxs-lookup"><span data-stu-id="bae7c-136">Defense Evasion</span></span>    | <span data-ttu-id="bae7c-137">동작:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="bae7c-138">자격 증명 액세스</span><span class="sxs-lookup"><span data-stu-id="bae7c-138">Credential Access</span></span>  | <span data-ttu-id="bae7c-139">동작:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="bae7c-140">검색</span><span class="sxs-lookup"><span data-stu-id="bae7c-140">Discovery</span></span>  | <span data-ttu-id="bae7c-141">동작:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="bae7c-142">측면 이동</span><span class="sxs-lookup"><span data-stu-id="bae7c-142">Lateral Movement</span></span> | <span data-ttu-id="bae7c-143">동작:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="bae7c-144">컬렉션</span><span class="sxs-lookup"><span data-stu-id="bae7c-144">Collection</span></span> |   <span data-ttu-id="bae7c-145">동작:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="bae7c-146">명령 및 제어</span><span class="sxs-lookup"><span data-stu-id="bae7c-146">Command and Control</span></span> | <span data-ttu-id="bae7c-147">동작:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="bae7c-148">유출</span><span class="sxs-lookup"><span data-stu-id="bae7c-148">Exfiltration</span></span>   | <span data-ttu-id="bae7c-149">동작:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="bae7c-150">영향</span><span class="sxs-lookup"><span data-stu-id="bae7c-150">Impact</span></span> | <span data-ttu-id="bae7c-151">동작:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="bae7c-152">Uncategorized</span><span class="sxs-lookup"><span data-stu-id="bae7c-152">Uncategorized</span></span>  | <span data-ttu-id="bae7c-153">동작:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="bae7c-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="bae7c-154">특정 위협에 대한 자세한 내용은 최근 전역 **[위협 활동을 참조합니다.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="bae7c-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="bae7c-155">클라이언트 동작 차단 구성</span><span class="sxs-lookup"><span data-stu-id="bae7c-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="bae7c-156">조직에서 끝점에 Defender를 사용하는 경우 클라이언트 동작 차단은 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="bae7c-157">그러나 동작 차단 및 포함을 비롯한 모든 [](behavioral-blocking-containment.md)Endpoint용 Defender 기능을 사용 가능하도록 끝점용 Defender의 다음 기능을 사용하도록 설정하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7c-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="bae7c-158">끝점 기준에 대한 Defender</span><span class="sxs-lookup"><span data-stu-id="bae7c-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="bae7c-159">Endpoint용 Defender에 온보딩된 장치</span><span class="sxs-lookup"><span data-stu-id="bae7c-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="bae7c-160">차단 모드의 EDR</span><span class="sxs-lookup"><span data-stu-id="bae7c-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="bae7c-161">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="bae7c-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="bae7c-162">[차세대 보호(바이러스](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) 백신)</span><span class="sxs-lookup"><span data-stu-id="bae7c-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="bae7c-163">관련 문서</span><span class="sxs-lookup"><span data-stu-id="bae7c-163">Related articles</span></span>

- [<span data-ttu-id="bae7c-164">동작 차단 및 제약</span><span class="sxs-lookup"><span data-stu-id="bae7c-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="bae7c-165">피드백-루프 차단</span><span class="sxs-lookup"><span data-stu-id="bae7c-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="bae7c-166">(블로그) 동작 차단 및 포함: 광학을 보호로 변환</span><span class="sxs-lookup"><span data-stu-id="bae7c-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="bae7c-167">엔드포인트 리소스에 대한 유용한 Defender</span><span class="sxs-lookup"><span data-stu-id="bae7c-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
