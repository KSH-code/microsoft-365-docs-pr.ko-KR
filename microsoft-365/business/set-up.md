---
title: Microsoft 365 Business Premium 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 도메인 및 사용자 추가, 보안 정책 설정 등 Microsoft 365 Business Premium의 설치 단계를 알아봅니다.
ms.openlocfilehash: 89186fbd00e47385f0320c45f7fc44c258742aa3
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785703"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="05595-103">설치 마법사에서 Microsoft 365 Business Premium 설정</span><span class="sxs-lookup"><span data-stu-id="05595-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="05595-104">이 비디오에서 Microsoft 365 Business Premium 설치에 대 한 개요를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="05595-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="05595-105">이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05595-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="05595-106">도메인, 사용자 및 정책 설정 추가</span><span class="sxs-lookup"><span data-stu-id="05595-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="05595-107">Microsoft 365 Business Premium을 구입 하는 경우 소유 하 고 있는 도메인을 사용 하거나 [등록](sign-up.md)중에 하나를 구입 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="05595-108">등록할 때 새 도메인을 구매한 경우 도메인은 모두 설정 되며 이동 하 여 [사용자를 추가 하 고 라이선스를 할당할](#add-users-and-assign-licenses)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="05595-109">로그인 개인 설정에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="05595-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="05595-110">전역 관리자 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="05595-111">**설정으로 이동을** 선택 하 여 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-111">Choose **Go to setup** to start the wizard.</span></span>

    ![설정으로 이동을 선택 합니다.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="05595-113">**Office 앱 설치** 페이지에서 필요에 따라 컴퓨터에 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="05595-114">**도메인 추가** 단계에서 사용 하려는 도메인 이름 (예 contoso.com)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="05595-115">등록할 때 도메인을 구매한 경우에 **는 추가 도메인** 단계가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="05595-116">대신 [사용자 추가](#add-users-and-assign-licenses) 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![로그인 페이지를 개인 설정 합니다.](../media/adddomain.png)

    
4. <span data-ttu-id="05595-118">마법사의 단계에 따라 도메인을 소유 하 고 있는지 확인 하는 [dns 호스팅 공급자 (Office 365)에 dns 레코드를 만듭니다](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) .</span><span class="sxs-lookup"><span data-stu-id="05595-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="05595-119">도메인 호스트를 알고 있는 경우에는 [호스트 관련 지침](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05595-119">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="05595-120">호스팅 공급자가 GoDaddy 이거나 [도메인 연결](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)을 사용 하 여 다른 호스트를 사용 하는 경우에는 프로세스가 쉬우며 자동으로 로그인 하 라는 메시지가 표시 되며 사용자가 대신 인증을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![GoDaddy 액세스 확인 페이지에서 권한 부여를 선택 합니다.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="05595-122">사용자 추가 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="05595-122">Add users and assign licenses</span></span>

<span data-ttu-id="05595-123">마법사에서 사용자를 추가할 수 있지만 나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-123">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="05595-124">또한 로컬 도메인 컨트롤러가 있는 경우 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)를 사용 하 여 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="05595-125">마법사에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="05595-125">Add users in the wizard</span></span>

<span data-ttu-id="05595-126">마법사에서 추가 하는 모든 사용자는 Microsoft 365 Business Premium 라이선스를 자동으로 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![마법사의 새 사용자 추가 페이지 스크린샷](../media/addnewuserspage.png)

1. <span data-ttu-id="05595-128">Microsoft 365 Business Premium 구독에 기존 사용자가 있는 경우 (예: Azure AD Connect를 사용한 경우) 지금 라이선스를 할당 하는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05595-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="05595-129">해당 사용자에게도 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="05595-130">사용자를 추가한 후에는 추가한 새 사용자와 자격 증명을 공유 하는 옵션도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05595-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="05595-131">자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="05595-132">도메인 연결</span><span class="sxs-lookup"><span data-stu-id="05595-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="05595-133">. Onmicrosoft 도메인을 사용 하도록 선택한 경우 또는 Azure AD Connect를 사용 하 여 사용자를 설정 하는 경우에는이 단계가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="05595-134">서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="05595-135">설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="05595-136">그렇지 [않은 경우 이름 서버를 변경 하 여 도메인 등록 기관에 Office 365을 설정](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="05595-137">기존 웹 사이트와 같이 기존 DNS 레코드가 있지만 DNS 호스트가 [도메인 연결](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)을 사용 하도록 설정 된 경우 **에는 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="05595-138">**온라인 서비스 선택** 페이지에서 기본값을 모두 적용 하 고 **다음**을 선택한 다음, DNS 호스트의 페이지에서 **권한 부여** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="05595-139">다른 DNS 호스트 (도메인 연결에 대해 사용 하도록 설정 되지 않음)의 기존 DNS 레코드가 있는 경우에는 자체 DNS 레코드를 관리 하 여 기존 서비스가 계속 연결 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="05595-140">자세한 내용은 [도메인 기본 사항을](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05595-140">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![레코드 활성화 페이지](../media/activaterecords.png)

2. <span data-ttu-id="05595-142">마법사의 단계를 따르고 전자 메일 및 기타 서비스가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05595-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="05595-143">조직 보호</span><span class="sxs-lookup"><span data-stu-id="05595-143">Protect your organization</span></span> 

<span data-ttu-id="05595-144">마법사에서 설정한 정책이 *모든 사용자*라는 [보안 그룹](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) 에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05595-144">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="05595-145">관리 센터에서 정책을 할당 하는 추가 그룹을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="05595-146">**고급 사이버 위협 으로부터 보호를 강화**하려면 기본값을 사용 하 여 [Office 365 advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 이 office 앱에서 파일 및 링크를 검사 하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![보호 기능 향상 페이지 스크린샷](../media/increasetreatprotection.png)


2. <span data-ttu-id="05595-148">**중요 한 데이터의 누출 방지** 페이지에서 OFFICE 365 DLP (데이터 손실 방지)를 설정 하 여 office 앱에서 중요 한 데이터를 추적 하 고 조직 외부에서 실수로 공유 하지 않도록 하는 기본값을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="05595-149">**비즈니스용 Office의 데이터 보호** 페이지에서 모바일 앱 관리를 유지 하 고 설정을 확장 하 고 검토 한 다음, **모바일 앱 관리 정책 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Mobile 용 Office의 데이터 보호 페이지 스크린샷](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="05595-151">Windows 10 Pc 보안</span><span class="sxs-lookup"><span data-stu-id="05595-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="05595-152">왼쪽 탐색 창에서 **설치** 를 선택 하 고 **로그인 및 보안**에서 **Windows 10 컴퓨터 보안**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="05595-153">시작 하려면 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05595-153">Choose **View** to get started.</span></span> <span data-ttu-id="05595-154">전체 지침은 [Windows 10 컴퓨터 보안](secure-win-10-pcs.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05595-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="05595-155">Office 365 클라이언트 앱 배포</span><span class="sxs-lookup"><span data-stu-id="05595-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="05595-156">설치 중에 Office 앱을 자동으로 설치 하도록 선택한 경우 앱은 사용자가 자신의 Windows 장치에서 Azure AD에 로그인 한 후 회사 자격 증명을 사용 하 여 Windows 10 장치에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05595-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="05595-157">모바일 iOS 또는 Android 장치에 Office를 설치 하려면 [Set up 모바일 장치 For Microsoft 365 Business Premium users](set-up-mobile-devices.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05595-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="05595-158">Office를 개별적으로 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05595-158">You can also install Office individually.</span></span> <span data-ttu-id="05595-159">자세한 내용은 [PC 또는 Mac에 Office 설치](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05595-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="05595-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05595-160">See also</span></span>

[<span data-ttu-id="05595-161">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="05595-161">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
