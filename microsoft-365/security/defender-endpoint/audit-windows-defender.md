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
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985099"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fef3e-104">끝점용 Microsoft Defender의 공격 표면 감소 테스트</span><span class="sxs-lookup"><span data-stu-id="fef3e-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fef3e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fef3e-105">**Applies to:**</span></span>

- [<span data-ttu-id="fef3e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fef3e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fef3e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fef3e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fef3e-108">조직의 보안 팀의 일부로 감사 모드에서 실행하도록 공격 표면 감소 기능을 구성하여 작동 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-108">As part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work.</span></span> <span data-ttu-id="fef3e-109">감사 모드에서는 다음을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-109">In audit mode, you can enable:</span></span>

- <span data-ttu-id="fef3e-110">공격 노출 영역 축소 규칙</span><span class="sxs-lookup"><span data-stu-id="fef3e-110">Attack surface reduction rules</span></span>
- <span data-ttu-id="fef3e-111">악용 방지</span><span class="sxs-lookup"><span data-stu-id="fef3e-111">Exploit protection</span></span>
- <span data-ttu-id="fef3e-112">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="fef3e-112">Network protection</span></span>
- <span data-ttu-id="fef3e-113">감사 모드에서 제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="fef3e-113">And controlled folder access in audit mode</span></span>

<span data-ttu-id="fef3e-114">감사 모드를 사용하면 기능을 사용하도록  설정한 경우 어떤 일이 일어나는지 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-114">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="fef3e-115">기능의 작동 방법을 테스트할 때 감사 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-115">You can enable audit mode when testing how the features will work.</span></span> <span data-ttu-id="fef3e-116">이렇게 하면 업무용 앱이 영향을 받지 않는지 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-116">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="fef3e-117">또한 특정 기간 동안 의심스러운 파일 수정 시도의 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-117">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="fef3e-118">이 기능은 앱, 스크립트 또는 파일이 수정되는 것을 차단하거나 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-118">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="fef3e-119">그러나 Windows 로그는 기능이 완전히 활성화된 것 같은 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-119">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="fef3e-120">감사 모드를 사용하면 이벤트 로그를 검토하여 활성화된 기능의 영향을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-120">With audit mode, you can review the event log to see what affect the feature would have had if it was enabled.</span></span>

<span data-ttu-id="fef3e-121">감사된 항목을 찾으면 응용 프로그램 및 서비스 Microsoft Windows  >    >    >  **Windows Defender**  >  **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fef3e-121">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="fef3e-122">끝점용 Defender를 사용하여 각 이벤트, 특히 공격 표면 감소 규칙을 조사하는 데 더 많은 세부 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-122">Use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="fef3e-123">Endpoint용 Defender 콘솔을 사용하면 경고 타임라인 및 조사 시나리오의 일부로 문제를 [조사할 수 있습니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="fef3e-123">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="fef3e-124">그룹 정책, PowerShell 및 CSP(구성 서비스 공급자)를 사용하여 감사 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-124">You can enable audit mode using Group Policy, PowerShell, and configuration service providers (CSPs).</span></span>

> [!TIP]
> <span data-ttu-id="fef3e-125">또한 Windows Defender Testground 웹 사이트를 방문하여 [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 작동을 확인하고 작동 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-125">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="fef3e-126">감사 옵션</span><span class="sxs-lookup"><span data-stu-id="fef3e-126">Audit options</span></span> | <span data-ttu-id="fef3e-127">감사 모드를 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="fef3e-127">How to enable audit mode</span></span> | <span data-ttu-id="fef3e-128">이벤트를 보는 방법</span><span class="sxs-lookup"><span data-stu-id="fef3e-128">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="fef3e-129">감사는 모든 이벤트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-129">Audit applies to all events</span></span> | [<span data-ttu-id="fef3e-130">제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="fef3e-130">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="fef3e-131">제어된 폴더 액세스 이벤트</span><span class="sxs-lookup"><span data-stu-id="fef3e-131">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="fef3e-132">감사는 개별 규칙에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-132">Audit applies to individual rules</span></span> | [<span data-ttu-id="fef3e-133">공격 표면 감소 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="fef3e-133">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="fef3e-134">공격 표면 감소 규칙 이벤트</span><span class="sxs-lookup"><span data-stu-id="fef3e-134">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="fef3e-135">감사는 모든 이벤트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-135">Audit applies to all events</span></span> | [<span data-ttu-id="fef3e-136">네트워크 보호 사용</span><span class="sxs-lookup"><span data-stu-id="fef3e-136">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="fef3e-137">네트워크 보호 이벤트</span><span class="sxs-lookup"><span data-stu-id="fef3e-137">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="fef3e-138">감사는 개별 완화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef3e-138">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="fef3e-139">악용 방지 사용</span><span class="sxs-lookup"><span data-stu-id="fef3e-139">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="fef3e-140">Exploit Protection 이벤트</span><span class="sxs-lookup"><span data-stu-id="fef3e-140">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
