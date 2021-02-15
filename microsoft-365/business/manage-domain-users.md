---
title: 도메인 사용자를 Microsoft 365와 동기화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 도메인 제어 사용자를 비즈니스용 Microsoft 365와 동기화합니다.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841362"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="74eee-103">도메인 사용자를 Microsoft 365와 동기화</span><span class="sxs-lookup"><span data-stu-id="74eee-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="74eee-104">1. 디렉터리 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="74eee-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="74eee-105">로컬 Active Directory 도메인에서 사용자 및 컴퓨터를 동기화하기 전에 [Microsoft 365로의](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization)디렉터리 동기화 준비를 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="74eee-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="74eee-106">특히:</span><span class="sxs-lookup"><span data-stu-id="74eee-106">In particular:</span></span>

   - <span data-ttu-id="74eee-107">메일, **proxyAddresses** 및 **userPrincipalName** 특성에 대한 중복이 디렉터리에 없는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="74eee-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="74eee-108">이러한 값은 고유해야 하며 중복된 값은 모두 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="74eee-109">사용이 허가된 Microsoft 365 사용자에 해당하는 기본 전자 메일 주소와 일치하도록 각 로컬 사용자 계정에 대해 **USERPrincipalName(UPN)** 특성을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="74eee-110">예: *mary.shelley@contoso.com.local이* 아닌 *mary@contoso 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="74eee-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="74eee-111">Active Directory 도메인이 .com 또는 *.org와* 같은 인터넷 라우팅 가능 접미사 대신 [](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization) *.local* 또는 *.lan과* 같은 라우팅할 수 없는 접미사로 끝나면 디렉터리 동기화를 위해 라우팅할 수 없는 도메인 준비에 설명된 바와 같이 로컬 사용자 계정의 UPN 접미사 먼저 조정합니다. </span><span class="sxs-lookup"><span data-stu-id="74eee-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="74eee-112">아래의 4단계(4단계)의 Run **IdFix를** 통해 디렉터리 동기화를 위한 준비도 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="74eee-113">2. Azure AD Connect 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="74eee-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="74eee-114">로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory에 동기화하려면 Azure Active Directory Connect를 설치하고 디렉터리 동기화를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="74eee-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="74eee-115">관리 [센터의](https://go.microsoft.com/fwlink/p/?linkid=2024339)왼쪽 **네비게이트에서** 설치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="74eee-116">로그인 **및 보안 아래에서,** 사용자의 디렉터리에서 동기화 아래에서 **보기를 선택하십시오.** </span><span class="sxs-lookup"><span data-stu-id="74eee-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="74eee-117">On the **Sync users from your org's directory** page, choose Get **started.**</span><span class="sxs-lookup"><span data-stu-id="74eee-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="74eee-118">첫 번째 단계에서 IdFix 도구를 실행하여 디렉터리 동기화를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="74eee-119">마법사 단계에 따라 Azure AD Connect를 다운로드하고 이를 사용하여 도메인 제어 사용자를 Microsoft 365와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="74eee-120">자세한 [내용은 Microsoft 365에](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) 대한 디렉터리 동기화 설정을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="74eee-121">Azure AD Connect에 대한 옵션을 구성할 때 비즈니스용 Microsoft 365에서도  지원되는 암호 동기화, 원활한 Single **Sign-On** 및 암호 쓰기 저장 기능을 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="74eee-122">Azure AD Connect의 확인란을 넘어 암호 쓰기 저장을 위한 몇 가지 추가 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74eee-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="74eee-123">자세한 내용은 방법: 암호 쓰기 [저장 구성을 참조하십시오.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)</span><span class="sxs-lookup"><span data-stu-id="74eee-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="74eee-124">도메인에 가입된 Windows 10 장치를 관리하려면 [Microsoft 365 Business Premium에서](manage-windows-devices.md) 도메인에 가입된 Windows 10 장치를 관리하도록 설정하여 하이브리드 Azure AD 가입을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="74eee-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 