---
title: Microsoft Defender에서 피싱 방지 정책 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender를 사용하여 조직에서 사용할 수 있는 고급 피싱 방지 정책을 만들고 수정하고 삭제하는 방법을 Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9af3824b245cd976d1e859d6ebc4efcda47325e0
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793091"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="20be7-103">Microsoft Defender에서 피싱 방지 정책 Office 365</span><span class="sxs-lookup"><span data-stu-id="20be7-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="20be7-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="20be7-104">**Applies to**</span></span>
- [<span data-ttu-id="20be7-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="20be7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="20be7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20be7-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="20be7-107">[Microsoft Defender](defender-for-office-365.md) for Office 365 피싱 방지 정책은 악의적인 가장 기반 피싱 공격 및 기타 유형의 피싱 공격으로부터 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="20be7-108">EOP(Exchange Online Protection)의 피싱 방지 정책과 Microsoft Defender의 피싱 방지 정책 간의 차이점에 대한 자세한 내용은 Office 365 피싱 방지 보호를 [참조하세요.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="20be7-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="20be7-109">관리자는 기본 피싱 방지 정책을 보고 편집하고 구성할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="20be7-110">세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 피싱 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="20be7-111">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="20be7-112">Microsoft 365 보안 센터 또는 PowerShell에서 Office 365 대한 피싱 Exchange Online 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 security center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="20be7-113">조직에서 사용할 수 있는 피싱 방지 정책(즉, Exchange Online Protection용 Defender가 없는 조직)에서 보다 제한적인 피싱 방지 정책을 구성하는 Office 365 자세한 내용은 EOP에서 피싱 방지 정책 구성을 [참조하세요.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="20be7-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="20be7-114">피싱 방지 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="20be7-115">**피싱** 방지 정책: 사용하도록 설정하거나 사용하지 않도록 설정할 피싱 보호와 옵션을 적용할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="20be7-116">**피싱** 방지 규칙: 피싱 방지 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="20be7-117">보안 센터에서 피싱 방지 정책을 관리할 때 이러한 두 요소의 차이는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the security center:</span></span>

- <span data-ttu-id="20be7-118">정책을 만들 때 실제로 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="20be7-119">정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 피싱 방지 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="20be7-120">다른 모든 설정은 연결된 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="20be7-121">정책을 제거하면 피싱 방지 규칙 및 연결된 피싱 방지 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="20be7-122">PowerShell Exchange Online 정책과 규칙을 별도로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="20be7-123">자세한 내용은 이 [문서의 Exchange Online PowerShell을](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 사용하여 피싱 방지 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="20be7-124">모든 Office 365 조직의 모든 Defender에는 다음 속성이 있는 Office365 AntiPhish Default라는 기본 제공 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="20be7-125">이 정책은 정책과 연결된 피싱 방지 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="20be7-126">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="20be7-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="20be7-127">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="20be7-128">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="20be7-129">Defender for Office 365 피싱 방지 보호의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20be7-130">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="20be7-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20be7-131"><https://security.microsoft.com/>에서 보안 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-131">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="20be7-132">피싱 방지 페이지로 직접 **이동하기** 위해 를 <https://security.microsoft.com/antiphishing> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="20be7-133">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="20be7-134">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="20be7-135">피싱 방지 정책을 추가, 수정 및 삭제하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="20be7-136">피싱 방지 정책에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 의 구성원이 <sup>\*</sup> 되거나.</span><span class="sxs-lookup"><span data-stu-id="20be7-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="20be7-137">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="20be7-138">**참고**:</span><span class="sxs-lookup"><span data-stu-id="20be7-138">**Notes**:</span></span>

  - <span data-ttu-id="20be7-139">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="20be7-140">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="20be7-141">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="20be7-142">Defender for Office 365 피싱 방지 정책에 대한 권장 설정은 Office 365 설정에 대한 Defender의 피싱 [Office 365 참조하세요.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="20be7-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="20be7-143">새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="20be7-144">필터링 파이프라인에서 피싱 방지 정책이 적용되는 위치는 전자 메일 보호의 순서 및 우선 [순위를 참조하세요.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="20be7-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a><span data-ttu-id="20be7-145">보안 센터를 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="20be7-145">Use the security center to create anti-phishing policies</span></span>

<span data-ttu-id="20be7-146">보안 센터에서 사용자 지정 피싱 방지 정책을 만들면 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-146">Creating a custom anti-phishing policy in the security center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="20be7-147">보안 센터에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="20be7-147">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="20be7-148">피싱 **방지 페이지에서** 만들기 아이콘 만들기 ![ ](../../media/m365-cc-sc-create-icon.png) **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="20be7-149">정책 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-149">The policy wizard opens.</span></span> <span data-ttu-id="20be7-150">정책 **이름 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="20be7-151">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="20be7-152">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="20be7-153">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="20be7-154">표시되는 **사용자, 그룹 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람(받는 사람 조건)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="20be7-155">**사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="20be7-156">**그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="20be7-157">**도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="20be7-158">적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="20be7-159">이 프로세스를 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="20be7-160">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-160">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="20be7-162">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-162">next to the value.</span></span>

   <span data-ttu-id="20be7-163">사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="20be7-164">사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="20be7-165">동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="20be7-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="20be7-166">서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="20be7-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="20be7-167">**다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="20be7-168">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="20be7-169">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="20be7-170">피싱 **임계값이 나타나면** & 보호 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="20be7-171">**피싱 전자 메일 임계값:** 슬라이더를 사용하여 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="20be7-172">**1 -** 표준(기본값)</span><span class="sxs-lookup"><span data-stu-id="20be7-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="20be7-173">**2 - 적극적**</span><span class="sxs-lookup"><span data-stu-id="20be7-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="20be7-174">**3 - 보다 적극적**</span><span class="sxs-lookup"><span data-stu-id="20be7-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="20be7-175">**4 - 가장 적극적인**</span><span class="sxs-lookup"><span data-stu-id="20be7-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="20be7-176">자세한 내용은 Microsoft Defender for [Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="20be7-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="20be7-177">**가장:** 이러한 설정은 인바운드 메시지의 보낸 사람 주소에서 검색할 특정 보낸 사람(개별적으로 또는 도메인별)을 식별하는 정책의 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="20be7-178">자세한 내용은 Microsoft Defender for [Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="20be7-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="20be7-179">각 피싱 방지 정책에서 보호되는 사용자(보낸 사람 전자 메일 주소)를 최대 60명까지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="20be7-180">동일한 보호된 사용자를 여러 정책에 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="20be7-181">보낸 사람 및 받는 사람이 이전에 전자 메일을 통해 통신한 경우 사용자 가장 보호가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="20be7-182">보낸 사람 및 받는 사람이 전자 메일을 통해 통신한 적이 없는 경우 가장 시도로 메시지가 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="20be7-183">**사용자가 보호할** 수 있도록 설정 : 기본값이 해제되어 있습니다(선택되지 않았습니다).</span><span class="sxs-lookup"><span data-stu-id="20be7-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="20be7-184">이 기능을 켜려면 확인란을 선택한 다음 나타나는 **관리(nn) 보낸** 사람 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="20be7-185">나타나는 **가장 보호를 위한** 보낸 사람 관리 플라이아웃에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="20be7-186">**내부 보낸 사람:** 내부 ![ 아이콘 추가를 클릭합니다. ](../../media/m365-cc-sc-add-internal-icon.png) **내부 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="20be7-187">나타나는 **내부 보낸** 사람 추가 플라이아웃에서 상자를 클릭하고 목록에서 내부 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="20be7-188">사용자를 입력한 다음 결과에서 사용자를 선택하여 목록을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="20be7-189">대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름이 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="20be7-190">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="20be7-191">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-191">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="20be7-193">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-193">next to the value.</span></span>

         <span data-ttu-id="20be7-194">완료되면 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="20be7-195">**외부 보낸 사람:** 외부 ![ 아이콘 추가를 클릭합니다. ](../../media/m365-cc-sc-create-icon.png) **외부 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="20be7-196">외부 **보낸** 사람 추가 플라이아웃이 나타나면 이름  추가 상자에 표시 이름과  전자 메일 주소를 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="20be7-197">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="20be7-198">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-198">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="20be7-200">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-200">next to the value.</span></span>

         <span data-ttu-id="20be7-201">완료되면 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="20be7-202">가장에  대한 보낸 사람 관리 플라이아웃으로 돌아가 목록에서 항목을 하나 이상 선택하여 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="20be7-203">검색 아이콘 검색 상자를 사용하여 ![ 항목을 ](../../media/m365-cc-sc-create-icon.png) **검색할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="20be7-204">항목을 하나 이상 선택하면 선택한 사용자 제거 아이콘 선택한 사용자 제거 아이콘이 나타나며, 이 아이콘을 사용하여 선택한 항목을 ![ ](../../media/m365-cc-sc-remove-selected-users-icon.png)  제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="20be7-205">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="20be7-206">**도메인을 보호하도록 설정**: 기본값이 해제되어 있습니다(선택되지 않았습니다).</span><span class="sxs-lookup"><span data-stu-id="20be7-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="20be7-207">이 기능을 설정하려면 확인란을 선택한 다음 나타나는 다음 설정 중 하나 또는 둘 다를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="20be7-208">**소유한** 도메인 포함: 이 설정을 켜면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="20be7-209">소유한 도메인을 보려면 내 도메인 **보기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="20be7-210">**사용자 지정** 도메인 포함: 이 설정을 켜려면 확인란을 선택한 다음 나타나는 사용자 지정 도메인 관리(nn) 링크를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="20be7-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="20be7-211">가장 **보호를** 위한 사용자 지정 도메인 관리 플라이아웃이 나타나면 도메인 추가 ![ 아이콘 ](../../media/m365-cc-sc-create-icon.png) **도메인 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="20be7-212">표시되는 **사용자** 지정 도메인 추가 플라이아웃에서  도메인 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="20be7-213">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="20be7-214">기존 값을 제거하려면 값 옆에 있는 제거 ![제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="20be7-215">완료되면 도메인 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="20be7-216">모든 피싱 방지 정책에는 최대 50개 도메인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="20be7-217">가장 플라이아웃에 대한 사용자 지정 도메인 관리로 돌아가 목록에서 항목을 하나 이상 선택하여 항목을 제거할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="20be7-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="20be7-218">검색 아이콘 검색 상자를 사용하여 ![ 항목을 ](../../media/m365-cc-sc-create-icon.png) **검색할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="20be7-219">하나 이상의 항목을 선택하면 선택한 항목을 제거하는 데 사용할 수 있는 도메인 삭제 아이콘 삭제 아이콘이 ![ ](../../media/m365-cc-sc-delete-icon.png)  나타납니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="20be7-220">**신뢰할** 수 있는 보낸 사람 및 도메인 추가: **관리(nn)** 신뢰할 수 있는 보낸 사람 및 도메인을 클릭하여 정책에 대한 가장 보호 예외를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="20be7-221">나타나는 **가장 보호를** 위한 사용자 지정 도메인 관리 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="20be7-222">**보낸 사람**:  보낸 사람 탭이 선택되어 있는지 확인하고 보낸 사람 추가 ![ 아이콘 을 ](../../media/m365-cc-sc-create-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="20be7-223">신뢰할 **수 있는 보낸** 사람 추가 플라이아웃이 나타나면 상자에 전자 메일 주소를 입력하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="20be7-224">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="20be7-225">기존 항목을 제거하려면 ![ 항목의 삭제 ](../../media/m365-cc-sc-close-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="20be7-226">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="20be7-227">**도메인**: 도메인 **탭을 선택하고** 도메인 추가 아이콘 ![ 을 ](../../media/m365-cc-sc-create-icon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="20be7-228">표시되는 **신뢰할** 수 있는 도메인 추가 플라이아웃에서 도메인 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="20be7-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="20be7-229">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="20be7-230">기존 값을 제거하려면 값 옆에 있는 제거 ![제거 아이콘](../../media/m365-cc-sc-remove-selection-icon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="20be7-231">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="20be7-232">가장에 대한 사용자 지정 도메인 관리 플라이아웃으로 돌아가 목록에서 항목을  하나 이상 선택하여 보낸 사람 및 도메인 탭에서 항목을 제거할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="20be7-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="20be7-233">검색 아이콘 검색 상자를 사용하여 ![ 항목을 ](../../media/m365-cc-sc-create-icon.png) **검색할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="20be7-234">하나 이상의 항목을 선택하면 선택한  항목을 제거하는 데 사용할 수 있는 삭제 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="20be7-235">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="20be7-236">**사서함 인텔리전스 사용:** 기본값은 설정(선택)으로 설정되어 있으며 그대로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="20be7-237">끄기 위해 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="20be7-238">**인텔리전스 기반** 가장 보호 사용: 이 설정은 사서함 인텔리전스 사용이 설정되어 있는(선택된 경우) **사용할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="20be7-239">이 설정을 사용하면 사서함 인텔리전스에서 가장 시도로 식별된 메시지에 대해 작업을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="20be7-240">사서함 인텔리전스에서  다음 페이지에서 가장된 사용자 설정을 검색하는 경우에서 취할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="20be7-241">이 설정은 확인란을 선택하여 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="20be7-242">이 설정을 끄기 위해 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="20be7-243">**스푸핑:** 이 섹션에서  스푸핑 인텔리전스 사용 확인란을 사용하여 스푸핑 인텔리전스를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="20be7-244">기본값은 설정(선택)으로 설정되어 있으며 그대로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="20be7-245">다음 페이지에서 스푸핑으로 검색된 경우 설정에서 차단된  스푸핑된 보낸 사람이 보낸 메시지에 대해 취할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="20be7-246">스푸핑 인텔리전스를 끄기 위해 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="20be7-247">MX 레코드가 스푸핑 방지를 설정하지 않는 경우 스푸핑 방지 보호 기능을 해제할 Microsoft 365. 대신 커넥터에 대해 향상된 필터링을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="20be7-248">자세한 내용은 [에서 커넥터에](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)대한 향상된 필터링을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="20be7-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="20be7-249">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="20be7-250">표시되는 **작업** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="20be7-251">**메시지 작업:** 이 섹션에서 다음 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="20be7-252">**가장된** 사용자로 메시지가 검색된 경우: 이 설정은 이전 페이지에서 사용자가 보호할 수 있도록 설정을 선택한 **경우만** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="20be7-253">드롭다운 목록에서 보낸 사람이 이전 페이지에서 지정한 보호된 사용자 중 하나인 메시지에 대해 다음 작업 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="20be7-254">**어떤 작업도 적용하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="20be7-255">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="20be7-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="20be7-256">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="20be7-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="20be7-257">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="20be7-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="20be7-258">**메시지를 배달하고 Bcc 줄에 다른 주소를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="20be7-259">**배달되기 전에 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="20be7-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="20be7-260">**가장된** 도메인으로 메시지가 검색된 경우: 이 설정은 이전 페이지에서 도메인을 보호하도록 설정을 선택한 **경우만** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="20be7-261">드롭다운 목록에서 보낸 사람 전자 메일 주소가 이전 페이지에서 지정한 보호된 도메인 중 하나에 있는 메시지에 대해 다음 작업 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="20be7-262">**어떤 작업도 적용하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="20be7-263">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="20be7-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="20be7-264">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="20be7-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="20be7-265">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="20be7-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="20be7-266">**메시지를 배달하고 Bcc 줄에 다른 주소를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="20be7-267">**배달되기 전에 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="20be7-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="20be7-268">**사서함 인텔리전스에서** 가장된 사용자를 검색하는 경우: 이 설정은 이전 페이지에서 가장 보호를 위해 **인텔리전스** 사용 을 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="20be7-269">사서함 인텔리전스에서 가장 시도로 식별된 메시지에 대해 드롭다운 목록에서 다음 작업 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="20be7-270">**어떤 작업도 적용하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="20be7-271">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="20be7-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="20be7-272">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="20be7-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="20be7-273">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="20be7-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="20be7-274">**메시지를 배달하고 Bcc 줄에 다른 주소를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="20be7-275">**배달되기 전에 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="20be7-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="20be7-276">**메시지가 스푸핑으로** 검색된 경우 : 이 설정은 이전 페이지에서 스푸핑 **인텔리전스** 사용 을 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="20be7-277">드롭다운 목록에서 차단된 스푸핑된 보낸 사람이 보낸 메시지에 대해 다음 작업 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="20be7-278">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="20be7-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="20be7-279">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="20be7-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="20be7-280">**안전 팁 & 표시기:** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="20be7-281">**사용자 가장** 표시 보안 팁 : 이 설정은 이전 페이지에서 사용자가 보호할 수 있도록 설정을 선택한 **경우만** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-281">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="20be7-282">**도메인 가장** 표시 보안 팁 : 이 설정은 이전 페이지에서 도메인을 보호하도록 설정을 **선택한** 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-282">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="20be7-283">**사용자 가장 비정상 문자** 표시 보안 팁 이 설정은 사용자가 이전  페이지에서 보호할  수 있도록 설정 또는 도메인을 보호할 수 있도록 설정을 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-283">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="20be7-284">**스푸핑에** 대해 확인되지 않은 보낸 사람에 대한 표시(?) : 이 설정은 이전 페이지에서 스푸핑 **인텔리전스** 사용 을 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-284">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="20be7-285">메시지가 SPF 또는 DKIM 검사를 통과하지 못하고 메시지가 DMARC 또는 복합 인증을 통과하지  Outlook 메시지의 보낸 사람 상자에 보낸 사람 사진에 물음표를 [추가합니다.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="20be7-285">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="20be7-286">**"via" 태그** 표시 : 이 설정은 이전 페이지에서 스푸핑 **인텔리전스** 사용 을 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-286">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="20be7-287">DKIM 서명의 도메인 또는 MAIL FROM 주소의 도메인과 다른 경우 보낸 chris@contoso.com (fabrikam.com 통해) 태그를 보낸사용자 주소에 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-287">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="20be7-288">기본값은 설정(선택)입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-288">The default value is on (selected).</span></span> <span data-ttu-id="20be7-289">끄기 위해 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-289">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="20be7-290">현재 일부 조직에서는 **"via" 태그 표시** 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-290">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="20be7-291">**"via"** 태그 표시 설정이 없는 경우 물음표와 via 태그는 모두 조직에서 스푸핑에 대한 확인되지 않은 보낸 사람에 대한 표시(?)에 의해 제어됩니다.  </span><span class="sxs-lookup"><span data-stu-id="20be7-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="20be7-292">설정을 켜기 위해 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="20be7-293">끄기 위해 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="20be7-294">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="20be7-295">표시되는 **검토** 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="20be7-296">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="20be7-297">또는 뒤로를 **클릭하거나** 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="20be7-298">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="20be7-299">표시되는 확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a><span data-ttu-id="20be7-300">보안 센터를 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="20be7-300">Use the security center to view anti-phishing policies</span></span>

1. <span data-ttu-id="20be7-301">보안 센터에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="20be7-301">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="20be7-302">피싱  방지 페이지에는 피싱 방지 정책 목록에 다음 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="20be7-303">**이름**</span><span class="sxs-lookup"><span data-stu-id="20be7-303">**Name**</span></span>
   - <span data-ttu-id="20be7-304">**상태**</span><span class="sxs-lookup"><span data-stu-id="20be7-304">**Status**</span></span>
   - <span data-ttu-id="20be7-305">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="20be7-305">**Priority**</span></span>
   - <span data-ttu-id="20be7-306">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="20be7-306">**Last modified**</span></span>

3. <span data-ttu-id="20be7-307">이름을 클릭하여 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="20be7-308">보안 센터를 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="20be7-308">Use the security center to modify anti-phishing policies</span></span>

1. <span data-ttu-id="20be7-309">보안 센터에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="20be7-309">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="20be7-310">피싱 **방지** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="20be7-311">표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="20be7-312">설정에 대한 자세한 내용은 [](#use-the-security-center-to-create-anti-phishing-policies) 이 문서 앞부분의 보안 센터를 사용하여 피싱 방지 정책 만들기 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="20be7-312">For more information about the settings, see the [Use the security center to create anti-phishing policies](#use-the-security-center-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="20be7-313">기본 피싱 방지 정책의 경우 **사용자,** 그룹 및 도메인 섹션을 사용할 수 없습니다(정책은 모든 사용자에게 적용), 정책의 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="20be7-314">정책을 사용하도록 설정하거나 사용하지 않도록 설정하거나 정책 우선 순위를 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="20be7-315">사용자 지정 피싱 방지 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="20be7-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="20be7-316">기본 피싱 방지 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="20be7-317">보안 센터에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="20be7-317">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="20be7-318">피싱 **방지** 페이지에서 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="20be7-319">표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="20be7-320">**정책 끄기**: 정책을 켜려면 ![켜기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="20be7-321">**정책**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="20be7-322">표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="20be7-323">정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="20be7-324">기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="20be7-325">사용자 지정 피싱 방지 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="20be7-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="20be7-326">기본적으로 피싱 방지 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="20be7-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="20be7-327">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="20be7-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="20be7-328">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="20be7-329">정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(보안 센터에서 **우선 순위** 번호를 직접 수정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="20be7-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="20be7-330">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="20be7-331">**참고**:</span><span class="sxs-lookup"><span data-stu-id="20be7-331">**Notes**:</span></span>

- <span data-ttu-id="20be7-332">보안 센터에서는 피싱 방지 정책을 만든 후에만 우선 순위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-332">In the security center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="20be7-333">PowerShell에서 피싱 방지 규칙을 만들 때 기본 우선 순위를 다시 지정하여 기존 규칙의 우선 순위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="20be7-334">피싱 방지 정책은 표시되는 순서대로 처리됩니다(첫 번째 정책의  우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="20be7-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="20be7-335">기본 피싱 방지 정책의 우선 순위 값은 **Lowest** 입니다. 이 정책은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="20be7-336">보안 센터에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="20be7-336">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="20be7-337">피싱 **방지** 페이지에서 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="20be7-338">표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="20be7-339">우선 순위 값이 **0인** 피싱 방지 정책에는 우선 순위 감소 옵션만 사용할  **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-339">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="20be7-340">우선 순위 값이 가장 낮은  피싱 방지 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-340">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="20be7-341">피싱 방지 정책이 세 개 이상 있는 경우 우선 순위가 가장  높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-341">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="20be7-342">![우선순위 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선순위** 또는 ![우선순위 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위** 를 클릭하여 **우선순위** 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="20be7-343">작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="20be7-344">보안 센터를 사용하여 사용자 지정 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="20be7-344">Use the security center to remove custom anti-phishing policies</span></span>

<span data-ttu-id="20be7-345">보안 센터를 사용하여 사용자 지정 피싱 방지 정책을 제거하면 피싱 방지 규칙과 해당 피싱 방지 정책이 모두 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-345">When you use the security center to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="20be7-346">기본 피싱 방지 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="20be7-347">보안 센터에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="20be7-347">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="20be7-348">정책 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-348">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="20be7-349">표시되는 정책 세부 정보 플라이아웃의 맨 위에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)**추가 작업**\>![정책 삭제 아이콘](../../media/m365-cc-sc-delete-icon.png)**정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="20be7-350">확인 대화 상자가 나타나면 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="20be7-351">PowerShell Exchange Online 사용하여 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="20be7-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="20be7-352">앞서 설명한 바와 같이 스팸 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="20be7-353">PowerShell에서 Exchange Online 피싱 방지 정책과 피싱 방지 규칙의 차이는 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="20be7-354">**\* -AntiPhishPolicy** cmdlet을 사용하여 피싱 방지 정책을 관리하고 - **\* AntiPhishRule** cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="20be7-355">PowerShell에서 먼저 피싱 방지 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="20be7-356">PowerShell에서는 피싱 방지 정책 및 피싱 방지 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="20be7-357">PowerShell에서 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="20be7-358">PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="20be7-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="20be7-359">PowerShell에서 피싱 방지 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="20be7-360">피싱 방지 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="20be7-361">규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="20be7-362">**참고:**</span><span class="sxs-lookup"><span data-stu-id="20be7-362">**Notes**:</span></span>

- <span data-ttu-id="20be7-363">새 피싱 방지 규칙을 만들고 기존의 통합되지 않은 피싱 방지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="20be7-364">피싱 방지 규칙은 두 개 이상의 피싱 방지 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="20be7-365">정책을 만든 후까지 보안 센터에서 사용할 수 없는 PowerShell의 새로운 피싱 방지 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
  - <span data-ttu-id="20be7-366">새 정책을 사용하지 않도록 `$false` **설정(New-AntiPhishRule** cmdlet에서 사용)으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="20be7-367"> _\<Number\>_ **New-AntiPhishRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="20be7-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="20be7-368">PowerShell에서 만든 새로운 피싱 방지 정책은 피싱 방지 규칙에 정책을 할당할 때까지 보안 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-368">A new anti-phish policy that you create in PowerShell isn't visible in the security center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="20be7-369">1단계: PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="20be7-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="20be7-370">피싱 방지 정책을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="20be7-371">이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="20be7-372">정책이 사용하도록 설정됩니다(Enabled 매개  변수를 사용하지 않습니다. 기본값은 `$true` 입니다).</span><span class="sxs-lookup"><span data-stu-id="20be7-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="20be7-373">설명은 리서치 부서 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="20be7-374">모든 허용 도메인에 대해 조직 도메인 보호를 설정하고 대상 도메인에 대한 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="20be7-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="20be7-375">가장으로부터 보호할 사용자로 Mai Fujito(mfujito@fabrikam.com)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="20be7-376">사서함 인텔리전스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="20be7-377">사서함 인텔리전스 보호를 사용하며, 검역 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="20be7-378">안전 팁을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="20be7-379">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy 를 참조하십시오.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="20be7-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="20be7-380">2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="20be7-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="20be7-381">피싱 방지 규칙을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="20be7-382">이 예에서는 다음 조건을 통해 Research Department라는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="20be7-383">이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="20be7-384">이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="20be7-385">Priority 매개 변수를  사용하지 않을 것이기 때문에 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="20be7-386">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="20be7-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="20be7-387">PowerShell을 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="20be7-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="20be7-388">기존 피싱 방지 정책을 보기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="20be7-389">이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="20be7-390">이 예에서는 Executives라는 피싱 방지 정책의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="20be7-391">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="20be7-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="20be7-392">PowerShell을 사용하여 피싱 방지 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="20be7-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="20be7-393">기존 피싱 방지 규칙을 보시다시피 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="20be7-394">이 예에서는 지정된 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="20be7-395">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="20be7-396">이 예에서는 Contoso Executives라는 피싱 방지 규칙의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="20be7-397">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule 을 참조하십시오.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="20be7-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="20be7-398">PowerShell을 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="20be7-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="20be7-399">다음 항목 이외에도 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-an-anti-phish-policy) 사용하여 피싱 방지 정책 만들기 섹션에 설명된 대로 PowerShell에서 피싱 방지 정책을 수정할 때와 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="20be7-400">지정된 정책을 기본 정책으로 전환하는 _MakeDefault_ 스위치는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다(모든 사용자에 적용, 항상 최하위 우선 순위 및 삭제할 수 없습니다). </span><span class="sxs-lookup"><span data-stu-id="20be7-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="20be7-401">피싱 방지 정책의 이름을 다시 설정할 수 **없습니다(Set-AntiPhishPolicy** cmdlet에는 Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="20be7-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="20be7-402">보안 센터에서 피싱 방지 정책의 이름을 다시 정하면 피싱 방지 규칙의 이름만 다시 _정해진 것입니다._</span><span class="sxs-lookup"><span data-stu-id="20be7-402">When you rename an anti-phishing policy in the security center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="20be7-403">피싱 방지 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="20be7-404">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="20be7-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="20be7-405">PowerShell을 사용하여 피싱 방지 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="20be7-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="20be7-406">PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용하지 않도록 설정된 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="20be7-407">기존 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20be7-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="20be7-408">그렇지 않으면 PowerShell에서 피싱 방지 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="20be7-409">이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 피싱 방지 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="20be7-410">피싱 방지 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="20be7-411">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule 을 참조하십시오.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="20be7-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="20be7-412">PowerShell을 사용하여 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="20be7-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="20be7-413">PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="20be7-414">기본 피싱 방지 정책은 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="20be7-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="20be7-415">PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="20be7-416">이 예에서는 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="20be7-417">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="20be7-418">구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 및 [Disable-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="20be7-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="20be7-419">PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="20be7-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="20be7-420">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-420">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="20be7-421">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-421">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="20be7-422">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-422">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="20be7-423">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-423">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="20be7-424">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-424">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="20be7-425">PowerShell에서 피싱 방지 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="20be7-426">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-426">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="20be7-427">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="20be7-427">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="20be7-428">**참고:**</span><span class="sxs-lookup"><span data-stu-id="20be7-428">**Notes**:</span></span>

- <span data-ttu-id="20be7-429">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-AntiPhishRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="20be7-430">기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없습니다. 또한 항상 가장 낮은 우선 순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="20be7-431">PowerShell을 사용하여 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="20be7-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="20be7-432">PowerShell을 사용하여 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="20be7-433">PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="20be7-434">이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="20be7-435">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="20be7-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="20be7-436">PowerShell을 사용하여 피싱 방지 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="20be7-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="20be7-437">PowerShell을 사용하여 피싱 방지 규칙을 제거하면 해당 피싱 방지 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="20be7-438">PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="20be7-439">이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="20be7-440">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="20be7-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="20be7-441">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="20be7-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="20be7-442">Defender에서 피싱 방지 정책을 성공적으로 구성한 Office 365 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="20be7-443">보안 센터에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="20be7-443">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="20be7-444">정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="20be7-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="20be7-445">자세한 내용을 보려면 이름을 클릭하고 나타나는 플라이아웃에서 세부 정보를 확인하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="20be7-446">PowerShell Exchange Online 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하여 \<Name\> 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="20be7-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
