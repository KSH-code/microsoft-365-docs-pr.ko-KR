---
title: 차단 모드에서 끝점 검색 및 응답
description: 차단 모드에서 끝점 검색 및 응답에 대해 자세히 알아보기
keywords: 끝점용 Microsoft Defender, mde, EDR 모드, 수동 모드 차단
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
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b0fe1da56c34cd0a79e1a41dba2fcb7a79c5a9f6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259574"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="dd599-104">차단 모드에서 끝점 EDR(응답)</span><span class="sxs-lookup"><span data-stu-id="dd599-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd599-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dd599-105">**Applies to:**</span></span>
- [<span data-ttu-id="dd599-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dd599-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dd599-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd599-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="dd599-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="dd599-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dd599-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="dd599-110">차단 EDR 어떤 것이 있나요?</span><span class="sxs-lookup"><span data-stu-id="dd599-110">What is EDR in block mode?</span></span>

<span data-ttu-id="dd599-111">[차단 모드의](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 끝점 감지 및 응답(EDR)은 수동 모드에서 실행되는 경우에도 Microsoft Defender 바이러스 백신 아티팩트로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-111">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="dd599-112">이 기능을 EDR 차단 모드에서는 디바이스에서 감지되는 악의적인 아티팩트 또는 동작을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="dd599-113">EDR 차단 모드에서는 장면 뒤에서 작동하여 위반 후 감지된 악성 아티팩트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="dd599-114">EDR 모드는 위협 [요소와 & 취약성 관리.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="dd599-114">EDR in block mode is also integrated with [threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="dd599-115">조직의 보안 팀은 아직 사용하도록 [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 설정되지 않은 경우 EDR 모드로 전환하는 보안 권장을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-115">Your organization's security team will get a [security recommendation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="차단 모드에서 EDR 설정하는 권장":::

> [!NOTE]
> <span data-ttu-id="dd599-117">최상의 보호를 위해 끝점 **[기준에 대한 Microsoft Defender를 배포해야 합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**</span><span class="sxs-lookup"><span data-stu-id="dd599-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="dd599-118">감지된 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="dd599-118">What happens when something is detected?</span></span>

<span data-ttu-id="dd599-119">차단 EDR 설정되어 있으며 악의적인 아티팩트가 감지되면 끝점용 Microsoft Defender는 이 아티팩트를 차단하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="dd599-120">검색 상태는 작업  센터 에서 완료된 작업으로 차단 또는 [방지로 표시됩니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center) </span><span class="sxs-lookup"><span data-stu-id="dd599-120">You'll see detection status as **Blocked** or **Prevented** as completed actions in the [Action center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center).</span></span>

<span data-ttu-id="dd599-121">다음 이미지는 차단 모드에서 검색되고 차단된 원치 않는 소프트웨어의 EDR 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR 모드로 검색된 것":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="dd599-123">차단 EDR 사용</span><span class="sxs-lookup"><span data-stu-id="dd599-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd599-124">차단 [모드로 전환하기](#requirements-for-edr-in-block-mode) 전에 EDR 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="dd599-125">Microsoft Defender 보안 센터 [https://securitycenter.windows.com](https://securitycenter.windows.com) ()로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-125">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span> 

2. <span data-ttu-id="dd599-126">고급 **설정**  >  **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd599-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="dd599-127">차단 모드에서 **EDR 을 켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd599-127">Turn on **EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="dd599-128">EDR 모드로 설정하면 차단 모드에서만 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="dd599-128">EDR in block mode can be turned on only in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="dd599-129">레지스트리 키, Intune 또는 그룹 정책을 사용하여 차단 모드에서 레지스트리 EDR 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="dd599-130">차단 모드의 EDR 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd599-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="dd599-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd599-131">Requirement</span></span>  |<span data-ttu-id="dd599-132">세부 정보</span><span class="sxs-lookup"><span data-stu-id="dd599-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="dd599-133">권한</span><span class="sxs-lookup"><span data-stu-id="dd599-133">Permissions</span></span> |<span data-ttu-id="dd599-134">에서 할당된 전역 관리자 [또는 보안 Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="dd599-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="dd599-135">기본 [사용 권한을 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)</span><span class="sxs-lookup"><span data-stu-id="dd599-135">See [Basic permissions](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions).</span></span> |
|<span data-ttu-id="dd599-136">운영 체제</span><span class="sxs-lookup"><span data-stu-id="dd599-136">Operating system</span></span>     |<span data-ttu-id="dd599-137">다음 버전 중 하나</span><span class="sxs-lookup"><span data-stu-id="dd599-137">One of the following versions:</span></span> <br/><span data-ttu-id="dd599-138">- Windows 10(모든 릴리스)</span><span class="sxs-lookup"><span data-stu-id="dd599-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="dd599-139">- Windows Server, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="dd599-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="dd599-140">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dd599-140">- Windows Server 2019</span></span>  <p><span data-ttu-id="dd599-141">**참고:** EDR 차단 모드에서는 지원되지 Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="dd599-141">**NOTE**: EDR in block mode is not supported on Windows Server 2016.</span></span>       |
|<span data-ttu-id="dd599-142">Windows E5 등록</span><span class="sxs-lookup"><span data-stu-id="dd599-142">Windows E5 enrollment</span></span>     |<span data-ttu-id="dd599-143">Windows E5는 다음 구독에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-143">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="dd599-144">- Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dd599-144">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="dd599-145">- Microsoft 365 E3 Id 및 위협 방지 & 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-145">- Microsoft 365 E3 together with the Identity & Threat Protection offering</span></span> <br/><br/><span data-ttu-id="dd599-146">각 [계획의](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) 구성 요소 및 [기능을 참조합니다.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="dd599-146">See [Components](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="dd599-147">Windows Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="dd599-147">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="dd599-148">Microsoft Defender 바이러스 백신 모드 또는 수동 모드에서 설치 및 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-148">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="dd599-149">Microsoft가 아닌 바이러스 백신 Microsoft Defender 바이러스 백신 함께 사용할 수 있습니다. [활성 Microsoft Defender 바이러스 백신 수동 모드에 있는지 확인](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="dd599-149">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="dd599-150">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="dd599-150">Cloud-delivered protection</span></span> |<span data-ttu-id="dd599-151">클라우드 제공 Microsoft Defender 바이러스 백신 사용하도록 구성해야 [합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="dd599-151">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus).</span></span> |
|<span data-ttu-id="dd599-152">Microsoft Defender 바이러스 백신 맬웨어 방지 클라이언트</span><span class="sxs-lookup"><span data-stu-id="dd599-152">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="dd599-153">클라이언트를 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-153">Make sure your client is up to date.</span></span> <span data-ttu-id="dd599-154">PowerShell을 사용하여 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet을 관리자 권한으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-154">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="dd599-155">**AMProductVersion** 줄에 **4.18.2001.10 이상이** 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-155">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="dd599-156">Microsoft Defender 바이러스 백신 엔진</span><span class="sxs-lookup"><span data-stu-id="dd599-156">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="dd599-157">엔진을 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-157">Make sure your engine is up to date.</span></span> <span data-ttu-id="dd599-158">PowerShell을 사용하여 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet을 관리자 권한으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-158">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="dd599-159">**AMEngineVersion** 줄에 **1.1.16700.2 이상이** 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-159">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="dd599-160">최상의 보호 값을 얻기 위해 정기적인 업데이트 및 필수 기능을 받도록 바이러스 백신 솔루션이 구성되어 있는지, 그리고 제외가 구성되어 [있는지 확인합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="dd599-160">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="dd599-161">EDR 모드는 차단 모드에 대해 정의된 제외를 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="dd599-161">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="dd599-162">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="dd599-162">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="dd599-163">장치에서 실행 중인 EDR 차단 모드에서 Microsoft Defender 바이러스 백신 설정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dd599-163">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="dd599-164">수동 모드 또는 EDR 모드에 Microsoft Defender 바이러스 백신 차단 모드로 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-164">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="dd599-165">EDR 모드에서는 끝점용 Microsoft Defender를 사용하여 또 다른 방어 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-165">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="dd599-166">이를 통해 끝점에 대한 Defender는 위반 후 행동 및 검색을 기반으로 EDR 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-166">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="dd599-167">차단 EDR 사용자의 바이러스 백신 보호에 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="dd599-167">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="dd599-168">EDR 모드에서는 사용자의 장치에서 실행되는 타사 바이러스 백신 보호에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-168">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="dd599-169">EDR 바이러스 백신 솔루션이 누락되거나 위반 후 검색이 있는 경우 차단 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-169">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="dd599-170">EDR 모드는 수동 Microsoft Defender 바이러스 백신 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)마찬가지로 작동하며, 검색된 악의적인 아티팩트 또는 동작도 차단하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-170">EDR in block mode works just like [Microsoft Defender Antivirus in passive mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state), except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span> 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="dd599-171">최신으로 유지해야 하는 Microsoft Defender 바이러스 백신 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="dd599-171">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="dd599-172">악의적인 Microsoft Defender 바이러스 백신 감지하고 수정하기 때문에 이를 최신으로 유지하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-172">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="dd599-173">블록 EDR 효과를 위해 최신 장치 학습 모델, 동작 감지 및추론을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-173">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="dd599-174">기능의 [끝점용 Defender](https://docs.microsoft.com/windows/security/threat-protection) 스택은 통합된 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-174">The [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="dd599-175">최상의 보호 값을 얻기 위해 최신 Microsoft Defender 바이러스 백신 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-175">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span>  

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="dd599-176">클라우드 보호가 필요한 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="dd599-176">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="dd599-177">디바이스에서 기능을 켜는 데 클라우드 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-177">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="dd599-178">클라우드 보호를 [통해 Endpoint용 Defender는](https://docs.microsoft.com/windows/security/threat-protection) 동작 및 장치 학습 모델과 함께 보안 인텔리전스의 다양한 깊이와 깊이에 따라 최신 및 최고의 보호를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-178">Cloud protection allows [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="dd599-179">수동 모드로 Microsoft Defender 바이러스 백신 어떻게 설정하나요?</span><span class="sxs-lookup"><span data-stu-id="dd599-179">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="dd599-180">사용 Microsoft Defender 바이러스 백신 수동 모드로 설정 [및 확인을 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="dd599-180">See [Enable Microsoft Defender Antivirus and confirm it's in passive mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="dd599-181">활성 모드 또는 Microsoft Defender 바이러스 백신 모드에 있는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="dd599-181">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="dd599-182">활성 모드 Microsoft Defender 바이러스 백신 수동 모드로 실행 중인지 확인하려면 명령 프롬프트 또는 PowerShell을 실행 중인 장치에서 명령 프롬프트를 Windows.</span><span class="sxs-lookup"><span data-stu-id="dd599-182">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

#### <a name="use-powershell"></a><span data-ttu-id="dd599-183">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="dd599-183">Use PowerShell</span></span>

1. <span data-ttu-id="dd599-184">시작 메뉴를 선택하고 를 입력한 다음 결과에서 Windows PowerShell `PowerShell` 을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-184">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="dd599-185">`Get-MpComputerStatus`(을)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-185">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="dd599-186">결과 목록의 **AMRunningMode** 행에서 다음 값 중 하나를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-186">In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span>
   - <span data-ttu-id="dd599-187">`Normal` - Defender 서비스가 정상적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-187">`Normal` - Defender service running normally.</span></span> <span data-ttu-id="dd599-188">특수 모드는 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-188">No special modes are enabled.</span></span>
   - <span data-ttu-id="dd599-189">`Passive Mode`- 조직에서 비 Microsoft 바이러스 백신/맬웨어 방지 솔루션과 함께 끝점용 Microsoft Defender를 사용하는 경우 자동으로 Microsoft Defender 바이러스 백신 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-189">`Passive Mode` - If your organization is using Microsoft Defender for Endpoint together with a non-Microsoft antivirus/antimalware solution, then Microsoft Defender Antivirus automatically goes into passive mode.</span></span> <span data-ttu-id="dd599-190">(실시간 보호 및 위협은 에 의해 해결되지 Microsoft Defender 바이러스 백신.)</span><span class="sxs-lookup"><span data-stu-id="dd599-190">(Real-time protection and threats are not remediated by Microsoft Defender Antivirus.)</span></span>
   - <span data-ttu-id="dd599-191">`SxS Passive Mode`- 수동 모드와 유사하지만 제한된 주기적 검색을 설정하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-191">`SxS Passive Mode`- Similar to passive mode, but with the option to turn on limited periodic scanning.</span></span>
   
<span data-ttu-id="dd599-192">자세한 내용은 [Get-MpComputerStatus 를 참조합니다.](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)</span><span class="sxs-lookup"><span data-stu-id="dd599-192">To learn more, see [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).</span></span>

#### <a name="use-command-prompt"></a><span data-ttu-id="dd599-193">명령 프롬프트 사용</span><span class="sxs-lookup"><span data-stu-id="dd599-193">Use Command Prompt</span></span>

1. <span data-ttu-id="dd599-194">시작 메뉴를 선택하고 를 입력한 다음 결과에서 명령 `Command Prompt` Windows 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-194">Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span>

2. <span data-ttu-id="dd599-195">`sc query windefend`(을)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-195">Type `sc query windefend`.</span></span>

3. <span data-ttu-id="dd599-196">결과 목록의 **STATE** 행에서 서비스가 실행 중인지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-196">In the list of results, in the **STATE** row, confirm that the service is running.</span></span>

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="dd599-197">차단 모드에서 EDR 데 얼마나 걸릴까요?</span><span class="sxs-lookup"><span data-stu-id="dd599-197">How much time does it take for EDR in block mode to be disabled?</span></span>

<span data-ttu-id="dd599-198">차단 모드에서 EDR 사용하지 않도록 선택한 경우 시스템에서 이 기능을 사용하지 않도록 설정하는 데 최대 30분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd599-198">If you chose to disable EDR in block mode it can take up to 30 minutes for the system to disable this capability.</span></span>

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a><span data-ttu-id="dd599-199">지원 EDR 차단 모드에서 지원 Windows Server 2016하나요?</span><span class="sxs-lookup"><span data-stu-id="dd599-199">Is EDR in block mode supported on Windows Server 2016?</span></span>

<span data-ttu-id="dd599-200">아니요.</span><span class="sxs-lookup"><span data-stu-id="dd599-200">No.</span></span> <span data-ttu-id="dd599-201">EDR 모드로 설정하면 다음과 같은 버전의 차단 모드가 Windows.</span><span class="sxs-lookup"><span data-stu-id="dd599-201">EDR in block mode is supported of the following versions of Windows:</span></span>

- <span data-ttu-id="dd599-202">Windows 10(모든 릴리스)</span><span class="sxs-lookup"><span data-stu-id="dd599-202">Windows 10 (all releases)</span></span>
- <span data-ttu-id="dd599-203">Windows 서버, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="dd599-203">Windows Server, version 1803 or newer</span></span> 
- <span data-ttu-id="dd599-204">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dd599-204">Windows Server 2019</span></span> 

## <a name="see-also"></a><span data-ttu-id="dd599-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd599-205">See also</span></span>

- [<span data-ttu-id="dd599-206">기술 Community 블로그: EDR 모드로 전환 소개: 추적에서 공격 중지</span><span class="sxs-lookup"><span data-stu-id="dd599-206">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="dd599-207">동작 차단 및 제약</span><span class="sxs-lookup"><span data-stu-id="dd599-207">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)
- [<span data-ttu-id="dd599-208">함께 활용: Microsoft Defender 바이러스 백신 및 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dd599-208">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

