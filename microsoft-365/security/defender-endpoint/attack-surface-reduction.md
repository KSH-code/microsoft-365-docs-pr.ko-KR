---
title: 공격 표면 감소 규칙을 사용하여 맬웨어 감염 방지
description: 공격 표면 감소 규칙은 악용이 앱 및 스크립트를 사용하여 장치를 맬웨어에 감염하는 것을 방지하는 데 도움이 될 수 있습니다.
keywords: 공격 표면 감소 규칙, asr, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: eadca063d50bf1f969f1bb247b6e56d8ec46a6e0
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169583"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="c9d5f-104">공격 표면 감소 규칙을 사용하여 맬웨어 감염 방지</span><span class="sxs-lookup"><span data-stu-id="c9d5f-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="c9d5f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c9d5f-105">**Applies to:**</span></span>

- [<span data-ttu-id="c9d5f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c9d5f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c9d5f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9d5f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="c9d5f-108">공격 표면 감소 규칙이 중요한 이유</span><span class="sxs-lookup"><span data-stu-id="c9d5f-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="c9d5f-109">조직의 공격 표면에는 공격자가 조직의 장치 또는 네트워크를 손상시킬 수 있는 모든 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="c9d5f-110">공격 표면을 줄이는 것은 조직의 장치와 네트워크를 보호하는 것을 의미하며, 공격자는 공격을 더 적은 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="c9d5f-111">끝점용 Microsoft Defender에서 공격 표면 감소 규칙을 구성하면 도움이 될 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="c9d5f-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="c9d5f-112">공격 표면 감소 규칙은 다음과 같은 특정 소프트웨어 동작을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="c9d5f-113">파일 다운로드 또는 실행을 시도하는 실행 파일 및 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="c9d5f-113">Launching executable files and scripts that attempt to download or run files</span></span>
- <span data-ttu-id="c9d5f-114">난동 또는 기타 의심스러운 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="c9d5f-114">Running obfuscated or otherwise suspicious scripts</span></span>
- <span data-ttu-id="c9d5f-115">앱이 일반적인 일과의 작업 중에 일반적으로 시작되지 않는 동작 수행</span><span class="sxs-lookup"><span data-stu-id="c9d5f-115">Performing behaviors that apps don't usually initiate during normal day-to-day work</span></span>

<span data-ttu-id="c9d5f-116">이러한 소프트웨어 동작은 경우에 따라 합법적인 응용 프로그램에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-116">Such software behaviors are sometimes seen in legitimate applications.</span></span> <span data-ttu-id="c9d5f-117">그러나 이러한 동작은 일반적으로 맬웨어를 통해 공격자에 의해 악용되는 위험한 동작으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-117">However, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="c9d5f-118">공격 표면 감소 규칙은 소프트웨어 기반의 위험한 동작을 제한하고 조직을 안전하게 유지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-118">Attack surface reduction rules can constrain software-based risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="c9d5f-119">공격 표면 감소 규칙을 구성하는 방법에 대한 자세한 내용은 공격 표면 감소 규칙 사용 [을 참조하세요.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-119">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="c9d5f-120">배포 전에 규칙 영향 평가</span><span class="sxs-lookup"><span data-stu-id="c9d5f-120">Assess rule impact before deployment</span></span>

<span data-ttu-id="c9d5f-121">에서 해당 규칙에 대한 보안 권장을 열면 공격 표면 감소 규칙이 네트워크에 어떤 [영향을 줄 수](/windows/security/threat-protection/#tvm)위협 및 취약성 관리.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-121">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="공격 표면 감소 규칙에 대한 보안 다시코":::

<span data-ttu-id="c9d5f-123">권장 사항 세부 정보 창에서 사용자 영향을 확인하여 생산성에 부정적인 영향을 주지 않으면서 차단 모드에서 규칙을 사용하도록 설정하는 새 정책을 허용할 수 있는 장치의 비율을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-123">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

<span data-ttu-id="c9d5f-124">[지원되는](enable-attack-surface-reduction.md#requirements) 운영 체제에 대한 자세한 내용은 "공격 표면 감소 규칙 사용" 문서의 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-124">See [Requirements](enable-attack-surface-reduction.md#requirements) in the "Enable attack surface reduction rules" article for information about supported operating systems.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="c9d5f-125">평가를 위한 감사 모드</span><span class="sxs-lookup"><span data-stu-id="c9d5f-125">Audit mode for evaluation</span></span>

<span data-ttu-id="c9d5f-126">감사 [모드를 사용하여](audit-windows-defender.md) 공격 표면 감소 규칙이 사용하도록 설정된 경우 조직에 어떤 영향을 주는지 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-126">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if enabled.</span></span> <span data-ttu-id="c9d5f-127">모든 규칙을 먼저 감사 모드에서 실행하여 해당 규칙이 업무(LINE-OF-BUSINESS) 응용 프로그램에 미치는 영향을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-127">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="c9d5f-128">많은 기간 업무(기간 업무) 응용 프로그램은 제한된 보안 문제로 작성되어 맬웨어와 유사한 방식으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-128">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="c9d5f-129">감사 데이터를 모니터링하고 [](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 필요한 응용 프로그램에 대한 제외를 추가하면 생산성을 줄이지 않고 공격 표면 감소 규칙을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-129">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="c9d5f-130">사용자에 대한 경고 모드</span><span class="sxs-lookup"><span data-stu-id="c9d5f-130">Warn mode for users</span></span>

<span data-ttu-id="c9d5f-131">(**NEW**!) 경고 모드 기능 이전에 사용하도록 설정된 공격 표면 감소 규칙을 감사 모드 또는 차단 모드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-131">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="c9d5f-132">새 경고 모드를 사용하면 콘텐츠가 공격 표면 축소 규칙에 의해 차단되면 콘텐츠가 차단된 것 을 나타내는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-132">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="c9d5f-133">또한 이 대화 상자에서는 콘텐츠 차단을 해제할 수 있는 옵션도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-133">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="c9d5f-134">그러면 사용자가 작업을 다시 시도할 수 있으며 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-134">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="c9d5f-135">사용자가 콘텐츠 차단을 해제하면 콘텐츠가 24시간 동안 차단되지 않은 상태로 유지된 다음 다시 시작을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-135">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="c9d5f-136">경고 모드는 사용자가 작업을 수행하는 데 필요한 콘텐츠에 액세스하지 못하게 하여 조직이 공격 표면 감소 규칙을 적용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-136">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="c9d5f-137">작동 경고 모드에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9d5f-137">Requirements for warn mode to work</span></span>

<span data-ttu-id="c9d5f-138">경고 모드는 다음 버전의 경고를 실행하는 장치에서 Windows.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-138">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="c9d5f-139">[Windows 10, 버전 1809](/windows/whats-new/whats-new-windows-10-version-1809) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-139">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="c9d5f-140">[Windows Server, 버전 1809 이상](/windows-server/get-started/whats-new-in-windows-server-1809)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-140">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="c9d5f-141">Microsoft Defender 바이러스 백신 활성 모드에서 실시간 보호를 통해 [실행해야 합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-141">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="c9d5f-142">또한 맬웨어 [방지 Microsoft Defender 바이러스 백신](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-142">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="c9d5f-143">최소 플랫폼 릴리스 요구 사항: `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-143">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="c9d5f-144">최소 엔진 릴리스 요구 사항: `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-144">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="c9d5f-145">자세한 내용은 Microsoft Defender 맬웨어 방지 플랫폼에 대한 업데이트를 [참조하세요.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-145">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="c9d5f-146">경고 모드가 지원되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="c9d5f-146">Cases where warn mode is not supported</span></span>

<span data-ttu-id="c9d5f-147">경고 모드는 3가지 공격 표면 감소 규칙에서 구성할 때 지원되지 Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-147">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="c9d5f-148">(그룹 정책을 사용하여 공격 표면 축소 규칙을 구성하는 경우 경고 모드가 지원됩니다.) 경고 모드에서 구성할 때 경고 모드를 지원하지 않는 세 가지 규칙은 Microsoft Endpoint Manager 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-148">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="c9d5f-149">[JavaScript 또는 VBScript에서 다운로드한](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) 실행 콘텐츠(GUID)를 시작하지 차단 `d3e037e1-3eb8-44c8-a917-57927947596d`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-149">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="c9d5f-150">[WMI 이벤트 구독(GUID)을 통한](#block-persistence-through-wmi-event-subscription) 지속성 `e6db77e5-3df2-4cf1-b95a-636979351e5b` 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-150">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="c9d5f-151">[랜섬웨어에 대한](#use-advanced-protection-against-ransomware) 고급 보호 사용(GUID) `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-151">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="c9d5f-152">또한 이전 버전의 버전을 실행하는 장치에서는 경고 모드가 지원되지 Windows.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-152">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="c9d5f-153">이러한 경우 경고 모드에서 실행하도록 구성된 공격 표면 감소 규칙은 차단 모드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-153">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="c9d5f-154">알림 및 알림</span><span class="sxs-lookup"><span data-stu-id="c9d5f-154">Notifications and alerts</span></span>

<span data-ttu-id="c9d5f-155">공격 표면 감소 규칙이 트리거될 때마다 알림이 장치에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-155">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="c9d5f-156">회사 세부 정보 및 연락처 정보로 [알림을 사용자 지정](customize-attack-surface-reduction.md#customize-the-notification)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-156">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="c9d5f-157">또한 특정 공격 표면 감소 규칙이 트리거되면 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-157">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="c9d5f-158">알림 및 생성된 경고는 Microsoft 365 Defender 포털()(이전의 [https://security.microsoft.com](https://security.microsoft.com) [Microsoft Defender 보안 센터)에서 볼 수 있습니다.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-158">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="c9d5f-159">고급 헌팅 및 공격 표면 축소 이벤트</span><span class="sxs-lookup"><span data-stu-id="c9d5f-159">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="c9d5f-160">고급 헌팅을 사용하여 공격 표면 감소 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-160">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="c9d5f-161">들어오는 데이터의 양을 간소화하기 위해 고급 헌팅을 통해 각 시간의 고유한 프로세스만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-161">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="c9d5f-162">공격 범위 축소 이벤트의 시간은 이벤트가 시간 내에 처음으로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-162">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="c9d5f-163">예를 들어 오후 2시 동안 10대의 장치에서 공격 표면 감소 이벤트가 발생했다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-163">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="c9d5f-164">첫 번째 이벤트가 2:15에 발생하고 마지막 2:45에 발생했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-164">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="c9d5f-165">고급 헌팅을 사용하면 실제로 10대의 장치에서 발생한 경우에도 해당 이벤트의 인스턴스가 하나씩 표시될 수 있으며 타임스탬프는 오후 2시 15분입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-165">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="c9d5f-166">고급 헌팅에 대한 자세한 내용은 고급 헌팅으로 위협을 사전 [대응적으로 헌팅을 참조하세요.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-166">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="c9d5f-167">여러 버전에서 공격 Windows 기능</span><span class="sxs-lookup"><span data-stu-id="c9d5f-167">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="c9d5f-168">다음 버전 및 버전의 디바이스를 실행하는 장치에 대해 공격 표면 감소 규칙을 설정할 수 Windows.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-168">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="c9d5f-169">Windows 10 Pro 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-169">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c9d5f-170">Windows 10 Enterprise 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-170">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c9d5f-171">Windows 서버, [버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-171">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="c9d5f-172">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-172">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c9d5f-173">공격 표면 감소 규칙에는 Windows E5 라이선스가 필요하지 않습니다. [E5를](/windows/deployment/deploy-enterprise-licenses)Windows 고급 관리 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-173">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="c9d5f-174">E5에서만 사용할 수 있는 고급 Windows 포함:</span><span class="sxs-lookup"><span data-stu-id="c9d5f-174">The advanced capabilities - available only in Windows E5 - include:</span></span>

- <span data-ttu-id="c9d5f-175">[Endpoint용 Defender에서](microsoft-defender-endpoint.md) 사용할 수 있는 모니터링, 분석 및 워크플로</span><span class="sxs-lookup"><span data-stu-id="c9d5f-175">The monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md)</span></span>
- <span data-ttu-id="c9d5f-176">의 보고 및 구성 [Microsoft 365 Defender.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-176">The reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="c9d5f-177">이러한 고급 기능은 E3 라이선스 또는 Windows Professional Windows 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-177">These advanced capabilities aren't available with a Windows Professional or Windows E3 license.</span></span> <span data-ttu-id="c9d5f-178">그러나 해당 라이선스가 있는 경우 이벤트 뷰어 및 로그를 사용하여 Microsoft Defender 바이러스 백신 축소 규칙 이벤트를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-178">However, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="c9d5f-179">포털에서 공격 표면 감소 Microsoft 365 Defender 검토</span><span class="sxs-lookup"><span data-stu-id="c9d5f-179">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="c9d5f-180">Endpoint용 Defender는 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-180">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="c9d5f-181">고급 헌팅을 사용하여 에서 Defender에서 [끝점 Microsoft 365 Defender](microsoft-defender-security-center.md) [쿼리할 수 있습니다.](advanced-hunting-query-language.md)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-181">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="c9d5f-182">감사 모드를 실행하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 공격 표면 감소 규칙이 환경에 미칠 수 있는 영향을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-182">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules might affect your environment.</span></span>

<span data-ttu-id="c9d5f-183">다음은 예제 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-183">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="c9d5f-184">이벤트 뷰어에서 공격 Windows 검토</span><span class="sxs-lookup"><span data-stu-id="c9d5f-184">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="c9d5f-185">다음과 같은 Windows 로그를 검토하여 공격 표면 감소 규칙에 의해 생성된 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-185">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="c9d5f-186">평가 [패키지를](https://aka.ms/mp7z2w) 다운로드하고  디바이스에서cfa-events.xml쉽게 액세스할 수 있는 위치에 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-186">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="c9d5f-187">이벤트 뷰어를 시작 메뉴 이벤트 뷰어에 Windows 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="c9d5f-187">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="c9d5f-188">**작업에서** 사용자 지정 보기 **가져오기... 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c9d5f-188">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="c9d5f-189">추출된 *cfa-events.xml* 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-189">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="c9d5f-190">또는 [XML을 직접 복사합니다.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-190">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="c9d5f-191">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-191">Select **OK**.</span></span>

<span data-ttu-id="c9d5f-192">이벤트를 필터로 지정하여 제어된 폴더 액세스와 관련된 다음 이벤트만 표시하는 사용자 지정 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-192">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="c9d5f-193">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c9d5f-193">Event ID</span></span>|<span data-ttu-id="c9d5f-194">설명</span><span class="sxs-lookup"><span data-stu-id="c9d5f-194">Description</span></span>|
|---|---|
|<span data-ttu-id="c9d5f-195">5007</span><span class="sxs-lookup"><span data-stu-id="c9d5f-195">5007</span></span>|<span data-ttu-id="c9d5f-196">설정이 변경될 때의 이벤트</span><span class="sxs-lookup"><span data-stu-id="c9d5f-196">Event when settings are changed</span></span>|
|<span data-ttu-id="c9d5f-197">1121</span><span class="sxs-lookup"><span data-stu-id="c9d5f-197">1121</span></span>|<span data-ttu-id="c9d5f-198">차단 모드에서 규칙이 발생하면 이벤트</span><span class="sxs-lookup"><span data-stu-id="c9d5f-198">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="c9d5f-199">1122</span><span class="sxs-lookup"><span data-stu-id="c9d5f-199">1122</span></span>|<span data-ttu-id="c9d5f-200">감사 모드에서 규칙이 발생하면 이벤트</span><span class="sxs-lookup"><span data-stu-id="c9d5f-200">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="c9d5f-201">이벤트 로그의 공격 표면 축소 이벤트에 대해 나열된 "엔진 버전"은 운영 체제가 아니라 Endpoint용 Defender에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-201">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="c9d5f-202">Endpoint용 Defender는 Windows 10 통합되어 있으므로 이 Windows 10 설치된 모든 장치에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-202">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="c9d5f-203">공격 노출 영역 축소 규칙</span><span class="sxs-lookup"><span data-stu-id="c9d5f-203">Attack surface reduction rules</span></span>

<span data-ttu-id="c9d5f-204">다음 표 및 하위 섹션에서는 16개 공격 표면 감소 규칙 각각에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-204">The following table and subsections describe each of the 16 attack surface reduction rules.</span></span> <span data-ttu-id="c9d5f-205">공격 표면 감소 규칙은 규칙 이름에 따라 사전순으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-205">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="c9d5f-206">그룹 정책 또는 PowerShell을 사용하여 공격 표면 감소 규칙을 구성하는 경우 GUID가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-206">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="c9d5f-207">반면에 사용자 또는 Microsoft Endpoint Manager Microsoft Intune GUID가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-207">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="c9d5f-208">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="c9d5f-208">Rule name</span></span>|<span data-ttu-id="c9d5f-209">GUID</span><span class="sxs-lookup"><span data-stu-id="c9d5f-209">GUID</span></span>|<span data-ttu-id="c9d5f-210">파일 & 제외</span><span class="sxs-lookup"><span data-stu-id="c9d5f-210">File & folder exclusions</span></span>|<span data-ttu-id="c9d5f-211">지원되는 최소 OS</span><span class="sxs-lookup"><span data-stu-id="c9d5f-211">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="c9d5f-212">악용된 취약한 서명된 드라이버의 남용 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-212">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="c9d5f-213">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-213">Supported</span></span>|<span data-ttu-id="c9d5f-214">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-214">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="c9d5f-215">Adobe Reader에서 하위 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-215">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="c9d5f-216">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-216">Supported</span></span>|<span data-ttu-id="c9d5f-217">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-217">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-218">모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-218">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="c9d5f-219">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-219">Supported</span></span>|<span data-ttu-id="c9d5f-220">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-220">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-221">로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-221">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="c9d5f-222">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-222">Supported</span></span>|<span data-ttu-id="c9d5f-223">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-223">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-224">전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-224">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="c9d5f-225">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-225">Supported</span></span>|<span data-ttu-id="c9d5f-226">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-226">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-227">실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-227">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="c9d5f-228">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-228">Supported</span></span>|<span data-ttu-id="c9d5f-229">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-229">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-230">잠재적으로 난치될 수 있는 스크립트의 실행 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-230">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="c9d5f-231">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-231">Supported</span></span>|<span data-ttu-id="c9d5f-232">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-232">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-233">JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-233">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="c9d5f-234">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-234">Supported</span></span>|<span data-ttu-id="c9d5f-235">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-235">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-236">응용 Office 콘텐츠 만들기 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-236">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="c9d5f-237">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-237">Supported</span></span>|<span data-ttu-id="c9d5f-238">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-238">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-239">응용 Office 코드 삽입 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-239">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="c9d5f-240">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-240">Supported</span></span>|<span data-ttu-id="c9d5f-241">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-241">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-242">통신 Office 응용 프로그램에서 자식 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-242">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="c9d5f-243">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-243">Supported</span></span>|<span data-ttu-id="c9d5f-244">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-244">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-245">WMI 이벤트 구독을 통한 지속성 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-245">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="c9d5f-246">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="c9d5f-246">Not supported</span></span>|<span data-ttu-id="c9d5f-247">[Windows 10 버전 1903(빌드](/windows/whats-new/whats-new-windows-10-version-1903) 18362) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-247">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="c9d5f-248">PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-248">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="c9d5f-249">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-249">Supported</span></span>|<span data-ttu-id="c9d5f-250">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-250">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-251">USB에서 실행된 무단 및 사인되지 않은 프로세스 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-251">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="c9d5f-252">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-252">Supported</span></span>|<span data-ttu-id="c9d5f-253">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-253">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-254">매크로에서 Win32 API Office 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-254">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="c9d5f-255">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-255">Supported</span></span>|<span data-ttu-id="c9d5f-256">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-256">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="c9d5f-257">랜섬웨어에 대한 고급 보호 사용</span><span class="sxs-lookup"><span data-stu-id="c9d5f-257">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="c9d5f-258">지원됨</span><span class="sxs-lookup"><span data-stu-id="c9d5f-258">Supported</span></span>|<span data-ttu-id="c9d5f-259">[Windows 10 버전 1709(RS3,](/windows/whats-new/whats-new-windows-10-version-1709) 빌드 16299) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-259">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="c9d5f-260">악용된 취약한 서명된 드라이버의 남용 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-260">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="c9d5f-261">이 규칙은 응용 프로그램이 디스크에 취약한 서명된 드라이버를 작성하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-261">This rule prevents an application from writing a vulnerable signed driver to disk.</span></span> <span data-ttu-id="c9d5f-262">와일드에서 취약한 서명된 드라이버는 커널에 액세스하기에 충분한 권한이 있는 로컬 응용 프로그램에 \-  \- 의해 악용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-262">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="c9d5f-263">취약한 서명된 드라이버를 사용하면 공격자가 보안 솔루션을 사용하지 않도록 설정하거나 우회할 수 있습니다. 결과적으로 시스템 손상이 일어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-263">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="c9d5f-264">**악용된** 취약한 드라이버 남용 차단 규칙은 시스템에 이미 있는 드라이버가 로드되는 것을 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-264">The **Block abuse of exploited vulnerable signed drivers** rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="c9d5f-265">MEM OMA-URI 사용자 지정 규칙의 프로시저 정보에 대해 [MEM OMA-URI를](enable-attack-surface-reduction.md#mem) 사용하여 이 규칙을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-265">You can configure this rule using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="c9d5f-266">PowerShell을 사용하여 이 규칙을 [구성할 수 있습니다.](enable-attack-surface-reduction.md#powershell)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-266">You can also configure this rule using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="c9d5f-267">드라이버를 검사하기 위해 이 웹 사이트를 사용하여 분석을 위해 [드라이버를 제출합니다.](https://www.microsoft.com/en-us/wdsi/driversubmission)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-267">To have a driver examined, use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="c9d5f-268">이 규칙은 ASR이 지원되는 모든 버전에서 지원됩니다. 은:</span><span class="sxs-lookup"><span data-stu-id="c9d5f-268">This rule is supported in all versions in which ASR is supported; which is:</span></span>

- <span data-ttu-id="c9d5f-269">[Windows 10 Pro 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-269">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c9d5f-270">[Windows 10 Enterprise 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-270">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="c9d5f-271">[Windows Server, 버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상</span><span class="sxs-lookup"><span data-stu-id="c9d5f-271">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="c9d5f-272">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-272">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c9d5f-273">Intune 이름: `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-273">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="c9d5f-274">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-274">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="c9d5f-275">Adobe Reader에서 하위 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-275">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="c9d5f-276">이 규칙은 Adobe Reader가 프로세스를 만들지 못하게 차단하여 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-276">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="c9d5f-277">소셜 엔지니어링 또는 악용을 통해 맬웨어는 페이로드를 다운로드 및 시작하고 Adobe Reader를 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-277">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="c9d5f-278">Adobe Reader에서 자식 프로세스가 생성되지 않도록 차단하면 벡터로 사용하려는 맬웨어가 확산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-278">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="c9d5f-279">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-279">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-280">Windows 10, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-280">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="c9d5f-281">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-281">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-282">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-282">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c9d5f-283">Intune 이름: `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-283">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="c9d5f-284">Configuration Manager 이름: 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-284">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="c9d5f-285">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-285">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="c9d5f-286">모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-286">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="c9d5f-287">이 규칙은 Office 프로세스 만들기를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-287">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="c9d5f-288">Office 앱에는 Word, Excel, PowerPoint, OneNote 및 Access가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-288">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="c9d5f-289">악의적인 자식 프로세스를 만드는 것은 일반적인 맬웨어 전략입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-289">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="c9d5f-290">벡터로 Office 악용하는 맬웨어는 VBA 매크로를 실행하고 코드를 악용하여 더 많은 페이로드를 다운로드하고 실행하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-290">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="c9d5f-291">그러나 일부 합법적인 업무(LINE-OF-BUSINESS) 응용 프로그램에서는 자식 프로세스를 무해한 용도로 생성할 수도 있습니다. 명령 프롬프트를 만들거나 PowerShell을 사용하여 레지스트리 설정을 구성하는 등의 경우</span><span class="sxs-lookup"><span data-stu-id="c9d5f-291">However, some legitimate line-of-business applications might also generate child processes for benign purposes; such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="c9d5f-292">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-292">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-293">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="c9d5f-293">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="c9d5f-294">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-294">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-295">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-295">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-296">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="c9d5f-296">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-297">Intune 이름: `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-297">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="c9d5f-298">Configuration Manager 이름: `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-298">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="c9d5f-299">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-299">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="c9d5f-300">로컬 보안 기관 하위 Windows 자격 증명 도용 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-300">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="c9d5f-301">이 규칙은 LSASS(Local Security Authority Subsystem Service)를 잠가 자격 증명 도용을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-301">This rule helps prevent credential stealing by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="c9d5f-302">LSASS는 Windows 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-302">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="c9d5f-303">Microsoft Defender Credential Guard는 Windows 10 LSASS에서 자격 증명을 추출하려고 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-303">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="c9d5f-304">그러나 일부 조직에서는 사용자 지정 스마트 카드 드라이버 또는 LSA(Local Security Authority)로 로드되는 다른 프로그램과의 호환성 문제로 인하여 모든 컴퓨터에서 Credential Guard를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-304">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="c9d5f-305">이러한 경우 공격자는 Mimikatz와 같은 해킹 도구를 사용하여 LSASS에서 지우기 암호 및 NTLM 해시를 스크랩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-305">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="c9d5f-306">일부 앱에서는 코드가 실행 중인 모든 프로세스를 열기하고 모든 사용 권한으로 열려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-306">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="c9d5f-307">이 규칙은 앱의 프로세스 열기 작업을 거부하고 보안 이벤트 로그에 세부 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-307">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="c9d5f-308">이 규칙은 노이즈를 많이 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-308">This rule can generate a lot of noise.</span></span> <span data-ttu-id="c9d5f-309">LSASS를 열기만 하지만 기능에는 실질적인 영향을 미치는 앱이 있는 경우 제외 목록에 앱을 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-309">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="c9d5f-310">이 이벤트 로그 항목 자체는 악의적인 위협을 나타낼 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-310">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="c9d5f-311">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-311">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-312">Windows 10 버전 1803</span><span class="sxs-lookup"><span data-stu-id="c9d5f-312">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="c9d5f-313">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-313">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-314">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-314">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-315">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="c9d5f-315">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-316">Intune 이름: `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-316">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="c9d5f-317">Configuration Manager 이름: `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-317">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="c9d5f-318">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-318">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="c9d5f-319">전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-319">Block executable content from email client and webmail</span></span>

<span data-ttu-id="c9d5f-320">이 규칙은 Microsoft Outlook 응용 프로그램 또는 Outlook.com 및 기타 인기 있는 웹 메일 공급자에서 연 전자 메일에서 다음 파일 형식이 시작되지 Outlook 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-320">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="c9d5f-321">실행 파일(예: .exe, .dll 또는 .scr)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-321">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="c9d5f-322">스크립트 파일(예: PowerShell .ps, Visual Basic .vbs 또는 JavaScript .js 파일)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-322">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="c9d5f-323">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-323">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-324">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="c9d5f-324">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="c9d5f-325">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-325">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-326">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-326">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-327">Microsoft Endpoint Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="c9d5f-327">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-328">Intune 이름: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-328">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="c9d5f-329">Microsoft Endpoint Manager 이름:`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-329">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="c9d5f-330">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-330">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="c9d5f-331">전자 **메일 클라이언트 및 웹** 메일에서 실행 가능한 콘텐츠 차단 규칙에는 사용하는 응용 프로그램에 따라 다음과 같은 대체 설명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-331">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="c9d5f-332">Intune(구성 프로필): 전자 메일(webmail/mail client)에서 삭제된 실행 가능한 콘텐츠(예: dll, ps, js, vbs 등)의 실행입니다(예외 없음).</span><span class="sxs-lookup"><span data-stu-id="c9d5f-332">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="c9d5f-333">Endpoint Manager: 전자 메일 및 웹 메일 클라이언트에서 실행 가능한 콘텐츠 다운로드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-333">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="c9d5f-334">그룹 정책: 전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-334">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="c9d5f-335">실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-335">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="c9d5f-336">이 규칙은 다음 조건이 충족되지 않는 한 .exe, .dll 또는 .scr과 같은 실행 파일이 시작되지 못하게 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-336">This rule blocks executable files, such as .exe, .dll, or .scr, from launching unless any of the following conditions are met:</span></span>

- <span data-ttu-id="c9d5f-337">Prevalence: The executable files are found on more than 1,000 endpoints</span><span class="sxs-lookup"><span data-stu-id="c9d5f-337">Prevalence: The executable files are found on more than 1,000 endpoints</span></span>
- <span data-ttu-id="c9d5f-338">사용 시간: 실행 파일이 24시간 이상 전에 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-338">Age: The executable files were released more than 24 hours ago</span></span>
- <span data-ttu-id="c9d5f-339">위치: 실행 파일이 신뢰할 수 있는 목록 또는 제외 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-339">Location: The executable files are included in a trusted list or an exclusion list</span></span>

<span data-ttu-id="c9d5f-340">파일이 악의적인 경우 처음에 명확하지 않을 수 있는 것으로 보아서, 트러블되지 않았거나 알 수 없는 실행 파일을 실행하는 것은 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-340">Launching untrusted or unknown executable files can be risky, as it might not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9d5f-341">이 규칙을 [사용하려면](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 클라우드 제공 보호를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-341">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="c9d5f-342">GUID로 **보전,** 보존 기간 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단 규칙은 Microsoft가 소유하며 관리자가 `01443614-cd74-433a-b99e-2ecdc07bfc25` 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-342">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="c9d5f-343">이 규칙은 클라우드 제공 보호를 사용하여 신뢰할 수 있는 목록을 정기적으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-343">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="c9d5f-344">개별 파일 또는 폴더(폴더 경로 또는 정식 리소스 이름을 사용하여)를 지정할 수 있지만 적용할 규칙이나 제외를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-344">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="c9d5f-345">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-345">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-346">Windows 10 버전 1803</span><span class="sxs-lookup"><span data-stu-id="c9d5f-346">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="c9d5f-347">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-347">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-348">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-348">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-349">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="c9d5f-349">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-350">Intune 이름: `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-350">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="c9d5f-351">Configuration Manager 이름: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-351">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="c9d5f-352">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-352">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="c9d5f-353">잠재적으로 난치될 수 있는 스크립트의 실행 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-353">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="c9d5f-354">이 규칙은 난처한 스크립트 내에서 의심스러운 속성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-354">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="c9d5f-355">스크립트 난동은 맬웨어 작성자와 합법적인 응용 프로그램이 지적 재산을 숨기거나 스크립트 로드 시간을 줄이는 데 사용하는 일반적인 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-355">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="c9d5f-356">또한 맬웨어 작성자는 난독을 사용하여 악의적인 코드를 읽기 어렵게 하여 사람 및 보안 소프트웨어에 의해 가려질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-356">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="c9d5f-357">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-357">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-358">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="c9d5f-358">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="c9d5f-359">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-359">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-360">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-360">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-361">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="c9d5f-361">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-362">Intune 이름: `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-362">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="c9d5f-363">Configuration Manager 이름: `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-363">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="c9d5f-364">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-364">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="c9d5f-365">JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-365">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="c9d5f-366">이 규칙은 스크립트가 잠재적으로 악의적인 다운로드 콘텐츠를 시작하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-366">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="c9d5f-367">JavaScript 또는 VBScript로 작성된 맬웨어는 종종 다운로드자 역할을 하여 인터넷에서 다른 맬웨어를 페치하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-367">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="c9d5f-368">일반적인 것은 아니며, 업무용 응용 프로그램에서는 스크립트를 사용하여 설치 관리자를 다운로드하고 실행하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-368">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="c9d5f-369">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-369">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-370">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="c9d5f-370">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="c9d5f-371">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-371">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-372">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-372">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-373">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="c9d5f-373">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-374">Intune 이름: `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-374">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="c9d5f-375">Configuration Manager 이름: `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-375">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="c9d5f-376">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-376">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="c9d5f-377">응용 Office 콘텐츠 만들기 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-377">Block Office applications from creating executable content</span></span>

<span data-ttu-id="c9d5f-378">이 규칙은 word, Excel 및 PowerPoint 등의 Office 앱이 악성 코드가 디스크에 기록되지 않도록 차단하여 잠재적으로 악의적인 실행 콘텐츠를 만들지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-378">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="c9d5f-379">벡터로 Office 악용하는 맬웨어는 악의적인 구성 요소를 Office 디스크에 저장하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-379">Malware that abuses Office as a vector might attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="c9d5f-380">이러한 악성 구성 요소는 컴퓨터 재부팅에서 유지되고 시스템에서 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-380">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="c9d5f-381">따라서 이 규칙은 일반적인 지속성 기술에 대해 방어합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-381">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="c9d5f-382">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-382">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-383">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="c9d5f-383">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="c9d5f-384">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-384">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-385">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-385">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="c9d5f-386">[](/configmgr/core/servers/manage/updates) System Center Configuration Manager(SCCM) CB 1710(SCCM이 현재 Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="c9d5f-386">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="c9d5f-387">Intune 이름: `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-387">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="c9d5f-388">SCCM 이름: `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-388">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="c9d5f-389">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-389">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="c9d5f-390">응용 Office 코드 삽입 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-390">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="c9d5f-391">이 규칙은 앱을 다른 프로세스로 Office 코드 삽입 시도를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-391">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="c9d5f-392">공격자는 앱의 Office 사용하여 코드 삽입을 통해 악성 코드를 다른 프로세스로 마이그레이션하려고 시도할 수 있으므로 코드가 깔끔한 프로세스로 악의적으로 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-392">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="c9d5f-393">코드 삽입을 사용하는 데 알려진 합법적인 비즈니스 목적이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-393">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="c9d5f-394">이 규칙은 Word, Excel 및 PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-394">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="c9d5f-395">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-395">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-396">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="c9d5f-396">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="c9d5f-397">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-397">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-398">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-398">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-399">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="c9d5f-399">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-400">Intune 이름: `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-400">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="c9d5f-401">Configuration Manager 이름: `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-401">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="c9d5f-402">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-402">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="c9d5f-403">통신 Office 응용 프로그램에서 자식 프로세스를 만들지 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-403">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="c9d5f-404">이 규칙은 Outlook 자식 프로세스를 만들지 못하게 하지만 합법적인 Outlook 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-404">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="c9d5f-405">이 규칙은 사회 엔지니어링 공격으로부터 보호하고 코드 악용을 통해 보안상 취약성을 악용하지 Outlook.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-405">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="c9d5f-406">또한 사용자의 자격 [Outlook](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 공격자가 사용할 수 있는 규칙 및 양식 악용으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-406">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="c9d5f-407">이 규칙은 규칙에 따라 DLP 정책 팁과 도구 Outlook.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-407">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="c9d5f-408">이 규칙은 Outlook Outlook.com에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-408">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="c9d5f-409">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-409">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-410">Windows 10, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-410">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="c9d5f-411">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-411">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-412">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-412">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c9d5f-413">Intune 이름: `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-413">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="c9d5f-414">Configuration Manager 이름: 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-414">Configuration Manager name: Not available</span></span>

<span data-ttu-id="c9d5f-415">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-415">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="c9d5f-416">WMI 이벤트 구독을 통한 지속성 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-416">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="c9d5f-417">이 규칙은 맬웨어가 WMI를 부인하여 디바이스에서 지속성에 이를 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-417">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9d5f-418">파일 및 폴더 제외는 이 공격 표면 축소 규칙에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-418">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="c9d5f-419">파일 없는 위협은 다양한 방법을 사용하여 숨김을 유지하여 파일 시스템에서 볼 수 없는 것을 방지하고 주기적인 실행 제어를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-419">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="c9d5f-420">일부 위협은 WMI 리포지토리 및 이벤트 모델을 남용하여 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-420">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="c9d5f-421">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-421">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-422">Windows 10 버전 1903</span><span class="sxs-lookup"><span data-stu-id="c9d5f-422">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="c9d5f-423">Windows Server 1903</span><span class="sxs-lookup"><span data-stu-id="c9d5f-423">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="c9d5f-424">Intune 이름: 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-424">Intune name: Not available</span></span>

<span data-ttu-id="c9d5f-425">Configuration Manager 이름: 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-425">Configuration Manager name: Not available</span></span>

<span data-ttu-id="c9d5f-426">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-426">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="c9d5f-427">PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-427">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="c9d5f-428">이 규칙은 [PsExec](/sysinternals/downloads/psexec) 및 [WMI를](/windows/win32/wmisdk/about-wmi) 통해 만든 프로세스의 실행을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-428">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="c9d5f-429">PsExec과 WMI 모두 코드를 원격으로 실행할 수 있으므로 맬웨어가 명령 및 제어 목적으로 이 기능을 남용하거나 조직의 네트워크 전체에 감염을 전파할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-429">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="c9d5f-430">[Intune](/intune) 또는 다른 MDM 솔루션으로 장치를 관리하는 경우 이 규칙만 사용</span><span class="sxs-lookup"><span data-stu-id="c9d5f-430">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="c9d5f-431">이 규칙은 Configuration Manager 클라이언트가 올바르게 Microsoft Endpoint Configuration Manager WMI 명령을 차단하기 때문에 이 규칙은 관리자를 [통해](/configmgr) 관리와 비호환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-431">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="c9d5f-432">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-432">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-433">Windows 10 버전 1803</span><span class="sxs-lookup"><span data-stu-id="c9d5f-433">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="c9d5f-434">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-434">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-435">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-435">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="c9d5f-436">Intune 이름: `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-436">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="c9d5f-437">Configuration Manager 이름: 해당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-437">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="c9d5f-438">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-438">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="c9d5f-439">USB에서 실행된 무단 및 사인되지 않은 프로세스 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-439">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="c9d5f-440">이 규칙을 사용하여 관리자는 SD 카드를 포함하여 USB 이동식 드라이브에서 사인되지 않은 실행 파일 또는 트러블된 실행 파일을 실행하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-440">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="c9d5f-441">차단된 파일 형식에는 실행 파일(예: .exe, .dll 또는 .scr)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-441">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="c9d5f-442">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-442">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-443">Windows 10 버전 1803</span><span class="sxs-lookup"><span data-stu-id="c9d5f-443">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="c9d5f-444">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-444">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-445">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-445">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-446">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="c9d5f-446">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-447">Intune 이름: `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-447">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="c9d5f-448">Configuration Manager 이름: `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-448">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="c9d5f-449">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-449">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="c9d5f-450">매크로에서 Win32 API Office 차단</span><span class="sxs-lookup"><span data-stu-id="c9d5f-450">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="c9d5f-451">이 규칙은 VBA 매크로가 Win32 API를 호출하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-451">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="c9d5f-452">Office VBA는 Win32 API 호출을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-452">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="c9d5f-453">맬웨어는 [Win32 API를](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) 호출하여 디스크에 직접 아무것도 쓰지 않고 악성 셸 코드를 시작하는 등 이 기능을 남용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-453">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="c9d5f-454">대부분의 조직에서는 다른 방법으로 매크로를 사용하는 경우에도 매일 작동할 때 Win32 API를 호출하는 기능을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-454">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="c9d5f-455">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-455">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-456">Windows 10 버전 1709</span><span class="sxs-lookup"><span data-stu-id="c9d5f-456">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="c9d5f-457">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-457">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-458">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-458">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-459">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="c9d5f-459">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-460">Intune 이름: `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-460">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="c9d5f-461">Configuration Manager 이름: `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-461">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="c9d5f-462">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-462">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="c9d5f-463">랜섬웨어에 대한 고급 보호 사용</span><span class="sxs-lookup"><span data-stu-id="c9d5f-463">Use advanced protection against ransomware</span></span>

<span data-ttu-id="c9d5f-464">이 규칙은 랜섬웨어에 대한 추가 보호 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-464">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="c9d5f-465">클라이언트와 클라우드추론을 모두 사용하여 파일이 랜섬웨어와 같은지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-465">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="c9d5f-466">이 규칙은 다음 특성 중 하나 이상이 있는 파일을 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-466">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="c9d5f-467">파일이 Microsoft 클라우드에서 이미 손상되지 않은 것으로 발견된 경우</span><span class="sxs-lookup"><span data-stu-id="c9d5f-467">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="c9d5f-468">파일이 유효한 서명된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-468">The file is a valid signed file.</span></span>
- <span data-ttu-id="c9d5f-469">이 파일은 랜섬웨어로 간주되지 않을 정도로 보전됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-469">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="c9d5f-470">규칙은 랜섬웨어를 방지하기 위해 신중하게 진행되는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-470">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="c9d5f-471">이 규칙을 [사용하려면](enable-cloud-protection-microsoft-defender-antivirus.md) 클라우드 제공 보호를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d5f-471">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="c9d5f-472">이 규칙은</span><span class="sxs-lookup"><span data-stu-id="c9d5f-472">This rule was introduced in:</span></span>

- [<span data-ttu-id="c9d5f-473">Windows 10 버전 1803</span><span class="sxs-lookup"><span data-stu-id="c9d5f-473">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="c9d5f-474">Windows 서버, 버전 1809</span><span class="sxs-lookup"><span data-stu-id="c9d5f-474">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="c9d5f-475">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c9d5f-475">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="c9d5f-476">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="c9d5f-476">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="c9d5f-477">Intune 이름: `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-477">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="c9d5f-478">Configuration Manager 이름: `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-478">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="c9d5f-479">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="c9d5f-479">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>
