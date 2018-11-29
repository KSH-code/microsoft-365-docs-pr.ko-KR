---
title: 1단계 - 장치 및 앱 준비
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 환경에서 장치 및 앱 준비 상태를 평가하는 방법을 알아봅니다.
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870367"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="8780b-103">1단계: 장치 및 앱 준비</span><span class="sxs-lookup"><span data-stu-id="8780b-103">Step 1: Device and App Readiness</span></span>

<span data-ttu-id="8780b-104">장치 및 앱의 인벤토리 사용하여 데스크톱 배포 보호를 시작하고, 이동할 항목의 우선 순위를 지정하고, 우선 순위가 지정된 앱 및 장치를 테스트한 후, 배포 준비 완료에 필요한 항목 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-104">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="8780b-105"><strong>1단계: 장치 및 앱 준비</strong></span><span class="sxs-lookup"><span data-stu-id="8780b-105"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="8780b-106">장치 및 앱의 인벤토리 사용하여 데스크톱 배포 보호를 시작하고, 이동할 항목의 우선 순위를 지정하고, 우선 순위가 지정된 앱 및 장치를 테스트한 후, 배포 준비 완료에 필요한 항목 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-106">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="8780b-p101">장치 및 앱 준비는 응용 프로그램 및 하드웨어 호환성의 전체적인 측면을 점검하는 권장되는 배포 프로세스 사이클의 첫 번째 단계입니다. 전체 데스크톱 배포 프로세스를 보려면 [최신 데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="8780b-p101">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="8780b-p102">과거에 사용자의 데스크톱을 업그레이드할 때 발생하는 주요 장애물은 응용 프로그램 및 하드웨어 호환성입니다. Windows 10 및 Office 365 ProPlus로의 전환을 계획할 경우 지난 10년 이내에 작성한 응용 프로그램을 전환할 때만 이점이 있으며, 조직에서 Office 2010 이후의 Office 버전에서 사용한 COM 추가 기능 및 VBA 매크로는 수정 없이도 최신 버전의 Office에서 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="8780b-111">즉, 응용 프로그램의 크기 및 사용 기간에 따라, 응용 프로그램 및 하드웨어 호환성은 권장되는 8단계 배포 프로세스에서 필수적인 초기 단계일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-111">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="8780b-112">이 문서에서는 Windows 라이선스를 통해 사용할 수 있는 지능형 클라우드 기반 솔루션인 새로운 Windows Analytics 업그레이드 준비 도구를 사용하여 첫 번째 단계인 장치 및 앱 준비를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-112">In this article we take you through that first phase – Device and App Readiness – using the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

<span data-ttu-id="8780b-113">현재, 환경에 대해 Windows Analytics를 설치하지 않았거나 평가판을 등록하려는 경우 [Windows Analytics 페이지](http://www.aka.ms/windowsanalytics)로 이동한 후 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-113">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="8780b-114">권장 도구: Windows Analytics 업그레이드 준비</span><span class="sxs-lookup"><span data-stu-id="8780b-114">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="8780b-p103">Windows Analytics 업그레이드 준비 기능은 기존 데스크톱 관리 시스템에 비해 많은 이점을 제공하며, 권장되는 도구입니다. 이 도구는 에이전트를 사용하지 않습니다. 수행할 작업을 안내하며, 수백만 대의 소비자 PC를 업그레이드하면서 수집한 응용 프로그램 및 드라이버 호환성 정보를 활용하여 자세한 평가를 제공하고, 업그레이드를 방해할 수 있는 호환성 문제를 식별하고 Microsoft에 알려진 제안되는 수정 프로그램 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p103">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool. It is agentless; it guides you through what needs to be done; and, it makes use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs, to give you a detailed assessment, identifying compatibility issues that might block your upgrade, with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="8780b-p104">Windows Analytics 업그레이드 준비 기능을 설정하려면 먼저 Azure 구독을 설정하고 해당 구독에 Azure Log Analytics 작업 공간을 포함해야 합니다. Windows Analytics 업그레이드 준비 서비스가 실행되는 동안, 그룹 정책 설정을 통해 인터넷 연결 Windows 7 SP1 이상 장치를 등록할 수 있습니다. 등록 과정은 간단합니다. 배포할 에이전트도 없으며, Windows Analytics 업그레이드 준비 기능의 시각적 워크플로는 파일럿부터 프로덕션 배포까지 사용자를 안내합니다. 원할 경우 Windows Analytics 업그레이드 준비 기능의 데이터를 System Center Configuration Manager와 같은 소프트웨어 배포 도구로 내보내 PC가 배포 준비가 완료되면 직접 타기팅하고 컬렉션을 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p104">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that. Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings. It’s that simple. There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment. If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="8780b-122">장치 및 앱 준비 프로세스</span><span class="sxs-lookup"><span data-stu-id="8780b-122">Device and App Readiness Process</span></span>

<span data-ttu-id="8780b-p105">장치 및 앱 준비는 4가지 단계, 즉 1. 인벤토리 파악, 2. 우선 순위 지정, 3. 테스트, 4. 수정으로 이루어집니다. 이러한 각 단계를 차례대로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p105">Device and App Readiness compromises four steps: 1. Inventory, 2. Prioritize, 3. Test, 4. Remediate. Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="8780b-p106">1\. 인벤토리 파악</span><span class="sxs-lookup"><span data-stu-id="8780b-p106">1\. Inventory</span></span>

<span data-ttu-id="8780b-131">Windows Analytics 업그레이드 준비 서비스는 에이전트 없는 프로세스를 사용하여 데스크톱 자산 전체의 컴퓨터, 응용 프로그램 및 Office 추가 기능에 대한 인벤토리를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-131">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="8780b-132">나중에 호환성 테스트를 수행하는 데 도움을 주기 위해 방문 횟수가 많은 인터넷 사이트, 앱 및 인트라넷 위치에 대한 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-132">It also provides reports on highly visited Internet sites, apps and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="8780b-p107">2\. 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="8780b-p107">2\. Prioritize</span></span>

<span data-ttu-id="8780b-135">인벤토리가 확인되면, Windows Analytics 업그레이드 준비 기능은 조직에서 가장 일반적으로 사용되는 앱 및 하드웨어, 배포를 위해 가능한 한 많은 PC를 차단 해제할 때 초점을 맞춰야 하는 항목을 식별하고 우선 순위를 부여하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-135">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, and what to focus on to unblock as many PCs as possible for deployment,</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="8780b-136">또한 다음 단계인 테스트 동안 문제를 해결하는 데 필요한 업데이트를 평가하는 데 도움이 되는 지침도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-136">also providing guidance to help you assess the updates are necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="8780b-p108">3\. 테스트</span><span class="sxs-lookup"><span data-stu-id="8780b-p108">3\. Testing</span></span>

<span data-ttu-id="8780b-p109">대부분의 응용 프로그램, 드라이버 및 추가 기능은 인벤토리에 포함되면 제대로 작동합니다. Windows Analytics 업그레이드 준비 기능은 문제가 있다고 평가한 항목에 대해 호환성 문제 해결을 위한 버전 업데이트를 찾을 수 있는 위치를 비롯한 알려진 정보를 제공합니다. 중요하지 않으며 드물게 배포된 응용 프로그램 및 이전 장치에서 복잡한 문제를 해결하기 위해 시간과 리소스를 투입하지 말고, 사용자와 협의하여 이러한 항목을 삭제한 후 새 항목으로 대체하는 것을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p109">You will find that most of the applications, drivers, and add-ins inventoried, will work as-is. For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information, including where to find version updates to resolve compatibility problems. Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="8780b-p110">Windows Analytics 업그레이드 준비 상태를 사용하여 브라우저 기반 호환성 문제도 평가하고, 사용자가 ActiveX 컨트롤, 브라우저 도우미 개체, VBScript 또는Microsoft Edge 브라우저에서 지원되지 않는 기타 레거시 기술을 사용하여 액세스하는 웹 사이트 및 웹앱을 식별할 수 있습니다. 사용자는 이러한 사이트를 위해 여전히 Internet Explorer 11을 사용해야 하며, Enterprise Mode Site List Manager를 사용하여 [엔터프라이즈 모드 사이트 목록](https://docs.microsoft.com/ko-KR/microsoft-edge/deploy/emie-to-improve-compatibility)에 이러한 사이트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p110">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/ko-KR/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="8780b-144">또한 Office 365 ProPlus로의 이전을 지원하기 위해, [Office용 Readiness Toolkit](https://docs.microsoft.com/ko-KR/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro)을 사용하여 추가 기능 및 Microsoft VBA(Visual Basic for Applications) 매크로의 호환성을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-144">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/ko-KR/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="8780b-p111">4\. 수정</span><span class="sxs-lookup"><span data-stu-id="8780b-p111">4\. Remediation</span></span>

<span data-ttu-id="8780b-p112">장치 및 앱 준비의 마지막 단계는 ‘수정’하는 것입니다. 여기에서 필요한 소프트웨어 또는 드라이버 패키지를 수집할 수 있습니다. 이러한 항목을 사용하여 배포 프로세스의 일부로 이전 버전을 대체하거나 업데이트하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p112">As the final phase of device and app readiness is to ‘remediate’. Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="8780b-p113">목록을 따라 이동하면서 문제를 수정하면 점점 더 많은 PC가 “배포 준비 완료” 상태가 되는 것을 알 수 있습니다. 즉, PC의 드라이버와 앱 둘 다 배포 목표로 지정한 Windows 10 버전과 호환되는 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p113">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

## <a name="continued-use-of-telemetry-tools"></a><span data-ttu-id="8780b-151">원격 분석 도구의 지속적인 사용</span><span class="sxs-lookup"><span data-stu-id="8780b-151">Continued use of telemetry tools</span></span>

<span data-ttu-id="8780b-p114">Windows Analytics 업그레이드 준비는 단지 Windows 10 및 Office 365 ProPlus로의 전환을 도와주기 위한 도구가 아닙니다. Windows 10 및 Office 365에서 데스크톱을 실행하는 경우 이 도구를 사용하여 배포를 유지 관리하고 반기 기능 업데이트를 관리하여 최신 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8780b-p114">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="8780b-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8780b-154">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="8780b-155">2단계: 디렉터리 및 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="8780b-155">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)