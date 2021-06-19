---
title: 동작 차단 및 제약
description: 끝점용 Microsoft Defender의 동작 차단 및 포함 기능에 대해 자세히 알아보기
keywords: 끝점용 Microsoft Defender, EDR 모드, 수동 모드 차단
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
ms.openlocfilehash: c480bb83465e6057cd1cf29f1f5077f2a0e165e8
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028826"
---
# <a name="behavioral-blocking-and-containment"></a><span data-ttu-id="192fe-104">동작 차단 및 제약</span><span class="sxs-lookup"><span data-stu-id="192fe-104">Behavioral blocking and containment</span></span>

<span data-ttu-id="192fe-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="192fe-105">**Applies to:**</span></span>
- [<span data-ttu-id="192fe-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="192fe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="192fe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="192fe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="192fe-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="192fe-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="192fe-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="192fe-110">개요</span><span class="sxs-lookup"><span data-stu-id="192fe-110">Overview</span></span>

<span data-ttu-id="192fe-111">오늘날의 위협 환경은 파일 [](/windows/security/threat-protection/intelligence/fileless-threats) 없는 맬웨어로 오버런되고, 기존의 솔루션보다 빠르게 변이되는 매우 다형성 위협과 손상된 디바이스에서 적들이 발견하는 공격에 적응하는 인간이 운영하는 공격에 의해 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-111">Today’s threat landscape is overrun by [fileless malware](/windows/security/threat-protection/intelligence/fileless-threats) and that lives off the land, highly polymorphic threats that mutate faster than traditional solutions can keep up with, and human-operated attacks that adapt to what adversaries find on compromised devices.</span></span> <span data-ttu-id="192fe-112">기존 보안 솔루션만으로는 이러한 공격을 막을 수 없습니다. 엔드포인트용 [Defender에](/windows/security)포함된 인공 지능(AI) 및 ML(장치 학습) 지원 기능(예: 동작 차단 및 포함)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-112">Traditional security solutions are not sufficient to stop such attacks; you need artificial intelligence (AI) and device learning (ML) backed capabilities, such as behavioral blocking and containment, included in [Defender for Endpoint](/windows/security).</span></span> 

<span data-ttu-id="192fe-113">동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리에 따라 위협을 식별하고 중지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-113">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> <span data-ttu-id="192fe-114">엔드포인트 구성 요소 및 기능에 대한 차세대 보호, EDR 및 Defender는 동작 차단 및 포함 기능에서 함께 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-114">Next-generation protection, EDR, and Defender for Endpoint components and features work together in behavioral blocking and containment capabilities.</span></span> 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="동작 차단 및 제약":::

<span data-ttu-id="192fe-116">동작 차단 및 포함 기능은 끝점용 Defender의 여러 구성 요소 및 기능과 함께 작동하여 공격을 즉시 중지하고 공격이 진행되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-116">Behavioral blocking and containment capabilities work with multiple components and features of Defender for Endpoint to stop attacks immediately and prevent attacks from progressing.</span></span>

- <span data-ttu-id="192fe-117">[차세대 보호(Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md) 포함)는 동작을 분석하여 위협을 감지하고 실행을 시작한 위협을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-117">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md) (which includes Microsoft Defender Antivirus) can detect threats by analyzing behaviors, and stop threats that have started running.</span></span>

- <span data-ttu-id="192fe-118">[끝점 감지](overview-endpoint-detection-response.md) 및 응답(EDR)은 네트워크, 장치 및 커널 동작을 통해 보안 신호를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-118">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) receives security signals across your network, devices, and kernel behavior.</span></span> <span data-ttu-id="192fe-119">위협이 감지되면 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-119">As threats are detected, alerts are created.</span></span> <span data-ttu-id="192fe-120">동일한 유형의 여러 경고가 인시던트로 집계됩니다. 따라서 보안 운영 팀이 보다 쉽게 조사하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-120">Multiple alerts of the same type are aggregated into incidents, which makes it easier for your security operations team to investigate and respond.</span></span>

- <span data-ttu-id="192fe-121">[끝점용 Defender에는](overview-endpoint-detection-response.md) 네트워크, 끝점 및 커널 동작을 통해 수신된 네트워크, 끝점 및 커널 동작 신호 외에도 ID, 전자 메일, 데이터 및 앱에 걸쳐 광범위한 광학 EDR.</span><span class="sxs-lookup"><span data-stu-id="192fe-121">[Defender for Endpoint](overview-endpoint-detection-response.md) has a wide range of optics across identities, email, data, and apps, in addition to the network, endpoint, and kernel behavior signals received through EDR.</span></span> <span data-ttu-id="192fe-122">의 [](../defender/microsoft-365-defender.md)구성 Microsoft 365 Defender 끝점용 Defender는 이러한 신호를 처리하고, 검색 경고를 발생시킵니다. 인시던트에서 관련 경고를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-122">A component of [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender for Endpoint processes and correlates these signals, raises detection alerts, and connects related alerts in incidents.</span></span>

<span data-ttu-id="192fe-123">이러한 기능을 사용하여 실행을 시작한 경우에도 더 많은 위협을 방지하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-123">With these capabilities, more threats can be prevented or blocked, even if they start running.</span></span> <span data-ttu-id="192fe-124">의심스러운 동작이 감지될 때마다 위협이 포함되어 경고가 생성되고 추적에서 위협이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-124">Whenever suspicious behavior is detected, the threat is contained, alerts are created, and threats are stopped in their tracks.</span></span> 

<span data-ttu-id="192fe-125">다음 이미지는 동작 차단 및 포함 기능에 의해 트리거된 경고의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-125">The following image shows an example of an alert that was triggered by behavioral blocking and containment capabilities:</span></span>

:::image type="content" source="images/blocked-behav-alert.png" alt-text="동작 차단 및 포함을 통한 경고의 예":::

## <a name="components-of-behavioral-blocking-and-containment"></a><span data-ttu-id="192fe-127">동작 차단 및 포함의 구성 요소</span><span class="sxs-lookup"><span data-stu-id="192fe-127">Components of behavioral blocking and containment</span></span>

- <span data-ttu-id="192fe-128">**클라이언트에서 정책 기반 공격 [표면 감소 규칙](attack-surface-reduction.md)** 미리 정의한 일반적인 공격 동작은 공격 표면 감소 규칙에 따라 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-128">**On-client, policy-driven [attack surface reduction rules](attack-surface-reduction.md)** Predefined common attack behaviors are prevented from executing, according to your attack surface reduction rules.</span></span> <span data-ttu-id="192fe-129">이러한 동작이 실행을 시도하면 정보 알림으로 Microsoft 365 Defender( [https://security.microsoft.com](https://security.microsoft.com) )에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-129">When such behaviors attempt to execute, they can be seen in Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) as informational alerts.</span></span> <span data-ttu-id="192fe-130">공격 표면 감소 규칙은 기본적으로 사용하도록 설정되지 않습니다. 에서 정책을 구성할 [Microsoft 365 Defender.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="192fe-130">Attack surface reduction rules are not enabled by default; you configure your policies in the [Microsoft 365 Defender](microsoft-defender-security-center.md).</span></span>

- <span data-ttu-id="192fe-131">**[클라이언트 동작 차단](client-behavioral-blocking.md)** 끝점의 위협은 기계 학습을 통해 감지된 다음 자동으로 차단되고 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-131">**[Client behavioral blocking](client-behavioral-blocking.md)** Threats on endpoints are detected through machine learning, and then are blocked and remediated automatically.</span></span> <span data-ttu-id="192fe-132">클라이언트 동작 차단은 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-132">(Client behavioral blocking is enabled by default.)</span></span> 

- <span data-ttu-id="192fe-133">**[피드백 루프](feedback-loop-blocking.md)** 차단(신속한 보호라고도 지칭) 위협 감지는 동작 인텔리전스를 통해 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-133">**[Feedback-loop blocking](feedback-loop-blocking.md)** (also referred to as rapid protection) Threat detections are observed through behavioral intelligence.</span></span> <span data-ttu-id="192fe-134">위협이 중지되고 다른 끝점에서 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-134">Threats are stopped and prevented from running on other endpoints.</span></span> <span data-ttu-id="192fe-135">피드백 루프 차단은 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-135">(Feedback-loop blocking is enabled by default.)</span></span> 

- <span data-ttu-id="192fe-136">**[차단 모드의 끝점 EDR 응답(EDR)](edr-in-block-mode.md)** 위반 후 보호를 통해 관찰되는 악의적인 아티팩트 또는 동작은 차단되어 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-136">**[Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md)** Malicious artifacts or behaviors that are observed through post-breach protection are blocked and contained.</span></span> <span data-ttu-id="192fe-137">EDR 기본 바이러스 백신 솔루션이 아니어도 Microsoft Defender 바이러스 백신 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-137">EDR in block mode works even if Microsoft Defender Antivirus is not the primary antivirus solution.</span></span> <span data-ttu-id="192fe-138">(EDR 모드로 설정하는 것은 기본적으로 사용하도록 설정되지 않습니다. 기본 설정에서 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="192fe-138">(EDR in block mode is not enabled by default; you turn it on in Microsoft 365 Defender.)</span></span> 

<span data-ttu-id="192fe-139">Microsoft는 계속해서 위협 방지 기능과 기능을 개선하기에 따라 동작 차단 및 포함 영역에 더 많은 것이 제공될 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-139">Expect more to come in the area of behavioral blocking and containment, as Microsoft continues to improve threat protection features and capabilities.</span></span> <span data-ttu-id="192fe-140">현재 계획된 계획 및 롤아웃을 보시다시피 Microsoft 365 [로드맵을 방문하세요.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="192fe-140">To see what's planned and rolling out now, visit the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a><span data-ttu-id="192fe-141">동작 차단 및 실행 포함의 예</span><span class="sxs-lookup"><span data-stu-id="192fe-141">Examples of behavioral blocking and containment in action</span></span>

<span data-ttu-id="192fe-142">동작 차단 및 포함 기능은 다음과 같은 공격자 기술을 차단했습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-142">Behavioral blocking and containment capabilities have blocked attacker techniques such as the following:</span></span>

- <span data-ttu-id="192fe-143">LSASS에서 자격 증명 덤프</span><span class="sxs-lookup"><span data-stu-id="192fe-143">Credential dumping from LSASS</span></span>
- <span data-ttu-id="192fe-144">크로스 프로세스 주입</span><span class="sxs-lookup"><span data-stu-id="192fe-144">Cross-process injection</span></span>
- <span data-ttu-id="192fe-145">프로세스 비우기</span><span class="sxs-lookup"><span data-stu-id="192fe-145">Process hollowing</span></span>
- <span data-ttu-id="192fe-146">사용자 계정 컨트롤 우회</span><span class="sxs-lookup"><span data-stu-id="192fe-146">User Account Control bypass</span></span>
- <span data-ttu-id="192fe-147">바이러스 백신 변조(예: 바이러스 백신을 사용하지 않는 경우 또는 맬웨어를 제외로 추가)</span><span class="sxs-lookup"><span data-stu-id="192fe-147">Tampering with antivirus (such as disabling it or adding the malware as exclusion)</span></span>
- <span data-ttu-id="192fe-148">명령 및 제어(C&C)에 문의하여 페이로드 다운로드</span><span class="sxs-lookup"><span data-stu-id="192fe-148">Contacting Command and Control (C&C) to download payloads</span></span>
- <span data-ttu-id="192fe-149">코인 마이너스</span><span class="sxs-lookup"><span data-stu-id="192fe-149">Coin mining</span></span>
- <span data-ttu-id="192fe-150">부팅 레코드 수정</span><span class="sxs-lookup"><span data-stu-id="192fe-150">Boot record modification</span></span>
- <span data-ttu-id="192fe-151">해시 전달 공격</span><span class="sxs-lookup"><span data-stu-id="192fe-151">Pass-the-hash attacks</span></span>
- <span data-ttu-id="192fe-152">루트 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="192fe-152">Installation of root certificate</span></span>
- <span data-ttu-id="192fe-153">다양한 취약점에 대한 악용 시도</span><span class="sxs-lookup"><span data-stu-id="192fe-153">Exploitation attempt for various vulnerabilities</span></span>

<span data-ttu-id="192fe-154">다음은 동작 차단 및 실행 포함의 실제 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-154">Below are two real-life examples of behavioral blocking and containment in action.</span></span>

### <a name="example-1-credential-theft-attack-against-100-organizations"></a><span data-ttu-id="192fe-155">예제 1: 100개 조직에 대한 자격 증명 도난 공격</span><span class="sxs-lookup"><span data-stu-id="192fe-155">Example 1: Credential theft attack against 100 organizations</span></span>

<span data-ttu-id="192fe-156">[Elusive Threats에](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)설명된 바와 같이: AI 기반 동작 기반 차단은 추적에서 공격을 중지합니다. 전 세계 100개 조직에 대한 자격 증명 도난 공격은 행동 차단 및 포함 기능에 의해 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-156">As described in [In hot pursuit of elusive threats: AI-driven behavior-based blocking stops attacks in their tracks](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks), a credential theft attack against 100 organizations around the world was stopped by behavioral blocking and containment capabilities.</span></span> <span data-ttu-id="192fe-157">루이지 문서가 포함된 스피어 피싱 전자 메일 메시지를 대상 조직으로 전송했습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-157">Spear-phishing email messages that contained a lure document were sent to the targeted organizations.</span></span> <span data-ttu-id="192fe-158">받는 사람이 첨부 파일을 연 경우 관련 원격 문서가 사용자의 디바이스에서 코드를 실행하고 Lokibot 맬웨어를 로드할 수 있습니다. 이 맬웨어는 자격 증명을 훔치고 훔친 데이터를 유출하고 명령 및 제어 서버에서 추가 지침을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-158">If a recipient opened the attachment, a related remote document was able to execute code on the user’s device and load Lokibot malware, which stole credentials, exfiltrated stolen data, and waited for further instructions from a command-and-control server.</span></span> 

<span data-ttu-id="192fe-159">Endpoint용 Defender의 동작 기반 장치 학습 모델은 공격 체인에서 다음 두 지점에서 공격자 기술을 잡았다가 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-159">Behavior-based device learning models in Defender for Endpoint caught and stopped the attacker’s techniques at two points in the attack chain:</span></span>

- <span data-ttu-id="192fe-160">첫 번째 보호 계층에서 악용 동작을 감지했습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-160">The first protection layer detected the exploit behavior.</span></span> <span data-ttu-id="192fe-161">클라우드의 장치 학습 분류자는 공격을 차단하라는 지시와 함께 위협을 올바르게 식별하고 즉시 클라이언트 장치에 지시했습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-161">Device learning classifiers in the cloud correctly identified the threat as and immediately instructed the client device to block the attack.</span></span>
- <span data-ttu-id="192fe-162">두 번째 보호 계층은 공격이 첫 번째 계층을 넘어가고, 프로세스 공백을 감지하고, 해당 프로세스를 중지하고, 해당 파일(예: Lokibot)을 제거한 경우를 중지하는 데 도움을 주었다.</span><span class="sxs-lookup"><span data-stu-id="192fe-162">The second protection layer, which helped stop cases where the attack got past the first layer, detected process hollowing, stopped that process, and removed the corresponding files (such as Lokibot).</span></span> 

<span data-ttu-id="192fe-163">공격이 감지되고 중지되는 동안 "초기 액세스 [알림"과 같은](microsoft-defender-security-center.md) 경고가 트리거되고 Microsoft 365 Defender 포털(이전의 Microsoft Defender 보안 센터)</span><span class="sxs-lookup"><span data-stu-id="192fe-163">While the attack was detected and stopped, alerts, such as an "initial access alert," were triggered and appeared in the [Microsoft 365 Defender portal](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center):</span></span>

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="사이트 포털의 Microsoft 365 Defender 알림":::

<span data-ttu-id="192fe-165">이 예에서는 실행을 시작한 후에도 클라우드의 동작 기반 장치 학습 모델이 공격으로부터 새로운 보호 계층을 추가하는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="192fe-165">This example shows how behavior-based device learning models in the cloud add new layers of protection against attacks, even after they have started running.</span></span>

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a><span data-ttu-id="192fe-166">예제 2: NTLM 릴레이 - Juicy Malware malware variant</span><span class="sxs-lookup"><span data-stu-id="192fe-166">Example 2: NTLM relay - Juicy Potato malware variant</span></span>

<span data-ttu-id="192fe-167">최근 블로그 게시물 동작 차단 및 [포함:](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)2020년 1월에 끝점용 Defender가 조직의 장치에서 권한 에스컬레이터 활동을 감지했습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-167">As described in the recent blog post, [Behavioral blocking and containment: Transforming optics into protection](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection), in January 2020, Defender for Endpoint detected a privilege escalation activity on a device in an organization.</span></span> <span data-ttu-id="192fe-168">"NTLM 릴레이를 사용하여 가능한 권한 에스컬레이터"라는 경고가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-168">An alert called “Possible privilege escalation using NTLM relay” was triggered.</span></span>

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Juicy Malware 맬웨어에 대한 NTLM 경고":::

<span data-ttu-id="192fe-170">위협이 맬웨어로 발견되었습니다. 이 도구는 공격자가 디바이스에서 권한 에스컬레이터를 다운로드하는 데 사용되는 주크로(Juicy)라는 의심스러운 해킹 도구의 새로운 변형으로, 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-170">The threat turned out to be malware; it was a new, not-seen-before variant of a notorious hacking tool called Juicy Potato, which is used by attackers to get privilege escalation on a device.</span></span> 

<span data-ttu-id="192fe-171">경고가 트리거된 후 파일이 분석된 후 악성으로 확인된 시간(분)입니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-171">Minutes after the alert was triggered, the file was analyzed, and confirmed to be malicious.</span></span> <span data-ttu-id="192fe-172">다음 이미지와 같이 프로세스가 중지 및 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-172">Its process was stopped and blocked, as shown in the following image:</span></span>

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="아티팩트 차단":::

<span data-ttu-id="192fe-174">아티팩트가 차단된 후 몇 분 후에 동일한 파일의 여러 인스턴스가 동일한 장치에서 차단되어 추가 공격자 또는 기타 맬웨어가 장치에 배포되지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-174">A few minutes after the artifact was blocked, multiple instances of the same file were blocked on the same device, preventing additional attackers or other malware from deploying on the device.</span></span> 

<span data-ttu-id="192fe-175">이 예에서는 동작 차단 및 포함 기능을 통해 위협이 자동으로 감지, 포함 및 차단되는 것으로 보여집니다.</span><span class="sxs-lookup"><span data-stu-id="192fe-175">This example shows that with behavioral blocking and containment capabilities, threats are detected, contained, and blocked automatically.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="192fe-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="192fe-176">Next steps</span></span>

- [<span data-ttu-id="192fe-177">끝점용 Defender에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="192fe-177">Learn more about Defender for Endpoint</span></span>](overview-endpoint-detection-response.md)

- [<span data-ttu-id="192fe-178">공격 표면 감소 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="192fe-178">Configure your attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="192fe-179">차단 EDR 사용</span><span class="sxs-lookup"><span data-stu-id="192fe-179">Enable EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="192fe-180">최근 전역 위협 활동 보기</span><span class="sxs-lookup"><span data-stu-id="192fe-180">See recent global threat activity</span></span>](https://www.microsoft.com/wdsi/threats)

- [<span data-ttu-id="192fe-181">개요를 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="192fe-181">Get an overview of Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)
