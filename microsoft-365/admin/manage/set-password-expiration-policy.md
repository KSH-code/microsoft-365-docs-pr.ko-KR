---
title: 조직의 암호 만료 정책 설정
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Microsoft 365 관리 센터에서 조직에 대한 암호 만료 정책을 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 4a7b544b6eded6f0cd6441ad7f6b02de790e5e44
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603987"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="3c9fd-103">조직의 암호 만료 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3c9fd-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3c9fd-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-104">The admin center is changing.</span></span> <span data-ttu-id="3c9fd-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="3c9fd-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="3c9fd-106">Before you begin</span></span>

<span data-ttu-id="3c9fd-107">회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="3c9fd-108">이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="3c9fd-109">[관리자 계정의 새로운 기능](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3c9fd-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span>

<span data-ttu-id="3c9fd-110">다음 단계를 수행하려면 [전역 관리자](../add-users/about-admin-roles.md)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-110">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="3c9fd-111">사용자에게는 만료일이 없는 암호를 설정할 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="3c9fd-112">회사 또는 학교의 기술 지원에 문의하여 이 문서의 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="3c9fd-113">관리자는 특정 일수 후에 사용자 암호가 만료되도록 하거나 암호가 만료되지 않도록 설정할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3c9fd-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="3c9fd-114">암호 만료 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3c9fd-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="3c9fd-115">기본적으로 암호는 90일 이내에 만료되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="3c9fd-116">현재 리서치에서는 강제 암호의 변경은 장점보다 단점이 많다는 것을 강하게 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="3c9fd-117">사용자가 더 취약한 암호를 선택하거나, 암호를 재사용하거나, 해커가 손쉽게 추측할 수 있는 방식으로 기존 암호를 업데이트하도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="3c9fd-118">암호가 만료되지 않도록 설정하는 경우 [다단계 인증](../security-and-compliance/set-up-multi-factor-authentication.md)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="3c9fd-119">특정 시간 후에 사용자 암호가 만료되도록 설정하려면 아래의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="3c9fd-120">관리 센터에서 **설정** \> **조직 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-120">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="3c9fd-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">보안 및 개인 정보</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="3c9fd-122">전역 관리자가 아닌 경우에는 보안 및 개인 정보 옵션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-122">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="3c9fd-123">**암호 만료 정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-123">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="3c9fd-124">사용자가 암호를 변경하지 않도록 하려면 **특정 일수가 지나면 사용자 암호가 만료되도록 설정** 옆의 확인란을 선택 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-124">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="3c9fd-125">암호가 만료되는 빈도를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-125">Type how often passwords should expire.</span></span> <span data-ttu-id="3c9fd-126">14에서 730 사이의 일수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-126">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="3c9fd-127">두 번째 상자에 사용자가 암호가 만료된다는 알림을 받는 시기를 입력한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-127">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="3c9fd-128">1에서 30 사이의 일수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-128">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="3c9fd-129">암호 만료 기능에 대해 알아야 할 중요 사항</span><span class="sxs-lookup"><span data-stu-id="3c9fd-129">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="3c9fd-p108">Outlook 앱만 사용하는 사용자는 Microsoft 365 암호가 캐시에서 만료될 때까지 해당 암호를 강제로 재설정할 수 없습니다. 이는 실제 만료 날짜의 몇 일 이후일 수 있습니다. 관리자 수준에서는 이 문제의 해결 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="3c9fd-133">마지막 암호가 다시 사용되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="3c9fd-133">Prevent last password from being used again</span></span>

<span data-ttu-id="3c9fd-134">사용자가 기존 암호를 재사용하지 못하도록 하려면 온-프레미스 AD(Active Directory)에 암호 기록을 적용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-134">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="3c9fd-135">[사용자 지정 암호 정책 만들기](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-135">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="3c9fd-136">Azure AD에서 사용자가 암호를 변경하는 경우 지난 암호를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-136">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="3c9fd-137">암호 정책은 Azure AD에서 직접 만들고 관리되는 모든 사용자 계정에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-137">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="3c9fd-138">기본 정책은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-138">This password policy can't be modified.</span></span> <span data-ttu-id="3c9fd-139">[Azure AD 암호 정책](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-139">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="3c9fd-140">온-프레미스 Active Directory Domain Services의 사용자 암호 해시를 Azure AD로 동기화(Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="3c9fd-140">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="3c9fd-141">이 문서는 클라우드 전용 사용자 (Azure AD)에 대한 만료 정책을 설정하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-141">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="3c9fd-142">암호 해시 동기화, 통과 인증 또는 ADFS와 같은 온-프레미스 페더레이션을 사용하는 하이브리드 ID 사용자에게는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-142">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="3c9fd-143">온-프레미스 AD에서 Azure AD로 사용자 암호 해시를 동기화하는 방법을 알아보려면 [Azure AD Connect 동기화를 사용하여 암호 해시 동기화 구현](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-143">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="3c9fd-144">Azure Active Directory의 암호 정책 및 제한</span><span class="sxs-lookup"><span data-stu-id="3c9fd-144">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="3c9fd-145">Azure Active Directory에서 더 많은 암호 정책 및 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-145">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="3c9fd-146">더 자세한 정보는 [Azure Active Directory의 암호 정책 및 제한](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy)에서 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-146">Check out [Password policies and account restrictions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="3c9fd-147">암호 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="3c9fd-147">Update password Policy</span></span>

<span data-ttu-id="3c9fd-148">MsolPasswordPolicy cmdlet은 지정된 도메인 또는 테넌트의 암호 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-148">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="3c9fd-149">두 가지 설정이 필요합니다. 첫 번째는 암호 변경 전까지 유효 기간을 표시하고 두 번째는 사용자가 만료 예정에 대한 미리 알림을 처음 받는 암호 만료일 전 일 수를 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-149">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="3c9fd-150">특정 도메인 또는 테넌트에 대한 암호 정책을 업데이트하는 방법에 대한 자세한 내용은 [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c9fd-150">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="3c9fd-151">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="3c9fd-151">Related content</span></span>

[<span data-ttu-id="3c9fd-152">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3c9fd-152">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="3c9fd-153">암호 초기화</span><span class="sxs-lookup"><span data-stu-id="3c9fd-153">Reset passwords</span></span>](../add-users/reset-passwords.md)
