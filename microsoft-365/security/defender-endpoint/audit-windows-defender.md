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
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570975"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a><span data-ttu-id="52a48-104">감사 모드에서 끝점용 Microsoft Defender 기능이 어떻게 작동 하는지 테스트</span><span class="sxs-lookup"><span data-stu-id="52a48-104">Test how Microsoft Defender for Endpoint features work in audit mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="52a48-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="52a48-105">**Applies to:**</span></span>
- <span data-ttu-id="52a48-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="52a48-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>
- [<span data-ttu-id="52a48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52a48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="52a48-108">감사 모드에서 공격 표면 감소 규칙, 악용 보호, 네트워크 보호 및 제어된 폴더 액세스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-108">You can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="52a48-109">감사 모드를 사용하면 기능을 사용하도록  설정한 경우 어떤 일이 일어나는지 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-109">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="52a48-110">조직에서 기능이 어떻게 작동할지 테스트할 때 감사 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-110">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="52a48-111">이렇게 하면 업무용 앱이 영향을 받지 않는지 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-111">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="52a48-112">또한 특정 기간 동안 의심스러운 파일 수정 시도의 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-112">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="52a48-113">이 기능은 앱, 스크립트 또는 파일이 수정되는 것을 차단하거나 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-113">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="52a48-114">그러나 Windows 이벤트 로그는 기능이 완전히 활성화된 것 같은 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-114">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="52a48-115">감사 모드를 사용하면 이벤트 로그를 검토하여 기능이 활성화된 경우 기능에 미칠 영향을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-115">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="52a48-116">감사된 항목을 찾으면 Applications **and Services**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="52a48-116">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="52a48-117">끝점용 Defender를 사용하여 각 이벤트, 특히 공격 표면 감소 규칙을 조사하는 데 더 많은 세부 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-117">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="52a48-118">Endpoint용 Defender 콘솔을 사용하면 경고 타임라인 및 조사 시나리오의 일부로 문제를 [조사할 수 있습니다.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="52a48-118">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="52a48-119">그룹 정책, PowerShell 및 CSP(구성 서비스 공급자)를 사용하여 감사 모드를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-119">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="52a48-120">또한 Windows Defender Testground 웹 사이트를 방문하여 [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 작동을 확인하고 작동 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-120">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

 <span data-ttu-id="52a48-121">**감사 옵션**</span><span class="sxs-lookup"><span data-stu-id="52a48-121">**Audit options**</span></span> | <span data-ttu-id="52a48-122">**감사 모드를 사용하도록 설정하는 방법**</span><span class="sxs-lookup"><span data-stu-id="52a48-122">**How to enable audit mode**</span></span> | <span data-ttu-id="52a48-123">**이벤트를 보는 방법**</span><span class="sxs-lookup"><span data-stu-id="52a48-123">**How to view events**</span></span>
|---------|---------|---------|
| <span data-ttu-id="52a48-124">감사는 모든 이벤트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-124">Audit applies to all events</span></span> | [<span data-ttu-id="52a48-125">제어된 폴더 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="52a48-125">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="52a48-126">제어된 폴더 액세스 이벤트</span><span class="sxs-lookup"><span data-stu-id="52a48-126">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="52a48-127">감사는 개별 규칙에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-127">Audit applies to individual rules</span></span> | [<span data-ttu-id="52a48-128">공격 표면 감소 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="52a48-128">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="52a48-129">공격 표면 감소 규칙 이벤트</span><span class="sxs-lookup"><span data-stu-id="52a48-129">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="52a48-130">감사는 모든 이벤트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-130">Audit applies to all events</span></span> | [<span data-ttu-id="52a48-131">네트워크 보호 사용</span><span class="sxs-lookup"><span data-stu-id="52a48-131">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="52a48-132">네트워크 보호 이벤트</span><span class="sxs-lookup"><span data-stu-id="52a48-132">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="52a48-133">감사는 개별 완화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52a48-133">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="52a48-134">악용 방지 사용</span><span class="sxs-lookup"><span data-stu-id="52a48-134">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="52a48-135">Exploit Protection 이벤트</span><span class="sxs-lookup"><span data-stu-id="52a48-135">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a><span data-ttu-id="52a48-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="52a48-136">Related topics</span></span>

* [<span data-ttu-id="52a48-137">악용으로부터 장치 보호</span><span class="sxs-lookup"><span data-stu-id="52a48-137">Protect devices from exploits</span></span>](exploit-protection.md)
* [<span data-ttu-id="52a48-138">공격 표면 감소 규칙을 사용하여 공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="52a48-138">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="52a48-139">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="52a48-139">Protect your network</span></span>](network-protection.md)
* [<span data-ttu-id="52a48-140">중요한 폴더 보호</span><span class="sxs-lookup"><span data-stu-id="52a48-140">Protect important folders</span></span>](controlled-folders.md)
