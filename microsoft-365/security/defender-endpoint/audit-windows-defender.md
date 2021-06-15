---
title: 감사 모드에서 끝점용 Microsoft Defender 기능이 어떻게 작동 하는지 테스트
description: 감사 모드를 사용하면 끝점용 Microsoft Defender가 디바이스를 사용하도록 설정한 경우 어떻게 보호하는지 볼 수 있습니다.
keywords: exploit guard, 감사, 감사, 모드, 사용, 비활성화, 테스트, 데모, 평가, 랩
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925662"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="133c7-104">끝점용 Microsoft Defender의 공격 표면 감소 테스트</span><span class="sxs-lookup"><span data-stu-id="133c7-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="133c7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="133c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="133c7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="133c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="133c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="133c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="133c7-108">조직의 보안 팀에 참여하는 경우 감사 모드에서 실행하도록 공격 표면 감소 기능을 구성하여 조직에서 어떻게 작동할지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="133c7-109">특히 감사 모드에서 공격 표면 감소 규칙, 악용 방지, 네트워크 보호 및 제어된 폴더 액세스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="133c7-110">감사 모드를 사용하면 기능을 사용하도록  설정한 경우 어떤 일이 일어나는지 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="133c7-111">조직에서 기능이 어떻게 작동할지 테스트할 때 감사 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="133c7-112">이렇게 하면 업무용 앱이 영향을 받지 않는지 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="133c7-113">또한 특정 기간 동안 의심스러운 파일 수정 시도의 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="133c7-114">이 기능은 앱, 스크립트 또는 파일이 수정되는 것을 차단하거나 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="133c7-115">그러나 Windows 로그는 기능이 완전히 활성화된 것 같은 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="133c7-116">감사 모드를 사용하면 이벤트 로그를 검토하여 기능이 활성화된 경우 기능에 미칠 영향을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="133c7-117">감사된 항목을 찾으면 응용 프로그램 및 서비스 Microsoft Windows  >    >    >  **Windows Defender**  >  **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="133c7-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="133c7-118">끝점용 Defender를 사용하여 각 이벤트, 특히 공격 표면 감소 규칙을 조사하는 데 더 많은 세부 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="133c7-119">Endpoint용 Defender 콘솔을 사용하면 경고 타임라인 및 조사 시나리오의 일부로 문제를 [조사할 수 있습니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="133c7-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="133c7-120">그룹 정책, PowerShell 및 CSP(구성 서비스 공급자)를 사용하여 감사 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="133c7-121">또한 Windows Defender Testground 웹 사이트를 방문하여 [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 작동을 확인하고 작동 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="133c7-122">감사 옵션</span><span class="sxs-lookup"><span data-stu-id="133c7-122">Audit options</span></span> | <span data-ttu-id="133c7-123">감사 모드를 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="133c7-123">How to enable audit mode</span></span> | <span data-ttu-id="133c7-124">이벤트를 보는 방법</span><span class="sxs-lookup"><span data-stu-id="133c7-124">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="133c7-125">감사는 모든 이벤트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-125">Audit applies to all events</span></span> | [<span data-ttu-id="133c7-126">제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="133c7-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="133c7-127">제어된 폴더 액세스 이벤트</span><span class="sxs-lookup"><span data-stu-id="133c7-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="133c7-128">감사는 개별 규칙에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="133c7-129">공격 표면 감소 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="133c7-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="133c7-130">공격 표면 감소 규칙 이벤트</span><span class="sxs-lookup"><span data-stu-id="133c7-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="133c7-131">감사는 모든 이벤트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-131">Audit applies to all events</span></span> | [<span data-ttu-id="133c7-132">네트워크 보호 사용</span><span class="sxs-lookup"><span data-stu-id="133c7-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="133c7-133">네트워크 보호 이벤트</span><span class="sxs-lookup"><span data-stu-id="133c7-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="133c7-134">감사는 개별 완화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="133c7-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="133c7-135">악용 방지 사용</span><span class="sxs-lookup"><span data-stu-id="133c7-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="133c7-136">Exploit Protection 이벤트</span><span class="sxs-lookup"><span data-stu-id="133c7-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


