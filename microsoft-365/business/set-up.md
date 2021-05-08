---
title: Microsoft 365 Business Premium 설정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 도메인 및 사용자 추가, Microsoft 365 Business Premium 정책 설정 등을 포함하여 사용자 지정에 대한 설정 단계를 검색합니다.
ms.openlocfilehash: 37607b483686fc12ac6253ae9f693ec86c073c4e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245047"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="b296a-103">설치 Microsoft 365 Business Premium 설정</span><span class="sxs-lookup"><span data-stu-id="b296a-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="b296a-104">설치에 대한 개요를 확인하려면 이 Microsoft 365 Business Premium 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="b296a-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="b296a-105">도메인, 사용자 추가 및 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b296a-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="b296a-106">구매 Microsoft 365 Business Premium 소유한 도메인을 사용하거나 등록하는 동안 도메인을 구입할 [수 있습니다.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="b296a-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="b296a-107">등록할 때 새 도메인을 구입하면 도메인이 모두 설정되어 [사용자 추가 및 라이선스를 할당](#add-users-and-assign-licenses)으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="b296a-108">로그인 개인 설정을 위한 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="b296a-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="b296a-109">전역 관리자 자격 증명을 사용하여 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="b296a-110">**설정으로 이동** 을 선택해 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-110">Choose **Go to setup** to start the wizard.</span></span>

    ![설정으로 이동을 선택합니다.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="b296a-112">**Office 앱 설치** 페이지에서 컴퓨터에 선택적으로 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="b296a-113">**도메인 추가** 단계에서 사용할 도메인 이름(예: contoso.com)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b296a-114">등록할 때 도메인을 구입한 경우에는 **도메인 추가** 단계가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="b296a-115">대신 [사용자 추가](#add-users-and-assign-licenses)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Screenshot of the Personalize your sign-in page.](../media/adddomain.png)

    
4. <span data-ttu-id="b296a-117">마법사의 단계에 따라 도메인을 소유하고 Microsoft 365 DNS 호스팅 공급자에서 [DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 레코드 만들기를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="b296a-118">도메인 호스트를 알고 있는 경우 [호스트 관련 지침](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b296a-118">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="b296a-119">호스팅 공급자가 GoDaddy이거나 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)을 사용하는 다른 호스트를 사용하는 경우에는 프로세스가 간단하며, 자동으로 로그인하라는 메시지가 표시되고 Microsoft가 사용자를 대신하여 인증하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![GoDaddy 액세스 확인 페이지에서 승인을 선택합니다.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="b296a-121">사용자 추가 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="b296a-121">Add users and assign licenses</span></span>

<span data-ttu-id="b296a-122">마법사에서 사용자를 추가하거나 관리 센터에서 [나중에 사용자를 추가](../admin/add-users/add-users.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-122">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="b296a-123">또한 로컬 도메인 컨트롤러를 사용하는 경우 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)를 사용하여 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="b296a-124">마법사에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="b296a-124">Add users in the wizard</span></span>

<span data-ttu-id="b296a-125">마법사에서 추가하는 모든 사용자에게 자동으로 라이선스가 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b296a-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![마법사에서 새 사용자 추가 페이지의 스크린샷](../media/addnewuserspage.png)

1. <span data-ttu-id="b296a-127">Microsoft 365 Business Premium 구독에 기존 사용자가 있는 경우(예: Azure AD 커넥트 사용하는 경우) 라이선스를 사용자에게 지금 할당할 수 있는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="b296a-128">해당 사용자에게도 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="b296a-129">해당 사용자를 추가한 후 새로 추가한 사용자와 자격 증명을 공유하는 옵션도 여기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="b296a-130">자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="b296a-131">도메인 연결</span><span class="sxs-lookup"><span data-stu-id="b296a-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="b296a-132">.onmicrosoft 도메인을 사용하거나 Azure AD Connect를 사용하여 사용자를 설정하는 경우에는 이 단계가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="b296a-133">서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="b296a-134">설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="b296a-135">그렇지 않은 경우 도메인 등록 기관에서 이름 Microsoft 365 [변경합니다.](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="b296a-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="b296a-136">기존 웹 사이트와 같은 기존 DNS 레코드를 사용하지만 DNS 호스트를 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)에서 사용할 수 있는 경우 **레코드 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="b296a-137">**온라인 서비스 선택** 페이지에서 모든 기본값을 적용하고 **다음** 을 선택한 후 DNS 호스트의 페이지에서 **승인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="b296a-138">도메인 연결 사용이 설정되지 않은 다른 DNS 호스트에서 기존 DNS 레코드를 사용하는 경우 기존 서비스를 계속 연결할 수 있도록 DNS 레코드를 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="b296a-139">자세한 내용은 [도메인 기본 사항](/office365/admin/get-help-with-domains/dns-basics)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b296a-139">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![레코드 활성화 페이지.](../media/activaterecords.png)

2. <span data-ttu-id="b296a-141">마법사의 단계를 따르면 전자 메일 및 기타 서비스가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="b296a-142">조직 보호</span><span class="sxs-lookup"><span data-stu-id="b296a-142">Protect your organization</span></span> 

<span data-ttu-id="b296a-143">마법사에서 설정한 정책은 모든 사용자라는 [보안](/office365/admin/create-groups/compare-groups#security-groups) 그룹에 *자동으로 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="b296a-143">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="b296a-144">추가 그룹을 만들어 관리 센터에서 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="b296a-145">고급 사이버 위협으로부터 보호 강화에서 Advanced [Threat Protection이](../security/office-365-security/defender-for-office-365.md) 앱의 파일 및 링크를 Office 365 수 있는 기본값을 Office 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![보호 강화 페이지의 스크린샷.](../media/increasetreatprotection.png)


2. <span data-ttu-id="b296a-147">중요한  데이터 누출 방지 페이지에서 기본값을 수락하여 Office 365 DLP(데이터 손실 방지)를 설정하여 Office 앱에서 중요한 데이터를 추적하고 조직 외부에서 이러한 데이터를 실수로 공유하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="b296a-148">모바일용 Office 데이터 보호 **페이지에서** 모바일 앱 관리를 그대로 두고 설정을 확장하고 검토한 다음 모바일 앱 관리 정책 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b296a-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Screenshot of Protect data in Office for mobile page.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="b296a-150">Windows 10 PC 보안</span><span class="sxs-lookup"><span data-stu-id="b296a-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="b296a-151">왼쪽 검색 창에서  설치를 선택한 다음 로그인 및 보안에서 보안 컴퓨터 **Windows 10 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b296a-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="b296a-152">**보기를** 선택하면 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-152">Choose **View** to get started.</span></span> <span data-ttu-id="b296a-153">자세한 [지침은 Windows 10 컴퓨터](secure-win-10-pcs.md) 보안을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b296a-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="b296a-154">클라이언트 Office 365 앱 배포</span><span class="sxs-lookup"><span data-stu-id="b296a-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="b296a-155">설치 중에 Office 앱을 자동으로 설치하도록 선택한 경우 사용자가 Windows 장치에서 Azure AD에 로그인한 후 앱은 Windows 10 장치에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="b296a-156">모바일 iOS Office 장치에 설치하려면 사용자용 모바일 장치 [Microsoft 365 Business Premium 참조합니다.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="b296a-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="b296a-157">또한 개별적으로 설치 Office 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b296a-157">You can also install Office individually.</span></span> <span data-ttu-id="b296a-158">지침은 Office PC 또는 [Mac에](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b296a-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="b296a-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b296a-159">See also</span></span>

[<span data-ttu-id="b296a-160">Microsoft 365 Business 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="b296a-160">Microsoft 365 for business training videos</span></span>](../business-video/index.yml)
