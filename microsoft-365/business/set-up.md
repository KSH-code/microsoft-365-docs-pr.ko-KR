---
title: Microsoft 365 Business 설정
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
description: Microsoft 365 Business를 설정 하는 방법을 알아보세요.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660842"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="bc217-103">Microsoft 365 Business 설정</span><span class="sxs-lookup"><span data-stu-id="bc217-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="bc217-104">시작 하기 전에 [Microsoft 365 Business](get-microsoft-365-business.md) to sign details를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="bc217-105">설정 마법사를 사용 하 여 [Microsoft 365 Business를 설정 하는 방법](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) , 온-프레미스 Active Directory가 없는 경우에 대 한 간단한 비디오 보기</span><span class="sxs-lookup"><span data-stu-id="bc217-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="bc217-106">개요</span><span class="sxs-lookup"><span data-stu-id="bc217-106">Overview</span></span>

<span data-ttu-id="bc217-107">설정 단계 대부분은 설치 마법사에서 수행할 수 있지만 다른 옵션도 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="bc217-108">[도메인 추가](#add-your-domain-to-personalize-sign-in) ( [등록](sign-up.md)중에 도메인을 구매한 경우에는이 단계가 이미 완료 되었습니다.)</span><span class="sxs-lookup"><span data-stu-id="bc217-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="bc217-109">사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-109">Add users.</span></span> <span data-ttu-id="bc217-110">다음 세 가지 방법 중 하나를 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="bc217-111">[설치 마법사](#add-users-in-the-wizard)</span><span class="sxs-lookup"><span data-stu-id="bc217-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="bc217-112">온-프레미스 Active directory가 있는 경우 디렉터리 동기화를 사용 하 여 [AZURE AD Connect를 사용 하 여 사용자를 추가](#add-users-by-using-azure-ad-connect) 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="bc217-113">나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="bc217-114">보안 정책을 설정 하 고 장치를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="bc217-115">다음 세 가지 방법 중 하나를 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="bc217-116">[설치 마법사](#set-up-policies-in-the-wizard)</span><span class="sxs-lookup"><span data-stu-id="bc217-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="bc217-117">[관리 센터](#modify-or-add-policies-in-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="bc217-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="bc217-118">[Intune 관리 센터](https://docs.microsoft.com/intune/what-is-device-management)</span><span class="sxs-lookup"><span data-stu-id="bc217-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="bc217-119">Windows 10 장치를 설정 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="bc217-120">WIndows 10 장치를 Azure AD에 가입 하면 모든 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="bc217-121">[설치 마법사](#set-up-policies-in-the-wizard)에서 Windows 10 장치 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="bc217-122">[새 Windows 10 장치](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) 를 Azure AD에 참가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="bc217-123">[기존 Windows 10 장치](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) 를 Azure AD에 참가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="bc217-124">Office 365 Business를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="bc217-125">[설치 마법사](#set-up-policies-in-the-wizard)를 사용 하 여 Windows 장치에 Office를 자동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="bc217-126">관리 센터에서 Office를 자동으로 [설치](auto-install-or-uninstall-office.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="bc217-127">사용자가 Windows 및 장치용 [Office 앱을 설치할](https://docs.microsoft.com/office365/admin/setup/install-applications) 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="bc217-128">추가 보안을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-128">Set up additional security.</span></span>
    - <span data-ttu-id="bc217-129">설치 마법사는 장치를 보호 하기 위한 정책을 추가 하지만 [추가 보안](#additional-security-settings) 기능을 활용 하 여 데이터, 계정 및 전자 메일의 보안을 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="bc217-130">도메인, 사용자 추가 및 정책 설정</span><span class="sxs-lookup"><span data-stu-id="bc217-130">Add your domain, users and set up policies</span></span>

![를 https://aka.ms/aboutM365preview가리키는 배너입니다.](media/m365admincenterchanging.png)

<span data-ttu-id="bc217-132">Microsoft 365 Business를 구매 하는 경우 소유 하 고 있는 도메인을 사용 하거나 [등록](sign-up.md)중에 하나를 구입 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="bc217-133">등록할 때 새 도메인을 구매한 경우 도메인은 모두 설정 되며 이동 하 여 [사용자를 추가 하 고 라이선스를 할당할](#add-users-and-assign-licenses)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="bc217-134">로그인 개인 설정에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="bc217-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="bc217-135">전역 관리자 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="bc217-136">**도메인 추가** 를 선택 하 여 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-136">Choose **Add a domain** to start the wizard.</span></span>

    ![도메인 추가를 선택 합니다.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="bc217-138">마법사에서 사용 하려는 도메인 이름 (예 contoso.com)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![로그인 페이지를 개인 설정 합니다.](media/personalizesignin.png)

    
4. <span data-ttu-id="bc217-140">마법사의 단계에 따라 도메인을 소유 하 고 있는지 확인 하는 [dns 호스팅 공급자 (Office 365)에 dns 레코드를 만듭니다](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) .</span><span class="sxs-lookup"><span data-stu-id="bc217-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="bc217-141">도메인 호스트를 알고 있는 경우에는 [호스트 관련 지침](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="bc217-142">호스팅 공급자가 GoDaddy 이면 프로세스를 쉽게 수행할 수 있으며 자동으로 로그인 하 라는 메시지가 표시 되며 사용자가 대신 인증을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![GoDaddy 액세스 확인 페이지에서 권한 부여를 선택 합니다.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="bc217-144">사용자 추가 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="bc217-144">Add users and assign licenses</span></span>

<span data-ttu-id="bc217-145">마법사에서 사용자를 추가할 수 있지만 나중에 관리 센터에서 [사용자를 추가할](add-users-m365b.md) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="bc217-146">또한 로컬 도메인 컨트롤러가 있는 경우 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)를 사용 하 여 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="bc217-147">마법사에서 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="bc217-147">Add users in the wizard</span></span>

<span data-ttu-id="bc217-148">마법사에서 추가 하는 모든 사용자는 Microsoft 365 비즈니스 라이선스를 자동으로 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="bc217-149">로컬 도메인 컨트롤러가 있고 Active Directory를 사용 하는 경우 [에는 AZURE AD Connect를 사용 하 여 사용자를 ddd](#add-users-by-using-azure-ad-connect)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![마법사의 새 사용자 추가 페이지 스크린샷](media/addnewuserspage.png)

1. <span data-ttu-id="bc217-p106">Microsoft 365 Business 구독에 기존 사용자가 있는 경우(예를 들어 Azure AD Connect를 사용한 경우) 해당 사용자에게 라이선스를 할당하는 옵션이 여기에 표시됩니다. 해당 사용자에게도 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="bc217-153">사용자를 추가한 후에는 추가한 새 사용자와 자격 증명을 공유 하는 옵션도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="bc217-154">자격 증명을 인쇄, 전자 메일로 전송 또는 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="bc217-155">전자 메일 메시지 마이그레이션을 건너뛰고 **전자 메일 메시지 마이그레이션** 페이지에서 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="bc217-156">다른 전자 메일 공급자에서 전환 중이 고 나중에 데이터를 복사 하려는 경우 [전자 메일 및 연락처를 Office 365로 마이그레이션할](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="bc217-157">Azure AD Connect를 사용 하 여 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="bc217-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="bc217-158">Active Directory가 있는 로컬 도메인 컨트롤러가 있는 경우 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)를 사용 하 여 사용자를 Microsoft 365 Business와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="bc217-159">설치 마법사를 시작 하기 전에이 정보를 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="bc217-160">관리 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="bc217-161">**사용자** \> **활성 사용자**로 이동 하 여 페이지 맨 위에 있는 줄임표를 선택한 다음 **디렉터리 동기화** 를 선택 하 여 Azure AD Connect를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![활성 사용자 페이지에서 > 디렉터리 snchronization 줄임표를 선택 합니다.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="bc217-163">이러한 방식으로 사용자를 만드는 경우에도 관리 센터에서 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="bc217-164">계속 해 서 도메인에 가입 된 앱 및 장치에 액세스</span><span class="sxs-lookup"><span data-stu-id="bc217-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="bc217-165">도메인에 가입 된 앱 및 장치에 계속 액세스 하려면 다음 문서를 참조 하 여 두 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="bc217-166">도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="bc217-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="bc217-167">이 방법이 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-167">This is the recommended way.</span></span>

- [<span data-ttu-id="bc217-168">Microsoft 365 Business의 Azure AD에 가입 된 장치에서 온-프레미스 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="bc217-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="bc217-169">도메인 연결</span><span class="sxs-lookup"><span data-stu-id="bc217-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="bc217-170">. Onmicrosoft 도메인을 사용 하도록 선택한 경우 또는 Azure AD Connect를 사용 하 여 사용자를 설정 하는 경우에는이 단계가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="bc217-171">서비스를 설정하려면 DNS 호스트 또는 도메인 등록 기관에서 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="bc217-172">설정 마법사는 일반적으로 사용자의 등록 기관을 감지하여 등록 기관 웹 사이트에서 NS 레코드를 업데이트하기 위한 단계별 지침의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="bc217-173">그렇지 [않은 경우 이름 서버를 변경 하 여 도메인 등록 기관에 Office 365을 설정](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="bc217-174">기존 웹 사이트와 같은 기존 DNS 레코드가 있는 경우에는 자체 DNS 레코드를 관리 하 여 기존 서비스가 계속 연결 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="bc217-175">자세한 내용은 [도메인 기본 사항을](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![도메인 연결 페이지에서 자체 DNS 레코드를 관리 합니다.](media/connectyourdomainpage.png)

2. <span data-ttu-id="bc217-177">마법사의 단계를 따르고 전자 메일 및 기타 서비스가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="bc217-178">보안 정책 및 장치 구성 설정</span><span class="sxs-lookup"><span data-stu-id="bc217-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="bc217-179">이러한 정책은 사용자 집합에 다른 정책을 할당 하도록 결정 한 경우 라이선스를 제공 하는 모든 사용자 또는 사용자 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="bc217-180">마법사에서 정책 설정</span><span class="sxs-lookup"><span data-stu-id="bc217-180">Set up policies in the wizard</span></span>

<span data-ttu-id="bc217-181">마법사에서 설정한 정책이 *모든 사용자*라는 [보안 그룹](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) 에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="bc217-182">**모바일 장치에서 작업 파일 보호** 옵션은 **장치를 분실 하거나 도난당 한 경우 기본적으로 작업 파일을 보호** 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="bc217-183">**사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법 관리**를 설정 하는 옵션을 사용할 수 있으며,이는 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![모바일 장치에서 작업 파일 보호 페이지의 스크린샷](media/protectworkfilesondevices.png)

     - <span data-ttu-id="bc217-185">**장치를 분실 하거나 도난당 했을 때 작업 파일 보호**를 확장 하면 [기본값](protect-work-files-on-lost-or-stolen-device.md) 은 미리 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![손실 된 장치에서 파일을 보호 하는 기본값의 스크린샷](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="bc217-187">**사용자가 모바일 장치에서 Office 파일에 액세스 하는 방법 관리** 를 선택 하 고 확장 하면 [기본값이](manage-user-access-on-mobile-devices.md) 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="bc217-188">설치 중에 기본값을 그대로 수락하여 모든 사용자에게 적용되도록 Android, iOS 및 Windows 10 응용 프로그램 정책을 생성하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="bc217-189">설치가 완료되면 추가로 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-189">You can create more policies after setup completes.</span></span>

        ![휴대폰의 Office 파일에 대 한 보호 설정 스크린샷](media/useraccessonmobile.png)

2. <span data-ttu-id="bc217-191">데이터 및 장치를 보호 하는 마지막 단계에서는 Windows 10 장치를 보호 하기 위한 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="bc217-192">사용자의 Windows 10이 조직에 연결할 때 이러한 설정이 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="bc217-193">**보안 Windows 10 장치** 를 확장 하 여 [기본값](secure-windows-10-devices.md)을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="bc217-194">Windows 10 장치에 [Office를 자동으로 설치](install-office-on-windows-10-during-setup.md) 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Set Windows 10 장치 구성 페이지의 스크린샷](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="bc217-196">관리 센터에서 정책 수정 또는 추가</span><span class="sxs-lookup"><span data-stu-id="bc217-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="bc217-197">장치 및 앱 보호 정책을 보거나 수정 하는 방법, 사용자 장치에서 데이터를 제거 또는 다시 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 365 Business 관리](manage.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="bc217-198">Windows 10 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="bc217-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="bc217-199">새 컴퓨터를 설치 하는 동안 또는 기존 컴퓨터에 대 한 로그인 프로필을 변경 하 여 [Microsoft 365 비즈니스 사용자를 위한 Windows 장치](set-up-windows-devices.md) 를 수동으로 Azure AD에 연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="bc217-200">Autopilot을 사용 하 여 새 장치 설정</span><span class="sxs-lookup"><span data-stu-id="bc217-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="bc217-201">[Windows Autopilot](add-autopilot-devices-and-profile.md) 를 사용 하 여 사용자에 대해 **새** Windows 10 장치를 자동으로 미리 구성할 수 있지만,이 작업을 대신 수행할 수 있는 [파트너](https://www.microsoft.com/solution-providers/search) 를 가져오는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="bc217-202">[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) 로 이동 하 여 클라우드 기술 전문가가 사용자를 위해 구입한 새 장치를 설정 하 게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="bc217-203">온-프레미스 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="bc217-203">Access on-premises resources</span></span>

<span data-ttu-id="bc217-204">조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="bc217-205">이를 설정 하려면 [도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정](manage-windows-devices.md) 의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="bc217-206">이 상태에서 기본 설정 방법 및 장치를 하이브리드 Azure AD 가입 장치 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="bc217-207">회사에 일부 온-프레미스 리소스 (예: 파일 공유 및 프린터)가 포함 된 로컬 Active Directory가 있는 경우 여기에 나와 있는 단계에 따라 Azure AD 조인 장치에 이러한 리소스에 대 한 액세스 권한을 부여할 수 있습니다. [ Azure AD-가입 된 장치 (Microsoft 365 Business)](access-resources.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="bc217-208">Office 365 클라이언트 앱 배포</span><span class="sxs-lookup"><span data-stu-id="bc217-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="bc217-209">설정 중에 Office 앱을 자동으로 설치 하도록 선택한 경우 사용자가 자신의 회사 자격 증명을 사용 하 여 Windows 디바이스에서 Azure AD에 로그인 한 후에 앱이 Windows 10 장치에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="bc217-210">모바일 iOS 또는 Android 장치에 Office를 설치 하려면 [Set up 모바일 장치 For Microsoft 365 Business users](set-up-mobile-devices.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="bc217-211">Office를 개별적으로 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-211">You can also install Office individually.</span></span> <span data-ttu-id="bc217-212">자세한 내용은 [PC 또는 Mac에 Office 설치](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="bc217-213">추가 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bc217-213">Additional security settings</span></span>

<span data-ttu-id="bc217-214">설치 마법사의 보안 및 규정 준수 설정 외에 다음과 같은 추가 설정을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc217-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="bc217-215">**전자 메일 맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="bc217-215">**Email malware protection**</span></span>
- <span data-ttu-id="bc217-216">**ATP (Advanced Threat Protection) 안전한 첨부 파일**</span><span class="sxs-lookup"><span data-stu-id="bc217-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="bc217-217">**ATP 안전한 링크**</span><span class="sxs-lookup"><span data-stu-id="bc217-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="bc217-218">**APT 피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="bc217-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="bc217-219">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="bc217-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="bc217-220">**DLP(데이터 손실 방지)**</span><span class="sxs-lookup"><span data-stu-id="bc217-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="bc217-221">**Azure Information Protection** (계획 1)</span><span class="sxs-lookup"><span data-stu-id="bc217-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="bc217-222">**Intune 포털 사용 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="bc217-222">**Intune portal availability**</span></span>

<span data-ttu-id="bc217-223">시작 하려면 [고급 보안 정책을 설정](set-up-advanced-security.md)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="bc217-224">모범 보안 관행 로드맵에 대해서는 [Microsoft 365 Business의 보안을 위한 상위 10 가지 방법](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc217-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>