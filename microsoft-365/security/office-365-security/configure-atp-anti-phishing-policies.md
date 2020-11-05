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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for Office 365를 사용 하 여 조직에서 사용할 수 있는 고급 피싱 방지 정책을 만들고, 수정 하 고, 삭제 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: ecc68a8dc050a5f08c6982b023861e0ea8976775
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920659"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-103">Microsoft Defender for Office 365에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="35a57-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="35a57-104">[Microsoft Defender For Office 365](office-365-atp.md) 의 피싱 방지 정책은 공격자가 악의적인 가장 기반 피싱 공격 및 기타 유형의 피싱 공격 으로부터 조직을 보호 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="35a57-105">EOP (Exchange Online Protection)의 피싱 방지 정책 및 Office 용 Microsoft Defender 365의 피싱 방지 정책 간의 차이점에 대 한 자세한 내용은 [피싱 방지 보호](anti-phishing-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="35a57-106">관리자는 기본 피싱 방지 정책을 보고 편집 하 고 구성할 수 있습니다 (삭제 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="35a57-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="35a57-107">세분성을 높이기 위해 조직의 특정 사용자, 그룹 또는 도메인에 적용 되는 사용자 지정 피싱 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="35a57-108">사용자 지정 정책은 항상 기본 정책보다 우선하지만, 사용자 지정 정책의 우선순위(실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="35a57-109">보안 & 준수 센터 또는 Exchange Online PowerShell에서 피싱 방지 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="35a57-110">Exchange Online Protection 조직에서 사용할 수 있는 피싱 방지 정책에서 더 제한 된 기능 365을 구성 하는 방법에 대 한 자세한 내용은 [EOP에서 피싱 방지 정책 구성을](configure-anti-phishing-policies-eop.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="35a57-111">피싱 방지 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="35a57-112">**피싱 정책** : 사용 하거나 사용 하지 않도록 설정할 피싱 보호를 지정 하 고 옵션을 적용 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-112">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="35a57-113">**피싱 규칙** : 피싱 정책에 대해 정책이 적용 되는 우선 순위 및 받는 사람 필터를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-113">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="35a57-114">보안 & 준수 센터에서 피싱 방지 정책을 관리할 때는 이러한 두 가지 요소 간의 차이가 명확 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="35a57-115">정책을 만들 때 실제로는 피싱 규칙과 관련 된 피싱 정책을 모두 같은 이름으로 사용 하 여 동시에 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="35a57-116">정책을 수정 하면 이름, 우선 순위, 사용/사용 안 함 및 받는 사람 필터와 관련 된 설정이 피싱 규칙을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="35a57-117">다른 모든 설정은 연결 된 피싱 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="35a57-118">정책을 제거 하면 피싱 규칙과 연결 된 피싱 정책이 모두 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="35a57-119">Exchange Online PowerShell에서는 정책과 규칙을 별도로 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="35a57-120">자세한 내용은이 항목 뒷부분에 나오는 [Microsoft Defender For Office 365 섹션에서 Exchange Online PowerShell을 사용 하 여 피싱 방지 정책을 구성 하](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) 는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="35a57-121">모든 Microsoft Defender for Office 365 조직에는 다음 속성이 포함 된 Office365 AntiPhish Default 라는 피싱 방지 정책이 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="35a57-122">정책과 연결 된 피싱 규칙 (받는 사람 필터)이 없더라도 조직의 모든 받는 사람에 게 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="35a57-123">정책의 사용자 지정 우선순위 값은 **가장 낮음** 이며 변경할 수 없습니다(이 정책은 항상 마지막으로 적용됨).</span><span class="sxs-lookup"><span data-stu-id="35a57-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="35a57-124">사용자가 만든 모든 사용자 지정 정책은 항상 더 높은 우선순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="35a57-125">그 정책이 기본 정책( **IsDefault** 속성의 값은 `True`)이고, 기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="35a57-126">Microsoft Defender for Office 365에서 피싱 방지 보호 기능의 효율성을 높이려면 특정 사용자나 사용자 그룹에 적용 되는 보다 엄격한 설정을 사용 하 여 사용자 지정 피싱 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="35a57-127">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="35a57-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="35a57-128"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="35a57-129">**ATP 피싱 방지** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/antiphishing> 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="35a57-130">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="35a57-131">이 문서의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="35a57-132">피싱 방지 정책을 추가, 수정 및 삭제 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-132">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="35a57-133">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="35a57-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="35a57-134">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="35a57-134">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="35a57-135">피싱 방지 정책에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-135">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="35a57-136">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="35a57-136">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="35a57-137">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="35a57-137">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="35a57-138">Microsoft Defender for Office 365의 피싱 방지 정책에 대 한 권장 설정에 대해서는 [Defender For office 365 설정에서 피싱 방지 정책을](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-138">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="35a57-139">새 정책이 나 업데이트 된 정책을 적용할 최대 30 분을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-139">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="35a57-140">필터링 파이프라인에서 피싱 방지 정책이 적용 되는 위치에 대 한 자세한 내용은 [전자 메일 보호의 주문 및 우선 순위](how-policies-and-protections-are-combined.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-140">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-141">보안 & 준수 센터를 사용 하 여 Microsoft Defender for Office 365의 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="35a57-141">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="35a57-142">보안 & 준수 센터에서 사용자 지정 피싱 방지 정책을 만들면 두 가지 모두에 동일한 이름을 사용 하 여 피싱 규칙과 연결 된 피싱 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-142">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="35a57-143">피싱 방지 정책을 만들 때 정책 이름, 설명 및 정책이 적용 되는 사람을 식별 하는 받는 사람 필터를 지정할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-143">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="35a57-144">정책을 만든 후에 정책을 수정 하 여 기본 피싱 방지 설정을 변경 하거나 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-144">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="35a57-145">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35a57-146">**피싱 방지** 페이지에서 **만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-146">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="35a57-147">**새 피싱 방지 정책 만들기** 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-147">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="35a57-148">**정책 이름** 설정 페이지에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="35a57-149">**이름** : 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-149">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="35a57-150">**설명** : 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-150">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="35a57-151">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="35a57-152">**적용 대상** 페이지에서 정책이 적용 되는 내부 받는 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-152">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="35a57-153">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-153">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="35a57-154">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="35a57-154">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="35a57-155">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="35a57-155">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="35a57-156">**조건 추가를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-156">Click **Add a condition**.</span></span> <span data-ttu-id="35a57-157">표시 되는 드롭다운 목록에서 다음의 **경우 적용** 아래의 조건을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-157">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="35a57-158">**받는 사람** : 조직의 사서함, 메일 사용자 또는 메일 연락처를 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-158">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="35a57-159">**받는 사람이 다음 구성원 인** 경우: 조직에서 그룹을 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-159">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="35a57-160">**받는 사람 도메인** : 조직에서 구성 된 허용 도메인 중 하나 이상의 받는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-160">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="35a57-161">조건을 선택한 후에는 **이러한 상자 중 하나** 에 해당 하는 dropdown이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-161">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="35a57-162">상자를 클릭 하 고 선택할 값 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-162">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="35a57-163">상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-163">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="35a57-164">값을 더 추가 하려면 상자에서 빈 영역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-164">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="35a57-165">개별 항목을 제거 하려면 값에서 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-165">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="35a57-166">전체 조건을 제거 하려면 **Remove** ![ 조건에서 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-166">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="35a57-167">조건을 더 추가 하려면 **조건 추가** 를 클릭 하 고 **적용 된 경우** 에는 나머지 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-167">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="35a57-168">예외를 추가 하려면 **조건 추가** 를 클릭 하 고 다음의 **경우 제외** 에서 예외를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-168">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="35a57-169">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="35a57-170">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="35a57-171">**설정 검토** 페이지가 나타나면 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-171">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="35a57-172">각 설정에 대해 **편집** 을 클릭 하 여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-172">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="35a57-173">작업이 완료 되 면 **이 정책 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-173">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="35a57-174">나타나는 확인 대화 상자에서 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-174">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="35a57-175">이러한 일반 설정을 사용 하 여 피싱 방지 정책을 만든 후에는 다음 섹션의 지침을 사용 하 여 정책에서 보호 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-175">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-176">보안 & 준수 센터를 사용 하 여 Microsoft Defender for Office 365의 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35a57-176">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="35a57-177">다음 절차에 따라 새로 만든 정책 또는 이미 사용자 지정 했던 기존 정책을 사용 하 여 피싱 방지 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-177">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="35a57-178">아직 없는 경우 보안 & 준수 센터를 열고 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-178">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35a57-179">수정 하려는 사용자 지정 피싱 방지 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-179">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="35a57-180">이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-180">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="35a57-181">정책 플라이 아웃 **\<name\> 편집** 이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-181">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="35a57-182">섹션에서 **편집** 을 클릭 하면 해당 섹션의 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-182">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="35a57-183">다음 단계는 섹션에 표시 되는 순서 대로 제공 되지만 순서에 관계 없이 섹션을 선택 하 고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-183">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="35a57-184">섹션에서 **편집** 을 클릭 하면 사용 가능한 설정이 마법사 형식으로 제공 되지만 페이지 **내에서 언제** 든 지 페이지를 이동할 수 있습니다. **또는** 닫기 아이콘을 클릭 하 여 **Close** ![ ](../../media/scc-remove-icon.png) **\<name\> 정책 편집** 페이지로 돌아갈 수 있습니다 (마법사의 마지막 페이지를 방문 하 여 저장 하거나 나갈 필요가 없음).</span><span class="sxs-lookup"><span data-stu-id="35a57-184">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="35a57-185">**정책 설정** : 이전 섹션에서 [정책을 만들](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) 때 사용 가능한 것과 동일한 설정을 수정 하려면 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-185">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="35a57-186">**이름**</span><span class="sxs-lookup"><span data-stu-id="35a57-186">**Name**</span></span>
   - <span data-ttu-id="35a57-187">**설명**</span><span class="sxs-lookup"><span data-stu-id="35a57-187">**Description**</span></span>
   - <span data-ttu-id="35a57-188">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="35a57-188">**Applied to**</span></span>
   - <span data-ttu-id="35a57-189">**설정 검토**</span><span class="sxs-lookup"><span data-stu-id="35a57-189">**Review your settings**</span></span>

   <span data-ttu-id="35a57-190">작업이 끝나면 모든 페이지에서 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-190">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="35a57-191">**가장** : 정책에서 **편집** 을 클릭 하 여 보호 된 보낸 사람 및 보호 된 도메인을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-191">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="35a57-192">이러한 설정은 인바운드 메시지의 보낸 사람 주소에서 찾을 수 있도록 (개별적으로 또는 도메인) 확인 되는 정책에 대 한 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-192">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="35a57-193">자세한 내용은 [Office 용 Microsoft Defender 365의 피싱 방지 정책에서 가장 설정을](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-193">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="35a57-194">**보호할 사용자 추가** : 기본값은 **Off** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-194">**Add users to protect** : The default value is **Off**.</span></span> <span data-ttu-id="35a57-195">설정 하려면 켜기/끄기를 **설정 하 고** 표시 되는 **사용자 추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-195">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="35a57-196">사용자 플라이 아웃 **추가** 가 표시 되 면 다음 값을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-196">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="35a57-197">**전자 메일 주소** :</span><span class="sxs-lookup"><span data-stu-id="35a57-197">**Email address** :</span></span>

       - <span data-ttu-id="35a57-198">상자를 클릭 하 고 선택할 사용자 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-198">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="35a57-199">상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-199">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="35a57-200">항목을 제거 하려면 **Remove** ![ 사용자에 대해 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-200">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="35a57-201">**이름** :이 값은 선택한 전자 메일 주소를 기준으로 채워지고 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-201">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="35a57-202">작업이 끝나면 모든 페이지에서 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-202">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="35a57-203">기존 항목을 편집 하려면 목록에서 보호 된 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-203">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     > <span data-ttu-id="35a57-204">모든 피싱 방지 정책에서 최대 60 명의 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-204">You can have a maximum of 60 users in all anti-phishing policies.</span></span> <span data-ttu-id="35a57-205">즉, 60는 한 정책에서 보호 된 사용자 12 명, 5 개의 보호 된 사용자의 경우에는 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-205">In other words, you can have 60 protected users in one policy, 12 protected users in 5 policies, etc.</span></span>

   - <span data-ttu-id="35a57-206">**보호할 도메인 추가** : 다음 설정 중 하나 또는 둘 다를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-206">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="35a57-207">**소유한 도메인을 자동으로 포함** : 기본값은 **Off** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-207">**Automatically include the domains I own** : The default value is **Off**.</span></span> <span data-ttu-id="35a57-208">설정 하려면 **슬라이드를 설정 합니다 .로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="35a57-209">**사용자 지정 도메인 포함** : 기본값은 **Off** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-209">**Include custom domains** : The default value is **Off**.</span></span> <span data-ttu-id="35a57-210">이 옵션을 설정 하려면 켜기/끄기를 **켜** 세요. 도메인 **추가** 상자에 도메인 이름 (예: contoso.com)을 입력 하 고 enter 키를 누른 다음 필요에 따라 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-210">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="35a57-211">모든 피싱 방지 정책에 최대 50 개의 도메인을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-211">You can have a maximum of 50 domains in all anti-phishing policies.</span></span> <span data-ttu-id="35a57-212">즉, 50의 보호 된 사용자는 한 정책에서, 10 개의 보호 된 사용자는 5 정책 등을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-212">In other words, you can have 50 protected users in one policy, 10 protected users in 5 policies, etc.</span></span>

   - <span data-ttu-id="35a57-213">**작업** : **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-213">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="35a57-214">**가장 된 사용자가 전자 메일을 보낸 경우** : 스푸핑된 보낸 사람이 **보호할 사용자 추가** 에 지정한 보호 된 사용자 중 하나인 메시지에 대해 다음 작업 중 하나를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-214">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="35a57-215">**작업 적용 안 함**</span><span class="sxs-lookup"><span data-stu-id="35a57-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="35a57-216">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="35a57-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="35a57-217">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="35a57-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="35a57-218">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="35a57-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="35a57-219">**메시지를 배달 하 고 숨은 참조 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="35a57-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="35a57-220">**메시지를 배달 하기 전에 삭제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="35a57-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="35a57-221">**가장 된 도메인이 전자 메일을 보낸 경우** : 스푸핑된 보낸 사람이 **보호할 도메인** 에 지정 된 보호 된 도메인 중 하나에 있는 메시지에 대해 다음 작업 중 하나를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-221">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

       - <span data-ttu-id="35a57-222">**작업 적용 안 함**</span><span class="sxs-lookup"><span data-stu-id="35a57-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="35a57-223">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="35a57-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="35a57-224">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="35a57-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="35a57-225">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="35a57-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="35a57-226">**메시지를 배달 하 고 숨은 참조 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="35a57-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="35a57-227">**메시지를 배달 하기 전에 삭제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="35a57-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="35a57-228">**가장 안전 팁 사용** 을 클릭 하 고 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="35a57-229">**가장 된 사용자에 대 한 팁 표시** : 기본값은 **Off** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-229">**Show tip for impersonated users** : The default value is **Off**.</span></span> <span data-ttu-id="35a57-230">설정 하려면 **슬라이드를 설정 합니다 .로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="35a57-231">**가장 된 도메인에 대 한 팁 표시** : 기본값은 **Off** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-231">**Show tip for impersonated domains** : The default value is **Off**.</span></span> <span data-ttu-id="35a57-232">설정 하려면 **슬라이드를 설정 합니다 .로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="35a57-233">**비정상적인 캐릭터에 대 한 팁 표시** : 기본값은 **Off** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-233">**Show tip for unusual characters** : The default value is **Off**.</span></span> <span data-ttu-id="35a57-234">설정 하려면 **슬라이드를 설정 합니다 .로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-234">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="35a57-235">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-235">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="35a57-236">**사서함 인텔리전스** :</span><span class="sxs-lookup"><span data-stu-id="35a57-236">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="35a57-237">**사서함 인텔리전스 사용 여부** : 기본값은 **On** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-237">**Enable mailbox intelligence?** : The default value is **On**.</span></span> <span data-ttu-id="35a57-238">해제 하려면 **토글을 끕니다.**</span><span class="sxs-lookup"><span data-stu-id="35a57-238">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="35a57-239">**Mailbox intelligence 기반 가장 보호 사용?** :이 설정은 **사서함 인텔리전스 사용** 이 설정 되어 있는 경우 **에** 만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-239">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="35a57-240">에서 **가장 된 사용자가 전자 메일을 보낸 경우** 에는 다음 작업 중 하나를 지정 하 여 사서함 인텔리전스 오류가 발생 한 메시지 (보호 되는 사용자와 보호 된 도메인에 사용할 수 있는 것과 동일한 작업)에 대해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-240">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="35a57-241">**작업 적용 안 함**</span><span class="sxs-lookup"><span data-stu-id="35a57-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="35a57-242">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="35a57-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="35a57-243">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="35a57-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="35a57-244">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="35a57-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="35a57-245">**메시지를 배달 하 고 숨은 참조 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="35a57-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="35a57-246">**메시지를 배달 하기 전에 삭제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="35a57-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="35a57-247">**신뢰할 수 있는 보낸 사람 및 도메인 추가** : 정책에 대 한 예외를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-247">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="35a57-248">**신뢰할 수 있는 보낸 사람** :</span><span class="sxs-lookup"><span data-stu-id="35a57-248">**Trusted senders** :</span></span>

       - <span data-ttu-id="35a57-249">상자를 클릭 하 고 선택할 사용자 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="35a57-250">상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="35a57-251">항목을 제거 하려면 **Remove** ![ 사용자에 대해 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="35a57-252">**신뢰할 수 있는 도메인** : contoso.com와 같은 도메인 이름을 입력 하 고 enter 키를 누른 다음 필요에 따라 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-252">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="35a57-253">**설정 검토** : 각 개별 단계를 클릭 하지 않고 설정이 요약으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-253">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="35a57-254">각 섹션에서 **편집** 을 클릭 하 여 관련 페이지로 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="35a57-255">이 **페이지에서 다음** 설정을 직접 설정 하거나 **해제할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="35a57-256">**보호 된 사용자**</span><span class="sxs-lookup"><span data-stu-id="35a57-256">**Protected users**</span></span>
       - <span data-ttu-id="35a57-257">**보호 된 도메인** \> **소유한 도메인 포함**</span><span class="sxs-lookup"><span data-stu-id="35a57-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="35a57-258">**보호 된 도메인** \> **보호 된 도메인** (사용자 지정 도메인)</span><span class="sxs-lookup"><span data-stu-id="35a57-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="35a57-259">**사서함 인텔리전스**</span><span class="sxs-lookup"><span data-stu-id="35a57-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="35a57-260">작업이 끝나면 모든 페이지에서 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="35a57-261">**스푸핑** : **편집** 을 클릭 하 여 스푸핑 인텔리전스를 설정 하거나 해제 하 고, Outlook에서 인증 되지 않은 보낸 사람 id를 설정/해제 하 고, 차단 된 스푸핑된 보낸 사람 으로부터 메시지에 적용할 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-261">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="35a57-262">자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md#spoof-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="35a57-263">이러한 동일한 설정은 EOP의 피싱 방지 정책 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="35a57-264">**스푸핑 필터 설정** : 기본값은 **on** 이며,이 값을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-264">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="35a57-265">해제 하려면 **토글을 끕니다.**</span><span class="sxs-lookup"><span data-stu-id="35a57-265">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="35a57-266">자세한 내용은 [Configure 스푸핑이 intelligence IN EOP](learn-about-spoof-intelligence.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="35a57-267">MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용 하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대 한 향상 된 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="35a57-268">자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="35a57-269">**인증 되지 않은 보낸 사람 기능 사용** : 기본값은 **On** 입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-269">**Enable Unauthenticated Sender feature** : The default value is **On**.</span></span> <span data-ttu-id="35a57-270">해제 하려면 **토글을 끕니다.**</span><span class="sxs-lookup"><span data-stu-id="35a57-270">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="35a57-271">**작업** : 스푸핑 인텔리전스에 실패 한 메시지에 대해 수행할 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-271">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="35a57-272">**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우** :</span><span class="sxs-lookup"><span data-stu-id="35a57-272">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="35a57-273">**받는 사람의 정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="35a57-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="35a57-274">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="35a57-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="35a57-275">**설정 검토** : 각 개별 단계를 클릭 하지 않고 설정이 요약으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-275">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="35a57-276">각 섹션에서 **편집** 을 클릭 하 여 관련 페이지로 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="35a57-277">이 **페이지에서 다음** 설정을 직접 설정 하거나 **해제할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="35a57-278">**스푸핑 방지 보호 사용**</span><span class="sxs-lookup"><span data-stu-id="35a57-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="35a57-279">**인증 되지 않은 보낸 사람 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="35a57-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="35a57-280">작업이 끝나면 모든 페이지에서 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="35a57-281">**고급 설정** : 고급 피싱 임계값을 구성 하려면 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-281">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="35a57-282">자세한 내용은 [Microsoft Defender For Office 365의 피싱 방지 정책에서 Advanced 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-282">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="35a57-283">**고급 피싱 임계값** : 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-283">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="35a57-284">**1-표준** (이 값은 기본값입니다.)</span><span class="sxs-lookup"><span data-stu-id="35a57-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="35a57-285">**2-적극적인**</span><span class="sxs-lookup"><span data-stu-id="35a57-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="35a57-286">**3-적극적인**</span><span class="sxs-lookup"><span data-stu-id="35a57-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="35a57-287">**4-최대 적극적인**</span><span class="sxs-lookup"><span data-stu-id="35a57-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="35a57-288">**설정 검토** : **편집** 을 클릭 하 여 **고급 피싱 임계값** 페이지로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-288">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="35a57-289">작업이 끝나면 두 페이지 중 하나에서 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="35a57-290">**\<Name\> 정책 편집** 페이지에서 설정을 검토 하 고 **닫기를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-291">보안 & 준수 센터를 사용 하 여 Microsoft Defender for Office 365의 기본 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35a57-291">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="35a57-292">Microsoft Defender for Office 365의 기본 피싱 방지 정책은 Office365 AntiPhish Default로 명명 되며 정책 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-292">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="35a57-293">기본 피싱 방지 정책을 수정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-293">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="35a57-294">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35a57-295">**피싱 방지** 페이지에서 **기본 정책을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-295">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="35a57-296">**정책 편집 Office365 AntiPhish 기본값** 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="35a57-297">다음 섹션에서는 [사용자 지정 정책을 수정할](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)때의 설정이 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="35a57-298">**가장**</span><span class="sxs-lookup"><span data-stu-id="35a57-298">**Impersonation**</span></span>
   - <span data-ttu-id="35a57-299">**신분을**</span><span class="sxs-lookup"><span data-stu-id="35a57-299">**Spoof**</span></span>
   - <span data-ttu-id="35a57-300">**고급 설정**</span><span class="sxs-lookup"><span data-stu-id="35a57-300">**Advanced settings**</span></span>

   <span data-ttu-id="35a57-301">기본 정책을 수정 하는 경우에는 다음 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="35a57-302">**정책 설정** 섹션 및 값을 볼 수는 있지만 **편집** 링크는 없는 경우에는 설정 (정책 이름, 설명 및 정책을 적용 하는 사람 (모든 받는 사람에 게 적용)을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="35a57-303">기본 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="35a57-304">기본 정책의 우선 순위를 변경할 수는 없습니다 (항상 마지막으로 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="35a57-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="35a57-305">**Policy Office365 AntiPhish 기본값 편집** 페이지에서 설정을 검토 하 고 **닫기를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-306">Microsoft Defender for Office 365에서 사용자 지정 피싱 방지 정책 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="35a57-306">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="35a57-307">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35a57-308">**상태** 열에서 다음 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="35a57-309">정책을 사용 하지 않도록 설정 하려면이 설정을 **해제** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="35a57-310">정책을 **사용 하려면 토글을 설정으로 이동** 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="35a57-311">기본 피싱 방지 정책을 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-312">Microsoft Defender for Office 365에서 사용자 지정 피싱 방지 정책의 우선 순위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-312">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="35a57-313">기본적으로 피싱 방지 정책에는 만든 순서를 기준으로 하는 우선 순위가 지정 됩니다 (최신 정책은 이전 정책 보다 낮은 우선 순위입니다).</span><span class="sxs-lookup"><span data-stu-id="35a57-313">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="35a57-314">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="35a57-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="35a57-315">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="35a57-316">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35a57-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="35a57-317">사용자 지정 피싱 방지 정책은 처리 되는 순서 대로 표시 됩니다 (첫 번째 정책의 **우선 순위** 값은 0).</span><span class="sxs-lookup"><span data-stu-id="35a57-317">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="35a57-318">Office365 AntiPhish Default 라는 기본 피싱 방지 정책은 사용자 지정 우선 순위 값이 **가장 낮은** 반면,이를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="35a57-319">**참고** : 보안 & 준수 센터에서는 피싱 방지 정책의 우선 순위를 만든 후에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-319">**Note** : In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="35a57-320">PowerShell에서는 기존 규칙의 우선 순위에 영향을 줄 수 있는 피싱 규칙을 만들 때 기본 우선 순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="35a57-321">정책의 우선 순위를 변경 하려면 정책의 속성에서 우선 **순위 높임** 또는 **우선 순위 낮추기** (보안 & 준수 센터에서 직접 **우선 순위** 번호를 수정할 수 없음)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="35a57-322">정책 우선 순위를 변경 하는 것은 정책이 여러 개인 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="35a57-323">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35a57-324">수정 하려는 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="35a57-325">이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="35a57-326">정책 플라이 아웃 **\<name\> 편집** 이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="35a57-327">**우선 순위** 값이 **0** 인 사용자 지정 피싱 방지 정책에는 **우선 순위 낮추기** 단추만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-327">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="35a57-328">**우선 순위** 값이 가장 낮은 사용자 지정 피싱 방지 정책 (예: **3** )에는 **우선 순위 향상** 단추만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-328">The custom anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="35a57-329">사용자 지정 피싱 방지 정책이 3 개 이상 있는 경우 가장 높거나 낮은 우선 순위 값 사이의 정책에는 **우선 순위 증가** 와 **우선 순위 낮추기** 단추가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="35a57-330">우선 **순위 높임** 또는 **우선 순위 낮추기** 를 클릭 하 여 **우선 순위** 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="35a57-331">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-331">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-332">보안 & 준수 센터를 사용 하 여 Microsoft Defender for Office 365의 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="35a57-332">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="35a57-333">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35a57-334">다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="35a57-335">보려는 사용자 지정 피싱 방지 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-335">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="35a57-336">이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="35a57-337">기본 **정책을** 클릭 하 여 기본 피싱 방지 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="35a57-338">설정 및 값을 볼 수 있는 **정책 \<name\>** 플라이 아웃 편집이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-339">보안 & 준수 센터를 사용 하 여 Microsoft Defender for Office 365에서 피싱 방지 정책 제거</span><span class="sxs-lookup"><span data-stu-id="35a57-339">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="35a57-340">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="35a57-341">제거할 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="35a57-342">이미 선택 되어 있으면 선택을 취소 하 고 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="35a57-343">표시 되는 **정책 \<name\>** 플라이 아웃 편집에서 **정책 삭제** 를 클릭 한 다음 표시 되는 경고 대화 상자에서 **예** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="35a57-344">기본 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="35a57-345">Exchange Online PowerShell을 사용 하 여 Microsoft Defender for Office 365에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="35a57-345">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="35a57-346">앞에서 설명한 것 처럼 스팸 방지 정책은 피싱 정책 및 피싱 규칙으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-346">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="35a57-347">Exchange Online PowerShell에서 피싱 정책 및 피싱 규칙 간의 차이가 명백 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="35a57-348">**\* -AntiPhishPolicy** cmdlet을 사용 하 여 피싱 정책을 관리 하 고 **\* -AntiPhishRule** cmdlet을 사용 하 여 피싱 규칙을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="35a57-349">PowerShell에서는 먼저 피싱 정책을 만든 다음 규칙이 적용 되는 정책을 식별 하는 피싱 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="35a57-350">PowerShell에서는 피싱 정책의 설정과 피싱 규칙을 각각 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="35a57-351">PowerShell에서 피싱 정책을 제거 하면 해당 하는 피싱 규칙이 자동으로 제거 되지 않고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="35a57-352">PowerShell을 사용 하 여 피싱 방지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="35a57-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="35a57-353">PowerShell에서 피싱 방지 정책을 만드는 과정은 다음 두 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="35a57-354">피싱 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="35a57-355">규칙이 적용 되는 피싱 정책을 지정 하는 피싱 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="35a57-356">**참고** :</span><span class="sxs-lookup"><span data-stu-id="35a57-356">**Notes** :</span></span>

- <span data-ttu-id="35a57-357">새 피싱 규칙을 만들고 연결 되지 않은 기존 피싱 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="35a57-358">피싱 규칙을 두 개 이상의 피싱 정책에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="35a57-359">정책을 만든 후에 야 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 피싱 정책에서 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="35a57-360">AntiPhishRule cmdlet에서 _사용 하도록 설정_ 된 새 정책을 사용 하지 않도록 설정 `$false` **New-AntiPhishRule** 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-360">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="35a57-361">AntiPhishRule cmdlet에 대 한 생성 ( _우선 순위_ ) 중에 정책의 우선 순위를 설정 _\<Number\>_ 합니다. **New-AntiPhishRule**</span><span class="sxs-lookup"><span data-stu-id="35a57-361">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="35a57-362">피싱 규칙에 정책을 할당 하기 전 까지는 PowerShell에서 만드는 새로운 피싱 정책이 보안 & 준수 센터에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="35a57-363">1 단계: PowerShell을 사용 하 여 피싱 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="35a57-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="35a57-364">피싱 정책을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="35a57-365">이 예에서는 다음 설정을 사용 하 여 Research Quarantine 라는 피싱 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="35a57-366">정책이 사용 하도록 설정 되어 있습니다 ( _enabled_ 매개 변수를 사용 하지 않으며 기본값은 `$true` ).</span><span class="sxs-lookup"><span data-stu-id="35a57-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="35a57-367">설명은 부서 정책 연구입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="35a57-368">모든 허용 도메인에 대해 조직 도메인을 보호 하 고 fabrikam.com에 대해 대상 도메인 보호를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="35a57-369">가장을 보호할 사용자에 게 Mai Fujito (mfujito@fabrikam.com)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="35a57-370">사서함 인텔리전스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="35a57-371">사서함 인텔리전스 보호를 사용 하도록 설정 하 고 격리 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="35a57-372">안전 팁을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="35a57-373">구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="35a57-374">2 단계: PowerShell을 사용 하 여 피싱 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="35a57-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="35a57-375">피싱 규칙을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="35a57-376">이 예에서는 다음 조건을 사용 하 여 Research 학과 라는 피싱 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="35a57-377">이 규칙은 조사 검역 이라는 피싱 정책에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="35a57-378">이 규칙은 Research Department 그룹의 구성원에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="35a57-379">_Priority_ 매개 변수를 사용 하지 않으므로 기본 우선 순위가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="35a57-380">구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="35a57-381">PowerShell을 사용 하 여 피싱 정책 보기</span><span class="sxs-lookup"><span data-stu-id="35a57-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="35a57-382">기존 피싱 정책을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="35a57-383">이 예제에서는 지정 된 속성과 함께 모든 피싱 정책의 요약 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="35a57-384">이 예제에서는 중역 이라는 피싱 정책에 대 한 모든 속성 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="35a57-385">구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="35a57-386">PowerShell을 사용 하 여 피싱 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="35a57-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="35a57-387">기존 피싱 규칙을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="35a57-388">이 예제에서는 지정 된 속성과 함께 모든 피싱 규칙의 요약 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="35a57-389">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="35a57-390">이 예에서는 Contoso 임원 이라는 피싱 규칙에 대 한 모든 속성 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="35a57-391">구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="35a57-392">PowerShell을 사용 하 여 피싱 정책 수정</span><span class="sxs-lookup"><span data-stu-id="35a57-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="35a57-393">다음 항목을 제외 하 고는이 항목 앞부분에 있는 [1 단계: powershell을 사용 하 여 피싱 정책 만들기](#step-1-use-powershell-to-create-an-anti-phish-policy) 섹션에 설명 된 대로, powershell을 만들 때 피싱 정책을 수정할 때도 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="35a57-394">지정 된 정책을 기본 정책으로 설정 하는 _makedefault_ 스위치 (모든 사용자에 게 적용 되며 항상 **가장 낮은** 우선 순위 이며 삭제할 수 없음)는 PowerShell에서 피싱 정책을 수정 하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="35a57-395">피싱 정책의 이름을 바꿀 수는 없습니다 (AntiPhishPolicy cmdlet은 _Name_ 매개 변수를 **사용** 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="35a57-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="35a57-396">보안 & 준수 센터에서 피싱 방지 정책의 이름을 바꾸면 피싱 _규칙_ 의 이름도 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="35a57-397">피싱 정책을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="35a57-398">구문 및 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="35a57-399">PowerShell을 사용 하 여 피싱 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="35a57-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="35a57-400">PowerShell에서 피싱 규칙을 수정할 때 사용할 수 없는 설정은 사용 하지 않도록 설정 된 규칙을 만들 수 있는 _사용_ 가능한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="35a57-401">기존 피싱 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="35a57-402">그렇지 않으면 PowerShell에서 피싱 규칙을 수정할 때 추가 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="35a57-403">이 항목 앞부분에 있는 [2 단계: PowerShell을 사용 하 여 피싱 규칙 만들기](#step-2-use-powershell-to-create-an-anti-phish-rule) 섹션에 설명 된 대로 규칙을 만들 때도 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="35a57-404">피싱 규칙을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="35a57-405">구문 및 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="35a57-406">PowerShell을 사용 하 여 피싱 규칙을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="35a57-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="35a57-407">PowerShell에서 피싱 규칙을 사용 하거나 사용 하지 않도록 설정 하면 전체 피싱 방지 정책 (피싱 규칙 및 할당 된 피싱 정책)을 사용 하거나 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="35a57-408">기본 피싱 방지 정책을 사용 하거나 사용 하지 않도록 설정할 수는 없습니다 (항상 모든 받는 사람에 게 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="35a57-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="35a57-409">PowerShell에서 피싱 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="35a57-410">이 예에서는 Marketing 부서 라는 피싱 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="35a57-411">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="35a57-412">구문 및 매개 변수에 대 한 자세한 내용은 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 및 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="35a57-413">PowerShell을 사용 하 여 피싱 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="35a57-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="35a57-414">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="35a57-415">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="35a57-416">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="35a57-417">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="35a57-418">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="35a57-419">PowerShell에서 피싱 규칙의 우선 순위를 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="35a57-420">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-420">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="35a57-421">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="35a57-421">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="35a57-422">**참고:**</span><span class="sxs-lookup"><span data-stu-id="35a57-422">**Notes** :</span></span>

- <span data-ttu-id="35a57-423">새 규칙을 만들 때 우선 순위를 설정 하려면 대신 **AntiPhishRule** Cmdlet에서 _priority_ 매개 변수를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="35a57-424">기본 피싱 정책에는 해당 하는 피싱 규칙이 없으며 항상 **가장 낮은** 우선 순위 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="35a57-425">PowerShell을 사용 하 여 피싱 정책 제거</span><span class="sxs-lookup"><span data-stu-id="35a57-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="35a57-426">PowerShell을 사용 하 여 피싱 정책을 제거 하면 해당 하는 피싱 규칙이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="35a57-427">PowerShell에서 피싱 정책을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="35a57-428">이 예에서는 Marketing 학과 라는 피싱 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="35a57-429">구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="35a57-430">PowerShell을 사용 하 여 피싱 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="35a57-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="35a57-431">PowerShell을 사용 하 여 피싱 규칙을 제거 하면 해당 하는 피싱 정책이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="35a57-432">PowerShell에서 피싱 규칙을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="35a57-433">이 예에서는 Marketing 학과 라는 피싱 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="35a57-434">구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35a57-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="35a57-435">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="35a57-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="35a57-436">Microsoft Defender for Office 365에서 피싱 방지 정책을 성공적으로 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-436">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="35a57-437">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="35a57-438">정책 목록, 해당 **상태** 값 및 해당 **우선 순위** 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="35a57-439">자세한 정보를 보려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="35a57-440">목록에서 정책을 선택 하 고 플라이 아웃의 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="35a57-441">**기본 정책을** 클릭 하 고 플라이 아웃에서 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="35a57-442">Exchange Online PowerShell에서 \<Name\> 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행 하 고 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a57-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
