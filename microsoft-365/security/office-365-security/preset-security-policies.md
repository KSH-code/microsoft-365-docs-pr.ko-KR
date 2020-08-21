---
title: 보안 정책 미리조정
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
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365 ATP(Advanced Threat Protection)의 보호 기능에서 표준 및 고급 정책 설정을 적용하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: a2f0472d8dd44c90fd5db14e71d2db0d5d323b50
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825260"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="b85d5-103">EOP 및 Office 365 ATP의 미리 설정된 보안 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-103">Preset security policies in EOP and Office 365 ATP</span></span>

<span data-ttu-id="b85d5-104">미리 설정된 보안 정책을 사용하면 권장되는 모든 스팸, 맬웨어 및 피싱 정책을 사용자에게 한 번에 적용할 수 있는 중앙 위치가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="b85d5-105">정책 설정은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-105">The policy settings are not configurable.</span></span> <span data-ttu-id="b85d5-106">대신 Microsoft에서 지원하며, 작업을 지장하지 않으면서 사용자로부터 유해한 콘텐츠를 유지할 수 있도록 데이터 센터의 관찰 및 환경을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="b85d5-107">이 항목의 나머지 부분에서는 미리 설정된 보안 정책 및 이러한 정책을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="b85d5-108">미리 설정된 보안 정책의 개시</span><span class="sxs-lookup"><span data-stu-id="b85d5-108">What preset security policies are made of</span></span>

<span data-ttu-id="b85d5-109">미리 설정된 보안 정책은 다음 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="b85d5-110">프로필</span><span class="sxs-lookup"><span data-stu-id="b85d5-110">Profiles</span></span>
- <span data-ttu-id="b85d5-111">정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-111">Policies</span></span>
- <span data-ttu-id="b85d5-112">정책 설정</span><span class="sxs-lookup"><span data-stu-id="b85d5-112">Policy settings</span></span>

<span data-ttu-id="b85d5-113">또한 동일한 사용자에 여러 개의 미리 설정된 보안 정책 및 기타 정책이 적용된 경우 우선 순위가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="b85d5-114">미리 설정된 보안 정책의 프로필</span><span class="sxs-lookup"><span data-stu-id="b85d5-114">Profiles in preset security policies</span></span>

<span data-ttu-id="b85d5-115">프로필은 보호 수준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-115">A profile determines the level of protection.</span></span> <span data-ttu-id="b85d5-116">사용할 수 있는 프로필은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-116">The following profiles are available:</span></span>

- <span data-ttu-id="b85d5-117">**표준 보호:** 대부분의 사용자에게 적합한 기준 보호 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="b85d5-118">**고급 보호**: 선택한 사용자를 위한 더 욱적극적인 보호 프로필(가치가 높은 대상 또는 우선 순위 사용자).</span><span class="sxs-lookup"><span data-stu-id="b85d5-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="b85d5-119">프로필이 적용되거나 적용되지 않는 사람을 확인하는 조건 및 예외와 함께 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="b85d5-120">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b85d5-121">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="b85d5-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b85d5-122">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b85d5-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="b85d5-123">사용 가능한 조건 및 예외는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="b85d5-124">**받는 사람은 조직의**사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="b85d5-125">**받는 사람이 조직의 구성원:** 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="b85d5-126">**받는 사람 도메인은**Microsoft 365에서 구성된 허용 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="b85d5-127">미리 설정된 보안 정책의 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-127">Policies in preset security policies</span></span>

<span data-ttu-id="b85d5-128">미리 설정된 보안 정책은 EOP 및 Office 365 ATP의 다양한 보호 기능에서 제공하는 해당 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-128">Preset security policies use the corresponding policies from the various protection features in EOP and Office 365 ATP.</span></span> <span data-ttu-id="b85d5-129">이러한 정책은 표준 _보호 또는_ **[Strict Protection)** **보호 정책을 사용자에게 할당한** 후 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="b85d5-130">이러한 정책은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-130">You can't modify these policies.</span></span>

- <span data-ttu-id="b85d5-131">**EOP(Exchange Online Protection) 정책**: Exchange Online 사서함과 함께 Microsoft 365 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="b85d5-132">[표준 미리 설정된 보안](configure-your-spam-filter-policies.md) **정책 및 Strict** 미리 **설정된 보안 정책이라는 스팸 방지 정책.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="b85d5-133">[표준 사전 보안 정책](configure-anti-malware-policies.md) **및 Strict 미리 설정된 보안** **정책이라고 하는 맬웨어 방지 정책.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="b85d5-134">[표준 사전 설정 보안 정책 및](set-up-anti-phishing-policies.md#spoof-settings) **Strict** **미리** 설정된 보안 정책(스푸핑 설정)이라고 하는 EOP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="b85d5-135">**Office 365 ADVANCED Threat Protection(ATP) 정책:** 여기에는 Microsoft 365 E5 또는 Office 365 ATP 추가 기능 구독을 사용하는 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-135">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="b85d5-136">다음을 포함하는 표준 사전 설정된 보안 정책 **및** **Strict 미리**설정 보안 정책이라고 하는 ATP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-136">ATP anti-phishing policies named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="b85d5-137">[EOP피싱 방지 정책에서](set-up-anti-phishing-policies.md#spoof-settings) 사용할 수 있는 것과 동일한 스푸핑 설정</span><span class="sxs-lookup"><span data-stu-id="b85d5-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="b85d5-138">가장 설정</span><span class="sxs-lookup"><span data-stu-id="b85d5-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="b85d5-139">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="b85d5-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="b85d5-140">[표준 사전 설정 보안](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) 정책 및 **Strict 미리 설정된 보안 정책이라고 하는 안전 링크**정책. **Standard Preset Security Policy**</span><span class="sxs-lookup"><span data-stu-id="b85d5-140">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="b85d5-141">[표준 미리 설정된 보안](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) 정책 및 **Strict 미리 설정된 보안 정책이라고 하는 안전 첨부 파일**정책. **Standard Preset Security Policy**</span><span class="sxs-lookup"><span data-stu-id="b85d5-141">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="b85d5-142">EOP 보호와는 다른 사용자에게 EOP 보호를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-142">Note that you can apply EOP protections to different users than ATP protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="b85d5-143">미리 설정된 보안 정책의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b85d5-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="b85d5-144">보호 프로필의 정책 설정은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="b85d5-145">EOP **및** Office 365 ATP 보안에 대한 권장 설정에서는 표준 및 **Strict** [정책 설정에 대한 값이 설명되어 있습니다.](recommended-settings-for-eop-and-office365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="b85d5-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="b85d5-146">미리 설정된 보안 정책 및 기타 정책의 우선 순위</span><span class="sxs-lookup"><span data-stu-id="b85d5-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="b85d5-147">여러 정책이 사용자에게 적용된 경우 다음 순서가 가장 높은 우선 순위부터 최하위 우선 순위로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="b85d5-148">**Strict Protection** 미리 설정된 보안 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="b85d5-149">**표준 보호** 미리 설정된 보안 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="b85d5-150">사용자 지정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-150">Custom security policies</span></span>
4. <span data-ttu-id="b85d5-151">기본 보안 정책</span><span class="sxs-lookup"><span data-stu-id="b85d5-151">Default security policies</span></span>

<span data-ttu-id="b85d5-152">즉, [보안 보호 정책" **설정은 표준** 보호 정책의 설정을 재정의하는 **표준** 보호 정책의 설정을 재정의합니다. 이 정책의 설정은 사용자 지정 정책의 설정을 무시합니다. 이 경우 기본 정책의 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="b85d5-153">사용자에게 미리 설정된 보안 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b85d5-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b85d5-154">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="b85d5-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b85d5-155"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b85d5-156">미리 설정된 보안 정책 **페이지로 직접 이동하려면 다음을** 사용합니다. <https://protection.office.com/presetSecurityPolicies></span><span class="sxs-lookup"><span data-stu-id="b85d5-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="b85d5-157">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b85d5-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b85d5-158">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-158">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="b85d5-159">미리 설정된 보안 정책을 구성하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-159">To configure preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b85d5-160">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="b85d5-160">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b85d5-161">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="b85d5-161">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="b85d5-162">미리 설정된 보안 정책에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-162">For read-only access to preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b85d5-163">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="b85d5-163">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b85d5-164">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="b85d5-164">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="b85d5-165">보안 그룹 & 준수 센터를 사용하여 미리 설정된 보안 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b85d5-165">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="b85d5-166">보안 전부 & 보안 센터에서 위협 관리 **정책 미리** \> **설정된 보안** \> **정책으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="b85d5-167">Standard **Protection 또는** **Strict Protection에서 편집을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-167">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="b85d5-168">표준 **보호 적용 또는** **[관리 보호 적용) 마법사가** 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-168">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="b85d5-169">EOP **보호가 단계에 적용되는 단계에는** EOP 보호가 적용되는 내부 [받는 사람을](#policies-in-preset-security-policies) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-169">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="b85d5-170">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-170">Click **Add a condition**.</span></span> <span data-ttu-id="b85d5-171">표시되는 드롭다운 메뉴에서 다음과 같은 경우 적용된 **조건을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-171">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="b85d5-172">**받는 사람이 다음과 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-172">**The recipients are**</span></span>
      - <span data-ttu-id="b85d5-173">**받는 사람이 다음의 구성원인 경우**</span><span class="sxs-lookup"><span data-stu-id="b85d5-173">**The recipients are members of**</span></span>
      - <span data-ttu-id="b85d5-174">**받는 사람 도메인이 다음과 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-174">**The recipient domains are**</span></span>

      <span data-ttu-id="b85d5-175">조건은 한 번만 사용할 수 있지만 조건에는 여러 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-175">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="b85d5-176">동일한 조건의 여러 값은 OR 논리(예: or)를 _\<recipient1\>_ _\<recipient2\>_ 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-176">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="b85d5-177">선택한 조건이 음중 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-177">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="b85d5-178">이 섹션에서 다음 **상자를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-178">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="b85d5-179">잠시 기다리면 값을 선택할 수 있도록 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-179">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="b85d5-180">또는 값을 입력하여 목록을 필터링하고 값을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-180">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="b85d5-181">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="b85d5-182">개별 값을 제거하려면 값에서 **제거** ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-182">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="b85d5-183">전체 조건을 제거하려면 해당 **조건에서** ![ 제거 아이콘 ](../../media/scc-remove-icon.png) 제거아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-183">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="b85d5-184">다른 조건을 추가하려면 **조건 추가를** 클릭하고 나머지 조건에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-184">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="b85d5-185">다른 조건에는 AND 논리(예: 및)가 _\<recipient1\>_ _\<member of group 1\>_ 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-185">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="b85d5-186">위 단계를 반복하여 조건에 값을 추가한 다음 필요한 만큼 또는 조건이 부과할 때까지 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-186">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="b85d5-187">예외를 추가하려면 조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-187">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="b85d5-188">표시되는 드롭다운에서 \*\* 제외\*\* 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-188">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="b85d5-189">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-189">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b85d5-190">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b85d5-191">조직에 Office 365 ATP가 있는 [경우, Office 365](#policies-in-preset-security-policies) **ATP 보호가** 적용되는 내부 받는 사람을 식별하기 위해 ATP 보호 조치가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-191">If your organization has Office 365 ATP, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Office 365 ATP protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="b85d5-192">설정 및 동작은 EOP 보호 단계와 **정확히 동일합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-192">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="b85d5-193">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b85d5-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b85d5-194">확인 **단계에서** 선택 사항을 확인하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-194">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="b85d5-195">보안 서비스 & 센터를 사용하여 미리 설정된 보안 정책 할당 수정</span><span class="sxs-lookup"><span data-stu-id="b85d5-195">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="b85d5-196">표준 보호 또는 **Strict** **Protection** 보안 정책 할당을 수정하는 단계는 처음에 미리 설정된 보안 [정책을 사용자에게 할당한 단계와 동일합니다.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)</span><span class="sxs-lookup"><span data-stu-id="b85d5-196">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="b85d5-197">기존 조건 **및 예외를** **유지하면서 표준** 보호 또는 고급 보호 보안 정책을 사용하지 않도록 설정하려면 토글을 사용 안 함으로 **밀어 넣습니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-197">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="b85d5-198">정책을 사용하려면 토글을 사용으로 **밀어 서는 방법을 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-198">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b85d5-199">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="b85d5-199">How do you know these procedures worked?</span></span>

<span data-ttu-id="b85d5-200">표준 보호 또는 **Strict** 보호 보안 정책을 사용자에게 성공적으로 할당되었는지 확인하려면 기본값이 표준 보호 설정과 다른 보호 **Standard protection** 설정([Strict **Protection)** 설정과는 다른 **보호 설정을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-200">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="b85d5-201">예를 들어 스팸(높은 신뢰도의 스팸이 아님)으로 검색된 전자 메일의 경우 해당 메시지가 **표준** 보호 사용자의 정크 메일 폴더에 배달되고, **Strict Protection 사용자를 위해 격리되는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-201">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="b85d5-202">또는 [대량 전자 메일의](bulk-complaint-level-values.md)경우, BCL 값이 6 이상인 표준 보호 사용자를 위해 **Standard protection** 메시지를 정크 메일 폴더에 배달하고, BCL 값 4 이상이 **Strict Protection 사용자에 대한 메시지를 격리하는지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="b85d5-202">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
