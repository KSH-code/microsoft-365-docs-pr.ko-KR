---
title: 1단계 - 장치 및 앱 준비
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 환경에서 장치 및 앱 준비 상태를 평가하는 방법을 알아봅니다.
ms.openlocfilehash: dad6b4092cbcedbc4674733af1459d28f9b1d50e
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112722"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="d762c-103">1단계: 장치 및 앱 준비</span><span class="sxs-lookup"><span data-stu-id="d762c-103">Step 1: Device and App Readiness</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="d762c-104"><strong>1단계: 장치 및 앱 준비</strong></span><span class="sxs-lookup"><span data-stu-id="d762c-104"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="d762c-105">장치 및 앱의 인벤토리 사용하여 데스크톱 배포 프로젝트를 시작하고, 이동할 항목의 우선 순위를 지정하고, 우선 순위가 지정된 앱 및 장치를 테스트한 후, 배포 준비 완료에 필요한 항목을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-105">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you need to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="d762c-106">장치 및 앱 준비는 응용 프로그램 및 하드웨어 호환성의 전체적인 측면을 점검하는 데 권장되는 배포 프로세스 사이클의 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-106">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility.</span></span> <span data-ttu-id="d762c-107">전체 데스크톱 배포 프로세스를 보려면 [데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="d762c-107">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="d762c-p102">과거에 사용자의 데스크톱을 업그레이드할 때 발생하는 주요 장애물은 응용 프로그램 및 하드웨어 호환성입니다. Windows 10 및 Office 365 ProPlus로의 전환을 계획할 경우 지난 10년 이내에 작성한 응용 프로그램을 전환할 때만 이점이 있으며, 조직에서 Office 2010 이후의 Office 버전에서 사용한 COM 추가 기능 및 VBA 매크로는 수정 없이도 최신 버전의 Office에서 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="d762c-110">즉, 응용 프로그램의 크기 및 사용 기간에 따라, 응용 프로그램 및 하드웨어 호환성은 권장되는 8단계 배포 프로세스에서 필수적인 초기 단계일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-110">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="d762c-111">이 문서에서는 Windows 라이선스를 통해 사용할 수 있는 지능형 클라우드 기반 솔루션인 Desktop Analytics를 비롯한 Microsoft 준비 상태 평가 도구를 사용하여 첫 번째 단계인 장치 및 앱 준비를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-111">In this article we take you through that first phase – Device and App Readiness – using Microsoft readiness assessment tools including the Desktop Analytics, an intelligent cloud-based solution available with your Windows license.</span></span>

## <a name="windows-10-compatibility-scan"></a><span data-ttu-id="d762c-112">Windows 10 호환성 검사</span><span class="sxs-lookup"><span data-stu-id="d762c-112">Windows 10 Compatibility Scan</span></span>

<span data-ttu-id="d762c-113">Windows 10을 배포하기 전에 Windows 7 또는 8 / 8.1을 실행하는 기존 장치의 준비 상태를 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-113">Before deploying Windows 10 Microsoft recommends checking the readiness of your existing devices running Windows 7 or 8/8.1.</span></span> <span data-ttu-id="d762c-114">Windows 10 설치 미디어는 setup.exe에 대한 명령줄 스위치를 지원하여 업그레이드를 실행하지만 실제로 업그레이드를 수행하는 것이 아니라 호환성을 확인하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-114">Windows 10 installation media supports a command line switch for the setup.exe to run the upgrade but only check for compatibility, not actually perform the upgrade.</span></span> <span data-ttu-id="d762c-115">ScanOnly는 스크립팅 된 배치 파일로 실행되거나 Microsoft Endpoint Configuration Manager 작업 시퀀스에 통합될 수 있습니다. 또한 네트워크에서 직접 ScanOnly를 실행하여 Windows 10 설치 미디어가 로컬 장치로 스트리밍되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-115">ScanOnly can be run as a scripted batch file or integrated into a System Center Configuration Manager task sequence, including the ability to run the ScanOnly directly from the network so the Windows 10 installation media isn't streamed down to the local device.</span></span> <span data-ttu-id="d762c-116">ScanOnly가 완료되면 Setup.EXE에 의해 생성된 로그 파일의 반환 코드를 통해 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-116">When ScanOnly completes the results are returned via return codes in log files generated by Setup.EXE.</span></span>   

<span data-ttu-id="d762c-117">호환성 검색을 자동으로 완료하는 샘플 ScanOnly 명령줄은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-117">A sample ScanOnly command line that completes the compatibility scan silently would look like the below:</span></span>

    Setup.EXE /Auto Upgrade /Quiet /NoReboot /Compat ScanOnly

<span data-ttu-id="d762c-118">ScanOnly 및 기타 Windows 설치 명령 스위치에 대한 자세한 내용은 [Windows 설치 명령줄 옵션](https://aka.ms/setupswitches)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-118">For more information on ScanOnly and other Windows setup command switches please review the [Windows Setup Command-line Options](https://aka.ms/setupswitches).</span></span>

## <a name="recommended-tool-desktop-analytics"></a><span data-ttu-id="d762c-119">권장 도구: Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="d762c-119">Recommended Tool: Desktop Analytics</span></span>

<span data-ttu-id="d762c-120">Desktop Analytics 기존 데스크톱 관리 시스템에 비해 많은 이점을 제공하는 권장 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-120">Desktop Analytics offers many advantages over traditional desktop management systems and is our recommended tool.</span></span> <span data-ttu-id="d762c-121">이 제품은 에이전트없이 수억 대의 소비자 PC 업그레이드를 통해 수집된 응용 프로그램 및 드라이버 호환성 정보를 사용하여 수행해야 할 작업을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-121">It is agentless and guides you through what needs to be done making use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs.</span></span> <span data-ttu-id="d762c-122">이 정보는 업그레이드를 가로막을 수 있는 호환성 문제를 식별하고 Microsoft에 알려진 수정 제안에 대한 링크를 통해 자세한 평가를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-122">This information gives you a detailed assessment, identifying compatibility issues that might block your upgrade, supported with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="d762c-123">Desktop Analytics를 설정하려면 먼저 Azure 구독을 설정하고 Azure Log Analytics 작업 공간을 포함시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-123">To set up Desktop Analytics you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that.</span></span> <span data-ttu-id="d762c-124">Desktop Analytics 서비스가 실행되면 그룹 정책 설정을 통해 인터넷에 연결된 Windows 7 SP1 또는 최신 장치를 손쉽게 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-124">Once you have the Desktop Analytics service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings - it’s that simple.</span></span> <span data-ttu-id="d762c-125">배포 에이전트가 없이, Desktop Analytics의 시각적 워크플로는 파일럿 배포에서 프로덕션 배포로 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-125">There are no agents to deploy, and Desktop Analytics’ visual workflow guides you from pilot to production deployment.</span></span> <span data-ttu-id="d762c-126">원하는 경우 Desktop Analytics에서 Microsoft Endpoint Configuration Manager(현재 분기)와 같은 소프트웨어 배포 도구로 데이터를 내보낼 수 있으므로 PC를 직접 대상으로하고 배포 준비가 된 컬렉션을 구축 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-126">If you wish, you can export data from Desktop Analytics to software deployment tools such as System Center Configuration Manager (Current Branch), to target PCs directly and build collections as they become ready for deployment.</span></span>

<span data-ttu-id="d762c-127">현재, 환경에 대해 Desktop Analytics를 설치하지 않았거나 평가판을 등록하려는 경우 Desktop Analytics 페이지](https://www.aka.ms/desktopanalytics)로 이동한 후 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-127">If you don’t currently have Desktop Analytics set up for your environment or would like to sign up for a trial, go the Desktop Analytics page](https://www.aka.ms/desktopanalytics) and get started.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="d762c-128">장치 및 앱 준비 프로세스</span><span class="sxs-lookup"><span data-stu-id="d762c-128">Device and App Readiness Process</span></span>

<span data-ttu-id="d762c-129">장치 및 앱 준비는 다음 네 단계로 구성됩니다. 1.</span><span class="sxs-lookup"><span data-stu-id="d762c-129">Device and App Readiness is comprised of four steps: 1.</span></span> <span data-ttu-id="d762c-130">인벤토리, 2.</span><span class="sxs-lookup"><span data-stu-id="d762c-130">Inventory, 2.</span></span> <span data-ttu-id="d762c-131">우선 순위 지정, 3.</span><span class="sxs-lookup"><span data-stu-id="d762c-131">Prioritize, 3.</span></span> <span data-ttu-id="d762c-132">테스트, 4.</span><span class="sxs-lookup"><span data-stu-id="d762c-132">Test, 4.</span></span> <span data-ttu-id="d762c-133">수정.</span><span class="sxs-lookup"><span data-stu-id="d762c-133">Remediate.</span></span> <span data-ttu-id="d762c-134">이들을 각각 차례대로 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-134">Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="d762c-135">1\.</span><span class="sxs-lookup"><span data-stu-id="d762c-135">1\.</span></span> <span data-ttu-id="d762c-136">재고</span><span class="sxs-lookup"><span data-stu-id="d762c-136">Inventory</span></span>

<span data-ttu-id="d762c-137">Desktop Analytics는 에이전트 없는 프로세스를 사용하여 데스크톱 자산 전체에 걸쳐 컴퓨터 및 응용 프로그램에 대한 인벤토리를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-137">Desktop Analytics uses an agent-less process to inventory the computers and applications across your desktop estate.</span></span> <span data-ttu-id="d762c-138">또한 자주 방문한 인터넷 사이트, 응용 프로그램 및 인트라넷 위치에 대한 보고서를 제공하여 나중에 호환성 테스트를 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-138">It also provides reports on highly visited Internet sites, apps, and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="d762c-139">2\.</span><span class="sxs-lookup"><span data-stu-id="d762c-139">2\.</span></span> <span data-ttu-id="d762c-140">우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="d762c-140">Prioritize</span></span>

<span data-ttu-id="d762c-141">인벤토리가 확인되면, Desktop Analytics는 조직에서 가장 일반적으로 사용되는 앱 및 하드웨어, 배포를 위해 가능한 한 많은 PC를 차단 해제할 때 초점을 맞춰야 하는 항목을 식별하고 또한 우선 순위를 부여하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-141">With inventory taken, Desktop Analytics helps you to identify and prioritize the most common apps and hardware used in your organization, as well as what to focus on to unblock as many PCs as possible for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="d762c-142">또한 다음 단계인 테스트 동안 문제를 해결하는 데 필요한 업데이트를 평가하는 데 도움이 되는 지침도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-142">It also provides guidance to help you assess the updates necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="d762c-143">3\.</span><span class="sxs-lookup"><span data-stu-id="d762c-143">3\.</span></span> <span data-ttu-id="d762c-144">테스트</span><span class="sxs-lookup"><span data-stu-id="d762c-144">Testing</span></span>

<span data-ttu-id="d762c-145">인벤토리 된 대부분의 응용 프로그램, 드라이버 및 추가 기능은 있는 그대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-145">You will find that most of the applications, drivers, and add-ins inventoried will work as-is.</span></span> <span data-ttu-id="d762c-146">Desktop Analytics에 문제가 있다고 평가할 경우 해당 항목에 대해 호환성 문제를 해결하기 위해 버전 업데이트를 찾을 수있는 위치를 비롯하여 알려진 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-146">For items Desktop Analytics assesses to have issues, it provides you with known information including where to find version updates to resolve compatibility problems.</span></span> <span data-ttu-id="d762c-147">중요도가 낮고 배포 빈도가 낮은 응용 프로그램 및 구형 장치에서 복잡한 문제를 해결하는 데 시간과 자원을 투입하는 대신 사용자와 협력하여 이러한 항목을 폐기하고 교체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-147">Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="d762c-148">Desktop Analytics를 사용하여 브라우저 기반 호환성 문제를 평가하고 ActiveX 컨트롤, 브라우저 도우미 개체, VBScript 또는 Microsoft Edge 브라우저에서 지원하지 않는 기타 레거시 기술을 사용하는 사용자가 액세스하는 웹 사이트 및 웹 앱을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-148">You can use Desktop Analytics to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser.</span></span> <span data-ttu-id="d762c-149">사용자는 여전히 이러한 사이트에 Internet Explorer 11을 사용해야 하며 엔터프라이즈 모드 사이트 목록 관리자를 사용하여 [엔터프라이즈 모드 사이트 목록](https://docs.microsoft.com/microsoft-edge/deploy/emie-to-improve-compatibility)에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-149">Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="d762c-150">또한 Office 365 ProPlus로의 이전을 지원하기 위해, [Office용 Readiness Toolkit](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro)을 사용하여 추가 기능 및 Microsoft VBA(Visual Basic for Applications) 매크로의 호환성을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-150">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="d762c-p113">4\. 수정</span><span class="sxs-lookup"><span data-stu-id="d762c-p113">4\. Remediation</span></span>

<span data-ttu-id="d762c-153">기기 및 앱 준비의 최종 단계는 '수정'입니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-153">The final phase of device and app readiness is to ‘remediate’.</span></span> <span data-ttu-id="d762c-154">여기에서 필요한 소프트웨어 또는 드라이버 패키지를 수집할 수 있습니다. 이러한 항목을 사용하여 배포 프로세스의 일부로 이전 버전을 대체하거나 업데이트하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-154">Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="d762c-p115">목록을 따라 이동하면서 문제를 수정하면 점점 더 많은 PC가 “배포 준비 완료” 상태가 되는 것을 알 수 있습니다. 즉, PC의 드라이버와 앱 둘 다 배포 목표로 지정한 Windows 10 버전과 호환되는 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-p115">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

### <a name="configuration-manager-software-inventory-for-application-prioritization"></a><span data-ttu-id="d762c-157">응용 프로그램 우선 순위 지정을 위한 Configuration Manager 소프트웨어 인벤토리</span><span class="sxs-lookup"><span data-stu-id="d762c-157">Configuration Manager Software Inventory for Application Prioritization</span></span>

<span data-ttu-id="d762c-158">Configuration Manager 소프트웨어 인벤토리는 장치 및 응용 프로그램 준비에 클라우드 기반 분석 솔루션 사용의 대안으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-158">Configuration Manager software inventory is an alternative to using cloud-based analytics solutions for device and app readiness.</span></span> <span data-ttu-id="d762c-159">설치 횟수 및 특정 컴퓨터를 조사하여 호환성 테스트 및 유효성 검사의 우선 순위를 지정하고 패키지 설정을 통해 Windows 10과 호환되는 응용 프로그램 패키지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-159">You can use installation counts and drill into specific computers to help prioritize compatibility testing and validation and set application packages as compatible with Windows 10 via package settings.</span></span> <span data-ttu-id="d762c-160">이 옵션은 Microsoft의 분석 서비스와 알려진 호환성 정보를 비교하는 기능을 제공하지는 않지만 우선 순위가 지정된 앱들을 더 작은 집합의 대상으로 하는 수동 테스트에 효과적인 솔루션이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-160">While this option does not offer the ability to compare known compatibility information with Microsoft’s analytics services, it can be an effective solution to target a smaller set of prioritized apps for manual testing.</span></span> 

<span data-ttu-id="d762c-161">자세한 내용은 [Configuration Manager의 소프트웨어 인벤토리 소개](https://docs.microsoft.com/configmgr/core/clients/manage/inventory/introduction-to-software-inventory) 및 [Configuration Manager의 패키지 및 프로그램](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)에서 응용 프로그램 패키지의 플랫폼 요구 사항 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d762c-161">For more information, see [Introduction to software inventory in System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/inventory/introduction-to-software-inventory) and setting platform requirements in application packages in [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>


## <a name="desktop-app-assure"></a><span data-ttu-id="d762c-162">데스크톱 앱 Assure</span><span class="sxs-lookup"><span data-stu-id="d762c-162">Desktop App Assure</span></span>

<span data-ttu-id="d762c-163">Windows 10 및 Office 365 ProPlus 응용 프로그램 호환성을 지원하는 또 다른 도구는 FastTrack Center를 통해 제공되는 [데스크톱 앱 Assure](https://aka.ms/desktopappassure) 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-163">Another tool to help with Windows 10 and Office 365 ProPlus app compatibility is the [Desktop App Assure](https://aka.ms/desktopappassure) program available through the FastTrack Center.</span></span> <span data-ttu-id="d762c-164">유효한 응용 프로그램 문제가 발생할 경우 데스크톱 앱 Assure를 통해 Microsoft 엔지니어가 추가 비용없이 사용자와 협력하여 응용 프로그램 비호환성 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-164">Through Desktop App Assure in the event of valid application issues a Microsoft engineer with work with you at no additional cost to help remediate the application incompatibility.</span></span>

## <a name="continued-use-of-diagnostic-data-tools"></a><span data-ttu-id="d762c-165">진단 데이터 도구의 지속적인 사용</span><span class="sxs-lookup"><span data-stu-id="d762c-165">Continued Use of Diagnostic Data Tools</span></span>

<span data-ttu-id="d762c-166">Desktop Analytics는 단지 Windows 10 및 Office 365 ProPlus로의 전환을 도와주기 위한 도구가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-166">Desktop Analytics isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus.</span></span> <span data-ttu-id="d762c-167">Windows 10 및 Office 365에서 데스크톱을 실행하는 경우 이 도구를 사용하여 배포를 유지 관리하고 반기 기능 업데이트를 관리하여 최신 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d762c-167">Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="d762c-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d762c-168">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="d762c-169">2단계: 디렉터리 및 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="d762c-169">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)
