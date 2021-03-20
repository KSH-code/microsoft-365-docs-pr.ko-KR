---
title: Microsoft 365 사용자 계정 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 사용자 계정을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909565"
---
# <a name="manage-microsoft-365-user-accounts"></a><span data-ttu-id="deefb-103">Microsoft 365 사용자 계정 관리</span><span class="sxs-lookup"><span data-stu-id="deefb-103">Manage Microsoft 365 user accounts</span></span>

<span data-ttu-id="deefb-104">구성에 따라 여러 가지 방법으로 Microsoft 365 사용자 계정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-104">You can manage Microsoft 365 user accounts in several different ways, depending on your configuration.</span></span> <span data-ttu-id="deefb-105">[Microsoft 365](../admin/add-users/index.yml)관리 센터, [PowerShell,](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)AD DS(Active Directory 도메인 서비스) 또는 Azure AD(Azure Active Directory) 관리 포털에서 사용자 계정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-105">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin portal.</span></span> 

<span data-ttu-id="deefb-106">Microsoft 365를 구입하는 즉시 Microsoft 365 관리 센터 및 PowerShell을 사용하여 계정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-106">As soon as you purchase Microsoft 365, the Microsoft 365 admin center and PowerShell can be used to manage accounts.</span></span> <span data-ttu-id="deefb-107">클라우드 ID를 관리할 때 조직의 모든 사용자에게 별도의 사용자 계정 이름과 암호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-107">When managing cloud identities, every person in your organization has a separate user account name and password.</span></span> <span data-ttu-id="deefb-108">Azure AD Connect를 사용하여 SSO(Single Sign-On) 기능에 대한 ID 및 암호 동기화를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-108">If you want to integrate with your on-premises infrastructure and have user accounts synchronized with Microsoft 365, you can use Azure AD Connect to provide synchronization of identities and passwords for single sign-on (SSO) functionality.</span></span>
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a><span data-ttu-id="deefb-109">사용자 계정을 관리하는 위치 및 방법 계획</span><span class="sxs-lookup"><span data-stu-id="deefb-109">Plan for where and how you will manage your user accounts</span></span>

<span data-ttu-id="deefb-110">사용자 계정을 관리하는 위치와 방법은 Microsoft 365에 사용하려는 ID 모델에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-110">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="deefb-111">두 가지 전체 모델은 클라우드 전용 및 하이브리드입니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-111">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="deefb-112">클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="deefb-112">Cloud-only</span></span>

<span data-ttu-id="deefb-113">Microsoft 365 관리 센터에서 사용자를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-113">You create and manage users in the Microsoft 365 admin center.</span></span> <span data-ttu-id="deefb-114">PowerShell 또는 Azure AD 관리 센터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-114">You can also use PowerShell or the Azure AD admin center.</span></span> 
    
### <a name="hybrid"></a><span data-ttu-id="deefb-115">하이브리드</span><span class="sxs-lookup"><span data-stu-id="deefb-115">Hybrid</span></span>

<span data-ttu-id="deefb-116">사용자 계정은 AD DS에서 Microsoft 365와 동기화되어 있으므로 사용자 계정을 관리하려면 사내 AD DS 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-116">User accounts are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage user accounts.</span></span> 
    
## <a name="managing-accounts"></a><span data-ttu-id="deefb-117">계정 관리</span><span class="sxs-lookup"><span data-stu-id="deefb-117">Managing Accounts</span></span>

<span data-ttu-id="deefb-118">조직에서 계정을 만들고 관리하는 방법을 결정하면 다음 요구 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="deefb-118">When deciding which way your organization will create and manage accounts, consider the following requirements:</span></span>
  
- <span data-ttu-id="deefb-119">Microsoft 365와 AD DS 간에 ID를 연결하기 위해 디렉터리 동기화 소프트웨어를 사내 환경 내의 서버에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-119">The directory synchronization software needs to be installed on servers within your on-premises environment to connect the identities between Microsoft 365 and your AD DS.</span></span>
    
- <span data-ttu-id="deefb-120">SSO 옵션을 비롯한 모든 디렉터리 동기화 옵션을 사용하려면 AD DS 특성이 표준을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-120">Any directory synchronization option, including SSO options, requires that your AD DS attributes meet standards.</span></span> <span data-ttu-id="deefb-121">디렉터리에서 사용되는 특성 및 필요한 정리(있는 경우)의 구체적인 설명은 Microsoft 365로의 디렉터리 동기화 [준비에 설명되어 있습니다.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="deefb-121">The specifics of what attributes are used in your directory and what cleanup (if any) is needed are described in [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span> 
    
- <span data-ttu-id="deefb-122">Microsoft 365 계정을 만드는 방법을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-122">Plan how you are going to create Microsoft 365 accounts.</span></span>
    
<span data-ttu-id="deefb-123">다음 표에는 다양한 계정 관리 도구가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-123">The following table lists the different account management tools.</span></span>
    
|<span data-ttu-id="deefb-124">도구</span><span class="sxs-lookup"><span data-stu-id="deefb-124">Tool</span></span>|<span data-ttu-id="deefb-125">참고</span><span class="sxs-lookup"><span data-stu-id="deefb-125">Notes</span></span>|
|:-----|:-----|
|<span data-ttu-id="deefb-126">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="deefb-126">Microsoft 365 admin center</span></span>  <br/> |[<span data-ttu-id="deefb-127">개별적으로 또는 대량으로 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="deefb-127">Add users individually or in bulk</span></span>](../admin/add-users/add-users.md) <br/>  <span data-ttu-id="deefb-128">사용자 계정을 추가하고 변경할 수 있는 간단한 웹 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-128">Provides a simple web interface to add and change user accounts.</span></span>  <br/>  <span data-ttu-id="deefb-129">디렉터리 동기화를 사용하도록 설정한 경우(위치 및 라이선스 할당을 설정할 수 있는 경우) 사용자를 변경하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-129">Can't be used to change users if directory synchronization is enabled (location and license assignment can be set).</span></span>  <br/>  <span data-ttu-id="deefb-130">SSO 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-130">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="deefb-131">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="deefb-131">Windows PowerShell</span></span>  <br/> |[<span data-ttu-id="deefb-132">Microsoft 365를 사용하여 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="deefb-132">Manage Microsoft 365 with Windows PowerShell</span></span>](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  <span data-ttu-id="deefb-133">사용자 일괄 스크립트를 사용하여 대량 사용자를 추가할 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-133">Allows you to add users in bulk users by using a Windows PowerShell script.</span></span>  <br/>  <span data-ttu-id="deefb-134">계정 생성 방법에 관계없이 계정에 위치 및 라이선스를 할당하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-134">Can be used to assign location and licenses to accounts, regardless of how the accounts are created.</span></span>  <br/> |
|<span data-ttu-id="deefb-135">대량 가져오기</span><span class="sxs-lookup"><span data-stu-id="deefb-135">Bulk import</span></span>  <br/> |[<span data-ttu-id="deefb-136">동시에 여러 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="deefb-136">Add several users at the same time</span></span>](add-several-users-at-the-same-time.md) <br/>  <span data-ttu-id="deefb-137">CSV 파일을 가져와 Microsoft 365에 사용자 그룹을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-137">Allows you to import a CSV file to add a group of users to Microsoft 365.</span></span>  <br/>  <span data-ttu-id="deefb-138">SSO 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-138">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="deefb-139">Azure AD</span><span class="sxs-lookup"><span data-stu-id="deefb-139">Azure AD</span></span>  <br/> |<span data-ttu-id="deefb-140">Microsoft 365 구독이 있는 무료 Azure AD 버전이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-140">You get a free edition of Azure AD with your Microsoft 365 subscription.</span></span> <span data-ttu-id="deefb-141">클라우드 사용자를 위한 셀프 서비스 암호 재설정, 무료 에디션을 사용하여 로그인 및 액세스 패널 페이지 사용자 지정과 같은 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-141">You can perform functions like self-service password reset for cloud users, and customization of the Sign-in and Access Panel pages by using the free edition.</span></span> <span data-ttu-id="deefb-142">향상된 기능을 얻기 위해 기본 버전, Azure AD Premium P1 또는 Azure AD Premium P2로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-142">To get enhanced functionality, you can upgrade to the basic edition, Azure AD Premium P1, or Azure AD Premium P2.</span></span> <span data-ttu-id="deefb-143">지원되는 기능 [목록은 Azure AD](/azure/active-directory/fundamentals/active-directory-whatis) 에디션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="deefb-143">See [Azure AD editions](/azure/active-directory/fundamentals/active-directory-whatis) for the list of supported features.</span></span>  <br/> |
|<span data-ttu-id="deefb-144">디렉터리 동기화</span><span class="sxs-lookup"><span data-stu-id="deefb-144">Directory synchronization</span></span>  <br/> |[<span data-ttu-id="deefb-145">Azure AD와 사내 ID 통합</span><span class="sxs-lookup"><span data-stu-id="deefb-145">Integrating your on-premises identities with Azure AD</span></span>](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  <span data-ttu-id="deefb-146">암호 동기화와 디렉터리 동기화의 [경우, Azure AD Connect와 Express 설정 을 사용합니다.](/azure/active-directory/hybrid/how-to-connect-install-express)</span><span class="sxs-lookup"><span data-stu-id="deefb-146">For directory synchronization with or without password synchronization, use [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>  <br/>  <span data-ttu-id="deefb-147">여러 포리스트 및 SSO 옵션의 경우 Azure AD Connect의 사용자 지정 [설치를 사용하세요.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="deefb-147">For multiple forests and SSO options, use [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>  <br/>  <span data-ttu-id="deefb-148">SSO를 사용하도록 설정하는 데 필요한 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-148">Provides the infrastructure that's necessary to enable SSO.</span></span>  <br/>  <span data-ttu-id="deefb-149">단계적 마이그레이션 및 하이브리드 Exchange와 같은 여러 하이브리드 시나리오에 필요</span><span class="sxs-lookup"><span data-stu-id="deefb-149">Required for many hybrid scenarios such as staged migration and hybrid Exchange</span></span>  <br/>  <span data-ttu-id="deefb-150">AD DS에서 보안 및 메일 사용 가능 그룹을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-150">Synchronizes security and mail-enabled groups from your AD DS.</span></span>  <br/> |
|||
   
- <span data-ttu-id="deefb-151">Microsoft 365에 사용자 계정을 추가하는 방법에 관계없이 라이선스 할당, 위치 지정 등의 여러 계정 기능을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-151">Regardless of how you intend to add the user accounts to Microsoft 365, you need to manage several account features, such as assigning licenses, specifying location, and so on.</span></span> <span data-ttu-id="deefb-152">이러한 기능은 Microsoft 365 관리 센터에서 장기적으로 관리하거나 [PowerShell을](./create-user-accounts-with-microsoft-365-powershell.md)사용하여 사용자 계정을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-152">These features can be managed long-term from the Microsoft 365 admin center or you can also [create user accounts with PowerShell](./create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
    <span data-ttu-id="deefb-153">관리 센터를 통해 모든 사용자를 추가하고 관리하려면 Microsoft 365 계정을 만드는 동시에 위치를 지정하고 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-153">If you choose to add and manage all your users through the admin center, you will specify the location and assign licenses at the same time as creating the Microsoft 365 account.</span></span> <span data-ttu-id="deefb-154">따라서 계획이 많이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-154">As a result, not much planning is required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="deefb-155">라이선스를 할당하지 않고(예: SharePoint Online에) Microsoft 365에서 계정을 만들면 계정 소유자가 Microsoft 365 센터를 볼 수 있지만 회사 구독 내의 서비스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-155">Creating accounts in Microsoft 365 without assigning a license (to SharePoint Online, for example) means that the account owner can view the Microsoft 365 center but can't access any of the services within your company's subscription.</span></span> <span data-ttu-id="deefb-156">위치와 라이선스를 할당하면 계정이 할당한 서비스 또는 서비스에 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-156">After you assign a location and the license, the account is replicated to the service or services that you assigned.</span></span> <span data-ttu-id="deefb-157">사용자는 계정에 로그인하여 할당한 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deefb-157">The user can sign in to their account and use the services that you assigned to them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="deefb-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="deefb-158">See also</span></span>

[<span data-ttu-id="deefb-159">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="deefb-159">Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)

[<span data-ttu-id="deefb-160">PowerShell</span><span class="sxs-lookup"><span data-stu-id="deefb-160">PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)