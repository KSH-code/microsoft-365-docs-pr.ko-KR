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
description: 관리자는 EOP(Exchange Online Protection) 및 Microsoft Defender for Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 244364b423ee633a9131aabf93b5fc1e7cf756c0
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822289"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="172b7-103">EOP 및 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="172b7-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="172b7-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="172b7-104">**Applies to**</span></span>
- [<span data-ttu-id="172b7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="172b7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="172b7-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="172b7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="172b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="172b7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="172b7-108">미리 설정한 보안 정책은 권장되는 모든 스팸, 맬웨어 및 피싱 정책을 한에 적용할 수 있는 중앙 집중식 위치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="172b7-109">정책 설정은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-109">The policy settings are not configurable.</span></span> <span data-ttu-id="172b7-110">대신 사용자로부터 유해한 콘텐츠를 보호하고 불필요한 중단을 방지하는 것 사이의 균형을 위해 데이터 센터의 관찰 및 환경을 기반으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users and avoiding unnecessary disruptions.</span></span>

<span data-ttu-id="172b7-111">이 문서의 나머지부분에서는 미리 설정한 보안 정책과 이를 구성하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-111">The rest of this article describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="172b7-112">미리 설정한 보안 정책의 적용</span><span class="sxs-lookup"><span data-stu-id="172b7-112">What preset security policies are made of</span></span>

<span data-ttu-id="172b7-113">미리 설정한 보안 정책은 다음 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="172b7-114">프로필</span><span class="sxs-lookup"><span data-stu-id="172b7-114">Profiles</span></span>
- <span data-ttu-id="172b7-115">정책</span><span class="sxs-lookup"><span data-stu-id="172b7-115">Policies</span></span>
- <span data-ttu-id="172b7-116">정책 설정</span><span class="sxs-lookup"><span data-stu-id="172b7-116">Policy settings</span></span>

<span data-ttu-id="172b7-117">또한 미리 설정한 여러 보안 정책 및 기타 정책이 동일한 사용자에 적용되는 경우 우선 순위가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="172b7-118">미리 설정한 보안 정책의 프로필</span><span class="sxs-lookup"><span data-stu-id="172b7-118">Profiles in preset security policies</span></span>

<span data-ttu-id="172b7-119">프로필에 따라 보호 수준이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-119">A profile determines the level of protection.</span></span> <span data-ttu-id="172b7-120">다음 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-120">The following profiles are available:</span></span>

- <span data-ttu-id="172b7-121">**표준 보호:** 대부분의 사용자에게 적합한 기준 보호 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="172b7-122">**엄격한 보호:** 선택한 사용자(높은 가치의 대상 또는 우선 순위 사용자)에 대한 보다 적극적인 보호 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="172b7-123">조건 및 예외와 함께 프로필이 누구인지 또는 적용되지 않는지 결정하는 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="172b7-124">사용 가능한 조건 및 예외는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-124">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="172b7-125">**사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-125">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="172b7-126">**그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-126">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
- <span data-ttu-id="172b7-127">**도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-127">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

<span data-ttu-id="172b7-128">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-128">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="172b7-129">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="172b7-129">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="172b7-130">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="172b7-130">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="172b7-131">미리 설정한 보안 정책의 정책</span><span class="sxs-lookup"><span data-stu-id="172b7-131">Policies in preset security policies</span></span>

<span data-ttu-id="172b7-132">미리 설정한 보안 정책은 EOP 및 Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="172b7-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="172b7-133">이러한 정책은 **Standard** _보호_ 또는 **엄격한** 보호 미리 설정 보안 정책을 사용자에게 할당한 후에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="172b7-134">이러한 정책은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-134">You can't modify these policies.</span></span>

- <span data-ttu-id="172b7-135">**Exchange Online Protection(EOP)** 정책: Microsoft 365 사서함이 없는 Exchange Online 독립 실행형 EOP Exchange Online 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="172b7-136">[Standard 미리](configure-your-spam-filter-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 스팸 **방지 정책**</span><span class="sxs-lookup"><span data-stu-id="172b7-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="172b7-137">[Standard 미리](configure-anti-malware-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 맬웨어 **방지 정책**</span><span class="sxs-lookup"><span data-stu-id="172b7-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="172b7-138">표준 미리 설정 보안 정책  및 엄격한 미리  설정 보안 정책(스푸핑 설정)이라는 [EOP](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="172b7-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="172b7-139">**Microsoft Defender for Office 365** 정책: Microsoft 365 E5 추가 기능 구독에 대한 Office 365 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="172b7-140">Standard Preset Security Policy 및 Strict **Preset** Security **Policy라는** 이름의 Microsoft Defender의 피싱 Office 365 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="172b7-141">EOP [](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책에서 사용할 수 있는 동일한 스푸핑 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="172b7-142">가장 설정</span><span class="sxs-lookup"><span data-stu-id="172b7-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="172b7-143">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="172b7-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="172b7-144">[표준 미리 설정](set-up-safe-links-policies.md) 보안 정책 및 엄격한 미리 **설정** 보안 정책 **이라는** 안전 링크 정책</span><span class="sxs-lookup"><span data-stu-id="172b7-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="172b7-145">[표준 미리](set-up-safe-attachments-policies.md) 설정  보안 정책 및 엄격한 미리 설정 보안 정책 이라는 안전 첨부 **파일 정책**</span><span class="sxs-lookup"><span data-stu-id="172b7-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="172b7-146">Microsoft Defender와는 다른 사용자에게 EOP 보호를 적용할 수 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="172b7-147">미리 설정한 보안 정책의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="172b7-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="172b7-148">보호 프로필에서는 정책 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="172b7-149">표준 **및** **엄격한** 정책 설정 값은 보안에 대한 EOP 및 Microsoft Defender에 대한 권장 [Office 365 설명되어 있습니다.](recommended-settings-for-eop-and-office365.md)</span><span class="sxs-lookup"><span data-stu-id="172b7-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="172b7-150">미리 설정한 보안 정책 및 기타 정책의 우선 순위</span><span class="sxs-lookup"><span data-stu-id="172b7-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="172b7-151">사용자에게 여러 정책이 적용될 경우 우선 순위가 가장 높은 순서부터 가장 낮은 우선 순위까지 다음 순서가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="172b7-152">**엄격한 보호** 미리 설정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="172b7-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="172b7-153">**표준 보호** 미리 설정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="172b7-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="172b7-154">사용자 지정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="172b7-154">Custom security policies</span></span>
4. <span data-ttu-id="172b7-155">기본 보안 정책</span><span class="sxs-lookup"><span data-stu-id="172b7-155">Default security policies</span></span>

<span data-ttu-id="172b7-156">즉, **엄격한** 보호 정책의 설정은 표준 보호 정책의 설정을 오버라데이트합니다. 이 정책은 기본 정책의 설정을 정의하는 사용자 지정 정책의 설정을 정의합니다. </span><span class="sxs-lookup"><span data-stu-id="172b7-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="172b7-157">미리 설정한 보안 정책을 사용자에게 할당</span><span class="sxs-lookup"><span data-stu-id="172b7-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="172b7-158">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="172b7-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="172b7-159">에서 Microsoft 365 보안 센터를 열 수 <https://security.microsoft.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-159">You open the Microsoft 365 security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="172b7-160">미리 설정 보안 정책 페이지로 직접 **이동하기 위해** 를 <https://security.microsoft.com/presetSecurityPolicies> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="172b7-160">To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="172b7-161">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="172b7-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="172b7-162">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="172b7-163">미리 설정한 보안 정책을 구성하려면 조직 관리  또는 보안 관리자 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="172b7-164">미리 설정한 보안 정책에 대한 읽기 전용 액세스의 경우 전역 읽기 전용 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="172b7-165">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="172b7-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="172b7-166">**참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="172b7-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="172b7-167">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="172b7-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-security-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="172b7-168">보안 센터를 사용하여 미리 설정한 보안 정책을 사용자에게 할당</span><span class="sxs-lookup"><span data-stu-id="172b7-168">Use the security center to assign preset security policies to users</span></span>

1. <span data-ttu-id="172b7-169">보안 센터에서 전자 메일 & **정책** & 규칙 위협 정책 템플릿 정책 섹션으로 \>  \>  \>  \> **이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="172b7-169">In the security center, go to **Email & collaboration** \> **Policies & Rules** \> **Threat Policies** \> **Templated policies** section \> **Preset Security Policies**.</span></span>

2. <span data-ttu-id="172b7-170">표준 **보호 또는** 엄격한 **보호에서** 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="172b7-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="172b7-171">표준 **보호 적용 또는** 엄격한 보호 적용 **마법사가** 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="172b7-172">**EOP 보호가** 페이지에 적용됨 페이지에서 [EOP](#policies-in-preset-security-policies) 보호가 적용되는 내부 받는 사람을 식별합니다(받는 사람 조건).</span><span class="sxs-lookup"><span data-stu-id="172b7-172">On the **EOP protections apply to** page, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to (recipient conditions):</span></span>
   - <span data-ttu-id="172b7-173">**사용자**</span><span class="sxs-lookup"><span data-stu-id="172b7-173">**Users**</span></span>
   - <span data-ttu-id="172b7-174">**그룹**</span><span class="sxs-lookup"><span data-stu-id="172b7-174">**Groups**</span></span>
   - <span data-ttu-id="172b7-175">**도메인**</span><span class="sxs-lookup"><span data-stu-id="172b7-175">**Domains**</span></span>

   <span data-ttu-id="172b7-176">적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-176">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="172b7-177">이 프로세스를 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-177">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="172b7-178">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-178">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="172b7-180">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-180">next to the value.</span></span>

   <span data-ttu-id="172b7-181">사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-181">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="172b7-182">사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-182">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   - <span data-ttu-id="172b7-183">**다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-183">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="172b7-184">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-184">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="172b7-185">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="172b7-186">Office 365 조직용 Microsoft Defender에서는 Office 365 보호를 위한 [Defender로](#policies-in-preset-security-policies) 이동하여 microsoft **Defender for** Office 365 보호가 적용되는 내부 받는 사람을 식별합니다(받는 사람 조건).</span><span class="sxs-lookup"><span data-stu-id="172b7-186">In Microsoft Defender for Office 365 organizations, you're taken to the **Defender for Office 365 protections apply to** page to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to (recipient conditions).</span></span>

   <span data-ttu-id="172b7-187">설정 및 동작은 EOP 보호가 페이지에 적용되는 **동작과 정확히 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="172b7-187">The settings and behavior are exactly like the **EOP protections apply to** page.</span></span>

   <span data-ttu-id="172b7-188">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-188">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="172b7-189">변경 **내용 검토 및 확인 페이지에서** 선택 사항을 확인하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="172b7-189">On the **Review and confirm your changes** page, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="172b7-190">보안 센터를 사용하여 미리 설정한 보안 정책 할당 수정</span><span class="sxs-lookup"><span data-stu-id="172b7-190">Use the security center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="172b7-191">**표준** 보호 또는 **엄격한** 보호 보안 정책 할당을 수정하는 단계는 미리 설정한 보안 정책을 사용자에게 처음 할당할 때와 [동일합니다.](#use-the-security-center-to-assign-preset-security-policies-to-users)</span><span class="sxs-lookup"><span data-stu-id="172b7-191">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="172b7-192">기존 조건 및 예외를 보존하면서 **표준** 보호 또는 **엄격한** 보호 보안 정책을 사용하지  않도록 설정하거나 해제 해제로 ![ 토글합니다. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="172b7-192">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="172b7-193">정책을 사용하도록 설정하려면 토글을 사용 토글 **으로** ![ 밀어 으로 끄면 ](../../media/scc-toggle-on.png) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-193">To enable the policies, slide the toggle to **Enabled** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="172b7-194">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="172b7-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="172b7-195">사용자에게 표준 보호 또는 엄격한  보호 보안  정책이 할당되어 있는지 확인하기 위해 기본값이 표준 보호  설정과 다른 보호 설정을 사용해야 합니다. 이는 **Strict protection** 설정과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-195">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="172b7-196">예를 들어 스팸으로 검색된 전자 메일(높은 지수 스팸 아님)의 경우 표준  보호 사용자를 위해 메시지가 정크  메일 폴더로 배달되고 고급 보호 사용자에 대해 검역됩니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-196">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="172b7-197">또는 대량 [](bulk-complaint-level-values.md)메일의 경우 BCL 값 6 이상이 **표준** 보호 사용자를 위해 메시지를 정크 메일 폴더로 배달하고 BCL 값 4 이상이 **엄격한** 보호 사용자에 대한 메시지를 차단하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="172b7-197">Or, for [bulk mail](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
