---
title: Microsoft 365 Business Standard 설정
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Microsoft 365 Business Standard를 구입하면 본인 소유 도메인을 사용하거나 가입 중 도메인을 구매할 수 있습니다.
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393814"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="30122-103">Microsoft Business Standard 설정</span><span class="sxs-lookup"><span data-stu-id="30122-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="30122-104">로그인 개인 설정을 위한 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="30122-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="30122-105">Microsoft 365 Business Standard를 구입하면 사용자가 소유하고 있는 도메인을 사용하거나 등록할 때 도메인을 구입하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="30122-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="30122-106">등록할 때 새 도메인을 구입하면 도메인이 모두 설정되어 [사용자 추가 및 라이선스를 할당](#add-users-and-assign-licenses)으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="30122-107">전역 관리자 자격 증명을 사용하여 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="30122-108">**설정으로 이동** 을 선택해 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="30122-109">**Office 앱 설치** 페이지에서 컴퓨터에 선택적으로 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="30122-110">**도메인 추가** 단계에서 사용할 도메인 이름(예: contoso.com)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="30122-p101">등록할 때 도메인을 구입한 경우에는 **도메인 추가** 단계가 표시되지 않습니다. 대신 [사용자 추가](#add-users-and-assign-licenses)로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="30122-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="30122-113">마법사의 단계에 따라 도메인을 소유하고 있는지 확인하는 [DNS 호스팅 공급자에 상관없이 Office 365용 DNS 레코드 만들기](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="30122-114">도메인 호스트를 알고 있는 경우 [Microsoft 365에 도메인 추가](/microsoft-365/admin/setup/add-domain)도 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30122-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="30122-115">호스팅 공급자가 GoDaddy이거나 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)을 사용하는 다른 호스트를 사용하는 경우에는 프로세스가 간단하며, 자동으로 로그인하라는 메시지가 표시되고 Microsoft가 사용자를 대신하여 인증하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![GoDaddy 액세스 확인 페이지에서 승인을 선택합니다.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="30122-117">사용자 추가 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="30122-117">Add users and assign licenses</span></span>

<span data-ttu-id="30122-118">마법사에서 사용자를 추가하거나 관리 센터에서 [나중에 사용자를 추가](../add-users/add-users.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="30122-119">또한 로컬 도메인 컨트롤러를 사용하는 경우 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)를 사용하여 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="30122-120">마법사에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="30122-120">Add users in the wizard</span></span>

<span data-ttu-id="30122-121">마법사에서 추가한 모든 사용자에게 자동으로 Microsoft 365 Business Standard 라이선스가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="30122-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="30122-p104">Microsoft 365 Business Standard 구독에 기존 사용자가 있는 경우(예를 들어 Azure AD Connect를 사용한 경우) 해당 사용자에게 라이선스를 할당하는 옵션이 여기에 표시됩니다. 해당 사용자에게도 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="30122-p105">사용자를 추가한 후에는 새로 추가한 사용자와 자격 증명을 공유하는 옵션도 여기에 표시됩니다. 자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="30122-126">도메인 연결</span><span class="sxs-lookup"><span data-stu-id="30122-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="30122-127">.onmicrosoft 도메인을 사용하거나 Azure AD Connect를 사용하여 사용자를 설정하는 경우에는 이 단계가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="30122-128">서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="30122-129">설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="30122-130">링크를 제공받지 못한 경우에는 [도메인 등록 기관에서 이름 서버를 변경하여 Office 365 설정](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)을 합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="30122-131">기존 웹 사이트와 같은 기존 DNS 레코드를 사용하지만 DNS 호스트를 [도메인 연결](/office365/admin/get-help-with-domains/domain-connect)에서 사용할 수 있는 경우 **레코드 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="30122-132">**온라인 서비스 선택** 페이지에서 모든 기본값을 적용하고 **다음** 을 선택한 후 DNS 호스트의 페이지에서 **승인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="30122-p108">도메인 연결 사용이 설정되지 않은 다른 DNS 호스트에서 기존 DNS 레코드를 사용하는 경우 기존 서비스를 계속 연결할 수 있도록 DNS 레코드를 관리하는 것이 좋습니다. 자세한 내용은 [도메인 기본 사항](/office365/admin/get-help-with-domains/dns-basics)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30122-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="30122-135">마법사의 단계를 따르면 전자 메일 및 기타 서비스가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="30122-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="30122-136">등록 프로세스가 완료되면 관리 센터로 이동하여 마법사를 따라 Office 앱을 설치하고 도메인을 추가하며 사용자를 추가하고 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="30122-137">초기 설정을 완료한 후 관리 센터의 **설정** 페이지를 사용하여 구독과 함께 제공되는 서비스를 계속 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="30122-138">설정 마법사와 관리 센터 **설정** 페이지에 대한 자세한 내용은 [설정 마법사와 설정 페이지의 차이점](o365-setup-wizard-and-setup-page.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30122-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="30122-139">설정 완료</span><span class="sxs-lookup"><span data-stu-id="30122-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="30122-140">Outlook을 전자 메일로 설정</span><span class="sxs-lookup"><span data-stu-id="30122-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="30122-141">Windows 시작 메뉴에서 Outlook을 검색하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="30122-142">(Mac을 사용하는 경우 도구 모음에서 Outlook을 열거나 Finder를 사용하여 Outlook을 찾습니다.)</span><span class="sxs-lookup"><span data-stu-id="30122-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="30122-143">방금 Outlook을 설치한 경우 시작 페이지에서 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="30122-144">**파일** \> **정보** \> **계정 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="30122-145">Microsoft 전자 메일 주소를 입력하고 **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="30122-146">시청: 전자 메일용 Outlook 설정</span><span class="sxs-lookup"><span data-stu-id="30122-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="30122-147">[Outlook을 전자 메일로 설정](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)에서 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="30122-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="30122-148">전자 메일 가져오기</span><span class="sxs-lookup"><span data-stu-id="30122-148">Import email</span></span>

<span data-ttu-id="30122-149">다른 이메일 계정으로 Outlook을 사용하는 경우 이전 전자 메일, 일정 및 연락처를 새 Microsoft 365 계정으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="30122-150">**이전 전자 메일 내보내기**</span><span class="sxs-lookup"><span data-stu-id="30122-150">**Export your old email**</span></span>

    <span data-ttu-id="30122-151">Outlook에서 **파일** \> **열기 &amp; 내보내기** \> **가져오기/내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="30122-152">**파일로 내보내기** 를 선택하고 다음 단계를 수행하여 Outlook 데이터 파일(.pst) 및 하위 폴더를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="30122-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="30122-153">**이전 전자 메일 가져오기**</span><span class="sxs-lookup"><span data-stu-id="30122-153">**Import your old email**</span></span>

    <span data-ttu-id="30122-154">Outlook에서 다시 **파일** \> **열기 &amp; 내보내기** \> **가져오기/내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="30122-155">이번에는 **다른 프로그램 또는 파일에서 가져 오기** 를 선택하고 다음 단계에 따라 이전 이메일을 내보낼 때 생성한 백업 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="30122-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="30122-156">시청: 전자 메일 가져오기 및 리디렉션</span><span class="sxs-lookup"><span data-stu-id="30122-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="30122-157">[Outlook으로 전자 메일을 가져오기](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)에서 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="30122-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="30122-158">Exchange 관리 센터를 사용하여 모든 사용자의 전자 메일을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="30122-159">자세한 내용은 [여러 전자 메일 계정을 마이그레이션하는 방법](/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30122-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="30122-160">공용 웹 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="30122-160">Use a public website</span></span>

<span data-ttu-id="30122-161">Microsoft 365에는 비즈니스용 공용 웹 사이트가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30122-161">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="30122-162">공용 웹 사이트를 설정하려면 GoDaddy 또는 WIX와 같은 Microsoft 파트너를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="30122-162">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="30122-163">관리 센터에서 **리소스** 로 이동한 다음, **공용 웹 사이트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="30122-164">옵션 중 하나에서 **자세한 정보** 를 선택한 다음, 웹 사이트 파트너에 등록하고 해당 도구를 사용하여 사이트를 설정하고 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="30122-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="30122-165">시청: 비즈니스 웹 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="30122-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="30122-166">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="30122-166">Related content</span></span>

<span data-ttu-id="30122-167">[웹 사이트 만들기](../../business-video/create-web-site.md)(비디오)</span><span class="sxs-lookup"><span data-stu-id="30122-167">[Create a website](../../business-video/create-web-site.md) (video)</span></span>\
<span data-ttu-id="30122-168">[비즈니스용 Microsoft 365](../../business-video/index.yml)(링크 페이지)</span><span class="sxs-lookup"><span data-stu-id="30122-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
