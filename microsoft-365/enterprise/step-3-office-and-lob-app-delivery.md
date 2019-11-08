---
title: 3단계 - Office 및 LOB 앱 배달
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/27/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Office 및 LOB 앱을 배달하는 방법을 알아봅니다.
ms.openlocfilehash: fdb16aa9d92e3fd2608ca3738dc5af80389f18ea
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031533"
---
# <a name="step-3-office-and-lob-app-delivery"></a><span data-ttu-id="4a415-103">3단계: Office 및 LOB 앱 배달</span><span class="sxs-lookup"><span data-stu-id="4a415-103">Step 3: Office and LOB App Delivery</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><span data-ttu-id="4a415-104"><strong>3단계: Office 및 LOB 앱 배달</strong></span><span class="sxs-lookup"><span data-stu-id="4a415-104"><strong>Step 3: Office and LOB App Delivery</strong></span></span></p>
<p><span data-ttu-id="4a415-p101">앱이 패키지되고 자동 방식으로 설치할 준비가 되었는지 확인합니다. Office 365 ProPlus가 포함된 간편 실행 패키지에 어떻게 Office 앱을 구성하고, 전달하고, 최신 상태로 유지하는 새 옵션이 포함되어 있는지 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p101">Ensure your apps are packaged and ready for automated installation. Learn how Click-to-Run packaging with Office 365 ProPlus gives you new options to configure, deliver and keep your Office apps up-to-date.</span></span></p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="4a415-107">Office 및 LOB 앱 배달은 Office 및 LOB를 설치 및 관리하는 옵션을 포함하는 권장 배포 프로세스 사이클의 세 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-107">Office and LOB App Delivery is the third step in our recommended deployment process wheel covering the options to install and manage Office and LOB.</span></span> <span data-ttu-id="4a415-108">성공적인 배포를 위해서는 처음 두 단계를 건너뛰지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4a415-108">For successful deployment do not skip the first two steps.</span></span>  <span data-ttu-id="4a415-109">전체 데스크톱 배포 프로세스를 보려면 [데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="4a415-109">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="4a415-110">이제 Office 및 LOB(기간 업무) 앱을 전달할 준비가 되었으며 이 작업을 수행하는 방법은 다양하며 이중에는 몇 가지 흥미로운 새 옵션도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-110">You are now ready to deliver Office and your Line of Business Apps and there are a number of ways to do this, including some exciting new options.</span></span> <span data-ttu-id="4a415-111">일부 애플리케이션은 32비트 또는 64비트 컴파일된 버전으로 사용할 수 있지만, Office 365 ProPlus 등의 다른 애플리케이션은 32비트 및 64비트 기본 컴파일된 버전을 모두 제공하므로, 배포할 버전을 결정하는 것이 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-111">While some applications are only available as either a 32-bit or 64-bit compiled version, others such as Office 365 ProPlus, offer both as 32-bit and 64-bit native compiled code, and one of biggest decisions you will make is which version to deploy.</span></span> <span data-ttu-id="4a415-112">새 디바이스에서 추가 컴퓨팅 성능 및 RAM을 활용하려면 32비트 종속성이 없는 경우 64비트 버전을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-112">To take advantage of additional compute power and RAM on new devices Microsoft recommends using the 64-bit version when there are no 32-bit dependencies.</span></span> <span data-ttu-id="4a415-113">추가 기능 또는 파일 관련 호환성 문제를 파악하려면 계속하기 전에 1단계 디바이스 및 앱 준비를 다시 검토하는 것이 바람직할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-113">To determine any add-in or file-related compatibility challenges you may have it is recommended to revisit Step 1 Device and App Readiness before you continue.</span></span>

<span data-ttu-id="4a415-p104">방해 요인이 없는 경우 Microsoft Office를 비롯한 모든 앱을 64비트 버전으로 배포하는 것이 좋습니다. 64비트 네이티브 컴파일 앱은 최상의 성능을 제공하며 향후에도 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p104">If nothing is blocking you, we recommend you deploy 64-bit versions of all apps, including Microsoft Office. 64-bit native compiled apps offer the best performance and is the most future-proof choice.</span></span>

<span data-ttu-id="4a415-116">Windows에 앱을 설치하는 데 사용할 수 있는 여러 방법과 모델이 있으며 전달 옵션을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-116">There are many methods and models for installing apps on Windows, so let’s look at your delivery options.</span></span>

[<span data-ttu-id="4a415-117">Windows 10 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="4a415-117">Windows 10 application management</span></span>](https://docs.microsoft.com/windows/application-management/)

## <a name="msi-based-deployments"></a><span data-ttu-id="4a415-118">MSI 기반 배포</span><span class="sxs-lookup"><span data-stu-id="4a415-118">MSI-based Deployments</span></span>

<span data-ttu-id="4a415-119">LOB(기간 업무) 앱의 경우 MSI 기반 패키지 또는 실행 파일을 사용하고, 앱을 OS 배포 작업 시퀀스의 일부로 설치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-119">For your line of business apps, you’ll probably use MSI-based packages or executable  and install apps as part of an OS deployment task sequence.</span></span> <span data-ttu-id="4a415-120">Windows 10은 이러한 패키지에서 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-120">Windows 10 continues to work with these packages.</span></span>

<span data-ttu-id="4a415-p106">System Center Configuration Manager 및 Microsoft Intune 등의 소프트웨어 배포 도구 또한 MSI 패키징 앱을 전달하도록 최적화됩니다. Windows 10에서 앱의 유효성을 검사하고 나면, 앱 전달을 위해 System Center Configuration Manager(현재 분기)를 사용할 수 있습니다. Microsoft Intune에서 회사 포털을 사용하는 경우 조직에서 사용할 수 있는 IT 승인 앱의 선택 범위를 최신 응용 프로그램을 포함하도록 확장할 수 있으며 사용자가 필요한 항목을 자체 선택하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p106">Software deployment tools like System Center Configuration Manager and Microsoft Intune are also optimized to deliver MSI-packaged apps. Once you have validated your apps on Windows 10, you can use System Center Configuration Manager (current branch) for app delivery. If you use the Company Portal in Microsoft Intune you can extend the choice of IT sanctioned apps available to your organization to include the latest applications, and users to self-select what they need.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a><span data-ttu-id="4a415-124">PC 이미징</span><span class="sxs-lookup"><span data-stu-id="4a415-124">PC Imaging</span></span>

<span data-ttu-id="4a415-125">다른 인기 있는 앱 전달 방법은 PC 이미징입니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-125">Another popular method of app delivery is PC imaging.</span></span> <span data-ttu-id="4a415-126">이 경우 애플리케이션은 샘플 PC에 작업 시퀀스를 통해 또는 수동으로 설치된 다음, 필수 애플리케이션이 미리 설치된 상태로 시스템 이미지가 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-126">In this case, applications are either installed via task sequence or manually on a sample PC, then a system image is captured with the required applications pre-installed.</span></span> <span data-ttu-id="4a415-127">이미징을 통한 빌드 및 캡처 방법은 새 PC를 프로비저닝할 때 시간을 절약할 수 있지만, 이미지 내의 운영 체제 및 앱이 빠르게 구형이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-127">The imaging approach to build and capture can save time when provisioning new PCs but remember operating systems and apps within the image can become stale quickly.</span></span> <span data-ttu-id="4a415-128">Windows 10 및 Office 365 ProPlus의 누적 업데이트 모델은 이 문제를 해결하는 데 도움이 되지만 완전히 해소하지는 못 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-128">The Cumulative Update model in Windows 10 and Office 365 ProPlus help with this problem, but doesn’t eliminate it completely.</span></span> <span data-ttu-id="4a415-129">따라서 배포 시에 애플리케이션을 이미지 외부에서 설치하는 씬 이미지 접근 방법을 권장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-129">This is why we recommend a thin image approach, where your applications are installed from outside the image at deploy time.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

<span data-ttu-id="4a415-130">Office 365 ProPlus를 이미지에 포함하지 않으려는 경우 이 기능이 사용자 기반 활성화라는 점을 기억하도록 합니다. 즉, 시스템 관리자가 미리 활성화할 수 없습니다. Office 배포 도구를 사용하여 이미징하는 장치에 Office를 미리 설치하고 사용자 로그인을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-130">If you do want to include Office 365 ProPlus in your image, remember that this uses a user-based activation; it cannot be pre-activated by the system admin. Use the Office Deployment Tool to pre-install Office on the device you are imaging and skip the user sign-in.</span></span> <span data-ttu-id="4a415-131">이미지가 배포되면 최종 사용자는 Office 365 자격 증명을 사용하여 로그인하고 Office 365 ProPlus를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-131">Once the image is deployed end users can sign-in using their Office 365 credentials and activate Office 365 ProPlus.</span></span>

[<span data-ttu-id="4a415-132">운영 체제를 설치하는 작업 시퀀스 만들기</span><span class="sxs-lookup"><span data-stu-id="4a415-132">Create a Task Sequence to Install an Operating System</span></span>](https://docs.microsoft.com/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

[<span data-ttu-id="4a415-133">운영 체제 이미지의 일부로 Office 365 ProPlus 배포</span><span class="sxs-lookup"><span data-stu-id="4a415-133">Deploy Office 365 ProPlus as part of an operating system image</span></span>](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-as-part-of-an-operating-system-image)

## <a name="office-click-to-run"></a><span data-ttu-id="4a415-134">Office 간편 실행</span><span class="sxs-lookup"><span data-stu-id="4a415-134">Office Click-to-Run</span></span> 

<span data-ttu-id="4a415-135">Office 365 ProPlus는 간편 실행을 사용하여 설치되고, 간편 실행은 예정된 Windows용 Office 2019 릴리스의 모든 버전에 포함된 MSI 기반 패키징을 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-135">Office 365 ProPlus is installed using Click-to-Run, and Click-to-Run replaces MSI-based packaging in every version of the upcoming Office 2019 release for Windows.</span></span> <span data-ttu-id="4a415-136">이 기능은 더 빠른 설치, 빠르고 효율적인 업데이트, 보다 깔끔한 제거를 비롯한 다양한 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-136">It brings with it a number of advantages, including faster installations, faster and more efficient updating, and cleaner uninstallation.</span></span> 

<span data-ttu-id="4a415-137">간편 실행을 통해 전달되는 프로그램은 컴퓨터의 가상 애플리케이션 환경에서 실행되며, 다른 애플리케이션과 함께 충돌 없이 공존합니다. 또한 MSI 기반 패키지의 경우보다 약 1/2의 디스크 공간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-137">Programs delivered via Click-to-Run execute in a virtual application environment on your computer and so co-exist with other applications without conflict; they also take about half the disk space they would as an MSI-based package.</span></span> <span data-ttu-id="4a415-138">Office 애플리케이션은 Office 앱을 다운로드, 구성 및 사용자 지정하는 데 필요한 Office 설치 엔진인 [Office 배포 도구](https://www.microsoft.com/download/details.aspx?id=49117)를 통해 배달되고 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-138">Office applications are delivered and managed via the [Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117) which is the Office setup engine needed to download, configure, and customize your Office apps.</span></span> <span data-ttu-id="4a415-139">Office 배포 도구는 Office 설치를 구성 및 사용자 지정하는 방법에 대한 메타데이터 지침을 제공하는 구성 XML 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-139">The Office Deployment Tool reads a configuration XML file which provides the metadata instructions on how to configure and customization your Office installation.</span></span>

<span data-ttu-id="4a415-140">[Office 사용자 지정 도구](https://config.office.com/)를 사용하여 배포 설정을 사용자 지정하고 구성 XML 파일을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-140">Microsoft recommends using the [Office Customization Tool](https://config.office.com/) to customize your deployment settings and create your configuration XML file.</span></span> <span data-ttu-id="4a415-141">Office 사용자 지정 도구를 통해 설치할 애플리케이션 및 언어, 애플리케이션 업데이트 방법, 애플리케이션 기본 설정 및 설치 환경 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-141">Through the Office Customization Tool you can set which applications and languages will be installed, how the applications will be updated, application preferences, and installation expereince settings.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-7.png)

<span data-ttu-id="4a415-p112">System Center Configuration Manager를 사용하는 경우 Office 365 ProPlus의 브로드 배포에도 사용할 수 있습니다. System Center Configuration Manager(현재 분기)는 업데이트된 Office 사용자 지정 도구에 대한 네티이브 지원, 간편 실행을 위한 설치 시 패키지 사용자 지정, 설치 후 소프트웨어 업데이트 관리에 대한 네이티브 지원도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p112">If you use System Center Configuration Manager, you can still use it for broad deployment of Office 365 ProPlus. System Center Configuration Manager (current branch) has native support for the updated Office Customization Tool, package customization for Click-to-Run at install time, and native support for software update management post installation.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-6.png)

[<span data-ttu-id="4a415-144">Office 365 ProPlus 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="4a415-144">Deployment Guide for Office 365 ProPlus</span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-for-office-365-proplus)

[<span data-ttu-id="4a415-145">Office 365 ProPlus로 업그레이드하는 경우 기존 MSI 버전의 Office 제거</span><span class="sxs-lookup"><span data-stu-id="4a415-145">Remove existing MSI versions of Office when upgrading to Office 365 ProPlus</span></span>](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version)

[<span data-ttu-id="4a415-146">Configuration Manager를 사용하여 Office 365 ProPlus 관리</span><span class="sxs-lookup"><span data-stu-id="4a415-146">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[<span data-ttu-id="4a415-147">Microsoft Intune을 사용하여 Office 365 앱을 Windows 10 장치에 할당</span><span class="sxs-lookup"><span data-stu-id="4a415-147">Assign Office 365 apps to Windows 10 devices with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/apps-add-office365)

## <a name="browser-based-apps"></a><span data-ttu-id="4a415-148">브라우저 기반 앱</span><span class="sxs-lookup"><span data-stu-id="4a415-148">Browser-based Apps</span></span>

<span data-ttu-id="4a415-p113">브라우저 기반 응용 프로그램이 예상대로 계속 작동하도록 하기 위해 고려해야 할 몇 가지 사항이 있습니다. Microsoft Edge와의 호환성 문제가 알려져 있는 특정 웹 사이트 및 앱이 있는 경우 해당 웹 사이트가 자동으로 Internet Explorer 11을 사용하여 열리도록 Enterprise Mode 사이트 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p113">There are a few things to consider in order to make sure that your browser-based applications continue to work as expected. If you have specific web sites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the web sites will automatically open using Internet Explorer 11.</span></span>

<span data-ttu-id="4a415-p114">또한 인트라넷 사이트가 Microsoft Edge에서 제대로 작동하지 않는 것으로 확인될 경우 모든 인트라넷 사이트가 자동으로 Internet Explorer 11을 사용하여 열리도록 설정할 수 있습니다. 이 프로세스는 XML 파일을 사용하여 각 사이트에 IE11이 사용되는지 여부를 제어하며 그룹 정책을 사용하여 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p114">Additionally, if you know that your intranet sites aren't going to work properly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. This process uses an XML file to govern whether IE11 is used for each site, using Group Policy to enforce settings.</span></span>

[<span data-ttu-id="4a415-153">엔터프라이즈 모드란?</span><span class="sxs-lookup"><span data-stu-id="4a415-153">What is Enterprise Mode</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

<span data-ttu-id="4a415-154">지금까지 잘 알려진 배포 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-154">So far, we have covered well known deployment methods.</span></span> <span data-ttu-id="4a415-155">하지만 고려할 수 있는 두 가지가 새로운 앱 배포 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-155">But there are two new approaches to app deployment you may wish to consider.</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="4a415-156">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4a415-156">Microsoft Store for Business</span></span> 

<span data-ttu-id="4a415-157">비즈니스용 Microsoft Store는 무료 및 유료 앱을 검색하고 획득하고 관리하고 대규모로 Windows 10 디바이스에 배포하는 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-157">Microsoft Store for Business provides a flexible way discover, acquire, manage, and distribute free and paid apps to Windows 10 devices at scale.</span></span> <span data-ttu-id="4a415-158">IT 관리자는 필요에 따라 라이선스를 할당 및 재사용하면서 선택한 Microsoft Store 앱을 사용자 지정 고유 앱과 함께 사용자의 개인 저장소에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-158">As an IT admin, you can publish selected Microsoft Store apps, along with your custom own apps, to your own private store while assigning and re-using licenses as needed.</span></span> <span data-ttu-id="4a415-159">사용자는 이 저장소로만 이동되므로 승인된 앱만 찾아서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-159">Your users are directed to this store only, and so can only find and install approved apps.</span></span>

<span data-ttu-id="4a415-p117">스토어 앱은 기본적으로 UWP 앱으로 빌드될 수 있고, 데스크톱 브리지를 사용하여 기존 앱을 스토어용으로 다시 패키지한 후 Windows 10용 최신 환경을 추가할 수 있습니다. Windows 10 환경을 향상시키는 데 사용하는 코드 외에는 앱은 변경되지 않은 상태를 유지하며, 전체 신뢰 사용자 모드에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p117">Store apps can be natively built as UWP apps or you can use the Desktop Bridge to repackage your existing apps for the Store and add modern experiences for Windows 10. Aside from the code that you use to light up Windows 10 experiences, your app remains unchanged and continues to run in full-trust user mode.</span></span>

## <a name="msix-containerization"></a><span data-ttu-id="4a415-162">MSIX 컨테이너화</span><span class="sxs-lookup"><span data-stu-id="4a415-162">MSIX Containerization</span></span>

<span data-ttu-id="4a415-163">애플리케이션 패키지를 위한 새 옵션은 MSIX입니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-163">A new option for application packaging is MSIX.</span></span> <span data-ttu-id="4a415-164">MSIX에서는 Windows에서 사용할 수 있는 컨테이너화 기술을 사용하여 간편 실행, UWP 및 MSI 패키징에 포함된 최상의 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-164">MSIX uses the containerization technology available in Windows, bringing together the best aspects of Click-to-Run, UWP and MSI packaging.</span></span> <span data-ttu-id="4a415-165">MSIX 컨테이너화는 EXE, MSI, APPV 및 APPX와 같은 기존 설치 관리자를 MSIX로 직접 마이그레이션하는 도구를 사용하여 오늘날 사용되는 많은 설치 기술을 포함하는 통합 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-165">With tools to migrate existing installers like EXE, MSI, APPV and APPX directly to MSIX we see MSIX Containerization provides a unifed path for the many installation technologies in use today.</span></span> <span data-ttu-id="4a415-166">MSIX 지원은 현재 버전의 Windows에 포함되어 있습니다. Windows 10 RS5 이상을 실행하는 디바이스에는 MSIX 패키징 앱을 설치 및 실행하는 데 필요한 모든 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-166">MSIX support is included in current versions of Windows: any device running Windows 10 RS5 or newer includes everything you need to install and run MSIX packaged apps.</span></span> <span data-ttu-id="4a415-167">Windows 10은 애플리케이션을 운영 체제와는 별도로 유지하면서 수신하는 MSIX 컨테이너를 동적으로 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-167">Windows 10 dynamically integrates MSIX containers it receives, while keeping the applications separate from the operating system.</span></span>

<span data-ttu-id="4a415-p119">컨테이너화는 시스템에서 항목을 남겨둘 수 있는 오늘날의 많은 MSI 및 EXE 기반 패키지와 달리, 패키지를 완전히 제거함을 의미합니다. 또한 응용 프로그램을 설치하기 위해 표준 사용자 자격 증명만 있으면 되며, MSIX 컨테이너를 설치하기 위해 관리자 자격 증명이 필요하지 않습니다. MSIX 컨테이너는 업데이트하는 데도 좀 더 효율적입니다. 업데이트가 게시될 때 블록 수준의 차이를 사용하여 새로운 이진 파일만 적용되므로 업데이트 페이로드가 감소하며, 더 적은 네트워크 대역폭을 사용하면서 배포는 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-p119">Containerization means clean uninstall and removal of packages, unlike a lot of MSI and EXE-based packages today that may leave items on the system. It also means only needing Standard User credentials to install applications – you do not have to have Administrator credentials to install MSIX containers. MSIX containers are more efficient to update too. When an update is published, use of block level differentials means only net new binaries are applied, reducing the update payload, for faster deployments consuming less network bandwidth.</span></span>

<span data-ttu-id="4a415-172">[MSIX 기술 커뮤니티 사이트](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)를 통해 MSIX에 대한 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a415-172">You can find more information on MSIX via the [MSIX Tech Community site](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)</span></span>

## <a name="next-step"></a><span data-ttu-id="4a415-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4a415-173">Next Step</span></span>

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[<span data-ttu-id="4a415-174">4단계: 사용자 파일 및 설정</span><span class="sxs-lookup"><span data-stu-id="4a415-174">Step 4: User Files and Settings</span></span>](https://aka.ms/mdd4)

## <a name="previous-step"></a><span data-ttu-id="4a415-175">이전 단계</span><span class="sxs-lookup"><span data-stu-id="4a415-175">Previous Step</span></span>

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="4a415-176">2단계: 디렉터리 및 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="4a415-176">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2) 