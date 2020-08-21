---
title: EOP에서 피싱 방지 정책 구성
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
description: 관리자는 Exchange Online 사서함의 사용 여부에 관계없이 EOP(Exchange Online Protection) 조직에서 사용할 수 있는 피싱 방지 정책을 만들고, 수정하고, 삭제하는 방법에 대해 알아보세요.
ms.openlocfilehash: af6577d32d43300867d29a365baaa4e1e7e1b5e3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825752"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="a2892-103">EOP에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a2892-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="a2892-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에는 기본적으로 사용하는 제한된 수의 스푸핑 방지 기능을 포함하는 기본 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="a2892-105">자세한 내용은 [피싱 방지 정책의 스푸핑 설정을 참조하십시오.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="a2892-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="a2892-106">관리자는 기본 피싱 방지 정책을 보고, 편집하고, 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="a2892-107">세분성을 크게 위해 사용자 지정 피싱 방지 정책을 만들 수 있습니다. 조직의 특정 사용자, 그룹 또는 도메인에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="a2892-108">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="a2892-109">Exchange Online 사서함이 있는 조직은 보안 업데이트 및 준수 센터 또는 Exchange Online PowerShell에서 & 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="a2892-110">독립 실행형 EOP 조직은 준수 센터에 있는 보안 및 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="a2892-111">Office 365 ATP(Advanced Threat Protection)에서 사용할 수 있는 고급 ATP 피싱 방지 정책을 만들고 수정하는 방법에 대한 자세한 내용은 [ATP 피싱 방지 정책 구성을 참조하세요.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a2892-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="a2892-112">피싱 방지 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="a2892-113">**피싱 방지 정책:** 사용하거나 사용하지 않도록 설정할 피싱 보호 기능과 옵션을 적용할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="a2892-114">**피싱 방지 규칙: 피싱 방지**정책에 대한 우선순위 및 받는 사람 필터(정책이 적용되는 사용자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="a2892-115">준수 센터에서 보안 설치 제거 정책을 관리하면, 두 가지 요소의 차이는 & 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a2892-116">피싱 방지 정책을 만들면 실제로 피싱 방지 규칙과 관련된 피싱 방지 정책이 두 가지 모두 동일한 이름을 사용하여 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a2892-117">피싱 방지 정책을 수정할 때는 이름, 우선순위, 활성화됨 또는 사용 안 함 및 받는 사람 필터와 관련된 설정이 피싱 방지 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="a2892-118">다른 모든 설정은 관련 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="a2892-119">피싱 방지 정책을 제거할 경우 피싱 방지 규칙과 관련된 피싱 방지 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="a2892-120">Exchange Online PowerShell에서 정책과 규칙은 별도로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a2892-121">자세한 내용은 이 항목 [뒷부분에 나오는 피싱 방지 정책](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 구성을 위한 Exchange Online PowerShell 사용 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2892-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="a2892-122">모든 조직에는 다음과 같은 속성을 가진 Office365 AntiPhish Default라는 피싱 방지 정책이 기본으로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="a2892-123">정책에 연결된 피싱 방지 규칙(받는 사람 필터)이 없더라도 조직의 모든 받는 사람에게 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="a2892-124">정책의 사용자 지정 우선순위 값은 **가장 낮음**이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="a2892-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="a2892-125">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="a2892-126">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="a2892-127">피싱 방지 보호의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 강조한 설정을 사용하여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2892-128">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a2892-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a2892-129"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a2892-130">피싱 방지 **페이지로 직접 이동하려면 을** 사용합니다. <https://protection.office.com/antiphishing></span><span class="sxs-lookup"><span data-stu-id="a2892-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="a2892-131">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="a2892-132">독립 실행형 EOP PowerShell에서 피싱 방지 정책을 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="a2892-133">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="a2892-134">피싱 방지 정책을 추가, 수정 및 삭제하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-134">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="a2892-135">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="a2892-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="a2892-136">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="a2892-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="a2892-137">피싱 방지 정책에 대한 읽기 전용 액세스에 액세스하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-137">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="a2892-138">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="a2892-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="a2892-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="a2892-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="a2892-140">독립 실행형 EOP에서 스팸 방지 정책을 만들고 수정하려면 테넌트에 대한 _하이드레이션이 필요한 작업을_ 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-140">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="a2892-141">예를 들어 EAC(Exchange 관리 센터)에서 **사용 권한** 탭으로 이동하여 기존 **Edit** 역할 그룹을 선택하고 편집 아이콘을 클릭하고 역할을 제거할 수 ![ ](../../media/ITPro-EAC-EditIcon.png) 있습니다(결국적으로 다시 추가).</span><span class="sxs-lookup"><span data-stu-id="a2892-141">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="a2892-142">테넌트가 하이드 산정되지 않았다면 성공적으로 완료되어야 하는 진행률 표시줄이 있는 **조직** 설정 업데이트라는 대화 상자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-142">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="a2892-143">하이드레이션에 대한 자세한 내용은 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet(독립 실행형 EOP PowerShell 또는 보안 센터에서는 사용할 수 없음)을 & 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2892-143">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="a2892-144">피싱 방지 정책에 대한 권장 설정은 [EOP 기본 피싱 방지 정책 설정을 참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="a2892-144">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="a2892-145">업데이트된 정책이 적용될 수 있도록 최대 30분 간 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-145">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="a2892-146">필터링 파이프라인에서 피싱 방지 정책을 적용한 위치에 대한 자세한 내용은 [전자 메일 보호의 순서 및 우선 순위를 참조하십시오.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="a2892-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="a2892-147">보안 그룹 & 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a2892-147">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="a2892-148">보안 센터에서 사용자 지정 피싱 방지 정책을 & 만들면 두 서비스 모두동일한 이름을 사용하여 피싱 방지 규칙과 관련된 피싱 방지 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="a2892-149">피싱 방지 정책을 만들 때는 정책이 적용되는 사용자를 식별하는 정책 이름, 설명 및 받는 사람 필터만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="a2892-150">정책을 만들고 나면 정책을 수정하여 기본 피싱 방지 설정을 변경하거나 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="a2892-151">보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a2892-152">피싱 **방지 페이지에서 만들기를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="a2892-153">새 **피싱 방지 정책 만들기 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="a2892-154">정책 이름 **지정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="a2892-155">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="a2892-156">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a2892-157">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a2892-158">페이지에 **정책이** 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="a2892-159">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a2892-160">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="a2892-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a2892-161">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a2892-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="a2892-162">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-162">Click **Add a condition**.</span></span> <span data-ttu-id="a2892-163">표시되는 드롭다운 메뉴에서 다음과 같은 경우 적용된 **조건을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="a2892-164">**받는 사람은**: 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a2892-165">**받는 사람이 조직의 그룹**구성원: 조직에서 하나 이상의 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="a2892-166">**받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="a2892-167">조건을 선택하면 해당 드롭다운이 다음 상자 중 **하나와 함께 나타납니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="a2892-168">상자를 클릭하고 선택할 값 목록을 따라 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="a2892-169">상자를 클릭하고 입력하여 목록을 필터링하고 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="a2892-170">값을 더 추가하려면 상자에서 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="a2892-171">개별 항목을 제거하려면 **값에서 제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="a2892-172">전체 조건을 제거하려면 해당 **조건에서 제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="a2892-173">조건을 더 추가하려면 조건 **추가를 클릭하고 적용된** 경우에는 나머지 **값을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="a2892-174">예외를 추가하려면 조건 **추가를 클릭하고** 다음의 경우 제외를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="a2892-175">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a2892-176">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a2892-177">**나타나는 설정** 검토 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="a2892-178">각 설정에서 **편집을** 클릭하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="a2892-179">완료되면 이 정책 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="a2892-180">확인 **대화** 상자가 나타나면 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="a2892-181">이러한 일반 정책 설정을 사용하여 피싱 방지 정책을 만들고 나면 다음 섹션의 지침을 사용하여 정책의 보호 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-181">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="a2892-182">보안 프리센터 & 사용하여 피싱 방지 정책 수정하기</span><span class="sxs-lookup"><span data-stu-id="a2892-182">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="a2892-183">다음 절차에 따라 사용자가 만든 새 정책 또는 이미 사용자 지정된 기존 정책과 같은 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="a2892-184">아직 선택되지 않은 경우 보안 센터를 열어 위협 **Threat management** 관리 & 정책 \> **Policy** \> **방지 정책 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a2892-185">수정할 사용자 지정 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="a2892-186">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a2892-187">정책 \*\* \<name\> 플라이아웃이\*\* 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="a2892-188">섹션에서 **편집을** 클릭하면 해당 섹션의 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="a2892-189">다음 단계는 섹션이 나타나는 순서대로 나와 있지만 순차적이지는 않습니다(순서와대로 구역을 선택하여 수정가능).</span><span class="sxs-lookup"><span data-stu-id="a2892-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="a2892-190">섹션에서 **편집을 클릭하면** 사용 가능한 설정이 마법사 형식으로 제공되지만 원하는 순서로 페이지 내로 이동할 수 있고, **Cancel** 페이지에서 **Close** **저장을** 클릭하거나 취소 또는 닫기 아이콘을 클릭하여 정책 편집 ![ ](../../media/scc-remove-icon.png) \*\*페이지로 돌아갈 수 \<name\> \*\* 있습니다. 마법사의 마지막 페이지를 방문하거나 저장하거나 나갈 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="a2892-191">**정책 설정:** **편집을** 클릭하여 이전 섹션에서 정책을 만들 때 사용 [가능한 것과 동일한 설정을](#use-the-security--compliance-center-to-create-anti-phishing-policies) 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="a2892-192">**이름**</span><span class="sxs-lookup"><span data-stu-id="a2892-192">**Name**</span></span>
   - <span data-ttu-id="a2892-193">**설명**</span><span class="sxs-lookup"><span data-stu-id="a2892-193">**Description**</span></span>
   - <span data-ttu-id="a2892-194">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="a2892-194">**Applied to**</span></span>
   - <span data-ttu-id="a2892-195">**설정 검토**</span><span class="sxs-lookup"><span data-stu-id="a2892-195">**Review your settings**</span></span>

   <span data-ttu-id="a2892-196">작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="a2892-197">**스푸핑**: **편집을 클릭하여** 스푸핑 인텔리전스를 설정 또는 해제하고, Outlook의 인증되지 않은 발신자 식별을 설정 또는 해제하고, 차단된 스푸핑된 보낸 사람의 메시지에 적용할 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-197">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="a2892-198">자세한 내용은 [피싱 방지 정책의 스푸핑 설정을 참조하십시오.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="a2892-198">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="a2892-199">ATP 피싱 방지 정책에서도 이러한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-199">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="a2892-200">**스푸핑 필터 설정**: 기본값은 **On이며**이 값을 사용하도록 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-200">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="a2892-201">이 기능을 끄려면 토글을 꺼서 **끄도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-201">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="a2892-202">자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="a2892-202">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="a2892-203">MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용하지 않을 필요가 없습니다. 대신 커넥터에 대한 향상된 필터링을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-203">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="a2892-204">자세한 내용은 [Exchange Online에서 커넥터에 대한 향상된 필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="a2892-204">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="a2892-205">**인증되지 않은 보낸 사람 기능 사용**: 기본값은 **켜기입니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-205">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="a2892-206">이 기능을 끄려면 토글을 꺼서 **끄도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-206">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="a2892-207">**작업:** 스푸핑 인텔리전스에 실패한 메시지에 대해 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-207">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="a2892-208">**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보내는 경우:**</span><span class="sxs-lookup"><span data-stu-id="a2892-208">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="a2892-209">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="a2892-209">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="a2892-210">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="a2892-210">**Quarantine the message**</span></span>

   - <span data-ttu-id="a2892-211">**설정 검토:** 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-211">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="a2892-212">각 섹션에서 **편집을** 클릭하여 관련 페이지로 돌아가볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-212">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="a2892-213">이 페이지에서 다음 설정을 직접 **설정/해제할** 수 있습니다. **On**</span><span class="sxs-lookup"><span data-stu-id="a2892-213">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="a2892-214">**맬웨어 방지 보호 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="a2892-214">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="a2892-215">**인증되지 않은 보낸 사람 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="a2892-215">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="a2892-216">작업을 마쳤을 때 임의의 **페이지에서 저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-216">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="a2892-217">정책 편집 **페이지로 \<Name\> 돌아가** 설정을 검토하고 닫기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-217">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="a2892-218">보안 정책 & 사용하여 기본 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="a2892-218">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="a2892-219">기본 피싱 방지 정책은 Office365 AntiPhish Default라는 이름으로, 정책 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-219">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="a2892-220">기본 피싱 방지 정책을 수정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-220">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="a2892-221">보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a2892-222">피싱 **방지 페이지에서 기본 정책을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-222">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="a2892-223">정책 **편집 Office365 AntiPhish Default 페이지가** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-223">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="a2892-224">사용자 지정 정책을 수정할 때와 대조한 설정을 포함하는 다음 [섹션을 사용할 수 있습니다.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="a2892-224">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="a2892-225">**가장**</span><span class="sxs-lookup"><span data-stu-id="a2892-225">**Impersonation**</span></span>
   - <span data-ttu-id="a2892-226">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="a2892-226">**Spoof**</span></span>
   - <span data-ttu-id="a2892-227">**고급 설정**</span><span class="sxs-lookup"><span data-stu-id="a2892-227">**Advanced settings**</span></span>

   <span data-ttu-id="a2892-228">기본 정책을 수정할 때는 다음과 같은 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-228">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="a2892-229">정책 설정 **섹션과 값을** 볼 수 있지만 편집 링크가 없기어도 설정을 수정할 수 없습니다(정책 이름, 설명 및 정책이 적용되는 대상(모든 받는 사람에게 적용됨). **Edit**</span><span class="sxs-lookup"><span data-stu-id="a2892-229">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="a2892-230">기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-230">You can't delete the default policy.</span></span>
   - <span data-ttu-id="a2892-231">기본 정책의 우선순위를 변경할 수 없습니다(항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="a2892-231">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="a2892-232">정책 **Office365 AntiPhish Default 페이지에서 설정을** 검토하고 닫기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-232">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="a2892-233">사용자 지정 피싱 방지 정책 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="a2892-233">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="a2892-234">보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-234">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a2892-235">**상태** 열의 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-235">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="a2892-236">토글을 끌어 정책을 **사용하지 않도록** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-236">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="a2892-237">토글을 밀어 정책을 **사용하도록** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-237">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="a2892-238">기본 피싱 방지 정책을 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-238">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="a2892-239">사용자 지정 피싱 방지 정책의 우선순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="a2892-239">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="a2892-240">기본적으로 만들어진 순서에 따라 우선순위가 지정됩니다(새 정책은 이전 정책보다 우선순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="a2892-240">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a2892-241">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="a2892-241">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a2892-242">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-242">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a2892-243">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-243">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="a2892-244">사용자 지정 피싱 방지 정책은 처리되는 순서로 표시됩니다(첫 번째 정책에는 **우선** 순위 값 0이 포함됨).</span><span class="sxs-lookup"><span data-stu-id="a2892-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="a2892-245">Office365 AntiPhish 기본값이라는 기본 피싱 방지 정책은 사용자 지정 우선순위 **값이 가장 낮음이며**변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="a2892-246">**참고**: 보안 & 센터에서, 만들고 나서 피싱 방지 정책의 우선순위만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="a2892-247">PowerShell에서 피싱 방지 규칙(기존 규칙의 우선순위에 영향을 줄 수 있는)을 만들 때 기본 우선순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="a2892-248">정책의 우선 순위를 변경하려면 **정책** 속성에서 **Decrease priority** 우선 순위 높이기 또는 우선 순위를 높입니다. (Security & Compliance Center에서 우선 순위 **번호를** 직접 수정할 수는 없습니다).</span><span class="sxs-lookup"><span data-stu-id="a2892-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="a2892-249">여러 정책을 포함한 경우에만 정책 우선순위를 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="a2892-250">보안 감사 & 센터에서 위협 **관리** \> **정책** \> **ATP 피싱 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="a2892-251">수정할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="a2892-252">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a2892-253">정책 \*\* \<name\> 플라이아웃이\*\* 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="a2892-254">우선순위 값이 **0인** 사용자 지정 피싱 방지 **정책에는** 사용 가능한 **우선 순위 하이버스 단추만** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="a2892-255">우선순위 값이 가장 낮은 사용자 지정 피싱 방지 정책(예: **Priority** **3)에는**우선 순위 **높이 버튼만 사용할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="a2892-256">사용자 지정 피싱 방지 정책이 세 개 이상 있는 경우 우선순위 값이 가장 높은 값과 가장 낮은 우선순위 값 사이의 정책은 모두 **사용할** 수 있는 우선 순위와 우선 순위 **낮게 지정** 단추를 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="a2892-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span><span class="sxs-lookup"><span data-stu-id="a2892-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="a2892-258">작업을 마쳤으면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="a2892-259">보안 & 준수 센터를 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="a2892-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="a2892-260">보안 그룹 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 방지 정책 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a2892-261">다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="a2892-262">보거나 는 사용자 지정 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="a2892-263">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="a2892-264">기본 **정책을** 클릭하여 기본 피싱 방지 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="a2892-265">정책 \*\* \<name\> 플라이아웃이\*\* 나타나면, 설정 및 값을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="a2892-266">Security & 센터를 사용하여 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="a2892-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="a2892-267">보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a2892-268">제거할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="a2892-269">이미 선택한 경우 선택을 선택을 삭제하고 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="a2892-270">표시되는 **정책 \<name\> 플라이아웃** 편집에서 **정책 삭제를**클릭한 후 나타나는 경고 대화 상자에서 예를 클릭합니다. **Yes**</span><span class="sxs-lookup"><span data-stu-id="a2892-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="a2892-271">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="a2892-272">Exchange Online PowerShell을 사용하여 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a2892-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="a2892-273">앞에서 설명한 것과 같이 스팸 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-273">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="a2892-274">Exchange Online PowerShell에서 피싱 방지 정책과 피싱 방지 규칙의 차이는 명백합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-274">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="a2892-275">\*\* \* -AntiPhishPolicy\*\* cmdlet을 사용하여 피싱 방지 정책을 관리하고, \*\* \* -AntiPhishRule\*\* cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-275">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="a2892-276">PowerShell에서 먼저 피싱 방지 정책을 만들고 해당 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-276">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a2892-277">PowerShell에서는 피싱 방지 정책및 피싱 방지 규칙의 설정을 개별적으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-277">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="a2892-278">PowerShell에서 피싱 방지 정책을 제거하면 해당피어 제거 규칙은 자동으로 제거되지 않거나, 전또한 경우에 따라 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-278">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="a2892-279">다음의 PowerShell 절차는 Exchange Online Protection PowerShell을 사용하는 독립 실행형 EOP 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-279">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="a2892-280">PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a2892-280">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="a2892-281">PowerShell에서 피싱 방지 정책을 만드는 두 단계 과정은 다음 두 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-281">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a2892-282">피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-282">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="a2892-283">규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-283">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="a2892-284">**참고:**</span><span class="sxs-lookup"><span data-stu-id="a2892-284">**Notes**:</span></span>

- <span data-ttu-id="a2892-285">새로운 피싱 방지 규칙을 만들고 연결되지 않은 기존의 피싱 방지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-285">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="a2892-286">피싱 방지 규칙은 두 개 이상의 피싱 방지 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-286">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="a2892-287">정책을 만들 때까지 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 피싱 방지 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-287">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="a2892-288">새 정책을 만듭니다(New-AntiPhishRule_Enabled_ `$false` **cmdlet에서 사용 안** 함).</span><span class="sxs-lookup"><span data-stu-id="a2892-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="a2892-289">_Priority_ _\<Number\>_ **New-AntiPhishRule** cmdlet에서 생성하는 동안 정책 우선순위를 설정합니다(우선 순위).</span><span class="sxs-lookup"><span data-stu-id="a2892-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="a2892-290">피싱 방지 규칙에 정책을 할당할 때까지 PowerShell에서 만든 피싱 방지 정책은 보안 & 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-290">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="a2892-291">1단계: PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a2892-291">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="a2892-292">피싱 방지 정책을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-292">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="a2892-293">이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-293">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="a2892-294">정책이 사용하도록 설정되었습니다(Enabled 매개 변수를 _사용하지 않지만_ 기본값은 다음과 같음). `$true`</span><span class="sxs-lookup"><span data-stu-id="a2892-294">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="a2892-295">설명에: 리서치 부서 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-295">The description is: Research department policy.</span></span>
- <span data-ttu-id="a2892-296">스푸핑을 위한 기본 동작을 격리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-296">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="a2892-297">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="a2892-297">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="a2892-298">2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="a2892-298">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="a2892-299">피싱 방지 규칙을 만들려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-299">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="a2892-300">이 예에서는 다음 조건에 따라 Research Department라는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-300">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="a2892-301">이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-301">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="a2892-302">이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-302">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="a2892-303">Priority 매개 변수를 사용하지 않는 _기기에_ 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-303">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="a2892-304">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="a2892-304">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="a2892-305">PowerShell을 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="a2892-305">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="a2892-306">기존의 피싱 방지 정책을 확인하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-306">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a2892-307">이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-307">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="a2892-308">이 예에서는 Executives라는 피싱 방지 정책에 대한 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-308">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="a2892-309">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="a2892-309">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="a2892-310">PowerShell을 사용하여 피싱 방지 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="a2892-310">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="a2892-311">기존의 피싱 방지 규칙을 확인하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-311">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a2892-312">이 예에서는 지정한 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-312">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="a2892-313">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-313">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="a2892-314">이 예에서는 Contoso Executives라는 피싱 방지 규칙에 대한 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-314">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="a2892-315">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="a2892-315">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="a2892-316">PowerShell을 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="a2892-316">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="a2892-317">다음과 같은 항목 외에 PowerShell에서 피싱 방지 정책을 수정할 때 이 항목 앞부분에 있는 [피싱](#step-1-use-powershell-to-create-an-anti-phish-policy) 방지 정책 섹션을 만들 때 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-317">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="a2892-318">_지정된 정책을_ 기본 정책으로 바라내는 MakeDefault 스위치(모든 사용자에게 적용, 항상 우선 순위가 가장 **낮은** 스위치, 삭제할 수 없음)는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-318">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="a2892-319">피싱 방지 정책의 이름을 바일 수 **없습니다(Set-AntiPhishPolicy cmdlet에** Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="a2892-319">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a2892-320">보안 서비스 준수 센터에서 피싱 방지 정책의 이름을 & 바는 경우 피싱 방지 규칙의 이름만 _변경됩니다._</span><span class="sxs-lookup"><span data-stu-id="a2892-320">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="a2892-321">피싱 방지 정책을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-321">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a2892-322">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="a2892-322">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="a2892-323">PowerShell을 사용하여 피싱 방지 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="a2892-323">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="a2892-324">PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 유일한 _설정은 사용 안_ 함 규칙을 만들 수 있는 사용 안 함 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-324">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a2892-325">기존의 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-325">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="a2892-326">그렇지 않으면 PowerShell에서 피싱 방지 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-326">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="a2892-327">[2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 이 항목 앞부분의 피싱 방지 규칙 섹션에 설명된 것과 같이 규칙을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-327">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="a2892-328">피싱 방지 규칙을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-328">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a2892-329">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="a2892-329">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="a2892-330">PowerShell을 사용하여 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a2892-330">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="a2892-331">PowerShell에서 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-331">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="a2892-332">기본 피싱 방지 정책을 사용하거나 사용하지 않도록 설정할 수 없습니다(모든 받는 사람에게 항상 적용됨).</span><span class="sxs-lookup"><span data-stu-id="a2892-332">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="a2892-333">PowerShell에서 피싱 방지 규칙을 사용하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-333">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="a2892-334">다음은 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-334">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a2892-335">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-335">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a2892-336">구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule 및](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [Disable-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="a2892-336">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="a2892-337">PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정하기</span><span class="sxs-lookup"><span data-stu-id="a2892-337">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="a2892-338">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-338">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a2892-339">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-339">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a2892-340">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-340">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a2892-341">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-341">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a2892-342">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-342">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a2892-343">PowerShell에서 피싱 방지 규칙의 우선순위를 설정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-343">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a2892-344">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-344">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a2892-345">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="a2892-345">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a2892-346">**참고:**</span><span class="sxs-lookup"><span data-stu-id="a2892-346">**Notes**:</span></span>

- <span data-ttu-id="a2892-347">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하려면 **New-AntiPhishRule** cmdlet의 _Priority_ 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-347">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="a2892-348">기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없고 항상 수정할 수 없는 우선순위 값이 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-348">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="a2892-349">PowerShell을 사용하여 피싱 방지 정책 제거하기</span><span class="sxs-lookup"><span data-stu-id="a2892-349">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="a2892-350">PowerShell을 사용하여 피싱 방지 정책을 제거할 때 해당 피싱 방지 규칙은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-350">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="a2892-351">PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-351">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a2892-352">이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-352">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a2892-353">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="a2892-353">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="a2892-354">PowerShell을 사용하여 피싱 방지 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="a2892-354">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="a2892-355">PowerShell을 사용하여 피싱 방지 규칙을 제거할 때 해당 피싱 방지 정책은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-355">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="a2892-356">PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a2892-356">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="a2892-357">이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-357">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="a2892-358">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참고하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="a2892-358">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a2892-359">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="a2892-359">How do you know these procedures worked?</span></span>

<span data-ttu-id="a2892-360">ATP 피싱 방지 정책을 성공적으로 구성되었는지 확인하려면 다음 단계를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2892-360">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="a2892-361">보안 그룹 & 위협 관리 **정책 방지** \> **Policy** \> **정책 방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-361">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="a2892-362">정책, 상태 값 및 **우선** 순위 값 목록을 **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2892-362">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a2892-363">자세한 내용을 보려면 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-363">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="a2892-364">목록에서 정책을 선택하 고 플라이아웃에서 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-364">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="a2892-365">기본 **정책을 클릭하고** 플라이아웃에서 세부 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-365">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="a2892-366">Exchange Online PowerShell에서 정책 \<Name\> 또는 규칙의 이름으로 바꾸고, 다음 명령을 실행하여 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2892-366">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
