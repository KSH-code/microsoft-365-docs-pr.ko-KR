---
title: EOP에서 스팸 방지 정책 구성
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
description: 관리자는 사서함을 사용하거나 사서함이 없는 EOP(Exchange Online Protection 조직)에서 사용할 수 있는 피싱 방지 정책을 만들고 수정하고 삭제하는 Exchange Online 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dcfba32a5c76915c8c905d55b69712162efac48
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062226"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="f06ee-103">EOP에서 스팸 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f06ee-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f06ee-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f06ee-104">**Applies to**</span></span>
- [<span data-ttu-id="f06ee-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f06ee-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="f06ee-106">Microsoft 365 사서함이 없는 Exchange Online 또는 Exchange Online Exchange Online Protection(독립 실행형 EOP) 조직에 사서함이 있는 조직에는 기본적으로 사용하도록 설정된 제한된 수의 스푸핑 방지 기능이 포함된 기본 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="f06ee-107">자세한 내용은 [피싱 방지 정책의 스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f06ee-108">관리자는 기본 피싱 방지 정책을 보고 편집하고 구성할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="f06ee-109">세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 피싱 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="f06ee-110">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="f06ee-111">사서함이 Exchange Online 조직은 Microsoft 365 Defender 포털 또는 PowerShell에서 피싱 Exchange Online 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="f06ee-112">독립 실행형 EOP 조직은 해당 포털만 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="f06ee-113">Microsoft Defender for Office 365 사용할 수 있는 고급 피싱 방지 정책을 만들고 수정하는 Office 365 Microsoft [Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책 구성을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="f06ee-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

<span data-ttu-id="f06ee-114">피싱 방지 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="f06ee-115">**피싱** 방지 정책: 사용하도록 설정하거나 사용하지 않도록 설정할 피싱 보호와 옵션을 적용할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="f06ee-116">**피싱** 방지 규칙: 피싱 방지 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="f06ee-117">이러한 두 요소 간의 차이는 피싱 방지 정책을 사이트 포털에서 관리할 때 명확히 Microsoft 365 Defender 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f06ee-118">피싱 방지 정책을 만들 때 실제로 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="f06ee-119">피싱 방지 정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 피싱 방지 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="f06ee-120">다른 모든 설정은 연결된 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="f06ee-121">피싱 방지 정책을 제거하면 피싱 방지 규칙 및 관련 피싱 방지 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="f06ee-122">PowerShell Exchange Online 정책과 규칙을 별도로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="f06ee-123">자세한 내용은 이 [문서의 Exchange Online PowerShell을](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 사용하여 피싱 방지 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="f06ee-124">모든 조직에는 다음 속성이 있는 Office365 AntiPhish Default라는 기본 제공 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="f06ee-125">이 정책은 정책과 연결된 피싱 방지 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="f06ee-126">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="f06ee-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="f06ee-127">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="f06ee-128">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="f06ee-129">피싱 방지 보호의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f06ee-130">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f06ee-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f06ee-131"><https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="f06ee-132">피싱 방지 페이지로 직접 **이동하기** 위해 를 <https://security.microsoft.com/antiphishing> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="f06ee-133">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="f06ee-134">독립 실행형 EOP PowerShell에서는 피싱 방지 정책을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="f06ee-135">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f06ee-136">피싱 방지 정책을 추가, 수정 및 삭제하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f06ee-137">피싱 방지 정책에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f06ee-138">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="f06ee-139">**참고**:</span><span class="sxs-lookup"><span data-stu-id="f06ee-139">**Notes**:</span></span>

  - <span data-ttu-id="f06ee-140">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f06ee-141">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="f06ee-142">또한 **조직의 보기** 전용 조직 관리 역할 Exchange Online 기능에 대한 읽기 [전용](/Exchange/permissions-exo/permissions-exo#role-groups) 액세스 권한을 <sup>\*</sup> 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="f06ee-143">피싱 방지 정책에 대한 권장 설정은 EOP 피싱 방지 정책 [설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="f06ee-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="f06ee-144">업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="f06ee-145">필터링 파이프라인에서 피싱 방지 정책이 적용되는 위치는 전자 메일 보호의 순서 및 우선 [순위를 참조하세요.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="f06ee-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="f06ee-146">Microsoft 365 Defender 포털을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f06ee-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="f06ee-147">Microsoft 365 Defender 포털에서 사용자 지정 피싱 방지 정책을 만들면 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f06ee-148">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f06ee-149">피싱 **방지 페이지에서** 만들기 아이콘 만들기 ![ ](../../media/m365-cc-sc-create-icon.png) **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="f06ee-150">정책 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-150">The policy wizard opens.</span></span> <span data-ttu-id="f06ee-151">정책 **이름 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="f06ee-152">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="f06ee-153">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f06ee-154">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f06ee-155">표시되는 **사용자, 그룹 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람(받는 사람 조건)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="f06ee-156">**사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f06ee-157">**그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="f06ee-158">**도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="f06ee-159">적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="f06ee-160">이 프로세스를 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="f06ee-161">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-161">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="f06ee-163">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-163">next to the value.</span></span>

   <span data-ttu-id="f06ee-164">사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="f06ee-165">사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="f06ee-166">동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="f06ee-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f06ee-167">서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="f06ee-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="f06ee-168">**다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="f06ee-169">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f06ee-170">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f06ee-171">나타나는 **피싱** 임계값 & 스푸핑 인텔리전스  사용 확인란을 사용하여 스푸핑 인텔리전스를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="f06ee-172">기본값은 설정(선택)으로 설정되어 있으며 그대로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="f06ee-173">다음 페이지에서 차단된 스푸핑된 메시지에 대해 수행하도록 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="f06ee-174">스푸핑 인텔리전스를 끄기 위해 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f06ee-175">MX 레코드가 스푸핑 방지를 설정하지 않는 경우 스푸핑 방지 보호 기능을 해제할 Microsoft 365. 대신 커넥터에 대해 향상된 필터링을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="f06ee-176">자세한 내용은 [에서 커넥터에](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)대한 향상된 필터링을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f06ee-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="f06ee-177">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f06ee-178">표시되는 **작업** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="f06ee-179">**메시지가 스푸핑으로** 검색된 경우 : 이 설정은 이전 페이지에서 스푸핑 **인텔리전스** 사용 을 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="f06ee-180">드롭다운 목록에서 차단된 스푸핑된 보낸 사람이 보낸 메시지에 대해 다음 작업 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="f06ee-181">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="f06ee-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="f06ee-182">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="f06ee-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="f06ee-183">**안전 팁 & 표시기**:</span><span class="sxs-lookup"><span data-stu-id="f06ee-183">**Safety tips & indicators**:</span></span>
     - <span data-ttu-id="f06ee-184">**첫 번째 연락처 보안 팁** 표시 : 자세한 내용은 첫 번째 연락처 [보안 팁.](set-up-anti-phishing-policies.md#first-contact-safety-tip)</span><span class="sxs-lookup"><span data-stu-id="f06ee-184">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="f06ee-185">스푸핑을 위해 인증되지 않은 보낸 사람에 대한 **표시(?)**: 메시지가 SPF 또는 DKIM 확인을 통과하지 못하고 메시지가 DMARC 또는 복합 인증을 통과하지 않는 경우 Outlook의 보낸 사람 상자에 보낸 사람 사진에 물음표를 <sup>\*</sup> 추가합니다.  [](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="f06ee-185">**Show (?) for unauthenticated senders for spoof**<sup>\*</sup>: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="f06ee-186">**"via"** 태그 표시 : DKIM 서명의 도메인 또는 MAIL FROM 주소의 도메인과 다른 경우 보낸 chris@contoso.com(fabrikam.com 통해)를 보낸 주소에 <sup>\*</sup> 추가합니다. </span><span class="sxs-lookup"><span data-stu-id="f06ee-186">**Show "via" tag**<sup>\*</sup>: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

     <span data-ttu-id="f06ee-187">설정을 켜기 위해 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-187">To turn on a setting, select the check box.</span></span> <span data-ttu-id="f06ee-188">끄기 위해 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-188">To turn it off, clear the check box.</span></span>

     <span data-ttu-id="f06ee-189"><sup>\*</sup>이 설정은 이전 페이지에서  스푸핑 인텔리전스 사용 을 선택한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-189"><sup>\*</sup> This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="f06ee-190">자세한 내용은 [Unauthenticated sender 을 참조하십시오.](set-up-anti-phishing-policies.md#unauthenticated-sender)</span><span class="sxs-lookup"><span data-stu-id="f06ee-190">For more information, see [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).</span></span>

   <span data-ttu-id="f06ee-191">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-191">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f06ee-192">표시되는 **검토** 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-192">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="f06ee-193">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-193">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="f06ee-194">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-194">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="f06ee-195">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-195">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="f06ee-196">표시되는 확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-196">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="f06ee-197">Microsoft 365 Defender 포털을 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="f06ee-197">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="f06ee-198">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-198">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f06ee-199">피싱 **방지 페이지에는** 정책 목록에 다음 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-199">On the **Anti-phishing** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="f06ee-200">**이름**</span><span class="sxs-lookup"><span data-stu-id="f06ee-200">**Name**</span></span>
   - <span data-ttu-id="f06ee-201">**상태**</span><span class="sxs-lookup"><span data-stu-id="f06ee-201">**Status**</span></span>
   - <span data-ttu-id="f06ee-202">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="f06ee-202">**Priority**</span></span>
   - <span data-ttu-id="f06ee-203">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="f06ee-203">**Last modified**</span></span>

3. <span data-ttu-id="f06ee-204">이름을 클릭하여 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-204">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="f06ee-205">Microsoft 365 Defender 포털을 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="f06ee-205">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="f06ee-206">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-206">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f06ee-207">피싱 **방지** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-207">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f06ee-208">표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-208">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="f06ee-209">설정에 대한 자세한 내용은 [](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) 이 문서 앞부분의 Microsoft 365 Defender 포털을 사용하여 피싱 방지 정책 만들기 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f06ee-209">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="f06ee-210">기본 피싱 방지 정책의 경우 **사용자,** 그룹 및 도메인 섹션을 사용할 수 없습니다(정책은 모든 사용자에게 적용), 정책의 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-210">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="f06ee-211">정책을 사용하도록 설정하거나 사용하지 않도록 설정하거나 정책 우선 순위를 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-211">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="f06ee-212">사용자 지정 피싱 방지 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f06ee-212">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="f06ee-213">기본 피싱 방지 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-213">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="f06ee-214">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-214">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f06ee-215">피싱 **방지** 페이지에서 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-215">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f06ee-216">표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-216">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="f06ee-217">**정책 끄기**: 정책을 켜려면 ![켜기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-217">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="f06ee-218">**정책**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-218">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="f06ee-219">표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-219">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="f06ee-220">정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-220">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="f06ee-221">기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-221">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="f06ee-222">사용자 지정 피싱 방지 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="f06ee-222">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="f06ee-223">기본적으로 피싱 방지 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="f06ee-223">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="f06ee-224">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="f06ee-224">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f06ee-225">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-225">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="f06ee-226">정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(Microsoft 365 Defender 포털에서 **우선 순위** 번호를 직접 수정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="f06ee-226">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="f06ee-227">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-227">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="f06ee-228">**참고**:</span><span class="sxs-lookup"><span data-stu-id="f06ee-228">**Notes**:</span></span>

- <span data-ttu-id="f06ee-229">Microsoft 365 Defender 포털에서 피싱 방지 정책의 우선 순위를 변경한 후에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-229">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="f06ee-230">PowerShell에서 피싱 방지 규칙을 만들 때 기본 우선 순위를 다시 지정하여 기존 규칙의 우선 순위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-230">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="f06ee-231">피싱 방지 정책은 표시되는 순서대로 처리됩니다(첫 번째 정책의  우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="f06ee-231">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f06ee-232">기본 피싱 방지 정책의 우선 순위 값은 **Lowest** 입니다. 이 정책은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-232">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="f06ee-233">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-233">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f06ee-234">피싱 **방지** 페이지에서 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-234">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f06ee-235">표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-235">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="f06ee-236">우선 순위  값이 **0인** 정책에는 우선 순위 감소 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-236">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="f06ee-237">우선 순위 값이 가장 **낮은** 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-237">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="f06ee-238">세 개 이상의 정책이 있는 경우 우선 순위가 가장  높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-238">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="f06ee-239">![우선순위 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선순위** 또는 ![우선순위 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위** 를 클릭하여 **우선순위** 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-239">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="f06ee-240">작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-240">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="f06ee-241">Microsoft 365 Defender 포털을 사용하여 사용자 지정 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="f06ee-241">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="f06ee-242">Microsoft 365 Defender 포털을 사용하여 사용자 지정 피싱 방지 정책을 제거하면 피싱 방지 규칙과 해당 피싱 방지 정책이 모두 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-242">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="f06ee-243">기본 피싱 방지 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-243">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="f06ee-244">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f06ee-245">피싱 **방지** 페이지에서 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-245">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f06ee-246">표시되는 정책 세부 정보 플라이아웃의 맨 위에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)**추가 작업**\>![정책 삭제 아이콘](../../media/m365-cc-sc-delete-icon.png)**정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="f06ee-247">확인 대화 상자가 나타나면 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="f06ee-248">PowerShell Exchange Online 사용하여 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f06ee-248">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="f06ee-249">앞서 설명한 바와 같이 피싱 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-249">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="f06ee-250">PowerShell에서 Exchange Online 피싱 방지 정책과 피싱 방지 규칙의 차이는 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-250">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="f06ee-251">**\* -AntiPhishPolicy** cmdlet을 사용하여 피싱 방지 정책을 관리하고 - **\* AntiPhishRule** cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-251">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="f06ee-252">PowerShell에서 먼저 피싱 방지 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-252">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f06ee-253">PowerShell에서는 피싱 방지 정책 및 피싱 방지 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-253">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="f06ee-254">PowerShell에서 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-254">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="f06ee-255">다음 PowerShell 절차는 PowerShell을 사용하는 독립 실행형 EOP 조직에서는 사용할 Exchange Online Protection 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-255">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="f06ee-256">PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f06ee-256">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="f06ee-257">PowerShell에서 피싱 방지 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-257">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f06ee-258">피싱 방지 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-258">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="f06ee-259">규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-259">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="f06ee-260">**참고:**</span><span class="sxs-lookup"><span data-stu-id="f06ee-260">**Notes**:</span></span>

- <span data-ttu-id="f06ee-261">새 피싱 방지 규칙을 만들고 기존의 통합되지 않은 피싱 방지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-261">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="f06ee-262">피싱 방지 규칙은 두 개 이상의 피싱 방지 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-262">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="f06ee-263">정책을 만든 후까지 Microsoft 365 Defender 포털에서 사용할 수 없는 PowerShell의 새 피싱 방지 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-263">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id="f06ee-264">새 정책을 사용하지 않도록 `$false` **설정(New-AntiPhishRule** cmdlet에서 사용)으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-264">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="f06ee-265"> _\<Number\>_ **New-AntiPhishRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="f06ee-265">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="f06ee-266">PowerShell에서 만든 새 피싱 방지 정책은 피싱 방지 규칙에 정책을 할당할 때까지 Microsoft 365 Defender 포털에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-266">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="f06ee-267">1단계: PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f06ee-267">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="f06ee-268">피싱 방지 정책을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-268">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="f06ee-269">이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-269">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="f06ee-270">설명은 리서치 부서 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-270">The description is: Research department policy.</span></span>
- <span data-ttu-id="f06ee-271">스푸핑에 대한 기본 작업을 Quarantine으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-271">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="f06ee-272">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy 를 참조하십시오.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="f06ee-272">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="f06ee-273">2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="f06ee-273">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="f06ee-274">피싱 방지 규칙을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-274">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="f06ee-275">이 예에서는 다음 조건을 통해 Research Department라는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-275">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="f06ee-276">이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-276">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="f06ee-277">이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-277">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="f06ee-278">Priority 매개 변수를  사용하지 않을 것이기 때문에 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-278">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="f06ee-279">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="f06ee-279">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="f06ee-280">PowerShell을 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="f06ee-280">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="f06ee-281">기존 피싱 방지 정책을 보기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-281">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f06ee-282">이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-282">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="f06ee-283">이 예에서는 Executives라는 피싱 방지 정책의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-283">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="f06ee-284">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="f06ee-284">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="f06ee-285">PowerShell을 사용하여 피싱 방지 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="f06ee-285">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="f06ee-286">기존 피싱 방지 규칙을 보시다시피 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-286">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f06ee-287">이 예에서는 지정된 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-287">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="f06ee-288">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-288">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="f06ee-289">이 예에서는 Contoso Executives라는 피싱 방지 규칙의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-289">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="f06ee-290">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule 을 참조하십시오.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="f06ee-290">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="f06ee-291">PowerShell을 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="f06ee-291">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="f06ee-292">다음 항목 이외에도 [1단계: PowerShell을](#step-1-use-powershell-to-create-an-anti-phish-policy) 사용하여 피싱 방지 정책을 만들기에 설명된 대로 PowerShell에서 피싱 방지 정책을 수정할 때와 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-292">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="f06ee-293">지정된 정책을 기본 정책으로 전환하는 _MakeDefault_ 스위치는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다(모든 사용자에 적용, 항상 최하위 우선 순위 및 삭제할 수 없습니다). </span><span class="sxs-lookup"><span data-stu-id="f06ee-293">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="f06ee-294">피싱 방지 정책의 이름을 다시 설정할 수 **없습니다(Set-AntiPhishPolicy** cmdlet에는 Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="f06ee-294">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f06ee-295">Microsoft 365 Defender 포털에서 피싱 방지 정책의 이름을 Microsoft 365 Defender 피싱 방지 규칙의 이름만 다시 _정합니다._</span><span class="sxs-lookup"><span data-stu-id="f06ee-295">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="f06ee-296">피싱 방지 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-296">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f06ee-297">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="f06ee-297">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="f06ee-298">PowerShell을 사용하여 피싱 방지 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="f06ee-298">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="f06ee-299">PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용하지 않도록 설정된 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-299">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f06ee-300">기존 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06ee-300">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="f06ee-301">그렇지 않으면 이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 피싱 방지 규칙 섹션에 설명된 대로 규칙을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-301">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="f06ee-302">피싱 방지 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-302">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f06ee-303">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule 을 참조하십시오.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="f06ee-303">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="f06ee-304">PowerShell을 사용하여 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f06ee-304">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="f06ee-305">PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-305">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="f06ee-306">기본 피싱 방지 정책은 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="f06ee-306">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="f06ee-307">PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-307">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="f06ee-308">이 예에서는 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-308">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f06ee-309">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-309">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f06ee-310">구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 및 [Disable-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="f06ee-310">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="f06ee-311">PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="f06ee-311">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="f06ee-312">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-312">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f06ee-313">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-313">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f06ee-314">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-314">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f06ee-315">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-315">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f06ee-316">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-316">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f06ee-317">PowerShell에서 피싱 방지 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-317">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f06ee-318">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-318">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="f06ee-319">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="f06ee-319">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f06ee-320">**참고:**</span><span class="sxs-lookup"><span data-stu-id="f06ee-320">**Notes**:</span></span>

- <span data-ttu-id="f06ee-321">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-AntiPhishRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-321">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="f06ee-322">기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없습니다. 또한 항상 가장 낮은 우선 순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-322">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="f06ee-323">PowerShell을 사용하여 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="f06ee-323">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="f06ee-324">PowerShell을 사용하여 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-324">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="f06ee-325">PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-325">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f06ee-326">이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-326">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f06ee-327">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="f06ee-327">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="f06ee-328">PowerShell을 사용하여 피싱 방지 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="f06ee-328">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="f06ee-329">PowerShell을 사용하여 피싱 방지 규칙을 제거하면 해당 피싱 방지 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-329">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="f06ee-330">PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-330">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="f06ee-331">이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-331">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f06ee-332">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="f06ee-332">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f06ee-333">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="f06ee-333">How do you know these procedures worked?</span></span>

<span data-ttu-id="f06ee-334">EOP에서 피싱 방지 정책을 성공적으로 구성한 경우 다음 단계를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="f06ee-334">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="f06ee-335">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 및 규칙 위협 정책 & 피싱 방지 \>  \>  \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-335">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="f06ee-336">정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="f06ee-336">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f06ee-337">자세한 내용을 보려면 이름을 클릭하고 나타나는 플라이아웃에서 세부 정보를 확인하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-337">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="f06ee-338">PowerShell Exchange Online 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f06ee-338">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
