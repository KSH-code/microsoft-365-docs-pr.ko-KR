---
title: 스팸 필터 정책 구성하기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 기본 스팸 필터 설정에는 스팸으로 식별되는 메시지에 관해 수행할 작업 선택이 포함됩니다.
ms.openlocfilehash: 39532db121bb4a9ca5b73ef129b2b0e74e46c69a
ms.sourcegitcommit: 1d5db6e8411b45d0dd1c517339074c2840e33a63
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2020
ms.locfileid: "43216926"
---
# <a name="configure-anti-spam-policies-in-office-365"></a><span data-ttu-id="1d0ea-103">Office 365에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-103">Configure anti-spam policies in Office 365</span></span>

<span data-ttu-id="1d0ea-104">Exchange Online 사서함이 있는 Office 365 고객 또는 Exchange online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 고객인 경우, 인바운드 전자 메일 메시지가 EOP에서 자동으로 스팸으로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="1d0ea-105">EOP는 스팸에 대한 조직의 전반적인 방어책의 일부로 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="1d0ea-106">자세한 내용은 [Office 365의 스팸 방지 보호](anti-spam-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-106">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="1d0ea-107">관리자는 기본 스팸 방지 정책을 보고, 편집하고, 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="1d0ea-108">세분성을 높이기 위해 사용자 지정 스팸 방지 정책을 만들어 조직의 특정 사용자, 그룹 또는 도메인에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="1d0ea-109">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="1d0ea-110">Office 365 보안 및 준수 센터 또는 PowerShell(Office 365 고객의 경우 Exchange Online PowerShell, 독립 실행형 EOP 고객의 경우 Exchange Online Protection PowerShell)에서 스팸 방지 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-110">You can configure anti-spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="anti-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="1d0ea-111">Office 365 보안 및 준수 센터 대 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell의 스팸 방지 정책</span><span class="sxs-lookup"><span data-stu-id="1d0ea-111">Anti-spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="1d0ea-112">EOP에서 스팸 방지 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-112">The basic elements of an anti-spam policy in EOP are:</span></span>

- <span data-ttu-id="1d0ea-113">**스팸 필터 정책**: 스팸 필터링 결과와 알림 옵션에 대한 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-113">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="1d0ea-114">**스팸 필터 규칙**: 스팸 필터 정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-114">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="1d0ea-115">보안 및 준수 센터에서 스팸 방지 정책을 관리하면, 두 가지 요소의 차이는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-115">The difference between these two elements isn't obvious when you manage anti-spam policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="1d0ea-116">보안 및 준수 센터에서 스팸 방지 정책을 만들면, 실제로는 같은 이름을 사용하여 스팸 필터 규칙과 관련된 스팸 필터 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-116">When you create an anti-spam policy in the Security & Compliance Center, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="1d0ea-117">보안 및 준수 센터에서 스팸 방지 정책을 수정할 때, 이름, 우선순위, 활성화됨 또는 비활성화됨 및 받는 사람 필터와 관련된 설정은 스팸 필터 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-117">When you modify an anti-spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="1d0ea-118">다른 모든 설정은 관련 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-118">All other settings modify the associated spam filter policy.</span></span>

- <span data-ttu-id="1d0ea-119">보안 및 준수 센터에서 스팸 방지 정책을 제거하면, 스팸 필터 규칙과 관련 스팸 필터 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-119">When you remove an anti-spam policy from the Security & Compliance Center, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="1d0ea-120">Exchange Online PowerShell 또는 독립 실행형 Exchange Online Protection PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙 사이의 차이가 명확합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-120">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="1d0ea-121">**\*-HostedContentFilterPolicy** cmdlet을 사용하여 스팸 필터 정책을 관리하고, **\*-HostedContentFilterRule** cmdlet을 사용하여 스팸 필터 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-121">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="1d0ea-122">PowerShell에서는 먼저 스팸 필터 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-122">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="1d0ea-123">PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙의 설정을 따로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-123">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>

- <span data-ttu-id="1d0ea-124">PowerShell에서 스팸 필터 정책을 제거하면 상응하는 스팸 필터 규칙은 자동으로 제거되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-124">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-anti-spam-policy"></a><span data-ttu-id="1d0ea-125">기본 스팸 방지 정책</span><span class="sxs-lookup"><span data-stu-id="1d0ea-125">Default anti-spam policy</span></span>

<span data-ttu-id="1d0ea-126">모든 조직에는 다음과 같은 속성을 포함하는 기본 제공되는 Default 스팸 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-126">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="1d0ea-127">정책과 연결된 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 Default 스팸 필터 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-127">The spam filter policy named Default is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="1d0ea-128">Default 정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-128">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="1d0ea-129">사용자가 만든 모든 사용자 지정 정책은 항상 기본 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-129">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="1d0ea-130">Default 정책은 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-130">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="1d0ea-131">스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 스팸 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-131">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1d0ea-132">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="1d0ea-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1d0ea-133"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1d0ea-134">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-134">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="1d0ea-135">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1d0ea-136">Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-136">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1d0ea-137">이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1d0ea-138">스팸 방지 정책을 추가, 수정 및 삭제하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-138">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1d0ea-139">스팸 방지 정책에 대한 읽기 전용 액세스를 위해서는 **보안 읽기 권한자** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-139">For read-only access to anti-spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="1d0ea-140">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [Office 365 보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1d0ea-141">스팸 방지 정책에 대한 권장 설정은 [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-141">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="1d0ea-142">보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-142">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="1d0ea-143">보안 및 준수 센터에서 사용자 지정 스팸 방지 정책을 만들면, 같은 이름을 사용하여 스팸 필터 규칙과 관련된 스팸 필터 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-143">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="1d0ea-144">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-144">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1d0ea-145">**스팸 방지 설정** 페이지에서 **정책 만들기** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-145">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="1d0ea-146">열리는 **새 스팸 필터 정책** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-146">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1d0ea-147">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-147">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="1d0ea-148">`\ % & * + / = ? { } | < > ( ) ; : , [ ] "` 문자를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-148">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="1d0ea-149">이전에 EAC(Exchange 관리 센터)에서 이러한 문자가 포함된 스팸 방지 정책을 만들었다면 PowerShell에서 스팸 방지 정책의 이름을 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-149">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="1d0ea-150">자세한 내용은 이 항목의 뒷부분에 나오는 [PowerShell을 사용하여 스팸 필터 규칙 수정하기](#use-powershell-to-modify-spam-filter-rules) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-150">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="1d0ea-151">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-151">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="1d0ea-152">(선택 사항) **스팸 및 대량 작업** 섹션을 확장하고, 다음 설정을 확인하거나 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-152">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="1d0ea-153">**들어오는 스팸 및 대량 전자 메일에 대해 수행할 작업 선택**: 다음 스팸 필터링 결과를 기반으로 메시지에 수행할 작업을 선택하거나 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-153">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="1d0ea-154">**스팸**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-154">**Spam**</span></span>
     - <span data-ttu-id="1d0ea-155">**높은 정확도의 스팸**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-155">**High confidence spam**</span></span>
     - <span data-ttu-id="1d0ea-156">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-156">**Phishing email**</span></span>
     - <span data-ttu-id="1d0ea-157">**높은 정확도의 피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-157">**High confidence phishing email**</span></span>
     - <span data-ttu-id="1d0ea-158">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-158">**Bulk email**</span></span>

     <span data-ttu-id="1d0ea-159">스팸 필터링 결과에 사용 가능한 작업은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-159">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="1d0ea-160">확인 표시(</span><span class="sxs-lookup"><span data-stu-id="1d0ea-160">A check mark (</span></span> ![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="1d0ea-162">) 작업을 사용할 수 있음을 의미합니다(모든 스팸 필터링 결과에 모든 작업을 사용할 수 있는 것은 아님).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-162">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="1d0ea-163">확인 표시 후 별표(<sup>\*</sup>)는 스팸 필터링 결과에 대한 기본 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-163">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||<span data-ttu-id="1d0ea-164">**스팸**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-164">**Spam**</span></span>|<span data-ttu-id="1d0ea-165">**높은<br/>정확도의<br/>스팸**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-165">**High<br/>confidence<br/>spam**</span></span>|<span data-ttu-id="1d0ea-166">**피싱<br/>전자 메일**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-166">**Phishing<br/>email**</span></span>|<span data-ttu-id="1d0ea-167">**높은<br/>신뢰도의<br/>피싱<br/>전자 메일**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-167">**High<br/>confidence<br/>phishing<br/>email**</span></span>|<span data-ttu-id="1d0ea-168">**대량<br/>전자 메일**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-168">**Bulk<br/>email**</span></span>|
    |<span data-ttu-id="1d0ea-169">**정크 메일 폴더로 메시지 이동**: 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-169">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="1d0ea-170">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-170">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="1d0ea-171">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-171">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="1d0ea-174">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-174">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="1d0ea-175">**X-헤더 추가**: 메시지 헤더에 X-헤더를 추가하고, 메시지를 사서함에 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-175">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="1d0ea-176">나중에 **이 X-헤더 텍스트를 추가** 상자에서 X-헤더 필드 이름(값 아님)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-176">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="1d0ea-177">**스팸** 및 **높은 정확도의 스팸** 결과의 경우, 메시지가 정크 메일 폴더로 이동됩니다.<sup>1, 2</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-177">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="1d0ea-181">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-181">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="1d0ea-182">**텍스트를 제목 줄 앞에 추가**: 메시지의 제목 줄 앞에 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-182">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="1d0ea-183">메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-183">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="1d0ea-184">**이 텍스트를 제목 줄 앞에 추가** 상자에 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-184">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1d0ea-189">**전자 메일 주소로 메시지 리디렉션**: 메시지를 의도된 받는 사람 대신 다른 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-189">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="1d0ea-190">나중에 **이 전자 메일 주소로 메시지 리디렉션** 상자에 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-190">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1d0ea-196">**메시지 삭제**: 모든 첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-196">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1d0ea-201">**메시지 격리**: 메시지를 의도된 받는 사람에게 보내는 대신 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-201">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="1d0ea-202">나중에 **격리** 상자에 메시지가 격리되는 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-202">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="1d0ea-205">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d0ea-205">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="1d0ea-208">**작업 없음**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-208">**No action**</span></span>|||||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <span data-ttu-id="1d0ea-210"><sup>1</sup> Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있으면 메시지는 정크 메일 폴더로 이동합니다(기본적으로 활성화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-210"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1d0ea-211">자세한 내용은 [Office 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-211">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span><br/><span data-ttu-id="1d0ea-212">EOP로 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP 환경에서는 EOP 스팸 필터링 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-212">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="1d0ea-213">자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-213">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span><br/><br/><span data-ttu-id="1d0ea-214"><sup>2</sup> 메일 흐름 규칙(전송 규칙이라고도 함)에서 이 값을 조건으로 사용하여 메시지를 필터링하거나 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-214"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="1d0ea-215">**임곗값 선택**: **대량 전자 메일** 스팸 필터링 결과에 지정된 작업을 트리거하는 메시지의 BCL(대량 불만 수준)을 지정합니다.(지정된 값보다 큼, 크거나 같지 않음).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-215">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="1d0ea-216">값이 높을수록 메시지가 덜 바람직함을 나타냅니다(스팸과 유사할 가능성 높음).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-216">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="1d0ea-217">기본값은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-217">The default value is 7.</span></span> <span data-ttu-id="1d0ea-218">자세한 내용은 [Office 365에서 BCL(대량 불만 수준)](bulk-complaint-level-values.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-218">For more information, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="1d0ea-219">기본적으로 PowerShell 전용 설정 _MarkAsSpamBulkMail_은 스팸 방지 정책에서 `On` 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-219">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="1d0ea-220">이 설정은 **대량 전자 메일** 필터링 결과의 결과에 크게 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-220">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="1d0ea-221">**_MarkAsSpamBulkMail_이 켜짐**: 임곗값보다 큰 BCL은 **스팸** 필터링 결과에 해당하는 SCL 6으로 변환되고, 메시지에 대한 **대량 전자 메일** 필터링 결과에 대한 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-221">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="1d0ea-222">**_MarkAsSpamBulkMail_이 꺼짐**: 메시지에는 BCL이 찍히지만 **대량 전자 메일** 필터링 결과에 대해 수행되는 _작업은 없습니다._</span><span class="sxs-lookup"><span data-stu-id="1d0ea-222">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="1d0ea-223">실제로 BCL 임곗값과 **대량 전자 메일** 필터링 결과 작업은 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-223">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="1d0ea-224">**격리**: 스팸 필터링 결과에 대한 작업으로 **메시지 격리**를 선택한 경우, 메시지를 격리할 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-224">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1d0ea-225">격리 기간이 만료되면 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-225">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="1d0ea-226">기본값은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-226">The default value is 30 days.</span></span> <span data-ttu-id="1d0ea-227">유효한 값은 1~30일입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-227">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="1d0ea-228">격리에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-228">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="1d0ea-229">Office 365에서 격리</span><span class="sxs-lookup"><span data-stu-id="1d0ea-229">Quarantine in Office 365</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="1d0ea-230">Office 365에서 관리자 권한으로 격리된 메시지 및 파일 관리하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-230">Manage quarantined messages and files as an admin in Office 365</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="1d0ea-231">Office 365에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-231">Find and release quarantined messages as a user in Office 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="1d0ea-232">**이 X-헤더 텍스트 추가**: 이 상자는 필수이며, **X-헤더 추가**를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-232">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1d0ea-233">사용자가 지정하는 값은 메시지 헤더에 추가되는 헤더 필드 *이름*입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-233">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="1d0ea-234">헤더 필드 *값*은 항상 `This message appears to be spam`입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-234">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="1d0ea-235">최대 길이는 255자이며, 값에는 공백이나 콜론(:)이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-235">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="1d0ea-236">예를 들어 값 `X-This-is-my-custom-header`을(를) 입력하면 메시지에 추가되는 X-헤더는 `X-This-is-my-custom-header: This message appears to be spam.`입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-236">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="1d0ea-237">공백이나 콜론(:)을 포함하는 값을 입력하면 입력하는 값이 무시되고, 기본 X 머리글이 메시지(`X-This-Is-Spam: This message appears to be spam.`)에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-237">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="1d0ea-238">**이 텍스트를 제목 줄 앞에 추가**: 이 상자는 필수이며, **텍스트를 제목 줄 앞에 추가**를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-238">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1d0ea-239">메시지의 제목 줄의 시작 부분에 추가할 텍스트를 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-239">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="1d0ea-240">**이 전자 메일 주소로 리디렉션**: 이 상자는 필수이며, 스팸 필터링 결과 작업으로 **메시지를 전자 메일 주소로 리디렉션**을 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-240">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="1d0ea-241">메시지를 배달하려는 전자 메일 주소를 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-241">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="1d0ea-242">세미콜론(;)으로 구분하여 여러 값을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-242">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="1d0ea-243">**보안 팁**: 기본적으로 보안 팁은 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-243">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="1d0ea-244">보안 팁에 대한 자세한 내용은 [Office 365에서 전자 메일 메시지의 보안 팁](safety-tips-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-244">For more information about Safety Tips, see [Safety tips in email messages in Office 365](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="1d0ea-245">**제로 아워 자동 제거** 설정: ZAP는 Exchange Online 사서함에 이미 배달된 메시지를 검색하여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-245">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="1d0ea-246">ZAP에 대한 자세한 내용은 [제로 아워 자동 제거 - 스팸 및 맬웨어로부터 보호](zero-hour-auto-purge.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-246">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="1d0ea-247">**스팸 ZAP**: 기본적으로 ZAP에는 스팸 검색이 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-247">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="1d0ea-248">**피싱 ZAP**: 기본적으로 ZAP에는 피싱 검색이 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-248">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="1d0ea-249">(선택 사항) **허용 목록** 섹션을 확장하여 스팸 필터링을 건너뛰도록 허용된 전자 메일 주소나 전자 메일 도메인을 기준으로 메시지를 보낸 사람을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-249">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   > <ul><li><span data-ttu-id="1d0ea-250">여기에 도메인을 추가하기 전에 신중하게 생각하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-250">Think very carefully before you add domains here.</span></span> <span data-ttu-id="1d0ea-251">자세한 내용은 [Office 365에서 수신 허용 - 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-251">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md)</span></span></li><li><span data-ttu-id="1d0ea-252">허용 도메인(소유하고 있는 도메인) 또는 공통 도메인(예: microsoft.com 또는 office.com)을 허용된 도메인 목록에 추가하지 않도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-252">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="1d0ea-253">이를 통해 침입자가 스팸 필터링을 우회하는 전자 메일을 조직에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-253">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span></li></ul>

   - <span data-ttu-id="1d0ea-254">**허용할 보낸 사람**: **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-254">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="1d0ea-255">표시되는 **허용되는 보낸 사람 목록** 플라이아웃에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-255">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="1d0ea-256">a.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-256">a.</span></span> <span data-ttu-id="1d0ea-257">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-257">Enter the sender's email address.</span></span> <span data-ttu-id="1d0ea-258">여러 개인 전자 메일 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-258">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="1d0ea-259">b.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-259">b.</span></span> <span data-ttu-id="1d0ea-260">이</span><span class="sxs-lookup"><span data-stu-id="1d0ea-260">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1d0ea-262">을 클릭하여 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-262">to add the senders.</span></span>

      <span data-ttu-id="1d0ea-263">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-263">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1d0ea-264">사용자가 추가한 보낸 사람은 플라이아웃의 **허용되는 보낸 사람** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-264">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="1d0ea-265">보낸 사람을 삭제하려면 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-265">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1d0ea-266">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-266">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1d0ea-267">**허용할 도메인**: **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-267">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="1d0ea-268">표시되는 **허용되는 도메인 목록** 플라이아웃에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-268">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="1d0ea-269">a.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-269">a.</span></span> <span data-ttu-id="1d0ea-270">도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-270">Enter the domain.</span></span> <span data-ttu-id="1d0ea-271">여러 개의 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-271">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="1d0ea-272">b.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-272">b.</span></span> <span data-ttu-id="1d0ea-273">이</span><span class="sxs-lookup"><span data-stu-id="1d0ea-273">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1d0ea-275">을 클릭하여 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-275">to add the domains.</span></span>

      <span data-ttu-id="1d0ea-276">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-276">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1d0ea-277">사용자가 추가한 도메인은 플라이아웃의 **허용되는 도메인** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-277">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="1d0ea-278">도메인을 삭제하려면 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-278">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1d0ea-279">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-279">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="1d0ea-280">(선택 사항) **차단 목록** 섹션을 확장하여 항상 높은 정확도의 스팸으로 표시되는 전자 메일 주소나 전자 메일 도메인을 기준으로 메시지를 보낸 사람을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-280">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="1d0ea-281">수동으로 도메인을 차단하는 것은 위험하지 않지만, 관리 작업 부하가 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-281">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="1d0ea-282">자세한 내용은 [Office 365에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-282">For more information, see [Create block sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="1d0ea-283">**차단할 보낸 사람**: **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-283">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="1d0ea-284">표시되는 **차단되는 보낸 사람 목록** 플라이아웃에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-284">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="1d0ea-285">a.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-285">a.</span></span> <span data-ttu-id="1d0ea-286">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-286">Enter the sender's email address.</span></span> <span data-ttu-id="1d0ea-287">여러 개인 전자 메일 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-287">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="1d0ea-288">와일드카드(\*)는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-288">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="1d0ea-289">b.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-289">b.</span></span> <span data-ttu-id="1d0ea-290">이</span><span class="sxs-lookup"><span data-stu-id="1d0ea-290">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1d0ea-292">을 클릭하여 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-292">to add the senders.</span></span>

      <span data-ttu-id="1d0ea-293">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-293">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1d0ea-294">추가한 보낸 사람은 플라이아웃의 **차단되는 보낸 사람** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-294">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="1d0ea-295">보낸 사람을 삭제하려면 ![제거 단추](../../media/scc-remove-icon.png)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-295">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1d0ea-296">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-296">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1d0ea-297">**차단할 도메인**: **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-297">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="1d0ea-298">표시되는 **차단되는 도메인 목록** 플라이아웃에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-298">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="1d0ea-299">a.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-299">a.</span></span> <span data-ttu-id="1d0ea-300">도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-300">Enter the domain.</span></span> <span data-ttu-id="1d0ea-301">여러 개의 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-301">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="1d0ea-302">와일드카드(\*)는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-302">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="1d0ea-303">b.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-303">b.</span></span> <span data-ttu-id="1d0ea-304">이</span><span class="sxs-lookup"><span data-stu-id="1d0ea-304">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1d0ea-306">을 클릭하여 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-306">to add the domains.</span></span>

      <span data-ttu-id="1d0ea-307">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-307">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="1d0ea-308">사용자가 추가한 도메인은 플라이아웃의 **차단되는 도메인** 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-308">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="1d0ea-309">도메인을 삭제하려면 ![제거 단추](../../media/scc-remove-icon.png)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-309">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="1d0ea-310">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-310">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="1d0ea-311">(선택 사항) **국제 스팸** 섹션을 확장하여 스팸 필터링으로 차단되는 전자 메일 언어나 원본 국가를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-311">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="1d0ea-312">**다음 언어로 작성된 전자 메일 메시지 필터링**: 이 설정은 기본적으로 비활성화되어 있습니다(**상태: 끔**).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-312">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="1d0ea-313">**편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-313">Click **Edit**.</span></span> <span data-ttu-id="1d0ea-314">표시되는 **국제 스팸 설정** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-314">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="1d0ea-315">**다음 언어로 작성된 전자 메일 메시지 필터링**: 확인란을 선택하여 해당 설정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-315">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="1d0ea-316">이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-316">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="1d0ea-317">상자를 클릭하여 언어의 *이름*을 입력하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-317">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="1d0ea-318">해당 ISO 639-2 언어 코드와 함께 지원되는 언어의 필터링된 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-318">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="1d0ea-319">원하는 언어를 찾았으면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-319">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="1d0ea-320">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-320">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="1d0ea-321">선택한 언어 목록이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-321">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="1d0ea-322">언어를 삭제하려면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-322">To delete a language, click</span></span> ![제거 단추](../../media/scc-remove-icon.png)<span data-ttu-id="1d0ea-324">.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-324">.</span></span>

     <span data-ttu-id="1d0ea-325">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-325">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1d0ea-326">**다음 국가나 지역에서 보낸 전자 메일 메시지 필터링**: 이 설정은 기본적으로 비활성화되어 있습니다(**상태: 꺼짐**).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-326">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="1d0ea-327">이 설정을 사용하도록 설정하려면 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-327">To enable it, click **Edit**.</span></span> <span data-ttu-id="1d0ea-328">표시되는 **국제 스팸 설정** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-328">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="1d0ea-329">**다음 국가나 지역에서 보낸 전자 메일 메시지 필터링**: 확인란을 선택하여 해당 설정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-329">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="1d0ea-330">이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-330">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="1d0ea-331">상자를 클릭하고, 국가나 지역의 *이름*을 입력하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-331">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="1d0ea-332">해당하는 두 자로 된 ISO 3166-1 국가 코드와 함께 지원되는 국가의 필터링된 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-332">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="1d0ea-333">원하는 국가나 지역을 찾았으면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-333">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="1d0ea-334">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-334">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="1d0ea-335">선택한 국가 목록이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-335">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="1d0ea-336">국가나 지역을 삭제하려면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-336">To delete a country or region, click</span></span> ![제거 단추](../../media/scc-remove-icon.png)<span data-ttu-id="1d0ea-338">.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-338">.</span></span>

     <span data-ttu-id="1d0ea-339">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-339">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="1d0ea-340">선택적 **스팸 속성** 섹션에는 기본적으로 꺼져 있는 ASF(고급 스팸 필터) 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-340">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="1d0ea-341">ASF 설정은 더 이상 사용되지 않으며, 해당 기능은 필터링 스택의 다른 부분에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-341">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="1d0ea-342">모든 ASF 설정을 스팸 방지 정책에서 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-342">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="1d0ea-343">이러한 설정에 대한 자세한 내용은 [Office 365에서 고급 스팸 필터 설정](advanced-spam-filtering-asf-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-343">For details about these settings, see [Advanced Spam Filter settings in Office 365](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="1d0ea-344">(필수 사항) **적용 대상** 섹션을 확장하여 정책을 적용할 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-344">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="1d0ea-345">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-345">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="1d0ea-346">동일한 조건이나 예외의 여러 값은 OR 논리를 사용합니다(예: _\<받는 사람1\>_ or _\<받는 사람2\>_).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-346">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="1d0ea-347">다른 조건이나 예외에는 AND 논리를 사용합니다(예: _\<받는 사람1\>_ and _\<그룹 1의 구성원\>_).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-347">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="1d0ea-348">사용 가능한 모든 조건을 보려면 **조건 추가**를 세 번 클릭하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-348">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="1d0ea-349">![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-349">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="1d0ea-350">**받는 사람 도메인은**: Office 365에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-350">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="1d0ea-351">**태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-351">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="1d0ea-352">두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-352">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="1d0ea-353">**받는 사람은**: 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-353">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="1d0ea-354">**태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-354">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="1d0ea-355">**태그 추가**를 다시 클릭하여 추가 받는 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-355">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="1d0ea-356">**받는 사람은 다음의 구성원**: 조직에서 그룹을 하나 이상 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-356">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="1d0ea-357">**태그 추가**를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-357">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="1d0ea-358">**태그 추가**를 다시 클릭하여 추가 받는 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-358">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="1d0ea-359">**다음의 경우 제외**: 규칙에 대한 예외를 추가하려면\*\* 조건 추가\*\*를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-359">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="1d0ea-360">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-360">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="1d0ea-361">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-361">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="1d0ea-362">보안 및 준수 센터를 사용하여 스팸 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-362">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="1d0ea-363">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-363">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1d0ea-364">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-364">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="1d0ea-365">**기본 스팸 필터 정책**이라는 기본 정책.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-365">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="1d0ea-366">**유형** 열의 값이 **사용자 지정 스팸 방지 정책**인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-366">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="1d0ea-367">주요 정책 설정은 표시되는 확장된 정책 세부 정보에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-367">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="1d0ea-368">자세한 내용을 보려면 **정책 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-368">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="1d0ea-369">보안 및 준수 센터를 사용하여 스팸 방지 정책 수정하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-369">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="1d0ea-370">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-370">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1d0ea-371">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-371">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="1d0ea-372">**기본 스팸 필터 정책**이라는 기본 정책.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-372">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="1d0ea-373">**유형** 열의 값이 **사용자 지정 스팸 방지 정책**인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-373">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="1d0ea-374">**정책 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-374">Click **Edit policy**.</span></span>

<span data-ttu-id="1d0ea-375">플라이아웃에서 표시되는 설정은 [보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기](#use-the-security--compliance-center-to-create-anti-spam-policies)에서 사용할 수 있는 설정과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-375">The settings in the flyout that appears are identical to the settings that are available in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="1d0ea-376">**기본 스팸 필터 정책**이라는 기본 스팸 방지 정책의 경우, **적용 대상** 섹션을 사용할 수 없으며(이 정책은 모든 사용자에게 적용됨) 정책의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-376">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="1d0ea-377">정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-377">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="1d0ea-378">스팸 방지 정책 활성화 또는 비활성화하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-378">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="1d0ea-379">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-379">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1d0ea-380">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 사용자가 만든 사용자 지정 정책을 확장합니다(**유형**의 열 값은 **사용자 지정 스팸 방지 정책**).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-380">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="1d0ea-381">표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-381">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="1d0ea-382">토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-382">Move the toggle to the left to disable the policy:</span></span> ![토글 끔](../../media/scc-toggle-off.png)

   <span data-ttu-id="1d0ea-384">토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-384">Move the toggle to the right to enable the policy:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="1d0ea-386">기본 스팸 방지 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-386">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="1d0ea-387">사용자 지정 스팸 방지 정책의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-387">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="1d0ea-388">기본적으로 만들어진 순서에 따라 스팸 방지 정책에 우선순위가 지정됩니다(새 정책은 이전 정책 보다 우선순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-388">By default, anti-spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="1d0ea-389">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-389">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="1d0ea-390">두 정책의 우선순위가 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-390">No two policies can have the same priority.</span></span>

<span data-ttu-id="1d0ea-391">사용자 지정 스팸 방지 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 **우선순위** 값 0이 표시됨).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-391">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="1d0ea-392">**기본 스팸 필터 정책**이라는 기본 스팸 방지 정책은 우선순위 값이 **가장 낮음**이며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-392">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="1d0ea-393">**참고**: 보안 및 준수 센터에서는 스팸 방지 정책을 만든 후에만 우선순위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-393">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="1d0ea-394">PowerShell에서 사용자는 기존 규칙의 우선순위에 영향을 줄 수 있는 스팸 필터 규칙을 만들 때 기본 우선순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-394">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="1d0ea-395">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-395">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="1d0ea-396">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-396">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1d0ea-397">**스팸 방지 설정** 페이지에서 **유형** 열의 값이 **사용자 지정 스팸 방지 정책**인 정책을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-397">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="1d0ea-398">**우선순위** 열의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-398">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="1d0ea-399">우선순위가 가장 높은 사용자 지정 스팸 방지 정책의 값은 ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **0**입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-399">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="1d0ea-400">우선순위가 가장 낮은 사용자 지정 스팸 방지 정책의 값은 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **n**(예: ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **3**)입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-400">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="1d0ea-401">사용자 지정 스팸 방지 정책이 세 개 이상 있는 경우, 가장 높은 우선순위와 가장 낮은 우선순위 사이의 정책 값은 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **n**입니다(예: ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-401">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="1d0ea-402">이</span><span class="sxs-lookup"><span data-stu-id="1d0ea-402">Click</span></span> ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="1d0ea-404">또는</span><span class="sxs-lookup"><span data-stu-id="1d0ea-404">or</span></span> ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="1d0ea-406">을 클릭하여 우선 순위 목록에서 사용자 지정 스팸 방지 정책을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-406">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="1d0ea-407">최종 사용자 스팸 알림 구성하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-407">Configure end-user spam notifications</span></span>

<span data-ttu-id="1d0ea-408">스팸 필터링 결과에서 메시지를 격리하는 경우, 받는 사람에게 전송된 메시지에 일어난 자세한 내용을 알릴 수 있도록 최종 사용자 스팸 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-408">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="1d0ea-409">이 알림에 대한 자세한 내용은 [Office 365에서 최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-409">For more information about these notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="1d0ea-410">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-410">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1d0ea-411">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-411">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="1d0ea-412">**기본 스팸 필터 정책**이라는 기본 정책.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-412">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="1d0ea-413">**유형** 열의 값이 **사용자 지정 스팸 방지 정책**인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-413">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="1d0ea-414">표시되는 확장된 정책 세부 정보에서 **최종 사용자 스팸 알림 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-414">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="1d0ea-415">열리는 **\<정책 이름\>** 대화 상자에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-415">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1d0ea-416">**최종 사용자 스팸 알림 활성화**: 확인란을 선택하여 알림을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-416">**Enable end-user spam notifications**: Select the checkbobx to enable notifications.</span></span> <span data-ttu-id="1d0ea-417">알림을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-417">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="1d0ea-418">**최종 사용자 스팸 알림 보내기 간격(일)**: 알림을 보내는 빈도를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-418">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="1d0ea-419">기본값은 3일입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-419">The default value is 3 days.</span></span> <span data-ttu-id="1d0ea-420">1~15일을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-420">You can enter 1 to 15 days.</span></span>

   - <span data-ttu-id="1d0ea-421">**알림 언어**: 드롭다운을 클릭하고. 목록에서 사용 가능한 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-421">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="1d0ea-422">기본값은 **기본**입니다. 즉, 최종 사용자 격리 알림은 EOP 조직의 기본 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-422">The default value is **Default**, which means end-user quarantine notifications use the default language of the EOP organization.</span></span>

   <span data-ttu-id="1d0ea-423">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-423">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="1d0ea-424">보안 및 준수 센터를 사용하여 스팸 방지 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-424">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="1d0ea-425">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-425">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1d0ea-426">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 삭제하려는 사용자 지정 정책을 확장합니다(**유형** 열은 **사용자 지정 스팸 방지 정책**).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-426">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="1d0ea-427">표시되는 확장된 정책 세부 정보에서 **정책 삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-427">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="1d0ea-428">표시되는 경고 대화 상자에서 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-428">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="1d0ea-429">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-429">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="1d0ea-430">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell을 사용하여 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-430">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="1d0ea-431">다음 스팸 방지 정책 설정은 PowerShell에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-431">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="1d0ea-432">기본적으로 `On` 상태인 _MarkAsSpamBulkMail_ 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-432">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="1d0ea-433">이 설정의 효과는 이 항목의 앞부분에 있는 [보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기](#use-the-security--compliance-center-to-create-anti-spam-policies) 섹션에서 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-433">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="1d0ea-434">최종 사용자 스팸 격리 알림을 위한 다음 설정:</span><span class="sxs-lookup"><span data-stu-id="1d0ea-434">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="1d0ea-435">_DownloadLink_ 매개 변수는 Outlook용 정크 메일 보고 도구에 대한 링크를 표시하거나 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-435">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="1d0ea-436">_EndUserSpamNotificationCustomSubject_ 매개 변수는 알림의 제목 줄을 사용자 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-436">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="1d0ea-437">PowerShell을 사용하여 스팸 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-437">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="1d0ea-438">PowerShell에서 스팸 방지 정책을 만드는 작업은 2단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-438">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="1d0ea-439">스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-439">Create the spam filter policy.</span></span>

2. <span data-ttu-id="1d0ea-440">규칙이 적용되는 스팸 필터 정책을 지정하는 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-440">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="1d0ea-441">**참고:**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-441">**Notes**:</span></span>

- <span data-ttu-id="1d0ea-442">새 스팸 필터 규칙을 만들어 연결되지 않은 기존 스팸 필터 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-442">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="1d0ea-443">스팸 필터 규칙은 둘 이상의 스팸 필터 정책에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-443">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="1d0ea-444">정책을 만들 때까지 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-444">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="1d0ea-445">비활성화된 새 정책을 만듭니다(**New-HostedContentFilterRule** cmdlet에서 `$false`를 _Enabled_).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-445">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="1d0ea-446">**New-HostedContentFilterRule** cmdlet에서 만드는 동안 정책 우선순위(_우선순위_ _\<번호\>_)를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-446">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="1d0ea-447">스팸 필터 규칙에 정책을 할당할 때까지 PowerShell에서 만든 새로운 스팸 필터 정책은 보안 및 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-447">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="1d0ea-448">1단계: PowerShell을 사용하여 스팸 필터 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-448">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="1d0ea-449">스팸 필터 정책을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-449">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="1d0ea-450">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 정책을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-450">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="1d0ea-451">스팸 필터링 결과가 스팸이거나 높은 정확도의 스팸인 경우 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-451">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="1d0ea-452">BCL 6은 대량 전자 메일 스팸 필터링 결과 작업을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-452">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="1d0ea-453">**New-Set-hostedcontentfilterpolicy** 및 **Set-Set-hostedcontentfilterpolicy**에는 이전 _ZapEnabled_ 매개 변수와 최신 _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-453">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="1d0ea-454">_ZapEnabled_ 매개 변수는 2020년 2월부터 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-454">The _ZapEnabled_ parameter was deprecated in February, 2020.</span></span> <span data-ttu-id="1d0ea-455">_PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수는 _ZapEnabled_ 매개 변수에서 값을 상속하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-455">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="1d0ea-456">그러나 명령에 _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수를 사용하거나 보안 및 준수 센터의 스팸 방지 정책에서 **Spam ZAP** 또는 **Phish ZAP** 설정을 사용하는 경우, _ZapEnabled_ 매개 변수의 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-456">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="1d0ea-457">즉, _ZapEnabled_ 매개 변수를 사용하지 않도록 하세요. _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-457">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="1d0ea-458">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-458">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="1d0ea-459">2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-459">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="1d0ea-460">스팸 필터 규칙을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-460">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="1d0ea-461">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 규칙을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-461">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="1d0ea-462">Contoso Executives라는 스팸 필터 정책은 규칙과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-462">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="1d0ea-463">이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-463">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="1d0ea-464">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-464">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="1d0ea-465">PowerShell을 사용하여 스팸 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-465">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="1d0ea-466">모든 스팸 필터 정책의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-466">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="1d0ea-467">특정 스팸 필터 정책에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-467">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="1d0ea-468">다음은 Executives라는 스팸 필터 정책의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-468">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="1d0ea-469">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-469">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="1d0ea-470">PowerShell을 사용하여 스팸 필터 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-470">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="1d0ea-471">기존 스팸 필터 규칙을 보려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-471">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled]
```

<span data-ttu-id="1d0ea-472">모든 스팸 필터 규칙의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-472">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="1d0ea-473">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-473">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="1d0ea-474">특정 스팸 필터 규칙에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-474">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="1d0ea-475">다음은 Contoso Executives라는 스팸 필터 규칙의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-475">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="1d0ea-476">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-476">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="1d0ea-477">PowerShell을 사용하여 스팸 필터 정책 수정하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-477">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="1d0ea-478">다음과 같은 항목 외에 PowerShell에서 맬웨어 필터 정책을 수정할 때 이 항목 앞부분의 [1단계 : PowerShell을 사용하여 스팸 필터 정책 만들기](#step-1-use-powershell-to-create-a-spam-filter-policy) 섹션에 설명된 대로 정책을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-478">Other than the following items, the same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="1d0ea-479">지정된 정책을 기본 정책으로 바꾸는 _MakeDefault_ 스위치(모든 사용자에게 적용, 항상 **가장 낮은** 우선순위이며 삭제할 수 없음)는 PowerShell에서 스팸 필터 정책을 수정할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-479">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="1d0ea-480">스팸 필터 정책 이름을 바꿀 수 없습니다(**Set-HostedContentFilterPolicy** cmdlet에 _Name_ 매개 변수가 없음).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-480">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="1d0ea-481">보안 및 준수 센터에서 스팸 방지 정책의 이름을 바꿀 경우 스팸 필터 _규칙_ 이름만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-481">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="1d0ea-482">스팸 필터 정책을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-482">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="1d0ea-483">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-483">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="1d0ea-484">PowerShell을 사용하여 스팸 필터 규칙 수정하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-484">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="1d0ea-485">PowerShell에서 스팸 필터 규칙을 수정할 때 사용할 수 없는 유일한 설정은 비활성화된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-485">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="1d0ea-486">기존 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-486">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="1d0ea-487">그렇지 않으면 PowerShell에서 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-487">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="1d0ea-488">이 항목 앞부분의 [2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기](#step-2-use-powershell-to-create-a-spam-filter-rule) 섹션에 설명된 대로 규칙을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-488">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="1d0ea-489">스팸 필터 규칙을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-489">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="1d0ea-490">다음은 보안 및 준수 센터에서 문제를 일으킬 수 있는 `{Fabrikam Spam Filter}`(이)라는 기존 스팸 필터 규칙의 이름을 바꾸는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-490">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="1d0ea-491">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-491">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="1d0ea-492">PowerShell을 사용하여 스팸 필터 규칙 활성화 또는 비활성화하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-492">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="1d0ea-493">PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하면 전체 스팸 방지 정책(스팸 필터 규칙과 할당된 스팸 필터 정책)을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-493">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="1d0ea-494">기본 스팸 방지 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됨).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-494">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="1d0ea-495">PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-495">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="1d0ea-496">다음은 Marketing Department라는 스팸 필터 규칙을 사용하지 않도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-496">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1d0ea-497">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-497">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1d0ea-498">자세한 구문 및 매개 변수 정보는 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule)과 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-498">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="1d0ea-499">PowerShell을 사용하여 스팸 필터 규칙의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-499">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="1d0ea-500">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-500">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="1d0ea-501">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-501">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="1d0ea-502">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-502">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="1d0ea-503">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-503">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="1d0ea-504">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-504">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="1d0ea-505">PowerShell에서 스팸 필터 규칙의 우선순위를 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-505">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="1d0ea-506">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-506">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="1d0ea-507">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="1d0ea-507">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="1d0ea-508">**참고:**</span><span class="sxs-lookup"><span data-stu-id="1d0ea-508">**Notes**:</span></span>

- <span data-ttu-id="1d0ea-509">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-HostedContentFilterRule** cmdlet에서 _우선순위_ 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-509">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="1d0ea-510">기본 스팸 필터 정책에는 상응하는 스팸 필터 규칙이 없으며 항상 수정할 수 없는 **가장 낮은** 우선순위 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-510">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="1d0ea-511">PowerShell을 사용하여 스팸 필터 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-511">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="1d0ea-512">PowerShell을 사용하여 스팸 필터 정책을 제거할 때 상응하는 스팸 필터 규칙은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-512">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="1d0ea-513">PowerShell에서 스팸 필터 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-513">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="1d0ea-514">다음은 Marketing Department라는 스팸 필터 정책을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-514">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="1d0ea-515">자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-515">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="1d0ea-516">PowerShell을 사용하여 스팸 필터 규칙 제거하기</span><span class="sxs-lookup"><span data-stu-id="1d0ea-516">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="1d0ea-517">PowerShell을 사용하여 스팸 필터 규칙을 제거할 때 상응하는 스팸 필터 정책은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-517">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="1d0ea-518">PowerShell에서 스팸 필터 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-518">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="1d0ea-519">다음은 Marketing Department라는 스팸 필터 규칙을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-519">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1d0ea-520">자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-520">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1d0ea-521">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="1d0ea-521">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="1d0ea-522">GTUBE 메시지를 보내서 스팸 정책 설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-522">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="1d0ea-523">이 단계는 GTUBE 메시지를 보내는 전자 메일 조직이 아웃바운드 스팸을 검사하지 않는 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-523">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="1d0ea-524">검사하는 경우에는 테스트 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-524">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="1d0ea-525">GTUBE(원치 않는 대량 전자 메일용 제네릭 테스트)는 조직에서 스팸 방지 설정을 확인하기 위해 테스트 메시지에 포함하는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-525">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="1d0ea-526">GTUBE 메시지는 맬웨어 설정을 테스트하기 위한 EICAR(European Institute for Computer Antivirus Research) 텍스트 파일과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-526">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="1d0ea-527">공백이나 줄 바꿈 없이 다음 GTUBE 텍스트를 전자 메일 메시지의 한 줄에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-527">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="1d0ea-528">허용/차단 목록</span><span class="sxs-lookup"><span data-stu-id="1d0ea-528">Allow/Block Lists</span></span>

<span data-ttu-id="1d0ea-529">필터가 메시지를 빠뜨리거나 시스템에서 메시지를 확인하는 데 시간이 걸리는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-529">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="1d0ea-530">이 경우 스팸 방지 정책에는 현재 결과를 재정의하는 데 사용할 수 있는 허용 및 차단 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-530">In this cases, the antispam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="1d0ea-531">수행할 작업이 필터링 스택에서 수행되고 있어야 하므로 목록을 관리할 수 없고 일시적이기 때문에 이 옵션은 드물게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-531">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="1d0ea-532">조직이 서비스에서 제공하는 결과에 동의하지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-532">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="1d0ea-533">이 경우 허용 또는 차단 목록을 영구적으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-533">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="1d0ea-534">하지만 도메인을 허용 목록에 오래 동안 유지할 경우 보낸 사람에게 도메인을 인증하는지 확인하고, 확인하지 않을 경우 DMARC 거부로 설정하도록 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-534">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
