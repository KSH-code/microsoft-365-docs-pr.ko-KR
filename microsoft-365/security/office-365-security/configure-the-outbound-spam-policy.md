---
title: 아웃바운드 스팸 필터링 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 아웃바운드 전자 메일 보내기 서비스를 사용하는 경우 아웃바운드 스팸 필터링이 항상 사용하도록 설정되므로 서비스와 받는 사람을 사용하여 조직을 보호할 수 있습니다.
ms.openlocfilehash: 699de94a300ac8625e92d2c467edd461d72c7d2f
ms.sourcegitcommit: a955324e33097bbd2fc4ad7f2b8d1f3d87bc8580
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43608177"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="9dc51-103">Office 365에서 아웃 바운드 스팸 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="9dc51-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="9dc51-104">Exchange online 사서함이 없는 Office 365 고객 또는 독립 실행형 EOP (Exchange Online Protection) 고객의 경우 EOP를 통해 전송 되는 아웃 바운드 전자 메일 메시지는 스팸 및 비정상적인 보내기 활동을 자동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="9dc51-105">조직에 있는 사용자의 아웃 바운드 스팸은 일반적으로 계정이 노출 된 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="9dc51-106">의심 스러운 아웃 바운드 메시지는 스팸 지 수 또는 SCL에 관계 없이 스팸으로 표시 되며, [높은 위험 배달 풀](high-risk-delivery-pool-for-outbound-messages.md) 을 통해 라우팅되는 서비스의 신뢰도를 보호 하는 데 도움이 됩니다 (즉, Office 365 원본 전자 메일 서버를 IP 차단 목록 밖으로 유지).</span><span class="sxs-lookup"><span data-stu-id="9dc51-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="9dc51-107">관리자는 [경고 정책을](../../compliance/alert-policies.md)통해 의심 스러운 아웃 바운드 전자 메일 활동 및 차단 된 사용자에 게 자동으로 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="9dc51-108">EOP에서는 스팸을 방지 하기 위해 조직의 전반적인 방어 과정에서 아웃 바운드 스팸 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="9dc51-109">자세한 내용은 [Office 365의 스팸 방지 보호](anti-spam-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="9dc51-110">관리자는 기본 아웃 바운드 스팸 정책을 보고 편집 하 고 구성할 수 있습니다 (삭제 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9dc51-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="9dc51-111">세분성을 높이기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용 되는 사용자 지정 아웃 바운드 스팸 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="9dc51-112">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="9dc51-113">Office 365 보안 & 준수 센터 또는 PowerShell (Office 365 고객을 위한 Exchange Online PowerShell)에서 아웃 바운드 스팸 정책을 구성할 수 있습니다. 독립 실행형 EOP 고객을 위한 Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dc51-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="9dc51-114">Office 365 보안 & 준수 센터 vs Exchange Online PowerShell 또는 Exchange Online Protection PowerShell의 아웃 바운드 스팸 정책</span><span class="sxs-lookup"><span data-stu-id="9dc51-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="9dc51-115">EOP의 아웃 바운드 스팸 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="9dc51-116">**아웃 바운드 스팸 필터 정책**: 아웃 바운드 스팸 필터링 verdicts 및 알림 옵션에 대 한 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="9dc51-117">**아웃 바운드 스팸 필터 규칙**: 아웃 바운드 스팸 필터 정책에 대해 정책이 적용 되는 우선 순위 및 받는 사람 필터를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="9dc51-118">보안 & 준수 센터에서 아웃 바운드 스팸 정책을 관리할 때는 이러한 두 가지 요소 간의 차이가 명확 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-118">The difference between these two elements isn't obvious when you manage outbound spam policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9dc51-119">보안 & 준수 센터에서 아웃 바운드 스팸 정책을 만드는 경우 실제로는 둘 다에 대해 동일한 이름을 사용 하 여 아웃 바운드 스팸 필터 규칙과 연결 된 아웃 바운드 스팸 필터 정책을 동시에 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="9dc51-120">보안 & 준수 센터에서 아웃 바운드 스팸 정책을 수정 하는 경우 이름, 우선 순위, 사용/사용 안 함 및 받는 사람 필터와 관련 된 설정이 아웃 바운드 스팸 필터 규칙을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="9dc51-121">다른 모든 설정은 연결 된 아웃 바운드 스팸 필터 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="9dc51-122">보안 & 준수 센터에서 아웃 바운드 스팸 정책을 제거 하면 아웃 바운드 스팸 필터 규칙과 연결 된 아웃 바운드 스팸 필터 정책이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="9dc51-123">Exchange Online PowerShell 또는 독립 실행형 Exchange Online Protection PowerShell에서 아웃 바운드 스팸 필터 정책 및 아웃 바운드 스팸 필터 규칙 간의 차이가 명백 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="9dc51-124">-Get-hostedcontentfilterpolicy cmdlet을 사용 하 여 아웃 바운드 스팸 필터 정책을 관리 하 고 \*\* \*-disable-hostedcontentfilterrule\*\* cmdlet을 사용 하 여 아웃 바운드 스팸 필터 규칙을 관리 합니다. \*\* \*\*\*</span><span class="sxs-lookup"><span data-stu-id="9dc51-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="9dc51-125">PowerShell에서 먼저 아웃 바운드 스팸 필터 정책을 만든 다음 규칙이 적용 되는 정책을 식별 하는 아웃 바운드 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="9dc51-126">PowerShell에서는 아웃 바운드 스팸 필터 정책 및 아웃 바운드 스팸 필터 규칙의 설정을 개별적으로 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="9dc51-127">PowerShell에서 아웃 바운드 스팸 필터 정책을 제거 하면 해당 하는 아웃 바운드 스팸 필터 규칙이 자동으로 제거 되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="9dc51-128">기본 아웃 바운드 스팸 정책</span><span class="sxs-lookup"><span data-stu-id="9dc51-128">Default outbound spam policy</span></span>

<span data-ttu-id="9dc51-129">모든 조직에는 다음과 같은 속성을 갖는 기본 제공 아웃 바운드 스팸 정책 (기본값)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="9dc51-130">정책과 연결 된 아웃 바운드 스팸 필터 규칙 (받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에 게 Default 라는 아웃 바운드 스팸 필터 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="9dc51-131">Default 정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="9dc51-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="9dc51-132">사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="9dc51-133">Default 정책은 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="9dc51-134">아웃 바운드 스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용 되는 보다 엄격한 설정을 사용 하 여 사용자 지정 아웃 바운드 스팸 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9dc51-135">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="9dc51-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9dc51-136"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9dc51-137">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="9dc51-138">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9dc51-139">Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9dc51-140">이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="9dc51-141">아웃 바운드 스팸 정책을 추가, 수정 및 삭제 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="9dc51-142">아웃 바운드 스팸 정책에 대 한 읽기 전용 액세스를 위해서는 **보안 독자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="9dc51-143">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [Office 365 보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="9dc51-144">아웃 바운드 스팸 정책에 대 한 권장 설정에 대 한 자세한 내용은 [EOP outbound 스팸 필터 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="9dc51-145">**전자 메일 전송 제한 초과**, **의심 스러운 전자 메일 전송 패턴 감지**및 아웃 바운드 스팸으로 인해 차단 된 사용자에 대 한 전자 메일 알림 (**글로벌 관리자**) 그룹의 구성원에 게 전자 메일을 보낼 **수 없도록 하** **는 기본** [알림 정책이](../../compliance/alert-policies.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="9dc51-146">자세한 내용은 [제한 된 사용자에 대 한 알림 설정 확인](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="9dc51-147">아웃 바운드 스팸 정책에서 알림 옵션 대신 이러한 경고 정책을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="9dc51-148">보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9dc51-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="9dc51-149">보안 & 준수 센터에서 사용자 지정 아웃 바운드 스팸 정책을 만들면 두 가지 모두에 대해 동일한 이름을 사용 하 여 스팸 필터 규칙과 연결 된 스팸 필터 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="9dc51-150">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="9dc51-151">**스팸 방지 설정** 페이지에서 **아웃 바운드 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="9dc51-152">**아웃 바운드 스팸 필터 정책** 날아가기가 열리면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="9dc51-153">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="9dc51-154">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="9dc51-155">반드시 **알림** 섹션을 확장 하 여 의심 스러운 아웃 바운드 전자 메일 메시지에 대 한 복사본 및 알림을 수신 해야 하는 추가 사용자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="9dc51-156">**의심 스러운 아웃 바운드 전자 메일 메시지의 복사본을 특정 사용자에 게 보내기**:이 설정은 지정한 사용자를 숨은 참조로 받는 사람에 게 의심 되는 아웃 바운드 메시지에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="9dc51-157">이 설정을 사용 하도록 설정 하려면:</span><span class="sxs-lookup"><span data-stu-id="9dc51-157">To enable this setting:</span></span>

     <span data-ttu-id="9dc51-158">a.</span><span class="sxs-lookup"><span data-stu-id="9dc51-158">a.</span></span> <span data-ttu-id="9dc51-159">확인란을 선택 하 여 설정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="9dc51-160">b.</span><span class="sxs-lookup"><span data-stu-id="9dc51-160">b.</span></span> <span data-ttu-id="9dc51-161">**사용자 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-161">Click **Add people**.</span></span> <span data-ttu-id="9dc51-162">표시 되는 **받는 사람 추가 또는 제거** 플라이 아웃에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="9dc51-163">c.</span><span class="sxs-lookup"><span data-stu-id="9dc51-163">c.</span></span> <span data-ttu-id="9dc51-164">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-164">Enter the sender's email address.</span></span> <span data-ttu-id="9dc51-165">세미콜론으로 구분 하 여 여러 전자 메일 주소를 지정할 수 있습니다 (;) 한 줄에 한 명 또는 여러 명의 받는 사람이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="9dc51-166">d.</span><span class="sxs-lookup"><span data-stu-id="9dc51-166">d.</span></span> <span data-ttu-id="9dc51-167">이</span><span class="sxs-lookup"><span data-stu-id="9dc51-167">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="9dc51-169">받는 사람을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-169">to add the recipients.</span></span>

        <span data-ttu-id="9dc51-170">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="9dc51-171">추가한 받는 사람이 플라이 아웃의 **받는 사람 목록** 섹션에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="9dc51-172">받는 사람을 삭제 하려면 제거 ![단추](../../media/scc-remove-icon.png)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="9dc51-173">e.</span><span class="sxs-lookup"><span data-stu-id="9dc51-173">e.</span></span> <span data-ttu-id="9dc51-174">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="9dc51-175">이 설정을 사용 하지 않도록 설정 하려면 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="9dc51-176">**아웃 바운드 스팸 전송로 인해 보낸 사람이 차단 된 경우 특정 사용자에 게 알림**:</span><span class="sxs-lookup"><span data-stu-id="9dc51-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="9dc51-177">**받는 사람 제한** 섹션의 제한을 초과 하 여 사용자가 **차단 된 경우** **전자 메일을 보내는** 것이 제한**Global admins**된 사용자에 게 이미 전자 메일 알림이 전송 됩니다. 라는 기본 [경고 정책](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9dc51-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="9dc51-178">아웃 바운드 스팸 정책에서이 설정이 관리자 및 기타 사용자에 게 알리도록 설정 하는 것이 아니라 경고 정책을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="9dc51-179">자세한 내용은 [제한 된 사용자에 대 한 알림 설정 확인](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="9dc51-180">이 설정을 사용 하도록 설정 하려면:</span><span class="sxs-lookup"><span data-stu-id="9dc51-180">To enable this setting:</span></span>

     <span data-ttu-id="9dc51-181">a.</span><span class="sxs-lookup"><span data-stu-id="9dc51-181">a.</span></span> <span data-ttu-id="9dc51-182">확인란을 선택 하 여 설정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="9dc51-183">b.</span><span class="sxs-lookup"><span data-stu-id="9dc51-183">b.</span></span> <span data-ttu-id="9dc51-184">**사용자 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-184">Click **Add people**.</span></span> <span data-ttu-id="9dc51-185">표시 되는 **받는 사람 추가 또는 제거** 플라이 아웃에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="9dc51-186">c.</span><span class="sxs-lookup"><span data-stu-id="9dc51-186">c.</span></span> <span data-ttu-id="9dc51-187">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-187">Enter the sender's email address.</span></span> <span data-ttu-id="9dc51-188">세미콜론으로 구분 하 여 여러 전자 메일 주소를 지정할 수 있습니다 (;) 한 줄에 한 명 또는 여러 명의 받는 사람이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="9dc51-189">d.</span><span class="sxs-lookup"><span data-stu-id="9dc51-189">d.</span></span> <span data-ttu-id="9dc51-190">이</span><span class="sxs-lookup"><span data-stu-id="9dc51-190">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="9dc51-192">받는 사람을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-192">to add the recipients.</span></span>

        <span data-ttu-id="9dc51-193">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="9dc51-194">추가한 받는 사람이 플라이 아웃의 **받는 사람 목록** 섹션에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="9dc51-195">받는 사람을 삭제 하려면 제거 ![단추](../../media/scc-remove-icon.png)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="9dc51-196">e.</span><span class="sxs-lookup"><span data-stu-id="9dc51-196">e.</span></span> <span data-ttu-id="9dc51-197">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="9dc51-198">이 설정을 사용 하지 않도록 설정 하려면 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="9dc51-199">반드시 **받는 사람 제한** 섹션을 확장 하 여 의심 스러운 아웃 바운드 전자 메일 메시지에 대 한 제한 및 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="9dc51-200">이러한 설정은 클라우드 기반 사서함에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-200">These settings are only applicable to cloud-based mailboxes.</span></span>
     
   - <span data-ttu-id="9dc51-201">**사용자 당 최대 받는 사람 수**</span><span class="sxs-lookup"><span data-stu-id="9dc51-201">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="9dc51-202">유효한 값은 0 ~ 1만입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-202">A valid value is 0 to 10000.</span></span> <span data-ttu-id="9dc51-203">기본값은 0 이며이 값은 서비스 기본값을 사용 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-203">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="9dc51-204">자세한 내용은 [Office 365 옵션을 통한 제한 보내기](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-204">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="9dc51-205">**외부 시간 제한**: 시간당 최대 외부 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-205">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="9dc51-206">**내부 시간 제한**: 시간당 내부 받는 사람의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-206">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="9dc51-207">**일별 제한**: 일별 최대 받는 사람 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-207">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="9dc51-208">**사용자가 위의 제한을 초과**하는 경우: **받는 사람 한도** 를 초과 하는 경우 수행할 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-208">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="9dc51-209">모든 작업의 경우 사용자에 게 **전자 메일 알림 정책 전송 제한** , 즉 아웃 바운드 스팸 정책 수신 전자 메일 알림을 보내는 **아웃 바운드 스팸 설정으로 인해 보낸 사람이 차단 되는 경우** 에는 중복 알림에 특정 사용자에 게 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-209">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="9dc51-210">**다음 날까지 사용자가 메일을 보낼 수 없도록 제한**합니다:이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-210">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="9dc51-211">전자 메일 알림이 전송 되 고 사용자가 UTC 시간을 기준으로 다음 날까지 메시지를 더 이상 보낼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-211">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="9dc51-212">관리자가이 블록을 무시할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-212">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="9dc51-213">**사용자가 전자 메일을 보낼 수 없도록 제한** 된 작업 경고는 전자 메일을 통해 관리자에 게 알림 페이지를 **표시** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-213">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="9dc51-214">정책에서 **아웃 바운드 스팸 설정을 전송 하 여 보낸 사람이 차단 되는 경우 특정 사용자에 게 알림** 메시지가 지정 된 모든 받는 사람은 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-214">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="9dc51-215">사용자는 UTC 시간을 기준으로 다음 날까지 메시지를 더 이상 보낼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-215">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="9dc51-216">관리자가이 블록을 무시할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-216">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="9dc51-217">**사용자가 메일을 보낼 수 없도록 제한**: 전자 메일 알림이 전송 되 고 사용자가 보안 & 준수 센터의 \*\*[제한 된 사용자]<https://sip.protection.office.com/restrictedusers> \*\* 포털에 추가 되 고 관리자가 제한 된 **사용자** 포털에서 제거 될 때까지 사용자가 전자 메일을 보낼 수 없습니다. 관리자가 목록에서 사용자를 제거 하면 해당 날짜에 대해 사용자가 다시 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-217">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="9dc51-218">자세한 내용은 [스팸 메일을 보낸 후 제한 된 사용자 포털에서 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-218">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="9dc51-219">**작업 없음, 알림만**: 전자 메일 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-219">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="9dc51-220">않아도 **적용 대상** 섹션을 확장 하 여 정책이 적용 되는 내부 보낸 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-220">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="9dc51-221">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-221">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9dc51-222">동일한 조건 또는 예외를 사용 하는 여러 값 또는 논리 (예: _ \<sender1\> _ 또는 _ \<sender2\>_)</span><span class="sxs-lookup"><span data-stu-id="9dc51-222">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="9dc51-223">서로 다른 조건 또는 예외 사용 및 논리 (예: _ \<sender1\> _ , _ \<그룹 1\>의 구성원_)</span><span class="sxs-lookup"><span data-stu-id="9dc51-223">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="9dc51-224">사용 가능한 모든 조건을 보려면 **조건 추가**를 세 번 클릭하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-224">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="9dc51-225">![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-225">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="9dc51-226">**보낸 사람 도메인**: Office 365에서 구성 된 허용 도메인 중 하나 이상에 있는 보낸 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-226">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="9dc51-227">**태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-227">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="9dc51-228">두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-228">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="9dc51-229">**Sender is**: 조직에서 사용자를 한 명 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-229">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="9dc51-230">**태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-230">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="9dc51-231">**태그 추가** 상자를 다시 클릭 하 여 추가 보낸 사람을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-231">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="9dc51-232">**보낸 사람이 다음 구성원 인 경우**: 조직의 그룹을 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-232">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="9dc51-233">**태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-233">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="9dc51-234">**태그 추가** 상자를 다시 클릭 하 여 추가 보낸 사람을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-234">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="9dc51-235">**다음의 경우 제외**: 규칙에 대한 예외를 추가하려면\*\* 조건 추가\*\*를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-235">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="9dc51-236">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-236">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="9dc51-237">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-237">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="9dc51-238">보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 보기</span><span class="sxs-lookup"><span data-stu-id="9dc51-238">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="9dc51-239">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="9dc51-240">**스팸 방지 설정** 페이지에서 확장 아이콘 ![](../../media/scc-expand-icon.png) 을 클릭 하 여 아웃 바운드 스팸 정책을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="9dc51-241">**아웃 바운드 스팸 필터 정책**이라는 기본 정책</span><span class="sxs-lookup"><span data-stu-id="9dc51-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="9dc51-242">**Type** 열의 값이 **사용자 지정 아웃 바운드 스팸 정책**인 경우 만든 사용자 지정 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="9dc51-243">표시 되는 확장 된 정책 세부 정보에 정책 설정이 표시 되거나, **정책 편집**을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-243">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="9dc51-244">보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 수정</span><span class="sxs-lookup"><span data-stu-id="9dc51-244">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="9dc51-245">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-245">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="9dc51-246">**스팸 방지 설정** 페이지에서 확장 아이콘 ![](../../media/scc-expand-icon.png) 을 클릭 하 여 아웃 바운드 스팸 정책을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-246">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="9dc51-247">**아웃 바운드 스팸 필터 정책**이라는 기본 정책</span><span class="sxs-lookup"><span data-stu-id="9dc51-247">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="9dc51-248">**Type** 열의 값이 **사용자 지정 아웃 바운드 스팸 정책**인 경우 만든 사용자 지정 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-248">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="9dc51-249">**정책 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-249">Click **Edit policy**.</span></span>

<span data-ttu-id="9dc51-250">사용자 지정 아웃 바운드 스팸 정책에서 표시 되는 플라이 아웃의 사용 가능 설정은 [보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 만들기](#use-the-security--compliance-center-to-create-outbound-spam-policies) 섹션에 설명 된 설정과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-250">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="9dc51-251">**아웃 바운드 스팸 필터 정책**이라는 기본 아웃 바운드 스팸 정책의 경우 **적용 대상** 섹션을 사용할 수 없으며 정책이 모든 사용자에 게 적용 되며 정책의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-251">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="9dc51-252">정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-252">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="9dc51-253">아웃 바운드 스팸 정책 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="9dc51-253">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="9dc51-254">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="9dc51-255">**스팸 방지 설정** 페이지에서 확장 아이콘](../../media/scc-expand-icon.png) 을 클릭 ![하 여 만든 사용자 지정 정책 ( **유형** 열의 값은 **사용자 지정 아웃 바운드 스팸 정책**)을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="9dc51-256">표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-256">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="9dc51-257">토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-257">Move the toggle to the left to disable the policy:</span></span> ![토글 끔](../../media/scc-toggle-off.png)

   <span data-ttu-id="9dc51-259">토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-259">Move the toggle to the right to enable the policy:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="9dc51-261">기본 아웃 바운드 스팸 정책을 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-261">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="9dc51-262">사용자 지정 아웃 바운드 스팸 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="9dc51-262">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="9dc51-263">기본적으로 아웃 바운드 스팸 정책에는 만든 순서를 기준으로 하는 우선 순위가 지정 됩니다 (최신 정책은 이전 정책 보다 낮은 우선 순위입니다).</span><span class="sxs-lookup"><span data-stu-id="9dc51-263">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="9dc51-264">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="9dc51-264">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9dc51-265">두 정책의 우선순위가 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-265">No two policies can have the same priority.</span></span>

<span data-ttu-id="9dc51-266">사용자 지정 아웃 바운드 스팸 정책은 처리 되는 순서 대로 표시 됩니다 (첫 번째 정책의 **우선 순위** 값은 0).</span><span class="sxs-lookup"><span data-stu-id="9dc51-266">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="9dc51-267">**아웃 바운드 스팸 필터 정책** 이라는 기본 아웃 바운드 스팸 정책에서는 우선 순위 값이 **가장 낮은**것 이며,이를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-267">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="9dc51-268">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-268">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="9dc51-269">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-269">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="9dc51-270">**스팸 방지 설정** 페이지에서 **유형** 열의 값이 **사용자 지정 아웃 바운드 스팸 정책**인 정책을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-270">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="9dc51-271">**우선순위** 열의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-271">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="9dc51-272">우선 순위가 가장 높은 사용자 지정 아웃 바운드 스팸 정책의 값 ![은 아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **0**입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-272">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="9dc51-273">우선 순위가 가장 낮은 사용자 ![지정 아웃 바운드 스팸 정책의 값 위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **n** (예: ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **3**)이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-273">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="9dc51-274">사용자 지정 된 아웃 바운드 스팸 정책이 3 개 이상인 경우 위쪽/최저 우선 순위 간의 정책에는 위쪽 ![](../../media/ITPro-EAC-UpArrowIcon.png)![화살표 아이콘 아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **n** (예를 들어, ![위 화살표가 아이콘](../../media/ITPro-EAC-UpArrowIcon.png)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **2**)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-274">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="9dc51-275">이</span><span class="sxs-lookup"><span data-stu-id="9dc51-275">Click</span></span> ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="9dc51-277">또는</span><span class="sxs-lookup"><span data-stu-id="9dc51-277">or</span></span> ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="9dc51-279">사용자 지정 아웃 바운드 스팸 정책을 우선 순위 목록에서 위아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-279">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="9dc51-280">보안 & 준수 센터를 사용 하 여 아웃 바운드 스팸 정책 제거</span><span class="sxs-lookup"><span data-stu-id="9dc51-280">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="9dc51-281">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-281">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="9dc51-282">**스팸 방지 설정** 페이지에서 확장 아이콘](../../media/scc-expand-icon.png) 을 클릭 ![하 여 삭제할 사용자 지정 정책 ( **유형** 열은 **사용자 지정 아웃 바운드 스팸 정책**)을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-282">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="9dc51-283">표시되는 확장된 정책 세부 정보에서 **정책 삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-283">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="9dc51-284">표시되는 경고 대화 상자에서 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-284">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="9dc51-285">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-285">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="9dc51-286">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell을 사용 하 여 아웃 바운드 스팸 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9dc51-286">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="9dc51-287">PowerShell을 사용 하 여 아웃 바운드 스팸 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9dc51-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="9dc51-288">PowerShell에서 아웃 바운드 스팸 정책을 만드는 과정은 다음 두 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9dc51-289">아웃 바운드 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-289">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="9dc51-290">규칙이 적용 되는 아웃 바운드 스팸 필터 정책을 지정 하는 아웃 바운드 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="9dc51-291">**참고:**</span><span class="sxs-lookup"><span data-stu-id="9dc51-291">**Notes**:</span></span>

- <span data-ttu-id="9dc51-292">새 아웃 바운드 스팸 필터 규칙을 만들고 연결 되지 않은 기존 아웃 바운드 스팸 필터 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="9dc51-293">아웃 바운드 스팸 필터 규칙을 두 개 이상의 아웃 바운드 스팸 필터 정책에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="9dc51-294">정책을 만든 후에 야 보안 & 준수 센터에서 사용할 수 없는 PowerShell에서 새 아웃 바운드 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="9dc51-295">**HostedOutboundSpamFilterRule** cmdlet에서_사용 하도록 설정_ `$false` 된 새 정책을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="9dc51-296">**HostedOutboundSpamFilterRule** cmdlet에 대해 만드는 동안 정책의 우선 순위 (_우선 순위_ _ \<번호\>_)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="9dc51-297">사용자가 PowerShell에서 만든 새 아웃 바운드 스팸 필터 정책이 보안 & 준수 센터에 표시 되지 않는 경우에는 해당 정책을 스팸 필터 규칙에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="9dc51-298">1 단계: PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9dc51-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="9dc51-299">아웃 바운드 스팸 필터 정책을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="9dc51-300">이 예에서는 다음 설정을 사용 하 여 Contoso 임원 이라는 새 아웃 바운드 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="9dc51-301">받는 사람 비율 제한은 기본값 보다 작은 값으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="9dc51-302">자세한 내용은 [Office 365 옵션을 통한 제한 보내기](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc51-302">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="9dc51-303">한도에 도달한 후에는 사용자가 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="9dc51-304">구문과 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="9dc51-305">2 단계: PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="9dc51-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="9dc51-306">아웃 바운드 스팸 필터 규칙을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="9dc51-307">이 예에서는 다음 설정을 사용 하 여 Contoso 임원 이라는 새 아웃 바운드 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="9dc51-308">Contoso 임원 이라는 아웃 바운드 스팸 필터 정책이 규칙과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="9dc51-309">이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="9dc51-310">구문과 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="9dc51-311">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="9dc51-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="9dc51-312">모든 아웃 바운드 스팸 필터 정책의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="9dc51-313">특정 아웃 바운드 스팸 필터 정책에 대 한 자세한 정보를 반환 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="9dc51-314">이 예에서는 임원 라는 아웃 바운드 스팸 필터 정책에 대 한 모든 속성 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="9dc51-315">구문과 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="9dc51-316">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="9dc51-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="9dc51-317">기존 아웃 바운드 스팸 필터 규칙을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="9dc51-318">모든 아웃 바운드 스팸 필터 규칙의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="9dc51-319">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="9dc51-320">특정 아웃 바운드 스팸 필터 규칙에 대 한 자세한 정보를 반환 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="9dc51-321">이 예에서는 Contoso 임원 이라는 아웃 바운드 스팸 필터 규칙에 대 한 모든 속성 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9dc51-322">구문과 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="9dc51-323">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 수정</span><span class="sxs-lookup"><span data-stu-id="9dc51-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="9dc51-324">이 항목 앞부분의 [1 단계: powershell을 사용 하 여 아웃 바운드 스팸 필터 정책 만들기](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 섹션에 설명 된 대로, powershell에서 맬웨어 필터 정책을 수정 하는 경우에도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="9dc51-325">**참고**: 아웃 바운드 스팸 필터 정책의 이름을 바꿀 수는 없습니다 (get-hostedoutboundspamfilterpolicy Cmdlet은 _Name_ 매개 변수를 **사용** 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9dc51-325">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9dc51-326">보안 & 준수 센터에서 아웃 바운드 스팸 정책의 이름을 바꿀 때 아웃 바운드 스팸 필터 _규칙만_이름을 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="9dc51-327">아웃 바운드 스팸 필터 정책을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9dc51-328">구문 및 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="9dc51-329">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="9dc51-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="9dc51-330">PowerShell에서 아웃 바운드 스팸 필터 규칙을 수정할 때 사용할 수 없는 설정은 사용 하지 않도록 설정 된 규칙을 만들 수 있는 _사용_ 가능한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9dc51-331">기존 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="9dc51-332">그렇지 않으면 PowerShell에서 아웃 바운드 스팸 필터 규칙을 수정할 때 사용할 수 있는 추가 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="9dc51-333">이 항목 앞부분의 [2 단계: PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 만들기](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 섹션에 설명 된 대로 규칙을 만들 때도 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="9dc51-334">아웃 바운드 스팸 필터 규칙을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9dc51-335">구문 및 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="9dc51-336">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9dc51-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="9dc51-337">PowerShell에서 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정 하면 전체 아웃 바운드 스팸 정책 (아웃 바운드 스팸 필터 규칙 및 할당 된 아웃 바운드 스팸 필터 정책)을 사용 하거나 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="9dc51-338">기본 아웃 바운드 스팸 정책을 사용 하거나 사용 하지 않도록 설정할 수 없습니다 (항상 항상 모든 받는 사람에 게 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="9dc51-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="9dc51-339">PowerShell에서 아웃 바운드 스팸 필터 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="9dc51-340">이 예에서는 Marketing 부서 라는 아웃 바운드 스팸 필터 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="9dc51-341">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="9dc51-342">구문 및 매개 변수에 대 한 자세한 내용은 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) 및 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="9dc51-343">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="9dc51-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="9dc51-344">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9dc51-345">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9dc51-346">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9dc51-347">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9dc51-348">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9dc51-349">PowerShell에서 아웃 바운드 스팸 필터 규칙의 우선 순위를 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9dc51-350">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="9dc51-351">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="9dc51-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9dc51-352">**참고:**</span><span class="sxs-lookup"><span data-stu-id="9dc51-352">**Notes**:</span></span>

- <span data-ttu-id="9dc51-353">새 규칙을 만들 때 우선 순위를 설정 하려면 대신 **HostedOutboundSpamFilterRule** Cmdlet에서 _priority_ 매개 변수를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="9dc51-354">아웃 바운드 기본 스팸 필터 정책에는 해당 하는 스팸 필터 규칙이 없으며 항상이에 해당 하지 않는 우선 순위 값이 **가장 낮습니다**.</span><span class="sxs-lookup"><span data-stu-id="9dc51-354">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="9dc51-355">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책 제거</span><span class="sxs-lookup"><span data-stu-id="9dc51-355">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="9dc51-356">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 정책을 제거 하면 해당 하는 아웃 바운드 스팸 필터 규칙이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-356">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="9dc51-357">PowerShell에서 아웃 바운드 스팸 필터 정책을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-357">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9dc51-358">이 예에서는 Marketing 학과 라는 아웃 바운드 스팸 필터 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-358">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9dc51-359">구문과 매개 변수에 대 한 자세한 내용은 [get-hostedoutboundspamfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-359">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="9dc51-360">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="9dc51-360">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="9dc51-361">PowerShell을 사용 하 여 아웃 바운드 스팸 필터 규칙을 제거 하면 해당 하는 아웃 바운드 스팸 필터 정책이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-361">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="9dc51-362">PowerShell에서 아웃 바운드 스팸 필터 규칙을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-362">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="9dc51-363">이 예에서는 Marketing 부서 라는 아웃 바운드 스팸 필터 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc51-363">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="9dc51-364">구문과 매개 변수에 대 한 자세한 내용은 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dc51-364">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="9dc51-365">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="9dc51-365">For more information</span></span>

[<span data-ttu-id="9dc51-366">Office 365의 제한된 사용자 포털에서 차단된 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="9dc51-366">Remove blocked users from the Restricted Users portal in Office 365</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="9dc51-367">아웃바운드 메시지용 높은 위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="9dc51-367">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="9dc51-368">스팸 방지 및 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="9dc51-368">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
