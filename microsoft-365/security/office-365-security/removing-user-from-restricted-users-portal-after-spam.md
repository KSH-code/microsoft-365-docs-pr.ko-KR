---
title: 제한된 사용자 포털에서 차단된 사용자 제거
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 관리자는 Office 365의 제한된 사용자 포털에서 사용자를 제거 하는 방법을 알아볼 수 있습니다. 사용자는 일반적으로 계정 손상의 결과로 아웃바운드 스팸 전송을 위해 제한된 사용자 포털에 추가됩니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ebc0cd1d6440673ec453322d3e4c3af2e88a028
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406715"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="4363c-104">Office 365의 제한된 사용자 포털에서 차단된 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="4363c-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4363c-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="4363c-105">**Applies to**</span></span>
- [<span data-ttu-id="4363c-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4363c-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4363c-107">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="4363c-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4363c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4363c-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4363c-109">사용자가 [서비스 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 또는 [아웃바운드 스팸 정책](configure-the-outbound-spam-policy.md)에 지정된 아웃바운드 전송 제한 중 하나를 초과하는 경우 전자 메일 보내기가 제한되지만 계속 전자 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="4363c-110">보안 및 규정 준수 센터의 제한된 사용자 포털에 사용자가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-110">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="4363c-111">사용자가 전자 메일을 보내려고 하면 메시지가 오류 코드 [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 및 다음 텍스트와 함께 배달 못 함 보고서(NDR 또는 바운스 메시지라고도 함)로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="4363c-112">"유효한 보낸 사람으로 인식되지 않았기 때문에 메시지를 배달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="4363c-113">가장 일반적인 이유는 전자 메일 주소가 스팸 메일을 보내는 것으로 의심어서 더 이상 전자 메일을 보낼 수 없는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="4363c-114">도움이 필요하면 전자 메일 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="4363c-115">원격 서버에서 '550 5.1.8 액세스가 거부되었습니다. 잘못된 아웃 바운드 보낸 사람"이 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="4363c-116">관리자는 보안 및 규정 준수 센터 또는 Exchange Online PowerShell에서 제한된 보낸 사람 포털의 사용자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-116">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4363c-117">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="4363c-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4363c-118"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4363c-119">**제한된 사용자** 페이지로 직접 이동하려면 <https://protection.office.com/restrictedusers>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-119">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="4363c-120">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4363c-121">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4363c-122">제한된 사용자 포털에서 사용자를 제거하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-122">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4363c-123">제한된 사용자 포털에 대한 읽기 전용 액세스를 위해서는 **글로벌 리더** 또는 **보안 리더** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-123">For read-only access to the Restricted Users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4363c-124">자세한 내용은 [Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-124">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="4363c-125">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4363c-126">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="4363c-127">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-127">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="4363c-128">아웃바운드 전자 메일 제한을 초과 하는 보낸 사람은 손상된 계정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="4363c-129">제한된 사용자 포털에서 사용자를 제거하기 전에 해당 계정을 다시 제어하기 위해 필요한 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-129">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="4363c-130">자세한 내용은 [Office 365에서 손상된 전자 메일 계정에 응답](responding-to-a-compromised-email-account.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="4363c-131">보안 및 규정 준수 센터를 사용하여 제한 된 사용자 목록에서 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="4363c-131">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="4363c-132">보안 및 규정 준수 센터에서 **위협 관리** \> **검토** \> **제한된 사용자** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-132">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="4363c-133">차단을 해제하려는 사용자를 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-133">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="4363c-134">**동작** 열에서 **차단 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-134">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="4363c-135">플라이아웃하면 전송이 제한된 계정에 대한 세부 정보로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-135">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="4363c-136">계정이 실제로 손상될 경우에 적절한 조치를 취하는지 확인하기 위해 권장 사항을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="4363c-137">완료되면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-137">Click **Next** when done.</span></span>

4. <span data-ttu-id="4363c-138">다음 화면에는 이후 손상을 방지하는 데 도움이 되는 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="4363c-139">MFA(다단계 인증)를 사용하도록 설정하고 암호를 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-139">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="4363c-140">작업이 완료되면 **사용자 차단 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-140">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="4363c-141">**예** 를 클릭하여 변경 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4363c-142">모든 제한 사항을 사용자에게서 제거하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="4363c-143">제한된 사용자에 대한 경고 설정 확인</span><span class="sxs-lookup"><span data-stu-id="4363c-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="4363c-144">**전자 메일을 보내지 못하도록 제한된 사용자** 라는 기본 경고 정책은 사용자가 아웃바운드 메일을 보내지 못하도록 차단되었을 때 관리자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="4363c-145">이러한 설정을 확인하고 알림을 보낼 사용자를 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="4363c-146">경고 정책에 대한 자세한 내용은 [보안 및 규정 준수 센터의 경고 정책](../../compliance/alert-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-146">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4363c-147">경고가 작동하려면 감사 로그 검색이 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="4363c-148">자세한 내용은 [감사 로그 검색 설정 및 해제](../../compliance/turn-audit-log-search-on-or-off.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="4363c-149">보안 및 규정 준수 센터에서 **경고** \> **경고 정책** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-149">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="4363c-150">**전자 메일 전송이 제한된 사용자** 를 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-150">Find and select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="4363c-151">플라이아웃이 나타나면 다음 설정을 확인하거나 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-151">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="4363c-152">**상태**: 경고가 ![토글 켬](../../media/scc-toggle-on.png)으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-152">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="4363c-153">**전자 메일 받는 사람**: **편집** 을 클릭하고 **받는 사람 편집** 플라이아웃이 나타나면 다음 설정을 확인하거나 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-153">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="4363c-154">**전자 메일 알림 보내기**: 확인란이 선택(**설정**)되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-154">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="4363c-155">**전자 메일 받는 사람**: 기본값은 **TenantAdmins**(즉, **전역 관리자** 구성원)입니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-155">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="4363c-156">받는 사람을 더 추가하려면 상자의 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-156">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="4363c-157">받는 사람 목록이 표시되면 이름을 입력하여 필터링하고 받는 사람을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-157">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="4363c-158">해당 이름 옆의 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭하여 상자에서 기존의 받는 사람을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-158">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="4363c-159">**일별 알림 제한**: 기본값은 **제한 없음** 이지만 일별 최대 알림 수에 대한 한도를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-159">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="4363c-160">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-160">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="4363c-161">**전자 메일을 보내지 못하도록 제한된 사용자** 플라이아웃으로 돌아가서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-161">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="4363c-162">Exchange Online PowerShell을 사용하여 제한된 사용자 목록에서 사용자 보기 및 제거</span><span class="sxs-lookup"><span data-stu-id="4363c-162">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="4363c-163">전자 메일을 보내지 못하도록 제한된 사용자 목록을 보려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-163">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="4363c-164">특정 사용자에 대한 세부 정보를 보려면 \<emailaddress\>를 그들의 전자 메일 주소로 바꾸고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-164">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="4363c-165">자세한 구문 및 매개 변수 정보는 [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-165">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="4363c-166">제한된 사용자 목록에서 사용자를 제거하려면 \<emailaddress\>를 그들의 전자 메일 주소로 바꾸고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4363c-166">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="4363c-167">자세한 구문 및 매개 변수 정보는 [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4363c-167">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
