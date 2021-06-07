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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online Protection(EOP)에서 스팸 방지 정책을 보고, 만들고 수정하고 삭제하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a272e78e05f86a8f9f918c873e9fb1a85f863bfc
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793103"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="189d7-103">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="189d7-103">Configure anti-spam policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="189d7-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="189d7-104">**Applies to**</span></span>
- [<span data-ttu-id="189d7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="189d7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="189d7-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="189d7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="189d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="189d7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="189d7-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 경우, 인바운드 전자 메일 메시지가 EOP를 통해 자동으로 스팸으로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="189d7-109">EOP는 스팸에 대한 조직의 전반적인 방어책의 일부로 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-109">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="189d7-110">자세한 내용은 [스팸 방지 보호](anti-spam-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-110">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="189d7-p102">관리자는 기본 스팸 방지 정책을 보고, 편집하고, 구성할 수 있습니다(삭제는 할 수 없음). 세분성을 높이기 위해 사용자 지정 스팸 방지 정책을 만들어 조직의 특정 사용자, 그룹 또는 도메인에 적용할 수도 있습니다. 사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-p102">Admins can view, edit, and configure (but not delete) the default anti-spam policy. For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization. Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="189d7-114">Microsoft 365 보안 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online PowerShell; Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 스팸 방지 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-114">You can configure anti-spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="189d7-115">스팸 방지 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-115">The basic elements of an anti-spam policy are:</span></span>

- <span data-ttu-id="189d7-116">**스팸 필터 정책**: 스팸 필터링 결과와 알림 옵션에 대한 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-116">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="189d7-117">**스팸 필터 규칙**: 스팸 필터 정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-117">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="189d7-118">보안 센터에서 스팸 방지 정책을 관리하면, 두 가지 요소의 차이는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-118">The difference between these two elements isn't obvious when you manage anti-spam polices in the security center:</span></span>

- <span data-ttu-id="189d7-119">스팸 방지 정책을 만드는 경우에는 사용자가 같은 이름을 사용하여 동시에 스팸 필터 규칙과 관련 스팸 필터 정책을 작성하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-119">When you create an anti-spam policy, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="189d7-120">스팸 방지 정책을 수정하는 경우, 이름, 우선 순위, 사용 또는 사용 안 함 및 받는 사람 필터와 관련된 설정은 스팸 필터 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-120">When you modify an anti-spam policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="189d7-121">다른 모든 설정은 관련 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-121">All other settings modify the associated spam filter policy.</span></span>
- <span data-ttu-id="189d7-122">스팸 방지 정책을 제거하면, 스팸 필터 규칙과 관련 스팸 필터 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-122">When you remove an anti-spam policy, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="189d7-123">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-123">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="189d7-124">자세한 내용은 이 문서의 뒷부분에 나오는 [Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 스팸 방지 정책 구성](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-124">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) section later in this article.</span></span>

<span data-ttu-id="189d7-125">모든 조직에는 다음과 같은 속성을 포함하는 기본 제공되는 Default 스팸 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-125">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="189d7-126">정책과 연결된 스팸 필터 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 스팸 필터 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-126">The policy is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="189d7-127">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="189d7-127">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="189d7-128">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-128">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="189d7-129">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-129">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="189d7-130">스팸 필터링의 효율성을 높이려면 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 스팸 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-130">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="189d7-131">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="189d7-131">What do you need to know before you begin?</span></span>

- <span data-ttu-id="189d7-132"><https://security.microsoft.com/>에서 보안 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-132">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="189d7-133">**스팸 방지 정책** 페이지로 직접 이동하려면 <https://security.microsoft.com/antispam>을(를) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-133">To go directly to the **Anti-spam policies** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="189d7-134">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-134">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="189d7-135">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-135">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="189d7-136">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-136">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="189d7-137">스팸 방지 정책을 추가, 수정 및 삭제하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-137">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="189d7-138">스팸 방지 정책에 대한 읽기 전용 액세스를 위해서는 **전체 읽기 권한자** 또는 **보안 읽기 권한자** 역할 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-138">For read-only access to anti-spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="189d7-139">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-139">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="189d7-140">**참고**:</span><span class="sxs-lookup"><span data-stu-id="189d7-140">**Notes**:</span></span>

  - <span data-ttu-id="189d7-141">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-141">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="189d7-142">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-142">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="189d7-143">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-143">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="189d7-144">스팸 방지 정책에 대한 권장 설정은 [EOP 스팸 방지 정책 설정](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-144">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security-center-to-create-anti-spam-policies"></a><span data-ttu-id="189d7-145">보안 센터를 사용하여 스팸 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="189d7-145">Use the security center to create anti-spam policies</span></span>

<span data-ttu-id="189d7-146">보안 센터에서 사용자 지정 스팸 방지 정책을 만들면, 같은 이름을 사용하여 스팸 필터 규칙과 관련된 스팸 필터 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-146">Creating a custom anti-spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="189d7-147">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-147">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="189d7-148">**스팸 방지 정책** 페이지에서 ![아이콘 만들기](../../media/m365-cc-sc-create-icon.png) **정책 만들기** 를 클릭한 다음 드롭다운 목록에서 **인바운드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-148">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Inbound** from the drop down list.</span></span>

3. <span data-ttu-id="189d7-149">정책 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-149">The policy wizard opens.</span></span> <span data-ttu-id="189d7-150">**정책 이름 페이지** 에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-150">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="189d7-151">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="189d7-152">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="189d7-153">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="189d7-154">표시되는 **사용자, 그룹 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람(받는 사람 조건)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="189d7-155">**사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="189d7-156">**그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="189d7-157">**도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="189d7-158">적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="189d7-159">이 프로세스를 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="189d7-160">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-160">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="189d7-162">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-162">next to the value.</span></span>

   <span data-ttu-id="189d7-163">사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="189d7-164">사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="189d7-165">동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="189d7-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="189d7-166">서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="189d7-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="189d7-167">**다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="189d7-168">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="189d7-169">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="189d7-170">표시되는 **대량 전자 메일 임계값 및 스팸 속성** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-170">On the **Bulk email threshold & spam properties** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="189d7-171">**대량 메일 임계값**: 다음 페이지에서 구성하는 **대량 전자 메일** 스팸 필터링 결과(지정된 값 이상, 이하 혹은 같음)에 지정된 작업을 트리거하는 메시지의 BCL(대량 불만 수준)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-171">**Bulk email threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk** spam filtering verdict that you configure on the next page (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="189d7-172">값이 높을수록 메시지가 덜 바람직함을 나타냅니다(스팸과 유사할 가능성 높음).</span><span class="sxs-lookup"><span data-stu-id="189d7-172">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="189d7-173">기본값은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-173">The default value is 7.</span></span> <span data-ttu-id="189d7-174">자세한 내용은 [EOP에서의 BCL(대량 불만 수준)](bulk-complaint-level-values.md) 및 [정크 메일과 대량 전자 메일의 차이점](what-s-the-difference-between-junk-email-and-bulk-email.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-174">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="189d7-175">기본적으로 PowerShell 전용 설정 _MarkAsSpamBulkMail_ 은 스팸 방지 정책에서 `On` 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-175">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="189d7-176">이 설정은 **대량** 필터링 결과의 결과에 크게 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-176">This setting dramatically affects the results of a **Bulk** filtering verdict:</span></span>

     - <span data-ttu-id="189d7-177">**_MarkAsSpamBulkMail_ 이 켜짐**: 임곗값보다 큰 BCL은 **스팸** 필터링 결과에 해당하는 SCL 6으로 변환되고, 메시지에 대한 **대량** 필터링 결과에 대한 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-177">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk** filtering verdict is taken on the message.</span></span>
     - <span data-ttu-id="189d7-178">**_MarkAsSpamBulkMail_ 이 꺼짐**: 메시지에는 BCL이 찍히지만 **대량** 필터링 결과에 대해 수행되는 _작업은 없습니다._</span><span class="sxs-lookup"><span data-stu-id="189d7-178">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk** filtering verdict.</span></span> <span data-ttu-id="189d7-179">실제로 BCL 임곗값과 **대량** 필터링 결과 작업은 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-179">In effect, the BCL threshold and **Bulk** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="189d7-180">**스팸 점수 증가**, **스팸으로 표시**<sup>\*</sup>및 **테스트 모드**: 기본적으로 꺼져있는 고급 스팸 필터(ASF) 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-180">**Increase spam score**, **Mark as spam**<sup>\*</sup> and **Test mode**: Contains the Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="189d7-181">ASF 설정은 더 이상 사용되지 않으며, 해당 기능은 필터링 스택의 다른 부분에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-181">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="189d7-182">모든 ASF 설정을 스팸 방지 정책에서 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-182">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

     <span data-ttu-id="189d7-183">이러한 설정에 대한 자세한 내용은 [EOP에서 고급 스팸 필터 설정](advanced-spam-filtering-asf-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-183">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

      <span data-ttu-id="189d7-184"><sup>\*</sup> **특정 언어** 를 포함하며 **이러한 국가에서** 는 ASF 설정의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-184"><sup>\*</sup> **Contains specific languages** and **from these countries** are not part of ASF settings.</span></span>

   - <span data-ttu-id="189d7-185">**특정 언어 포함**: 상자를 클릭하고 선택하거나 드롭다운 목록에서 **켜짐** 또는 **꺼짐** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-185">**Contains specific languages**: Click the box and select **On** or **Off** from the drop down list.</span></span> <span data-ttu-id="189d7-186">이 기능을 켜면 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-186">If you turn it on, a box appears.</span></span> <span data-ttu-id="189d7-187">상자에 언어 이름을 입력하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-187">Start typing the name of a language in the box.</span></span> <span data-ttu-id="189d7-188">지원되는 언어의 필터링된 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-188">A filtered list of supported languages will appear.</span></span> <span data-ttu-id="189d7-189">원하는 언어를 찾았으면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-189">When you find the language that you're looking for, select it.</span></span> <span data-ttu-id="189d7-190">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="189d7-191">기존 값을 제거하려면 값 옆에 있는 제거 ![제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-191">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   - <span data-ttu-id="189d7-192">**이러한 국가에서** _: 상자를 클릭하고 드롭다운 목록에서 _ *켜기*\* 또는 **끄기** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-192">**From these countries** _: Click the box and select _ *On*\* or **Off** from the drop down list.</span></span> <span data-ttu-id="189d7-193">이 기능을 켜면 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-193">If you turn it on, a box appears.</span></span> <span data-ttu-id="189d7-194">상자에 국가 이름을 입력하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-194">Start typing the name of a country in the box.</span></span> <span data-ttu-id="189d7-195">지원되는 국가의 필터링된 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-195">A filtered list of supported countries will appear.</span></span> <span data-ttu-id="189d7-196">원하는 국가를 찾으면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-196">When you find the country that you're looking for, select it.</span></span> <span data-ttu-id="189d7-197">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="189d7-198">기존 값을 제거하려면 값 옆에 있는 제거 ![제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-198">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   <span data-ttu-id="189d7-199">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-199">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="189d7-200">표시되는 **작업** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-200">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="189d7-201">**메시지 작업**: 다음 스팸 필터링 결과에 따라 메시지에 대해 수행할 작업을 선택하거나 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-201">**Message actions**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>
     - <span data-ttu-id="189d7-202">**스팸**</span><span class="sxs-lookup"><span data-stu-id="189d7-202">**Spam**</span></span>
     - <span data-ttu-id="189d7-203">**높은 정확도의 스팸**</span><span class="sxs-lookup"><span data-stu-id="189d7-203">**High confidence spam**</span></span>
     - <span data-ttu-id="189d7-204">**피싱**</span><span class="sxs-lookup"><span data-stu-id="189d7-204">**Phishing**</span></span>
     - <span data-ttu-id="189d7-205">**높은 정확도 피싱**</span><span class="sxs-lookup"><span data-stu-id="189d7-205">**High confidence phishing**</span></span>
     - <span data-ttu-id="189d7-206">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="189d7-206">**Bulk**</span></span>

     <span data-ttu-id="189d7-207">스팸 필터링 결과에 사용 가능한 작업은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-207">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="189d7-208">확인 표시(</span><span class="sxs-lookup"><span data-stu-id="189d7-208">A check mark (</span></span> ![확인 표시](../../media/checkmark.png)<span data-ttu-id="189d7-210">) 작업을 사용할 수 있음을 의미합니다(모든 결과에 모든 작업을 사용할 수 있는 것은 아님).</span><span class="sxs-lookup"><span data-stu-id="189d7-210">) indicates the action is available (not all actions are available for all verdicts).</span></span>
     - <span data-ttu-id="189d7-211">확인 표시 후 별표(<sup>\*</sup>)는 스팸 필터링 결과에 대한 기본 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-211">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     <br>

     ****

     |<span data-ttu-id="189d7-212">조치</span><span class="sxs-lookup"><span data-stu-id="189d7-212">Action</span></span>|<span data-ttu-id="189d7-213">스팸</span><span class="sxs-lookup"><span data-stu-id="189d7-213">Spam</span></span>|<span data-ttu-id="189d7-214">높음</span><span class="sxs-lookup"><span data-stu-id="189d7-214">High</span></span><br><span data-ttu-id="189d7-215">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="189d7-215">confidence</span></span><br><span data-ttu-id="189d7-216">스팸</span><span class="sxs-lookup"><span data-stu-id="189d7-216">spam</span></span>|<span data-ttu-id="189d7-217">피싱</span><span class="sxs-lookup"><span data-stu-id="189d7-217">Phishing</span></span>|<span data-ttu-id="189d7-218">높음</span><span class="sxs-lookup"><span data-stu-id="189d7-218">High</span></span><br><span data-ttu-id="189d7-219">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="189d7-219">confidence</span></span><br><span data-ttu-id="189d7-220">피싱</span><span class="sxs-lookup"><span data-stu-id="189d7-220">phishing</span></span>|<span data-ttu-id="189d7-221">대량</span><span class="sxs-lookup"><span data-stu-id="189d7-221">Bulk</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="189d7-222">**정크 메일 폴더로 메시지 이동**: 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-222">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="189d7-223">![확인 표시](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-223">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="189d7-224">![확인 표시](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-224">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|<span data-ttu-id="189d7-227">![확인 표시](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-227">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="189d7-228">**X-헤더 추가**: 메시지 헤더에 X-헤더를 추가하고, 메시지를 사서함에 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-228">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <p> <span data-ttu-id="189d7-229">나중에 **이 X-헤더 텍스트를 추가** 상자에서 X-헤더 필드 이름(값 아님)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-229">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <p> <span data-ttu-id="189d7-230">**스팸** 및 **높은 정확도의 스팸** 결과의 경우, 메시지가 정크 메일 폴더로 이동됩니다.<sup>1, 2</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-230">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||<span data-ttu-id="189d7-234">![확인 표시](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-234">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="189d7-235">**텍스트를 제목 줄 앞에 추가**: 메시지의 제목 줄 앞에 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-235">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="189d7-236">메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.<sup>1,2</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-236">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <p> <span data-ttu-id="189d7-237">**이 텍스트를 제목 줄 앞에 추가** 상자에 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-237">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
     |<span data-ttu-id="189d7-242">**전자 메일 주소로 메시지 리디렉션**: 메시지를 의도된 받는 사람 대신 다른 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-242">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <p> <span data-ttu-id="189d7-243">나중에 **이 전자 메일 주소로 메시지 리디렉션** 상자에 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-243">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
     |<span data-ttu-id="189d7-249">**메시지 삭제**: 모든 첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-249">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
     |<span data-ttu-id="189d7-254">**메시지 격리**: 메시지를 의도된 받는 사람에게 보내는 대신 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-254">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <p> <span data-ttu-id="189d7-255">나중에 **격리** 상자에 메시지가 격리되는 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-255">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|<span data-ttu-id="189d7-258">![확인 표시](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="189d7-258">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
     |<span data-ttu-id="189d7-261">**작업 없음**</span><span class="sxs-lookup"><span data-stu-id="189d7-261">**No action**</span></span>|||||![확인 표시](../../media/checkmark.png)|
     |

     > <span data-ttu-id="189d7-263"><sup>1</sup> Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있으면 메시지는 정크 메일 폴더로 이동합니다(기본적으로 활성화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="189d7-263"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="189d7-264">자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-264">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="189d7-265">EOP로 온-프레미스 Exchange 사서함을 보호하는 하이브리드 환경에서는 EOP 스팸 필터링 평가 결과를 변환하여 정크 메일 규칙에 따라 메시지를 정크 메일 폴더로 이동하기 위해 온-프레미스 Exchange에서 메일 흐름 규칙(전송 규칙이라고도 함)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-265">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="189d7-266">자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 EOP 구성하기](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-266">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span>
     >
     > <span data-ttu-id="189d7-267"><sup>2</sup> 메일 흐름 규칙에서 해당 값을 조건으로 사용하여 메시지를 필터링하거나 경로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-267"><sup>2</sup> You can this use value as a condition in mail flow rules to filter or route the message.</span></span>

   - <span data-ttu-id="189d7-268">**이 많은 일수 동안 스팸을 격리 상태로 유지**: 스팸 필터링 결과에 대한 작업으로 **메시지 격리** 를 선택한 경우, 메시지를 격리할 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-268">**Retain spam in quarantine for this many days**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="189d7-269">격리 기간이 만료되면 메시지가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-269">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="189d7-270">기본값은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-270">The default value is 30 days.</span></span> <span data-ttu-id="189d7-271">유효한 값은 1~30일입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-271">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="189d7-272">격리에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-272">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="189d7-273">EOP에서 격리된 메시지</span><span class="sxs-lookup"><span data-stu-id="189d7-273">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="189d7-274">EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기</span><span class="sxs-lookup"><span data-stu-id="189d7-274">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="189d7-275">EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기</span><span class="sxs-lookup"><span data-stu-id="189d7-275">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="189d7-276">**이 X-헤더 텍스트 추가**: 이 상자는 필수이며, **X-헤더 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-276">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="189d7-277">사용자가 지정하는 값은 메시지 헤더에 추가되는 헤더 필드 *이름* 입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-277">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="189d7-278">헤더 필드 *값* 은 항상 `This message appears to be spam`입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-278">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="189d7-279">최대 길이는 255자이며, 값에는 공백이나 콜론(:)이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-279">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="189d7-280">예를 들어 값 `X-This-is-my-custom-header`을(를) 입력하면 메시지에 추가되는 X-헤더는 `X-This-is-my-custom-header: This message appears to be spam.`입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-280">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="189d7-281">공백이나 콜론(:)을 포함하는 값을 입력하면 입력하는 값이 무시되고, 기본 X 머리글이 메시지(`X-This-Is-Spam: This message appears to be spam.`)에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-281">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="189d7-282">**이 텍스트를 제목 줄 앞에 추가**: 이 상자는 필수이며, **텍스트를 제목 줄 앞에 추가** 를 스팸 필터링 결과 작업으로 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-282">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="189d7-283">메시지의 제목 줄의 시작 부분에 추가할 텍스트를 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-283">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="189d7-284">**이 전자 메일 주소로 리디렉션**: 이 상자는 필수이며, 스팸 필터링 결과 작업으로 **메시지를 전자 메일 주소로 리디렉션** 을 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-284">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="189d7-285">메시지를 배달하려는 전자 메일 주소를 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-285">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="189d7-286">세미콜론(;)으로 구분하여 여러 값을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-286">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="189d7-287">**보안 팁 사용**: 기본적으로 보안 팁은 활성화되어 있지만, 확인란을 선택 취소하여 이 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-287">**Enable safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the checkbox.</span></span> <span data-ttu-id="189d7-288">보안 팁에 대한 자세한 내용은 [전자 메일 메시지 보안 팁](safety-tips-in-office-365.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-288">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   - <span data-ttu-id="189d7-289">**제로 아워 자동 제거(ZAP) 사용**: ZAP는 Exchange Online 사서함에 이미 배달된 메시지를 검색하여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-289">**Enable zero-hour auto purge (ZAP)**: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="189d7-290">자세한 내용은 [제로 아워 자동 제거 - 스팸 및 맬웨어로부터 보호](zero-hour-auto-purge.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-290">For more information, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

     <span data-ttu-id="189d7-291">ZAP는 기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-291">ZAP is turned on by default.</span></span> <span data-ttu-id="189d7-292">ZAP가 켜져 있으면 다음 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-292">When ZAP is turned on, the following settings are available:</span></span>

     - <span data-ttu-id="189d7-293">**피싱 메시지에 대한 ZAP 사용**: 기본적으로 ZAP는 피싱 검색에 대해 사용하도록 설정되지만 확인란의 선택을 취소하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-293">**Enable ZAP for phishing messages**: By default, ZAP is enabled for phishing detections, but you can disable it by clearing the checkbox.</span></span>
     - <span data-ttu-id="189d7-294">**스팸 메시지에 대한 ZAP 사용**: 기본적으로 ZAP는 스팸 검색에 대해 사용하도록 설정되지만 확인란의 선택을 취소하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-294">**Enable ZAP for spam messages**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the checkbox.</span></span>

   - <span data-ttu-id="189d7-295">**최종 사용자 스팸 알림 사용**: 자세한 내용은 이 항목의 뒷부분에 있는 [최종 사용자 스팸 알림 구성](#configure-end-user-spam-notifications) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-295">**Enable end-user spam notifications**: For more information, see the [Configure end-user spam notifications](#configure-end-user-spam-notifications) section later in this topic.</span></span>

   <span data-ttu-id="189d7-296">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-296">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="189d7-297">표시되는 **허용 및 차단 목록** 플라이아웃에서 스팸 필터링을 건너뛸 수 있는 전자 메일 주소 또는 전자 메일 도메인별로 메시지 보낸 사람을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-297">On the **Allow & block list** flyout that appears, you are able to configure message senders by email address or email domain that are allowed to skip spam filtering.</span></span>

   <span data-ttu-id="189d7-298">**허용** 섹션에서 허용된 보낸 사람 및 허용된 도메인을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-298">In the **Allowed** section, you can configure allowed senders and allowed domains.</span></span> <span data-ttu-id="189d7-299">**차단된** 섹션에서 차단된 보낸 사람 및 차단된 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-299">In the **Blocked** section, you can add blocked senders and blocked domains.</span></span>

   > [!IMPORTANT]
   >
   > <span data-ttu-id="189d7-300">허용된 도메인 목록에 도메인을 추가하기 전에 신중하게 생각하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-300">Think very carefully before you add domains to the allowed domains list.</span></span> <span data-ttu-id="189d7-301">자세한 내용은 [EOP에서 안전한 보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-301">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > <span data-ttu-id="189d7-302">자신의 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 또는 공통 도메인(예: microsoft.com 또는 office.com)을 허용된 도메인 목록에 추가하지 않도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-302">Never add your own [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="189d7-303">이러한 도메인이 스팸 필터링을 우회할 수 있는 경우 공격자가 조직으로 이메일을 쉽게 보낼 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-303">If these domains are allowed to bypass spam filtering, allow attackers an easily send email into your organization.</span></span>
   >
   > <span data-ttu-id="189d7-304">차단된 도메인 목록에 도메인을 추가하여 수동으로 도메인을 차단하는 것은 위험하지 않지만, 관리 작업 부하가 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-304">Manually blocking domains by adding the domains to the blocked domains list isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="189d7-305">자세한 내용은 [EOP에서 차단할 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-305">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>
   >
   > <span data-ttu-id="189d7-306">필터가 메시지를 빠뜨리거나 필터링 평가에 동의하지 않거나 시스템에서 메시지를 확인하는 데 시간이 걸리는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-306">There will be times when our filters will miss a message, you don't agree with the filtering verdict, or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="189d7-307">이러한 경우 허용 목록 및 차단 목록을 사용하여 현재 필터링 결과를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-307">In these cases, the allow list and block list are available to override the current filtering verdicts.</span></span> <span data-ttu-id="189d7-308">그러나 이러한 목록은 일시적으로 사용해야 합니다. longs 목록은 관리할 수 없게 될 수 있으며 필터링 스택은 예상되는 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-308">But, you should use these lists sparingly and temporarily: longs lists can become unmanageable, and our filtering stack should be doing what it's supposed to be doing.</span></span> <span data-ttu-id="189d7-309">허용된 도메인을 오랫동안 유지하려는 경우 보낸 사람에게 도메인이 인증되었는지 확인하고 도메인이 인증되지 않은 경우 DMARC 거부로 설정하도록 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-309">If you're going to keep an allowed domain for an extended period of time, you should tell the sender to verify that their domain is authenticated and set to DMARC reject if it's not.</span></span>

   <span data-ttu-id="189d7-310">목록에 항목을 추가하는 단계는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-310">The steps to add entries to any of the lists are the same:</span></span>

   1. <span data-ttu-id="189d7-311">구성할 목록의 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-311">Click the link for the list that you want to configure:</span></span>
      - <span data-ttu-id="189d7-312">**허용된** \> **보낸 사람**: **보낸 사람 관리(nn)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-312">**Allowed** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="189d7-313">**허용된** \> **도메인**: **도메인 허용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-313">**Allowed** \> **Domains**: Click **Allow domains**.</span></span>
      - <span data-ttu-id="189d7-314">**차단된** \> **보낸 사람**: **보낸 사람 관리(nn)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-314">**Blocked** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="189d7-315">**차단된** \> **도메인**: **도메인 차단** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-315">**Blocked** \> **Domains**: Click **Block domains**.</span></span>

   2. <span data-ttu-id="189d7-316">표시되는 플라이아웃에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-316">In the flyout that appears, do the following steps:</span></span>
      1. <span data-ttu-id="189d7-317">![아이콘 만들기](../../media/m365-cc-sc-create-icon.png) **보낸 사람 추가** 또는 **도메인 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-317">Click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Add senders** or **Add domains**.</span></span>
      2. <span data-ttu-id="189d7-318">표시되는 **보낸 사람 추가** 또는 **도메인 추가** 플라이아웃에서 보낸 사람의 전자 메일 주소를 **보낸 사람** 상자에 입력하거나 **도메인** 상자에 도메인을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-318">In the **Add senders** or **Add domains** flyout that appears, enter the sender's email address in the **Sender** box or the domain in the **Domain** box.</span></span> <span data-ttu-id="189d7-319">입력할 때 값이 상자 아래에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-319">As you're typing, the value appears below the box.</span></span> <span data-ttu-id="189d7-320">전자 메일 주소 또는 도메인 입력을 마쳤으면 상자 아래의 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-320">When you're finished typing the email address or domain, select the value below the box.</span></span>
      3. <span data-ttu-id="189d7-321">이전 단계를 필요한 횟수만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-321">Repeat the previous step as many times as necessary.</span></span> <span data-ttu-id="189d7-322">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-322">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="189d7-324">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-324">next to the value.</span></span>

      <span data-ttu-id="189d7-325">완료되면 **보낸 사람 추가** 또는 **도메인 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-325">When you're finished, click **Add senders** or **Add domains**.</span></span>

      <span data-ttu-id="189d7-326">기본 플라이아웃으로 돌아가서 추가한 보낸 사람 또는 도메인이 페이지에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-326">Back on the main flyout, the senders or domains that you added are listed on the page.</span></span> <span data-ttu-id="189d7-327">이 페이지에서 항목을 제거하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-327">To remove an entry from this page, do the following steps:</span></span>

      1. <span data-ttu-id="189d7-328">목록에서 하나 이상의 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-328">Select one or more entries from the list.</span></span> <span data-ttu-id="189d7-329">**검색** 상자를 사용하여 목록에서 값을 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-329">You can also use the **Search** box to find values in the list.</span></span>
      2. <span data-ttu-id="189d7-330">항목을 하나 이상 선택한 후 삭제 아이콘</span><span class="sxs-lookup"><span data-stu-id="189d7-330">After you select at least one entry, the delete icon</span></span> ![삭제 아이콘](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="189d7-332">나타납니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-332">appears.</span></span>
      3. <span data-ttu-id="189d7-333">삭제 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-333">Click the delete icon</span></span> ![삭제 아이콘](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="189d7-335">선택한 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-335">to remove the selected entries.</span></span>

      <span data-ttu-id="189d7-336">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-336">When you're finished, click **Done**.</span></span>

      <span data-ttu-id="189d7-337">**허용 및 차단 목록** 페이지로 돌아가서, 읽을 때 **다음** 클릭하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-337">Back on the **Allow & block list** page, click **Next** when you're read to continue.</span></span>

8. <span data-ttu-id="189d7-338">표시되는 **검토** 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-338">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="189d7-339">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-339">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="189d7-340">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-340">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="189d7-341">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-341">When you're finished, click **Create**.</span></span>

9. <span data-ttu-id="189d7-342">표시되는 확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-342">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-spam-policies"></a><span data-ttu-id="189d7-343">보안 센터를 사용하여 스팸 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="189d7-343">Use the security center to view anti-spam policies</span></span>

1. <span data-ttu-id="189d7-344">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-344">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="189d7-345">**스팸 방지 정책** 페이지에서 다음 값 중 하나를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-345">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="189d7-346">**유형** 값은 **사용자 지정 스팸 방지 정책** 입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-346">The **Type** value is **Custom anti-spam policy**</span></span>
   - <span data-ttu-id="189d7-347">**이름** 값은 **스팸 방지 인바운드 정책(기본값)** 입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-347">The **Name** value is **Anti-spam inbound policy (Default)**</span></span>

   <span data-ttu-id="189d7-348">스팸 방지 정책 목록에는 다음 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-348">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="189d7-349">**이름**</span><span class="sxs-lookup"><span data-stu-id="189d7-349">**Name**</span></span>
   - <span data-ttu-id="189d7-350">**상태**</span><span class="sxs-lookup"><span data-stu-id="189d7-350">**Status**</span></span>
   - <span data-ttu-id="189d7-351">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="189d7-351">**Priority**</span></span>
   - <span data-ttu-id="189d7-352">**유형**</span><span class="sxs-lookup"><span data-stu-id="189d7-352">**Type**</span></span>

3. <span data-ttu-id="189d7-353">이름을 클릭하여 스팸 방지 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-353">When you select an anti-spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-spam-policies"></a><span data-ttu-id="189d7-354">보안 센터를 사용하여 스팸 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="189d7-354">Use the security center to modify anti-spam policies</span></span>

1. <span data-ttu-id="189d7-355">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-355">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="189d7-356">**스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 스팸 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-356">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="189d7-357">**유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="189d7-357">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="189d7-358">**스팸 방지 인바운드 정책(기본값)이라는 기본 정책** 입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-358">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="189d7-359">표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-359">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="189d7-360">설정에 대한 자세한 내용은 이 문서의 이전 [보안 센터를 사용하여 스팸 방지 정책](#use-the-security-center-to-create-anti-spam-policies) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-360">For more information about the settings, see the previous [Use the security center to create anti-spam policies](#use-the-security-center-to-create-anti-spam-policies) section in this article.</span></span>

   <span data-ttu-id="189d7-361">기본 스팸 방지 정책의 경우, **적용 대상** 섹션을 사용할 수 없으며(이 정책은 모든 사용자에게 적용됨) 정책의 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-361">For the default anti-spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="189d7-362">정책을 사용하거나 사용하지 않도록 설정하거나, 정책 우선순위 순서를 설정하거나, 최종 사용자 격리 알림을 구성하려면, 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-362">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="189d7-363">스팸 방지 정책 활성화 또는 비활성화하기</span><span class="sxs-lookup"><span data-stu-id="189d7-363">Enable or disable anti-spam policies</span></span>

<span data-ttu-id="189d7-364">기본 스팸 방지 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-364">You can't disable the default anti-spam policy.</span></span>

1. <span data-ttu-id="189d7-365">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-365">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="189d7-366">**스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 **사용자 지정 스팸 방지 정책** **유형 값** 이 있는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-366">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="189d7-367">표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-367">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="189d7-368">**정책 끄기**: 정책을 켜려면 ![켜기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-368">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="189d7-369">**정책**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-369">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="189d7-370">표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-370">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="189d7-371">정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-371">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="189d7-372">기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-372">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="189d7-373">사용자 지정 스팸 방지 정책의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="189d7-373">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="189d7-374">기본적으로 만들어진 순서에 따라 스팸 방지 정책에 우선순위가 지정됩니다(새 정책은 이전 정책 보다 우선순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="189d7-374">By default, anti-spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="189d7-375">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="189d7-375">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="189d7-376">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-376">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="189d7-377">정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(보안 센터에서 **우선 순위** 번호를 직접 수정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="189d7-377">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="189d7-378">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-378">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="189d7-379">**참고**:</span><span class="sxs-lookup"><span data-stu-id="189d7-379">**Notes**:</span></span>

- <span data-ttu-id="189d7-380">보안 센터에서는 스팸 방지 정책을 만든 후에만 우선순위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-380">In the security center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="189d7-381">PowerShell에서 사용자는 기존 규칙의 우선순위에 영향을 줄 수 있는 스팸 필터 규칙을 만들 때 기본 우선순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-381">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="189d7-382">스팸 방지 정책은 표시되는 순서로 처리됩니다(첫 번째 정책에는 **우선순위** 값 0이 표시됨).</span><span class="sxs-lookup"><span data-stu-id="189d7-382">Anti-spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="189d7-383">기본 스팸 방지 정책은 우선순위 값이 **가장 낮음** 이며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-383">The default anti-spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="189d7-384">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-384">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="189d7-385">**스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 **사용자 지정 스팸 방지 정책** **유형 값** 이 있는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-385">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="189d7-386">표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-386">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="189d7-387">**우선 순위** 값이 **0** 인 스팸 방지 정책에는 **우선 순위** 감소 옵션만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-387">The anti-spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="189d7-388">**우선 순위** 값이 가장 낮은 스팸 방지 정책(예: **3**)에는 **우선 순위 증가** 옵션만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-388">The anti-spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="189d7-389">스팸 방지 정책이 세 개 이상 있는 경우 가장 높은 우선 순위 값과 가장 낮은 우선 순위 값 사이의 정책에는 **우선 순위 증가** 및 **우선 순위 감소** 옵션을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-389">If you have three or more anti-spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="189d7-390">![우선순위 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선순위** 또는 ![우선순위 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위** 를 클릭하여 **우선순위** 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-390">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="189d7-391">작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-391">When you're finished, click **Close** in the policy details flyout.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="189d7-392">최종 사용자 스팸 알림 구성하기</span><span class="sxs-lookup"><span data-stu-id="189d7-392">Configure end-user spam notifications</span></span>

<span data-ttu-id="189d7-393">스팸 필터링 결과에서 메시지를 격리하는 경우, 받는 사람에게 전송된 메시지에 일어난 자세한 내용을 알릴 수 있도록 최종 사용자 스팸 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-393">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="189d7-394">이 알림에 대한 자세한 내용은 [EOP에서 최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-394">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="189d7-395">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-395">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="189d7-396">**스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 스팸 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-396">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="189d7-397">**유형** 열의 값이 **사용자 지정 스팸 방지 정책** 인 사용자가 만든 사용자 지정 정책.</span><span class="sxs-lookup"><span data-stu-id="189d7-397">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="189d7-398">**스팸 방지 인바운드 정책(기본값)이라는 기본 정책** 입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-398">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="189d7-399">표시되는 정책 세부 정보 플라이아웃에서 **작업** 섹션에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-399">In the policy details flyout that appears, click **Edit** in the **Actions** section.</span></span> <span data-ttu-id="189d7-400">표시되는 **작업** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-400">In the **Actions** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="189d7-401">**최종 사용자 스팸 알림 사용**: 이 확인란을 선택하여 알림을 사용하도록 설정하거나 확인란의 선택을 취소하여 알림을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-401">**Enable end-user spam notifications**: Select the checkbox to enable notifications or clear the checkbox to disable notifications.</span></span> <span data-ttu-id="189d7-402">확인란을 선택하면 다음과 같은 추가 설정이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-402">When you select the checkbox, the following additional settings appear:</span></span>

     - <span data-ttu-id="189d7-403">**최종 사용자 스팸 알림 보내기 간격(일)**: 알림을 보내는 빈도를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-403">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="189d7-404">기본값은 3일입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-404">The default value is 3 days.</span></span> <span data-ttu-id="189d7-405">1~15일을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-405">You can enter 1 to 15 days.</span></span>

       <span data-ttu-id="189d7-406">24시간 내에 다음 시간에 시작하는 최종 사용자 스팸 알림의 3가지 주기가 있습니다(01:00 UTC, 08:00 UTC 및 16:00 UTC).</span><span class="sxs-lookup"><span data-stu-id="189d7-406">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

       > [!NOTE]
       > <span data-ttu-id="189d7-407">이전 주기 중에 알림이 누락되면 다음 주기가 알림을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-407">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="189d7-408">이로 인해 당일에 여러 알림이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-408">This might give the appearance of multiple notifications within the same day.</span></span>

     - <span data-ttu-id="189d7-409">**언어**: 드롭다운을 클릭하고. 목록에서 사용 가능한 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-409">**Language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="189d7-410">기본적인 값은 **기본값** 이고 이는 영어를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-410">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="189d7-411">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-411">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="189d7-412">정책 세부 정보 플라이아웃으로 돌아와 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-412">Back on the policy details flyout, click **Close**.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-spam-policies"></a><span data-ttu-id="189d7-413">보안 센터를 사용하여 사용자 지정 스팸 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="189d7-413">Use the security center to remove custom anti-spam policies</span></span>

<span data-ttu-id="189d7-p151">보안 센터를 사용하여 사용자 지정 스팸 방지 정책을 제거하면 스팸 필터 규칙과 해당 스팸 필터 정책이 모두 삭제됩니다. 기본 스팸 방지 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-p151">When you use the security center to remove a custom anti-spam policy, the spam filter rule and the corresponding spam filter policy are both deleted. You can't remove the default anti-spam policy.</span></span>

1. <span data-ttu-id="189d7-416">보안 센터에서 **전자 메일 및 공동 작성** \> **정책 및 규칙** \> **위협 정책** \> **정책** 구역 \> **스팸 방지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-416">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="189d7-417">**스팸 방지 정책** 페이지에서 이름을 클릭하여 목록에서 **사용자 지정 스팸 방지 정책** **유형 값** 이 있는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-417">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="189d7-418">표시되는 정책 세부 정보 플라이아웃의 맨 위에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)**추가 작업**\>![정책 삭제 아이콘](../../media/m365-cc-sc-delete-icon.png)**정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-418">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="189d7-419">확인 대화 상자가 나타나면 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-419">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="189d7-420">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 스팸 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="189d7-420">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="189d7-421">앞서 설명한 것 처럼 스팸 방지 정책은 스팸 필터 정책 및 스팸 필터 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-421">As previously described, an anti-spam policy consists of a spam filter policy and a spam filter rule.</span></span>

<span data-ttu-id="189d7-422">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙 사이의 차이가 명확합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-422">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="189d7-423">**\*-HostedContentFilterPolicy** cmdlet을 사용하여 스팸 필터 정책을 관리하고, **\*-HostedContentFilterRule** cmdlet을 사용하여 스팸 필터 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-423">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="189d7-424">PowerShell에서는 먼저 스팸 필터 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-424">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="189d7-425">PowerShell에서는 스팸 필터 정책과 스팸 필터 규칙의 설정을 따로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-425">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>
- <span data-ttu-id="189d7-426">PowerShell에서 스팸 필터 정책을 제거하면 상응하는 스팸 필터 규칙은 자동으로 제거되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-426">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

<span data-ttu-id="189d7-427">다음 스팸 방지 정책 설정은 PowerShell에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-427">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="189d7-428">기본적으로 `On` 상태인 _MarkAsSpamBulkMail_ 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="189d7-428">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="189d7-429">이 설정의 효과는 이 문서의 앞부분에 있는 [보안 센터를 사용하여 스팸 방지 정책 만들기](#use-the-security-center-to-create-anti-spam-policies) 섹션에서 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-429">The effects of this setting were explained in the [Use the security center to create anti-spam policies](#use-the-security-center-to-create-anti-spam-policies) section earlier in this article.</span></span>

- <span data-ttu-id="189d7-430">최종 사용자 스팸 격리 알림을 위한 다음 설정:</span><span class="sxs-lookup"><span data-stu-id="189d7-430">The following settings for end-user spam quarantine notifications:</span></span>
  - <span data-ttu-id="189d7-431">_DownloadLink_ 매개 변수는 Outlook용 정크 메일 보고 도구에 대한 링크를 표시하거나 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-431">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>
  - <span data-ttu-id="189d7-432">_EndUserSpamNotificationCustomSubject_ 매개 변수는 알림의 제목 줄을 사용자 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-432">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="189d7-433">PowerShell을 사용하여 스팸 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="189d7-433">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="189d7-434">PowerShell에서 스팸 방지 정책을 만드는 작업은 2단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-434">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="189d7-435">스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-435">Create the spam filter policy.</span></span>
2. <span data-ttu-id="189d7-436">규칙이 적용되는 스팸 필터 정책을 지정하는 스팸 필터 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-436">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="189d7-437">**참고:**</span><span class="sxs-lookup"><span data-stu-id="189d7-437">**Notes**:</span></span>

- <span data-ttu-id="189d7-438">새 스팸 필터 규칙을 만들어 연결되지 않은 기존 스팸 필터 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-438">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="189d7-439">스팸 필터 규칙은 둘 이상의 스팸 필터 정책에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-439">A spam filter rule can't be associated with more than one spam filter policy.</span></span>
- <span data-ttu-id="189d7-440">정책을 만들 때까지 보안 센터에서 사용할 수 없는 PowerShell의 새 스팸 필터 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-440">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
  - <span data-ttu-id="189d7-441">비활성화된 새 정책을 만듭니다(**New-HostedContentFilterRule** cmdlet에서 `$false`를 _Enabled_).</span><span class="sxs-lookup"><span data-stu-id="189d7-441">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="189d7-442">**New-HostedContentFilterRule** cmdlet에서 정책을 만드는 동안 우선 순위(_우선 순위_ _\<Number\>_)를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-442">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="189d7-443">스팸 필터 규칙에 정책을 할당할 때까지 PowerShell에서 만든 새로운 스팸 필터 정책은 보안 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-443">A new spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="189d7-444">1단계: PowerShell을 사용하여 스팸 필터 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="189d7-444">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="189d7-445">스팸 필터 정책을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-445">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="189d7-446">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 정책을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-446">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="189d7-447">스팸 필터링 결과가 스팸이거나 높은 정확도의 스팸인 경우 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-447">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>
- <span data-ttu-id="189d7-448">BCL 7, 8 또는 9는 대량 전자 메일 스팸 필터링 결과 작업을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-448">BCL 7, 8, or 9 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

<span data-ttu-id="189d7-449">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-449">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="189d7-450">2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="189d7-450">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="189d7-451">스팸 필터 규칙을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-451">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="189d7-452">다음은 다음과 같은 설정을 사용하여 Contoso Executives라는 스팸 필터 규칙을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-452">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="189d7-453">Contoso Executives라는 스팸 필터 정책은 규칙과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-453">The spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="189d7-454">이 규칙은 Contoso Executives라는 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-454">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="189d7-455">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-455">For detailed syntax and parameter information, see [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="189d7-456">PowerShell을 사용하여 스팸 필터 정책 보기</span><span class="sxs-lookup"><span data-stu-id="189d7-456">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="189d7-457">모든 스팸 필터 정책의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-457">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="189d7-458">특정 스팸 필터 정책에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-458">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="189d7-459">다음은 Executives라는 스팸 필터 정책의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-459">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="189d7-460">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-460">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="189d7-461">PowerShell을 사용하여 스팸 필터 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="189d7-461">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="189d7-462">기존 스팸 필터 규칙을 보려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-462">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="189d7-463">모든 스팸 필터 규칙의 요약 목록을 반환하려면 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-463">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="189d7-464">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-464">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="189d7-465">특정 스팸 필터 규칙에 대한 자세한 정보를 반환하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-465">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="189d7-466">다음은 Contoso Executives라는 스팸 필터 규칙의 모든 속성 값을 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-466">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="189d7-467">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-467">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="189d7-468">PowerShell을 사용하여 스팸 필터 정책 수정하기</span><span class="sxs-lookup"><span data-stu-id="189d7-468">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="189d7-469">다음과 같은 항목 외에 PowerShell에서 스팸 필터 정책을 수정할 때 이 문서 앞부분의 [1단계 : PowerShell을 사용하여 스팸 필터 정책 만들기](#step-1-use-powershell-to-create-a-spam-filter-policy) 섹션에 설명된 대로 정책을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-469">Other than the following items, the same settings are available when you modify a spam filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this article.</span></span>

- <span data-ttu-id="189d7-470">지정된 정책을 기본 정책으로 바꾸는 _MakeDefault_ 스위치(모든 사용자에게 적용, 항상 우선순위가 **가장 낮으며** 삭제할 수 없음)는 PowerShell에서 스팸 필터 정책을 수정할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-470">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>
- <span data-ttu-id="189d7-471">스팸 필터 정책 이름을 바꿀 수 없습니다(**Set-HostedContentFilterPolicy** cmdlet에 _Name_ 매개 변수가 없음).</span><span class="sxs-lookup"><span data-stu-id="189d7-471">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="189d7-472">보안 및 준수 센터에서 스팸 방지 정책의 이름을 바꿀 경우 스팸 필터 _규칙_ 이름만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-472">When you rename an anti-spam policy in the security center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="189d7-473">스팸 필터 정책을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-473">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="189d7-474">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-474">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="189d7-475">PowerShell을 사용하여 스팸 필터 규칙 수정하기</span><span class="sxs-lookup"><span data-stu-id="189d7-475">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="189d7-476">PowerShell에서 스팸 필터 규칙을 수정할 때 사용할 수 없는 유일한 설정은 비활성화된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-476">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="189d7-477">기존 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-477">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="189d7-478">그렇지 않으면 PowerShell에서 스팸 필터 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-478">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="189d7-479">이 문서 앞부분의 [2단계: PowerShell을 사용하여 스팸 필터 규칙 만들기](#step-2-use-powershell-to-create-a-spam-filter-rule) 섹션에 설명된 대로 규칙을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-479">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="189d7-480">스팸 필터 규칙을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-480">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="189d7-481">이 예에서는 이름이 `{Fabrikam Spam Filter}`라는 이름의 기존 스팸 필터 규칙의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-481">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}`.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="189d7-482">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-482">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="189d7-483">PowerShell을 사용하여 스팸 필터 규칙 활성화 또는 비활성화하기</span><span class="sxs-lookup"><span data-stu-id="189d7-483">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="189d7-484">PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하면 전체 스팸 방지 정책(스팸 필터 규칙과 할당된 스팸 필터 정책)을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-484">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="189d7-485">기본 스팸 방지 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용됨).</span><span class="sxs-lookup"><span data-stu-id="189d7-485">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="189d7-486">PowerShell에서 스팸 필터 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-486">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="189d7-487">다음은 Marketing Department라는 스팸 필터 규칙을 사용하지 않도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-487">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="189d7-488">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-488">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="189d7-489">자세한 구문 및 매개 변수 정보는 [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule)과 [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-489">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="189d7-490">PowerShell을 사용하여 스팸 필터 규칙의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="189d7-490">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="189d7-491">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-491">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="189d7-492">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-492">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="189d7-493">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-493">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="189d7-494">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-494">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="189d7-495">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-495">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="189d7-496">PowerShell에서 스팸 필터 규칙의 우선순위를 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-496">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="189d7-497">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-497">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="189d7-498">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="189d7-498">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="189d7-499">**참고:**</span><span class="sxs-lookup"><span data-stu-id="189d7-499">**Notes**:</span></span>

- <span data-ttu-id="189d7-500">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-HostedContentFilterRule** cmdlet에서 _우선순위_ 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-500">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="189d7-501">기본 스팸 필터 정책에는 상응하는 스팸 필터 규칙이 없으며 항상 수정할 수 없는 **가장 낮은** 우선순위 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-501">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="189d7-502">PowerShell을 사용하여 스팸 필터 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="189d7-502">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="189d7-503">PowerShell을 사용하여 스팸 필터 정책을 제거할 때 상응하는 스팸 필터 규칙은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-503">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="189d7-504">PowerShell에서 스팸 필터 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-504">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="189d7-505">다음은 Marketing Department라는 스팸 필터 정책을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-505">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="189d7-506">자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-506">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="189d7-507">PowerShell을 사용하여 스팸 필터 규칙 제거하기</span><span class="sxs-lookup"><span data-stu-id="189d7-507">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="189d7-508">PowerShell을 사용하여 스팸 필터 규칙을 제거할 때 상응하는 스팸 필터 정책은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-508">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="189d7-509">PowerShell에서 스팸 필터 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-509">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="189d7-510">다음은 Marketing Department라는 스팸 필터 규칙을 제거하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-510">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="189d7-511">자세한 구문 및 매개 변수 정보는 [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="189d7-511">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="189d7-512">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="189d7-512">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="189d7-513">GTUBE 메시지를 보내서 스팸 정책 설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-513">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="189d7-p162">이 단계는 GTUBE 메시지를 보내는 전자 메일 조직이 아웃바운드 스팸을 검사하지 않는 경우에만 작동합니다. 검사를 시행하는 경우에는 테스트 메시지를 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-p162">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam. If it does, you can't send the test message.</span></span>

<span data-ttu-id="189d7-516">GTUBE(원치 않는 대량 전자 메일용 제네릭 테스트)는 조직에서 스팸 방지 설정을 확인하기 위해 테스트 메시지에 포함하는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-516">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="189d7-517">GTUBE 메시지는 맬웨어 설정을 테스트하기 위한 EICAR(European Institute for Computer Antivirus Research) 텍스트 파일과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-517">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="189d7-518">공백이나 줄 바꿈 없이 다음 GTUBE 텍스트를 전자 메일 메시지의 한 줄에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="189d7-518">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
