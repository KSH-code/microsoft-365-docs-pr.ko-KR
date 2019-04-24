---
title: 설정 마법사를 사용하여 Microsoft 365 Business 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 4 단계를 완료 하 여 Microsoft 365 Business를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283926"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="5f6f5-103">설정 마법사를 사용하여 Microsoft 365 Business 설정</span><span class="sxs-lookup"><span data-stu-id="5f6f5-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="5f6f5-104">아래의 1-4 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="5f6f5-105">Microsoft 365 Business 설정</span><span class="sxs-lookup"><span data-stu-id="5f6f5-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="5f6f5-106">온-프레미스 Active Directory가 없는 경우 Microsoft 365 Business를 설정 하는 방법에 대 한 비디오를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="5f6f5-107">설정 단계에는 로컬 Active Directory를 포함 하는 설치에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-107">The set-up steps include information for setups that include local Active Directory.</span></span> <span data-ttu-id="5f6f5-108">계속 해 서 도메인에 가입 된 장치에 액세스 하려면 다음 문서를 참조 하 여 두 가지 방법을 사용 하 고 설치 마법사를 실행 하기 전에 해당 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-108">If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="5f6f5-109">도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="5f6f5-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="5f6f5-110">-이것이 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="5f6f5-111">Microsoft 365 Business의 Azure AD에 가입 된 장치에서 온-프레미스 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="5f6f5-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="5f6f5-112">1 단계: 로그인 개인 설정</span><span class="sxs-lookup"><span data-stu-id="5f6f5-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="5f6f5-p102">전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business](https://portal.microsoft.com)에 로그인합니다. **관리** 타일을 선택하여 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="5f6f5-115">관리 센터에서 **설정 시작**(상태에 따라 **설정 계속**이 표시될 수 있음)을 선택하여 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="5f6f5-116">사용할 도메인 이름(예: contoso.com)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="5f6f5-117">예를 들어 Azure AD Connect를 사용하는 동안 도메인을 확인한 경우에도 도메인을 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-117">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example.</span></span> <span data-ttu-id="5f6f5-118">Azure AD Connect를 사용 하 여 도메인을 확인 한 경우에는 다음 두 단계가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-118">The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="5f6f5-119">마법사의 단계에 따라 도메인을 소유 하 고 있는지 확인 하는 [dns 호스팅 공급자 (Office 365)에 dns 레코드를 만듭니다](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) .</span><span class="sxs-lookup"><span data-stu-id="5f6f5-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="5f6f5-120">비디오의 예 [: 새 관리 센터에서 Office 365 설치](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-120">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span></span> <span data-ttu-id="5f6f5-121">이 비디오에는 Microsoft 365 Business의 데이터 보호 단계는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-121">Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="5f6f5-123">2 단계: 사용자 추가 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5f6f5-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="5f6f5-124">여기에서 사용자를 추가하거나 관리 센터에서 [나중에 사용자를 추가](add-users-m365b.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="5f6f5-125">추가된 사용자는 모두 Microsoft 365 Business 라이선스를 자동으로 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="5f6f5-p105">Microsoft 365 Business 구독에 기존 사용자가 있는 경우(예를 들어 Azure AD Connect를 사용한 경우) 해당 사용자에게 라이선스를 할당하는 옵션이 여기에 표시됩니다. 해당 사용자에게도 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="5f6f5-p106">새로 추가한 사용자와 자격 증명을 공유하는 옵션도 여기에 표시됩니다. 자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="5f6f5-130">전자 메일 메시지 마이그레이션을 건너뛰고 **전자 메일 메시지 마이그레이션** 페이지에서 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="5f6f5-131">다른 전자 메일 공급자에서 전환 중이 고 나중에 데이터를 복사 하려는 경우 [전자 메일 및 연락처를 Office 365로 마이그레이션할](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="5f6f5-133">3 단계: 도메인 연결</span><span class="sxs-lookup"><span data-stu-id="5f6f5-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="5f6f5-134">. onmicrosoft 도메인을 사용 하도록 선택한 경우 또는 Azure AD Connect를 사용 하는 경우에는이 단계가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="5f6f5-135">서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="5f6f5-136">설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="5f6f5-137">그렇지 [않은 경우 이름 서버를 변경 하 여 도메인 등록 기관에 Office 365을 설정](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="5f6f5-138">전자 메일 및 기타 서비스가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="5f6f5-139">4 단계: 장치 및 작업 파일 관리</span><span class="sxs-lookup"><span data-stu-id="5f6f5-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="5f6f5-140">**모바일 장치의 작업 파일 보호** 페이지에서 **장치를 분실하거나 도난당한 경우 작업 파일 보호** 및 **사용자가 모바일 장치에서 Office 파일에 액세스하는 방법 관리**를 모두 **켜기**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-140">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**.</span></span> <span data-ttu-id="5f6f5-141">각 설정 옆의 갈매기형 펼침 단추를 클릭 하 여 각 하위 설정에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-141">You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="5f6f5-142">이제 [Office 앱을 설치](set-up-mobile-devices.md) 하 고 Microsoft 365 비즈니스 자격 증명을 사용 하 여 인증 하는 즉시 iOS 및 Android 장치에서 사용이 허가 된 모든 사용자의 작업 파일이 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="5f6f5-144">**windows 10 장치 구성 설정** 페이지에서 **보안 windows 10 장치** 설정을 켜기로 설정 합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5f6f5-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="5f6f5-145">또한 옆에 있는 펼침을 클릭 하 여 각 하위 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="5f6f5-146">모든 사용자가 windows 10 컴퓨터를 보유 하 고 있고 기존 office가 설치 되지 않았거나 간편 실행 office 설치를 사용 하지 않는 경우 **windows 10 장치에 Office 설치** 설정을 **Yes** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-146">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs.</span></span> <span data-ttu-id="5f6f5-147">그렇지 않은 경우에는이 옵션을 **No**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-147">If this is not the case, set this option to **No**.</span></span> <span data-ttu-id="5f6f5-148">사용자 컴퓨터를 준비한 후에 관리 센터에서 나중에 [Office를 자동으로 설치할](auto-install-or-uninstall-office.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-148">You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers.</span></span> <span data-ttu-id="5f6f5-149">자세한 내용은 [Office 클라이언트 설치 준비](prepare-for-office-client-deployment.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-149">For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="5f6f5-150">windows 10 장치에서 사용이 허가 된 사용자의 작업 파일은 [windows 10 장치](set-up-windows-devices.md) 를 microsoft 365 Business Azure AD 도메인에 가입 하거나 microsoft 365에 동시에 참가 하는 동안 [새 컴퓨터에 windows 10을 설치](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) 하는 즉시 예측 됩니다. 비즈니스 Azure AD 도메인</span><span class="sxs-lookup"><span data-stu-id="5f6f5-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="5f6f5-151">**다음** 을 클릭 하 고 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="5f6f5-152">이 단계에서는 경험을 개선 하는 데 도움이 되는 우리 의견을 남겨 주세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="5f6f5-154">추가 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5f6f5-154">Additional security settings</span></span>

<span data-ttu-id="5f6f5-155">설치 마법사의 보안 및 규정 준수 설정 외에 다음과 같은 추가 설정을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="5f6f5-156">안전 하지 않은 첨부 파일에 대 한 보호 설정</span><span class="sxs-lookup"><span data-stu-id="5f6f5-156">Set up protection against unsafe attachments.</span></span> <span data-ttu-id="5f6f5-157">**Advanced Threat Protection** (ATP) 악성 콘텐츠를 식별 한 다음 안전 하지 않은 첨부 파일의 배달을 차단 하 여 피싱 수법 및 랜 섬 웨어 감염 으로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-157">**Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="5f6f5-158">첨부 파일 보호를 활성화 하려면 [Office 365 ATP 안전 첨부 파일 정책을 설정](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-158">To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="5f6f5-159">사용자가 악성 링크를 클릭 하면 환경을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-159">Protect your environment when users click malicious links.</span></span> <span data-ttu-id="5f6f5-160">ATP는 사용자가 전자 메일을 클릭할 때 링크를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-160">ATP examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="5f6f5-161">링크가 안전 하지 않은 경우 사용자에 게 사이트를 방문 하지 않거나 사이트가 차단 되었음을 알리는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-161">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="5f6f5-162">이를 통해 피싱 수법을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-162">This helps protect against phishing schemes.</span></span> <span data-ttu-id="5f6f5-163">[office 365 atp 안전한 링크 정책을 설정](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) 하거나 [office 365 atp 안전한 링크 정책을 설정](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-163">[Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="5f6f5-164">사용자의 전체 사서함을 **소송 보존 상태로**두어 삭제 된 항목을 비롯 한 모든 사서함 콘텐츠를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-164">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**.</span></span> <span data-ttu-id="5f6f5-165">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="5f6f5-165">For instructions, see</span></span> 
- <span data-ttu-id="5f6f5-166">[Exchange Online 보관을 사용 하 여 전자 메일 보존을 설정](security-features.md#set-up-email-retention-with-exchange-online-archiving)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="5f6f5-167">보존 기간이 끝나면 사용자 지정 된 **보존 정책을**설정 하 여 특정 시간 동안 보존 하거나 콘텐츠를 영구적으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-167">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="5f6f5-168">사용자 지정 된 보존 정책을 증권 및 준수 센터에서 사용 하도록 설정 하 고, **데이터 관리** \> **보존**으로 이동한 다음 마법사의 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-168">You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard.</span></span> <span data-ttu-id="5f6f5-169">자세한 내용은 [보존 정책 개요](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-169">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="5f6f5-170">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5f6f5-170">Next steps</span></span>

<span data-ttu-id="5f6f5-171">라이선스를 보유한 사용자는 이제 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="5f6f5-172">[Microsoft 365 Business 사용자를 위한 Windows 장치 설정](set-up-windows-devices.md) 및 [Microsoft 365 Business 사용자를 위한 모바일 장치 설정](set-up-mobile-devices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="5f6f5-173">장치 및 앱 보호 정책을 설정하는 방법과 사용자 장치에서 데이터를 제거하는 방법에 대한 항목의 링크를 보려면 [Microsoft 365 Business 관리](manage.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6f5-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


