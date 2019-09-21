---
title: 도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정
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
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Microsoft 365에서 로컬 AD에 가입 된 Windows 10 장치를 보호 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 15804a0bd6cf9d013c5138470aa4a4a7acec57e1
ms.sourcegitcommit: 08c334b754bd6d64375b33d91a972a31f2f309cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2019
ms.locfileid: "37100444"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="99f96-103">도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="99f96-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="99f96-104">조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="99f96-105">이를 설정 하려면 **하이브리드 AZURE AD에 가입 된 장치**를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-105">To set this up, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="99f96-106">온-프레미스 Active Directory 및 Azure Active Directory에 모두 가입 된 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-106">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="99f96-107">다음 비디오에서는 다음 단계에서 자세히 설명 되는 가장 일반적인 시나리오에서이를 설정 하는 방법에 대 한 단계를 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-107">The following video details the steps for how to set this up for the most common scenario that is also detailed in the following steps.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="99f96-108">1. 디렉터리 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="99f96-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="99f96-109">로컬 Active Directory 도메인에서 사용자 및 컴퓨터를 동기화 하기 전에 [Office 365에 대 한 디렉터리 동기화 준비](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="99f96-110">특히 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-110">In particular:</span></span>

   - <span data-ttu-id="99f96-111">**Mail**, **proxyAddresses**및 **userPrincipalName**특성에 대 한 중복 된 디렉터리가 디렉터리에 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-111">Ensure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="99f96-112">이러한 값은 고유 해야 하며 모든 중복 항목을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-112">These values should be unique and any duplicates should be removed..</span></span>
   
   - <span data-ttu-id="99f96-113">각 로컬 사용자 계정에 대 한 **userPrincipalName** (UPN) 특성은 라이선스가 부여 된 Microsoft 365 사용자에 해당 하는 기본 전자 메일 주소와 일치 하도록 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-113">We recommended that the **userPrincipalName** (UPN) attribute for each local user account is configured to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="99f96-114">예를 들어 \*shelley @<span>contoso를 예로<span> 들 있습니다. \* *mary @ contoso. 로컬* 이 아닌 com</span><span class="sxs-lookup"><span data-stu-id="99f96-114">For example *mary.shelley@<span>contoso.<span>com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="99f96-115">Active Directory 도메인이 *.com* 또는 *org*와 같이 라우팅할 수 없는 접미사로 끝나는 *경우, 로컬*사용자 계정의 UPN 접미사는 다음에 설명 된 대로 먼저 조정 해야 합니다 (예: " *).* [디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 준비](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, you will need to adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="99f96-116">2. Azure AD Connect 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="99f96-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="99f96-117">로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory에 동기화 하려면 Azure Active Directory Connect를 설치 하 고 디렉터리 동기화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="99f96-118">자세한 내용은 [Office 365에 대 한 디렉터리 동기화 설정](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f96-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="99f96-119">이 단계는 Microsoft 365 비즈니스에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="99f96-120">Azure AD Connect에 대 한 옵션을 구성할 때 암호 **동기화** 및 **원활한 Single sign-on**을 사용 하도록 설정 하는 것이 좋지만 Microsoft 365 Business 에서도 지원 되는 **암호 쓰기 저장** 기능도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-120">As you configure your options for Azure AD Connect, we recommend enabling **Password Synchronization** and **Seamless Single Sign-On**, as well as the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="99f96-121">Azure AD Connect의 확인란 외에도 암호 쓰기 저장을 위한 몇 가지 추가 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="99f96-122">자세한 내용은 [방법: 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f96-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="99f96-123">3. 하이브리드 Azure AD 조인 구성</span><span class="sxs-lookup"><span data-stu-id="99f96-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="99f96-124">Windows 10 장치에서 하이브리드 Azure AD에 가입 되도록 설정 하기 전에 다음 필수 구성 요소를 충족 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, you should make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="99f96-125">최신 버전의 Azure AD connect를 실행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-125">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="99f96-126">Azure AD connect에서 하이브리드 Azure AD에 가입 하려는 장치의 모든 컴퓨터 개체를 동기화 했습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="99f96-127">컴퓨터 개체가 특정 OU (조직 구성 단위)에 속하는 경우 이러한 Ou가 Azure AD connect 에서도 동기화 되도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="99f96-128">기존 도메인에 가입한 Windows 10 장치를 하이브리드 Azure AD에 연결 된 상태로 등록 하려면 [자습서: managed domains에 대 한 하이브리드 Azure Active Directory Join 구성](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="99f96-129">이렇게 하면 Windows 10 컴퓨터에 가입 된 기존 온-프레미스 Active Directory에 하이브리드를 사용할 수 있도록 설정 하 고 클라우드를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-129">This will hybrid-enable your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="99f96-130">4. Windows 10에 대해 자동 등록을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="99f96-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="99f96-131">Intune에서 모바일 장치 관리용 Windows 10 장치를 자동으로 등록 하려면 [그룹 정책을 사용 하 여 자동으로 windows 10 장치 등록](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f96-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="99f96-132">그룹 정책을 로컬 컴퓨터 수준에서 설정 하거나 일괄 작업을 수행 하는 경우 그룹 정책 관리 콘솔 및 ADMX 템플릿을 사용 하 여 도메인 컨트롤러에서이 그룹 정책 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-132">You can set the Group Policy at a local computer level, or for bulk operations, you can create this group policy setting on your Domain Controller using the Group Policy Management Console and ADMX templates.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="99f96-133">5. 원활한 Single Sign-on 구성</span><span class="sxs-lookup"><span data-stu-id="99f96-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="99f96-134">원활한 SSO는 회사 컴퓨터를 사용할 때 Microsoft 365 클라우드 리소스에 사용자에 게 자동으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-134">Seamless SSO will automatically sign users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="99f96-135">[Azure Active Directory 원활한 Single sign-on: 빠른 시작](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)에 설명 된 두 가지 그룹 정책 옵션 중 하나를 배포 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="99f96-136">**그룹 정책** 옵션을 사용 하 여 사용자가 자신의 설정을 변경할 수는 없지만 **그룹 정책 기본 설정** 옵션은 값을 설정 하지만 사용자 구성도 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-136">The **Group Policy** option does not allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="99f96-137">6. 비즈니스용 Windows Hello 설정</span><span class="sxs-lookup"><span data-stu-id="99f96-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="99f96-138">비즈니스용 Windows Hello는 암호를 강력한 2 단계 인증 (2FA)으로 대체 하 여 로컬 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="99f96-139">한 가지 요인은 비대칭 키 쌍이 고 다른 하나는 장치에서 지 원하는 경우 지문 또는 얼굴 인식과 같은 다른 로컬 제스처 또는 PIN입니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="99f96-140">가능한 경우 암호를 2 FA 및 Windows Hello for Business로 바꾸는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-140">We recommended that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="99f96-141">비즈니스용 하이브리드 Windows Hello를 구성 하려면 [하이브리드 키 트러스트 Windows hello For Business 필수 구성 요소](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f96-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="99f96-142">그런 다음 [비즈니스용 하이브리드 Windows Hello 키 트러스트 설정](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="99f96-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
