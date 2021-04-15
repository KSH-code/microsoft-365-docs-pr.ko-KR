---
title: Microsoft Defender 바이러스 백신을 통해 잠재적으로 원치 않는 응용 프로그램 차단
description: 잠재적으로 원치 않는 응용 프로그램(PUA) 바이러스 백신 기능을 사용하도록 설정하여 애드웨어와 같은 원치 않는 소프트웨어를 차단합니다.
keywords: pua, 사용, 원치 않는 소프트웨어, 원치 않는 앱, 애드웨어, 브라우저 도구 모음, 검색, 차단, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 20d4767f9813b741c55109d617f78302feaa0f7e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765026"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="0beac-104">잠재적으로 원치 않는 응용 프로그램 검색 및 차단</span><span class="sxs-lookup"><span data-stu-id="0beac-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0beac-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0beac-105">**Applies to:**</span></span>

- <span data-ttu-id="0beac-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="0beac-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>
- [<span data-ttu-id="0beac-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0beac-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="0beac-108">PUA(잠재적으로 원치 않는 응용 프로그램)는 컴퓨터의 실행 속도가 느려지거나 예기치 않은 광고를 표시하거나, 최악의 경우 예기치 않게 또는 원치 않는 다른 소프트웨어를 설치할 수 있는 소프트웨어 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="0beac-109">기본적으로 Windows 10(버전 2004 이상)에서 Microsoft Defender 바이러스 백신은 엔터프라이즈(E5) 장치에 대해 PUA로 간주되는 앱을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="0beac-110">잠재적으로 원치 않는 응용 프로그램(PUA)은 바이러스, 맬웨어 또는 기타 유형의 위협으로 간주되지 않지만 끝점 성능이나 사용에 부정적인 영향을 주는 끝점에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="0beac-111">_PUA는_ 특정 종류의 원치 않은 동작으로 인해 끝점용 Microsoft Defender에서 평가한 신뢰도가 낮은 응용 프로그램을 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="0beac-112">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-112">Here are some examples:</span></span>

- <span data-ttu-id="0beac-113">**웹 페이지로** 광고를 삽입하는 소프트웨어를 포함하여 광고 또는 프로모션을 표시하는 광고 소프트웨어.</span><span class="sxs-lookup"><span data-stu-id="0beac-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="0beac-114">**동일한 엔터티가** 디지털 서명하지 않은 다른 소프트웨어를 설치하기 위해 제공하는 소프트웨어 번들링.</span><span class="sxs-lookup"><span data-stu-id="0beac-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="0beac-115">또한 PUA로 자격이 있는 다른 소프트웨어를 설치하기 위해 제공하는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="0beac-116">**보안 제품에서** 다르게 행동하는 소프트웨어를 포함하여 보안 제품의 검색을 적극적으로 피하는 소프트웨어 사용.</span><span class="sxs-lookup"><span data-stu-id="0beac-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="0beac-117">보안 기능에서 특별히 주의를 기울이기 위해 응용 프로그램에 레이블을 지정하는 데 사용하는 기준에 대한 자세한 예와 자세한 내용은 Microsoft에서 맬웨어 및 사용자 지정 응용 프로그램을 식별하는 [방법을 참조합니다.](/windows/security/threat-protection/intelligence/criteria)</span><span class="sxs-lookup"><span data-stu-id="0beac-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="0beac-118">잠재적으로 원치 않는 응용 프로그램은 네트워크가 실제 맬웨어에 감염될 위험을 높이거나, 맬웨어 감염을 식별하기 어렵게 만들거나, IT 리소스를 정리하는 데 리소스를 낭비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="0beac-119">PUA 보호는 Windows 10, Windows Server 2019 및 Windows Server 2016에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="0beac-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0beac-120">Microsoft Edge</span></span>

<span data-ttu-id="0beac-121">Chromium 기반의 새 [Microsoft Edge는](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)잠재적으로 원치 않는 응용 프로그램 다운로드 및 연결된 리소스 URL을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="0beac-122">이 기능은 [Microsoft Defender SmartScreen을 통해 제공됩니다.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="0beac-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="0beac-123">Chromium 기반 Microsoft Edge에서 PUA 보호 사용</span><span class="sxs-lookup"><span data-stu-id="0beac-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="0beac-124">Microsoft Edge(Chromium 기반 버전 80.0.361.50)의 잠재적으로 원치 않는 응용 프로그램 보호가 기본적으로 꺼져 있는 경우 브라우저 내에서 쉽게 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="0beac-125">타원을 선택한 다음 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0beac-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="0beac-126">개인 **정보, 검색 및 서비스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0beac-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="0beac-127">보안 **섹션에서** 잠재적으로 원치 않는 앱 **차단을 켜십시오.**</span><span class="sxs-lookup"><span data-stu-id="0beac-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="0beac-128">Microsoft Edge(Chromium 기반)를 실행하는 경우 [Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/)데모 페이지 중 하나에서 테스트하여 PUA 보호의 URL 차단 기능을 안전하게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="0beac-129">Microsoft Defender SmartScreen을 통해 URL 차단</span><span class="sxs-lookup"><span data-stu-id="0beac-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="0beac-130">PUA 보호가 켜진 Chromium 기반 Edge에서 Microsoft Defender SmartScreen은 PUA 관련 URL로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="0beac-131">보안 관리자는 Microsoft [Edge와](/DeployEdge/configure-microsoft-edge) Microsoft Defender SmartScreen이 함께 작동하여 PUA 관련 URL로부터 사용자 그룹을 보호하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="0beac-132">PUA를 [](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 차단하기 위한 설정을 포함하여 Microsoft Defender SmartScreen에 대해 명시적으로 사용할 수 있는 여러 그룹 정책 [설정이 있습니다.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)</span><span class="sxs-lookup"><span data-stu-id="0beac-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="0beac-133">또한 관리자는 그룹 정책 설정을 사용하여 Microsoft Defender SmartScreen을 설정하거나 해제하여 [Microsoft Defender SmartScreen을](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 전체적으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="0beac-134">Microsoft Defender for Endpoint에는 Microsoft에서 관리하는 데이터 집합을 기반으로 하는 자체 차단 목록이 있습니다. 그러나 위협 인텔리전스를 기반으로 이 목록을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="0beac-135">끝점 [포털용](/microsoft-365/security/defender-endpoint/manage-indicators) Microsoft Defender에서 표시기를 만들고 관리하는 경우 Microsoft Defender SmartScreen은 새 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="0beac-136">Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="0beac-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="0beac-137">Microsoft Defender 바이러스 백신의 잠재적으로 원치 않는 PUA(응용 프로그램) 보호 기능은 네트워크의 끝점에서 PUA를 검색하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="0beac-138">이 기능은 Windows 10, Windows Server 2019 및 Windows Server 2016에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="0beac-139">Microsoft Defender 바이러스 백신은 검색된 PUA 파일 및 다운로드, 이동, 실행 또는 설치 시도를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="0beac-140">그런 다음 차단된 PUA 파일이 검지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="0beac-141">끝점에서 PUA 파일이 검색되면 Microsoft Defender 바이러스 백신은 알림이[](configure-notifications-microsoft-defender-antivirus.md)사용하지 않도록 설정되지 않은 경우 다른 위협 감지와 동일한 형식으로 사용자에게 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="0beac-142">알림은 콘텐츠를 `PUA:` 나타내기 위해 미리 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="0beac-143">알림은 Windows 보안 앱 내의 일반적인 [검지 목록에 표시됩니다.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0beac-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="0beac-144">Microsoft Defender 바이러스 백신에서 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="0beac-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="0beac-145">[Microsoft Intune, Microsoft Endpoint](/mem/intune/protect/device-protect) [Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection)그룹 [](/azure/active-directory-domain-services/manage-group-policy)정책 또는 [PowerShell cmdlet을](/powershell/module/defender/?preserve-view=true&view=win10-ps)통해 PUA 보호를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="0beac-146">감사 모드에서 PUA 보호를 사용하여 잠재적으로 원치 않는 응용 프로그램을 차단하지 않고 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="0beac-147">검색은 Windows 이벤트 로그에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="0beac-148">Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com/Page/UrlRep) 데모 웹 사이트(demo.wd.microsoft.com)를 방문하여 기능이 작동하고 있는지 확인하고 작동을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0beac-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="0beac-149">감사 모드에서 PUA 보호는 회사에서 내부 소프트웨어 보안 준수 검사를 수행하고 있으며 가극적 긍정을 방지하고자 하는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="0beac-150">Intune을 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="0beac-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="0beac-151">자세한 [내용은 Microsoft Intune의](/intune/device-restrictions-configure) 장치 제한 설정 구성 및 [Intune에서 Windows 10에](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 대한 Microsoft Defender 바이러스 백신 장치 제한 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0beac-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="0beac-152">Configuration Manager를 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="0beac-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="0beac-153">PUA 보호는 기본적으로 Microsoft Endpoint Manager(현재 분기)에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="0beac-154">Microsoft Endpoint Manager(현재 분기)를 구성하는 방법에 대한 자세한 내용은 맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 예약된 검사 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0beac-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="0beac-155">구성 System Center 2012 대한 자세한 내용은 [Configuration Manager에서 Endpoint Protection에](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)대해 잠재적으로 원치 않는 응용 프로그램 보호 정책을 배포하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="0beac-156">Microsoft Defender 바이러스 백신에서 차단된 PUA 이벤트는 Microsoft Endpoint Configuration Manager가 아닌 Windows 이벤트 뷰어에 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="0beac-157">그룹 정책을 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="0beac-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="0beac-158">[Windows 10 2020년 10월 업데이트용 관리 템플릿(.admx)을 다운로드하여 설치(20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="0beac-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="0beac-159">그룹 정책 관리 컴퓨터에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="0beac-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="0beac-160">구성할 그룹 정책 개체를 선택한 다음 편집 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0beac-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="0beac-161">그룹 **정책 관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 **템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0beac-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="0beac-162">Windows 구성 요소 Microsoft Defender 바이러스 **백신까지**  >  **트리를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="0beac-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="0beac-163">원치 않는 응용 프로그램에 대한 검색 구성을 두 **번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0beac-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="0beac-164">PUA **보호를** 사용하도록 설정하려면 사용 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="0beac-165">**옵션에서** **차단을** 선택하여 잠재적으로 원치  않는 응용 프로그램을 차단하거나 감사 모드를 선택하여 해당 환경에서 설정이 작동하는 방법을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="0beac-166">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-166">Select **OK**.</span></span>

9. <span data-ttu-id="0beac-167">일반적으로와 같은 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="0beac-168">PowerShell cmdlet을 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="0beac-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="0beac-169">PUA 보호를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0beac-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="0beac-170">이 cmdlet의 값을 설정하여 사용하지 않도록 설정한 경우 기능을 `Enabled` 켜게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="0beac-171">PUA 보호를 감사 모드로 설정</span><span class="sxs-lookup"><span data-stu-id="0beac-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="0beac-172">설정은 `AuditMode` PUAS를 차단하지 않고 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="0beac-173">PUA 보호를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0beac-173">To disable PUA protection</span></span>

<span data-ttu-id="0beac-174">PUA 보호는 계속 켜져 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="0beac-175">그러나 다음 cmdlet을 사용하여 이 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="0beac-176">이 cmdlet의 값을 설정하여 기능이 활성화된 `Disabled` 경우 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="0beac-177">Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/index) 구성 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0beac-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="0beac-178">PUA 이벤트 보기</span><span class="sxs-lookup"><span data-stu-id="0beac-178">View PUA events</span></span>

<span data-ttu-id="0beac-179">PUA 이벤트는 Windows 이벤트 뷰어에서 보고되지만 Microsoft Endpoint Manager 또는 Intune에서는 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="0beac-180">이 cmdlet을 사용하여 Microsoft Defender 바이러스 백신이 처리한 `Get-MpThreat` 위협을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="0beac-181">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

<span data-ttu-id="0beac-182">PUA 검색에 대한 메일을 받기 위해 전자 메일 알림을 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="0beac-183">Microsoft Defender 바이러스 백신 이벤트 보기에 대한 자세한 내용은 이벤트 [ID](troubleshoot-microsoft-defender-antivirus.md) 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0beac-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="0beac-184">PUA 이벤트는 이벤트 ID **1160 아래에 기록됩니다.**</span><span class="sxs-lookup"><span data-stu-id="0beac-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="0beac-185">파일 제외</span><span class="sxs-lookup"><span data-stu-id="0beac-185">Excluding files</span></span>

<span data-ttu-id="0beac-186">파일이 PUA 보호에 의해 오차적으로 차단되거나 작업을 완료하기 위해 PUA의 기능이 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="0beac-187">이러한 경우 제외 목록에 파일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0beac-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="0beac-188">자세한 내용은 파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사를 [참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0beac-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0beac-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0beac-189">See also</span></span>

- [<span data-ttu-id="0beac-190">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="0beac-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="0beac-191">동작,추론적 및 실시간 보호 구성</span><span class="sxs-lookup"><span data-stu-id="0beac-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)