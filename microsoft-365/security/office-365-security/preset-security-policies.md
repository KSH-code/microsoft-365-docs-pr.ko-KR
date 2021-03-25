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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365용 Microsoft Defender의 보호 기능에 표준 및 엄격한 정책 설정을 적용하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7579b2d2a47135ab9628d2ec8990f53c3917514b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205805"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="99e69-103">EOP 및 Office 365용 Microsoft Defender에서 보안 정책 미리 설정</span><span class="sxs-lookup"><span data-stu-id="99e69-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="99e69-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="99e69-104">**Applies to**</span></span>
- [<span data-ttu-id="99e69-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="99e69-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="99e69-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="99e69-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="99e69-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99e69-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="99e69-108">미리 설정한 보안 정책은 권장되는 모든 스팸, 맬웨어 및 피싱 정책을 한에 적용할 수 있는 중앙 집중식 위치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="99e69-109">정책 설정은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-109">The policy settings are not configurable.</span></span> <span data-ttu-id="99e69-110">대신, 사용자가 작업을 중단하지 않고 유해한 콘텐츠를 사용자에게 노출하지 못하게 하는 균형을 위해 데이터 센터의 관찰 및 환경을 기반으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="99e69-111">이 항목의 나머지 항목에서는 미리 설정한 보안 정책과 이를 구성하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-111">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="99e69-112">미리 설정한 보안 정책의 적용</span><span class="sxs-lookup"><span data-stu-id="99e69-112">What preset security policies are made of</span></span>

<span data-ttu-id="99e69-113">미리 설정한 보안 정책은 다음 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="99e69-114">프로필</span><span class="sxs-lookup"><span data-stu-id="99e69-114">Profiles</span></span>
- <span data-ttu-id="99e69-115">정책</span><span class="sxs-lookup"><span data-stu-id="99e69-115">Policies</span></span>
- <span data-ttu-id="99e69-116">정책 설정</span><span class="sxs-lookup"><span data-stu-id="99e69-116">Policy settings</span></span>

<span data-ttu-id="99e69-117">또한 미리 설정한 여러 보안 정책 및 기타 정책이 동일한 사용자에 적용되는 경우 우선 순위가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="99e69-118">미리 설정한 보안 정책의 프로필</span><span class="sxs-lookup"><span data-stu-id="99e69-118">Profiles in preset security policies</span></span>

<span data-ttu-id="99e69-119">프로필에 따라 보호 수준이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-119">A profile determines the level of protection.</span></span> <span data-ttu-id="99e69-120">다음 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-120">The following profiles are available:</span></span>

- <span data-ttu-id="99e69-121">**표준 보호:** 대부분의 사용자에게 적합한 기준 보호 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="99e69-122">**엄격한 보호:** 선택한 사용자(높은 가치의 대상 또는 우선 순위 사용자)에 대한 보다 적극적인 보호 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="99e69-123">조건 및 예외와 함께 프로필이 누구인지 또는 적용되지 않는지 결정하는 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="99e69-124">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-124">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="99e69-125">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="99e69-125">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="99e69-126">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="99e69-126">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="99e69-127">사용 가능한 조건 및 예외는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-127">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="99e69-128">**받는 사람은 조직의** 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-128">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="99e69-129">**받는 사람은 조직의**: 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-129">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="99e69-130">**받는 사람 도메인은**: Microsoft 365에서 구성된 허용 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-130">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="99e69-131">미리 설정한 보안 정책의 정책</span><span class="sxs-lookup"><span data-stu-id="99e69-131">Policies in preset security policies</span></span>

<span data-ttu-id="99e69-132">미리 설정한 보안 정책은 EOP 및 Office 365용 Microsoft Defender의 다양한 보호 기능에서 해당 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="99e69-133">이러한 정책은 **Standard** _보호_ 또는 **엄격한** 보호 미리 설정 보안 정책을 사용자에게 할당한 후에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="99e69-134">이러한 정책은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-134">You can't modify these policies.</span></span>

- <span data-ttu-id="99e69-135">**EOP(Exchange Online Protection)** 정책: Exchange Online 사서함이 있는 Microsoft 365 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="99e69-136">[Standard 미리](configure-your-spam-filter-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 스팸 **방지 정책**</span><span class="sxs-lookup"><span data-stu-id="99e69-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="99e69-137">[Standard 미리](configure-anti-malware-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 맬웨어 **방지 정책**</span><span class="sxs-lookup"><span data-stu-id="99e69-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="99e69-138">표준 미리 설정 보안 정책  및 엄격한 미리  설정 보안 정책(스푸핑 설정)이라는 [EOP](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="99e69-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="99e69-139">**Microsoft Defender for Office 365 정책:** 여기에는 Microsoft 365 E5 또는 Office 365용 Defender 추가 기능 구독이 있는 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="99e69-140">Standard Preset Security Policy 및 Strict **Preset Security Policy라는** Microsoft Defender for Office 365의 피싱 방지 정책에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="99e69-141">EOP [](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책에서 사용할 수 있는 동일한 스푸핑 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="99e69-142">가장 설정</span><span class="sxs-lookup"><span data-stu-id="99e69-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="99e69-143">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="99e69-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="99e69-144">[표준 미리 설정](set-up-safe-links-policies.md) 보안 정책 및 엄격한 미리 **설정** 보안 정책 **이라는** 안전 링크 정책</span><span class="sxs-lookup"><span data-stu-id="99e69-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="99e69-145">[표준 미리](set-up-safe-attachments-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 안전 첨부 **파일 정책**</span><span class="sxs-lookup"><span data-stu-id="99e69-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="99e69-146">Office 365 보호를 위한 Microsoft Defender와 다른 사용자에게 EOP 보호를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="99e69-147">미리 설정한 보안 정책의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="99e69-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="99e69-148">보호 프로필에서는 정책 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="99e69-149">표준 **및** **엄격한** 정책 설정 값은 EOP 및 [Office 365용 Microsoft Defender](recommended-settings-for-eop-and-office365.md)보안에 대한 권장 설정에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="99e69-150">미리 설정한 보안 정책 및 기타 정책의 우선 순위</span><span class="sxs-lookup"><span data-stu-id="99e69-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="99e69-151">사용자에게 여러 정책이 적용될 경우 우선 순위가 가장 높은 순서부터 가장 낮은 우선 순위까지 다음 순서가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="99e69-152">**엄격한 보호** 미리 설정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="99e69-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="99e69-153">**표준 보호** 미리 설정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="99e69-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="99e69-154">사용자 지정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="99e69-154">Custom security policies</span></span>
4. <span data-ttu-id="99e69-155">기본 보안 정책</span><span class="sxs-lookup"><span data-stu-id="99e69-155">Default security policies</span></span>

<span data-ttu-id="99e69-156">즉, **엄격한** 보호 정책의 설정은 표준 보호 정책의 설정을 오버라데이트합니다. 이 정책은 기본 정책의 설정을 정의하는 사용자 지정 정책의 설정을 정의합니다. </span><span class="sxs-lookup"><span data-stu-id="99e69-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="99e69-157">미리 설정한 보안 정책을 사용자에게 할당</span><span class="sxs-lookup"><span data-stu-id="99e69-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="99e69-158">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="99e69-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="99e69-159"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-159">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="99e69-160">미리 설정 보안 정책 페이지로 직접 **이동하기 위해** 를 <https://protection.office.com/presetSecurityPolicies> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="99e69-160">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="99e69-161">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99e69-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="99e69-162">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="99e69-163">미리 설정한 보안 정책을 구성하려면 조직 관리  또는 보안 관리자 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="99e69-164">미리 설정한 보안 정책에 대한 읽기 전용 액세스의 경우 전역 읽기 전용 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="99e69-165">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99e69-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="99e69-166">**참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에  사용자를 추가하면 사용자에게 Microsoft 365의 다른 기능에 필요한 사용 권한 및 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="99e69-167">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99e69-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="99e69-168">보안 및 & 센터를 사용하여 미리 설정한 보안 정책을 사용자에게 할당</span><span class="sxs-lookup"><span data-stu-id="99e69-168">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="99e69-169">보안 및 준수 & 위협 관리  \> **정책** \> **미리 설정 보안 정책으로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-169">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="99e69-170">표준 **보호 또는** 엄격한 **보호에서** 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="99e69-171">표준 **보호 적용 또는** 엄격한 보호 적용 **마법사가** 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="99e69-172">**EOP 보호는** 단계에 적용될 때 [EOP](#policies-in-preset-security-policies) 보호가 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-172">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="99e69-173">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-173">Click **Add a condition**.</span></span> <span data-ttu-id="99e69-174">나타나는 드롭다운에서 적용된 조건(있는 **경우)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-174">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="99e69-175">**받는 사람은**</span><span class="sxs-lookup"><span data-stu-id="99e69-175">**The recipients are**</span></span>
      - <span data-ttu-id="99e69-176">**받는 사람이 다음의 구성원**</span><span class="sxs-lookup"><span data-stu-id="99e69-176">**The recipients are members of**</span></span>
      - <span data-ttu-id="99e69-177">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="99e69-177">**The recipient domains are**</span></span>

      <span data-ttu-id="99e69-178">조건을 한 번만 사용할 수 있지만 조건에 대해 여러 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-178">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="99e69-179">같은 조건의 여러 값은 OR 논리(예: 또는 )를 _\<recipient1\>_ _\<recipient2\>_ 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-179">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="99e69-180">선택한 조건이 음영이 있는 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-180">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="99e69-181">해당 섹션에서 다음 중 **원하는 상자를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-181">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="99e69-182">잠시 기다리면 값을 선택할 수 있도록 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-182">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="99e69-183">또는 값을 입력하여 목록을 필터링하고 값을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-183">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="99e69-184">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-184">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="99e69-185">개별 값을 제거하려면 **값에서** 제거 ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-185">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="99e69-186">전체 조건을 제거하려면 **조건에서** 제거 ![ 아이콘 ](../../media/scc-remove-icon.png) 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-186">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="99e69-187">다른 조건을 추가하려면 조건 추가를 **클릭하고** 나머지 조건에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-187">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="99e69-188">다른 조건은 AND 논리(예: 및 )를 _\<recipient1\>_ _\<member of group 1\>_ 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-188">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="99e69-189">이전 단계를 반복하여 조건에 값을 추가하고 필요한 수만큼 또는 조건이 다를 때까지 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-189">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="99e69-190">예외를 추가하려면 조건 **추가 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-190">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="99e69-191">나타나는 드롭다운에서 다음인 경우 **제외에서 조건을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-191">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="99e69-192">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-192">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="99e69-193">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-193">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="99e69-194">조직에 Office 365용 Microsoft Defender가 있는 경우 MICROSOFT [Defender for Office 365](#policies-in-preset-security-policies) 보호가 적용되는 내부 받는 사람을 식별하기 위한 **단계로 ATP** 보호가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-194">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="99e69-195">설정 및 동작은 **단계에 적용되는 EOP 보호와 정확히 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-195">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="99e69-196">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="99e69-197">확인 **단계에서** 선택을 확인한 다음 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-197">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="99e69-198">보안 및 & 센터를 사용하여 미리 설정한 보안 정책 할당 수정</span><span class="sxs-lookup"><span data-stu-id="99e69-198">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="99e69-199">**표준** 보호 또는 **엄격한** 보호 보안 정책 할당을 수정하는 단계는 미리 설정한 보안 정책을 사용자에게 처음 할당할 때와 [동일합니다.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)</span><span class="sxs-lookup"><span data-stu-id="99e69-199">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="99e69-200">기존 조건 및 예외를 보존하면서 **표준** 보호 또는 **엄격한** 보호 보안 정책을 사용하지 않도록 설정하고 토글을 사용 안 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-200">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="99e69-201">정책을 사용하도록 설정하려면 토글을 사용으로 **끄면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="99e69-201">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="99e69-202">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="99e69-202">How do you know these procedures worked?</span></span>

<span data-ttu-id="99e69-203">사용자에게 표준 보호 또는 엄격한  보호 보안  정책이 할당되어 있는지 확인하기 위해 기본값이 표준 보호  설정과 다른 보호 설정을 사용해야 합니다. 이는 **Strict protection** 설정과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-203">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="99e69-204">예를 들어 스팸으로 검색된 전자 메일(높은 지수 스팸 아님)의 경우 표준  보호 사용자를 위해 메시지가 정크  메일 폴더로 배달되고 고급 보호 사용자에 대해 검역됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-204">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="99e69-205">또는 대량 [](bulk-complaint-level-values.md)전자 메일의 경우 BCL 값 6 이상이 **표준** 보호 사용자를 위해 메시지를 정크 메일 폴더로 배달하고 BCL 값 4 이상이 **엄격한** 보호 사용자에 대한 메시지를 차단하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99e69-205">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>