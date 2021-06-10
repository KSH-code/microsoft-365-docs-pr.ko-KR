---
title: 사용자용 Windows 장치 Microsoft 365 Business Premium 설정
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 중앙 집중식 Windows 제어를 Windows 10 Pro Microsoft 365 Business Premium 실행되는 디바이스를 설정하십시오.
ms.openlocfilehash: 7a9c75f6ec14605225d40c103c18e62937e773bf
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635877"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="b4dcc-103">사용자용 Windows 장치 Microsoft 365 Business Premium 설정</span><span class="sxs-lookup"><span data-stu-id="b4dcc-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b4dcc-104">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="b4dcc-104">Before you begin</span></span>

<span data-ttu-id="b4dcc-105">Windows 사용자를 위해 Windows Microsoft 365 Business Premium 장치를 설정하기 전에 모든 Windows 장치가 Windows 10 Pro 버전 1703(크리에이터스 업데이트)을 실행하고 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="b4dcc-106">Windows 10 Pro 클라우드 서비스 및 장치 관리 기능 집합인 Windows 10 Business 배포하기 위한 선행 구성 Windows 10 Pro 관리 및 보안 제어를 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="b4dcc-107">Windows 7 Pro, Windows 8 Pro Windows 또는 Windows 8.1 Pro 7을 실행하는 Microsoft 365 Business Premium 디바이스가 있는 경우 Microsoft 365 Business Premium 업그레이드를 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="b4dcc-108">Windows 장치를 Windows 10 Pro 크리에이터 업데이트로 업그레이드하는 방법에 대한 자세한 내용은 [Windows Pro 크리에이터 업데이트로 Windows 장치 업그레이드](upgrade-to-windows-pro-creators-update.md)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="b4dcc-109">디바이스가 [Azure AD에](#verify-the-device-is-connected-to-azure-ad) 연결되어 있는지 확인을 참조하여 업그레이드가 있는지 확인하거나 업그레이드가 올바르게 진행된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a><span data-ttu-id="b4dcc-110">시청: 커넥트 PC를 Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b4dcc-110">Watch: Connect your PC to Microsoft 365 Business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="b4dcc-111">이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 완전한 교육 시리즈](../business-video/index.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="b4dcc-112">Windows 10 장치를 조직의 Azure AD에 연결</span><span class="sxs-lookup"><span data-stu-id="b4dcc-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="b4dcc-113">조직의 모든 Windows 장치가 Windows 10 Pro 크리에이터스 업데이트로 업그레이드되거나 Windows 10 Pro 크리에이터스 업데이트를 이미 실행 중인 경우 이러한 장치를 조직의 크리에이터스에 가입할 수 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="b4dcc-114">디바이스가 가입되고 나면 디바이스가 Windows 10 Business 구독의 일부인 Microsoft 365 Business Premium 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="b4dcc-115">최신 또는 새로 업그레이드된 Windows 10 Pro 장치의 경우</span><span class="sxs-lookup"><span data-stu-id="b4dcc-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="b4dcc-116">Windows 10 Pro 크리에이터 업데이트를 실행하는 새로운 장치 또는 Windows 10 Pro 크리에이터 업데이트로 업그레이드했지만 Windows 10 장치 설정을 완료하지 않은 장치의 경우 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="b4dcc-117">**어떻게 설정하시겠어요?** 페이지에 도달할 때까지 Windows 10 장치 설정을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="b4dcc-119">여기서 조직에 대해 설정 **을 선택한** 다음 조직에 대한 사용자 이름과 암호를 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="b4dcc-120">Windows 10 장치 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="b4dcc-p103">설정을 완료하면 사용자가 조직의 Azure AD에 연결됩니다. [장치가 Azure AD에 연결되었는지 확인](#verify-the-device-is-connected-to-azure-ad)을 참조하여 연결을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="b4dcc-123">Windows 10 Pro를 이미 설치하여 운영 중인 장치의 경우</span><span class="sxs-lookup"><span data-stu-id="b4dcc-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="b4dcc-124">**Azure AD에 사용자 연결:**</span><span class="sxs-lookup"><span data-stu-id="b4dcc-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="b4dcc-125">사용자의 Windows PC에서 Windows 10 Pro 버전 1703(크리에이터 업데이트)([필수 조건](pre-requisites-for-data-protection.md) 확인)을 사용하는 경우 Windows 로고와 설정 아이콘을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="b4dcc-127">**설정** 에서 **계정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="b4dcc-129">**사용자 정보** 페이지에서 **회사 또는 학교 액세스** \> **연결** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="b4dcc-131">**회사 또는 학교 계정 설정** 대화 상자의 **대체 작업** 에서 **Azure Active Directory에 이 장치 가입** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="b4dcc-133">**로그인 시작** 페이지에 회사 또는 학교 계정을 입력합니다 \> **다음**.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="b4dcc-134">**암호 입력** 페이지에서 암호를 입력합니다 \> **로그인**.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="b4dcc-136">조직 **페이지가 맞는지 확인 페이지에서** 정보가 올바른지 확인하고 참가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4dcc-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="b4dcc-137">모두 **설정되어 있습니다!**</span><span class="sxs-lookup"><span data-stu-id="b4dcc-137">On the **You're all set!**</span></span> <span data-ttu-id="b4dcc-138">page, chosse **Done**.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-138">page, chosse **Done**.</span></span>
  
   ![조직 화면에서 가입을 선택 합니다.](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="b4dcc-140">파일을 업로드하여 비즈니스용 OneDrive 다시 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="b4dcc-141">타사 도구를 사용하여 프로필 및 파일을 마이그레이션한 경우 이러한 도구를 새 프로필과 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="b4dcc-142">장치가 Azure AD에 연결되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="b4dcc-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="b4dcc-143">동기화 상태를 확인하려면 설정  직장 또는 학교 액세스 페이지에서 _  _에 연결 **영역을** 선택하여 정보 및 연결 끊기 단추를 \<organization name\>  **노출합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4dcc-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="b4dcc-144">정보를 **선택하면** 동기화 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="b4dcc-145">동기화 **상태 페이지에서** **동기화를** 선택하면 PC에 최신 모바일 장치 관리 정책을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="b4dcc-146">Microsoft 365 Business Premium 계정을 사용하려면 Windows 시작 단추로 이동하여 현재 계정 사진을 **마우스** 오른쪽 단추로 클릭한 다음 계정 전환 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4dcc-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="b4dcc-147">조직 전자 메일 및 암호를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-147">Sign in by using your organization email and password.</span></span>
  
![동기화 상태를 보려면 정보 버튼을 클릭합니다.](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="b4dcc-149">PC가 서버로 업그레이드되어 있는지 Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="b4dcc-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="b4dcc-150">Azure AD에 가입된 Windows 10 디바이스가 Windows 10 Business 구독의 일부로 Microsoft 365 Business Premium 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="b4dcc-151">**설정** \> **시스템** \> **정보** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="b4dcc-152">**버전** 이 **Windows 10 Business** 인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="b4dcc-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b4dcc-154">Next steps</span></span>

<span data-ttu-id="b4dcc-155">모바일 장치를 설정하려면 Microsoft 365 Business Premium 사용자를 위한 모바일 장치 설정 [,](set-up-mobile-devices.md)장치 보호 또는 앱 보호 정책을 설정하려면 비즈니스용 Microsoft 365 [관리를 참조하세요.](manage.md)</span><span class="sxs-lookup"><span data-stu-id="b4dcc-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="related-content"></a><span data-ttu-id="b4dcc-156">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="b4dcc-156">Related content</span></span>

<span data-ttu-id="b4dcc-157">[Microsoft 365 교육용 비디오(링크](../business-video/index.yml) 페이지)</span><span class="sxs-lookup"><span data-stu-id="b4dcc-157">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
