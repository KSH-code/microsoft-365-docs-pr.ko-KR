---
title: 차단 모드에서 끝점 검색 및 응답
description: 차단 모드에서 끝점 검색 및 응답에 대해 자세히 알아보기
keywords: Microsoft Defender ATP, 차단 모드의 EDR, 수동 모드 차단
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
ms.date: 01/26/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b31e7aeb9178cb6021434319e55ddef927d7c263
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165876"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="ce00a-104">차단 모드의 끝점 검색 및 응답(EDR)</span><span class="sxs-lookup"><span data-stu-id="ce00a-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ce00a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ce00a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ce00a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ce00a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ce00a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce00a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ce00a-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ce00a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ce00a-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="ce00a-110">차단 모드의 EDR이란?</span><span class="sxs-lookup"><span data-stu-id="ce00a-110">What is EDR in block mode?</span></span>

<span data-ttu-id="ce00a-111">[차단 모드의](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 끝점 감지 및 응답(EDR)은 Microsoft Defender 바이러스 백신이 수동 모드에서 실행되는 경우에도 악성 아티팩트로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-111">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="ce00a-112">차단 모드의 EDR은 디바이스에서 감지되는 악의적인 아티팩트 또는 동작을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="ce00a-113">차단 모드의 EDR은 장면 뒤에서 작동하여 위반 후 감지된 악성 아티팩트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="ce00a-114">차단 모드의 EDR도 위협 및 [취약성 & 통합되어 있습니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="ce00a-114">EDR in block mode is also integrated with [threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="ce00a-115">조직의 보안 팀은 아직 EDR을 사용하도록 설정하지 않은 경우 차단 모드로 EDR을 설정하는 보안 권장을 받을 수 있습니다. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)</span><span class="sxs-lookup"><span data-stu-id="ce00a-115">Your organization's security team will get a [security recommendation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="차단 모드에서 EDR을 켜는 권장":::

> [!NOTE]
> <span data-ttu-id="ce00a-117">최상의 보호를 위해 끝점 **[기준에 대한 Microsoft Defender를 배포해야 합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**</span><span class="sxs-lookup"><span data-stu-id="ce00a-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="ce00a-118">감지된 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="ce00a-118">What happens when something is detected?</span></span>

<span data-ttu-id="ce00a-119">차단 모드의 EDR이 켜져 있는 경우 악의적인 아티팩트가 감지되면 끝점용 Microsoft Defender는 이 아티팩트를 차단하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="ce00a-120">검색 상태는 작업  센터 에서 완료된 작업으로 차단 또는 [방지로 표시됩니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center) </span><span class="sxs-lookup"><span data-stu-id="ce00a-120">You'll see detection status as **Blocked** or **Prevented** as completed actions in the [Action center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center).</span></span>

<span data-ttu-id="ce00a-121">다음 이미지는 차단 모드에서 EDR을 통해 검색 및 차단된 원치 않는 소프트웨어의 인스턴스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="차단 모드의 EDR에서 감지된 것":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="ce00a-123">차단 모드에서 EDR 사용</span><span class="sxs-lookup"><span data-stu-id="ce00a-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce00a-124">차단 [모드에서](#requirements-for-edr-in-block-mode) EDR을 켜기 전에 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="ce00a-125">Microsoft Defender 보안 센터()로 이동하여 [https://securitycenter.windows.com](https://securitycenter.windows.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-125">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span> 

2. <span data-ttu-id="ce00a-126">설정 **고급**  >  **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce00a-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="ce00a-127">차단 모드에서 **EDR을 켜기**</span><span class="sxs-lookup"><span data-stu-id="ce00a-127">Turn on **EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="ce00a-128">차단 모드의 EDR은 Microsoft Defender 보안 센터에서만 으로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-128">EDR in block mode can be turned on only in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="ce00a-129">레지스트리 키, Intune 또는 그룹 정책을 사용하여 차단 모드에서 EDR을 활성화 또는 비활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="ce00a-130">차단 모드의 EDR 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce00a-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="ce00a-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce00a-131">Requirement</span></span>  |<span data-ttu-id="ce00a-132">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ce00a-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="ce00a-133">사용 권한</span><span class="sxs-lookup"><span data-stu-id="ce00a-133">Permissions</span></span> |<span data-ttu-id="ce00a-134">[Azure Active Directory에](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)할당된 전역 관리자 또는 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="ce00a-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="ce00a-135">기본 [사용 권한을 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)</span><span class="sxs-lookup"><span data-stu-id="ce00a-135">See [Basic permissions](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions).</span></span> |
|<span data-ttu-id="ce00a-136">운영 체제</span><span class="sxs-lookup"><span data-stu-id="ce00a-136">Operating system</span></span>     |<span data-ttu-id="ce00a-137">다음 버전 중 하나</span><span class="sxs-lookup"><span data-stu-id="ce00a-137">One of the following versions:</span></span> <br/><span data-ttu-id="ce00a-138">- Windows 10(모든 릴리스)</span><span class="sxs-lookup"><span data-stu-id="ce00a-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="ce00a-139">- Windows Server, 버전 1803 이상</span><span class="sxs-lookup"><span data-stu-id="ce00a-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="ce00a-140">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="ce00a-140">- Windows Server 2019</span></span>         |
|<span data-ttu-id="ce00a-141">Windows E5 등록</span><span class="sxs-lookup"><span data-stu-id="ce00a-141">Windows E5 enrollment</span></span>     |<span data-ttu-id="ce00a-142">Windows E5는 다음 구독에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-142">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="ce00a-143">- Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ce00a-143">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="ce00a-144">- Identity & Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="ce00a-144">- Microsoft 365 E3 together with the Identity & Threat Protection offering</span></span> <br/><br/><span data-ttu-id="ce00a-145">각 [계획의](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) 구성 요소 및 [기능을 참조합니다.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="ce00a-145">See [Components](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="ce00a-146">Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="ce00a-146">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="ce00a-147">Microsoft Defender 바이러스 백신은 활성 모드 또는 수동 모드로 설치 및 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-147">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="ce00a-148">비 Microsoft 바이러스 백신 솔루션과 함께 Microsoft Defender 바이러스 백신을 사용할 수 있습니다. [Microsoft Defender 바이러스 백신이 활성 또는 수동 모드에 있는지 확인](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="ce00a-148">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="ce00a-149">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="ce00a-149">Cloud-delivered protection</span></span> |<span data-ttu-id="ce00a-150">클라우드 제공 보호를 사용하도록 Microsoft Defender 바이러스 백신이 [구성되어 있는지 확인합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="ce00a-150">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus).</span></span> |
|<span data-ttu-id="ce00a-151">Microsoft Defender 바이러스 백신 맬웨어 방지 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ce00a-151">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="ce00a-152">클라이언트를 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-152">Make sure your client is up to date.</span></span> <span data-ttu-id="ce00a-153">PowerShell을 사용하여 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet을 관리자 권한으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-153">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="ce00a-154">**AMProductVersion** 줄에 **4.18.2001.10 이상이** 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-154">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="ce00a-155">Microsoft Defender 바이러스 백신 엔진</span><span class="sxs-lookup"><span data-stu-id="ce00a-155">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="ce00a-156">엔진을 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-156">Make sure your engine is up to date.</span></span> <span data-ttu-id="ce00a-157">PowerShell을 사용하여 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet을 관리자 권한으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-157">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="ce00a-158">**AMEngineVersion** 줄에 **1.1.16700.2 이상이** 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-158">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="ce00a-159">최상의 보호 값을 얻기 위해 정기적인 업데이트 및 필수 기능을 받도록 바이러스 백신 솔루션이 구성되어 있는지, 그리고 제외가 구성되어 [있는지 확인합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="ce00a-159">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="ce00a-160">차단 모드의 EDR은 Microsoft Defender 바이러스 백신에 대해 정의된 제외를 존중합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-160">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="ce00a-161">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="ce00a-161">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="ce00a-162">장치에서 Microsoft Defender 바이러스 백신을 실행하고 있는 경우에도 차단 모드로 EDR을 켜야 하나요?</span><span class="sxs-lookup"><span data-stu-id="ce00a-162">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="ce00a-163">Microsoft Defender 바이러스 백신이 수동 모드로 실행 중인지 활성 모드에서 실행 중인지 여부에 따라 EDR을 차단 모드로 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-163">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="ce00a-164">차단 모드의 EDR은 끝점용 Microsoft Defender를 사용하여 또 다른 방어 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-164">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ce00a-165">이를 통해 끝점에 대한 Defender가 위반 후 행동 EDR 검색을 기반으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-165">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="ce00a-166">차단 모드의 EDR은 사용자의 바이러스 백신 보호에 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="ce00a-166">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="ce00a-167">차단 모드의 EDR은 사용자의 장치에서 실행되는 타사 바이러스 백신 보호에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-167">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="ce00a-168">기본 바이러스 백신 솔루션이 누락되거나 위반 후 검색이 있는 경우 차단 모드의 EDR이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-168">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="ce00a-169">차단 모드의 EDR은 수동 모드에서 [Microsoft Defender 바이러스](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)백신과 마찬가지로 작동하며, 검색된 악성 아티팩트 또는 동작도 차단하고 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-169">EDR in block mode works just like [Microsoft Defender Antivirus in passive mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state), except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span> 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="ce00a-170">Microsoft Defender 바이러스 백신을 최신 상태로 유지해야 하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ce00a-170">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="ce00a-171">Microsoft Defender 바이러스 백신은 악의적인 항목을 감지하고 수정하기 때문에 최신 상태로 유지하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-171">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="ce00a-172">차단 모드의 EDR이 효과적이기 위해 최신 장치 학습 모델, 동작 감지 및추론을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-172">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="ce00a-173">기능의 [끝점용 Defender](https://docs.microsoft.com/windows/security/threat-protection) 스택은 통합된 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-173">The [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="ce00a-174">최상의 보호 값을 얻기 위해 Microsoft Defender 바이러스 백신을 최신 상태로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-174">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span>  

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="ce00a-175">클라우드 보호가 필요한 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ce00a-175">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="ce00a-176">디바이스에서 기능을 켜는 데 클라우드 보호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-176">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="ce00a-177">클라우드 보호를 [통해 Endpoint용 Defender는](https://docs.microsoft.com/windows/security/threat-protection) 동작 및 장치 학습 모델과 함께 보안 인텔리전스의 다양한 깊이와 깊이에 따라 최신 및 최고의 보호를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-177">Cloud protection allows [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="ce00a-178">Microsoft Defender 바이러스 백신을 수동 모드로 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="ce00a-178">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="ce00a-179">Microsoft Defender 바이러스 백신 사용 및 수동 모드에 [있는지 확인을 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="ce00a-179">See [Enable Microsoft Defender Antivirus and confirm it's in passive mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="ce00a-180">Microsoft Defender 바이러스 백신이 활성 또는 수동 모드에 있는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="ce00a-180">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="ce00a-181">Microsoft Defender 바이러스 백신이 활성 모드 또는 수동 모드에서 실행 중인지 확인하려면 Windows를 실행하는 장치에서 명령 프롬프트 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-181">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

#### <a name="use-powershell"></a><span data-ttu-id="ce00a-182">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="ce00a-182">Use PowerShell</span></span>

1. <span data-ttu-id="ce00a-183">시작 메뉴를 선택하고 를 입력한 다음 결과에서 Windows PowerShell `PowerShell` 를 니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-183">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="ce00a-184">`Get-MpComputerStatus`(을)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-184">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="ce00a-185">결과 목록의 **AMRunningMode** 행에서 다음 값 중 하나를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-185">In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span>   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

<span data-ttu-id="ce00a-186">자세한 내용은 [Get-MpComputerStatus 를 참조합니다.](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)</span><span class="sxs-lookup"><span data-stu-id="ce00a-186">To learn more, see [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).</span></span>

#### <a name="use-command-prompt"></a><span data-ttu-id="ce00a-187">명령 프롬프트 사용</span><span class="sxs-lookup"><span data-stu-id="ce00a-187">Use Command Prompt</span></span>

1. <span data-ttu-id="ce00a-188">시작 메뉴를 선택하고 를 입력한 다음 `Command Prompt` 결과에서 Windows 명령 프롬프트를 니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-188">Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span>

2. <span data-ttu-id="ce00a-189">`sc query windefend`(을)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-189">Type `sc query windefend`.</span></span>

3. <span data-ttu-id="ce00a-190">결과 목록의 **STATE** 행에서 서비스가 실행 중인지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ce00a-190">In the list of results, in the **STATE** row, confirm that the service is running.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce00a-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce00a-191">See also</span></span>

- [<span data-ttu-id="ce00a-192">기술 커뮤니티 블로그: 차단 모드에서 EDR 소개: 추적에서 공격 중지</span><span class="sxs-lookup"><span data-stu-id="ce00a-192">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="ce00a-193">동작 차단 및 포함</span><span class="sxs-lookup"><span data-stu-id="ce00a-193">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)
- [<span data-ttu-id="ce00a-194">함께 사용: Microsoft Defender 바이러스 백신 및 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ce00a-194">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

