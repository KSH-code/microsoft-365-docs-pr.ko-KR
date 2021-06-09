---
title: 아웃바운드 스팸 필터링 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(2013)에서 아웃바운드 스팸 정책을 보고, 만들고, 수정하고, 삭제하는 Exchange Online Protection 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ebff0a93acd505532773fbf5d714268df220c9a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822012"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="d6448-103">EOP에서 아웃바운드 스팸 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="d6448-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d6448-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="d6448-104">**Applies to**</span></span>
- [<span data-ttu-id="d6448-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d6448-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d6448-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="d6448-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d6448-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6448-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d6448-108">Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 Exchange Online 사서함이 없는 조직에서는 EOP를 통해 전송되는 아웃바운드 전자 메일 메시지에서 스팸 및 비정상적인 보내는 활동이 자동으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="d6448-109">조직의 사용자로부터의 아웃바운드 스팸은 일반적으로 손상된 계정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="d6448-110">의심스러운 아웃바운드 메시지는 스팸으로 표시되어(스팸 지수 또는 SCL에 관계없이) [](high-risk-delivery-pool-for-outbound-messages.md) 서비스의 신뢰도 보호를 위해 고위험 배달 풀을 통해 라우팅됩니다(즉, ip 차단 목록에서 Microsoft 365 원본 전자 메일 서버를 유지).</span><span class="sxs-lookup"><span data-stu-id="d6448-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="d6448-111">관리자는 경고 정책을 통해 의심스러운 아웃바운드 전자 메일 활동 및 차단된 사용자에게 자동으로 [알림을 수신합니다.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d6448-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="d6448-112">EOP는 스팸에 대한 조직의 전반적인 방어의 일부로 아웃바운드 스팸 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="d6448-113">자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="d6448-114">관리자는 기본 아웃바운드 스팸 정책을 보고, 편집하고, 구성할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="d6448-115">세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 아웃바운드 스팸 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d6448-116">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d6448-117">Microsoft 365 보안 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 Exchange Online 조직, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 아웃바운드 스팸 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-117">You can configure outbound spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="d6448-118">EOP에서 아웃바운드 스팸 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="d6448-119">**아웃바운드 스팸** 필터 정책: 아웃바운드 스팸 필터링 판정 및 알림 옵션에 대한 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="d6448-120">**아웃바운드** 스팸 필터 규칙: 아웃바운드 스팸 필터 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="d6448-121">보안 센터에서 아웃바운드 스팸 경찰을 관리할 때 이러한 두 요소의 차이는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the security center:</span></span>

- <span data-ttu-id="d6448-122">정책을 만들 때 실제로 둘 다에 대해 동일한 이름을 사용하여 아웃바운드 스팸 필터 규칙과 연결된 아웃바운드 스팸 필터 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="d6448-123">정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 아웃바운드 스팸 필터 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="d6448-124">다른 모든 설정은 연결된 아웃바운드 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="d6448-125">정책을 제거하면 아웃바운드 스팸 필터 규칙 및 연결된 아웃바운드 스팸 필터 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="d6448-126">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="d6448-127">자세한 내용은 이 문서의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 사용하여 아웃바운드 스팸 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="d6448-128">모든 조직에는 Default라는 기본 제공 아웃바운드 스팸 정책이 있습니다. 이 정책에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="d6448-129">정책과 연결된 아웃바운드 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 이 정책은 조직의 모든 받는 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="d6448-130">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="d6448-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d6448-131">사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="d6448-132">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d6448-133">아웃바운드 스팸 필터링의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 아웃바운드 스팸 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d6448-134">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d6448-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d6448-135"><https://security.microsoft.com>에서 보안 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-135">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="d6448-136">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://security.microsoft.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="d6448-137">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d6448-138">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d6448-139">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d6448-140">아웃바운드 스팸 정책을 추가, 수정 및 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d6448-141">아웃바운드 스팸 정책에 대한 읽기 전용 액세스의  경우 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d6448-142">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="d6448-143">**참고**:</span><span class="sxs-lookup"><span data-stu-id="d6448-143">**Notes**:</span></span>

  - <span data-ttu-id="d6448-144">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d6448-145">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="d6448-146">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="d6448-147">아웃바운드 스팸 정책에 대한 권장 설정은 [EOP 아웃바운드 스팸 필터 정책 설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="d6448-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="d6448-148">이름이 [](../../compliance/alert-policies.md) Email **sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** **(Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span><span class="sxs-lookup"><span data-stu-id="d6448-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="d6448-149">자세한 내용은 [제한된 사용자에 대한 경고 설정 확인을 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="d6448-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="d6448-150">아웃바운드 스팸 정책의 알림 옵션 대신 이러한 경고 정책을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a><span data-ttu-id="d6448-151">보안 센터를 사용하여 아웃바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d6448-151">Use the security center to create outbound spam policies</span></span>

<span data-ttu-id="d6448-152">보안 센터에서 사용자 지정 아웃바운드 스팸 정책을 만들면 스팸 필터 규칙과 연결된 스팸 필터 정책이 동시에 동일한 이름을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-152">Creating a custom outbound spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d6448-153">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-153">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d6448-154">스팸 **방지 정책** 페이지에서 만들기 아이콘 정책 만들기를 클릭한 다음 드롭다운 목록에서 ![ ](../../media/m365-cc-sc-create-icon.png)  아웃바운드를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="d6448-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="d6448-155">정책 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-155">The policy wizard opens.</span></span> <span data-ttu-id="d6448-156">**정책 이름 페이지** 에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="d6448-157">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="d6448-158">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d6448-159">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d6448-160">표시되는 **사용자, 그룹 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람(받는 사람 조건)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="d6448-161">**사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d6448-162">**그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="d6448-163">**도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="d6448-164">적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="d6448-165">이 프로세스를 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="d6448-166">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-166">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="d6448-168">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-168">next to the value.</span></span>

   <span data-ttu-id="d6448-169">사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="d6448-170">사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="d6448-171">동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="d6448-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d6448-172">서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d6448-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="d6448-173">**다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="d6448-174">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d6448-175">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d6448-176">열 **수 있는 보호 설정** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="d6448-177">**메시지 제한:** 이 섹션의 설정은 사서함의 아웃바운드 전자 **메일 메시지에 Exchange Online** 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="d6448-178">**외부 메시지 제한 설정:** 시간당 최대 외부 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="d6448-179">**내부 메시지 제한 설정:** 시간당 최대 내부 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="d6448-180">**일별 메시지 제한 설정:** 하루 최대 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="d6448-181">유효한 값은 0에서 10000까지입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="d6448-182">기본값은 0으로, 서비스 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="d6448-183">자세한 내용은 보내기 [제한을 참조하세요.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="d6448-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="d6448-184">상자에 값을 입력하거나 상자에 늘리기/축소 화살표를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="d6448-185">**메시지 제한에** 도달한 사용자에게 적용된 제한: 보호 설정 섹션의 제한이  초과되는 경우 드롭다운 목록에서 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="d6448-186">모든 작업에 대해 사용자에 지정된  받는 사람이 전자 메일 경고 정책을 보내지  못하도록 제한했습니다(그리고 이 페이지의 나중에 아웃바운드 스팸 설정으로 인해 보낸 사람이 차단된 경우 현재 중복된 알림에서) 전자 메일 알림을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="d6448-187">**다음 날까지 사용자가** 메일을 보내지 못하도록 제한 : 이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="d6448-188">전자 메일 알림이 전송됩니다. 사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d6448-189">관리자가 이 블록을 다시 정할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="d6448-190">전자 메일을 보내지 못하도록 제한된 **사용자라는** 활동 경고는 관리자에게 알리고(전자 메일 및 알림 보기 **페이지에서)**</span><span class="sxs-lookup"><span data-stu-id="d6448-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="d6448-191">정책의 아웃바운드 스팸 보내기 설정으로 인해 보낸 사람이 차단된 경우 특정 사용자에게 알림에 지정된 받는 사람도 알림을 보냅니다. </span><span class="sxs-lookup"><span data-stu-id="d6448-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="d6448-192">사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d6448-193">관리자가 이 블록을 다시 정할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="d6448-194">**사용자가 메일을 보내지** 못하도록 제한: 전자 메일 알림이 전송되고, 사용자가 보안 센터의 제한된 사용자에게 추가되고, 관리자가 제한된 사용자에서 제거될 때까지 전자 메일을 보낼 수  <https://security.microsoft.com/restrictedusers>  없습니다. 관리자가 목록에서 사용자를 제거한 후 해당 일에 대해 사용자를 다시 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the security center, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="d6448-195">자세한 내용은 스팸 전자 메일을 전송한 후 제한된 사용자 포털에서 [사용자 제거를 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="d6448-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="d6448-196">**작업 없음, 알림만:** 전자 메일 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="d6448-197">**전달 규칙:** 이 섹션의 설정을 사용하여 사서함을 외부 보낸 **Exchange Online 자동** 전자 메일 전달을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="d6448-198">자세한 내용은 에서 자동 외부 전자 메일 전달 [제어를 Microsoft 365.](external-email-forwarding.md)</span><span class="sxs-lookup"><span data-stu-id="d6448-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d6448-199">자동 전달을 사용하지 않도록 설정하면 외부 보낸 사람이 전달이 있는 사서함으로 전자 메일을 보내는 경우 받는 사람은 배달 못함 보고서(NDR 또는 반송 메시지라고도함)를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="d6448-200">내부 보낸 사람이 메시지를 보내고  전달 방법이 사서함 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) _전달(SMTP_ 전달)인 경우 내부 보낸 사람이 NDR을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="d6448-201">받은 편지함 규칙으로 인해 전달이 발생한 경우 내부 보낸 사람이 NDR을 얻지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="d6448-202">자동 전달 규칙 드롭다운 목록에서 다음 작업 중 **하나를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="d6448-203">**자동 - 시스템 제어**: 아웃바운드 스팸 필터링을 통해 자동 외부 전자 메일 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="d6448-204">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-204">This is the default value.</span></span>
     - <span data-ttu-id="d6448-205">**On**: 정책에 의해 자동 외부 전자 메일 전달을 사용하지 않도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="d6448-206">**Off:** 정책에 의해 모든 자동 외부 전자 메일 전달을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="d6448-207">**알림:** 섹션의 설정을 사용하여 의심스러운 아웃바운드 전자 메일 메시지의 복사본 및 알림을 수신해야 하는 추가 받는 사람을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="d6448-208">**이러한 사용자** 및 그룹에 이러한 제한을 초과하는 의심스러운 아웃바운드 복사본 보내기: 이 설정은 지정된 받는 사람을 의심스러운 아웃바운드 메시지의 Bcc 필드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="d6448-209">이 설정은 기본 아웃바운드 스팸 정책에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="d6448-210">만드는 사용자 지정 아웃바운드 스팸 정책에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="d6448-211">이 설정을 사용하도록 설정하려면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="d6448-212">상자가 나타나면 상자를 클릭하고 유효한 전자 메일 주소를 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 전체 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="d6448-213">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="d6448-214">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-214">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="d6448-216">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-216">next to the value.</span></span>

   - <span data-ttu-id="d6448-217">**아웃바운드 스팸 전송으로 인해 보낸 사람이 차단된 경우 이러한 사용자 및 그룹에 알릴 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d6448-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="d6448-218">이 설정은 아웃바운드 스팸 정책에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="d6448-219">전자 [메일을](../../compliance/alert-policies.md) 보내지 않는 **사용자라는** 기본 경고 정책은 사용자가 받는 사람 제한 섹션의 제한을 초과하여 차단된 경우 **이미 TenantAdmins(전역** **관리자)** 그룹의 구성원에게 전자 메일 알림을 보냅니다. </span><span class="sxs-lookup"><span data-stu-id="d6448-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="d6448-220">아웃바운드 스팸 정책에서 이 설정이 아닌 경고 정책을 사용하여 관리자 및 다른 사용자에게 **알리는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="d6448-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="d6448-221">자세한 내용은 [제한된 사용자에 대한 경고 설정 확인을 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="d6448-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="d6448-222">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d6448-223">표시되는 **검토** 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="d6448-224">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="d6448-225">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="d6448-226">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="d6448-227">표시되는 확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a><span data-ttu-id="d6448-228">보안 센터를 사용하여 아웃바운드 스팸 정책 보기</span><span class="sxs-lookup"><span data-stu-id="d6448-228">Use the security center to view outbound spam policies</span></span>

1. <span data-ttu-id="d6448-229">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-229">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d6448-230">**스팸 방지 정책** 페이지에서 다음 값 중 하나를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="d6448-231">유형 **값은** 사용자 지정 **아웃바운드 스팸 정책입니다.**</span><span class="sxs-lookup"><span data-stu-id="d6448-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="d6448-232">Name **값은** **스팸 방지 아웃바운드 정책(기본값)입니다.**</span><span class="sxs-lookup"><span data-stu-id="d6448-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="d6448-233">스팸 방지 정책 목록에는 다음 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="d6448-234">**이름**</span><span class="sxs-lookup"><span data-stu-id="d6448-234">**Name**</span></span>
   - <span data-ttu-id="d6448-235">**상태**</span><span class="sxs-lookup"><span data-stu-id="d6448-235">**Status**</span></span>
   - <span data-ttu-id="d6448-236">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="d6448-236">**Priority**</span></span>
   - <span data-ttu-id="d6448-237">**유형**</span><span class="sxs-lookup"><span data-stu-id="d6448-237">**Type**</span></span>

3. <span data-ttu-id="d6448-238">이름을 클릭하여 아웃바운드 스팸 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="d6448-239">보안 센터를 사용하여 아웃바운드 스팸 정책 수정</span><span class="sxs-lookup"><span data-stu-id="d6448-239">Use the security center to modify outbound spam policies</span></span>

1. <span data-ttu-id="d6448-240">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-240">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d6448-241">스팸 **방지 정책 페이지에서** 이름을 클릭하여 목록에서 아웃바운드 스팸 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="d6448-242">유형 열의 값이 사용자 지정  아웃바운드 스팸 정책인 경우 만든 사용자 지정 **정책입니다.**</span><span class="sxs-lookup"><span data-stu-id="d6448-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="d6448-243">스팸 방지 아웃바운드 **정책(기본값)이라는 기본 정책입니다.**</span><span class="sxs-lookup"><span data-stu-id="d6448-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="d6448-244">표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="d6448-245">설정에 대한 자세한 내용은 이 문서의 이전 보안 센터를 [사용하여](#use-the-security-center-to-create-outbound-spam-policies) 아웃바운드 스팸 정책 만들기 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-245">For more information about the settings, see the previous [Use the security center to create outbound spam policies](#use-the-security-center-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="d6448-246">기본 아웃바운드 스팸  정책의 경우 적용된 섹션을 사용할 수 없습니다(정책은 모든 사람에 적용), 정책의 이름을 바출 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="d6448-247">정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="d6448-248">사용자 지정 아웃바운드 스팸 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d6448-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="d6448-249">기본 아웃바운드 스팸 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="d6448-250">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-250">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d6448-251">스팸 **방지 정책 페이지에서** 이름을 클릭하여 목록에서 사용자 지정  **아웃바운드** 스팸 정책 유형 값이 있는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="d6448-252">표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="d6448-253">**정책 끄기**: 정책을 켜려면 ![켜기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="d6448-254">**정책**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="d6448-255">표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="d6448-256">정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="d6448-257">기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="d6448-258">사용자 지정 아웃바운드 스팸 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="d6448-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="d6448-259">기본적으로 아웃바운드 스팸 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="d6448-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="d6448-260">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="d6448-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d6448-261">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="d6448-262">정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(보안 센터에서 **우선 순위** 번호를 직접 수정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="d6448-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="d6448-263">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="d6448-264">**참고**:</span><span class="sxs-lookup"><span data-stu-id="d6448-264">**Notes**:</span></span>

- <span data-ttu-id="d6448-265">보안 센터에서는 아웃바운드 스팸 정책을 만든 후에만 우선 순위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-265">In the security center, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="d6448-266">PowerShell에서 사용자는 기존 규칙의 우선순위에 영향을 줄 수 있는 스팸 필터 규칙을 만들 때 기본 우선순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="d6448-267">아웃바운드 스팸 정책은 표시되는 순서대로 처리됩니다(첫 번째  정책의 우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="d6448-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d6448-268">기본 아웃바운드 스팸 정책의 우선 순위 값은 **가장** 낮습니다. 이 값은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="d6448-269">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-269">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d6448-270">스팸 **방지 정책** 페이지에서 이름을 클릭하여 목록에서  사용자 지정 **아웃바운드** 스팸 정책 유형 값이 있는 정책 선택을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="d6448-271">표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="d6448-272">우선 순위 값이 **0인** 아웃바운드 스팸 정책에는 우선 순위 감소 옵션만 사용할 **수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="d6448-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="d6448-273">우선 순위 값이 가장  낮은 아웃바운드 스팸 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="d6448-274">아웃바운드 스팸 정책이 세 개 이상 있는 경우 우선  순위가 가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-274">If you have three or more outbound spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="d6448-275">![우선순위 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선순위** 또는 ![우선순위 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위** 를 클릭하여 **우선순위** 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="d6448-276">작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="d6448-277">보안 센터를 사용하여 사용자 지정 아웃바운드 스팸 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d6448-277">Use the security center to remove custom outbound spam policies</span></span>

<span data-ttu-id="d6448-278">보안 센터를 사용하여 사용자 지정 아웃바운드 스팸 정책을 제거하면 스팸 필터 규칙과 해당 스팸 필터 정책이 모두 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-278">When you use the security center to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="d6448-279">기본 아웃바운드 스팸 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="d6448-280">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-280">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d6448-281">스팸 **방지 정책 페이지에서** 이름을 클릭하여 목록에서 사용자 지정  **아웃바운드** 스팸 정책 유형 값이 있는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="d6448-282">표시되는 정책 세부 정보 플라이아웃의 맨 위에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)**추가 작업**\>![정책 삭제 아이콘](../../media/m365-cc-sc-delete-icon.png)**정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="d6448-283">확인 대화 상자가 나타나면 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="d6448-284">PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 아웃바운드 스팸 정책 구성</span><span class="sxs-lookup"><span data-stu-id="d6448-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="d6448-285">앞서 설명한 바와 같이 아웃바운드 스팸 정책은 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="d6448-286">PowerShell Exchange Online 독립 실행형 EOP PowerShell에서 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙의 차이는 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="d6448-287">**\* -HostedOutboundSpamFilterPolicy** cmdlet을 사용하여 아웃바운드 스팸 필터 정책을 관리하고 **\* -HostedOutboundSpamFilterRule** cmdlet을 사용하여 아웃바운드 스팸 필터 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="d6448-288">PowerShell에서 아웃바운드 스팸 필터 정책을 먼저 만든 다음 규칙이 적용되는 정책을 식별하는 아웃바운드 스팸 필터 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d6448-289">PowerShell에서는 아웃바운드 스팸 필터 정책 및 아웃바운드 스팸 필터 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="d6448-290">PowerShell에서 아웃바운드 스팸 필터 정책을 제거하면 해당 아웃바운드 스팸 필터 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="d6448-291">PowerShell을 사용하여 아웃바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d6448-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="d6448-292">PowerShell에서 아웃바운드 스팸 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d6448-293">아웃바운드 스팸 필터 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="d6448-294">규칙이 적용되는 아웃바운드 스팸 필터 정책을 지정하는 아웃바운드 스팸 필터 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="d6448-295">**참고:**</span><span class="sxs-lookup"><span data-stu-id="d6448-295">**Notes**:</span></span>

   - <span data-ttu-id="d6448-296">새 아웃바운드 스팸 필터 규칙을 만들고 기존의 통합되지 않은 아웃바운드 스팸 필터 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="d6448-297">아웃바운드 스팸 필터 규칙은 두 개 이상의 아웃바운드 스팸 필터 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="d6448-298">정책을 만든 후까지 보안 센터에서 사용할 수 없는 PowerShell의 새 아웃바운드 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
     - <span data-ttu-id="d6448-299">새 정책을 사용하지 않도록 `$false` **설정합니다(New-HostedOutboundSpamFilterRule** cmdlet에서 사용).</span><span class="sxs-lookup"><span data-stu-id="d6448-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="d6448-300"> _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet에서 만들 때 정책의 우선 순위(우선 순위)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6448-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="d6448-301">PowerShell에서 만든 새 아웃바운드 스팸 필터 정책은 아웃바운드 스팸 필터 규칙에 정책을 할당할 때까지 보안 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="d6448-302">1단계: PowerShell을 사용하여 아웃바운드 스팸 필터 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d6448-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="d6448-303">아웃바운드 스팸 필터 정책을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="d6448-304">이 예에서는 다음 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="d6448-305">받는 사람 비율 제한은 기본값인 더 작은 값으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="d6448-306">자세한 내용은 여러 옵션 에서 Microsoft 365 [참조하세요.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="d6448-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="d6448-307">제한 중 하나에 도달하면 사용자가 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="d6448-308">구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="d6448-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="d6448-309">2단계: PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="d6448-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="d6448-310">아웃바운드 스팸 필터 규칙을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d6448-311">이 예에서는 다음 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="d6448-312">Contoso Executives라는 아웃바운드 스팸 필터 정책은 규칙과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="d6448-313">이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="d6448-314">구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="d6448-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="d6448-315">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="d6448-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="d6448-316">모든 아웃바운드 스팸 필터 정책의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="d6448-317">특정 아웃바운드 스팸 필터 정책에 대한 자세한 정보를 반환하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d6448-318">이 예에서는 Executives라는 아웃바운드 스팸 필터 정책의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="d6448-319">구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="d6448-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="d6448-320">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="d6448-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="d6448-321">기존 아웃바운드 스팸 필터 규칙을 표시하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="d6448-322">모든 아웃바운드 스팸 필터 규칙의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="d6448-323">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="d6448-324">특정 아웃바운드 스팸 필터 규칙에 대한 자세한 정보를 반환하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d6448-325">이 예에서는 Contoso Executives라는 아웃바운드 스팸 필터 규칙의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="d6448-326">구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6448-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="d6448-327">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 수정</span><span class="sxs-lookup"><span data-stu-id="d6448-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="d6448-328">이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 사용하여 아웃바운드 스팸 필터 정책 만들기 섹션에 설명된 대로 PowerShell에서 맬웨어 필터 정책을 수정할 때와 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="d6448-329">아웃바운드 스팸 필터 정책의 이름을 바울 수 **없습니다(Set-HostedOutboundSpamFilterPolicy** cmdlet에 _Name_ 매개 변수가 없음).</span><span class="sxs-lookup"><span data-stu-id="d6448-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d6448-330">보안 센터에서 아웃바운드 스팸 정책의 이름을 바출 경우 아웃바운드 스팸 필터 규칙의 이름만 바입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-330">When you rename an outbound spam policy in the security center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="d6448-331">아웃바운드 스팸 필터 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d6448-332">구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="d6448-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="d6448-333">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="d6448-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="d6448-334">PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용되지 않는 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d6448-335">기존 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6448-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="d6448-336">그렇지 않으면 PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="d6448-337">이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 사용하여 아웃바운드 스팸 필터 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="d6448-338">아웃바운드 스팸 필터 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d6448-339">구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="d6448-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="d6448-340">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d6448-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="d6448-341">PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 아웃바운드 스팸 정책(아웃바운드 스팸 필터 규칙 및 할당된 아웃바운드 스팸 필터 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="d6448-342">기본 아웃바운드 스팸 정책을 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됩니다).</span><span class="sxs-lookup"><span data-stu-id="d6448-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="d6448-343">PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="d6448-344">이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d6448-345">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d6448-346">구문과 매개 변수에 대한 자세한 내용은 [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 및 [Disable-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="d6448-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="d6448-347">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="d6448-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="d6448-348">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d6448-349">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d6448-350">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d6448-351">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d6448-352">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d6448-353">PowerShell에서 아웃바운드 스팸 필터 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d6448-354">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-354">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d6448-355">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="d6448-355">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d6448-356">**참고:**</span><span class="sxs-lookup"><span data-stu-id="d6448-356">**Notes**:</span></span>

- <span data-ttu-id="d6448-357">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-HostedOutboundSpamFilterRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="d6448-358">아웃바운드 기본 스팸 필터 정책에는 해당하는 스팸 필터 규칙이 없습니다. 항상 가장 낮은 우선 순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="d6448-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="d6448-359">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d6448-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="d6448-360">PowerShell을 사용하여 아웃바운드 스팸 필터 정책을 제거하면 해당 아웃바운드 스팸 필터 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="d6448-361">PowerShell에서 아웃바운드 스팸 필터 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d6448-362">이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d6448-363">구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterPolicy를 참조하십시오.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="d6448-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="d6448-364">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="d6448-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="d6448-365">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙을 제거하면 해당 아웃바운드 스팸 필터 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="d6448-366">PowerShell에서 아웃바운드 스팸 필터 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="d6448-367">이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d6448-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d6448-368">구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterRule을 참조하십시오.](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="d6448-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d6448-369">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="d6448-369">For more information</span></span>

[<span data-ttu-id="d6448-370">제한된 사용자 포털에서 차단된 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="d6448-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="d6448-371">아웃바운드 메시지용 높은 위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="d6448-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="d6448-372">스팸 방지 및 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="d6448-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="d6448-373">자동 전달 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="d6448-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
