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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 4 단계를 완료 하 여 Microsoft 365 비즈니스를 설정 하는 방법에 알아봅니다.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869725"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="23764-103">설정 마법사를 사용하여 Microsoft 365 Business 설정</span><span class="sxs-lookup"><span data-stu-id="23764-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="23764-104">1-4 아래 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="23764-105">Microsoft 365 Business 설정</span><span class="sxs-lookup"><span data-stu-id="23764-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="23764-106">온-프레미스 Active Directory 없을 때 Microsoft 365 비즈니스를 설정 하는 방법에 대 한 비디오를 시청 합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="23764-p101">설정 단계에는 로컬 Active Directory를 포함 하는 설치에 대 한 정보를 포함 합니다. 도메인에 가입 된 장치에 액세스 하 여 계속 하려면 두 다른 방법 사용 하는, 사용에 대 한 다음 문서를 읽기 하 고 설치 마법사를 실행 하기 전에 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="23764-109">Microsoft 365 비즈니스에서 관리 되는 도메인 가입 Windows 10 장치를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="23764-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="23764-110">-이 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="23764-111">Access 온-프레미스 Microsoft 365 비즈니스에서 Azure AD에 가입 된 장치에서 리소스</span><span class="sxs-lookup"><span data-stu-id="23764-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="23764-112">1 단계: 사용자 로그인에 맞게 설정</span><span class="sxs-lookup"><span data-stu-id="23764-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="23764-p102">전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business](https://portal.microsoft.com)에 로그인합니다. **관리** 타일을 선택하여 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="23764-115">관리 센터에서 **설정 시작**(상태에 따라 **설정 계속**이 표시될 수 있음)을 선택하여 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="23764-116">사용할 도메인 이름(예: contoso.com)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="23764-p103">계속 진행 하 고 예 Azure AD 연결을 사용 하는 동안 확인 한 경우에 도메인을 입력 합니다. 도메인을 확인 하려면 Azure AD 연결을 사용 하는 경우에 다음 두 단계 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="23764-119">해당 도메인의 소유를 확인 하는 [DNS 레코드 만들기 Office 365에 대 한 모든 DNS 호스팅 공급자에서](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) 마법사의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="23764-p104">예제 비디오를 볼 수 [비디오: 새 관리 센터에서 설치 프로그램 Office 365](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)합니다. 참고가이 비디오는 Microsoft 365 비즈니스 데이터 보호 단계를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="23764-123">2 단계: 사용자 추가 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="23764-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="23764-124">여기에서 사용자를 추가하거나 관리 센터에서 [나중에 사용자를 추가](add-users-m365b.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="23764-125">추가된 사용자는 모두 Microsoft 365 Business 라이선스를 자동으로 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="23764-p105">Microsoft 365 Business 구독에 기존 사용자가 있는 경우(예를 들어 Azure AD Connect를 사용한 경우) 해당 사용자에게 라이선스를 할당하는 옵션이 여기에 표시됩니다. 해당 사용자에게도 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="23764-p106">새로 추가한 사용자와 자격 증명을 공유하는 옵션도 여기에 표시됩니다. 자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="23764-130">전자 메일 메시지 마이그레이션을 건너뛰고 **전자 메일 메시지 마이그레이션** 페이지에서 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="23764-131">다른 전자 메일 공급자에서 이동 하는 데이터를 나중에 복사 하려면 하는 경우 [Migrate 전자 메일 및 Office 365에 대화 상대를](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="23764-133">3 단계: 도메인에 연결</span><span class="sxs-lookup"><span data-stu-id="23764-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="23764-134">.Onmicrosoft 도메인을 사용 하 여 선택한 또는 Azure AD 연결을 사용 하는 경우이 단계를 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="23764-135">서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="23764-p107">설치 마법사는 일반적으로 해당 등록자를 감지 하 고 등록자 웹사이트에서 NS 레코드를 업데이트 하기 위한 단계별 지침에 대 한 링크를 제공 합니다. 그렇지 않은 경우 [모든 도메인 등록자를 사용 하 여 Office 365를 설정 하려면 이름 서버 변경](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="23764-138">전자 메일 및 기타 서비스가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="23764-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="23764-139">4 단계: 장치를 관리 하 고 파일 작업</span><span class="sxs-lookup"><span data-stu-id="23764-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="23764-p108">**모바일 장치에서 암호로 보호 작업 파일** 에서 페이지 **전환** **장치는 분실 또는 도난당 한 경우 암호로 보호 작업 파일** 및 설정 **사용자가 모바일 장치에서 Office 파일을 액세스 하는 방식을 관리** 를 모두 설정합니다. 각 하위 설정 각 설정 옆에 있는 갈매기형 수를 클릭 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="23764-142">사용이 허가 된 사용자의 작업 파일을 모두 이제와 구성 설정은 iOS와 Android 장치에 자신이 되는 즉시 [Office 앱 설치](set-up-mobile-devices.md) (및 해당 Microsoft 365 비즈니스 자격 증명을 가진 인증).</span><span class="sxs-lookup"><span data-stu-id="23764-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="23764-144">**Windows 10 설정 장치 구성** 페이지에서 **Windows 10 장치 보안** 설정을 **On**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="23764-145">각 하위 설정 옆에 있는 펼침 단추를 클릭 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="23764-p109">**Windows 10 장치에서 Office 설치** 설정을 **예** Windows 10 컴퓨터를 가진 모든 사용자에 게 하 고 두 없는 기존 Office 설치 하는 경우 또는 간편 실행 Office 설치로 설정 합니다. 없는 경우이 옵션을 **No**로 설정 합니다. 사용자 컴퓨터를 준비한 후 나중에 관리 센터에서에서 [자동으로 Office를 설치할](auto-install-or-uninstall-office.md) 수 있습니다. 자세한 내용은 [Office 클라이언트 설치에 대 한 준비](prepare-for-office-client-deployment.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="23764-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="23764-150">Windows 10 장치에서 사용이 허가 된 사용자의 작업 파일을 자신이 되는 즉시 예측할 수는 365 Microsoft 비즈니스 Azure AD 도메인 또는 Microsoft 365를 동시에 연결 하는 동안 [새 컴퓨터에 Windows 10 설치](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) 에 [자신의 Windows 10 장치에 참가](set-up-windows-devices.md) 비즈니스 Azure AD 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="23764-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="23764-151">**다음** 을 클릭 설치가 완료 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="23764-152">두십시오 우리 피드백을 환경을 개선 하기 위한이 단계에서.</span><span class="sxs-lookup"><span data-stu-id="23764-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="23764-154">추가 보안 설정</span><span class="sxs-lookup"><span data-stu-id="23764-154">Additional security settings</span></span>

<span data-ttu-id="23764-155">보안 및 규정 준수 설정을 설치 마법사의 외에 다음과 같은 추가 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="23764-p110">안전 하지 않은 첨부 파일에 대 한 보호를 설정 합니다. **고급 위협 보호** (ATP) 악의적인 콘텐츠를 식별 하 고 피싱 구성표 및 ransomware 감염 으로부터 시스템을 보호할 수 안전 하지 않은 첨부 파일의 배달을 차단 합니다. 첨부 파일 보호 기능을 활성화 하려면 [Office 365 ATP 안전한 첨부 정책 설정](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="23764-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="23764-p111">사용자가 악의적인 링크를 클릭할 때 환경을 보호 합니다. ATP은 사용자가 해당를 클릭할 때 전자 메일의 링크를 검사 합니다. 링크가 안전 하지 않으면 사용자가 사이트를 방문 하 여 하지 경고가 표시 하거나 사이트 차단 된 관련 정보를 받아보십시오. 피싱을 막을 수 있습니다. [Office 365 ATP 안전한 링크 정책을 설정](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) 하거나 [Office 365 ATP 안전한 링크 정책을 설정](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="23764-p112">사용자의 전체 사서함을 **소송 보존**에 배치 하 여 삭제 된 항목을 포함 하는 모든 사서함 콘텐츠를 유지할 수 있습니다. 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="23764-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="23764-166">[Exchange Online 보관 된 전자 메일 보존 설정](security-features.md#set-up-email-retention-with-exchange-online-archiving)합니다.</span><span class="sxs-lookup"><span data-stu-id="23764-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="23764-p113">설정 사용자 지정 된 **보존 정책**등을 특정 시간 동안 보존 하거나 보존 기간이 끝날 때 콘텐츠를 영구적으로 삭제 합니다. 유가 증권 및 **데이터 관리 방식** 으로 이동 준수 센터의 사용자 지정 된 보존 정책 사용 하도록 설정할 수 \> **보존**한 다음 마법사의 단계를 따릅니다. 자세한 내용은, [보존 정책 개요](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="23764-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="23764-170">다음 단계</span><span class="sxs-lookup"><span data-stu-id="23764-170">Next steps</span></span>

<span data-ttu-id="23764-171">라이선스를 보유한 사용자는 이제 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23764-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="23764-172">[Microsoft 365 Business 사용자를 위한 Windows 장치 설정](set-up-windows-devices.md) 및 [Microsoft 365 Business 사용자를 위한 모바일 장치 설정](set-up-mobile-devices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23764-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="23764-173">장치 및 앱 보호 정책을 설정하는 방법과 사용자 장치에서 데이터를 제거하는 방법에 대한 항목의 링크를 보려면 [Microsoft 365 Business 관리](manage.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23764-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


