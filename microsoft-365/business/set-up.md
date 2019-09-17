---
title: Microsoft 365 Business 설정
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business를 설정 하는 방법을 알아보세요.
ms.openlocfilehash: 1efb7379930f639cf10875cf5aa6731001bb41c8
ms.sourcegitcommit: 2e5ae52bb641ee1f72c077260b5d0f35622935fe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "37005201"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="0991d-103">설치 마법사에서 Microsoft 365 Business 설정</span><span class="sxs-lookup"><span data-stu-id="0991d-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="0991d-104">도메인, 사용자 및 정책 설정 추가</span><span class="sxs-lookup"><span data-stu-id="0991d-104">Add your domain, users, and set up policies</span></span>

![를 https://aka.ms/aboutM365preview가리키는 배너입니다.](media/m365admincenterchanging.png)

<span data-ttu-id="0991d-106">Microsoft 365 Business를 구매 하는 경우 소유 하 고 있는 도메인을 사용 하거나 [등록](sign-up.md)중에 하나를 구입 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="0991d-107">등록할 때 새 도메인을 구매한 경우 도메인은 모두 설정 되며 이동 하 여 [사용자를 추가 하 고 라이선스를 할당할](#add-users-and-assign-licenses)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="0991d-108">로그인 개인 설정에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="0991d-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="0991d-109">전역 관리자 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="0991d-110">**도메인 추가** 또는 **사용자 추가** 를 선택 하 여 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="0991d-111">등록할 때 도메인을 구매한 경우에 **는 추가 도메인** 단계가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="0991d-112">대신 [사용자 추가](#add-users-and-assign-licenses) 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![도메인 추가를 선택 합니다.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="0991d-114">마법사에서 사용 하려는 도메인 이름 (예 contoso.com)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![로그인 페이지를 개인 설정 합니다.](media/personalizesignin.png)

    
4. <span data-ttu-id="0991d-116">마법사의 단계에 따라 도메인을 소유 하 고 있는지 확인 하는 [dns 호스팅 공급자 (Office 365)에 dns 레코드를 만듭니다](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) .</span><span class="sxs-lookup"><span data-stu-id="0991d-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="0991d-117">도메인 호스트를 알고 있는 경우에는 [호스트 관련 지침](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0991d-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="0991d-118">호스팅 공급자가 GoDaddy 이거나 [도메인 연결](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)을 사용 하 여 사용 하도록 설정 된 다른 호스트의 경우에는 프로세스가 쉬우며 자동으로 로그인 하 라는 메시지가 표시 되며 사용자가 대신 인증을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-118">If your hosting provider is GoDaddy, or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect),the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![GoDaddy 액세스 확인 페이지에서 권한 부여를 선택 합니다.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="0991d-120">사용자 추가 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="0991d-120">Add users and assign licenses</span></span>

<span data-ttu-id="0991d-121">마법사에서 사용자를 추가할 수 있지만 나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="0991d-122">또한 로컬 도메인 컨트롤러가 있는 경우 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)를 사용 하 여 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="0991d-123">마법사에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="0991d-123">Add users in the wizard</span></span>

<span data-ttu-id="0991d-124">마법사에서 추가 하는 모든 사용자는 Microsoft 365 비즈니스 라이선스를 자동으로 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![마법사의 새 사용자 추가 페이지 스크린샷](media/addnewuserspage.png)

1. <span data-ttu-id="0991d-126">Microsoft 365 비즈니스 구독에 기존 사용자가 있는 경우 (예: Azure AD Connect를 사용한 경우) 지금 라이선스를 할당 하는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="0991d-127">해당 사용자에게도 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-127">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="0991d-128">사용자를 추가한 후에는 추가한 새 사용자와 자격 증명을 공유 하는 옵션도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="0991d-129">자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-129">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="0991d-130">전자 메일 메시지 마이그레이션을 건너뛰고 **전자 메일 메시지 마이그레이션** 페이지에서 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="0991d-131">다른 전자 메일 공급자에서 전환 중이 고 나중에 데이터를 복사 하려는 경우 [전자 메일 및 연락처를 Office 365로 마이그레이션할](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="0991d-132">도메인 연결</span><span class="sxs-lookup"><span data-stu-id="0991d-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="0991d-133">. Onmicrosoft 도메인을 사용 하도록 선택한 경우 또는 Azure AD Connect를 사용 하 여 사용자를 설정 하는 경우에는이 단계가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="0991d-134">서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="0991d-135">설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="0991d-136">그렇지 [않은 경우 이름 서버를 변경 하 여 도메인 등록 기관에 Office 365을 설정](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="0991d-137">기존 웹 사이트와 같이 기존 DNS 레코드가 있지만 DNS 호스트가 [도메인 연결](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)을 사용 하도록 설정 된 경우 **에는 레코드 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> 
    - <span data-ttu-id="0991d-138">다른 DNS 호스트 (도메인 연결에 대해 사용 하도록 설정 되지 않음)의 기존 DNS 레코드가 있는 경우에는 자체 DNS 레코드를 관리 하 여 기존 서비스가 연결 된 상태 인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="0991d-139">자세한 내용은 [도메인 기본 사항을](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0991d-139">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![도메인 연결 페이지에서 자체 DNS 레코드를 관리 합니다.](media/connectyourdomainpage.png)

2. <span data-ttu-id="0991d-141">마법사의 단계를 따르고 전자 메일 및 기타 서비스가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="0991d-142">보안 정책 및 장치 구성 설정</span><span class="sxs-lookup"><span data-stu-id="0991d-142">Set up security policies and device configurations</span></span> 

<span data-ttu-id="0991d-143">마법사에서 설정한 정책이 *모든 사용자*라는 [보안 그룹](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) 에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-143">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="0991d-144">관리 센터에서 정책을 할당 하는 추가 그룹을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="0991d-145">**모바일 장치에서 작업 파일 보호** 옵션은 **장치를 분실 하거나 도난당 한 경우 기본적으로 작업 파일을 보호** 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-145">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="0991d-146">**사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법 관리**를 설정 하는 옵션을 사용할 수 있으며,이는 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-146">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![모바일 장치에서 작업 파일 보호 페이지의 스크린샷](media/protectworkfilesondevices.png)

     - <span data-ttu-id="0991d-148">**장치를 분실 하거나 도난당** 하 여 [기본값](protect-work-files-on-lost-or-stolen-device.md)을 표시 하려면 작업 파일 보호를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-148">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![손실 된 장치에서 파일을 보호 하는 기본값의 스크린샷](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="0991d-150">**사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법 관리** 를 선택 하 고 확장 하 여 [기본값](manage-user-access-on-mobile-devices.md)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-150">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="0991d-151">설치 중에 기본값을 사용 하 여 모든 사용자에 게 적용 되는 Android, iOS 및 Windows 10에 대 한 응용 프로그램 정책을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-151">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="0991d-152">설치가 완료되면 추가로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-152">You can create more policies after setup completes.</span></span>

        ![휴대폰의 Office 파일에 대 한 보호 설정 스크린샷](media/useraccessonmobile.png)

2. <span data-ttu-id="0991d-154">데이터 및 장치를 보호 하는 마지막 단계에서는 Windows 10 장치를 보호 하기 위한 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-154">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="0991d-155">사용자의 Windows 10이 조직에 연결할 때 이러한 설정이 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-155">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="0991d-156">**보안 Windows 10 장치** 를 확장 하 여 [기본값](secure-windows-10-devices.md)을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-156">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="0991d-157">Windows 10 장치에 [Office를 자동으로 설치](install-office-on-windows-10-during-setup.md) 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-157">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Set Windows 10 장치 구성 페이지의 스크린샷](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="0991d-159">Office 365 클라이언트 앱 배포</span><span class="sxs-lookup"><span data-stu-id="0991d-159">Deploy Office 365 client apps</span></span>

<span data-ttu-id="0991d-160">설정 중에 Office 앱을 자동으로 설치 하도록 선택한 경우 사용자가 자신의 회사 자격 증명을 사용 하 여 Windows 디바이스에서 Azure AD에 로그인 한 후에 앱이 Windows 10 장치에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-160">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="0991d-161">모바일 iOS 또는 Android 장치에 Office를 설치 하려면 [Set up 모바일 장치 For Microsoft 365 Business users](set-up-mobile-devices.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0991d-161">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="0991d-162">Office를 개별적으로 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0991d-162">You can also install Office individually.</span></span> <span data-ttu-id="0991d-163">자세한 내용은 [PC 또는 Mac에 Office 설치](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0991d-163">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
