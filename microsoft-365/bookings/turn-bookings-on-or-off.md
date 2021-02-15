---
title: Microsoft Bookings 설정 또는 해제
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft 365에서 Microsoft Bookings에 액세스하는 방법을 알아보십시오.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126602"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="bb2b5-103">Microsoft Bookings 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="bb2b5-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="bb2b5-104">전체 조직 또는 특정 사용자에 대해 예약을 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="bb2b5-105">사용자에 대해 Bookings를 설정하면 Bookings 페이지를 만들고 일정을 만들고 다른 사용자가 예약 시간을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="bb2b5-106">이 섹션에 설명된 관리 컨트롤은 21Vianet(중국) 고객이 운영하는 Office 365에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="bb2b5-107">Microsoft 365 관리 센터를 사용하여 조직에 대한 예약 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="bb2b5-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="bb2b5-108">전역 관리자로 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="bb2b5-109">관리 센터에서 설정  \*\*\*\*   \> **Org 설정으로** 이동하여 **Bookings를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb2b5-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="bb2b5-110">조직에서 **Bookings를 사용하여 조직에 Bookings를** 사용하도록 설정하거나 사용하지 않도록 설정하도록 허용하는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bb2b5-111">Bookings를 해제하면 Bookings 페이지 만들기 및 관리를 포함하여 서비스에 대한 모든 액세스가 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="bb2b5-112">변경 **내용 저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb2b5-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="bb2b5-113">PowerShell을 사용하여 조직에 대해 Bookings 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="bb2b5-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="bb2b5-114">PowerShell cmdlet [Set-OrganizationConfig를](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)사용하여 조직에서 Bookings를 켜거나 끄기 위해 [Exchange Online PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 연결하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="bb2b5-115">개별 사용자에 대해 예약 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="bb2b5-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="bb2b5-116">개별 사용자에 대해 Bookings를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="bb2b5-117">Microsoft 365 관리 센터로 이동한 다음 사용자  \> **활성 사용자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb2b5-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="bb2b5-118">원하는 사용자를 선택한 다음 라이선스 및 **앱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb2b5-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="bb2b5-119">앱을 **확장하고** Microsoft Bookings 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="bb2b5-120">공유하기 전에 직원 승인 필요/사용 중 정보 공유</span><span class="sxs-lookup"><span data-stu-id="bb2b5-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="bb2b5-121">관리자는 가용성 정보가 Bookings를 통해 공유되기 전에 그리고 예약 페이지를 통해 예약 가능하기 전에 조직의 직원이 옵트인(opt in)을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="bb2b5-122">이 설정은 설정 예약의 Microsoft 365 관리 **센터에서** 사용할 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="bb2b5-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="bb2b5-123">이 설정을 사용하도록 설정하면 예약 일정에서 직원으로 추가된 직원이 받는 전자 메일 알림에서 승인/거부 링크를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="bb2b5-124">이 기능은 전 세계를 Microsoft 365 고객에게 점진적으로 배포하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="bb2b5-125">Microsoft 365 관리 센터에 이 옵션이 없는 경우 곧 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="bb2b5-126">공유 공유 옵션 차단</span><span class="sxs-lookup"><span data-stu-id="bb2b5-126">Block social sharing options</span></span>

<span data-ttu-id="bb2b5-127">관리자는 소셜 네트워크에서 예약 페이지를 공유하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="bb2b5-128">이 설정은 설정 예약의 Microsoft 365 관리 **센터에서** 사용할 \>  \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="bb2b5-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="bb2b5-129">이 기능은 전 세계를 Microsoft 365 고객에게 점진적으로 배포하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="bb2b5-130">Microsoft 365 관리 센터에 이 옵션이 없는 경우 곧 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="bb2b5-131">선택한 사용자만 Bookings 일정을 만들 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="bb2b5-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="bb2b5-132">정책 제한을 사용하면 라이선스가 부여된 사용자가 Bookings 일정을 만들 수 없는 것을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="bb2b5-133">먼저 전체 조직에 대해 Bookings를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="bb2b5-134">조직의 모든 사용자에게 Bookings 라이선스가 있지만 정책에 포함된 사용자만 Bookings 일정을 만들고 만든 일정에 액세스할 수 있는 사용자를 모두 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="bb2b5-135">이 정책에 포함된 사용자는 새 Bookings 일정을 만들 수 있으며 관리자 역할을 포함하여 모든 용량의 직원으로 기존 Bookings 일정에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="bb2b5-136">이 정책에 포함되지 않은 사용자는 새 Bookings 일정을 만들 수 없습니다. 이렇게 하려고 하면 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="bb2b5-137">Exchange Online PowerShell을 사용하여 다음 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="bb2b5-138">Exchange Online cmdlet 실행에 대한 자세한 내용은 [Exchange Online PowerShell에 연결을 참조하세요.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="bb2b5-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb2b5-139">아래 단계에서는 조직에서 OWA(Outlook Web App) 사서함 정책이 만들어졌다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="bb2b5-140">Bookings 일정을 만들 수 있도록 허용해야 하는 사용자에 대한 새 사서함 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="bb2b5-141">Bookings 일정 만들기는 새 사서함 정책에 따라 기본적으로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="bb2b5-142">자세한 내용은 [New-OwaMailboxPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="bb2b5-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="bb2b5-143">Bookings 일정을 만들 수 있는 권한을 부여할 각 사용자에 대해 이 명령을 실행하여 관련 사용자에게 이 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="bb2b5-144">자세한 내용은 [Set-CASMailbox를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)</span><span class="sxs-lookup"><span data-stu-id="bb2b5-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="bb2b5-145">선택 사항: 조직의 다른 모든 사용자에 대해 Bookings를 사용하지 않도록 설정하려는 경우 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="bb2b5-146">자세한 내용은 [Set-OwaMailboxPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="bb2b5-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="bb2b5-147">OWA 사서함 정책에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb2b5-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="bb2b5-148">Exchange Online에서 웹에서 Outlook 사서함 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="bb2b5-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="bb2b5-149">Exchange Online의 사서함에서 웹에서 Outlook 사서함 정책 적용 또는 제거</span><span class="sxs-lookup"><span data-stu-id="bb2b5-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
