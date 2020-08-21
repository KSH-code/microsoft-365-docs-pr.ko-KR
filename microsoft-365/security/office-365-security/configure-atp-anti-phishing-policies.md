---
title: ATP 피싱 방지 정책 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Office 365 ATP(Advanced Threat Protection) 기능을 사용하는 조직에서 사용할 수 있는 고급 피싱 방지 정책을 만들고, 수정하고, 삭제하는 방법을 알아내고,
ms.openlocfilehash: f7770945e6b99a3d2f3fa2b12daa13b2cc3c2612
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825740"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-103">ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="73fb3-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="73fb3-104">ATP 피싱 방지 정책은 Office [365 Advanced Threat Protection의 일부입니다.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="73fb3-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="73fb3-105">ATP 피싱 방지 정책은 악의적인 가장 기반의 피싱 공격과 다른 유형의 피싱 공격으로부터 조직을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="73fb3-106">EOP(Exchange Online Protection)의 피싱 방지 정책과 ATP 피싱 방지 정책 간의 차이에 대한 자세한 내용은 [피싱 방지 보호 기능을 참조하십시오.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="73fb3-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="73fb3-107">관리자는 기본 ATP 피싱 방지 정책을 보고, 편집하고, 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="73fb3-108">세분성을 상세히 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 ATP 피싱 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="73fb3-109">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="73fb3-110">보안 정책 준수 센터 또는 Exchange Online PowerShell에서 ATP & 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="73fb3-111">Exchange Online Protection 조직(즉, Office 365 ATP가 없는 Microsoft 365 조직)에서 사용할 수 있는 보다 제한적인 피싱 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서 피싱 방지 정책 구성을 참조하세요.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="73fb3-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="73fb3-112">보안 센터의 ATP 피싱 방지 정책이 & PowerShell</span><span class="sxs-lookup"><span data-stu-id="73fb3-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="73fb3-113">ATP 피싱 방지 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="73fb3-114">**피싱 방지 정책:** 사용하거나 사용하지 않도록 설정할 피싱 보호 기능과 옵션을 적용할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="73fb3-115">**피싱 방지 규칙: 피싱 방지**정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="73fb3-116">보안 준수 센터에서 ATP 피싱 방지 정책을 관리할 때, 두 가지 요소의 차이는 & 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="73fb3-117">정책을 만들면 실제로 피싱 방지 규칙과 관련된 피싱 방지 정책이 두 가지 모두 동일한 이름을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="73fb3-118">정책을 수정할 때는 이름, 우선순위, 사용안 함 및 사용 안 함 및 받는 사람 필터와 관련된 설정이 피싱 방지 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="73fb3-119">다른 모든 설정은 관련 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="73fb3-120">정책을 제거하면 피싱 방지 규칙과 관련된 피싱 방지 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="73fb3-121">Exchange Online PowerShell에서 정책과 규칙은 별도로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="73fb3-122">자세한 내용은 이 항목 [뒷부분에 나오는 ATP 피싱](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) 방지 정책 구성을 위한 Exchange Online PowerShell을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="73fb3-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="73fb3-123">모든 Office 365 ATP 조직에는 다음과 같은 속성을 포함한 Office365 AntiPhish Default라는 ATP 피싱 방지 정책이 기본으로 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="73fb3-124">정책에 연결된 피싱 방지 규칙(받는 사람 필터)이 없더라도 조직의 모든 받는 사람에게 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="73fb3-125">정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="73fb3-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="73fb3-126">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="73fb3-127">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="73fb3-128">피싱 방지 보호의 효율성을 높이기 위해서는 특정 사용자 또는 사용자 그룹에 적용되는 더 강조한 설정을 사용하여 사용자 지정 ATP 피싱 방지 정책을 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="73fb3-129">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="73fb3-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="73fb3-130"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="73fb3-131">ATP 피싱 **방지 페이지로 직접 이동하려면 을** <https://protection.office.com/antiphishing> 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="73fb3-132">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="73fb3-133">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="73fb3-134">ATP 피싱 방지 정책을 추가, 수정 및 삭제하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="73fb3-135">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="73fb3-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="73fb3-136">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="73fb3-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="73fb3-137">ATP 피싱 방지 정책에 대한 읽기 전용 액세스에 액세스하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="73fb3-138">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="73fb3-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="73fb3-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="73fb3-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="73fb3-140">ATP 피싱 방지 정책에 대한 권장 설정은 [Office ATP 피싱 방지 정책 설정을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="73fb3-140">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="73fb3-141">신게 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="73fb3-142">필터링 파이프라인에서 피싱 방지 정책을 적용한 위치에 대한 자세한 내용은 [전자 메일 보호의 순서 및 우선 순위를 참조하십시오.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="73fb3-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-143">보안 센터 & 사용하여 ATP 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="73fb3-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="73fb3-144">보안 & 준수 센터에서 사용자 지정 ATP 피싱 방지 정책을 만들면 두 가지 모두 동일한 이름을 사용하여 피싱 방지 규칙과 관련된 피싱 방지 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="73fb3-145">ATP 피싱 방지 정책을 만들 때는 정책이 적용되는 사용자를 식별하는 정책 이름, 설명 및 받는 사람 필터만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="73fb3-146">정책을 만들고 나면 정책을 수정하여 기본 피싱 방지 설정을 변경하거나 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="73fb3-147">보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="73fb3-148">피싱 **방지 페이지에서 만들기를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-148">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="73fb3-149">새 **피싱 방지 정책 만들기 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="73fb3-150">정책 이름 **지정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="73fb3-151">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="73fb3-152">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="73fb3-153">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="73fb3-154">페이지에 **정책이** 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="73fb3-155">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="73fb3-156">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="73fb3-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="73fb3-157">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="73fb3-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="73fb3-158">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-158">Click **Add a condition**.</span></span> <span data-ttu-id="73fb3-159">표시되는 드롭다운 메뉴에서 다음과 같은 경우 적용된 **조건을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-159">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="73fb3-160">**받는 사람은**: 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-160">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="73fb3-161">**받는 사람이 조직의 그룹**구성원: 조직에서 하나 이상의 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-161">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="73fb3-162">**받는 사람 도메인은:** 조직에서 구성된 허용 도메인 중 하나 이상의 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-162">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="73fb3-163">조건을 선택하면 해당 드롭다운이 다음 상자 중 **하나와 함께 나타납니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="73fb3-164">상자를 클릭하고 선택할 값 목록을 따라 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="73fb3-165">상자를 클릭하고 입력하여 목록을 필터링하고 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="73fb3-166">값을 더 추가하려면 상자에서 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="73fb3-167">개별 항목을 제거하려면 **값에서 제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="73fb3-168">전체 조건을 제거하려면 해당 **조건에서 제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="73fb3-169">조건을 더 추가하려면 조건 **추가를 클릭하고 적용된** 경우에는 나머지 **값을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="73fb3-170">예외를 추가하려면 조건 **추가를 클릭하고** 다음의 경우 제외를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-170">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="73fb3-171">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="73fb3-172">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-172">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="73fb3-173">**나타나는 설정** 검토 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="73fb3-174">각 설정에서 **편집을** 클릭하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="73fb3-175">완료되면 이 정책 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-175">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="73fb3-176">확인 **대화** 상자가 나타나면 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="73fb3-177">이러한 일반 정책 설정을 사용하여 ATP 피싱 방지 정책을 만들고 나면 다음 섹션의 지침을 사용하여 정책에서 보호 설정을 구성하십시오.</span><span class="sxs-lookup"><span data-stu-id="73fb3-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-178">보안 그룹 준수 & 사용하여 ATP 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="73fb3-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="73fb3-179">다음 절차에 따라 ATP 피싱 방지 정책, 즉 사용자가 만든 새로운 정책 또는 이미 사용자 지정된 기존 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="73fb3-180">아직 이 창에 없는 경우 보안 & 준수 센터를 연 후 **위협** 관리 \> **Policy** \> **정책 ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="73fb3-181">수정하려는 사용자 지정 ATP 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="73fb3-182">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="73fb3-183">정책 \*\* \<name\> 플라이아웃이\*\* 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="73fb3-184">섹션에서 **편집을** 클릭하면 해당 섹션의 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="73fb3-185">다음 단계는 섹션이 나타나는 순서대로 나와 있지만 순차적이지는 않습니다(순서와대로 구역을 선택하여 수정가능).</span><span class="sxs-lookup"><span data-stu-id="73fb3-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="73fb3-186">섹션에서 **편집을 클릭하면** 사용 가능한 설정이 마법사 형식으로 제공되지만 원하는 순서로 페이지 내로 이동할 수 있고, **Cancel** 페이지에서 **Close** **저장을** 클릭하거나 취소 또는 닫기 아이콘을 클릭하여 정책 편집 ![ ](../../media/scc-remove-icon.png) \*\*페이지로 돌아갈 수 \<name\> \*\* 있습니다. 마법사의 마지막 페이지를 방문하거나 저장하거나 나갈 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="73fb3-187">**정책 설정:** **편집을** 클릭하여 이전 섹션에서 정책을 만들 때 사용 [가능한 것과 동일한 설정을](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-187">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="73fb3-188">**이름**</span><span class="sxs-lookup"><span data-stu-id="73fb3-188">**Name**</span></span>
   - <span data-ttu-id="73fb3-189">**설명**</span><span class="sxs-lookup"><span data-stu-id="73fb3-189">**Description**</span></span>
   - <span data-ttu-id="73fb3-190">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="73fb3-190">**Applied to**</span></span>
   - <span data-ttu-id="73fb3-191">**설정 검토**</span><span class="sxs-lookup"><span data-stu-id="73fb3-191">**Review your settings**</span></span>

   <span data-ttu-id="73fb3-192">작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="73fb3-193">**가장: 편집을** **클릭하여** 보호된 보낸 사람 및 정책의 보호된 도메인을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-193">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="73fb3-194">이러한 설정은 인바운드 메시지의 보낸 사람 주소에서 찾을 스푸핑된 보낸 사람을 (개별적 또는 도메인으로 식별하는 정책의 조건)입니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="73fb3-195">자세한 내용은 [ATP 피싱 방지 정책의 가장 설정을 참조하십시오.](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="73fb3-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="73fb3-196">**보호할 사용자 추가:** 기본값은 **Off입니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-196">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="73fb3-197">켜려면 토글을 켜는 토글을 **클릭한**다음 나타나는 **사용자 단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-197">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="73fb3-198">표시되는 사용자 **플라이아웃** 추가에서 다음 값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="73fb3-199">**전자 메일 주소**:</span><span class="sxs-lookup"><span data-stu-id="73fb3-199">**Email address**:</span></span>

        - <span data-ttu-id="73fb3-200">상자를 클릭하고 선택할 사용자 목록을 따라 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="73fb3-201">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="73fb3-202">항목을 제거하려면 사용자에 **대해** ![ 제거 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="73fb3-203">**이름:** 이 값은 선택한 전자 메일 주소를 기반으로 채워지지만 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-203">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="73fb3-204">작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-204">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="73fb3-205">기존 항목을 편집하려면 목록에서 보호된 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-205">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="73fb3-206">**보호할 도메인 을 추가:** 다음 설정 중 하나 또는 둘 다를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-206">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="73fb3-207">**도메인 I 소유를 자동으로 포함:** 기본값은 **해제입니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-207">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="73fb3-208">켜려면 토글을 켜서 **켜기를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="73fb3-209">**사용자 지정 도메인 포함**: 기본값은 **사용 안 됨입니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-209">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="73fb3-210">To turn it on, slide the **toggle**to On, and in the **Add domains** box, enter the domain name (for example, contoso.com and example, enter, and repeat as necessary.</span><span class="sxs-lookup"><span data-stu-id="73fb3-210">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="73fb3-211">**동작:** 편집 **클릭**</span><span class="sxs-lookup"><span data-stu-id="73fb3-211">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="73fb3-212">**가장된 사용자가 전자 메일을 보내는 경우**: 스푸핑된 보낸 사람이 보호할 사용자 추가에 지정된 보호된 사용자 중 하나인 메시지에 대해 **다음 작업 중 하나를 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-212">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="73fb3-213">**모든 작업 적용 금지**</span><span class="sxs-lookup"><span data-stu-id="73fb3-213">**Don't apply any action**</span></span>
       - <span data-ttu-id="73fb3-214">**다른 전자 메일 주소로 메시지 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="73fb3-214">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="73fb3-215">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="73fb3-215">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="73fb3-216">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="73fb3-216">**Quarantine the message**</span></span>
       - <span data-ttu-id="73fb3-217">**메시지 배달 및 "Bcc 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="73fb3-217">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="73fb3-218">**메시지를 배달하기 전에 삭제**</span><span class="sxs-lookup"><span data-stu-id="73fb3-218">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="73fb3-219">**가장된 도메인에서 전자 메일을 보내는**경우: 스푸핑된 보낸 사람이 보호할 도메인 추가에 지정한 보호된 도메인 중 하나에 있는 경우 메시지에 대해 **다음 작업 중 하나를 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-219">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="73fb3-220">**모든 작업 적용 금지**</span><span class="sxs-lookup"><span data-stu-id="73fb3-220">**Don't apply any action**</span></span>
     - <span data-ttu-id="73fb3-221">**다른 전자 메일 주소로 메시지 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="73fb3-221">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="73fb3-222">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="73fb3-222">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="73fb3-223">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="73fb3-223">**Quarantine the message**</span></span>
     - <span data-ttu-id="73fb3-224">**메시지 배달 및 "Bcc 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="73fb3-224">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="73fb3-225">**메시지를 배달하기 전에 삭제**</span><span class="sxs-lookup"><span data-stu-id="73fb3-225">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="73fb3-226">가장 **보안 팁을 켜고 다음 설정을** 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-226">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="73fb3-227">**가장된 사용자에 대한 팁 표시**: 기본값은 해제입니다. **Off**</span><span class="sxs-lookup"><span data-stu-id="73fb3-227">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="73fb3-228">켜려면 토글을 켜서 **켜기를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-228">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="73fb3-229">**가장된 도메인에 대한 팁 표시**: 기본값은 해제입니다. **Off**</span><span class="sxs-lookup"><span data-stu-id="73fb3-229">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="73fb3-230">켜려면 토글을 켜서 **켜기를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="73fb3-231">**비정상 문자에 대한 팁 표시:** 기본값은 사용 안 **과정입니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-231">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="73fb3-232">켜려면 토글을 켜서 **켜기를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-232">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="73fb3-233">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-233">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="73fb3-234">**사서함 인텔리전스:**</span><span class="sxs-lookup"><span data-stu-id="73fb3-234">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="73fb3-235">**사서함 인텔리전스 사용 여부**: 기본값은 **On입니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-235">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="73fb3-236">이 기능을 끄려면 토글을 꺼서 **끄도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-236">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="73fb3-237">**사서함 인텔리전스 기반 가장 보호 사용**여부 : 이 설정은 사서함 인텔리전스 사용 **여부에서만** 사용할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-237">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="73fb3-238">가장된 **사용자가 전자 메일을 보내는 경우**사서함 인텔리전스(보호된 사용자와 보호된 도메인에 대해 사용 가능한 것과 동일한 작업)가 포함된 메시지에서 수행할 다음 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-238">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="73fb3-239">**모든 작업 적용 금지**</span><span class="sxs-lookup"><span data-stu-id="73fb3-239">**Don't apply any action**</span></span>
       - <span data-ttu-id="73fb3-240">**다른 전자 메일 주소로 메시지 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="73fb3-240">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="73fb3-241">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="73fb3-241">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="73fb3-242">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="73fb3-242">**Quarantine the message**</span></span>
       - <span data-ttu-id="73fb3-243">**메시지 배달 및 "Bcc 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="73fb3-243">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="73fb3-244">**메시지를 배달하기 전에 삭제**</span><span class="sxs-lookup"><span data-stu-id="73fb3-244">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="73fb3-245">**신뢰할 수 있는 발신자와 도메인 추가:** 정책에 대한 예외를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-245">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="73fb3-246">**신뢰할 수 있는 보낸 사람:**</span><span class="sxs-lookup"><span data-stu-id="73fb3-246">**Trusted senders**:</span></span>

       - <span data-ttu-id="73fb3-247">상자를 클릭하고 선택할 사용자 목록을 따라 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-247">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="73fb3-248">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-248">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="73fb3-249">항목을 제거하려면 사용자에 **대해** ![ 제거 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-249">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="73fb3-250">**신뢰할 수 있는**도메인: 도메인 이름(예: contoso.com)을 입력하고, Enter 키를 누르고 필요에 따라 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-250">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="73fb3-251">**설정 검토:** 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-251">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="73fb3-252">각 섹션에서 **편집을** 클릭하여 관련 페이지로 돌아가볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-252">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="73fb3-253">이 페이지에서 다음 설정을 직접 **설정/해제할** 수 있습니다. **On**</span><span class="sxs-lookup"><span data-stu-id="73fb3-253">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="73fb3-254">**보호된 사용자**</span><span class="sxs-lookup"><span data-stu-id="73fb3-254">**Protected users**</span></span>
       - <span data-ttu-id="73fb3-255">**보호된 도메인** \> **도메인 I 소유 포함**</span><span class="sxs-lookup"><span data-stu-id="73fb3-255">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="73fb3-256">**보호된 도메인** \> **보호된 도메인(사용자** 지정 도메인)</span><span class="sxs-lookup"><span data-stu-id="73fb3-256">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="73fb3-257">**사서함 인텔리전스**</span><span class="sxs-lookup"><span data-stu-id="73fb3-257">**Mailbox intelligence**</span></span>

   <span data-ttu-id="73fb3-258">작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-258">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="73fb3-259">**스푸핑**: **편집을 클릭하여** 스푸핑 인텔리전스를 설정 또는 해제하고, Outlook의 인증되지 않은 발신자 식별을 설정 또는 해제하고, 차단된 스푸핑된 보낸 사람의 메시지에 적용할 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-259">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="73fb3-260">자세한 내용은 [피싱 방지 정책의 스푸핑 설정을 참조하십시오.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="73fb3-260">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="73fb3-261">이러한 설정은 EOP의 피싱 방지 정책에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-261">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="73fb3-262">**스푸핑 필터 설정**: 기본값은 **On이며**이 값을 사용하도록 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-262">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="73fb3-263">이 기능을 끄려면 토글을 꺼서 **끄도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-263">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="73fb3-264">자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="73fb3-264">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="73fb3-265">MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용하지 않을 필요가 없습니다. 대신 커넥터에 대한 향상된 필터링을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-265">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="73fb3-266">자세한 내용은 [Exchange Online에서 커넥터에 대한 향상된 필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="73fb3-266">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="73fb3-267">**인증되지 않은 보낸 사람 기능 사용**: 기본값은 **켜기입니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-267">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="73fb3-268">이 기능을 끄려면 토글을 꺼서 **끄도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-268">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="73fb3-269">**작업:** 스푸핑 인텔리전스에 실패한 메시지에 대해 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-269">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="73fb3-270">**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보내는 경우:**</span><span class="sxs-lookup"><span data-stu-id="73fb3-270">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="73fb3-271">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="73fb3-271">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="73fb3-272">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="73fb3-272">**Quarantine the message**</span></span>

   - <span data-ttu-id="73fb3-273">**설정 검토:** 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-273">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="73fb3-274">각 섹션에서 **편집을** 클릭하여 관련 페이지로 돌아가볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-274">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="73fb3-275">이 페이지에서 다음 설정을 직접 **설정/해제할** 수 있습니다. **On**</span><span class="sxs-lookup"><span data-stu-id="73fb3-275">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="73fb3-276">**맬웨어 방지 보호 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="73fb3-276">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="73fb3-277">**인증되지 않은 보낸 사람 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="73fb3-277">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="73fb3-278">작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-278">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="73fb3-279">**고급 설정:** **편집을** 클릭하여 고급 피싱 임계값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-279">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="73fb3-280">자세한 내용은 [ATP 피싱 방지 정책의 고급 피싱 임계값을 참조하십시오.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="73fb3-280">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="73fb3-281">**고급 피싱 임계값:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-281">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="73fb3-282">**1 -** Standard(기본값)</span><span class="sxs-lookup"><span data-stu-id="73fb3-282">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="73fb3-283">**2 - 적각**</span><span class="sxs-lookup"><span data-stu-id="73fb3-283">**2 - Aggressive**</span></span>
   - <span data-ttu-id="73fb3-284">**3 - 더욱 적전합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-284">**3 - More aggressive**</span></span>
   - <span data-ttu-id="73fb3-285">**4 - 가장 강도적**</span><span class="sxs-lookup"><span data-stu-id="73fb3-285">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="73fb3-286">**설정 검토:** **편집을** 클릭하여 고급 피싱 **임계값 페이지로 돌아가기**</span><span class="sxs-lookup"><span data-stu-id="73fb3-286">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="73fb3-287">작업을 마쳤을 때 두 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-287">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="73fb3-288">정책 편집 **페이지로 \<Name\> 돌아가** 설정을 검토하고 닫기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-288">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="73fb3-289">Security & 준수 센터를 사용하여 기본 ATP 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="73fb3-289">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="73fb3-290">기본 ATP 피싱 방지 정책은 Office365 AntiPhish Default라는 이름으로, 정책 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-290">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="73fb3-291">기본 ATP 피싱 방지 정책을 수정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-291">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="73fb3-292">보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-292">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="73fb3-293">피싱 **방지 페이지에서 기본 정책을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-293">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="73fb3-294">정책 **편집 Office365 AntiPhish Default 페이지가** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-294">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="73fb3-295">다음 섹션을 통해 사용자 지정 정책을 수정할 때와 대조한 [설정이 포함되어 있습니다.](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="73fb3-295">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="73fb3-296">**가장**</span><span class="sxs-lookup"><span data-stu-id="73fb3-296">**Impersonation**</span></span>
   - <span data-ttu-id="73fb3-297">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="73fb3-297">**Spoof**</span></span>
   - <span data-ttu-id="73fb3-298">**고급 설정**</span><span class="sxs-lookup"><span data-stu-id="73fb3-298">**Advanced settings**</span></span>

   <span data-ttu-id="73fb3-299">기본 정책을 수정할 때는 다음과 같은 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-299">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="73fb3-300">정책 설정 **섹션과 값을** 볼 수 있지만 편집 링크가 없기어도 설정을 수정할 수 없습니다(정책 이름, 설명 및 정책이 적용되는 대상(모든 받는 사람에게 적용됨). **Edit**</span><span class="sxs-lookup"><span data-stu-id="73fb3-300">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="73fb3-301">기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-301">You can't delete the default policy.</span></span>
   - <span data-ttu-id="73fb3-302">기본 정책의 우선순위를 변경할 수 없습니다(항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="73fb3-302">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="73fb3-303">정책 **Office365 AntiPhish Default 페이지에서 설정을** 검토하고 닫기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-303">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-304">사용자 지정 ATP 피싱 방지 정책 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="73fb3-304">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="73fb3-305">보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-305">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="73fb3-306">**상태** 열의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-306">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="73fb3-307">토글을 끌어 정책을 **사용하지 않도록** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-307">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="73fb3-308">토글을 밀어 정책을 **사용하도록** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-308">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="73fb3-309">기본 피싱 방지 정책을 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-309">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-310">사용자 지정 ATP 피싱 방지 정책의 우선순위 설정</span><span class="sxs-lookup"><span data-stu-id="73fb3-310">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="73fb3-311">기본적으로 ATP 피싱 방지 정책은 만들어진 순서에 따라 우선 순위가 지정됩니다(새 정책은 이전 정책보다 우선순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="73fb3-311">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="73fb3-312">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="73fb3-312">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="73fb3-313">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-313">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="73fb3-314">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-314">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="73fb3-315">사용자 지정 ATP 피싱 방지 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 **우선 순위** 값 0이 지정됨).</span><span class="sxs-lookup"><span data-stu-id="73fb3-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="73fb3-316">Office365 AntiPhish 기본값이라는 기본 피싱 방지 정책은 사용자 지정 우선순위 **값이 가장 낮음이며**변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="73fb3-317">**참고**: 보안 & 준수 센터에서 ATP 피싱 방지 정책을 만들고 의우선순위를 변경해야 만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="73fb3-318">PowerShell에서 피싱 방지 규칙(기존 규칙의 우선순위에 영향을 줄 수 있는)을 만들 때 기본 우선순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="73fb3-319">정책의 우선 순위를 변경하려면 **정책** 속성에서 **Decrease priority** 우선 순위 높이기 또는 우선 순위를 높입니다. (Security & Compliance Center에서 우선 순위 **번호를** 직접 수정할 수는 없습니다).</span><span class="sxs-lookup"><span data-stu-id="73fb3-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="73fb3-320">여러 정책을 포함한 경우에만 정책 우선순위를 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="73fb3-321">보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="73fb3-322">수정할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="73fb3-323">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="73fb3-324">정책 \*\* \<name\> 플라이아웃이\*\* 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="73fb3-325">우선순위 값이 **0인** 사용자 지정 ATP 피싱 방지 **정책에는** 사용 가능한 **우선 순위 가시 사용 전제만** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="73fb3-326">우선순위 값이 가장 낮은 사용자 지정 ATP **Priority** 피싱 방지 **정책(예: 3)에는**우선 순위 **높이 버튼만 사용할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="73fb3-327">사용자 지정 피싱 방지 정책이 세 개 이상 있는 경우 우선순위 값이 가장 높은 값과 가장 낮은 우선순위 값 사이의 정책은 모두 **사용할** 수 있는 우선 순위와 우선 순위 **낮게 지정** 단추를 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="73fb3-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span><span class="sxs-lookup"><span data-stu-id="73fb3-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="73fb3-329">작업을 마쳤으면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-330">보안 센터 & 사용하여 ATP 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="73fb3-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="73fb3-331">보안 그룹 & 센터에서 위협 **관리 정책** \> **Policy** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="73fb3-332">다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="73fb3-333">보거나, 보는 사용자 지정 ATP 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="73fb3-334">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="73fb3-335">기본 **정책을** 클릭하여 기본 피싱 방지 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="73fb3-336">정책 \*\* \<name\> 플라이아웃이\*\* 나타나면, 설정 및 값을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-337">Security & 준수 센터를 사용하여 ATP 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="73fb3-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="73fb3-338">보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="73fb3-339">제거할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="73fb3-340">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="73fb3-341">표시되는 **정책 \<name\> 플라이아웃** 편집에서 **정책 삭제를**클릭한 후 나타나는 경고 대화 상자에서 예를 클릭합니다. **Yes**</span><span class="sxs-lookup"><span data-stu-id="73fb3-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="73fb3-342">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="73fb3-343">Exchange Online PowerShell을 사용하여 ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="73fb3-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="73fb3-344">앞에서 설명한 것것과 같이, ATP 스팸 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-344">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="73fb3-345">Exchange Online PowerShell에서 피싱 방지 정책과 피싱 방지 규칙의 차이는 명백합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-345">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="73fb3-346">\*\* \* -AntiPhishPolicy\*\* cmdlet을 사용하여 피싱 방지 정책을 관리하고, \*\* \* -AntiPhishRule\*\* cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-346">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="73fb3-347">PowerShell에서 먼저 피싱 방지 정책을 만들고 해당 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-347">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="73fb3-348">PowerShell에서는 피싱 방지 정책및 피싱 방지 규칙의 설정을 개별적으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-348">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="73fb3-349">PowerShell에서 피싱 방지 정책을 제거하면 해당피어 제거 규칙은 자동으로 제거되지 않거나, 전또한 경우에 따라 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-349">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="73fb3-350">PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="73fb3-350">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="73fb3-351">PowerShell에서 피싱 방지 정책을 만드는 두 단계 과정은 다음 두 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-351">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="73fb3-352">피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-352">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="73fb3-353">규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-353">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="73fb3-354">**참고:**</span><span class="sxs-lookup"><span data-stu-id="73fb3-354">**Notes**:</span></span>

- <span data-ttu-id="73fb3-355">새로운 피싱 방지 규칙을 만들고 연결되지 않은 기존의 피싱 방지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-355">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="73fb3-356">피싱 방지 규칙은 두 개 이상의 피싱 방지 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-356">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="73fb3-357">정책을 만들 때까지 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 피싱 방지 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-357">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="73fb3-358">새 정책을 만듭니다(New-AntiPhishRule_Enabled_ `$false` **cmdlet에서 사용 안** 함).</span><span class="sxs-lookup"><span data-stu-id="73fb3-358">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="73fb3-359">_Priority_ _\<Number\>_ **New-AntiPhishRule** cmdlet에서 생성하는 동안 정책 우선순위를 설정합니다(우선 순위).</span><span class="sxs-lookup"><span data-stu-id="73fb3-359">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="73fb3-360">피싱 방지 규칙에 정책을 할당할 때까지 PowerShell에서 만든 피싱 방지 정책은 보안 & 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-360">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="73fb3-361">1단계: PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="73fb3-361">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="73fb3-362">피싱 방지 정책을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-362">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="73fb3-363">이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-363">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="73fb3-364">정책이 사용하도록 설정되었습니다(Enabled 매개 변수를 _사용하지 않지만_ 기본값은 다음과 같음). `$true`</span><span class="sxs-lookup"><span data-stu-id="73fb3-364">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="73fb3-365">설명에: 리서치 부서 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-365">The description is: Research department policy.</span></span>
- <span data-ttu-id="73fb3-366">모든 허용 도메인에 대해 조직 도메인 보호 및 특정 도메인에 대해 대상 도메인 보호를 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="73fb3-366">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="73fb3-367">가장으로부터 보호할 수 있도록 마이니 아이재 mfujito@fabrikam.com(미국 수화)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-367">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="73fb3-368">사서함 인텔리전스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-368">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="73fb3-369">사서함 인텔리전스 보호를 사용하도록 설정하고 격리 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-369">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="73fb3-370">보안 팁을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-370">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="73fb3-371">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="73fb3-371">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="73fb3-372">2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="73fb3-372">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="73fb3-373">피싱 방지 규칙을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-373">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="73fb3-374">이 예에서는 다음 조건에 따라 Research Department라는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-374">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="73fb3-375">이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-375">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="73fb3-376">이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-376">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="73fb3-377">Priority 매개 변수를 사용하지 않는 _기기에_ 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-377">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="73fb3-378">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="73fb3-378">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="73fb3-379">PowerShell을 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="73fb3-379">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="73fb3-380">기존의 피싱 방지 정책을 확인하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-380">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="73fb3-381">이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-381">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="73fb3-382">이 예에서는 Executives라는 피싱 방지 정책에 대한 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-382">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="73fb3-383">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="73fb3-383">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="73fb3-384">PowerShell을 사용하여 피싱 방지 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="73fb3-384">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="73fb3-385">기존의 피싱 방지 규칙을 확인하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-385">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="73fb3-386">이 예에서는 지정한 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-386">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="73fb3-387">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-387">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="73fb3-388">이 예에서는 Contoso Executives라는 피싱 방지 규칙에 대한 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-388">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="73fb3-389">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="73fb3-389">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="73fb3-390">PowerShell을 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="73fb3-390">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="73fb3-391">다음과 같은 항목 외에 PowerShell에서 피싱 방지 정책을 수정할 때 이 항목 앞부분에 있는 [피싱](#step-1-use-powershell-to-create-an-anti-phish-policy) 방지 정책 섹션을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-391">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="73fb3-392">_지정된 정책을_ 기본 정책으로 바라내는 MakeDefault 스위치(모든 사용자에게 적용, 항상 우선 순위가 가장 **낮은** 스위치, 삭제할 수 없음)는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-392">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="73fb3-393">피싱 방지 정책의 이름을 바일 수 **없습니다(Set-AntiPhishPolicy cmdlet에** Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="73fb3-393">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="73fb3-394">보안 서비스 준수 센터에서 피싱 방지 정책의 이름을 & 바는 경우 피싱 방지 규칙의 이름만 _변경됩니다._</span><span class="sxs-lookup"><span data-stu-id="73fb3-394">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="73fb3-395">피싱 방지 정책을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-395">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="73fb3-396">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="73fb3-396">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="73fb3-397">PowerShell을 사용하여 피싱 방지 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="73fb3-397">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="73fb3-398">PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 유일한 _설정은 사용 안_ 함 규칙을 만들 수 있는 사용 안 함 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-398">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="73fb3-399">기존의 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-399">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="73fb3-400">그렇지 않으면 PowerShell에서 피싱 방지 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-400">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="73fb3-401">[2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 이 항목 앞부분의 피싱 방지 규칙 섹션에 설명된 것과 같이 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-401">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="73fb3-402">피싱 방지 규칙을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-402">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="73fb3-403">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="73fb3-403">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="73fb3-404">PowerShell을 사용하여 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="73fb3-404">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="73fb3-405">PowerShell에서 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-405">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="73fb3-406">기본 피싱 방지 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(모든 받는 사람에게 항상 적용됨).</span><span class="sxs-lookup"><span data-stu-id="73fb3-406">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="73fb3-407">PowerShell에서 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-407">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="73fb3-408">다음은 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-408">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="73fb3-409">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-409">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="73fb3-410">구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule 및](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [Disable-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="73fb3-410">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="73fb3-411">PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="73fb3-411">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="73fb3-412">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-412">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="73fb3-413">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-413">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="73fb3-414">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-414">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="73fb3-415">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-415">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="73fb3-416">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-416">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="73fb3-417">PowerShell에서 피싱 방지 규칙의 우선순위를 설정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-417">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="73fb3-418">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-418">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="73fb3-419">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="73fb3-419">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="73fb3-420">**참고:**</span><span class="sxs-lookup"><span data-stu-id="73fb3-420">**Notes**:</span></span>

- <span data-ttu-id="73fb3-421">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-AntiPhishRule** cmdlet의 _Priority_ 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-421">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="73fb3-422">기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없고 항상 수정할 수 없는 우선순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-422">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="73fb3-423">PowerShell을 사용하여 피싱 방지 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="73fb3-423">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="73fb3-424">PowerShell을 사용하여 피싱 방지 정책을 제거할 때 해당 피싱 방지 규칙은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-424">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="73fb3-425">PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-425">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="73fb3-426">이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-426">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="73fb3-427">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="73fb3-427">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="73fb3-428">PowerShell을 사용하여 피싱 방지 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="73fb3-428">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="73fb3-429">PowerShell을 사용하여 피싱 방지 규칙을 제거할 때 해당 피싱 방지 정책은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-429">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="73fb3-430">PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="73fb3-430">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="73fb3-431">이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-431">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="73fb3-432">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="73fb3-432">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="73fb3-433">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="73fb3-433">How do you know these procedures worked?</span></span>

<span data-ttu-id="73fb3-434">ATP 피싱 방지 정책을 성공적으로 구성되었는지 확인하려면 다음 단계를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="73fb3-434">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="73fb3-435">보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-435">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="73fb3-436">정책, 상태 값 및 **우선** 순위 값 목록을 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="73fb3-436">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="73fb3-437">자세한 내용을 보려면 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-437">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="73fb3-438">목록에서 정책을 선택하 고 플라이아웃에서 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-438">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="73fb3-439">기본 **정책을 클릭하고** 플라이아웃에서 세부 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-439">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="73fb3-440">Exchange Online PowerShell에서 정책 \<Name\> 또는 규칙의 이름으로 바꾸고, 다음 명령을 실행하여 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="73fb3-440">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
