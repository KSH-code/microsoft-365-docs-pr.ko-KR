---
title: 관리자 계정 보호
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 관리자 계정을 설정 하 고 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: 857c24ac0ec134e119b3de083afe8dc3269bdbe2
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183378"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="4e72f-103">관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="4e72f-103">Protect your administrator accounts</span></span>

<span data-ttu-id="4e72f-104">관리자 계정에 상승 된 권한이 제공 되므로 해커 및 사이버 범죄자에 게 유용한 대상이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-104">Because the admin accounts come with elevated privileges, they are valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="4e72f-105">이 문서에서는 다음에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-105">This article describes:</span></span>

- <span data-ttu-id="4e72f-106">응급 상황에 대 한 추가 관리자 계정을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4e72f-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="4e72f-107">이러한 계정을 보호 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4e72f-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="4e72f-108">Microsoft 365 Business에 등록 하 고 정보를 입력 하면 자동으로 전역 관리자가 됩니다. 전역 관리자는 Microsoft 관리 센터의 사용자 계정 및 기타 모든 설정에 대 한 궁극적인 제어를 제공 하지만, 액세스 수준이 다양 한 다양 한 종류의 관리자 계정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-108">When you sign up for Microsoft 365 Business and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="4e72f-109">각 관리자 역할 유형에 대 한 다양 한 액세스 수준에 대 한 자세한 내용은 [관리자 역할](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e72f-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="4e72f-110">추가 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="4e72f-110">Create additional admin accounts</span></span>

<span data-ttu-id="4e72f-111">관리 계정만 관리자에 게 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="4e72f-112">관리자는 Office 앱을 정기적으로 사용 하기 위한 별도의 사용자 계정을 가져야 하며, 계정, 장치 및 기타 관리 기능 작업을 관리 하는 데 필요한 경우에만 해당 관리자 계정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts, devices and while working on other admin functions.</span></span>  <span data-ttu-id="4e72f-113">또한 관리자 계정에서 Microsoft 365 Business 라이선스를 제거 하 여 요금을 지불할 필요가 없도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-113">It is also a good idea to remove the Microsoft 365 Business license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="4e72f-114">다른 신뢰할 수 있는 직원에 게 관리자 액세스 권한을 부여 하려면 하나 이상의 추가 전역 관리자 계정을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="4e72f-115">사용자 관리를 위해 별도의 관리자 계정을 만들 수도 있습니다 (이 역할은 **사용자 관리 관리자**라고 함).</span><span class="sxs-lookup"><span data-stu-id="4e72f-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="4e72f-116">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e72f-116">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for more information.</span></span>

<span data-ttu-id="4e72f-117">추가 관리자 계정을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="4e72f-118"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">관리 센터로</a> 이동한 후 왼쪽 탐색 창에서 **사용자** \> **활성 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![사용자를 선택한 다음 왼쪽 탐색 창에서 활성 사용자를 선택 합니다.](media/Activeusers.png)

2. <span data-ttu-id="4e72f-120">**활성 사용자** 페이지에서 페이지 위쪽에 있는 **사용자 추가** 를 선택 하 고 **새 사용자** 패널에서 이름 및 기타 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-120">On the **Active users** page select **Add a user** on the top of the page and on the **New user** panel,  enter the name and other information.</span></span>
3. <span data-ttu-id="4e72f-121">**역할** 섹션을 확장 하 고 **전역 관리자** 를 선택 하 여이 사용자에 게 전역 관리자 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="4e72f-122">또한 **사용자 지정 된 관리자** 를 선택 하 고 표시 되는 역할 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="4e72f-123">대체 전자 메일 주소 텍스트 상자에 대체 전자 메일을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-123">Enter an alternate email in the Alternative email address text box.</span></span> <span data-ttu-id="4e72f-124">잠긴 경우이 주소를 사용 하 여 암호 정보를 복구할 수 있습니다. 전역 관리자의 경우에는이 주소로 대금 청구 문도 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![관리자 역할 선택](media/adminroles.png)
    
4. <span data-ttu-id="4e72f-126">**제품 라이선스** 섹션에서 **Microsoft 365 Business** 에 대 한 선택기를 **Off** 로, **제품 라이선스 없이 사용자 만들기** 를 **설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![제품 라이선스 선택](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="4e72f-128">비상 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="4e72f-128">Create an emergency admin account</span></span>

<span data-ttu-id="4e72f-129">또한 MFA (multi-factor authentication)를 사용 하 여 설정 되지 않은 백업 계정을 만들어 실수로 해제 하지 않도록 해야 합니다 (예: 확인에서 두 번째로 사용 하는 전화가 손실 되지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="4e72f-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you are using as a second from of verification).</span></span> <span data-ttu-id="4e72f-130">이 계정의 암호가 구 또는 16 자 이상 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-130">Make sure the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="4e72f-131">이를 "사용이 가능한 계정" 이라고 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="4e72f-132">자신을 위한 사용자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="4e72f-132">Create a user account for yourself</span></span>

<span data-ttu-id="4e72f-133">사용자 계정을 사용 하 여 메일 검사를 포함 하 여 조직과 공동 작업에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="4e72f-134">즉, 관리자 자격 증명은 *Chavez<span></span>@Contoso* 와 유사할 수 있으며 일반 사용자 계정은 *alice<span></span>@Contoso*와 비슷할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="4e72f-135">새 사용자 계정을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-135">To create a new user account:</span></span>
1. <span data-ttu-id="4e72f-136"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">관리 센터로</a> 이동한 후 왼쪽 탐색 창에서 **사용자** \> **활성 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="4e72f-137">**활성 사용자** 페이지에서 페이지 위쪽에 있는 **사용자 추가** 를 선택 하 고 **새 사용자** 패널에서 이름 및 기타 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-137">On the **Active users** page select **Add a user** on the top of the page and on the **New user** panel,  enter the name and other information.</span></span>
3. <span data-ttu-id="4e72f-138">**역할** 섹션을 확장 하 고 **사용자 (관리 권한 없음)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="4e72f-139">**제품 라이선스** 섹션에서 **Microsoft 365 Business** 에 대 한 선택기를 **설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="4e72f-140">각 계정에 다단계 인증을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="4e72f-141">추가 권장 사항</span><span class="sxs-lookup"><span data-stu-id="4e72f-141">Additional recommendations</span></span>

- <span data-ttu-id="4e72f-142">관리자 계정도 다단계 인증용으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-142">Be sure admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="4e72f-143">여기서는 [조건부 액세스 정책 구성](m365-campaigns-conditional-access.md)에서이 작업을 수행 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="4e72f-144">관리 계정을 사용 하기 전에 개인 전자 메일 계정을 포함 하 여 관련 없는 브라우저 세션과 앱을 모두 닫으십시오.</span><span class="sxs-lookup"><span data-stu-id="4e72f-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="4e72f-145">전용 또는 incognito 브라우저 창 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="4e72f-146">관리 작업을 완료 한 후에는 브라우저 세션에서 로그 아웃 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e72f-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>