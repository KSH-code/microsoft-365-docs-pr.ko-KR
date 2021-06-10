---
title: 공격 표면 감소 규칙 평가
description: 공격 표면 감소가 사용자 지정 데모 도구를 사용하여 공격을 차단하고 방지하는 방법을 참조하세요.
keywords: 공격 표면 감소, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 평가, 테스트, 데모
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c2dea22cc8a0ebb875f83ebd5a3e42f723e5f254
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771324"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="963ed-104">공격 표면 감소 규칙 평가</span><span class="sxs-lookup"><span data-stu-id="963ed-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="963ed-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="963ed-105">**Applies to:**</span></span>

- [<span data-ttu-id="963ed-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="963ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="963ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="963ed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="963ed-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="963ed-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="963ed-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="963ed-110">공격 표면 감소 규칙은 일반적으로 맬웨어가 장치 또는 네트워크를 손상시킬 때 사용하는 작업을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="963ed-111">공격 표면 감소 규칙은 맬웨어 및 랜섬웨어에 사용되는 많은 일반적인 진입점을 닫는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span> 

<span data-ttu-id="963ed-112">다음 버전 및 버전의 디바이스를 실행하는 장치에 대해 공격 표면 감소 규칙을 Windows.</span><span class="sxs-lookup"><span data-stu-id="963ed-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="963ed-113">Windows 10 Pro 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="963ed-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="963ed-114">Windows 10 Enterprise 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상</span><span class="sxs-lookup"><span data-stu-id="963ed-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="963ed-115">Windows 서버, [버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상</span><span class="sxs-lookup"><span data-stu-id="963ed-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="963ed-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="963ed-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="963ed-117">감사 모드를 사용하도록 설정하여 조직에서 기능을 직접 테스트하여 공격 표면 감소 규칙을 평가하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="963ed-117">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="963ed-118">Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 데모 시나리오 웹 사이트(demo.wd.microsoft.com)를 방문하여 기능이 작동하는지 확인하고 작동 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-118">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="963ed-119">감사 모드를 사용하여 영향 측정</span><span class="sxs-lookup"><span data-stu-id="963ed-119">Use audit mode to measure impact</span></span>

<span data-ttu-id="963ed-120">감사 모드에서 공격 표면 감소 규칙을 사용하도록 설정하여 기능이 완전히 활성화된 경우 차단된 앱의 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-120">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="963ed-121">이 기능이 조직에서 어떻게 작동할지 테스트하여 업무 앱에 영향을 주지 않는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-121">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="963ed-122">또한 일반 사용 중에 규칙이 얼마나 자주 발생하게 될지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-122">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="963ed-123">감사 모드에서 공격 표면 감소 규칙을 사용하도록 설정하려면 다음 PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-123">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="963ed-124">여기서 는 공격 표면 감소 규칙의 `<rule ID>` [GUID 값입니다.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="963ed-124">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="963ed-125">감사 모드에서 추가된 모든 공격 표면 축소 규칙을 사용하도록 설정하려면 다음 PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-125">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="963ed-126">조직에서 공격 표면 감소 규칙이 어떻게 작동할지 완전히 감사하려면 관리 도구를 사용하여 이 설정을 네트워크의 장치에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-126">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="963ed-127">그룹 정책, Intune 또는 MDM(모바일 장치 관리) CSP(구성 서비스 공급자)를 사용하여 설정을 구성하고 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-127">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="963ed-128">자세한 내용은 주 공격 표면 [감소 규칙 문서에서 자세히](attack-surface-reduction.md) 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="963ed-128">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="963ed-129">이벤트 뷰어에서 공격 Windows 검토</span><span class="sxs-lookup"><span data-stu-id="963ed-129">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="963ed-130">차단된 앱을 검토하려면 Microsoft-Windows-Windows Defender/작동 로그에서 이벤트 뷰어를 열고 이벤트 ID 1121을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-130">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="963ed-131">다음 표에는 모든 네트워크 보호 이벤트가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-131">The following table lists all network protection events.</span></span>

<span data-ttu-id="963ed-132">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="963ed-132">Event ID</span></span> | <span data-ttu-id="963ed-133">설명</span><span class="sxs-lookup"><span data-stu-id="963ed-133">Description</span></span>
-|-
 <span data-ttu-id="963ed-134">5007</span><span class="sxs-lookup"><span data-stu-id="963ed-134">5007</span></span> | <span data-ttu-id="963ed-135">설정이 변경될 때의 이벤트</span><span class="sxs-lookup"><span data-stu-id="963ed-135">Event when settings are changed</span></span>
 <span data-ttu-id="963ed-136">1121</span><span class="sxs-lookup"><span data-stu-id="963ed-136">1121</span></span> | <span data-ttu-id="963ed-137">차단 모드에서 공격 표면 감소 규칙이 발생하면 이벤트</span><span class="sxs-lookup"><span data-stu-id="963ed-137">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="963ed-138">1122</span><span class="sxs-lookup"><span data-stu-id="963ed-138">1122</span></span> | <span data-ttu-id="963ed-139">감사 모드에서 공격 표면 감소 규칙이 발생하면 이벤트</span><span class="sxs-lookup"><span data-stu-id="963ed-139">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="963ed-140">공격 표면 감소 규칙 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="963ed-140">Customize attack surface reduction rules</span></span>

<span data-ttu-id="963ed-141">평가하는 동안 각 규칙을 개별적으로 구성하거나 특정 파일 및 프로세스가 기능으로 평가되지 못하도록 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963ed-141">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="963ed-142">그룹 [정책 및](customize-attack-surface-reduction.md) MDM CSP 정책을 포함하여 관리 도구를 사용하여 기능을 구성하는 방법에 대한 자세한 내용은 공격 표면 축소 규칙 사용자 지정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="963ed-142">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="963ed-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="963ed-143">See also</span></span>

* [<span data-ttu-id="963ed-144">공격 표면 감소 규칙을 사용하여 공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="963ed-144">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="963ed-145">감사 모드를 사용하여 감사 Windows Defender</span><span class="sxs-lookup"><span data-stu-id="963ed-145">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="963ed-146">공격 표면 감소 FAQ</span><span class="sxs-lookup"><span data-stu-id="963ed-146">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
