---
title: Microsoft Defender for Office 365에서 피싱 방지 정책 구성
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
description: 관리자는 Office 365용 Microsoft Defender를 사용하여 조직에서 사용할 수 있는 고급 피싱 방지 정책을 만들고 수정하고 삭제하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c8d61aee9afb332a8426890560ad221a9c87c7d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204987"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-103">Microsoft Defender for Office 365에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9e47f-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9e47f-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="9e47f-104">**Applies to**</span></span>
- [<span data-ttu-id="9e47f-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="9e47f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9e47f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e47f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9e47f-107">[Microsoft Defender for Office 365의](defender-for-office-365.md) 피싱 방지 정책은 악의적인 가장 기반 피싱 공격 및 기타 유형의 피싱 공격으로부터 조직을 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="9e47f-108">EOP(Exchange Online Protection)의 피싱 방지 정책과 Office 365용 Microsoft Defender의 피싱 방지 정책 간의 차이점에 대한 자세한 내용은 피싱 방지 보호를 [참조하세요.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9e47f-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="9e47f-109">관리자는 기본 피싱 방지 정책을 보고 편집하고 구성할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="9e47f-110">세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 피싱 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="9e47f-111">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="9e47f-112">보안 및 준수 센터 또는 Exchange Online PowerShell에서 피싱 & 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="9e47f-113">Exchange Online Protection 조직(즉, Office 365용 Microsoft Defender가 없는 조직)에서 사용할 수 있는 피싱 방지 정책에서 더 제한적인 구성에 대한 자세한 내용은 [EOP에서](configure-anti-phishing-policies-eop.md)피싱 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="9e47f-114">피싱 방지 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="9e47f-115">**피싱** 방지 정책: 사용하도록 설정하거나 사용하지 않도록 설정할 피싱 보호와 옵션을 적용할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="9e47f-116">**피싱** 방지 규칙: 피싱 방지 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="9e47f-117">보안 및 준수 센터에서 피싱 방지 정책을 관리할 때 이러한 두 요소의 & 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9e47f-118">정책을 만들 때 실제로 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="9e47f-119">정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 피싱 방지 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="9e47f-120">다른 모든 설정은 연결된 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="9e47f-121">정책을 제거하면 피싱 방지 규칙 및 연결된 피싱 방지 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="9e47f-122">Exchange Online PowerShell에서는 정책과 규칙을 별도로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="9e47f-123">자세한 내용은 이 문서 부분의 [Microsoft Defender for Office 365에서 Exchange Online PowerShell을](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) 사용하여 피싱 방지 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="9e47f-124">모든 Microsoft Defender for Office 365 조직에는 다음 속성이 있는 Office365 AntiPhish Default라는 기본 제공 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="9e47f-125">이 정책은 정책과 연결된 피싱 방지 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="9e47f-126">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="9e47f-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="9e47f-127">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="9e47f-128">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="9e47f-129">Microsoft Defender for Office 365에서 피싱 방지 보호의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9e47f-130">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="9e47f-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9e47f-131"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9e47f-132">**ATP** 피싱 방지 페이지로 직접 이동하기 위해 를 <https://protection.office.com/antiphishing> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="9e47f-133">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9e47f-134">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9e47f-135">피싱 방지 정책을 추가, 수정 및 삭제하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9e47f-136">피싱 방지 정책에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 의 구성원이 <sup>\*</sup> 되거나.</span><span class="sxs-lookup"><span data-stu-id="9e47f-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="9e47f-137">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="9e47f-138">**참고**:</span><span class="sxs-lookup"><span data-stu-id="9e47f-138">**Notes**:</span></span>

  - <span data-ttu-id="9e47f-139">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9e47f-140">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="9e47f-141">[또한 Exchange Online의](/Exchange/permissions-exo/permissions-exo#role-groups) 보기 **전용 조직** 관리 역할 그룹은 기능에 대한 읽기 전용 액세스 권한을 <sup>\*</sup> 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="9e47f-142"><sup>\*</sup> 보안 & 준수 센터에서 읽기 전용 액세스를 통해 사용자는 사용자 지정 피싱 방지 정책의 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="9e47f-143">읽기 전용 사용자는 기본 피싱 방지 정책의 설정을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="9e47f-144">Microsoft Defender for Office 365의 피싱 방지 정책에 대한 권장 설정은 [Defender for Office 365 설정의](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)피싱 방지 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="9e47f-145">새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="9e47f-146">필터링 파이프라인에서 피싱 방지 정책이 적용되는 위치는 전자 메일 보호의 순서 및 우선 [순위를 참조하세요.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="9e47f-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-147">보안 및 & 센터를 사용하여 Microsoft Defender for Office 365에서 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9e47f-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9e47f-148">보안 & 준수 센터에서 사용자 지정 피싱 방지 정책을 만들면 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="9e47f-149">피싱 방지 정책을 만들 때 정책이 적용되는 사람을 식별하는 정책 이름, 설명 및 받는 사람 필터만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="9e47f-150">정책을 만든 후 기본 피싱 방지 설정을 변경하거나 검토하도록 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="9e47f-151">보안 및 & 센터에서 위협 **관리** 정책 ATP 피싱 방지 로 \>  \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9e47f-152">피싱 **방지 페이지에서** 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="9e47f-153">새 피싱 방지 정책 **만들기 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="9e47f-154">정책 **이름 지정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="9e47f-155">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="9e47f-156">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="9e47f-157">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9e47f-158">적용 **대상** 페이지가 나타나면 정책이 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="9e47f-159">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9e47f-160">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="9e47f-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9e47f-161">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="9e47f-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="9e47f-162">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-162">Click **Add a condition**.</span></span> <span data-ttu-id="9e47f-163">나타나는 드롭다운에서 적용된 조건(있는 **경우)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="9e47f-164">**받는 사람:** 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="9e47f-165">**받는 사람이 :의 구성원입니다.** 조직에서 하나 이상의 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="9e47f-166">**받는 사람 도메인은**: 조직에서 구성된 하나 이상의 허용 도메인에 있는 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="9e47f-167">조건을 선택하면 해당 드롭다운이 다음 상자와 **함께** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="9e47f-168">상자를 클릭하고 선택할 값 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="9e47f-169">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="9e47f-170">값을 더 추가하려면 상자의 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="9e47f-171">개별 항목을 제거하려면 값에서 **제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="9e47f-172">전체 조건을 제거하려면 **조건에서** 제거 ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="9e47f-173">조건을 더 추가하려면 조건 추가를 **클릭하고** 적용된 경우 아래에서 나머지 **값을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="9e47f-174">예외를 추가하려면 조건 추가를 **클릭하고** 다음의 경우 **제외에서 예외를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="9e47f-175">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9e47f-176">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9e47f-177">나타나는 **설정** 검토 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="9e47f-178">각 설정에서 **편집을** 클릭하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9e47f-179">완료되면 이 정책 만들기 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="9e47f-180">나타나는 **확인** 대화 상자에서 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="9e47f-181">이러한 일반 설정을 사용하여 피싱 방지 정책을 만든 후 다음 섹션의 지침을 사용하여 정책의 보호 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-182">보안 및 & 센터를 사용하여 Microsoft Defender for Office 365에서 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="9e47f-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9e47f-183">다음 절차에 따라 피싱 방지 정책(만든 새 정책 또는 이미 사용자 지정한 기존 정책)을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="9e47f-184">아직 없는 경우 보안 및 준수 센터를 & 위협 **관리** 정책 ATP 피싱 방지 \>  \> **로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9e47f-185">수정할 사용자 지정 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="9e47f-186">이미 선택되어 있는 경우 선택을 선택하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="9e47f-187">정책 **편집 \<name\> 플라이아웃이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="9e47f-188">모든 **섹션에서** 편집을 클릭하면 해당 섹션의 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="9e47f-189">다음 단계는 섹션이 나타나는 순서대로 나타나지만 순서는 없습니다(순서에 따라 섹션을 선택하고 수정할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="9e47f-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="9e47f-190">섹션에서  편집을 클릭하면 사용 가능한 설정이 마법사 형식으로 제공되지만 원하는 순서로 페이지 내에서 이동하고,    ![ ](../../media/scc-remove-icon.png) **\<name\>** 원하는 페이지에서 저장을 클릭하거나 취소 또는 닫기 아이콘을 클릭하여 정책 편집 페이지로 돌아올 수 있습니다(저장하거나 남기기 위해 마법사의 마지막 페이지를 방문할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="9e47f-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="9e47f-191">**정책 설정:** **편집을** 클릭하여 이전 섹션에서 [](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) 정책을 만들 때 사용 가능한 설정과 동일한 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="9e47f-192">**이름**</span><span class="sxs-lookup"><span data-stu-id="9e47f-192">**Name**</span></span>
   - <span data-ttu-id="9e47f-193">**설명**</span><span class="sxs-lookup"><span data-stu-id="9e47f-193">**Description**</span></span>
   - <span data-ttu-id="9e47f-194">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="9e47f-194">**Applied to**</span></span>
   - <span data-ttu-id="9e47f-195">**설정 검토**</span><span class="sxs-lookup"><span data-stu-id="9e47f-195">**Review your settings**</span></span>

   <span data-ttu-id="9e47f-196">완료되면 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="9e47f-197">**가장: 편집을** **클릭하여** 정책에서 보호된 보낸 사람 및 보호된 도메인을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="9e47f-198">이러한 설정은 인바운드 메시지의 보낸 사람 주소에서 검색할 스푸핑된 보낸 사람(개별적으로 또는 도메인별)을 식별하는 정책의 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="9e47f-199">자세한 내용은 [Microsoft Defender for Office 365의](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)피싱 방지 정책의 가장 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="9e47f-200">**보호할 사용자 추가**: 기본값은 **Off입니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="9e47f-201">이 기능을 켜려면 토글을 **켜고** 나타나는 사용자  추가 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="9e47f-202">나타나는 **사용자 추가** 플라이아웃에서 다음 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="9e47f-203">**전자 메일 주소**:</span><span class="sxs-lookup"><span data-stu-id="9e47f-203">**Email address**:</span></span>

       - <span data-ttu-id="9e47f-204">상자를 클릭하고 선택할 사용자 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="9e47f-205">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="9e47f-206">항목을 제거하려면 사용자의  제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="9e47f-207">**이름:** 이 값은 선택한 전자 메일 주소를 기준으로 채워지지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="9e47f-208">완료되면 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="9e47f-209">기존 항목을 편집하려면 목록에서 보호된 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="9e47f-210">각 피싱 방지 정책에서 보호되는 사용자(보낸 사람 전자 메일 주소)를 최대 60명까지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="9e47f-211">동일한 보호된 사용자를 여러 정책에 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="9e47f-212">보낸 사람 및 받는 사람이 이전에 전자 메일을 통해 통신한 경우 사용자 가장 보호가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="9e47f-213">보낸 사람 및 받는 사람이 전자 메일을 통해 통신한 적이 없는 경우 가장 시도로 메시지가 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="9e47f-214">**보호할 도메인** 추가: 다음 설정 중 하나 또는 둘 다를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="9e47f-215">**소유한 도메인** 자동 포함: 기본값은 **Off입니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="9e47f-216">켜기 위해 토글을 켜고 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="9e47f-217">**사용자 지정 도메인 포함**: 기본값은 **Off입니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="9e47f-218">켜기하려면 토글을 **켜고** 도메인 추가 상자에 도메인 이름(예: contoso.com)을 입력하고 Enter를 누르고 필요에 따라 반복합니다. </span><span class="sxs-lookup"><span data-stu-id="9e47f-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="9e47f-219">모든 피싱 방지 정책에는 최대 50개 도메인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="9e47f-220">**작업:** 편집 **클릭**</span><span class="sxs-lookup"><span data-stu-id="9e47f-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="9e47f-221">**가장된** 사용자가 전자 메일을 보낸 경우: 스푸핑된 보낸 사람이 보호할 사용자 추가에서 지정한 보호된 사용자 중 하나인 메시지에 대해 다음 작업 중 하나를 **구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="9e47f-222">**어떤 작업도 적용하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="9e47f-223">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="9e47f-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="9e47f-224">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="9e47f-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="9e47f-225">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="9e47f-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="9e47f-226">**메시지를 배달하고 Bcc 줄에 다른 주소를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="9e47f-227">**배달되기 전에 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="9e47f-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="9e47f-228">**가장된** 도메인에서 전자 메일을 보내는 경우: 스푸핑된 보낸 사람이 보호할 도메인 추가에서 지정한 보호된 도메인 중 하나에 있는 메시지에 대해 다음 작업 중 하나를 **구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="9e47f-229">**어떤 작업도 적용하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="9e47f-230">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="9e47f-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="9e47f-231">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="9e47f-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="9e47f-232">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="9e47f-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="9e47f-233">**메시지를 배달하고 Bcc 줄에 다른 주소를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="9e47f-234">**배달되기 전에 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="9e47f-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="9e47f-235">가장 보안 팁 켜기 를 **클릭하고** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="9e47f-236">**가장된** 사용자에 대한 팁 표시 : 기본값은 **Off입니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="9e47f-237">켜기 위해 토글을 켜고 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="9e47f-238">**가장된** 도메인에 대한 팁 표시 : 기본값은 **Off입니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="9e47f-239">켜기 위해 토글을 켜고 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="9e47f-240">**비정상적인 문자에 대한** 팁 표시 : 기본값은 **Off입니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="9e47f-241">켜기 위해 토글을 켜고 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="9e47f-242">작업을 마친 후 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="9e47f-243">**사서함 인텔리전스**:</span><span class="sxs-lookup"><span data-stu-id="9e47f-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="9e47f-244">**사서함 인텔리전스 사용:** 기본값은 **입니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="9e47f-245">끄기 위해 토글을 끄기 로 **밀어 끄기합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="9e47f-246">**사서함 인텔리전스 기반** 가장 보호 사용: 이 설정은 사서함 인텔리전스 사용이 설정되어 있는 **경우** 에서만 사용할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="9e47f-247">사서함 인텔리전스 결과에서 가장 검색에 대해 메시지에 대해 수행되는 작업을 지정하기 위해 이 설정을 으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="9e47f-248">**가장된** 사용자가 전자 메일을 보낸 경우 다음 작업 중 하나를 지정할 수 있습니다(보호된 사용자 및 보호된 도메인에 사용할 수 있는 동일한 작업).</span><span class="sxs-lookup"><span data-stu-id="9e47f-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="9e47f-249">아무 작업도 **적용하지** 않습니다. 이 값은 사서함 인텔리전스 사용 설정과 결과가 같지만 사서함 인텔리전스 기반 가장 보호 사용은 **해제합니다.** </span><span class="sxs-lookup"><span data-stu-id="9e47f-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="9e47f-250">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="9e47f-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="9e47f-251">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="9e47f-251">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="9e47f-252">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="9e47f-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="9e47f-253">**메시지를 배달하고 Bcc 줄에 다른 주소를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="9e47f-254">**배달되기 전에 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="9e47f-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="9e47f-255">**신뢰할 수 있는 보낸 사람 및 도메인 추가:** 정책에 대한 예외를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="9e47f-256">**신뢰할 수 있는 보낸 사람**:</span><span class="sxs-lookup"><span data-stu-id="9e47f-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="9e47f-257">상자를 클릭하고 선택할 사용자 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="9e47f-258">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="9e47f-259">항목을 제거하려면 사용자의  제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="9e47f-260">**신뢰할 수** 있는 도메인: 도메인 이름(예: contoso.com)을 입력하고 Enter를 누르고 필요에 따라 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="9e47f-261">**설정 검토:** 각 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="9e47f-262">각 **섹션에서 편집을** 클릭하여 관련 페이지로 다시 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="9e47f-263">이 페이지에서 직접 다음 설정을  **설정 또는** 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="9e47f-264">**보호된 사용자**</span><span class="sxs-lookup"><span data-stu-id="9e47f-264">**Protected users**</span></span>
       - <span data-ttu-id="9e47f-265">**보호된 도메인** \> **소유한 도메인 포함**</span><span class="sxs-lookup"><span data-stu-id="9e47f-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="9e47f-266">**보호된 도메인** \> **보호된 도메인(사용자** 지정 도메인)</span><span class="sxs-lookup"><span data-stu-id="9e47f-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="9e47f-267">**사서함 인텔리전스**</span><span class="sxs-lookup"><span data-stu-id="9e47f-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="9e47f-268">완료되면 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="9e47f-269">**스푸핑:**  편집을 클릭하여 스푸핑 인텔리전스를 켜거나 끄고, Outlook에서 확인되지 않은 보낸 사람 ID를 켜거나 끄고, 차단된 스푸핑된 보낸 사람이 보낸 메시지에 적용할 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="9e47f-270">자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="9e47f-270">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="9e47f-271">이러한 동일한 설정은 EOP의 피싱 방지 정책에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="9e47f-272">**스푸핑 필터 설정:** 기본값은 **On** 으로, 그대로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-272">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="9e47f-273">끄기 위해 토글을 끄기 로 **밀어 끄기합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-273">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="9e47f-274">자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="9e47f-274">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="9e47f-275">MX 레코드가 Microsoft 365를 사용하지 않는 경우 스푸핑 방지 보호 기능을 사용하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대해 향상된 필터링을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-275">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="9e47f-276">자세한 내용은 Exchange Online에서 커넥터에 대한 [향상된 필터링을 참조하세요.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="9e47f-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="9e47f-277">**Enable Unauthenticated Sender feature**: The default value is **On**.</span><span class="sxs-lookup"><span data-stu-id="9e47f-277">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="9e47f-278">끄기 위해 토글을 끄기 로 **밀어 끄기합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-278">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="9e47f-279">**작업:** 스푸핑 인텔리전스에 실패한 메시지에 대해 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-279">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="9e47f-280">**도메인을 스푸핑할** 수 없는 사람이 전자 메일을 보낸 경우:</span><span class="sxs-lookup"><span data-stu-id="9e47f-280">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="9e47f-281">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="9e47f-281">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="9e47f-282">**메시지 Quarantine the message**</span><span class="sxs-lookup"><span data-stu-id="9e47f-282">**Quarantine the message**</span></span>

   - <span data-ttu-id="9e47f-283">**설정 검토:** 각 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-283">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="9e47f-284">각 **섹션에서 편집을** 클릭하여 관련 페이지로 다시 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-284">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="9e47f-285">이 페이지에서 직접 다음 설정을  **설정 또는** 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-285">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="9e47f-286">**스푸핑 방지 보호 사용**</span><span class="sxs-lookup"><span data-stu-id="9e47f-286">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="9e47f-287">**비인식 보낸 사람 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="9e47f-287">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="9e47f-288">완료되면 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-288">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="9e47f-289">**고급 설정:** **편집을 클릭하여** 고급 피싱 임계값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-289">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="9e47f-290">자세한 내용은 [Microsoft Defender for Office 365의](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)피싱 방지 정책의 고급 피싱 임계값을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-290">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="9e47f-291">**고급 피싱 임계값:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-291">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="9e47f-292">**1 -** 표준(기본값)</span><span class="sxs-lookup"><span data-stu-id="9e47f-292">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="9e47f-293">**2 - 적극적**</span><span class="sxs-lookup"><span data-stu-id="9e47f-293">**2 - Aggressive**</span></span>
   - <span data-ttu-id="9e47f-294">**3 - 보다 적극적**</span><span class="sxs-lookup"><span data-stu-id="9e47f-294">**3 - More aggressive**</span></span>
   - <span data-ttu-id="9e47f-295">**4 - 가장 적극적인**</span><span class="sxs-lookup"><span data-stu-id="9e47f-295">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="9e47f-296">**설정 검토:** **편집을** 클릭하여 고급 피싱 임계값 **페이지로 다시** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-296">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="9e47f-297">완료되면 두 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-297">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="9e47f-298">정책 편집 **\<Name\> 페이지에서** 설정을 검토한 다음 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-298">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-299">보안 및 & 센터를 사용하여 Microsoft Defender for Office 365의 기본 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="9e47f-299">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9e47f-300">Microsoft Defender for Office 365의 기본 피싱 방지 정책의 이름은 Office365 AntiPhish Default로 지정되어 있으며 정책 목록에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-300">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="9e47f-301">기본 피싱 방지 정책을 수정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-301">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="9e47f-302">보안 및 & 센터에서 위협 **관리** 정책 ATP 피싱 방지 로 \>  \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-302">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9e47f-303">피싱 **방지 페이지에서** 기본 정책 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-303">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="9e47f-304">정책 **편집 Office365 AntiPhish Default 페이지가** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-304">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="9e47f-305">사용자 지정 정책을 수정할 때 동일한 설정을 포함하는 다음 섹션을 사용할 [수 있습니다.](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="9e47f-305">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="9e47f-306">**가장**</span><span class="sxs-lookup"><span data-stu-id="9e47f-306">**Impersonation**</span></span>
   - <span data-ttu-id="9e47f-307">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="9e47f-307">**Spoof**</span></span>
   - <span data-ttu-id="9e47f-308">**고급 설정**</span><span class="sxs-lookup"><span data-stu-id="9e47f-308">**Advanced settings**</span></span>

   <span data-ttu-id="9e47f-309">기본 정책을 수정할 때 다음 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-309">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="9e47f-310">정책 설정  섹션과 값을 볼 수 있지만  편집 링크는 있으므로 설정(정책 이름, 설명 및 정책이 적용되는 사람)을 수정할 수 없습니다(모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="9e47f-310">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="9e47f-311">기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-311">You can't delete the default policy.</span></span>
   - <span data-ttu-id="9e47f-312">기본 정책의 우선 순위는 변경할 수 없습니다(항상 마지막에 적용).</span><span class="sxs-lookup"><span data-stu-id="9e47f-312">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="9e47f-313">정책 **편집 Office365 AntiPhish Default 페이지에서** 설정을 검토하고 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-313">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-314">Microsoft Defender for Office 365에서 사용자 지정 피싱 방지 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9e47f-314">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="9e47f-315">보안 및 & 센터에서 위협 **관리** 정책 ATP 피싱 방지 로 \>  \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-315">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9e47f-316">상태 열의 **값을 확인할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-316">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="9e47f-317">토글을 해제로 **밀어** 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-317">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="9e47f-318">토글을 **으로 밀어 정책을** 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-318">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="9e47f-319">기본 피싱 방지 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-319">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-320">Microsoft Defender for Office 365에서 사용자 지정 피싱 방지 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="9e47f-320">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9e47f-321">기본적으로 피싱 방지 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="9e47f-321">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="9e47f-322">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="9e47f-322">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9e47f-323">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-323">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="9e47f-324">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-324">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="9e47f-325">사용자 지정 피싱 방지 정책은 처리되는 순서대로 표시됩니다(첫 번째  정책의 우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="9e47f-325">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="9e47f-326">Office365 AntiPhish Default라는 기본 피싱 방지 정책의 사용자 지정 우선 순위 값은 **가장** 낮습니다. 이 정책은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-326">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="9e47f-327">**참고:** 보안 & 준수 센터에서 피싱 방지 정책의 우선 순위를 변경한 후에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-327">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="9e47f-328">PowerShell에서 피싱 방지 규칙을 만들 때 기본 우선 순위를 다시 지정하여 기존 규칙의 우선 순위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-328">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="9e47f-329">정책의 우선 순위를 변경하려면 정책  속성에서 우선 순위 늘리기 또는 우선 순위  감소를 클릭합니다(보안 및 준수 센터에서 우선 순위 번호를 직접 수정할 & 없습니다). </span><span class="sxs-lookup"><span data-stu-id="9e47f-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="9e47f-330">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="9e47f-331">보안 및 & 센터에서 위협 **관리** 정책 ATP 피싱 방지 로 \>  \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9e47f-332">수정할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-332">Select the policy that you want to modify.</span></span> <span data-ttu-id="9e47f-333">이미 선택되어 있는 경우 선택을 선택하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-333">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="9e47f-334">정책 **편집 \<name\> 플라이아웃이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-334">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="9e47f-335">우선 순위 값이 **0인**  사용자 지정 피싱 방지 정책에는 사용 가능한 우선 순위 감소 **단추만** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-335">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="9e47f-336">우선 순위 값이 가장 낮은 사용자  지정 피싱 방지 정책(예: **3)에는** 우선 순위 늘리기 단추만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-336">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="9e47f-337">사용자 지정 피싱 방지 정책이 세 개 이상 있는 경우 우선 순위가 가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 단추를 모두 사용할 **수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9e47f-337">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="9e47f-338">우선 **순위 늘리기 또는** **우선** 순위 감소를 클릭하여 우선 순위 값을 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-338">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="9e47f-339">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-339">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-340">보안 및 & 센터를 사용하여 Microsoft Defender for Office 365에서 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="9e47f-340">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="9e47f-341">보안 & 준수 센터에서 위협 관리  정책 ATP 피싱 방지 \>  \> **로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-341">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9e47f-342">다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-342">Do one of the following steps:</span></span>

   - <span data-ttu-id="9e47f-343">보하려는 사용자 지정 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-343">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="9e47f-344">이미 선택되어 있는 경우 선택을 선택하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-344">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="9e47f-345">기본 **정책을 클릭하여** 기본 피싱 방지 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-345">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="9e47f-346">설정 **및 \<name\> 값을** 볼 수 있는 정책 편집 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-346">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-347">보안 및 & 센터를 사용하여 Microsoft Defender for Office 365에서 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="9e47f-347">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="9e47f-348">보안 및 & 센터에서 위협 **관리** 정책 ATP 피싱 방지 로 \>  \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-348">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9e47f-349">제거할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-349">Select the policy that you want to remove.</span></span> <span data-ttu-id="9e47f-350">이미 선택되어 있는 경우 선택을 선택하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-350">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="9e47f-351">정책 **편집 플라이아웃이 \<name\>** 나타나면 정책 삭제를 클릭한 다음 나타나는 경고 대화 상자에서 예를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="9e47f-351">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="9e47f-352">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-352">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9e47f-353">Exchange Online PowerShell을 사용하여 Office 365용 Microsoft Defender에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9e47f-353">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9e47f-354">앞서 설명한 바와 같이 스팸 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-354">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="9e47f-355">Exchange Online PowerShell에서는 피싱 방지 정책과 피싱 방지 규칙의 차이점이 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-355">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="9e47f-356">**\* -AntiPhishPolicy** cmdlet을 사용하여 피싱 방지 정책을 관리하고 - **\* AntiPhishRule** cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-356">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="9e47f-357">PowerShell에서 먼저 피싱 방지 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-357">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="9e47f-358">PowerShell에서는 피싱 방지 정책 및 피싱 방지 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-358">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="9e47f-359">PowerShell에서 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-359">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="9e47f-360">PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9e47f-360">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="9e47f-361">PowerShell에서 피싱 방지 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-361">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9e47f-362">피싱 방지 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-362">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="9e47f-363">규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-363">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="9e47f-364">**참고:**</span><span class="sxs-lookup"><span data-stu-id="9e47f-364">**Notes**:</span></span>

- <span data-ttu-id="9e47f-365">새 피싱 방지 규칙을 만들고 기존의 통합되지 않은 피싱 방지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-365">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="9e47f-366">피싱 방지 규칙은 두 개 이상의 피싱 방지 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-366">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="9e47f-367">정책을 만든 후까지 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새로운 피싱 방지 정책에 대해 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-367">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="9e47f-368">새 정책을 사용하지 않도록 `$false` **설정(New-AntiPhishRule** cmdlet에서 사용)으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-368">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="9e47f-369"> _\<Number\>_ **New-AntiPhishRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e47f-369">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="9e47f-370">PowerShell에서 만든 새로운 피싱 방지 정책은 피싱 방지 규칙에 정책을 할당할 때까지 & 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-370">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="9e47f-371">1단계: PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9e47f-371">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="9e47f-372">피싱 방지 정책을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-372">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="9e47f-373">이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-373">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="9e47f-374">정책이 사용하도록 설정됩니다(Enabled 매개  변수를 사용하지 않습니다. 기본값은 `$true` 입니다).</span><span class="sxs-lookup"><span data-stu-id="9e47f-374">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="9e47f-375">설명은 리서치 부서 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-375">The description is: Research department policy.</span></span>
- <span data-ttu-id="9e47f-376">모든 허용 도메인에 대해 조직 도메인 보호를 설정하고 대상 도메인에 대한 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="9e47f-376">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="9e47f-377">가장으로부터 보호할 사용자로 Mai Fujito(mfujito@fabrikam.com)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-377">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="9e47f-378">사서함 인텔리전스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-378">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="9e47f-379">사서함 인텔리전스 보호를 사용하며, 검역 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-379">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="9e47f-380">안전 팁을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-380">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="9e47f-381">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy 를 참조하십시오.](/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="9e47f-381">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="9e47f-382">2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="9e47f-382">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="9e47f-383">피싱 방지 규칙을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-383">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="9e47f-384">이 예에서는 다음 조건을 통해 Research Department라는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-384">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="9e47f-385">이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-385">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="9e47f-386">이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-386">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="9e47f-387">Priority 매개 변수를  사용하지 않을 것이기 때문에 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-387">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="9e47f-388">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="9e47f-388">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="9e47f-389">PowerShell을 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="9e47f-389">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="9e47f-390">기존 피싱 방지 정책을 보기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-390">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9e47f-391">이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-391">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="9e47f-392">이 예에서는 Executives라는 피싱 방지 정책의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-392">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="9e47f-393">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="9e47f-393">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="9e47f-394">PowerShell을 사용하여 피싱 방지 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="9e47f-394">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="9e47f-395">기존 피싱 방지 규칙을 보시다시피 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-395">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9e47f-396">이 예에서는 지정된 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-396">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="9e47f-397">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-397">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="9e47f-398">이 예에서는 Contoso Executives라는 피싱 방지 규칙의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-398">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="9e47f-399">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule 을 참조하십시오.](/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="9e47f-399">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="9e47f-400">PowerShell을 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="9e47f-400">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="9e47f-401">다음 항목 이외에도 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-an-anti-phish-policy) 사용하여 피싱 방지 정책 만들기 섹션에 설명된 대로 PowerShell에서 피싱 방지 정책을 수정할 때와 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-401">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="9e47f-402">지정된 정책을 기본 정책으로 전환하는 _MakeDefault_ 스위치는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다(모든 사용자에 적용, 항상 최하위 우선 순위 및 삭제할 수 없습니다). </span><span class="sxs-lookup"><span data-stu-id="9e47f-402">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="9e47f-403">피싱 방지 정책의 이름을 다시 설정할 수 **없습니다(Set-AntiPhishPolicy** cmdlet에는 Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="9e47f-403">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9e47f-404">보안 및 준수 센터에서 피싱 방지 정책의 이름을 & 피싱 방지 규칙의 이름만 다시 _매기게 됩니다._</span><span class="sxs-lookup"><span data-stu-id="9e47f-404">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="9e47f-405">피싱 방지 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-405">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9e47f-406">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="9e47f-406">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="9e47f-407">PowerShell을 사용하여 피싱 방지 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="9e47f-407">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="9e47f-408">PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용하지 않도록 설정된 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-408">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9e47f-409">기존 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-409">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="9e47f-410">그렇지 않으면 PowerShell에서 피싱 방지 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-410">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="9e47f-411">이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 피싱 방지 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-411">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="9e47f-412">피싱 방지 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-412">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9e47f-413">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule 을 참조하십시오.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="9e47f-413">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="9e47f-414">PowerShell을 사용하여 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9e47f-414">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="9e47f-415">PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-415">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="9e47f-416">기본 피싱 방지 정책은 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="9e47f-416">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="9e47f-417">PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-417">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="9e47f-418">이 예에서는 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-418">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="9e47f-419">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-419">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="9e47f-420">구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) 및 [Disable-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="9e47f-420">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="9e47f-421">PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="9e47f-421">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="9e47f-422">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-422">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9e47f-423">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-423">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9e47f-424">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-424">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9e47f-425">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-425">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9e47f-426">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-426">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9e47f-427">PowerShell에서 피싱 방지 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-427">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9e47f-428">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-428">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="9e47f-429">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="9e47f-429">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9e47f-430">**참고:**</span><span class="sxs-lookup"><span data-stu-id="9e47f-430">**Notes**:</span></span>

- <span data-ttu-id="9e47f-431">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-AntiPhishRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-431">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="9e47f-432">기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없습니다. 또한 항상 가장 낮은 우선 순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-432">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="9e47f-433">PowerShell을 사용하여 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="9e47f-433">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="9e47f-434">PowerShell을 사용하여 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-434">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="9e47f-435">PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-435">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9e47f-436">이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-436">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9e47f-437">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="9e47f-437">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="9e47f-438">PowerShell을 사용하여 피싱 방지 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="9e47f-438">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="9e47f-439">PowerShell을 사용하여 피싱 방지 규칙을 제거하면 해당 피싱 방지 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-439">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="9e47f-440">PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-440">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="9e47f-441">이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-441">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="9e47f-442">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참조하십시오.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="9e47f-442">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9e47f-443">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="9e47f-443">How do you know these procedures worked?</span></span>

<span data-ttu-id="9e47f-444">Microsoft Defender for Office 365에서 피싱 방지 정책을 성공적으로 구성한 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-444">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="9e47f-445">보안 및 & 센터에서 위협 **관리** 정책 ATP 피싱 방지 로 \>  \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-445">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="9e47f-446">정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e47f-446">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="9e47f-447">자세한 내용을 확인하기 위해 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-447">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="9e47f-448">목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-448">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="9e47f-449">기본 **정책을 클릭하고** 플라이아웃에서 세부 정보를 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e47f-449">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="9e47f-450">Exchange Online PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 \<Name\> 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9e47f-450">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```