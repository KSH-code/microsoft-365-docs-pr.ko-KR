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
description: 도메인 제어 사용자를 비즈니스용 Microsoft 365와 동기화 합니다.
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306452"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="711d3-103">도메인 사용자를 Microsoft 365와 동기화</span><span class="sxs-lookup"><span data-stu-id="711d3-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="711d3-104">1. 디렉터리 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="711d3-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="711d3-105">로컬 Active Directory 도메인에서 사용자 및 컴퓨터를 동기화 하기 전에 [디렉터리 동기화를 Microsoft 365에 대해 준비](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization)를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="711d3-106">특히 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-106">In particular:</span></span>

   - <span data-ttu-id="711d3-107">디렉터리에 **mail**, **proxyAddresses**및 **userPrincipalName**특성에 대 한 중복이 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="711d3-108">이러한 값은 고유 해야 하며 모든 중복 항목을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="711d3-109">사용이 허가 된 Microsoft 365 사용자에 해당 하는 기본 전자 메일 주소와 일치 하도록 각 로컬 사용자 계정에 대 한 **userPrincipalName** (UPN) 특성을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="711d3-110">예: *mary@contoso* 가 아닌 *mary.shelley@contoso.com*</span><span class="sxs-lookup"><span data-stu-id="711d3-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="711d3-111">Active Directory 도메인이 *.com* 또는 *org*와 같이 라우팅할 수 없는 접미사로 끝나는 *.local* 경우 [디렉터리 동기화를 위해 라우팅할 수 없는 도메인을 준비](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)하는 방법에 설명 된 대로 로컬 사용자 계정의 UPN *접미사를 먼저*조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="711d3-112">아래 4 단계의 **IdFix 실행** (4)에서는 온-프레미스 Active Directory가 dir 동기화를 수행할 수 있도록 준비 되어 있는지도 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="711d3-113">2. Azure AD Connect 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="711d3-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="711d3-114">로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory에 동기화 하려면 Azure Active Directory Connect를 설치 하 고 디렉터리 동기화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="711d3-115">관리 센터의 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 왼쪽 탐색 창에서 **설치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="711d3-116">**로그인 및 보안**에서 조직의 **디렉터리에서 사용자 동기화**아래의 **보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="711d3-117">**Org 디렉터리에서 사용자 동기화** 페이지에서 **시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="711d3-118">첫 번째 단계에서는 IdFix 도구를 실행 하 여 디렉터리 동기화를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="711d3-119">마법사의 단계에 따라 Azure AD Connect를 다운로드 하 고이를 사용 하 여 도메인 제어 사용자를 Microsoft 365와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="711d3-120">자세한 내용은 [Microsoft 365에 대 한 디렉터리 동기화 설정](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="711d3-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="711d3-121">Azure AD Connect에 대 한 옵션을 구성 하는 경우 **암호 동기화**, **원활한 Single sign-on**및 **암호 쓰기 저장** 기능을 사용 하도록 설정 하는 것이 좋습니다 (비즈니스용 Microsoft 365 에서도 지원 됨).</span><span class="sxs-lookup"><span data-stu-id="711d3-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="711d3-122">Azure AD Connect의 확인란 외에도 암호 쓰기 저장을 위한 몇 가지 추가 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="711d3-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="711d3-123">자세한 내용은 [방법: 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="711d3-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="711d3-124">도메인에 가입 된 Windows 10 장치를 관리 하려면 하이브리드 Azure AD 조인을 설정 하기 위해 [Microsoft 365 Business Premium에서 관리할 도메인 가입 windows 10 장치를 사용 하도록 설정](manage-windows-devices.md) 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="711d3-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 