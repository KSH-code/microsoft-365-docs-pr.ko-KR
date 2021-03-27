---
title: 관리자 계정 보호
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 관리자 계정을 설정하고 보호하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398244"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="692a5-103">관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="692a5-103">Protect your administrator accounts</span></span>

<span data-ttu-id="692a5-104">관리자 계정에는 상승된 권한이 있기 때문에 해커와 사이버 범죄자에 대한 중요한 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="692a5-105">이 문서에서는 다음에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-105">This article describes:</span></span>

- <span data-ttu-id="692a5-106">긴급에 대한 추가 관리자 계정을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="692a5-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="692a5-107">이러한 계정을 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="692a5-107">How to protect these accounts.</span></span>

<span data-ttu-id="692a5-108">Microsoft 365에 등록하고 정보를 입력하면 자동으로 전역 관리자가 됩니다. 전역 관리자는 Microsoft 관리 센터의 사용자 계정 및 다른 모든 설정을 최종적으로 제어할 수 있지만 액세스 권한이 다양한 다양한 종류의 관리자 계정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-108">When you sign up for Microsoft 365 and enter your information, you automatically become the Global admin. A Global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="692a5-109">각 [관리자 역할 종류에](/office365/admin/add-users/about-admin-roles) 대한 다양한 액세스 수준에 대한 자세한 내용은 관리자 역할 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="692a5-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="692a5-110">추가 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="692a5-110">Create additional admin accounts</span></span>

<span data-ttu-id="692a5-111">관리에만 관리자 계정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="692a5-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="692a5-112">관리자는 Office 앱을 정기적으로 사용하기 위해 별도의 사용자 계정이 있으며, 필요한 경우 계정 및 장치를 관리하고 다른 관리자 기능에서 작업하는 동안 관리 계정만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="692a5-113">또한 관리자 계정에서 Microsoft 365 라이선스를 제거하여 비용을 지불하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="692a5-114">하나 이상의 추가 전역 관리자 계정을 설정하여 다른 신뢰할 수 있는 직원에게 관리자 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-114">You'll want to set up at least one additional Global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="692a5-115">사용자 관리를 위한 별도의 관리자 계정을 만들 수도 있습니다(이 역할을 사용자 관리 **관리자라고도 합니다).**</span><span class="sxs-lookup"><span data-stu-id="692a5-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="692a5-116">자세한 내용은 관리자 역할 [정보를 참조하세요.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="692a5-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="692a5-117">추가 관리자 계정을 만들 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="692a5-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="692a5-118">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">센터로 이동한</a> 다음 왼쪽 네비게이트에서 **사용자** \> **활성** 사용자를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="692a5-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![사용자, 왼쪽으로 나타났다가 활성 사용자 선택](../media/Activeusers.png)

 2. <span data-ttu-id="692a5-120">활성 **사용자 페이지에서** 페이지  맨 위에 있는 사용자 추가를 선택하고  새 사용자 패널에서 이름 및 기타 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="692a5-121">역할 **섹션을 확장하고** 전역 관리자를 **선택해** 이 사용자에게 전역 관리자 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="692a5-122">사용자 지정 **관리자를 선택하고** 표시되는 역할을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="692a5-123">대체 전자 메일 주소 텍스트 **상자에** 대체 전자 메일을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="692a5-124">잠긴 경우 이 주소를 사용하여 암호 정보를 복구할 수 있습니다. 전역 관리자의 경우 청구서도 이 주소로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-124">You can use this address to recover your password information if you get locked out. For Global admins, a billing statement will also be sent to this address.</span></span>

    ![관리자 역할 선택](../media/adminroles.png)

 4. <span data-ttu-id="692a5-126">제품 **라이선스 섹션에서** **Microsoft 365 Business용** 선택기  를 해제로 이동하고 제품 라이선스가 없는 사용자 만들기를 **으로** **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="692a5-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![제품 라이선스 선택](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="692a5-128">응급 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="692a5-128">Create an emergency admin account</span></span>

<span data-ttu-id="692a5-129">또한 MFA(다단계 인증)로 설정되지 않은 백업 계정을 만들어 실수로 자신을 잠그지 않도록 해야 합니다(예: 두 번째 확인 양식으로 사용하는 휴대폰을 분실하는 경우).</span><span class="sxs-lookup"><span data-stu-id="692a5-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="692a5-130">이 계정의 암호가 구 또는 16자 이상인지 확인</span><span class="sxs-lookup"><span data-stu-id="692a5-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="692a5-131">이를 "차단 계정"이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="692a5-132">자신에 대한 사용자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="692a5-132">Create a user account for yourself</span></span>

<span data-ttu-id="692a5-133">사용자 계정을 사용하여 메일 확인을 포함하여 조직과 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="692a5-134">즉, 관리자 자격 증명이  *Alice.Chavez <span></span> @Contoso.org* 사용자 계정이 *Alice <span></span> @Contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="692a5-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="692a5-135">새 사용자 계정을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="692a5-135">To create a new user account:</span></span>

1. <span data-ttu-id="692a5-136">관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">센터로 이동한</a> 다음 왼쪽 네비게이트에서 **사용자** \> **활성** 사용자를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="692a5-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="692a5-137">활성 **사용자 페이지에서** 페이지  맨 위에 있는 사용자 추가를 선택하고  새 사용자 패널에서 이름 및 기타 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="692a5-138">역할 **섹션을 확장하고** 사용자(관리 액세스 **권한 없음)를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="692a5-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="692a5-139">제품 **라이선스 섹션에서** **Microsoft 365 Business의** 선택기 를 으로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="692a5-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="turn-on-security-defaults"></a><span data-ttu-id="692a5-140">보안 기본값 켜기</span><span class="sxs-lookup"><span data-stu-id="692a5-140">Turn on security defaults</span></span>

<span data-ttu-id="692a5-141">보안 기본값은 Microsoft가 조직을 대신하여 관리하는 미리 구성한 보안 설정을 제공하여 ID 관련 공격으로부터 조직을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-141">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="692a5-142">이러한 설정에는 모든 관리자 및 사용자 계정에 대해 MFA(다단계 인증)를 사용하도록 설정하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-142">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="692a5-143">보안 기본값에 대한 자세한 내용을 보고 설정하는 방법에 대한 자세한 내용은 보안 기본값 [켜기 을 참조하세요.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="692a5-143">For more information about security defaults and to learn how to enable them on, see [Turn on security defaults](m365-campaigns-conditional-access.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="692a5-144">추가 권장 사항</span><span class="sxs-lookup"><span data-stu-id="692a5-144">Additional recommendations</span></span>

- <span data-ttu-id="692a5-145">관리자 계정을 사용하려면 먼저 개인 전자 메일 계정을 포함하여 관련 없는 모든 브라우저 세션 및 앱을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="692a5-146">개인 또는 시그니치 브라우저 창에서 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="692a5-147">관리 작업을 완료한 후 브라우저 세션에서 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="692a5-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
