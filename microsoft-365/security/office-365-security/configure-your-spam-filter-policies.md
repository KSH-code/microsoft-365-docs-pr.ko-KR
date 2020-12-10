---
title: 스팸 필터 정책 구성하기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online Protection(EOP)에서 스팸 방지 정책을 보고, 만들고 수정하고 삭제하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 81c5e74ec45cc633b3a4ba46c7865d0a643af2cd
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616695"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="8596c-103">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="8596c-103">Configure anti-spam policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8596c-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 경우, 인바운드 전자 메일 메시지가 EOP를 통해 자동으로 스팸으로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="8596c-105">EOP는 스팸에 대한 조직의 전반적인 방어책의 일부로 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="8596c-106">자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-106">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="8596c-107">관리자는 기본 스팸 방지 정책을 보고, 편집하고, 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="8596c-108">세분성을 높이기 위해 사용자 지정 스팸 방지 정책을 만들어 조직의 특정 사용자, 그룹 또는 도메인에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="8596c-109">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="8596c-110">보안 및 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online PowerShell; Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 스팸 방지 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-110">You can configure anti-spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="8596c-111">스팸 방지 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-111">The basic elements of an anti-spam policy are:</span></span>

- <span data-ttu-id="8596c-112">**스팸 필터 정책**: 스팸 필터링 결과와 알림 옵션에 대한 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-112">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="8596c-113">**스팸 필터 규칙**: 스팸 필터 정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-113">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="8596c-114">보안 및 준수 센터에서 스팸 방지 정책을 관리하면, 두 가지 요소의 차이는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-114">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="8596c-115">스팸 방지 정책을 만드는 경우에는 사용자가 같은 이름을 사용하여 동시에 스팸 필터 규칙과 관련 스팸 필터 정책을 작성하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-115">When you create an anti-spam policy, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="8596c-116">스팸 방지 정책을 수정하는 경우, 이름, 우선 순위, 사용 또는 사용 안 함 및 받는 사람 필터와 관련된 설정은 스팸 필터 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-116">When you modify an anti-spam policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="8596c-117">다른 모든 설정은 관련 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-117">All other settings modify the associated spam filter policy.</span></span>
- <span data-ttu-id="8596c-118">스팸 방지 정책을 제거하면, 스팸 필터 규칙과 관련 스팸 필터 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-118">When you remove an anti-spam policy, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="8596c-119">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="8596c-120">자세한 내용은 이 항목의 뒷부분에 나오는 [Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 스팸 방지 정책 구성](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="8596c-121">모든 조직에는 다음과 같은 속성을 포함하는 기본 제공되는 Default 스팸 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-121">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="8596c-122">정책과 연결된 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 스팸 필터 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-122">The policy is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="8596c-123">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="8596c-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="8596c-124">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="8596c-125">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="8596c-126">스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 스팸 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-126">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8596c-127">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8596c-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8596c-128"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8596c-129">**스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-129">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="8596c-130">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8596c-131">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8596c-132">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-132">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8596c-133">스팸 방지 정책을 추가, 수정 및 삭제하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-133">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8596c-134">스팸 방지 정책에 대한 읽기 전용 액세스를 위해서는 **전체 읽기 권한자** 또는 **보안 읽기 권한자** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-134">For read-only access to anti-spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8596c-135">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-135">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="8596c-136">**참고**:</span><span class="sxs-lookup"><span data-stu-id="8596c-136">**Notes**:</span></span>

  - <span data-ttu-id="8596c-137">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8596c-138">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-138">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="8596c-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="8596c-140">스팸 방지 정책에 대한 권장 설정은 [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-140">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="8596c-141">보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8596c-141">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="8596c-142">보안 및 준수 센터에서 사용자 지정 스팸 방지 정책을 만들면, 같은 이름을 사용하여 스팸 필터 규칙과 관련된 스팸 필터 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-142">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="8596c-143">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8596c-144">**스팸 방지 설정** 페이지에서 **정책 만들기** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-144">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="8596c-145">열리는 **새 스팸 필터 정책** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-145">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="8596c-146">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-146">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="8596c-147">`\ % & * + / = ? { } | < > ( ) ; : , [ ] "` 문자를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-147">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="8596c-148">이전에 EAC(Exchange 관리 센터)에서 이러한 문자가 포함된 스팸 방지 정책을 만들었다면 PowerShell에서 스팸 방지 정책의 이름을 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-148">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="8596c-149">자세한 내용은 이 항목의 뒷부분에 나오는 [PowerShell을 사용하여 스팸 필터 규칙 수정하기](#use-powershell-to-modify-spam-filter-rules) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-149">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="8596c-150">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-150">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="8596c-151">(선택 사항) **스팸 및 대량 작업** 섹션을 확장하고, 다음 설정을 확인하거나 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-151">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="8596c-152">**들어오는 스팸 및 대량 전자 메일에 대해 수행할 작업 선택**: 다음 스팸 필터링 결과를 기반으로 메시지에 수행할 작업을 선택하거나 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-152">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="8596c-153">**스팸**</span><span class="sxs-lookup"><span data-stu-id="8596c-153">**Spam**</span></span>
     - <span data-ttu-id="8596c-154">**높은 정확도의 스팸**</span><span class="sxs-lookup"><span data-stu-id="8596c-154">**High confidence spam**</span></span>
     - <span data-ttu-id="8596c-155">**피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="8596c-155">**Phishing email**</span></span>
     - <span data-ttu-id="8596c-156">**높은 정확도의 피싱 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="8596c-156">**High confidence phishing email**</span></span>
     - <span data-ttu-id="8596c-157">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="8596c-157">**Bulk email**</span></span>

     <span data-ttu-id="8596c-158">스팸 필터링 결과에 사용 가능한 작업은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-158">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="8596c-159">확인 표시(</span><span class="sxs-lookup"><span data-stu-id="8596c-159">A check mark (</span></span> ![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="8596c-161">) 작업을 사용할 수 있음을 의미합니다(모든 스팸 필터링 결과에 모든 작업을 사용할 수 있는 것은 아님).</span><span class="sxs-lookup"><span data-stu-id="8596c-161">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="8596c-162">확인 표시 후 별표(<sup>\*</sup>)는 스팸 필터링 결과에 대한 기본 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-162">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     ****

     |<span data-ttu-id="8596c-163">조치</span><span class="sxs-lookup"><span data-stu-id="8596c-163">Action</span></span>|<span data-ttu-id="8596c-164">스팸</span><span class="sxs-lookup"><span data-stu-id="8596c-164">Spam</span></span>|<span data-ttu-id="8596c-165">높음</span><span class="sxs-lookup"><span data-stu-id="8596c-165">High</span></span><br><span data-ttu-id="8596c-166">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="8596c-166">confidence</span></span><br><span data-ttu-id="8596c-167">스팸</span><span class="sxs-lookup"><span data-stu-id="8596c-167">spam</span></span>|<span data-ttu-id="8596c-168">피싱</span><span class="sxs-lookup"><span data-stu-id="8596c-168">Phishing</span></span><br><span data-ttu-id="8596c-169">전자 메일</span><span class="sxs-lookup"><span data-stu-id="8596c-169">email</span></span>|<span data-ttu-id="8596c-170">높음</span><span class="sxs-lookup"><span data-stu-id="8596c-170">High</span></span><br><span data-ttu-id="8596c-171">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="8596c-171">confidence</span></span><br><span data-ttu-id="8596c-172">피싱</span><span class="sxs-lookup"><span data-stu-id="8596c-172">phishing</span></span><br><span data-ttu-id="8596c-173">전자 메일</span><span class="sxs-lookup"><span data-stu-id="8596c-173">email</span></span>|<span data-ttu-id="8596c-174">대량</span><span class="sxs-lookup"><span data-stu-id="8596c-174">Bulk</span></span><br><span data-ttu-id="8596c-175">전자 메일</span><span class="sxs-lookup"><span data-stu-id="8596c-175">email</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="8596c-176">**정크 메일 폴더로 메시지 이동**: 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-176">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="8596c-177">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-177">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="8596c-178">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-178">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="8596c-181">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-181">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="8596c-182">**X-헤더 추가**: 메시지 헤더에 X-헤더를 추가하고, 메시지를 사서함에 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-182">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <p> <span data-ttu-id="8596c-183">나중에 **이 X-헤더 텍스트를 추가** 상자에서 X-헤더 필드 이름(값 아님)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-183">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <p> <span data-ttu-id="8596c-184">**스팸** 및 **높은 정확도의 스팸** 결과의 경우, 메시지가 정크 메일 폴더로 이동됩니다.<sup>1, 2</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-184">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="8596c-188">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-188">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="8596c-189">**텍스트를 제목 줄 앞에 추가**: 메시지의 제목 줄 앞에 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-189">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="8596c-190">메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-190">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <p> <span data-ttu-id="8596c-191">**이 텍스트를 제목 줄 앞에 추가** 상자에 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-191">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="8596c-196">**전자 메일 주소로 메시지 리디렉션**: 메시지를 의도된 받는 사람 대신 다른 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-196">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <p> <span data-ttu-id="8596c-197">나중에 **이 전자 메일 주소로 메시지 리디렉션** 상자에 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-197">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="8596c-203">**메시지 삭제**: 모든 첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-203">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="8596c-208">**메시지 격리**: 메시지를 의도된 받는 사람에게 보내는 대신 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-208">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <p> <span data-ttu-id="8596c-209">나중에 **격리** 상자에 메시지가 격리되는 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-209">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="8596c-212">![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8596c-212">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |<span data-ttu-id="8596c-215">**작업 없음**</span><span class="sxs-lookup"><span data-stu-id="8596c-215">**No action**</span></span>|||||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     > <span data-ttu-id="8596c-217"><sup>1</sup> Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있으면 메시지는 정크 메일 폴더로 이동합니다(기본적으로 활성화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="8596c-217"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="8596c-218">자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-218">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="8596c-219">EOP로 온-프레미스 Exchange 사서함을 보호하는 독립 실행형 EOP 환경에서는 EOP 스팸 필터링 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-219">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="8596c-220">자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-220">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>
     >
     > <span data-ttu-id="8596c-221"><sup>2</sup> 메일 흐름 규칙에서 해당 값을 조건으로 사용하여 메시지를 필터링하거나 경로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-221"><sup>2</sup> You can this use value as a condition in mail flow rules to filter or route the message.</span></span>

   - <span data-ttu-id="8596c-222">**임계값 선택**: **대량 전자 메일** 스팸 필터링 결과(지정된 값 이상, 이하 혹은 같음)에 지정된 작업을 트리거하는 메시지의 BCL(대량 불만 수준)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-222">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="8596c-223">값이 높을수록 메시지가 덜 바람직함을 나타냅니다(스팸과 유사할 가능성 높음).</span><span class="sxs-lookup"><span data-stu-id="8596c-223">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="8596c-224">기본값은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-224">The default value is 7.</span></span> <span data-ttu-id="8596c-225">자세한 내용은 [EOP에서의 BCL(대량 불만 수준)](bulk-complaint-level-values.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-225">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="8596c-226">기본적으로 PowerShell 전용 설정 _MarkAsSpamBulkMail_ 은 스팸 방지 정책에서 `On` 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-226">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="8596c-227">이 설정은 **대량 전자 메일** 필터링 결과의 결과에 크게 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-227">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="8596c-228">**_MarkAsSpamBulkMail_ 이 켜짐**: 임곗값보다 큰 BCL은 **스팸** 필터링 결과에 해당하는 SCL 6으로 변환되고, 메시지에 대한 **대량 전자 메일** 필터링 결과에 대한 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-228">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="8596c-229">**_MarkAsSpamBulkMail_ 이 꺼짐**: 메시지에는 BCL이 찍히지만 **대량 전자 메일** 필터링 결과에 대해 수행되는 _작업은 없습니다._</span><span class="sxs-lookup"><span data-stu-id="8596c-229">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="8596c-230">실제로 BCL 임곗값과 **대량 전자 메일** 필터링 결과 작업은 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-230">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="8596c-231">**격리**: 스팸 필터링 결과에 대한 작업으로 **메시지 격리** 를 선택한 경우, 메시지를 격리할 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-231">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8596c-232">격리 기간이 만료되면 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-232">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="8596c-233">기본값은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-233">The default value is 30 days.</span></span> <span data-ttu-id="8596c-234">유효한 값은 1~30일입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-234">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="8596c-235">격리에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-235">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="8596c-236">EOP에서 격리된 메시지</span><span class="sxs-lookup"><span data-stu-id="8596c-236">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="8596c-237">EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기</span><span class="sxs-lookup"><span data-stu-id="8596c-237">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="8596c-238">EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기</span><span class="sxs-lookup"><span data-stu-id="8596c-238">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="8596c-239">**이 X-헤더 텍스트 추가**: 이 상자는 필수이며, **X-헤더 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-239">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8596c-240">사용자가 지정하는 값은 메시지 헤더에 추가되는 헤더 필드 *이름* 입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-240">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="8596c-241">헤더 필드 *값* 은 항상 `This message appears to be spam`입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-241">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="8596c-242">최대 길이는 255자이며, 값에는 공백이나 콜론(:)이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-242">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="8596c-243">예를 들어 값 `X-This-is-my-custom-header`을(를) 입력하면 메시지에 추가되는 X-헤더는 `X-This-is-my-custom-header: This message appears to be spam.`입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-243">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="8596c-244">공백이나 콜론(:)을 포함하는 값을 입력하면 입력하는 값이 무시되고, 기본 X 머리글이 메시지(`X-This-Is-Spam: This message appears to be spam.`)에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-244">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="8596c-245">**이 텍스트를 제목 줄 앞에 추가**: 이 상자는 필수이며, **텍스트를 제목 줄 앞에 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-245">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8596c-246">메시지의 제목 줄의 시작 부분에 추가할 텍스트를 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-246">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="8596c-247">**이 전자 메일 주소로 리디렉션**: 이 상자는 필수이며, 스팸 필터링 결과 작업으로 **메시지를 전자 메일 주소로 리디렉션** 을 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-247">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="8596c-248">메시지를 배달하려는 전자 메일 주소를 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-248">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="8596c-249">세미콜론(;)으로 구분하여 여러 값을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-249">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="8596c-250">**보안 팁**: 기본적으로 보안 팁은 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-250">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="8596c-251">보안 팁에 대한 자세한 내용은 [전자 메일 메시지 보안 팁](safety-tips-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-251">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="8596c-252">**제로 아워 자동 제거** 설정: ZAP는 Exchange Online 사서함에 이미 배달된 메시지를 검색하여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-252">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="8596c-253">ZAP에 대한 자세한 내용은 [제로 아워 자동 제거 - 스팸 및 맬웨어로부터 보호](zero-hour-auto-purge.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-253">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="8596c-254">**스팸 ZAP**: 기본적으로 ZAP에는 스팸 검색이 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-254">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="8596c-255">**피싱 ZAP**: 기본적으로 ZAP에는 피싱 검색이 활성화되어 있지만, **켬** 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-255">**Phish ZAP**: By default, ZAP is enabled for phishing detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="8596c-256">(선택 사항) **허용 목록** 섹션을 확장하여 스팸 필터링을 건너뛰도록 허용된 전자 메일 주소나 전자 메일 도메인을 기준으로 메시지를 보낸 사람을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-256">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   >
   > - <span data-ttu-id="8596c-257">여기에 도메인을 추가하기 전에 신중하게 생각하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-257">Think very carefully before you add domains here.</span></span> <span data-ttu-id="8596c-258">자세한 내용은 [EOP에서 안전한 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-258">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > - <span data-ttu-id="8596c-259">허용 도메인(소유하고 있는 도메인) 또는 공통 도메인(예: microsoft.com 또는 office.com)을 허용된 도메인 목록에 추가하지 않도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-259">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="8596c-260">이를 통해 침입자가 스팸 필터링을 우회하는 전자 메일을 조직에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-260">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span>

   - <span data-ttu-id="8596c-261">**허용할 보낸 사람**: **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-261">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="8596c-262">표시되는 **허용되는 보낸 사람 목록** 플라이아웃에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-262">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="8596c-263">a.</span><span class="sxs-lookup"><span data-stu-id="8596c-263">a.</span></span> <span data-ttu-id="8596c-264">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-264">Enter the sender's email address.</span></span> <span data-ttu-id="8596c-265">여러 개인 전자 메일 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-265">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="8596c-266">b.</span><span class="sxs-lookup"><span data-stu-id="8596c-266">b.</span></span> <span data-ttu-id="8596c-267">이</span><span class="sxs-lookup"><span data-stu-id="8596c-267">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="8596c-269">을 클릭하여 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-269">to add the senders.</span></span>

      <span data-ttu-id="8596c-270">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-270">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="8596c-271">사용자가 추가한 보낸 사람은 플라이아웃의 **허용되는 보낸 사람** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-271">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="8596c-272">보낸 사람을 삭제하려면 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-272">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="8596c-273">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-273">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="8596c-274">**허용할 도메인**: **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-274">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="8596c-275">표시되는 **허용되는 도메인 목록** 플라이아웃에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-275">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="8596c-276">a.</span><span class="sxs-lookup"><span data-stu-id="8596c-276">a.</span></span> <span data-ttu-id="8596c-277">도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-277">Enter the domain.</span></span> <span data-ttu-id="8596c-278">여러 개의 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-278">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="8596c-279">b.</span><span class="sxs-lookup"><span data-stu-id="8596c-279">b.</span></span> <span data-ttu-id="8596c-280">이</span><span class="sxs-lookup"><span data-stu-id="8596c-280">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="8596c-282">을 클릭하여 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-282">to add the domains.</span></span>

      <span data-ttu-id="8596c-283">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-283">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="8596c-284">사용자가 추가한 도메인은 플라이아웃의 **허용되는 도메인** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-284">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="8596c-285">도메인을 삭제하려면 ![제거 아이콘](../../media/scc-remove-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-285">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="8596c-286">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-286">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="8596c-287">(선택 사항) **차단 목록** 섹션을 확장하여 항상 높은 정확도의 스팸으로 표시되는 전자 메일 주소나 전자 메일 도메인을 기준으로 메시지를 보낸 사람을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-287">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="8596c-288">수동으로 도메인을 차단하는 것은 위험하지 않지만, 관리 작업 부하가 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-288">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="8596c-289">자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-289">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="8596c-290">**차단할 보낸 사람**: **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-290">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="8596c-291">표시되는 **차단되는 보낸 사람 목록** 플라이아웃에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-291">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="8596c-292">a.</span><span class="sxs-lookup"><span data-stu-id="8596c-292">a.</span></span> <span data-ttu-id="8596c-293">보낸 사람의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-293">Enter the sender's email address.</span></span> <span data-ttu-id="8596c-294">여러 개인 전자 메일 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-294">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="8596c-295">와일드카드(\*)는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-295">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="8596c-296">b.</span><span class="sxs-lookup"><span data-stu-id="8596c-296">b.</span></span> <span data-ttu-id="8596c-297">이</span><span class="sxs-lookup"><span data-stu-id="8596c-297">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="8596c-299">을 클릭하여 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-299">to add the senders.</span></span>

      <span data-ttu-id="8596c-300">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-300">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="8596c-301">추가한 보낸 사람은 플라이아웃의 **차단되는 보낸 사람** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-301">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="8596c-302">보낸 사람을 삭제하려면 ![제거 단추](../../media/scc-remove-icon.png)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-302">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="8596c-303">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-303">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="8596c-304">**차단할 도메인**: **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-304">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="8596c-305">표시되는 **차단되는 도메인 목록** 플라이아웃에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-305">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="8596c-306">a.</span><span class="sxs-lookup"><span data-stu-id="8596c-306">a.</span></span> <span data-ttu-id="8596c-307">도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-307">Enter the domain.</span></span> <span data-ttu-id="8596c-308">여러 개의 도메인을 세미콜론(;)으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-308">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="8596c-309">와일드카드(\*)는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-309">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="8596c-310">b.</span><span class="sxs-lookup"><span data-stu-id="8596c-310">b.</span></span> <span data-ttu-id="8596c-311">이</span><span class="sxs-lookup"><span data-stu-id="8596c-311">Click</span></span> ![추가 아이콘](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="8596c-313">을 클릭하여 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-313">to add the domains.</span></span>

      <span data-ttu-id="8596c-314">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-314">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="8596c-315">사용자가 추가한 도메인은 플라이아웃의 **차단되는 도메인** 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-315">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="8596c-316">도메인을 삭제하려면 ![제거 단추](../../media/scc-remove-icon.png)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-316">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="8596c-317">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-317">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="8596c-318">(선택 사항) **국제 스팸** 섹션을 확장하여 스팸 필터링으로 차단되는 전자 메일 언어나 원본 국가를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-318">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="8596c-319">**다음 언어로 작성된 전자 메일 메시지 필터링**: 이 설정은 기본적으로 비활성화되어 있습니다(**상태: 끔**).</span><span class="sxs-lookup"><span data-stu-id="8596c-319">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="8596c-320">**편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-320">Click **Edit**.</span></span> <span data-ttu-id="8596c-321">표시되는 **국제 스팸 설정** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-321">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="8596c-322">**다음 언어로 작성된 전자 메일 메시지 필터링**: 확인란을 선택하여 해당 설정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-322">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="8596c-323">이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-323">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="8596c-324">상자를 클릭하여 언어의 *이름* 을 입력하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-324">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="8596c-325">해당 ISO 639-2 언어 코드와 함께 지원되는 언어의 필터링된 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-325">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="8596c-326">원하는 언어를 찾았으면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-326">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="8596c-327">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-327">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="8596c-328">선택한 언어 목록이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-328">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="8596c-329">언어를 삭제하려면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-329">To delete a language, click</span></span> ![제거 단추](../../media/scc-remove-icon.png)<span data-ttu-id="8596c-331">.</span><span class="sxs-lookup"><span data-stu-id="8596c-331">.</span></span>

     <span data-ttu-id="8596c-332">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-332">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="8596c-333">**다음 국가나 지역에서 보낸 전자 메일 메시지 필터링**: 이 설정은 기본적으로 비활성화되어 있습니다(**상태: 꺼짐**).</span><span class="sxs-lookup"><span data-stu-id="8596c-333">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="8596c-334">이 설정을 사용하도록 설정하려면 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-334">To enable it, click **Edit**.</span></span> <span data-ttu-id="8596c-335">표시되는 **국제 스팸 설정** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-335">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="8596c-336">**다음 국가나 지역에서 보낸 전자 메일 메시지 필터링**: 확인란을 선택하여 해당 설정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-336">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="8596c-337">이 설정을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-337">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="8596c-338">상자를 클릭하고, 국가나 지역의 *이름* 을 입력하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-338">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="8596c-339">해당하는 두 자로 된 ISO 3166-1 국가 코드와 함께 지원되는 국가의 필터링된 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-339">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="8596c-340">원하는 국가나 지역을 찾았으면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-340">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="8596c-341">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-341">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="8596c-342">선택한 국가 목록이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-342">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="8596c-343">국가나 지역을 삭제하려면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-343">To delete a country or region, click</span></span> ![제거 단추](../../media/scc-remove-icon.png)<span data-ttu-id="8596c-345">.</span><span class="sxs-lookup"><span data-stu-id="8596c-345">.</span></span>

     <span data-ttu-id="8596c-346">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-346">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="8596c-347">선택적 **스팸 속성** 섹션에는 기본적으로 꺼져 있는 ASF(고급 스팸 필터) 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-347">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="8596c-348">ASF 설정은 더 이상 사용되지 않으며, 해당 기능은 필터링 스택의 다른 부분에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-348">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="8596c-349">모든 ASF 설정을 스팸 방지 정책에서 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-349">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="8596c-350">이러한 설정에 대한 자세한 내용은 [EOP에서 고급 스팸 필터 설정](advanced-spam-filtering-asf-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-350">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="8596c-351">(필수 사항) **적용 대상** 섹션을 확장하여 정책을 적용할 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-351">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="8596c-352">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-352">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="8596c-353">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="8596c-353">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="8596c-354">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="8596c-354">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="8596c-355">사용 가능한 모든 조건을 보려면 **조건 추가** 를 세 번 클릭하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-355">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="8596c-356">![제거 단추](../../media/scc-remove-icon.png)를 클릭하여 구성하지 않을 조건을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-356">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="8596c-357">**받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-357">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span> <span data-ttu-id="8596c-358">**태그 추가** 상자를 클릭하여 도메인을 확인하고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-358">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="8596c-359">두 개 이상의 도메인을 사용할 수 있는 경우, **태그 추가** 상자를 다시 클릭하여 추가 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-359">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="8596c-360">**받는 사람은**: 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-360">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="8596c-361">**태그 추가** 를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-361">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="8596c-362">**태그 추가** 를 다시 클릭하여 추가 받는 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-362">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="8596c-363">**받는 사람은 다음의 구성원**: 조직에서 그룹을 하나 이상 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-363">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="8596c-364">**태그 추가** 를 클릭하고, 입력을 시작하여 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-364">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="8596c-365">**태그 추가** 를 다시 클릭하여 추가 받는 사람을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-365">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="8596c-366">**다음의 경우 제외**: 규칙에 대한 예외를 추가하려면 **조건 추가** 를 세 번 클릭하여 사용 가능한 모든 예외를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-366">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="8596c-367">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-367">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="8596c-368">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-368">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="8596c-369">보안 및 준수 센터를 사용하여 스팸 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="8596c-369">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="8596c-370">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-370">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8596c-371">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-371">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="8596c-372">**기본 스팸 필터 정책** 이라는 기본 정책.</span><span class="sxs-lookup"><span data-stu-id="8596c-372">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="8596c-373">**유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="8596c-373">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="8596c-374">주요 정책 설정은 표시되는 확장된 정책 세부 정보에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-374">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="8596c-375">자세한 내용을 보려면 **정책 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-375">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="8596c-376">보안 및 준수 센터를 사용하여 스팸 방지 정책 수정하기</span><span class="sxs-lookup"><span data-stu-id="8596c-376">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="8596c-377">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-377">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8596c-378">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-378">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="8596c-379">**기본 스팸 필터 정책** 이라는 기본 정책.</span><span class="sxs-lookup"><span data-stu-id="8596c-379">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="8596c-380">**유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="8596c-380">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="8596c-381">**정책 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-381">Click **Edit policy**.</span></span>

<span data-ttu-id="8596c-382">사용자 지정 스팸 방지 정책의 경우, 플라이아웃에서 표시되는 사용 가능한 설정은 [보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기](#use-the-security--compliance-center-to-create-anti-spam-policies)에서 설명한 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-382">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="8596c-383">**기본 스팸 필터 정책** 이라는 기본 스팸 방지 정책의 경우, **적용 대상** 섹션을 사용할 수 없으며(이 정책은 모든 사용자에게 적용됨) 정책의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-383">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="8596c-384">정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-384">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="8596c-385">스팸 방지 정책 활성화 또는 비활성화하기</span><span class="sxs-lookup"><span data-stu-id="8596c-385">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="8596c-386">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-386">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8596c-387">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 사용자가 만든 사용자 지정 정책을 확장합니다(**유형** 의 열 값은 **사용자 지정 스팸 방지 정책**).</span><span class="sxs-lookup"><span data-stu-id="8596c-387">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="8596c-388">표시되는 확장된 정책 세부 정보에서 **켬** 열에 있는 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-388">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="8596c-389">토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-389">Move the toggle to the left to disable the policy:</span></span> ![토글 끔](../../media/scc-toggle-off.png)

   <span data-ttu-id="8596c-391">토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-391">Move the toggle to the right to enable the policy:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="8596c-393">기본 스팸 방지 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-393">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="8596c-394">사용자 지정 스팸 방지 정책의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="8596c-394">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="8596c-395">기본적으로 만들어진 순서에 따라 스팸 방지 정책에 우선순위가 지정됩니다(새 정책은 이전 정책 보다 우선순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="8596c-395">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="8596c-396">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="8596c-396">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="8596c-397">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-397">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="8596c-398">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-398">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="8596c-399">사용자 지정 스팸 방지 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 **우선순위** 값 0이 표시됨).</span><span class="sxs-lookup"><span data-stu-id="8596c-399">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="8596c-400">**기본 스팸 필터 정책** 이라는 기본 스팸 방지 정책은 우선순위 값이 **가장 낮음** 이며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-400">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="8596c-401">**참고**: 보안 및 준수 센터에서는 스팸 방지 정책을 만든 후에만 우선순위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-401">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="8596c-402">PowerShell에서 사용자는 기존 규칙의 우선순위에 영향을 줄 수 있는 스팸 필터 규칙을 만들 때 기본 우선순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-402">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="8596c-403">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-403">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="8596c-404">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-404">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8596c-405">**스팸 방지 설정** 페이지에서 **유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 정책을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-405">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="8596c-406">**우선순위** 열의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-406">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="8596c-407">우선순위가 가장 높은 사용자 지정 스팸 방지 정책의 값은 ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **0** 입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-407">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="8596c-408">우선순위가 가장 낮은 사용자 지정 스팸 방지 정책의 값은 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **n**(예: ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) **3**)입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-408">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="8596c-409">사용자 지정 스팸 방지 정책이 세 개 이상 있는 경우, 가장 높은 우선순위와 가장 낮은 우선순위 사이의 정책 값은 ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **n** 입니다(예: ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png)![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="8596c-409">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="8596c-410">이</span><span class="sxs-lookup"><span data-stu-id="8596c-410">Click</span></span> ![위쪽 화살표 아이콘](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="8596c-412">또는</span><span class="sxs-lookup"><span data-stu-id="8596c-412">or</span></span> ![아래쪽 화살표 아이콘](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="8596c-414">을 클릭하여 우선 순위 목록에서 사용자 지정 스팸 방지 정책을 위나 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-414">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="8596c-415">최종 사용자 스팸 알림 구성하기</span><span class="sxs-lookup"><span data-stu-id="8596c-415">Configure end-user spam notifications</span></span>

<span data-ttu-id="8596c-416">스팸 필터링 결과에서 메시지를 격리하는 경우, 받는 사람에게 전송된 메시지에 일어난 자세한 내용을 알릴 수 있도록 최종 사용자 스팸 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-416">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="8596c-417">이 알림에 대한 자세한 내용은 [EOP에서 최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-417">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="8596c-418">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-418">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8596c-419">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 스팸 방지 정책을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-419">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="8596c-420">**기본 스팸 필터 정책** 이라는 기본 정책.</span><span class="sxs-lookup"><span data-stu-id="8596c-420">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="8596c-421">**유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="8596c-421">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="8596c-422">표시되는 확장된 정책 세부 정보에서 **최종 사용자 스팸 알림 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-422">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="8596c-423">열리는 **\<Policy Name\>** 대화 상자에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-423">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="8596c-424">**최종 사용자 스팸 알림 사용 설정**: 확인란을 선택하여 알림을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8596c-424">**Enable end-user spam notifications**: Select the checkbox to enable notifications.</span></span> <span data-ttu-id="8596c-425">알림을 사용하지 않도록 설정하려면 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-425">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="8596c-426">**최종 사용자 스팸 알림 보내기 간격(일)**: 알림을 보내는 빈도를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-426">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="8596c-427">기본값은 3일입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-427">The default value is 3 days.</span></span> <span data-ttu-id="8596c-428">1~15일을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-428">You can enter 1 to 15 days.</span></span>

     <span data-ttu-id="8596c-429">24시간 내에 다음 시간에 시작하는 최종 사용자 스팸 알림의 3가지 주기가 있습니다(01:00 UTC, 08:00 UTC 및 16:00 UTC).</span><span class="sxs-lookup"><span data-stu-id="8596c-429">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8596c-430">이전 주기 중에 알림이 누락되면 다음 주기가 알림을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-430">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="8596c-431">이로 인해 당일에 여러 알림이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-431">This may give the appearance of multiple notifications within the same day.</span></span>

   - <span data-ttu-id="8596c-432">**알림 언어**: 드롭다운을 클릭하고. 목록에서 사용 가능한 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-432">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="8596c-433">기본적인 값은 **기본값** 이고 이는 영어를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-433">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="8596c-434">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-434">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="8596c-435">보안 및 준수 센터를 사용하여 스팸 방지 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="8596c-435">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="8596c-436">보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-436">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8596c-437">**스팸 방지 설정** 페이지에서 ![확장 아이콘](../../media/scc-expand-icon.png)을 클릭하여 삭제하려는 사용자 지정 정책을 확장합니다(**유형** 열은 **사용자 지정 스팸 방지 정책**).</span><span class="sxs-lookup"><span data-stu-id="8596c-437">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="8596c-438">표시되는 확장된 정책 세부 정보에서 **정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-438">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="8596c-439">표시되는 경고 대화 상자에서 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-439">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="8596c-440">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-440">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="8596c-441">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 스팸 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="8596c-441">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="8596c-442">앞서 설명한 것 처럼 스팸 방지 정책은 스팸 필터 정책 및 스팸 필터 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-442">As previously described, an anti-spam policy consists of a spam filter policy and a spam filter rule.</span></span>

<span data-ttu-id="8596c-443">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙 사이의 차이가 명확합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-443">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="8596c-444">**\*-HostedContentFilterPolicy** cmdlet을 사용하여 스팸 필터 정책을 관리하고, **\*-HostedContentFilterRule** cmdlet을 사용하여 스팸 필터 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-444">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="8596c-445">PowerShell에서는 먼저 스팸 필터 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-445">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="8596c-446">PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙의 설정을 따로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-446">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>
- <span data-ttu-id="8596c-447">PowerShell에서 스팸 필터 정책을 제거하면 상응하는 스팸 필터 규칙은 자동으로 제거되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-447">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

<span data-ttu-id="8596c-448">다음 스팸 방지 정책 설정은 PowerShell에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-448">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="8596c-449">기본적으로 `On` 상태인 _MarkAsSpamBulkMail_ 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="8596c-449">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="8596c-450">이 설정의 효과는 이 항목의 앞부분에 있는 [보안 및 준수 센터를 사용하여 스팸 방지 정책 만들기](#use-the-security--compliance-center-to-create-anti-spam-policies) 섹션에서 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-450">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="8596c-451">최종 사용자 스팸 격리 알림을 위한 다음 설정:</span><span class="sxs-lookup"><span data-stu-id="8596c-451">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="8596c-452">_DownloadLink_ 매개 변수는 Outlook용 정크 메일 보고 도구에 대한 링크를 표시하거나 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-452">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="8596c-453">_EndUserSpamNotificationCustomSubject_ 매개 변수는 알림의 제목 줄을 사용자 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-453">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="8596c-454">PowerShell을 사용하여 스팸 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8596c-454">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="8596c-455">PowerShell에서 스팸 방지 정책을 만드는 작업은 2단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-455">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="8596c-456">스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-456">Create the spam filter policy.</span></span>
2. <span data-ttu-id="8596c-457">규칙이 적용되는 스팸 필터 정책을 지정하는 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-457">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="8596c-458">**참고:**</span><span class="sxs-lookup"><span data-stu-id="8596c-458">**Notes**:</span></span>

- <span data-ttu-id="8596c-459">새 스팸 필터 규칙을 만들어 연결되지 않은 기존 스팸 필터 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-459">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="8596c-460">스팸 필터 규칙은 둘 이상의 스팸 필터 정책에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-460">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="8596c-461">정책을 만들 때까지 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-461">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="8596c-462">비활성화된 새 정책을 만듭니다(**New-HostedContentFilterRule** cmdlet에서 `$false`를 _Enabled_).</span><span class="sxs-lookup"><span data-stu-id="8596c-462">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="8596c-463">**New-HostedContentFilterRule** cmdlet에서 정책을 만드는 동안 우선 순위(_우선 순위_ _\<Number\>_)를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-463">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="8596c-464">스팸 필터 규칙에 정책을 할당할 때까지 PowerShell에서 만든 새로운 스팸 필터 정책은 보안 및 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-464">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="8596c-465">1단계: PowerShell을 사용하여 스팸 필터 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8596c-465">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="8596c-466">스팸 필터 정책을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-466">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="8596c-467">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 정책을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-467">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="8596c-468">스팸 필터링 결과가 스팸이거나 높은 정확도의 스팸인 경우 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-468">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="8596c-469">BCL 6은 대량 전자 메일 스팸 필터링 결과 작업을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-469">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="8596c-470">**New-Set-hostedcontentfilterpolicy** 및 **Set-Set-hostedcontentfilterpolicy** 에는 이전 _ZapEnabled_ 매개 변수와 최신 _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-470">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="8596c-471">_ZapEnabled_ 매개 변수는 2020년 2월부터 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-471">The _ZapEnabled_ parameter was deprecated in February 2020.</span></span> <span data-ttu-id="8596c-472">_PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수는 _ZapEnabled_ 매개 변수에서 값을 상속하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-472">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="8596c-473">그러나 명령에 _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수를 사용하거나 보안 및 준수 센터의 스팸 방지 정책에서 **Spam ZAP** 또는 **Phish ZAP** 설정을 사용하는 경우, _ZapEnabled_ 매개 변수의 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-473">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="8596c-474">즉, _ZapEnabled_ 매개 변수를 사용하지 않도록 하세요. _PhishZapEnabled_ 및 _SpamZapEnabled_ 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-474">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="8596c-475">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-475">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="8596c-476">2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="8596c-476">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="8596c-477">스팸 필터 규칙을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-477">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="8596c-478">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 규칙을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-478">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="8596c-479">Contoso Executives라는 스팸 필터 정책은 규칙과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-479">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="8596c-480">이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-480">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="8596c-481">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-481">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="8596c-482">PowerShell을 사용하여 스팸 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="8596c-482">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="8596c-483">모든 스팸 필터 정책의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-483">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="8596c-484">특정 스팸 필터 정책에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-484">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="8596c-485">다음은 Executives라는 스팸 필터 정책의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-485">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="8596c-486">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-486">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="8596c-487">PowerShell을 사용하여 스팸 필터 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="8596c-487">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="8596c-488">기존 스팸 필터 규칙을 보려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-488">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="8596c-489">모든 스팸 필터 규칙의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-489">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="8596c-490">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-490">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="8596c-491">특정 스팸 필터 규칙에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-491">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="8596c-492">다음은 Contoso Executives라는 스팸 필터 규칙의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-492">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="8596c-493">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-493">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="8596c-494">PowerShell을 사용하여 스팸 필터 정책 수정하기</span><span class="sxs-lookup"><span data-stu-id="8596c-494">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="8596c-495">다음과 같은 항목 외에 PowerShell에서 스팸 필터 정책을 수정할 때 이 항목 앞부분의 [1단계 : PowerShell을 사용하여 스팸 필터 정책 만들기](#step-1-use-powershell-to-create-a-spam-filter-policy) 섹션에 설명된 대로 정책을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-495">Other than the following items, the same settings are available when you modify a spam filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="8596c-496">지정된 정책을 기본 정책으로 바꾸는 _MakeDefault_ 스위치(모든 사용자에게 적용, 항상 우선순위가 **가장 낮으며** 삭제할 수 없음)는 PowerShell에서 스팸 필터 정책을 수정할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-496">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="8596c-497">스팸 필터 정책 이름을 바꿀 수 없습니다(**Set-HostedContentFilterPolicy** cmdlet에 _Name_ 매개 변수가 없음).</span><span class="sxs-lookup"><span data-stu-id="8596c-497">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="8596c-498">보안 및 준수 센터에서 스팸 방지 정책의 이름을 바꿀 경우 스팸 필터 _규칙_ 이름만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-498">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="8596c-499">스팸 필터 정책을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-499">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="8596c-500">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-500">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="8596c-501">PowerShell을 사용하여 스팸 필터 규칙 수정하기</span><span class="sxs-lookup"><span data-stu-id="8596c-501">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="8596c-502">PowerShell에서 스팸 필터 규칙을 수정할 때 사용할 수 없는 유일한 설정은 비활성화된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-502">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="8596c-503">기존 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-503">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="8596c-504">그렇지 않으면 PowerShell에서 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-504">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="8596c-505">이 항목 앞부분의 [2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기](#step-2-use-powershell-to-create-a-spam-filter-rule) 섹션에 설명된 대로 규칙을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-505">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="8596c-506">스팸 필터 규칙을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-506">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="8596c-507">다음은 보안 및 준수 센터에서 문제를 일으킬 수 있는 `{Fabrikam Spam Filter}`(이)라는 기존 스팸 필터 규칙의 이름을 바꾸는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-507">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="8596c-508">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-508">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="8596c-509">PowerShell을 사용하여 스팸 필터 규칙 활성화 또는 비활성화하기</span><span class="sxs-lookup"><span data-stu-id="8596c-509">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="8596c-510">PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하면 전체 스팸 방지 정책(스팸 필터 규칙과 할당된 스팸 필터 정책)을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-510">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="8596c-511">기본 스팸 방지 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됨).</span><span class="sxs-lookup"><span data-stu-id="8596c-511">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="8596c-512">PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-512">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="8596c-513">다음은 Marketing Department라는 스팸 필터 규칙을 사용하지 않도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-513">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="8596c-514">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-514">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="8596c-515">자세한 구문 및 매개 변수 정보는 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule)과 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-515">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="8596c-516">PowerShell을 사용하여 스팸 필터 규칙의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="8596c-516">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="8596c-517">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-517">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="8596c-518">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-518">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="8596c-519">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-519">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="8596c-520">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-520">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="8596c-521">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-521">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="8596c-522">PowerShell에서 스팸 필터 규칙의 우선순위를 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-522">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="8596c-523">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-523">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="8596c-524">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="8596c-524">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="8596c-525">**참고:**</span><span class="sxs-lookup"><span data-stu-id="8596c-525">**Notes**:</span></span>

- <span data-ttu-id="8596c-526">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-HostedContentFilterRule** cmdlet에서 _우선순위_ 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-526">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="8596c-527">기본 스팸 필터 정책에는 상응하는 스팸 필터 규칙이 없으며 항상 수정할 수 없는 **가장 낮은** 우선순위 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-527">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="8596c-528">PowerShell을 사용하여 스팸 필터 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="8596c-528">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="8596c-529">PowerShell을 사용하여 스팸 필터 정책을 제거할 때 상응하는 스팸 필터 규칙은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-529">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="8596c-530">PowerShell에서 스팸 필터 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-530">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="8596c-531">다음은 Marketing Department라는 스팸 필터 정책을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-531">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="8596c-532">자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-532">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="8596c-533">PowerShell을 사용하여 스팸 필터 규칙 제거하기</span><span class="sxs-lookup"><span data-stu-id="8596c-533">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="8596c-534">PowerShell을 사용하여 스팸 필터 규칙을 제거할 때 상응하는 스팸 필터 정책은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-534">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="8596c-535">PowerShell에서 스팸 필터 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-535">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="8596c-536">다음은 Marketing Department라는 스팸 필터 규칙을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-536">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="8596c-537">자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8596c-537">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8596c-538">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="8596c-538">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="8596c-539">GTUBE 메시지를 보내서 스팸 정책 설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-539">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="8596c-540">이 단계는 GTUBE 메시지를 보내는 전자 메일 조직이 아웃바운드 스팸을 검사하지 않는 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-540">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="8596c-541">검사하는 경우에는 테스트 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-541">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="8596c-542">GTUBE(원치 않는 대량 전자 메일용 제네릭 테스트)는 조직에서 스팸 방지 설정을 확인하기 위해 테스트 메시지에 포함하는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-542">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="8596c-543">GTUBE 메시지는 맬웨어 설정을 테스트하기 위한 EICAR(European Institute for Computer Antivirus Research) 텍스트 파일과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-543">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="8596c-544">공백이나 줄 바꿈 없이 다음 GTUBE 텍스트를 전자 메일 메시지의 한 줄에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-544">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="8596c-545">허용/차단 목록</span><span class="sxs-lookup"><span data-stu-id="8596c-545">Allow/Block Lists</span></span>

<span data-ttu-id="8596c-546">필터가 메시지를 빠뜨리거나 시스템에서 메시지를 확인하는 데 시간이 걸리는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-546">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="8596c-547">이 경우 스팸 방지 정책에는 현재 결과를 재정의 하는데 사용 할 수 있는 허용 및 차단 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-547">In this cases, the anti-spam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="8596c-548">수행할 작업이 필터링 스택에서 수행되고 있어야 하므로 목록을 관리할 수 없고 일시적이기 때문에 이 옵션은 드물게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-548">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="8596c-549">조직이 서비스에서 제공하는 결과에 동의하지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-549">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="8596c-550">이 경우 허용 또는 차단 목록을 영구적으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-550">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="8596c-551">하지만 도메인을 허용 목록에 오래 동안 유지할 경우 보낸 사람에게 도메인을 인증하는지 확인하고, 확인하지 않을 경우 DMARC 거부로 설정하도록 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8596c-551">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
