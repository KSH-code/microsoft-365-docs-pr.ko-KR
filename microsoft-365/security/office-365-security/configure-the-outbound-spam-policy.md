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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 아웃바운드 스팸 정책을 보고, 만들고, 수정하고, 삭제하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845981"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="af8f8-103">EOP에서 아웃바운드 스팸 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="af8f8-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="af8f8-104">Exchange Online 사서함 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 모든 전자 메일 메시지가 자동으로 스팸 및 비정상적 전송 활동임을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="af8f8-105">조직의 사용자가 보내는 아웃바운드 스팸은 일반적으로 어디에 있다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="af8f8-106">의심스러운 아웃바운드 메시지는 스팸 지수 또는 SCL에 관계없이 스팸으로 표시되며 위험도가 높은 배달 [풀을](high-risk-delivery-pool-for-outbound-messages.md) 통해 라우팅되어 서비스의 신뢰도를 보호하기 위해(즉, Microsoft 365 원본 전자 메일 서버를 IP 차단 목록으로부터 보호) 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="af8f8-107">관리자는 경고 정책을 통해 의심스러운 아웃바운드 전자 메일 활동 과정 및 차단된 사용자에게 자동으로 알림을 [받습니다.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="af8f8-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="af8f8-108">EOP는 스팸에 대한 조직의 전반적인 방어의 일부로 아웃바운드 스팸 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="af8f8-109">자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="af8f8-110">관리자는 기본 아웃바운드 스팸 정책을 보고, 편집하고, 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="af8f8-111">세분성을 상세히 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 아웃바운드 스팸 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="af8f8-112">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="af8f8-113">보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 아웃바운드 스팸 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="af8f8-114">EOP에서 아웃바운드 스팸 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="af8f8-115">**아웃바운드 스팸 필터 정책:** 아웃바운드 스팸 필터링 결과와 알림 옵션에 대한 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="af8f8-116">**아웃바운드 스팸 필터 규칙: 아웃바운드**스팸 필터 정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="af8f8-117">준수 센터에서 아웃바운드 스팸 정책을 관리하면, 두 가지 요소의 차이는 & 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="af8f8-118">정책을 만들면 실제로는 아웃바운드 스팸 필터 규칙과 관련된 아웃바운드 스팸 필터 정책이 같은 이름을 사용하여 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="af8f8-119">정책을 수정할 때, 이름, 우선순위, 사용안함 또는 사용 안 함 및 받는 사람 필터와 관련된 설정은 아웃바운드 스팸 필터 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="af8f8-120">다른 모든 설정은 관련 아웃바운드 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="af8f8-121">정책을 제거하면 아웃바운드 스팸 필터 규칙과 연결된 아웃바운드 스팸 필터 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="af8f8-122">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="af8f8-123">자세한 내용은 이 항목 [뒷부분에 나오는 Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 아웃바운드 스팸 정책](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 섹션을 구성하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="af8f8-124">모든 조직에는 다음과 같은 속성을 가진 Default라는 기본 제공 아웃바운드 스팸 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="af8f8-125">정책과 연결된 아웃바운드 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="af8f8-126">정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="af8f8-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="af8f8-127">사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="af8f8-128">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="af8f8-129">아웃바운드 스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용되는 더 강격한 설정을 사용하여 사용자 지정 아웃바운드 스팸 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="af8f8-130">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="af8f8-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="af8f8-131"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="af8f8-132">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="af8f8-133">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="af8f8-134">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="af8f8-135">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="af8f8-136">아웃바운드 스팸 정책을 추가, 수정 및 삭제하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="af8f8-137">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="af8f8-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="af8f8-138">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="af8f8-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="af8f8-139">아웃바운드 스팸 정책에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="af8f8-140">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="af8f8-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="af8f8-141">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="af8f8-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="af8f8-142">아웃바운드 스팸 정책에 대한 권장 설정은 EOP 아웃바운드 [스팸 필터 정책 설정을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="af8f8-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="af8f8-143">Email sending limit **exceeded, 의심스러운**전자 메일 전송 패턴이 감지되고, **사용자가 이미** [alert policies](../../compliance/alert-policies.md) **TenantAdmins(전역** **관리자)** 그룹의 구성원에게 전자 메일 알림을 보내고 아웃바운드 스팸으로 인해 차단됨에 대한 전자 메일 알림을 보냅니다. **Suspicious email sending patterns detected**</span><span class="sxs-lookup"><span data-stu-id="af8f8-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="af8f8-144">자세한 내용은 제한된 [사용자에 대한 경고 설정 확인을 참조하십시오.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="af8f8-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="af8f8-145">아웃바운드 스팸 정책의 알림 옵션 대신 이러한 경고 정책을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="af8f8-146">보안 그룹 & 사용하여 아웃바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="af8f8-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="af8f8-147">보안 센터에서 사용자 지정 아웃바운드 스팸 정책을 & 준수 센터에서 동일한 이름을 사용하여 스팸 필터 규칙과 관련된 스팸 필터 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="af8f8-148">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="af8f8-149">스팸 **방지 설정 페이지에서 아웃바운드** 정책 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="af8f8-150">아웃바운드 스팸 **필터 정책이 나타나면** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="af8f8-151">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="af8f8-152">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="af8f8-153">(옵션) 알림 **섹션을** 확장하여 의심스러운 아웃바운드 전자 메일 메시지의 복사본 및 알림을 받을 추가 사용자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="af8f8-154">**특정 사람에게 의심스러운 아웃바운드**전자 메일 메시지 복사본 보내기 : 이 설정은 지정된 사용자를 의심스러운 아웃바운드 메시지에 숨은 참조 받는 사람으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="af8f8-155">이 설정은 기본 아웃바운드 스팸 정책에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="af8f8-156">이 기능은 사용자가 만드는 사용자 지정 아웃바운드 스팸 정책에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="af8f8-157">이 설정을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="af8f8-157">To enable this setting:</span></span>

     1. <span data-ttu-id="af8f8-158">확인란을 선택하여 설정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="af8f8-159">사용자 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-159">Click **Add people**.</span></span> <span data-ttu-id="af8f8-160">표시되는 받는 사람 **추가 또는 제거** 플라이아웃에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="af8f8-161">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-161">Enter the sender's email address.</span></span> <span data-ttu-id="af8f8-162">전자 메일 주소가 여러 개인 경우 각 주소를 세미콜론(목록)으로 구분하여 ;) 또는 한 줄에 받는 사람 한 명</span><span class="sxs-lookup"><span data-stu-id="af8f8-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="af8f8-163">이</span><span class="sxs-lookup"><span data-stu-id="af8f8-163">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="af8f8-165">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-165">to add the recipients.</span></span>

        <span data-ttu-id="af8f8-166">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="af8f8-167">추가한 받는 사람은 **플라이아웃의** 받는 사람 목록 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="af8f8-168">받는 사람을 삭제하려면 제거 ![ 단추를 ](../../media/scc-remove-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="af8f8-169">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="af8f8-170">이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="af8f8-171">**아웃바운드 스팸 방지로 인해 차단되는 경우 특정 사용자에게 알림:**</span><span class="sxs-lookup"><span data-stu-id="af8f8-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="af8f8-172">이 설정은 아웃바운드 스팸 정책에서 더 이상 사용되지 않기 위한 프로세스에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="af8f8-173">The default [alert policy](../../compliance/alert-policies.md) **restricted from sending email from sending email from sending email** notifications already sending email notifications to members of the **TenantAdmins** (**Global admins)** group when exceeding the **recipient limits** section.</span><span class="sxs-lookup"><span data-stu-id="af8f8-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="af8f8-174">아웃바운드 스팸 정책의 이 설정 대신 다른 사용자에게 알림을 보내려면 알림 **정책을 사용하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="af8f8-175">자세한 내용은 제한된 [사용자에 대한 경고 설정을 확인합니다.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="af8f8-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="af8f8-176">(옵션) 받는 사람 **제한 섹션을** 확장하여 의심스러운 아웃바운드 전자 메일 메시지에 대한 제한 및 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="af8f8-177">이러한 설정은 클라우드 기반 사서함에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="af8f8-178">**사용자당 최대 받는 사람 수**</span><span class="sxs-lookup"><span data-stu-id="af8f8-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="af8f8-179">유효한 값은 0에서 10000까지입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="af8f8-180">기본값은 0이며, 이는 서비스 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="af8f8-181">자세한 내용은 보내기 [제한을 참조하십시오.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="af8f8-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="af8f8-182">**외부 시간 한도:** 시간당 외부 받는 사람의 최대 수.</span><span class="sxs-lookup"><span data-stu-id="af8f8-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="af8f8-183">**내부 시간 한도:** 시간당 내부 받는 사람의 최대 수.</span><span class="sxs-lookup"><span data-stu-id="af8f8-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="af8f8-184">**일별 제한:** 하루 최대 받는 사람 수.</span><span class="sxs-lookup"><span data-stu-id="af8f8-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="af8f8-185">**사용자가 위한 제한을 초과하는 경우의 작업:** 받는 사람 제한 중 하나를 초과하는 **경우 수행할** 작업 구성</span><span class="sxs-lookup"><span data-stu-id="af8f8-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="af8f8-186">모든 작업에 대해, 사용자가 전자 메일 알림 정책을 보내지 못하도록 **제한된** **Notify specific people if a sender is blocked due to sending outbound spam** 사용자 및 현재 중복된 사용자에 게 아웃바운드 스팸 설정에서 메일 알림을 받으려면 해당 받는 사람이 특정 인사를 알리도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="af8f8-187">**사용자가 메일을 보내지 않도록 제한하면 다음 날:** 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="af8f8-188">전자 메일 알림을 보내고 사용자는 UTC 시간에 따라 다음 날까지 더 많은 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="af8f8-189">관리자는 이 블록을 재정의할 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="af8f8-190">전자 메일을 **보내지 않도록 제한된 활동 알림은** 전자 메일을 통해 관리자에게 알림을 보냅니다(전자 메일을 통해, **경고 보기** 페이지에서).</span><span class="sxs-lookup"><span data-stu-id="af8f8-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="af8f8-191">정책에서 아웃바운드 스팸 **설정 설정으로 인해** 보낸 사람이 차단된 경우 알림에 지정된 모든 받는 사람에게도 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="af8f8-192">사용자는 다음 날에 UTC 시간에 따라 더 이상 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="af8f8-193">관리자는 이 블록을 재정의할 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="af8f8-194">**메일 보내기 제한:** 전자 메일 알림을 보내거나 보안 & 규정 준수 센터에서 \*\*[제한된 사용자] 포털에 <https://sip.protection.office.com/restrictedusers> \*\* 사용자가 추가되며, 사용자는 관리자가 제한된 사용자 포털에서 제거될 때까지 전자 **메일을** 보낼 수 없습니다. 관리자가 목록에서 사용자를 제거한 후에는 해당 날짜에 대해 사용자를 다시 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="af8f8-195">자세한 내용은 스팸 [메일을 전송한 후 제한된 사용자 포털에서 사용자 제거를 참조하세요.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="af8f8-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="af8f8-196">**수행하지 않음, 알림만:** 전자 메일 알림만 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="af8f8-197">(옵션) 자동 **전달 섹션을 확장하여** 사용자의 외부 보낸 사람에 대한 자동 전자 메일 전달을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="af8f8-198">자동 전달에 대한 자세한 내용은 전자 메일 전달 [구성을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="af8f8-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="af8f8-199">2020년 9월 이전에는 이러한 설정을 사용할 수 있지만 적용되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="af8f8-200">이러한 설정은 클라우드 기반 사서함에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="af8f8-201">내부 받는 사람에게 자동으로 전달하는 기능은 이 설정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="af8f8-202">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-202">The available values are:</span></span>

   - <span data-ttu-id="af8f8-203">**자동 - 시스템 제어: 아웃바운드**스팸 필터링을 허용하여 자동 외부 전자 메일 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="af8f8-204">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-204">This is the default value.</span></span>

   - <span data-ttu-id="af8f8-205">**설정**: 정책에 의해 자동 외부 전자 메일 전달이 사용하지 않도록 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="af8f8-206">**꺼짐:** 모든 자동 외부 전자 메일 전달이 정책에 의해 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="af8f8-207">(필수) 적용된 **항목섹션을** 확장하여 정책을 적용할 내부 보낸 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="af8f8-208">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="af8f8-209">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<sender1\>_ 혹은 _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="af8f8-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="af8f8-210">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<sender1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="af8f8-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="af8f8-211">사용 가능한 모든 조건을 보려면 **조건 추가**를 세 번 클릭하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="af8f8-212">![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="af8f8-213">**보낸 사람 도메인은**: 조직에서 구성된 허용 도메인 중 하나 이상의 보낸 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="af8f8-214">**태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="af8f8-215">두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="af8f8-216">**보낸 사람:** 조직에서 하나 이상의 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="af8f8-217">**태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="af8f8-218">태그 추가 **상자를 다시 클릭하여** 추가 보낸 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="af8f8-219">**보낸 사람이 보낸 사람이 다음의**구성원임 : 조직에서 그룹을 하나 이상 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="af8f8-220">**태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="af8f8-221">태그 추가 **상자를 다시 클릭하여** 추가 보낸 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="af8f8-222">**다음의 경우 제외**: 규칙에 대한 예외를 추가하려면\*\* 조건 추가\*\*를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="af8f8-223">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="af8f8-224">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="af8f8-225">보안 센터 & 사용하여 아웃바운드 스팸 정책 보기</span><span class="sxs-lookup"><span data-stu-id="af8f8-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="af8f8-226">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="af8f8-227">스팸 방지 **설정 페이지에서 확장 아이콘을** ![ 클릭하여 아웃바운드 스팸 ](../../media/scc-expand-icon.png) 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="af8f8-228">아웃바운드 스팸 필터 **정책이라는 기본**정책</span><span class="sxs-lookup"><span data-stu-id="af8f8-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="af8f8-229">유형 열의 값이 사용자 지정 아웃바운드 스팸 정책인 **경우에 만든** 사용자 **지정 정책.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="af8f8-230">정책 설정이 표시되는 확장된 정책 세부 정보에 표시될 수 있고 정책 편집을 클릭할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="af8f8-231">보안 센터 & 사용하여 아웃바운드 스팸 정책 수정</span><span class="sxs-lookup"><span data-stu-id="af8f8-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="af8f8-232">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="af8f8-233">스팸 방지 **설정 페이지에서 확장 아이콘을** ![ 클릭하여 아웃바운드 스팸 ](../../media/scc-expand-icon.png) 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="af8f8-234">아웃바운드 스팸 필터 **정책이라는 기본**정책</span><span class="sxs-lookup"><span data-stu-id="af8f8-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="af8f8-235">유형 열의 값이 사용자 지정 아웃바운드 스팸 정책인 **경우에 만든** 사용자 **지정 정책.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="af8f8-236">**정책 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-236">Click **Edit policy**.</span></span>

<span data-ttu-id="af8f8-237">사용자 지정 아웃바운드 스팸 정책의 경우, 플라이아웃에서 표시되는 사용 가능한 설정은 보안 & 준수 센터를 사용하여 아웃바운드 스팸 정책 섹션을 만드는 [것과 같습니다.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="af8f8-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="af8f8-238">아웃바운드 스팸 필터 정책이라는 기본 아웃바운드 스팸 **Applied to** **정책의**경우 적용된 섹션을 사용할 수 없고(정책은 모든 사용자에게 적용됨) 정책의 이름을 바일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="af8f8-239">정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="af8f8-240">아웃바운드 스팸 정책 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="af8f8-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="af8f8-241">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="af8f8-242">스팸 방지 **설정 페이지에서 확장 아이콘을** 클릭하여 만든 사용자 지정 ![ ](../../media/scc-expand-icon.png) 정책을 확장합니다(유형 **열의 값은** **사용자 지정 아웃바운드 스팸 정책입니다).**</span><span class="sxs-lookup"><span data-stu-id="af8f8-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="af8f8-243">표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="af8f8-244">토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-244">Move the toggle to the left to disable the policy:</span></span> ![토글 끔](../../media/scc-toggle-off.png)

   <span data-ttu-id="af8f8-246">토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-246">Move the toggle to the right to enable the policy:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="af8f8-248">기본 아웃바운드 스팸 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="af8f8-249">사용자 지정 아웃바운드 스팸 정책의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="af8f8-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="af8f8-250">기본적으로 아웃바운드 스팸 정책에는 만들어진 순서에 따라 우선 순위가 지정됩니다(새 정책은 이전 정책보다 우선순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="af8f8-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="af8f8-251">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="af8f8-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="af8f8-252">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="af8f8-253">사용자 지정 아웃바운드 스팸 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 우선 순위 **값 0이** 포함됨).</span><span class="sxs-lookup"><span data-stu-id="af8f8-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="af8f8-254">아웃바운드 스팸 필터 정책이라는 **기본 아웃바운드 스팸 정책은** 우선 순위 **값이 낮은**것이며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="af8f8-255">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="af8f8-256">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="af8f8-257">스팸 **방지 설정 페이지에서 유형** 열의 값이 사용자 지정 아웃바운드 스팸 **정책인** **정책을 찾습니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="af8f8-258">**우선순위** 열의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="af8f8-259">우선순위가 가장 높은 사용자 지정 아웃바운드 스팸 정책의 값은 아래쪽 ![ 화살표 아이콘 ](../../media/ITPro-EAC-DownArrowIcon.png) **0입니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="af8f8-260">우선순위가 가장 낮은 사용자 지정 아웃바운드 스팸 정책의 값 위쪽 화살표 ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **아이콘** 이하(예: ![ 위쪽 화살표 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png) **3).가 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="af8f8-261">사용자 지정 아웃바운드 스팸 정책이 세 개 이상 있는 경우 가장 높은 우선순위와 가장 낮은 우선순위 사이의 정책은 위쪽 ![ 화살표 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **n** 값(예: 위쪽 화살표 ![ 아이콘 ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)을 가합니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="af8f8-262">이</span><span class="sxs-lookup"><span data-stu-id="af8f8-262">Click</span></span> ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="af8f8-264">또는</span><span class="sxs-lookup"><span data-stu-id="af8f8-264">or</span></span> ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="af8f8-266">을 클릭하여 우선 순위 목록에서 사용자 지정 아웃바운드 스팸 정책을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="af8f8-267">보안 센터 & 사용하여 아웃바운드 스팸 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="af8f8-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="af8f8-268">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="af8f8-269">스팸 **방지 설정 페이지에서 확장 아이콘을** 클릭하여 삭제할 사용자 지정 ![ ](../../media/scc-expand-icon.png) 정책을 확장합니다(유형 **열은** **사용자 지정 아웃바운드 스팸 정책입니다).**</span><span class="sxs-lookup"><span data-stu-id="af8f8-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="af8f8-270">표시되는 확장된 정책 세부 정보에서 **정책 삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="af8f8-271">표시되는 경고 대화 상자에서 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="af8f8-272">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="af8f8-273">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 아웃바운드 스팸 정책 구성</span><span class="sxs-lookup"><span data-stu-id="af8f8-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="af8f8-274">앞에서 설명한 바와 같이 아웃바운드 스팸 정책은 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="af8f8-275">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙 사이의 차이가 명시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="af8f8-276">\*\* \* -HostedOutboundSpamFilterPolicy\*\* cmdlet을 사용하여 아웃바운드 스팸 필터 정책을 관리하고, \*\* \* -HostedOutboundSpamFilterRule\*\* cmdlet을 사용하여 아웃바운드 스팸 필터 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="af8f8-277">PowerShell에서는 먼저 아웃바운드 스팸 필터 정책을 한 후 규칙이 적용되는 정책을 식별하는 아웃바운드 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="af8f8-278">PowerShell에서는 아웃바운드 스팸 필터 정책과 아웃바운드 스팸 필터 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="af8f8-279">PowerShell에서 아웃바운드 스팸 필터 정책을 제거하면 이에 해당하는 아웃바운드 스팸 필터 규칙은 자동으로 제거되지 않습니다. 또한 이에 국한될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="af8f8-280">PowerShell을 사용하여 아웃바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="af8f8-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="af8f8-281">PowerShell에서 아웃바운드 스팸 정책을 만드는 2단계 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="af8f8-282">아웃바운드 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="af8f8-283">규칙이 적용되는 아웃바운드 스팸 필터 정책을 지정하는 아웃바운드 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="af8f8-284">**참고:**</span><span class="sxs-lookup"><span data-stu-id="af8f8-284">**Notes**:</span></span>

- <span data-ttu-id="af8f8-285">새 아웃바운드 스팸 필터 규칙을 만들고 연결되지 않은 기존 아웃바운드 스팸 필터 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="af8f8-286">아웃바운드 스팸 필터 규칙은 둘 이상의 아웃바운드 스팸 필터 정책과 연관될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="af8f8-287">정책을 만들 때까지 보안 그룹 준수 센터에서 사용할 수 없는 PowerShell의 새 아웃바운드 & 필터 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="af8f8-288">새 정책을 만듭니다(New-HostedOutboundSpamFilterRule_Enabled_ `$false` **cmdlet에서 사용함).**</span><span class="sxs-lookup"><span data-stu-id="af8f8-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="af8f8-289">_Priority_ _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet에서 생성하는 동안 정책우선순위(우선 순위)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="af8f8-290">스팸 필터 규칙에 정책을 할당할 때까지 PowerShell에서 만든 새로운 아웃바운드 & 스팸 보안 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="af8f8-291">1단계: PowerShell을 사용하여 아웃바운드 스팸 필터 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="af8f8-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="af8f8-292">아웃바운드 스팸 필터 정책을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="af8f8-293">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 정책을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="af8f8-294">받는 사람 비율 제한은 기본값인 값으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="af8f8-295">자세한 내용은 [Microsoft 365 옵션별 보내기 제한을 참조하십시오.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="af8f8-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="af8f8-296">한도에 도달하면 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="af8f8-297">구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="af8f8-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="af8f8-298">2단계: PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="af8f8-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="af8f8-299">아웃바운드 스팸 필터 규칙을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="af8f8-300">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 새 아웃바운드 스팸 필터 규칙을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="af8f8-301">Contoso Executives라는 아웃바운드 스팸 필터 정책은 규칙과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="af8f8-302">이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="af8f8-303">구문과 매개 변수에 대한 자세한 내용은 [New-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="af8f8-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="af8f8-304">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="af8f8-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="af8f8-305">모든 아웃바운드 스팸 필터 정책의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="af8f8-306">특정 아웃바운드 스팸 필터 정책에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="af8f8-307">다음은 Executives라는 아웃바운드 스팸 필터 정책의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="af8f8-308">구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="af8f8-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="af8f8-309">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="af8f8-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="af8f8-310">기존 아웃바운드 스팸 필터 규칙을 확인하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="af8f8-311">모든 아웃바운드 스팸 필터 규칙의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="af8f8-312">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="af8f8-313">특정 아웃바운드 스팸 필터 규칙에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="af8f8-314">다음은 Contoso Executives라는 아웃바운드 스팸 필터 규칙의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="af8f8-315">구문과 매개 변수에 대한 자세한 내용은 [Get-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="af8f8-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="af8f8-316">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 수정하기</span><span class="sxs-lookup"><span data-stu-id="af8f8-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="af8f8-317">PowerShell에서 맬웨어 필터 정책을 수정할 때 이 항목의 [앞부분에 나오는 1단계: PowerShell을](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 사용하여 아웃바운드 스팸 필터 정책 섹션을 만들 때와 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="af8f8-318">아웃바운드 스팸 필터 정책의 이름을 바일 **수없습니다(Set-HostedOutboundSpamFilterPolicy cmdlet에는** Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="af8f8-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="af8f8-319">보안 그룹 준수 센터에서 아웃바운드 스팸 & 이름을 바운드하면 아웃바운드 스팸 필터 규칙의 이름만 _변경됩니다._</span><span class="sxs-lookup"><span data-stu-id="af8f8-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="af8f8-320">아웃바운드 스팸 필터 정책을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="af8f8-321">자세한 구문 및 매개 변수 정보는 [Set-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="af8f8-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="af8f8-322">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 수정하기</span><span class="sxs-lookup"><span data-stu-id="af8f8-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="af8f8-323">PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 사용할 수 없는 설정은 사용 안 함 _규칙을 만들_ 수 있는 사용 안 함 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="af8f8-324">기존 아웃바운드 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="af8f8-325">그렇지 않으면 PowerShell에서 아웃바운드 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="af8f8-326">[2단계: PowerShell을](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 사용하여 이 항목의 앞부분에 있는 아웃바운드 스팸 필터 규칙 섹션에 설명된 것과 같이 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="af8f8-327">아웃바운드 스팸 필터 규칙을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="af8f8-328">구문과 매개 변수에 대한 자세한 내용은 [Set-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="af8f8-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="af8f8-329">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="af8f8-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="af8f8-330">PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하면 전체 아웃바운드 스팸 정책(아웃바운드 스팸 필터 규칙과 할당된 아웃바운드 스팸 필터 정책)을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="af8f8-331">기본 아웃바운드 스팸 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됨).</span><span class="sxs-lookup"><span data-stu-id="af8f8-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="af8f8-332">PowerShell에서 아웃바운드 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="af8f8-333">다음은 Marketing Department라는 아웃바운드 스팸 필터 규칙을 사용하지 않도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="af8f8-334">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="af8f8-335">자세한 구문 및 매개 변수 정보는 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 및 [Disable-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="af8f8-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="af8f8-336">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙의 우선 순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="af8f8-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="af8f8-337">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="af8f8-338">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="af8f8-339">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="af8f8-340">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="af8f8-341">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="af8f8-342">PowerShell에서 아웃바운드 스팸 필터 규칙의 우선순위를 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="af8f8-343">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-343">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="af8f8-344">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="af8f8-344">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="af8f8-345">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-HostedOutboundSpamFilterRule** cmdlet의 _우선_ 순위 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="af8f8-346">아웃바운드 기본 스팸 필터 정책에는 상용되는 스팸 필터 규칙이 없고 항상 수정할 수 없는 우선순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="af8f8-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="af8f8-347">PowerShell을 사용하여 아웃바운드 스팸 필터 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="af8f8-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="af8f8-348">PowerShell을 사용하여 아웃바운드 스팸 필터 정책을 제거할 때 이용하는 아웃바운드 스팸 필터 규칙은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="af8f8-349">PowerShell에서 아웃바운드 스팸 필터 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="af8f8-350">다음은 Marketing Department라는 아웃바운드 스팸 필터 정책을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="af8f8-351">구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="af8f8-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="af8f8-352">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙 제거하기</span><span class="sxs-lookup"><span data-stu-id="af8f8-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="af8f8-353">PowerShell을 사용하여 아웃바운드 스팸 필터 규칙을 제거할 때 이에 해당하는 아웃바운드 스팸 필터 정책은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="af8f8-354">PowerShell에서 아웃바운드 스팸 필터 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="af8f8-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="af8f8-355">다음은 Marketing Department라는 아웃바운드 스팸 필터 규칙을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="af8f8-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="af8f8-356">구문과 매개 변수에 대한 자세한 내용은 [Remove-HostedOutboundSpamFilterRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)</span><span class="sxs-lookup"><span data-stu-id="af8f8-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="af8f8-357">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="af8f8-357">For more information</span></span>

[<span data-ttu-id="af8f8-358">제한된 사용자 포털에서 차단된 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="af8f8-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="af8f8-359">아웃바운드 메시지용 높은 위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="af8f8-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="af8f8-360">스팸 방지 및 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="af8f8-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="af8f8-361">자동 전달 메시지 보고서</span><span class="sxs-lookup"><span data-stu-id="af8f8-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
