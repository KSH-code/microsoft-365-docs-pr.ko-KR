---
title: Microsoft 365 Business 사용자를 위해 Windows 장치 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Microsoft 365 Business 사용자 Windows 10 Pro를 실행하는 Windows 장치를 설정하는 방법에 대해 알아보십시오. '
ms.openlocfilehash: 1e160d624ce5150a1fb74899949aca824589d908
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831346"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="658f6-103">Microsoft 365 Business 사용자를 위해 Windows 장치 설정</span><span class="sxs-lookup"><span data-stu-id="658f6-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="658f6-104">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="658f6-104">Prerequisites</span></span>

<span data-ttu-id="658f6-p101">Microsoft 365 Business 사용자를 위해 Windows 장치를 설정하기 전에 모든 Windows 장치가 Windows 10 Pro 버전 1703(크리에이터 업데이트)을 사용하고 있는지 확인하세요. Windows 10 Pro를 보완하고 중앙 집중식 관리와 Microsoft 365 Business의 보안 제어를 사용할 수 있는 클라우드 서비스이자 장치 관리 기능인 Windows 10 Business를 배포하려면 Windows 10 Pro가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="658f6-107">Windows 장치에서 Windows 7 Pro, Windows 8 Pro 또는 Windows 8.1 Pro를 실행하는 경우 Microsoft 365 Business 구독을 통해 Windows 10으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="658f6-108">Windows 장치를 Windows 10 Pro 크리에이터 업데이트로 업그레이드하는 방법에 대한 자세한 내용은 [Windows Pro 크리에이터 업데이트로 Windows 장치 업그레이드](upgrade-to-windows-pro-creators-update.md)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="658f6-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="658f6-109">[장치가 AZURE AD에 연결 되었는지 확인](#verify-the-device-is-connected-to-azure-ad) 을 참조 하 여 업그레이드가 있는지 확인 하거나 업그레이드가 제대로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="658f6-110">Microsoft 365에 Windows를 연결 하는 방법에 대 한 간단한 비디오를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="658f6-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="658f6-111">이 비디오를 통해 도움이 되는 경우에는 [소규모 기업을 위한 전체 교육 시리즈 및 Microsoft 365에 새로 소개 하](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="658f6-112">Windows 10 장치를 조직의 Azure AD에 연결</span><span class="sxs-lookup"><span data-stu-id="658f6-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="658f6-113">조직의 모든 Windows 장치가 Windows 10 Pro 크리에이터 업데이트로 업그레이드 되었거나 이미 Windows 10 Pro 작성자 업데이트를 실행 하 고 있는 경우 이러한 장치를 조직의 Azure Active Directory에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="658f6-114">장치가 연결 되 면 Microsoft 365 비즈니스 구독의 일부인 Windows 10 Business로 자동으로 업그레이드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="658f6-115">최신 또는 새로 업그레이드된 Windows 10 Pro 장치의 경우</span><span class="sxs-lookup"><span data-stu-id="658f6-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="658f6-116">Windows 10 Pro 크리에이터 업데이트를 실행하는 새로운 장치 또는 Windows 10 Pro 크리에이터 업데이트로 업그레이드했지만 Windows 10 장치 설정을 완료하지 않은 장치의 경우 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="658f6-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="658f6-117">**어떻게 설정하시겠어요?** 페이지에 도달할 때까지 Windows 10 장치 설정을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="658f6-119">해당 페이지에서 **조직용 설정**을 선택한 다음 Microsoft 365 Business 사용자 이름과 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="658f6-120">Windows 10 장치 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="658f6-p103">설정을 완료하면 사용자가 조직의 Azure AD에 연결됩니다. [장치가 Azure AD에 연결되었는지 확인](#verify-the-device-is-connected-to-azure-ad)을 참조하여 연결을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="658f6-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="658f6-123">Windows 10 Pro를 이미 설치하여 운영 중인 장치의 경우</span><span class="sxs-lookup"><span data-stu-id="658f6-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="658f6-124">**Azure AD에 사용자 연결:**</span><span class="sxs-lookup"><span data-stu-id="658f6-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="658f6-125">사용자의 Windows PC에서 Windows 10 Pro 버전 1703(크리에이터 업데이트)([필수 조건](pre-requisites-for-data-protection.md) 확인)을 사용하는 경우 Windows 로고와 설정 아이콘을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="658f6-127">**설정**에서 **계정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="658f6-129">**사용자 정보** 페이지에서 **회사 또는 학교 액세스** \> **연결**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="658f6-131">**회사 또는 학교 계정 설정** 대화 상자의 **대체 작업**에서 **Azure Active Directory에 이 장치 가입**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="658f6-133">**로그인 시작** 페이지에 회사 또는 학교 계정을 입력합니다 \> **다음**.</span><span class="sxs-lookup"><span data-stu-id="658f6-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="658f6-134">**암호 입력** 페이지에서 암호를 입력합니다 \> **로그인**.</span><span class="sxs-lookup"><span data-stu-id="658f6-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="658f6-136">**조직** 확인 페이지에서 정보가 올바른지 확인 하 고 **참가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="658f6-p104">**완료되었습니다!** 페이지에서 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="658f6-140">비즈니스용 OneDrive에 파일을 업로드 한 경우 다시 동기화 하세요.</span><span class="sxs-lookup"><span data-stu-id="658f6-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="658f6-141">타사 도구를 사용 하 여 프로필 및 파일을 마이그레이션한 경우이를 새 프로필과 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="658f6-142">장치가 Azure AD에 연결되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="658f6-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="658f6-p106">동기화 상태를 확인하려면 **설정**의 **회사 또는 학교 액세스** 페이지에서 \<조직 이름\> _ **에 연결** _ 영역에서 클릭하여 **정보** 및 **연결 해제** 버튼을 표시합니다. **정보**를 클릭해 동기화 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="658f6-145">동기화 상태 페이지에서 동기화를 클릭하여 최신 모바일 장치 관리 정책을 PC로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="658f6-146">Microsoft 365 Business 계정을 사용 하려면 Windows **시작** 단추로 이동 하 여 현재 계정 사진을 마우스 오른쪽 단추로 클릭 한 다음 **계정을 전환**합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-146">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="658f6-147">조직 전자 메일 및 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-147">Sign in by using your organization email and password.</span></span>
  
![동기화 상태를 보려면 정보 버튼을 클릭합니다.](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="658f6-149">장치가 Windows 10 Business로 업그레이드 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="658f6-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="658f6-150">Azure AD에 연결된 Windows 10 장치가 Microsoft 365 Business 구독의 일부로서 Windows 10 Business로 업그레이드 되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="658f6-151">**설정** \> **시스템** \> **정보**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="658f6-152">**버전**이 **Windows 10 Business**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="658f6-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="658f6-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="658f6-154">Next steps</span></span>

<span data-ttu-id="658f6-155">모바일 장치를 설정하려면 [Microsoft 365 Business 사용자를 위한 모바일 장치 설정](set-up-mobile-devices.md)을 참조하고 장치 보호 또는 앱 보호를 설정하려면 [Microsoft 365 Business 관리](manage.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="658f6-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="658f6-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="658f6-156">See also</span></span>

[<span data-ttu-id="658f6-157">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="658f6-157">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
