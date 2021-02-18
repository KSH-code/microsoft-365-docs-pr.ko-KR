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
description: 관리자는 EOP(Exchange Online Protection)에서 아웃바운드 스팸 정책을 보고, 만들고, 수정하고, 삭제하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 742c58a8a94938c5896382a6d53acac127974f02
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288936"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="6fdf0-103">EOP에서 아웃바운드 스팸 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="6fdf0-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6fdf0-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-104">**Applies to**</span></span>
- [<span data-ttu-id="6fdf0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6fdf0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6fdf0-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="6fdf0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6fdf0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fdf0-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6fdf0-108">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP를 통해 전송되는 아웃바운드 전자 메일 메시지에서 스팸 및 비정상적인 보내는 활동이 자동으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="6fdf0-109">조직의 사용자로부터의 아웃바운드 스팸은 일반적으로 손상된 계정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="6fdf0-110">의심스러운 아웃바운드 메시지는 스팸으로 표시되어(스팸 지수 또는 SCL에 상관없이) [](high-risk-delivery-pool-for-outbound-messages.md) 서비스의 신뢰도 보호를 위해 높은 위험 배달 풀을 통해 라우팅됩니다(즉, Microsoft 365 원본 전자 메일 서버를 IP 차단 목록에서 유지).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="6fdf0-111">관리자는 경고 정책을 통해 의심스러운 아웃바운드 전자 메일 활동 및 차단된 사용자에게 자동으로 [알림을 제공합니다.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="6fdf0-112">EOP는 스팸에 대한 조직의 전반적인 방어의 일부로 아웃바운드 스팸 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="6fdf0-113">자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="6fdf0-114">관리자는 기본 아웃바운드 스팸 정책을 보고 편집하고 구성할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="6fdf0-115">세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 아웃바운드 스팸 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="6fdf0-116">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="6fdf0-117">보안 및 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 아웃바운드 스팸 정책을 구성할 수 있습니다. &</span><span class="sxs-lookup"><span data-stu-id="6fdf0-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="6fdf0-118">EOP에서 아웃바운드 스팸 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="6fdf0-119">**아웃바운드 스팸 필터 정책:** 아웃바운드 스팸 필터링 판정 및 알림 옵션에 대한 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="6fdf0-120">**아웃바운드 스팸 필터 규칙:** 아웃바운드 스팸 필터 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="6fdf0-121">보안 및 준수 센터에서 아웃바운드 스팸 & 경우 이러한 두 요소의 차이는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="6fdf0-122">정책을 만들 때 실제로 둘 다에 대해 동일한 이름을 사용하여 아웃바운드 스팸 필터 규칙과 연결된 아웃바운드 스팸 필터 정책을 동시에 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6fdf0-123">정책을 수정할 때 이름, 우선 순위, 사용 또는 사용하지 않도록 설정된 설정 및 받는 사람 필터와 관련된 설정은 아웃바운드 스팸 필터 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="6fdf0-124">다른 모든 설정은 연결된 아웃바운드 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="6fdf0-125">정책을 제거하면 아웃바운드 스팸 필터 규칙 및 연결된 아웃바운드 스팸 필터 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="6fdf0-126">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6fdf0-127">자세한 내용은 이 문서 부분의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 사용하여 아웃바운드 스팸 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="6fdf0-128">모든 조직에는 다음 속성이 있는 Default라는 기본 제공 아웃바운드 스팸 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="6fdf0-129">정책과 연결된 아웃바운드 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 이 정책은 조직의 모든 받는 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="6fdf0-130">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="6fdf0-131">사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="6fdf0-132">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="6fdf0-133">아웃바운드 스팸 필터링의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 아웃바운드 스팸 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6fdf0-134">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6fdf0-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6fdf0-135"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6fdf0-136">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="6fdf0-137">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6fdf0-138">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6fdf0-139">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-139">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6fdf0-140">아웃바운드 스팸 정책을 추가, 수정 및 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 구성원이 **되거나** 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6fdf0-141">아웃바운드 스팸 정책에 대한 읽기 전용 액세스 권한을  사용하려면 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나,</span><span class="sxs-lookup"><span data-stu-id="6fdf0-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6fdf0-142">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-142">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="6fdf0-143">**참고**:</span><span class="sxs-lookup"><span data-stu-id="6fdf0-143">**Notes**:</span></span>

  - <span data-ttu-id="6fdf0-144">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6fdf0-145">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="6fdf0-146">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-146">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="6fdf0-147">아웃바운드 스팸 정책에 대한 권장 설정은 EOP 아웃바운드 스팸 필터 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="6fdf0-148">전자 [](../../compliance/alert-policies.md) 메일 보내기 제한이라는 기본 경고 정책, 검색된 의심스러운  전자 메일 전송 패턴 및 사용자가 이미 **TenantAdmins(전역** **관리자)** 그룹의 구성원에게 전자 메일 알림을 보내지 못하도록 제한되어 있으며 아웃바운드 스팸으로 인해 비정상적인 아웃바운드 전자 메일 활동 및 차단된 사용자에 대한 전자 메일 알림을 보내지 못하도록 제한되었습니다. </span><span class="sxs-lookup"><span data-stu-id="6fdf0-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="6fdf0-149">자세한 내용은 제한된 [사용자에 대한 경고 설정 확인을 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="6fdf0-150">아웃바운드 스팸 정책의 알림 옵션 대신 이러한 경고 정책을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="6fdf0-151">보안 및 & 센터를 사용하여 아웃바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6fdf0-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="6fdf0-152">Security & 준수 센터에서 사용자 지정 아웃바운드 스팸 정책을 만들면 스팸 필터 규칙과 연결된 스팸 필터 정책이 동시에 두 가지에 대해 동일한 이름을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="6fdf0-153">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6fdf0-154">스팸 방지 **설정 페이지에서** 아웃바운드 정책 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="6fdf0-155">**아웃바운드 스팸 필터 정책이** 열리면 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="6fdf0-156">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="6fdf0-157">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="6fdf0-158">(선택 사항) 알림 **섹션을** 확장하여 의심스러운 아웃바운드 전자 메일 메시지의 복사본 및 알림을 수신해야 하는 추가 사용자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="6fdf0-159">**의심스러운** 아웃바운드 전자 메일 메시지 복사본을 특정 사용자에게 보냅니다. 이 설정은 지정된 사용자를 의심스러운 아웃바운드 메시지에 Bcc 받는 사람으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="6fdf0-160">이 설정은 기본 아웃바운드 스팸 정책에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="6fdf0-161">만드는 사용자 지정 아웃바운드 스팸 정책에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="6fdf0-162">이 설정을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="6fdf0-162">To enable this setting:</span></span>

     1. <span data-ttu-id="6fdf0-163">설정을 사용하도록 설정하려면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="6fdf0-164">사용자 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-164">Click **Add people**.</span></span> <span data-ttu-id="6fdf0-165">받는 사람 **추가 또는 제거 플라이아웃에** 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="6fdf0-166">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-166">Enter the sender's email address.</span></span> <span data-ttu-id="6fdf0-167">전자 메일 주소가 여러 개인 경우 각 주소를 세미코론으로 구분하여 지정할 수 ;) 또는 한 줄에 받는 사람 한 명.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="6fdf0-168">이</span><span class="sxs-lookup"><span data-stu-id="6fdf0-168">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="6fdf0-170">을(를) 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-170">to add the recipients.</span></span>

        <span data-ttu-id="6fdf0-171">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="6fdf0-172">추가한 받는 사람은 플라이아웃의 받는 사람 **목록** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="6fdf0-173">받는 사람을 삭제하려면 제거 ![ 단추를 ](../../media/scc-remove-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="6fdf0-174">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="6fdf0-175">이 설정을 사용하지 않도록 설정한 경우 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="6fdf0-176">**아웃바운드 스팸 전송으로** 인해 보낸 사람이 차단된 경우 특정 사용자에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="6fdf0-177">이 설정은 아웃바운드 스팸 정책에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-177">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="6fdf0-178">전자 [메일을](../../compliance/alert-policies.md) 보내지 않는 **사용자** 제한이라는 기본 경고 정책은 사용자가 받는 사람 제한 섹션의 제한을 초과하여 차단된 경우 **TenantAdmins(전역** **관리자)** 그룹의 구성원에게 이미 전자 메일 알림을 보냅니다. </span><span class="sxs-lookup"><span data-stu-id="6fdf0-178">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="6fdf0-179">아웃바운드 스팸 정책에서 이 설정 대신 경고 정책을 사용하여 관리자 및 기타 사용자에게 **알리는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-179">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="6fdf0-180">자세한 내용은 제한된 [사용자에 대한 경고 설정 확인을 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-180">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="6fdf0-181">(선택 사항) 받는 사람 제한 **섹션을 확장하여** 의심스러운 아웃바운드 전자 메일 메시지에 대한 제한 및 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-181">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="6fdf0-182">이러한 설정은 클라우드 기반 사서함에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-182">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="6fdf0-183">**사용자당 최대 받는 사람 수**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-183">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="6fdf0-184">유효한 값은 0에서 10000까지입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-184">A valid value is 0 to 10000.</span></span> <span data-ttu-id="6fdf0-185">기본값은 0으로, 서비스 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-185">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="6fdf0-186">자세한 내용은 보내기 [제한을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-186">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="6fdf0-187">**외부 시간 제한:** 시간당 최대 외부 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-187">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="6fdf0-188">**내부 시간 제한:** 시간당 최대 내부 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-188">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="6fdf0-189">**일별 제한:** 일별 최대 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-189">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="6fdf0-190">**사용자가 위의** 제한을 초과하는 경우의 작업: 받는 사람 제한  중 하나를 초과할 때 수행하도록 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="6fdf0-191">모든 작업에 대해 사용자에 지정된  받는 사람이 전자 메일 경고 정책을 보내지  못하도록 제한했습니다(그리고 아웃바운드 스팸 정책의 아웃바운드 스팸 설정으로 인해 보낸 사람이 차단된 경우 현재 중복된 특정 사용자에게 알림).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-191">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="6fdf0-192">**다음 날까지** 사용자가 메일을 보내지 못하도록 제한합니다. 이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-192">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="6fdf0-193">전자 메일 알림이 전송됩니다. 사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-193">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="6fdf0-194">관리자가 이 블록을 다시 정할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-194">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="6fdf0-195">전자 메일을 보내지 못하도록 제한된 **User라는** 활동 경고는 전자 메일을 통해 관리자에게 알림(전자 메일 및 알림 보기 **페이지)에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-195">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="6fdf0-196">정책에서 아웃바운드 스팸 설정으로 인해 보낸 사람이 차단된 경우 특정 사용자에게 알림에 지정된 모든 받는 사람도 알림을 보냅니다. </span><span class="sxs-lookup"><span data-stu-id="6fdf0-196">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="6fdf0-197">사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-197">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="6fdf0-198">관리자가 이 블록을 다시 정할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-198">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="6fdf0-199">사용자가 메일을 보내지 못하도록 **제한:** 전자 메일 알림이 전송되고, 사용자가 보안 & 준수 센터의 **[제한된 사용자] <https://sip.protection.office.com/restrictedusers>** 포털에 추가되고,  관리자가 제한된 사용자 포털에서 전자 메일을 제거할 때까지 전자 메일을 보낼 수 없습니다. 관리자가 목록에서 사용자를 제거하면 해당 일에 대해 사용자가 다시 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-199">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="6fdf0-200">자세한 내용은 스팸 메일을 전송한 후 제한된 사용자 포털에서 [사용자 제거를 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-200">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="6fdf0-201">**작업 없음, 알림만:** 전자 메일 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-201">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="6fdf0-202">(선택 사항) 자동 **전달 섹션을 확장하여** 사용자가 외부 보낸 사람에 대한 자동 전자 메일 전달을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-202">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="6fdf0-203">자세한 내용은 [Microsoft 365에서](external-email-forwarding.md)자동 외부 전자 메일 전달 제어를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-203">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="6fdf0-204">2020년 9월 전에는 이러한 설정을 사용할 수 있지만 적용되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-204">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="6fdf0-205">이러한 설정은 클라우드 기반 사서함에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-205">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="6fdf0-206">자동 전달을 사용하지 않도록 설정하면 외부 보낸 사람이 전달이 있는 사서함으로 전자 메일을 보내는 경우 받는 사람은 배달 못함 보고서(NDR 또는 반송 메시지라고도함)를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-206">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="6fdf0-207">내부 보낸 사람이 메시지를 보내고  전달 방법이 사서함 [](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) _전달(SMTP_ 전달)인 경우 내부 보낸 사람이 NDR을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-207">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="6fdf0-208">받은 편지함 규칙으로 인해 전달이 발생한 경우 내부 보낸 사람이 NDR을 얻지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-208">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="6fdf0-209">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-209">The available values are:</span></span>

   - <span data-ttu-id="6fdf0-210">**자동 - 시스템 제어**: 아웃바운드 스팸 필터링이 자동 외부 전자 메일 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-210">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="6fdf0-211">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-211">This is the default value.</span></span>
   - <span data-ttu-id="6fdf0-212">**On**: 자동 외부 전자 메일 전달이 정책에 의해 사용하지 않도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-212">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="6fdf0-213">**해제:** 정책에 의해 모든 자동 외부 전자 메일 전달이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-213">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="6fdf0-214">(필수) 적용된 **섹션을** 확장하여 정책이 적용되는 내부 보낸 사람 식별</span><span class="sxs-lookup"><span data-stu-id="6fdf0-214">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="6fdf0-215">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-215">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="6fdf0-216">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<sender1\>_ 혹은 _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-216">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="6fdf0-217">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<sender1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-217">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="6fdf0-218">사용 가능한 모든 조건을 보려면 **조건 추가** 를 세 번 클릭하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-218">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="6fdf0-219">![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-219">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="6fdf0-220">**보낸 사람 도메인**: 조직에서 구성된 허용 도메인 중 하나 이상에서 보낸 사람 지정</span><span class="sxs-lookup"><span data-stu-id="6fdf0-220">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="6fdf0-221">**태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-221">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="6fdf0-222">두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-222">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="6fdf0-223">**보낸 사람 :** 조직에서 하나 이상의 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-223">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="6fdf0-224">**태그 추가** 를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-224">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="6fdf0-225">태그 추가 **상자를 다시** 클릭하여 보낸 사람 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-225">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="6fdf0-226">**보낸 사람이 다음의** 구성원입니다. 조직에서 하나 이상의 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-226">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="6fdf0-227">**태그 추가** 를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-227">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="6fdf0-228">태그 추가 **상자를 다시** 클릭하여 보낸 사람 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-228">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="6fdf0-229">**다음의 경우 제외**: 규칙에 대한 예외를 추가하려면 **조건 추가** 를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-229">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="6fdf0-230">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-230">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="6fdf0-231">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-231">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="6fdf0-232">보안 및 & 센터를 사용하여 아웃바운드 스팸 정책 보기</span><span class="sxs-lookup"><span data-stu-id="6fdf0-232">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="6fdf0-233">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6fdf0-234">스팸 방지 **설정 페이지에서** 확장 아이콘을 클릭하여 아웃바운드 스팸 ![ 정책을 ](../../media/scc-expand-icon.png) 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="6fdf0-235">아웃바운드 스팸 필터 정책이라는 기본 **정책입니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-235">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="6fdf0-236">유형 열의 값이 사용자 지정  아웃바운드 스팸 정책인 경우 만든 사용자 지정 **정책입니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="6fdf0-237">정책 설정이 표시되는 확장된 정책 세부 정보에서 표시되거나 정책 편집을 **클릭할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-237">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="6fdf0-238">보안 및 & 센터를 사용하여 아웃바운드 스팸 정책 수정</span><span class="sxs-lookup"><span data-stu-id="6fdf0-238">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="6fdf0-239">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6fdf0-240">스팸 방지 **설정 페이지에서** 확장 아이콘을 클릭하여 아웃바운드 스팸 ![ 정책을 ](../../media/scc-expand-icon.png) 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="6fdf0-241">아웃바운드 스팸 필터 정책이라는 기본 **정책입니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="6fdf0-242">유형 열의 값이 사용자 지정  아웃바운드 스팸 정책인 경우 만든 사용자 지정 **정책입니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="6fdf0-243">**정책 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-243">Click **Edit policy**.</span></span>

<span data-ttu-id="6fdf0-244">사용자 지정 아웃바운드 스팸 정책의 경우 플라이아웃에 나타나는 사용 가능한 설정은 보안 및 준수 센터를 사용하여 [아웃바운드](#use-the-security--compliance-center-to-create-outbound-spam-policies) 스팸 정책 & 섹션에 설명된 설정과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-244">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="6fdf0-245">아웃바운드 스팸 필터 정책이라는 기본 아웃바운드 스팸 정책의 경우 적용된 섹션을 사용할 수 없습니다(정책은 모든 사용자에 적용), 정책의 이름을 바을 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="6fdf0-245">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="6fdf0-246">정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-246">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="6fdf0-247">아웃바운드 스팸 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6fdf0-247">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="6fdf0-248">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6fdf0-249">스팸 **방지** 설정 페이지에서 확장 아이콘을 클릭하여 만든 사용자 지정 정책을 확장합니다(유형 열의 값은 사용자 지정 아웃바운드 ![ 스팸 ](../../media/scc-expand-icon.png)  **정책).**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="6fdf0-250">표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-250">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="6fdf0-251">토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-251">Move the toggle to the left to disable the policy:</span></span> ![토글 끔](../../media/scc-toggle-off.png)

   <span data-ttu-id="6fdf0-253">토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-253">Move the toggle to the right to enable the policy:</span></span> ![토글 켬](../../media/scc-toggle-on.png)

<span data-ttu-id="6fdf0-255">기본 아웃바운드 스팸 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-255">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="6fdf0-256">사용자 지정 아웃바운드 스팸 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="6fdf0-256">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="6fdf0-257">기본적으로 아웃바운드 스팸 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-257">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="6fdf0-258">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-258">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6fdf0-259">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-259">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6fdf0-260">사용자 지정 아웃바운드 스팸 정책은 처리되는 순서대로 표시됩니다(첫 번째 정책의 우선 순위 값은 0). </span><span class="sxs-lookup"><span data-stu-id="6fdf0-260">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="6fdf0-261">아웃바운드 스팸  필터 정책이라는 기본 아웃바운드 스팸 정책의 우선 순위 값은 **가장** 낮습니다. 이 정책은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-261">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="6fdf0-262">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-262">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="6fdf0-263">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6fdf0-264">스팸 방지 **설정** 페이지에서 유형 열의 값이 사용자  지정 아웃바운드 스팸 정책인 **정책을 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-264">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="6fdf0-265">**우선순위** 열의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-265">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="6fdf0-266">우선 순위가 가장 높은 사용자 지정 아웃바운드 스팸 정책의 값은 ![ 아래쪽 화살표 아이콘 ](../../media/ITPro-EAC-DownArrowIcon.png) **0입니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-266">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="6fdf0-267">우선 순위가 가장 낮은 사용자 지정 아웃바운드 스팸 정책의 값은 위쪽 화살표 아이콘 ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **n(예:** ![ 위쪽 화살표 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png) **3)입니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-267">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="6fdf0-268">사용자 지정 아웃바운드 스팸 정책이 세 개 이상 있는 경우 가장 높은 우선 순위와 가장 낮은 우선 순위 사이의 정책에는 위쪽 화살표 아이콘 아래쪽 화살표 아이콘 n(예: 위쪽 화살표 아이콘 아래쪽 화살표 아이콘 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)이** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-268">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="6fdf0-269">이</span><span class="sxs-lookup"><span data-stu-id="6fdf0-269">Click</span></span> ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="6fdf0-271">또는</span><span class="sxs-lookup"><span data-stu-id="6fdf0-271">or</span></span> ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="6fdf0-273">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-273">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="6fdf0-274">보안 및 & 센터를 사용하여 아웃바운드 스팸 정책 제거</span><span class="sxs-lookup"><span data-stu-id="6fdf0-274">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="6fdf0-275">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="6fdf0-276">스팸 **방지** 설정 페이지에서 확장 아이콘을 클릭하여 삭제할 사용자 지정 정책을 확장합니다(유형 열은 사용자 지정 아웃바운드 ![ 스팸 ](../../media/scc-expand-icon.png)  **정책).**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-276">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="6fdf0-277">표시되는 확장된 정책 세부 정보에서 **정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-277">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="6fdf0-278">표시되는 경고 대화 상자에서 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-278">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="6fdf0-279">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="6fdf0-280">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 아웃바운드 스팸 정책 구성</span><span class="sxs-lookup"><span data-stu-id="6fdf0-280">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="6fdf0-281">앞서 설명한 바와 같이 아웃바운드 스팸 정책은 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-281">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="6fdf0-282">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙의 차이점이 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-282">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="6fdf0-283">**\* -HostedOutboundSpamFilterPolicy** cmdlet을 사용하여 아웃바운드 스팸 필터 정책을 관리하고 **\* -HostedOutboundSpamFilterRule** cmdlet을 사용하여 아웃바운드 스팸 필터 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-283">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="6fdf0-284">PowerShell에서 먼저 아웃바운드 스팸 필터 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 아웃바운드 스팸 필터 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-284">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6fdf0-285">PowerShell에서는 아웃바운드 스팸 필터 정책 및 아웃바운드 스팸 필터 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-285">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="6fdf0-286">PowerShell에서 아웃바운드 스팸 필터 정책을 제거하면 해당 아웃바운드 스팸 필터 규칙이 자동으로 제거되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-286">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="6fdf0-287">PowerShell을 사용하여 아웃바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6fdf0-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="6fdf0-288">PowerShell에서 아웃바운드 스팸 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6fdf0-289">아웃바운드 스팸 필터 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-289">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="6fdf0-290">규칙이 적용되는 아웃바운드 스팸 필터 정책을 지정하는 아웃바운드 스팸 필터 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="6fdf0-291">**참고:**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-291">**Notes**:</span></span>

- <span data-ttu-id="6fdf0-292">새 아웃바운드 스팸 필터 규칙을 만들고 기존의 통합되지 않은 아웃바운드 스팸 필터 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="6fdf0-293">아웃바운드 스팸 필터 규칙은 두 개 이상의 아웃바운드 스팸 필터 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="6fdf0-294">정책을 만든 후 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새 아웃바운드 스팸 필터 정책에 대해 다음 설정을 구성할 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="6fdf0-295">새 정책을 사용할 수 `$false` **없습니다(New-HostedOutboundSpamFilterRule** cmdlet에서 사용).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="6fdf0-296"> _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet에서 만들기 중 정책의 우선 순위(우선 순위)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="6fdf0-297">PowerShell에서 만든 새 아웃바운드 스팸 필터 정책은 스팸 필터 규칙에 정책을 할당할 때까지 보안 & 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="6fdf0-298">1단계: PowerShell을 사용하여 아웃바운드 스팸 필터 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6fdf0-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="6fdf0-299">아웃바운드 스팸 필터 정책을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="6fdf0-300">이 예에서는 다음 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="6fdf0-301">받는 사람 비율 제한은 기본값인 더 작은 값으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="6fdf0-302">자세한 내용은 [Microsoft 365 옵션 전반에 걸쳐 전송 제한을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-302">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="6fdf0-303">제한 중 하나에 도달하면 사용자가 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="6fdf0-304">구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="6fdf0-305">2단계: PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="6fdf0-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="6fdf0-306">아웃바운드 스팸 필터 규칙을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="6fdf0-307">이 예에서는 다음 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="6fdf0-308">Contoso Executives라는 아웃바운드 스팸 필터 정책은 규칙과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="6fdf0-309">이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="6fdf0-310">구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="6fdf0-311">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="6fdf0-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="6fdf0-312">모든 아웃바운드 스팸 필터 정책의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="6fdf0-313">특정 아웃바운드 스팸 필터 정책에 대한 자세한 정보를 반환하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="6fdf0-314">이 예에서는 Executives라는 아웃바운드 스팸 필터 정책의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="6fdf0-315">구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="6fdf0-316">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="6fdf0-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="6fdf0-317">기존 아웃바운드 스팸 필터 규칙을 표시하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="6fdf0-318">모든 아웃바운드 스팸 필터 규칙의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="6fdf0-319">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="6fdf0-320">특정 아웃바운드 스팸 필터 규칙에 대한 자세한 정보를 반환하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="6fdf0-321">이 예에서는 Contoso Executives라는 아웃바운드 스팸 필터 규칙의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="6fdf0-322">구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="6fdf0-323">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 수정</span><span class="sxs-lookup"><span data-stu-id="6fdf0-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="6fdf0-324">PowerShell에서 맬웨어 필터 정책을 수정할 때와 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 사용하여 아웃바운드 스팸 필터 정책 섹션을 만들 때와 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="6fdf0-325">아웃바운드 스팸 필터 정책의 이름을 바울 수 **없습니다(Set-HostedOutboundSpamFilterPolicy** cmdlet에는 _Name_ 매개 변수가 없음).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-325">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6fdf0-326">보안 및 준수 센터에서 아웃바운드 스팸 정책의 이름을 & 아웃바운드 스팸 필터 규칙의 이름만 _바)_</span><span class="sxs-lookup"><span data-stu-id="6fdf0-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="6fdf0-327">아웃바운드 스팸 필터 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6fdf0-328">구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="6fdf0-329">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="6fdf0-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="6fdf0-330">PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 사용할 수 없는 설정은 _사용되지_ 않는 규칙을 만들 수 있는 Enabled 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6fdf0-331">기존 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="6fdf0-332">그렇지 않으면 PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="6fdf0-333">[2단계: PowerShell을](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 사용하여 이 문서 앞부분의 아웃바운드 스팸 필터 규칙 섹션을 만드는 2단계에서 설명한 대로 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="6fdf0-334">아웃바운드 스팸 필터 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6fdf0-335">구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="6fdf0-336">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙을 활성화 또는 비활성화</span><span class="sxs-lookup"><span data-stu-id="6fdf0-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="6fdf0-337">PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 아웃바운드 스팸 정책(아웃바운드 스팸 필터 규칙 및 할당된 아웃바운드 스팸 필터 정책)이 사용 또는 사용되지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="6fdf0-338">기본 아웃바운드 스팸 정책은 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="6fdf0-339">PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="6fdf0-340">이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="6fdf0-341">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="6fdf0-342">구문과 매개 변수에 대한 자세한 내용은 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 및 [Disable-HostedOutboundSpamFilterRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="6fdf0-343">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="6fdf0-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="6fdf0-344">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="6fdf0-345">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="6fdf0-346">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="6fdf0-347">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="6fdf0-348">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6fdf0-349">PowerShell에서 아웃바운드 스팸 필터 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6fdf0-350">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="6fdf0-351">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="6fdf0-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="6fdf0-352">새 규칙을 만들 때 새 규칙의 우선  순위를 설정하기 위해 **New-HostedOutboundSpamFilterRule** cmdlet에서 Priority 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="6fdf0-353">아웃바운드 기본 스팸 필터 정책에는 해당하는 스팸 필터 규칙이 없습니다. 항상 이 정책의 우선 순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="6fdf0-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="6fdf0-354">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 제거</span><span class="sxs-lookup"><span data-stu-id="6fdf0-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="6fdf0-355">PowerShell을 사용하여 아웃바운드 스팸 필터 정책을 제거하면 해당 아웃바운드 스팸 필터 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="6fdf0-356">PowerShell에서 아웃바운드 스팸 필터 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6fdf0-357">이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6fdf0-358">구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="6fdf0-359">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="6fdf0-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="6fdf0-360">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙을 제거하면 해당 아웃바운드 스팸 필터 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="6fdf0-361">PowerShell에서 아웃바운드 스팸 필터 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="6fdf0-362">이 예에서는 Marketing Department라는 아웃바운드 스팸 필터 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6fdf0-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="6fdf0-363">구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="6fdf0-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="6fdf0-364">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="6fdf0-364">For more information</span></span>

[<span data-ttu-id="6fdf0-365">제한된 사용자 포털에서 차단된 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="6fdf0-365">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="6fdf0-366">아웃바운드 메시지용 높은 위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="6fdf0-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="6fdf0-367">스팸 방지 및 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="6fdf0-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="6fdf0-368">자동 전달 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="6fdf0-368">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
