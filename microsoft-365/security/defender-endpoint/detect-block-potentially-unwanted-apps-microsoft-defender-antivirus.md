---
title: Microsoft Defender 바이러스 백신을 통해 사용자 동의없이 설치된 응용 프로그램 차단
description: PUA(사용자 동의없이 설치된 응용 프로그램) 바이러스 백신 기능을 사용하도록 설정하여 애드웨어와 같은 원하지 않는 소프트웨어를 차단합니다.
keywords: pua, 사용, 원하지 않는 소프트웨어, 원하지 않는 앱, 애드웨어, 브라우저 도구 모음, 감지, 차단, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275243"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="79645-104">사용자 동의없이 설치된 응용 프로그램 검색 및 차단</span><span class="sxs-lookup"><span data-stu-id="79645-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79645-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="79645-105">**Applies to:**</span></span>

- [<span data-ttu-id="79645-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="79645-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="79645-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="79645-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="79645-108">PUA(사용자 동의없이 설치된 응용 프로그램)는 컴퓨터가 느리게 실행되거나 예기치 않은 광고가 표시되거나 최악의 상황으로 예상치 못하거나 원치 않을 수 있는 기타 소프트웨어를 설치하게 할 수 있는 소프트웨어 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="79645-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="79645-109">PUA는 바이러스, 맬웨어 또는 다른 유형의 위협으로 간주되지 않지만 끝점에서 끝점 성능이나 사용에 부정적인 영향을 주는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="79645-110">*PUA* 라는 용어는 특정 종류의 바람직하지 않은 동작으로 인해 엔드포인트용 Microsoft Defender에서 평가한 평판이 나쁜 응용 프로그램을 가리키지도 합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="79645-111">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="79645-111">Here are some examples:</span></span>

- <span data-ttu-id="79645-112">광고나 프로모션을 표시하는 **광고 소프트웨어**, 광고를 웹페이지에 삽입하는 소프트웨어 포함.</span><span class="sxs-lookup"><span data-stu-id="79645-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="79645-113">동일한 엔터티에서 디지털 서명된 것이 아닌 다른 소프트웨어를 설치하도록 제안하는 **번들화 소프트웨어**.</span><span class="sxs-lookup"><span data-stu-id="79645-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="79645-114">또한 PUA로 적격한 다른 소프트웨어를 설치하도록 제안하는 소프트웨어를 말하기도 함.</span><span class="sxs-lookup"><span data-stu-id="79645-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="79645-115">보안 제품이 있을 때 다르게 동작하는 소프트웨어를 포함해 보안 제품의 탐지를 적극적으로 피하려고 하는 **회피 소프트웨어**.</span><span class="sxs-lookup"><span data-stu-id="79645-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="79645-116">보안 기능에서 특별히 주의를 기울이기 위해 응용 프로그램에 레이블을 지정하는 데 사용하는 기준에 대한 논의 사항과 추가 예제는 [Microsoft에서 맬웨어 및 사용자 동의없이 설치된 응용 프로그램을 식별하는 방법](/windows/security/threat-protection/intelligence/criteria)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="79645-117">사용자 동의없이 설치된 응용 프로그램이 있으면 네트워크가 실제 맬웨어에 감염될 위험이 높아지고 맬웨어 감염을 식별하기 어렵게 되거나 감염을 없애는 데 IT 리소스가 낭비될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="79645-118">PUA 보호는 Windows 10, Windows Server 2019 및 Windows Server 2016에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="79645-119">Windows 10(버전 2004 이상)에서 Microsoft Defender 바이러스 백신은 기본적으로 Enterprise(E5) 디바이스용 PUA로 간주되는 앱을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="79645-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="79645-120">Microsoft Edge</span></span>

<span data-ttu-id="79645-121">[새로운 Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)는 Chromium 기반으로 사용자 동의없이 설치된 응용 프로그램 다운로드 및 관련 리소스 URL을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="79645-122">이 기능은 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="79645-123">Chromium 기반 Microsoft Edge에서 PUA 보호 사용</span><span class="sxs-lookup"><span data-stu-id="79645-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="79645-124">Microsoft Edge(Chromium 기반 버전 80.0.361.50)에서 사용자 동의없이 설치된 응용 프로그램 보호는 기본적으로 꺼져 있지만 브라우저 내에서 손쉽게 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="79645-125">Microsoft Edge 브라우저에서 줄임표를 선택한 후 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="79645-126">**개인 정보, 검색 및 서비스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="79645-127">**보안** 섹션에서 **사용자 동의없이 설치된 앱 차단** 을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="79645-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="79645-128">Microsoft Edge(Chromium 기반)를 실행하는 경우 [Microsoft Defender SmartScreen 데모 페이지](https://demo.smartscreen.msft.net/) 중 하나에서 테스트하여 PUA 보호의 URL 차단 기능을 안전하게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="79645-129">Microsoft Defender SmartScreen로 URL 차단</span><span class="sxs-lookup"><span data-stu-id="79645-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="79645-130">PUA 보호가 켜진 Chromium 기반 Edge에서 Microsoft Defender SmartScreen은 PUA 관련 URL로부터 사용자를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="79645-131">보안 관리자는 Microsoft Edge 및 Microsoft Defender SmartScreen이 함께 작동하여 PUA 관련 URL로부터 사용자 그룹을 보호하는 방법을 [구성](/DeployEdge/configure-microsoft-edge)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="79645-132">Microsoft Defender SmartScreen에는 [PUA를 차단하기 위한 설정](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)을 포함하여 몇 가지 명시적으로 사용할 수 있는 [그룹 정책 설정](/DeployEdge/microsoft-edge-policies#smartscreen-settings)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="79645-133">또한 관리자는 그룹 정책 설정을 통해 [Microsoft Defender SmartScreen을 하나의 전체로 구성](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)하여 Microsoft Defencer SmartScreen을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="79645-134">엔드포인트용 Microsoft Defender에는 Microsoft에서 관리하는 데이터 집합을 기반으로 한 자체 차단 목록이 있지만, 자체 위협 인텔리전스 기반의 이 목록을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="79645-135">엔드포인트용 Microsoft Defender 포털에서 [지표를 만들고 관리](manage-indicators.md)하는 경우 Microsoft Defender SmartScreen은 새 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="79645-136">Microsoft Defender 바이러스 백신 및 PUA 보호</span><span class="sxs-lookup"><span data-stu-id="79645-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="79645-137">Microsoft Defender 바이러스 백신의 PUA(사용자 동의없이 설치된 응용 프로그램) 보호 기능은 네트워크의 끝점에서 PUA를 검색하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="79645-138">이 기능은 Windows 10, Windows Server 2019 및 Windows Server 2016에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="79645-139">Microsoft Defender 바이러스 백신은 감지된 PUA 파일 및 이를 다운로드, 이동, 실행 또는 설치하려는 시도를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="79645-140">그런 다음 차단된 PUA 파일은 이동하여 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="79645-141">끝점에서 PUA 파일이 감지되면 Microsoft Defender 바이러스 백신에서는 다른 위협 감지와 같은 형식으로 사용자에게 알림을 전송합니다([알림이 사용하지 않도록 설정된 경우가 아니면](configure-notifications-microsoft-defender-antivirus.md)).</span><span class="sxs-lookup"><span data-stu-id="79645-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="79645-142">알림은 내용은 표시하기 위해 `PUA:`(으)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="79645-143">알림은 [Windows 보안 앱 내 일반적인 격리 목록](microsoft-defender-security-center-antivirus.md)에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="79645-144">Microsoft Defender 바이러스 백신에서 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="79645-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="79645-145">[Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [그룹 정책](/azure/active-directory-domain-services/manage-group-policy), 또는 [PowerShell cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)을 통해 PUA 보호를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="79645-146">사용자 동의없이 설치된 응용 프로그램을 차단하지 않고 감지하기 위해 PUA 보호를 감사 모드로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="79645-147">감지는 Windows 이벤트 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="79645-148">[demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep)에서 엔드포인트용 Microsoft Defender 데모 웹 사이트를 방문하여 기능이 작동하는지 확인하고 실제로 작동해 보세요.</span><span class="sxs-lookup"><span data-stu-id="79645-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="79645-149">회사에서 내부 소프트웨어 보안 규정 준수 검사를 수행하고 있으며 오탐지를 피하고자 하는 경우에 PUA 보호를 감사 모드로 사용하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="79645-150">Intune을 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="79645-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="79645-151">자세한 내용은 [Microsoft Intune에서 디바이스 제한 설정 구성](/intune/device-restrictions-configure) 및 [Intune에서 Windows 10의 Microsoft Defender 바이러스 백신 디바이스 제한 설정](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="79645-152">Configuration Manager를 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="79645-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="79645-153">PUA 보호는 기본적으로 Microsoft Endpoint Manager(현재 분기)에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="79645-154">Microsoft Endpoint Manager(현재 분기) 구성에 대한 자세한 내용은 [맬웨어 방지 정책을 만들고 배포하는 방법: 예약 검사 설정](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="79645-155">System Center 2012 Configuration Manager의 경우 [Configuration Manager에서 Endpoint Protection을 위한 사용자 동의없이 설치된 응용 프로그램 보호 정책을 배포하는 방법](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="79645-156">Microsoft Defender 바이러스 백신에서 차단하는 PUA 이벤트는 Microsoft Endpoint Configuration Manager가 아닌 Windows 이벤트 뷰어에서 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="79645-157">그룹 정책을 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="79645-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="79645-158">[Windows 10 2020년 10월 업데이트(20H2)의 관리 템플릿(.admx)](https://www.microsoft.com/download/details.aspx?id=102157) 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="79645-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="79645-159">그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="79645-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="79645-160">구성할 그룹 정책 개체를 선택한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="79645-161">**그룹 정책 관리 편집기** 에서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="79645-162">**Windows 구성 요소** > **Microsoft Defender 바이러스 백신** 으로 트리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="79645-163">**사용자 동의없이 설치된 응용 프로그램에 대한 감지 구성** 을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="79645-164">PUA 보호를 사용하도록 설정하려면 **사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="79645-165">**옵션** 에서 **차단** 을 선택하여 사용자 동의없이 설치된 응용 프로그램을 차단하거나 **감사 모드** 를 선택하여 환경에서 설정이 작동하는 방식을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="79645-166">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-166">Select **OK**.</span></span>

9. <span data-ttu-id="79645-167">평소와 같이 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="79645-168">PowerShell cmdlet을 사용하여 PUA 보호 구성</span><span class="sxs-lookup"><span data-stu-id="79645-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="79645-169">PUA 보호를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="79645-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="79645-170">사용하지 않도록 설정되어 있는 경우 이 cmdlet 값을 `Enabled`(으)로 설정하면 기능이 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="79645-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="79645-171">PUA 보호를 감사 모드로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="79645-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="79645-172">`AuditMode`을(를) 설정하면 PUA를 차단하지 않고 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="79645-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="79645-173">PUA 보호를 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="79645-173">To disable PUA protection</span></span>

<span data-ttu-id="79645-174">PUA 보호가 계속 켜져 있도록 하는 것이 권장되지만</span><span class="sxs-lookup"><span data-stu-id="79645-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="79645-175">다음 cmdlet을 사용하여 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="79645-176">사용하도록 설정되어 있는 경우 이 cmdlet 값을 `Disabled`(으)로 설정하면 기능이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="79645-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="79645-177">자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/index)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="79645-178">PowerShell을 사용하여 PUA 이벤트 보기</span><span class="sxs-lookup"><span data-stu-id="79645-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="79645-179">PUA 이벤트는 Microsoft Endpoint Manager 또는 Intune이 아니라 Windows 이벤트 뷰어에서 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="79645-180">또한 `Get-MpThreat` cmdlet을 사용하여 Microsoft Defender 바이러스 백신에서 처리한 위협을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="79645-181">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="79645-181">Here's an example:</span></span>

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

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="79645-182">PUA 감지에 대한 전자 메일 알림 수신</span><span class="sxs-lookup"><span data-stu-id="79645-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="79645-183">PUA 감지에 대한 메일을 수신하려면 전자 메일 알림을 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="79645-184">Microsoft Defender 바이러스 백신 이벤트 보기에 대한 자세한 내용은 [이벤트 ID 문제 해결](troubleshoot-microsoft-defender-antivirus.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="79645-185">PUA 이벤트는 이벤트 ID **1160** 아래에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="79645-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="79645-186">고급 헌팅을 사용하여 PUA 이벤트 보기</span><span class="sxs-lookup"><span data-stu-id="79645-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="79645-187">[엔드포인트용 Microsoft Defender](microsoft-defender-endpoint.md)를 사용할 경우 고급 헌팅 쿼리를 사용하여 PUA 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="79645-188">다음은 쿼리의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="79645-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="79645-189">고급 헌팅에 대한 자세한 내용을 확인하려면 [고급 헌팅으로 위협을 사전 예방적으로 헌팅하는 방법](advanced-hunting-overview.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="79645-190">PUA 보호에서 파일 제외</span><span class="sxs-lookup"><span data-stu-id="79645-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="79645-191">경우에 따라 PUA 보호로 파일이 잘못 차단되거나 작업을 완료하기 위해서 PUA 기능이 필요할 때가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="79645-192">이 경우 파일을 제외 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79645-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="79645-193">자세한 내용은 [파일 확장명 및 폴더 위치를 기준으로 제외를 구성하고 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79645-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79645-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79645-194">See also</span></span>

- [<span data-ttu-id="79645-195">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="79645-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="79645-196">동작, 추론 및 실시간 보호 구성</span><span class="sxs-lookup"><span data-stu-id="79645-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)