---
title: Windows Autopilot를 사용 하 여 새 장치에 Windows 10 Enterprise 배포
description: Windows Autopilot를 사용 하 여 Windows 10 Enterprise를 구성 및 배포 하기 위한 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, Windows 10 Enterprise, deployment, Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: e5e3e4fb48a0eb2af1978cbd5a687c67c72bea0c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596645"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a><span data-ttu-id="b7471-104">3 단계: Windows Autopilot를 사용 하 여 새 장치에 Windows 10 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="b7471-104">Step 3: Deploy Windows 10 Enterprise for new devices with Windows Autopilot</span></span>

<span data-ttu-id="b7471-105">*이 문서는 Microsoft 365 Enterprise E3 및 E5 버전에 모두 적용 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="b7471-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![3단계: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="b7471-107">새 Windows 10 Pc가 있는 경우 Windows Autopilot을 사용 하 여 조직의 OOBE (기본 제공 경험)를 사용자 지정 하 고 앱 및 설정이 이미 구성 된 새 시스템을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-107">If you have new Windows 10 PCs, you can use Windows Autopilot to customize the out-of-box-experience (OOBE) for your organization and deploy a new system with apps and settings already configured.</span></span> <span data-ttu-id="b7471-108">배포할 이미지, 주입할 드라이버 및 관리할 인프라가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-108">There are no images to deploy, no drivers to inject, and no infrastructure to manage.</span></span> <span data-ttu-id="b7471-109">사용자는 IT 관리자에 게 문의 하지 않아도 배포 프로세스를 독립적으로 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-109">Users can go through the deployment process independently, without the need consult their IT administrator.</span></span>

<span data-ttu-id="b7471-110">새 Windows 10 장치를 설정 하 고 사전 구성할 수 있으며 Windows Autopilot을 사용 하 여 생산적으로 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-110">You can set up and pre-configure new Windows 10 devices and get them ready for productive use using Windows Autopilot.</span></span> <span data-ttu-id="b7471-111">혜택 및 Windows Autopilot 시나리오를 비롯 한 Windows Autopilot에 대 한 자세한 내용은 [Overview For Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7471-111">To learn more about Windows Autopilot, including benefits and Windows Autopilot scenarios, see [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot).</span></span> <span data-ttu-id="b7471-112">준비가 되 면 다음 부분에 따라 새 장치 설정을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-112">When ready, follow these parts to start setting up new devices.</span></span>

## <a name="the-windows-autopilot-deployment-process-poster"></a><span data-ttu-id="b7471-113">Windows Autopilot 배포 프로세스 포스터</span><span class="sxs-lookup"><span data-stu-id="b7471-113">The Windows Autopilot deployment process poster</span></span>

<span data-ttu-id="b7471-114">Windows Autopilot 포스터는 세로 모드 (11x17)의 두 페이지로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-114">The Windows Autopilot poster is two pages in portrait mode (11x17).</span></span> <span data-ttu-id="b7471-115">아래 이미지를 클릭 하면 브라우저에서 PDF를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-115">Click the image below to view a PDF in your browser.</span></span> 

<span data-ttu-id="b7471-116">[![Autopilot 포스터를 사용하여 Windows 10 배포](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://docs.microsoft.com/windows/deployment/media/Windows10AutopilotFlowchart.pdf)</span><span class="sxs-lookup"><span data-stu-id="b7471-116">[![Deploy Windows 10 with Autopilot poster](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://docs.microsoft.com/windows/deployment/media/Windows10AutopilotFlowchart.pdf)</span></span>

<span data-ttu-id="b7471-117">[PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf)나 [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx) 형식으로도 포스터를 다운로드 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-117">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) or [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx) format.</span></span>

## <a name="part-1-start-windows-autopilot-deployment"></a><span data-ttu-id="b7471-118">1 부: Windows Autopilot 배포 시작</span><span class="sxs-lookup"><span data-stu-id="b7471-118">Part 1: Start Windows Autopilot deployment</span></span>
<span data-ttu-id="b7471-119">[Windows Autopilot 개요](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7471-119">See [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) to:</span></span>

1. <span data-ttu-id="b7471-120">Windows Autopilot 배포에 대 한 필수 구성 요소 및 완료 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-120">Learn about and complete the prerequisites for Windows Autopilot deployment.</span></span> <span data-ttu-id="b7471-121">필수 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-121">The prerequisites include:</span></span>
    - <span data-ttu-id="b7471-122">**장치 등록 및 OOBE 사용자 지정**</span><span class="sxs-lookup"><span data-stu-id="b7471-122">**Device registration and OOBE customization**</span></span>

        <span data-ttu-id="b7471-123">장치를 등록 하려면 하드웨어 ID를 취득 하 여 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-123">To register devices, you need to acquire their hardware ID and register it.</span></span> <span data-ttu-id="b7471-124">Microsoft는 다양 한 하드웨어 공급 업체와 협력 하 여 필요한 정보를 제공 하거나 대신 업로드 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-124">We are actively working with various hardware vendors to enable them to provide the required information to you, or upload it on your behalf.</span></span> <span data-ttu-id="b7471-125">장치의 하드웨어 ID와 함께 .csv 파일을 생성 하는 PowerShell 스크립트를 사용 하 여이 정보를 직접 캡처할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-125">You also have the option to capture this information by yourself using a PowerShell script that generates a .csv file with the device's hardware ID.</span></span>

        <span data-ttu-id="b7471-126">장치를 등록 한 후에는 개인 정보 설정 및 EULA 건너뛰기를 포함 하 여 구성할 수 있는 OOBE 사용자 지정 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-126">Once devices are registered, there are OOBE customization options that you can configure including skipping privacy settings and EULA.</span></span>

    - <span data-ttu-id="b7471-127">**OOBE에 대한 회사 브랜딩**</span><span class="sxs-lookup"><span data-stu-id="b7471-127">**Company branding for OOBE**</span></span>

        <span data-ttu-id="b7471-128">이를 통해 장치 OOBE 중에 표시 되는 브랜딩을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-128">This allows you to add branding to appear during device OOBE.</span></span>

    - <span data-ttu-id="b7471-129">**Microsoft Intune에서 MDM 자동 등록**</span><span class="sxs-lookup"><span data-stu-id="b7471-129">**MDM auto-enrollment in Microsoft Intune**</span></span>
        
        <span data-ttu-id="b7471-130">자동 등록을 사용 하면 사용자가 장치를 Azure AD에 연결할 때 Intune에서 Windows 10 장치를 등록 하 여 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-130">Automatic enrollment lets users enroll their Windows 10 devices in Intune for device management when they connect their devices to Azure AD.</span></span> <span data-ttu-id="b7471-131">등록 하려면 사용자가 자신의 회사 계정을 개인 소유 장치에 추가 하거나 회사 소유의 장치를 Azure AD에 가입 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-131">To enroll, users add their work account to their personally-owned devices or join corporate-owned devices to Azure AD.</span></span> <span data-ttu-id="b7471-132">백그라운드에서는 Intune을 사용 하 여 장치에 대 한 관리도 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-132">In the background, the device is also enrolled for management with Intune.</span></span>

    - <span data-ttu-id="b7471-133">**Windows Autopilot에서 사용되는 클라우드 서비스에 대한 네트워크 연결**</span><span class="sxs-lookup"><span data-stu-id="b7471-133">**Network connectivity to cloud services used by Windows Autopilot**</span></span>

        <span data-ttu-id="b7471-134">Windows Autopilot 배포 프로그램은 다양 한 클라우드 서비스를 사용 하 여 장치를 생산적 상태로 가져오고, 이러한 서비스는 Windows Autopilot 장치로 등록 된 장치에서 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-134">The Windows Autopilot Deployment Program uses a number of cloud services to get your devices to a productive state and these services must be accessible from devices registered as Windows Autopilot devices.</span></span> 

    - <span data-ttu-id="b7471-135">**장치에는 Windows 10, 버전 1703 이상이 미리 설치되어 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7471-135">**Devices must be pre-installed with Windows 10, version 1703 or later**</span></span>

2. <span data-ttu-id="b7471-136">조직의 Windows Autopilot 배포 프로그램에 대해 설명 하 고 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-136">Learn about and select the Windows Autopilot Deployment Program for your organization.</span></span> <span data-ttu-id="b7471-137">다음 배포 프로그램 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-137">You can select from these deployment programs:</span></span>
    - <span data-ttu-id="b7471-138">**비즈니스용 Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="b7471-138">**Microsoft Store for Business**</span></span>
    - <span data-ttu-id="b7471-139">**Microsoft Intune**</span><span class="sxs-lookup"><span data-stu-id="b7471-139">**Microsoft Intune**</span></span>
    - <span data-ttu-id="b7471-140">**파트너 센터**</span><span class="sxs-lookup"><span data-stu-id="b7471-140">**Partner Center**</span></span>

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a><span data-ttu-id="b7471-141">2 부: Microsoft 365 용 Windows 10 장치 설정</span><span class="sxs-lookup"><span data-stu-id="b7471-141">Part 2: Set up a Windows 10 device for Microsoft 365</span></span>
<span data-ttu-id="b7471-142">Microsoft 365 사용자를 위해 Windows 장치를 설정 하기 전에 모든 Windows 장치가 Windows 10, 버전 1703 (크리에이터 업데이트) 이상을 실행 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-142">Before you can set up Windows devices for Microsoft 365 users, make sure all the Windows devices are running Windows 10, version 1703 (Creators Update) or later.</span></span>

<span data-ttu-id="b7471-143">조직의 모든 Windows 장치가 Windows 10 크리에이터 업데이트로 업그레이드 되었거나 이미 Windows 10 크리에이터 업데이트를 실행 하 고 있는 경우 이러한 장치를 조직의 Azure Active Directory에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-143">After all Windows devices in your organization have either been upgraded to Windows 10 Creators Update or are already running Windows 10 Creators Update, you can join these devices to your organization’s Azure Active Directory.</span></span>

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a><span data-ttu-id="b7471-144">새로운 또는 새로 업그레이드 된 Windows 10 장치 설치</span><span class="sxs-lookup"><span data-stu-id="b7471-144">Set up a brand new or newly-upgraded Windows 10 device</span></span>
<span data-ttu-id="b7471-145">Windows 10 크리에이터 업데이트 (또는 이상)를 실행 하는 새 장치 또는 Windows 10 크리에이터 업데이트 이상으로 업그레이드 한 장치에서 windows 10 OOBE를 사용 하 여 장치를 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-145">Follow these steps to set up a device using the Windows 10 OOBE on a brand new device running Windows 10 Creators Update (or later) or on a device that was upgrade to Windows 10 Creators Update (or later) but has not gone through out-of-box setup.</span></span>

1. <span data-ttu-id="b7471-146">무선 네트워크가 구성 되어 있지 않은 경우 유선 또는 이더넷 연결을 통해 장치를 인터넷에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-146">If you don't have a wireless network configured, make sure you connect the device to the internet through a wired or Ethernet connection.</span></span>
2. <span data-ttu-id="b7471-147">Windows 장치 설치 환경을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-147">Go through the Windows device setup experience.</span></span> <span data-ttu-id="b7471-148">새로 만들거나 다시 설정 하는 장치에서는 설정 환경이 **Let의 시작 지역으로 시작 합니다. 적절 하나요?** 화면의.</span><span class="sxs-lookup"><span data-stu-id="b7471-148">On a new or reset device, the setup experience starts with the **Let's start with region. Is this right?** screen.</span></span>
3. <span data-ttu-id="b7471-149">**어떻게 설정하시겠어요?** 페이지에 도달할 때까지 Windows 10 장치 설정을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-149">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> <span data-ttu-id="b7471-150">여기에서 **조직에 대해 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-150">Here, select **Set up for an organization**.</span></span>
4. <span data-ttu-id="b7471-151">Microsoft 365 사용자 계정 및 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-151">Sign in using the Microsoft 365 user's account and password.</span></span> <span data-ttu-id="b7471-152">사용자 암호 설정에 따라 암호를 업데이트 하 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-152">Depending on the user password setting, you may be prompted to update the password.</span></span> 
5. <span data-ttu-id="b7471-153">Windows 10 장치 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-153">Finish Windows 10 device setup.</span></span>

<span data-ttu-id="b7471-154">작업이 완료 되 면 디바이스가 조직의 Azure AD에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-154">After you’re done, the device will be connected to your organization’s Azure AD.</span></span>

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a><span data-ttu-id="b7471-155">기본 설치가 이미 완료 된 장치 설정</span><span class="sxs-lookup"><span data-stu-id="b7471-155">Set up a device that has already completed out-of-box setup</span></span>
<span data-ttu-id="b7471-156">장치에 Windows 10 크리에이터 업데이트 (또는 이상)가 있고 기본 설정 설정이 이미 완료 된 경우에는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-156">If your device has Windows 10 Creators Update (or later) and has already gone through the out-of-box setup, follow these steps.</span></span>

1. <span data-ttu-id="b7471-157">Windows 10을 실행 하는 사용자의 Windows PC, 버전 1703 (작성자 업데이트)에서 **windows** 로고를 선택 하 고 **설정** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-157">On your user's Windows PC that is running Windows 10, version 1703 (Creators Update), select the **Windows** logo, and then select the **Settings** icon.</span></span>
2. <span data-ttu-id="b7471-158">**설정**에서 **계정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-158">In **Settings**, go to **Accounts**.</span></span>
3. <span data-ttu-id="b7471-159">**정보** 페이지에서 **회사 또는 학교** > **연결**액세스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-159">On the **Your info** page, select **Access work or school** > **Connect**.</span></span>
4. <span data-ttu-id="b7471-160">**회사 또는 학교 계정 설정** 대화 상자의 **대체 작업**에서 **Azure Active Directory에이 장치 가입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-160">On the **Set up a work or school account** dialog, under **Alternate actions**, select **Join this device to Azure Active Directory**.</span></span>
5. <span data-ttu-id="b7471-161">**로그인 시작** 페이지에서 회사 또는 학교 계정을 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-161">On the **Let's get you signed in** page, enter your work or school account, and select **Next**.</span></span>
6. <span data-ttu-id="b7471-162">**암호 입력** 페이지에서 암호를 입력 하 고 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-162">On the **Enter password** page, enter your password, and select **Sign in**.</span></span>
7. <span data-ttu-id="b7471-163">**조직** 확인 페이지에서 정보가 올바른지 확인 하 고 **참가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-163">On the **Make sure this is your organization** page, verify that the information is correct, and select **Join**.</span></span>
8. <span data-ttu-id="b7471-164">**완료 되었습니다!**</span><span class="sxs-lookup"><span data-stu-id="b7471-164">On the **You're all set!**</span></span> <span data-ttu-id="b7471-165">페이지에서 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-165">page, select **Done**.</span></span>

<span data-ttu-id="b7471-166">작업을 마치면 사용자가 조직의 Azure AD에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-166">After you're done, the user will be connected to your organization's Azure AD.</span></span>

### <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="b7471-167">장치가 Azure AD에 연결되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="b7471-167">Verify the device is connected to Azure AD</span></span>
<span data-ttu-id="b7471-168">다음 단계에 따라 Azure AD에서 장치의 동기화 상태를 확인 한 다음 장치에서 Microsoft 365 계정을 사용 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-168">Follow these steps to verify the device’s sync status with Azure AD, and then start using your Microsoft 365 account on the device.</span></span> 

1. <span data-ttu-id="b7471-169">**설정을**엽니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-169">Open **Settings**.</span></span>
2. <span data-ttu-id="b7471-170">**회사 또는 학교 액세스** 페이지에서 \*\*연결 <organization name> \*\* 프로그램 영역을 선택 하 여 단추 **정보** 를 표시 하 고 **연결을 끊습니다**.</span><span class="sxs-lookup"><span data-stu-id="b7471-170">On the **Access work or school** page, select the **Connected to <organization name>** area to expose the buttons **Info** and **Disconnect**.</span></span>
3. <span data-ttu-id="b7471-171">**정보** 를 선택 하 여 동기화 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-171">Select **Info** to get your synchronization status.</span></span>
4. <span data-ttu-id="b7471-172">**동기화 상태** 페이지에서 **동기화** 를 선택 하 여 PC에 최신 모바일 장치 관리 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-172">On the **Sync status** page, select **Sync** to get the latest mobile device management policies onto the PC.</span></span>
5. <span data-ttu-id="b7471-173">Microsoft 365 계정을 사용 하려면 Windows **시작** 단추로 이동 하 여 현재 계정 사진을 마우스 오른쪽 단추로 클릭 한 다음 계정 **전환을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-173">To start using the Microsoft 365 account, go to the Windows **Start** button, right-click your current account picture and then select **Switch** account.</span></span>
6. <span data-ttu-id="b7471-174">조직 전자 메일 및 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-174">Sign in by using your organization email and password.</span></span>

<span data-ttu-id="b7471-175">엔터프라이즈 환경에서 Windows 10을 사용할 때 문제가 발생 하면 [가장 일반적인 문제에 대 한 주요 Microsoft 지원 솔루션](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-175">If you experience issues when using Windows 10 in an enterprise environment, you can consult [top Microsoft Support solutions for the most common issues](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions).</span></span> <span data-ttu-id="b7471-176">이러한 리소스에는 기술 자료 문서, 업데이트 및 라이브러리 아티클이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-176">These resources include KB articles, updates, and library articles.</span></span>

<span data-ttu-id="b7471-177">중간 검사점으로 이 단계에 해당하는 [종료 조건](windows10-exit-criteria.md#crit-windows10-step3)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7471-177">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b7471-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b7471-178">Next step</span></span>

|||
|:-------|:-----|
|![4단계](./media/stepnumbers/Step4.png)| [<span data-ttu-id="b7471-180">장치 상태 및 준수 모니터링</span><span class="sxs-lookup"><span data-stu-id="b7471-180">Monitor device health and compliance</span></span>](windows10-enable-windows-analytics.md) |
