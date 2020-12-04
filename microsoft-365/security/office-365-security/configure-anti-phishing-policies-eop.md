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
description: 관리자는 Exchange Online 사서함을 사용하거나 없는 EOP(Exchange Online Protection) 조직에서 사용할 수 있는 피싱 방지 정책을 만들고 수정하고 삭제하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 69ab17263ab8c0cc03d3bc4aed6bdf39b251b9fb
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572528"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="d8732-103">EOP에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="d8732-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d8732-104">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에는 기본적으로 사용하도록 설정된 제한된 수의 스푸핑 방지 기능을 포함하는 기본 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="d8732-105">자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="d8732-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="d8732-106">관리자는 기본 피싱 방지 정책을 보고 편집하고 구성할 수 있지만 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="d8732-107">세분성을 강화하기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용되는 사용자 지정 피싱 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d8732-108">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d8732-109">Exchange Online 사서함이 있는 조직은 보안 & 준수 센터 또는 Exchange Online PowerShell에서 피싱 방지 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="d8732-110">독립 실행형 EOP 조직은 보안 및 준수 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="d8732-111">Office 365용 Defender에서 사용할 수 있는 Microsoft Defender for Office 365의 고급 피싱 방지 정책을 만들고 수정하는 데 대한 자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-111">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="d8732-112">피싱 방지 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="d8732-113">**피싱** 방지 정책: 사용하도록 설정하거나 사용하지 않도록 설정할 피싱 보호 및 옵션을 적용할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="d8732-114">**피싱** 방지 규칙: 피싱 방지 정책에 대한 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="d8732-115">보안 및 준수 센터에서 피싱 방지 정책을 관리할 때 이러한 두 요소의 차이는 & 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d8732-116">피싱 방지 정책을 만들 때 실제로는 둘 다에 대해 동일한 이름을 사용하여 피싱 방지 규칙과 연결된 피싱 방지 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="d8732-117">피싱 방지 정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정, 받는 사람 필터와 관련된 설정은 피싱 방지 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="d8732-118">다른 모든 설정은 연결된 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="d8732-119">피싱 방지 정책을 제거하면 피싱 방지 규칙 및 연결된 피싱 방지 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="d8732-120">Exchange Online PowerShell에서는 정책과 규칙을 별도로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="d8732-121">자세한 내용은 이 문서 부분의 [Exchange Online PowerShell을](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 사용하여 피싱 방지 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="d8732-122">모든 조직에는 다음 속성이 있는 Office365 AntiPhish Default라는 기본 제공 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="d8732-123">이 정책은 정책과 연결된 피싱 방지 규칙(받는 사람 필터)이 없는 경우에도 조직의 모든 받는 사람에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="d8732-124">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="d8732-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d8732-125">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="d8732-126">그 정책이 기본 정책(**IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d8732-127">피싱 방지 보호의 효율성을 높이기 위해 특정 사용자 또는 사용자 그룹에 적용되는 더 엄격한 설정을 사용하여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d8732-128">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d8732-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d8732-129"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d8732-130">피싱 방지 **페이지로** 직접 이동하기 위해 다음을 <https://protection.office.com/antiphishing> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="d8732-131">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="d8732-132">독립 실행형 EOP PowerShell에서는 피싱 방지 정책을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="d8732-133">이 문서의 절차를 수행하려면 먼저 보안 및 준수 & 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-133">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d8732-134">피싱 방지 정책을 추가, 수정 및 삭제하려면 조직 관리 또는 **Organization Management** 보안 관리자 역할 그룹의 구성원이 **되거나** 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-134">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d8732-135">피싱 방지 정책에 대한 읽기 전용 액세스의 경우 전역 **Global Reader** 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** <sup>\*</sup> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-135">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="d8732-136">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="d8732-137">**참고**:</span><span class="sxs-lookup"><span data-stu-id="d8732-137">**Notes**:</span></span>

  - <span data-ttu-id="d8732-138">Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 & _and_ 준수 센터에서 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d8732-139">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-139">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="d8732-140">[또한 Exchange Online의](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 보기 **전용 조직 관리** 역할 그룹은 기능에 대한 읽기 전용 액세스를 <sup>\*</sup> 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-140">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="d8732-141"><sup>\*</sup> 보안 & 준수 센터에서 읽기 전용 액세스를 통해 사용자는 사용자 지정 피싱 방지 정책의 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-141"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="d8732-142">읽기 전용인 사용자는 기본 피싱 방지 정책의 설정을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-142">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="d8732-143">독립 실행형 EOP에서 피싱 방지 정책을 만들고 수정하려면 테넌트에 대한 하이드레이션이 필요한 작업을 해야 합니다. _hydration_</span><span class="sxs-lookup"><span data-stu-id="d8732-143">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="d8732-144">예를 들어 EAC(Exchange 관리 센터)에서 사용 **Permissions** 권한 탭으로 이동하여 기존 **Edit** 역할 그룹을 선택하고 편집 아이콘을 클릭한 다음 역할을 제거할 수 있습니다(최종적으로 다시 추가). ![ ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="d8732-144">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="d8732-145">테넌트가 하이드레이션된 적이 없는 경우 **Update Organization Settings** 성공적으로 완료해야 하는 진행률 표시줄이 있는 조직 설정 업데이트라는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-145">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="d8732-146">하이드레이션에 대한 자세한 내용은 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet(독립 실행형 EOP PowerShell 또는 보안 및 준수 센터에서는 사용할 수 & 없습니다.)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-146">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="d8732-147">피싱 방지 정책에 대한 권장 설정은 EOP 기본 피싱 방지 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="d8732-147">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="d8732-148">업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-148">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="d8732-149">필터링 파이프라인에서 피싱 방지 정책이 적용되는 위치는 전자 메일 보호의 순서 및 우선 순위를 [참조하세요.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="d8732-149">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="d8732-150">보안 및 & 센터를 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d8732-150">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="d8732-151">보안 & 준수 센터에서 사용자 지정 피싱 방지 정책을 만들면 피싱 방지 규칙과 연결된 피싱 방지 정책이 동시에 동일한 이름의 피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-151">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="d8732-152">피싱 방지 정책을 만들 때 정책이 적용되는 사람을 식별하는 정책 이름, 설명 및 받는 사람 필터만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-152">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="d8732-153">정책을 만든 후 기본 피싱 방지 설정을 변경하거나 검토하도록 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-153">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="d8732-154">보안 및 & 센터에서 위협 **관리** 정책 피싱 \> **Policy** \> **방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d8732-155">피싱 **방지** 페이지에서 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-155">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="d8732-156">새 피싱 방지 정책 **만들기 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-156">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="d8732-157">정책 **이름 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-157">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="d8732-158">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-158">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d8732-159">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-159">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d8732-160">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-160">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d8732-161">적용 **대상** 페이지가 나타나면 정책이 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-161">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="d8732-162">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-162">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d8732-163">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="d8732-163">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d8732-164">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d8732-164">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="d8732-165">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-165">Click **Add a condition**.</span></span> <span data-ttu-id="d8732-166">나타나는 드롭다운에서 적용된 조건(다음의 **경우)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-166">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="d8732-167">**받는 사람:** 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-167">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d8732-168">**받는 사람이 다음의** 구성원입니다. 조직에서 하나 이상의 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-168">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="d8732-169">**받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-169">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="d8732-170">조건을 선택하면 해당 드롭다운이 다음 **상자와 함께** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-170">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="d8732-171">상자를 클릭하고 선택할 값 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-171">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="d8732-172">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-172">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="d8732-173">값을 더 추가하려면 상자의 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-173">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="d8732-174">개별 항목을 제거하려면 **Remove** 값에서 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-174">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="d8732-175">전체 조건을 제거하려면 **조건에서** 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-175">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="d8732-176">조건을 더 추가하려면 **조건** 추가를 클릭하고 적용된 경우 나머지 **값을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-176">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="d8732-177">예외를 추가하려면 **조건** 추가를 클릭하고 다음의 예외를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-177">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="d8732-178">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-178">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d8732-179">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-179">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d8732-180">나타나는 **설정** 검토 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-180">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="d8732-181">각 **설정에서** 편집을 클릭하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-181">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="d8732-182">완료되면 이 정책 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-182">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="d8732-183">확인 **대화** 상자가 나타나면 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-183">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="d8732-184">이러한 일반 정책 설정을 사용하여 피싱 방지 정책을 만든 후 다음 섹션의 지침을 사용하여 정책의 보호 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-184">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="d8732-185">보안 및 & 센터를 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="d8732-185">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="d8732-186">다음 절차에 따라 만든 새 정책 또는 이미 사용자 지정한 기존 정책과 같은 피싱 방지 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-186">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="d8732-187">아직 없는 경우 보안 및 준수 센터를 & 위협 **관리** 정책 피싱 \> **Policy** \> **방지로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-187">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d8732-188">수정할 사용자 지정 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-188">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="d8732-189">이미 선택되어 있는 경우 선택을 선택을 했다가 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-189">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d8732-190">정책 **편집 \<name\> 플라이아웃이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-190">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="d8732-191">모든 **섹션에서** 편집을 클릭하면 해당 섹션의 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-191">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="d8732-192">다음 단계는 섹션이 나타나는 순서대로 나타나지만 순서에 구문을 추가하지는 않습니다(순서에 따라 섹션을 선택하고 수정할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="d8732-192">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="d8732-193">섹션에서 **Edit** 편집을 클릭하면 사용 가능한 설정이 마법사 형식으로 제공되지만 순서에 따라 페이지 내에서 점프할 수 있습니다. **Cancel** **Save** **Close** ![ ](../../media/scc-remove-icon.png) **\<name\>** 또는 페이지에서 저장 또는 닫기 아이콘을 클릭하여 정책 편집 페이지로 돌아올 수 있습니다(저장하거나 남기기 위해 마법사의 마지막 페이지를 방문할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="d8732-193">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="d8732-194">**정책 설정:** **편집을** 클릭하여 이전 섹션에서 [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) 정책을 만들 때 사용 가능한 설정과 동일한 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-194">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="d8732-195">**이름**</span><span class="sxs-lookup"><span data-stu-id="d8732-195">**Name**</span></span>
   - <span data-ttu-id="d8732-196">**설명**</span><span class="sxs-lookup"><span data-stu-id="d8732-196">**Description**</span></span>
   - <span data-ttu-id="d8732-197">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="d8732-197">**Applied to**</span></span>
   - <span data-ttu-id="d8732-198">**설정 검토**</span><span class="sxs-lookup"><span data-stu-id="d8732-198">**Review your settings**</span></span>

   <span data-ttu-id="d8732-199">완료되면 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-199">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="d8732-200">**스푸핑**: **편집을** 클릭하여 스푸핑 인텔리전스를 켜거나 끄고, Outlook에서 확인되지 않은 보낸 사람 ID를 설정 또는 해제하고, 차단된 스푸핑된 보낸 사람이 보낸 메시지에 적용할 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-200">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="d8732-201">자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="d8732-201">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="d8732-202">이러한 동일한 설정은 Office 365용 Defender의 피싱 방지 정책에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-202">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="d8732-203">**스푸핑 필터 설정:** 기본값은 **On으로** 설정되어 있으며 그대로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-203">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="d8732-204">끄기 위해 토글을 끄면 **끄기**</span><span class="sxs-lookup"><span data-stu-id="d8732-204">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="d8732-205">자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="d8732-205">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d8732-206">MX 레코드가 Microsoft 365를 사용하지 않는 경우 스푸핑 방지 보호 기능을 사용하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대해 향상된 필터링을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-206">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="d8732-207">자세한 내용은 Exchange Online의 커넥터에 대한 향상된 [필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="d8732-207">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="d8732-208">**사용 안 하도록** 설정 보낸 사람 기능 : 기본값은 **On입니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-208">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="d8732-209">끄기 위해 토글을 끄면 **끄기**</span><span class="sxs-lookup"><span data-stu-id="d8732-209">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="d8732-210">**작업:** 스푸핑 인텔리전스에 실패한 메시지에 대해 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-210">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="d8732-211">**도메인을 스푸핑할** 수 없는 사람이 전자 메일을 보낸 경우:</span><span class="sxs-lookup"><span data-stu-id="d8732-211">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="d8732-212">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="d8732-212">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="d8732-213">**메시지에 대한 검소리**</span><span class="sxs-lookup"><span data-stu-id="d8732-213">**Quarantine the message**</span></span>

   - <span data-ttu-id="d8732-214">**설정 검토:** 각 개별 단계를 클릭하는 대신 설정이 요약에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-214">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="d8732-215">각 **섹션에서** 편집을 클릭하여 관련 페이지로 다시 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-215">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="d8732-216">이 페이지에서 직접 다음 설정을 **Off** **설정 또는** 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-216">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="d8732-217">**스푸핑 방지 보호 사용**</span><span class="sxs-lookup"><span data-stu-id="d8732-217">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="d8732-218">**비인식 보낸 사람 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="d8732-218">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="d8732-219">완료되면 페이지에서 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-219">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="d8732-220">정책 편집 **\<Name\> 페이지에서** 설정을 검토한 다음 닫기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-220">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="d8732-221">보안 및 & 센터를 사용하여 기본 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="d8732-221">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="d8732-222">기본 피싱 방지 정책의 이름은 Office365 AntiPhish Default로 지정되어 있으며 정책 목록에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-222">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="d8732-223">기본 피싱 방지 정책을 수정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-223">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="d8732-224">보안 및 & 센터에서 위협 **관리** 정책 피싱 \> **Policy** \> **방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d8732-225">피싱 **방지 페이지에서** 기본 정책을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-225">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="d8732-226">The **Edit your policy Office365 AntiPhish Default** page appears.</span><span class="sxs-lookup"><span data-stu-id="d8732-226">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="d8732-227">사용자 지정 정책을 수정할 때와 동일한 설정을 포함하는 다음 섹션을 사용할 [수 있습니다.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="d8732-227">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="d8732-228">**가장**</span><span class="sxs-lookup"><span data-stu-id="d8732-228">**Impersonation**</span></span>
   - <span data-ttu-id="d8732-229">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="d8732-229">**Spoof**</span></span>
   - <span data-ttu-id="d8732-230">**고급 설정**</span><span class="sxs-lookup"><span data-stu-id="d8732-230">**Advanced settings**</span></span>

   <span data-ttu-id="d8732-231">기본 정책을 수정할 때 다음 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-231">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="d8732-232">정책 설정 **Policy setting** 섹션과 값을 볼 수 있지만 **Edit** 편집 링크는 있으므로 설정(정책 이름, 설명 및 정책이 적용되는 사람)을 수정할 수 없습니다(모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="d8732-232">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="d8732-233">기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-233">You can't delete the default policy.</span></span>
   - <span data-ttu-id="d8732-234">기본 정책의 우선 순위는 변경할 수 없습니다(항상 마지막에 적용).</span><span class="sxs-lookup"><span data-stu-id="d8732-234">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="d8732-235">On the **Edit your policy Office365 AntiPhish Default page,** review your settings and then click **Close.**</span><span class="sxs-lookup"><span data-stu-id="d8732-235">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="d8732-236">사용자 지정 피싱 방지 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d8732-236">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="d8732-237">보안 및 & 센터에서 위협 **관리** 정책 피싱 \> **Policy** \> **방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-237">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d8732-238">상태 열의 **값을** 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-238">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="d8732-239">토글을 **해제로 밀어** 정책을 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-239">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="d8732-240">토글을 **설정으로 밀어** 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-240">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="d8732-241">기본 피싱 방지 정책은 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-241">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="d8732-242">사용자 지정 피싱 방지 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="d8732-242">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="d8732-243">기본적으로 피싱 방지 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="d8732-243">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="d8732-244">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="d8732-244">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d8732-245">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-245">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="d8732-246">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-246">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="d8732-247">사용자 지정 피싱 방지 정책은 처리되는 순서대로 표시됩니다(첫 번째 **Priority** 정책의 우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="d8732-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d8732-248">Office365 AntiPhish Default라는 기본 피싱 방지 정책은 사용자 지정 우선 순위 값이 **가장** 낮습니다. 이 정책은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="d8732-249">**참고:** 보안 & 준수 센터에서는 피싱 방지 정책의 우선 순위를 변경할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="d8732-250">PowerShell에서 피싱 방지 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="d8732-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d8732-251">정책의 우선 순위를 변경하려면 정책 **Decrease priority** 속성에서 우선 순위 늘리기 또는 우선 순위 **Priority** 감소를 클릭합니다(보안 및 준수 센터에서 우선 순위 번호를 직접 수정할 & 없습니다). **Increase priority**</span><span class="sxs-lookup"><span data-stu-id="d8732-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="d8732-252">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="d8732-253">보안 & 준수 센터에서 위협 관리 **Threat management** 정책 ATP 피싱 \> **Policy** \> **방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d8732-254">수정할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="d8732-255">이미 선택되어 있는 경우 선택을 선택을 했다가 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d8732-256">정책 **편집 \<name\> 플라이아웃이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="d8732-257">우선 순위 값이 **0인** **Priority** 사용자 지정 피싱 방지 정책에는 우선 순위 감소 단추만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="d8732-258">우선 순위 값이 가장 낮은 사용자 **Priority** 지정 피싱 방지 정책(예: **3)에는** 우선 순위 늘리기 단추만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="d8732-259">사용자 지정 피싱 방지 정책이 세 개 이상 있는 경우 우선 순위가 가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 단추를 모두 사용할 **수** 있습니다. **Increase priority**</span><span class="sxs-lookup"><span data-stu-id="d8732-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="d8732-260">우선 **순위 늘리기 또는** 우선 순위 **감소를** 클릭하여 우선 순위 값을 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="d8732-261">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="d8732-262">보안 및 & 센터를 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="d8732-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="d8732-263">보안 & 준수 센터에서 위협 **관리** 정책 피싱 \> **Policy** \> **방지로 이동**</span><span class="sxs-lookup"><span data-stu-id="d8732-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d8732-264">다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="d8732-265">보하려는 사용자 지정 피싱 방지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="d8732-266">이미 선택되어 있는 경우 선택을 선택을 했다가 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="d8732-267">기본 **정책을 클릭하여** 기본 피싱 방지 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="d8732-268">설정 **및 \<name\> 값을 볼** 수 있는 정책 플라이아웃 편집이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="d8732-269">보안 및 & 센터를 사용하여 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d8732-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="d8732-270">보안 및 & 센터에서 위협 **관리** 정책 피싱 \> **Policy** \> **방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d8732-271">제거할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="d8732-272">이미 선택되어 있는 경우 선택을 선택을 했다가 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d8732-273">나타나는 **\<name\> 정책** 플라이아웃 편집에서 정책 **Delete policy** 삭제를 클릭한 다음 나타나는 경고 대화 상자에서 **예를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d8732-274">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="d8732-275">Exchange Online PowerShell을 사용하여 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="d8732-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="d8732-276">앞서 설명한 바와 같이 피싱 방지 정책은 피싱 방지 정책과 피싱 방지 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-276">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="d8732-277">Exchange Online PowerShell에서는 피싱 방지 정책과 피싱 방지 규칙의 차이점이 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-277">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="d8732-278">**\* -AntiPhishPolicy** cmdlet을 사용하여 피싱 방지 정책을 관리하고 **\* -AntiPhishRule** cmdlet을 사용하여 피싱 방지 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-278">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="d8732-279">PowerShell에서 먼저 피싱 방지 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-279">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d8732-280">PowerShell에서는 피싱 방지 정책 및 피싱 방지 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-280">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="d8732-281">PowerShell에서 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-281">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="d8732-282">다음 PowerShell 절차는 Exchange Online Protection PowerShell을 사용하는 독립 실행형 EOP 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-282">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="d8732-283">PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d8732-283">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="d8732-284">PowerShell에서 피싱 방지 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-284">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d8732-285">피싱 방지 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-285">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="d8732-286">규칙이 적용되는 피싱 방지 정책을 지정하는 피싱 방지 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-286">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="d8732-287">**참고**:</span><span class="sxs-lookup"><span data-stu-id="d8732-287">**Notes**:</span></span>

- <span data-ttu-id="d8732-288">새 피싱 방지 규칙을 만들고 기존의 통합되지 않은 피싱 방지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-288">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="d8732-289">피싱 방지 규칙은 피싱 방지 정책과 두 개 이상 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-289">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="d8732-290">정책을 만들 때까지 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새 피싱 방지 정책에 대해 & 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-290">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d8732-291">새 정책을 사용할 수 _Enabled_ `$false` **없습니다(New-AntiPhishRule** cmdlet에서 사용).</span><span class="sxs-lookup"><span data-stu-id="d8732-291">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="d8732-292">_Priority_ _\<Number\>_ **New-AntiPhishRule** cmdlet에서 만들기 중 정책의 우선 순위(우선 순위)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-292">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="d8732-293">PowerShell에서 만든 새로운 피싱 방지 정책은 피싱 방지 규칙에 정책을 할당할 때까지 보안 & 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-293">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="d8732-294">1단계: PowerShell을 사용하여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d8732-294">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="d8732-295">피싱 방지 정책을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-295">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="d8732-296">이 예에서는 다음 설정을 사용하여 Research Quarantine이라는 피싱 방지 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-296">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="d8732-297">설명은 리서치 부서 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-297">The description is: Research department policy.</span></span>
- <span data-ttu-id="d8732-298">스푸핑에 대한 기본 작업을 Quarantine으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-298">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="d8732-299">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="d8732-299">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="d8732-300">2단계: PowerShell을 사용하여 피싱 방지 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="d8732-300">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="d8732-301">피싱 방지 규칙을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-301">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d8732-302">이 예에서는 다음 조건을 통해 Research Department라는 피싱 방지 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-302">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="d8732-303">이 규칙은 Research Quarantine이라는 피싱 방지 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-303">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="d8732-304">이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-304">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="d8732-305">Priority 매개 변수를 _Priority_ 사용하지 않는 경우 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-305">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="d8732-306">구문과 매개 변수에 대한 자세한 내용은 [New-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="d8732-306">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="d8732-307">PowerShell을 사용하여 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="d8732-307">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="d8732-308">기존 피싱 방지 정책을 보시다시피 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-308">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d8732-309">이 예에서는 지정된 속성과 함께 모든 피싱 방지 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-309">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="d8732-310">이 예에서는 Executives라는 피싱 방지 정책의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-310">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="d8732-311">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="d8732-311">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="d8732-312">PowerShell을 사용하여 피싱 방지 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="d8732-312">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="d8732-313">기존 피싱 방지 규칙을 보시다시피 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-313">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d8732-314">이 예제에서는 지정된 속성과 함께 모든 피싱 방지 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-314">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="d8732-315">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-315">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="d8732-316">이 예에서는 Contoso Executives라는 피싱 방지 규칙의 모든 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-316">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="d8732-317">구문과 매개 변수에 대한 자세한 내용은 [Get-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="d8732-317">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="d8732-318">PowerShell을 사용하여 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="d8732-318">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="d8732-319">다음 항목 이외에도 이 문서의 앞부분에서 설명한 대로 PowerShell에서 피싱 방지 정책을 수정할 때와 동일한 설정을 사용할 수 있습니다. [1단계: PowerShell을](#step-1-use-powershell-to-create-an-anti-phish-policy) 사용하여 피싱 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-319">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="d8732-320">지정된 정책을 기본 정책으로 전환하는 _MakeDefault_ 스위치는 PowerShell에서 피싱 방지 정책을 수정할 때만 사용할 수 있습니다(모든 사용자, 항상 최하위 우선 순위 및 삭제할 수 없습니다). **Lowest**</span><span class="sxs-lookup"><span data-stu-id="d8732-320">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="d8732-321">피싱 방지 정책의 이름을 다시 설정할 수 **없습니다(Set-AntiPhishPolicy** cmdlet에는 Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="d8732-321">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d8732-322">보안 및 준수 센터에서 피싱 방지 정책의 & 경우 피싱 방지 규칙의 이름만 다시 _매기게 됩니다._</span><span class="sxs-lookup"><span data-stu-id="d8732-322">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="d8732-323">피싱 방지 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-323">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d8732-324">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="d8732-324">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="d8732-325">PowerShell을 사용하여 피싱 방지 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="d8732-325">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="d8732-326">PowerShell에서 피싱 방지 규칙을 수정할 때 사용할 수 없는 설정은 _사용되지_ 않는 규칙을 만들 수 있는 Enabled 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-326">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d8732-327">기존 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8732-327">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="d8732-328">그렇지 않으면 [2단계: PowerShell을](#step-2-use-powershell-to-create-an-anti-phish-rule) 사용하여 이 문서의 앞부분에서 설명한 대로 피싱 방지 규칙 섹션을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-328">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="d8732-329">피싱 방지 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-329">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d8732-330">구문과 매개 변수에 대한 자세한 내용은 [Set-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="d8732-330">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="d8732-331">PowerShell을 사용하여 피싱 방지 규칙을 활성화 또는 비활성화</span><span class="sxs-lookup"><span data-stu-id="d8732-331">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="d8732-332">PowerShell에서 피싱 방지 규칙을 설정하거나 사용하지 않도록 설정하면 전체 피싱 방지 정책(피싱 방지 규칙 및 할당된 피싱 방지 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-332">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="d8732-333">기본 피싱 방지 정책을 활성화하거나 사용하지 않도록 설정할 수 없습니다(항상 모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="d8732-333">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="d8732-334">PowerShell에서 피싱 방지 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-334">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="d8732-335">이 예에서는 Marketing Department라는 피싱 방지 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-335">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d8732-336">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-336">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d8732-337">구문과 매개 변수에 대한 자세한 내용은 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 및 [Disable-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="d8732-337">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="d8732-338">PowerShell을 사용하여 피싱 방지 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="d8732-338">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="d8732-339">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d8732-340">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d8732-341">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d8732-342">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d8732-343">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d8732-344">PowerShell에서 피싱 방지 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-344">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d8732-345">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-345">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d8732-346">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="d8732-346">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d8732-347">**참고:**</span><span class="sxs-lookup"><span data-stu-id="d8732-347">**Notes**:</span></span>

- <span data-ttu-id="d8732-348">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-AntiPhishRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-348">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="d8732-349">기본 피싱 방지 정책에는 해당하는 피싱 방지 규칙이 없습니다. 항상 이 정책의 우선 순위는 **가장 낮습니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-349">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="d8732-350">PowerShell을 사용하여 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d8732-350">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="d8732-351">PowerShell을 사용하여 피싱 방지 정책을 제거하면 해당 피싱 방지 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-351">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="d8732-352">PowerShell에서 피싱 방지 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-352">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d8732-353">이 예에서는 Marketing Department라는 피싱 방지 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-353">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d8732-354">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="d8732-354">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="d8732-355">PowerShell을 사용하여 피싱 방지 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="d8732-355">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="d8732-356">PowerShell을 사용하여 피싱 방지 규칙을 제거하면 해당 피싱 방지 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-356">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="d8732-357">PowerShell에서 피싱 방지 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-357">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="d8732-358">이 예에서는 Marketing Department라는 피싱 방지 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-358">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d8732-359">구문과 매개 변수에 대한 자세한 내용은 [Remove-AntiPhishRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="d8732-359">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d8732-360">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="d8732-360">How do you know these procedures worked?</span></span>

<span data-ttu-id="d8732-361">Office 365용 Microsoft Defender에서 피싱 방지 정책을 성공적으로 구성한지 확인하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-361">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="d8732-362">보안 및 & 센터에서 위협 **관리** 정책 피싱 \> **Policy** \> **방지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-362">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="d8732-363">정책 목록, **정책** 상태 값 및 우선 순위 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8732-363">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="d8732-364">자세한 내용을 확인하면 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-364">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="d8732-365">목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-365">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="d8732-366">기본 **정책을 클릭하고** 플라이아웃에서 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-366">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="d8732-367">Exchange Online PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d8732-367">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
