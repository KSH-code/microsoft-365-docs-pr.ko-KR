---
title: 도메인 사용자를 Microsoft 365와 동기화
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: 도메인 제어 사용자를 비즈니스용 Microsoft 365 동기화합니다.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578410"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="e77d2-103">도메인 사용자를 Microsoft 365와 동기화</span><span class="sxs-lookup"><span data-stu-id="e77d2-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="e77d2-104">1. 디렉터리 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="e77d2-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="e77d2-105">로컬 Active Directory 도메인에서 사용자 및 컴퓨터를 동기화하기 전에 [디렉터리](../enterprise/prepare-for-directory-synchronization.md)동기화 준비를 검토하여 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e77d2-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="e77d2-106">특히:</span><span class="sxs-lookup"><span data-stu-id="e77d2-106">In particular:</span></span>

   - <span data-ttu-id="e77d2-107">메일, **proxyAddresses** 및 **userPrincipalName** 특성에 대한 중복이 디렉터리에 없는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="e77d2-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="e77d2-108">이러한 값은 고유해야 합니다. 중복된 값은 모두 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="e77d2-109">사용이 허가된 사용자에 해당하는 기본 전자 메일 주소와 일치하도록 각 로컬 사용자 계정에 대해 **UPN(userPrincipalName)** 특성을 Microsoft 365 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="e77d2-110">예:  *mary.shelley@contoso.com.local이* 아닌 mary@contoso.</span><span class="sxs-lookup"><span data-stu-id="e77d2-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="e77d2-111">Active Directory 도메인이 *.com* 또는 *.org와* 같은 인터넷 라우팅 가능 접미사 대신 *.local* 또는 *.lan과* 같은 라우팅할 수 없는 접미사로 끝나면 디렉터리 동기화를 위해 라우팅할 수 없는 도메인 준비에 설명된 바와 같이 먼저 로컬 사용자 계정의 UPN 접미사를 조정합니다. [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="e77d2-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="e77d2-112">아래 4단계에서 **IdFix** 실행을 통해 디렉터리 동기화를 위한 준비도 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="e77d2-113">2. Azure AD 2013 설치 및 커넥트</span><span class="sxs-lookup"><span data-stu-id="e77d2-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="e77d2-114">로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory, Azure Active Directory 커넥트 동기화를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="e77d2-115">관리 [센터의](https://go.microsoft.com/fwlink/p/?linkid=2024339)왼쪽 **네비게이트에서** 설치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="e77d2-116">로그인 **및 보안에서,**  사용자의 디렉터리에서 사용자 동기화 아래에서 **보기를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="e77d2-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="e77d2-117">On the **Sync users from your org's directory** page, choose Get **started**.</span><span class="sxs-lookup"><span data-stu-id="e77d2-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="e77d2-118">첫 번째 단계에서 IdFix 도구를 실행하여 디렉터리 동기화를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="e77d2-119">마법사 단계에 따라 Azure AD 커넥트 다운로드하고 도메인 제어 사용자를 동기화하는 데 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e77d2-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="e77d2-120">자세한 [내용은 Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="e77d2-121">Azure AD 커넥트 옵션을 구성할 때 비즈니스용 Microsoft 365 지원되는 암호 동기화, 원활한  Single **Sign-On** 및 암호 쓰기 저장 기능을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e77d2-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="e77d2-122">Azure AD 2013의 확인란을 넘어서 암호 쓰기 저장을 위한 몇 가지 추가 단계가 커넥트.</span><span class="sxs-lookup"><span data-stu-id="e77d2-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="e77d2-123">자세한 내용은 방법: 암호 쓰기 [저장 구성을 참조하십시오.](/azure/active-directory/authentication/howto-sspr-writeback)</span><span class="sxs-lookup"><span data-stu-id="e77d2-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="e77d2-124">도메인에 가입된 Windows 10 장치를 관리하려면 하이브리드 Azure [](manage-windows-devices.md) AD Windows 10 설정하기 위해 도메인에 가입된 Windows 10 장치를 관리하도록 Microsoft 365 Business Premium 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e77d2-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>