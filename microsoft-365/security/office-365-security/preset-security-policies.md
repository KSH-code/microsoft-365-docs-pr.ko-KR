---
title: 보안 정책 미리조정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 EOP (Exchange Online Protection) 및 Office 365 Advanced Threat Protection (ATP)의 보호 기능을 통해 표준 및 엄격한 정책 설정을 적용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: dd730639aa15709bafd600d4cc2706befb143cd4
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430402"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="0fb4c-103">EOP 및 Office 365 ATP의 미리 설정 된 보안 정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-103">Preset security policies in EOP and Office 365 ATP</span></span>

<span data-ttu-id="0fb4c-104">미리 설정 된 보안 정책은 권장 되는 모든 스팸, 맬웨어 및 피싱 정책을 사용자에 게 한 번에 적용 하기 위한 중앙 집중식 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="0fb4c-105">정책 설정을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-105">The policy settings are not configurable.</span></span> <span data-ttu-id="0fb4c-106">대신, 이러한 기능은 우리에 의해 설정 되며, 데이터 센터의 관찰 및 경험에 따라 작업을 방해 하지 않고 사용자에 게 해로운 콘텐츠를 보관 하는 것 간의 균형을 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="0fb4c-107">이 항목의 나머지 부분에서는 미리 설정 된 보안 정책 및 이러한 정책을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="0fb4c-108">미리 설정 된 보안 정책 구성</span><span class="sxs-lookup"><span data-stu-id="0fb4c-108">What preset security policies are made of</span></span>

<span data-ttu-id="0fb4c-109">미리 설정 된 보안 정책은 다음 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="0fb4c-110">프로필</span><span class="sxs-lookup"><span data-stu-id="0fb4c-110">Profiles</span></span>
- <span data-ttu-id="0fb4c-111">정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-111">Policies</span></span>
- <span data-ttu-id="0fb4c-112">정책 설정</span><span class="sxs-lookup"><span data-stu-id="0fb4c-112">Policy settings</span></span>

<span data-ttu-id="0fb4c-113">또한 미리 설정 된 여러 보안 정책 및 기타 정책이 동일한 사람에 게 적용 되는 경우에는 우선 순위 순서가 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="0fb4c-114">미리 설정 된 보안 정책의 프로필</span><span class="sxs-lookup"><span data-stu-id="0fb4c-114">Profiles in preset security policies</span></span>

<span data-ttu-id="0fb4c-115">프로필은 보호 수준을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-115">A profile determines the level of protection.</span></span> <span data-ttu-id="0fb4c-116">다음과 같은 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-116">The following profiles are available:</span></span>

- <span data-ttu-id="0fb4c-117">**표준 보호**: 대부분의 사용자에 게 적합 한 기본 보호 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="0fb4c-118">**엄격한 보호**: 선택한 사용자 (높은 값 목표 또는 우선 순위 사용자)에 대 한 적극적인 보호 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="0fb4c-119">프로필을 지정 하거나 적용 하지 않을 사람을 결정 하는 조건 및 예외 사항에 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="0fb4c-120">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0fb4c-121">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="0fb4c-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0fb4c-122">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0fb4c-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="0fb4c-123">사용 가능한 조건 및 예외는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="0fb4c-124">**받는 사람은**조직의 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="0fb4c-125">**받는 사람은**조직의 그룹 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="0fb4c-126">**받는 사람 도메인**은 Microsoft 365에 구성 되어 있는 허용 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="0fb4c-127">미리 설정 된 보안 정책의 정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-127">Policies in preset security policies</span></span>

<span data-ttu-id="0fb4c-128">미리 설정 된 보안 정책은 EOP 및 Office 365 ATP의 다양 한 보호 기능에서 해당 하는 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-128">Preset security policies use the corresponding policies from the various protection features in EOP and Office 365 ATP.</span></span> <span data-ttu-id="0fb4c-129">이러한 정책은 **표준 보호** 또는 **엄격한 보호** 사전 설정 보안 정책을 사용자에 게 할당 _한 후_ 에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="0fb4c-130">이러한 정책은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-130">You can't modify these policies.</span></span>

- <span data-ttu-id="0fb4c-131">**EOP (Exchange Online Protection) 정책**: exchange online 사서함을 사용 하는 Microsoft 365 조직과 exchange online 사서함이 없는 독립 실행형 EOP 조직이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="0fb4c-132">**표준 사전 설정 보안 정책** 및 **엄격한 사전 설정 보안 정책**이라는 [스팸 방지 정책](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0fb4c-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="0fb4c-133">**표준 사전 설정 보안 정책** 및 **엄격한 사전 설정 보안 정책**이라는 [맬웨어 방지 정책](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0fb4c-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="0fb4c-134">**표준 사전 설정 보안 정책** 및 **엄격한 미리 설정 된 보안 정책** (스푸핑 설정) 이라는 [EOP 피싱 방지 정책](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="0fb4c-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="0fb4c-135">**Office 365 atp (Advanced Threat Protection) 정책**: 여기에는 Microsoft 365 E5 또는 OFFICE 365 ATP 추가 기능 구독이 있는 조직이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-135">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="0fb4c-136">다음을 포함 하는 **표준 사전 설정 보안 정책** 및 **엄격한 미리 설정 보안 정책**이라는 ATP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-136">ATP anti-phishing policies named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="0fb4c-137">EOP 피싱 방지 정책에서 사용할 수 있는 것과 동일한 [스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="0fb4c-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="0fb4c-138">가장 설정</span><span class="sxs-lookup"><span data-stu-id="0fb4c-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="0fb4c-139">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="0fb4c-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="0fb4c-140">[안전한 링크 정책](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) **표준 사전 설정 보안 정책** 및 **엄격한 미리 설정 된 보안 정책**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-140">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="0fb4c-141">[안전한 첨부 파일 정책](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) **표준 미리 설정 보안 정책** 및 **엄격한 미리 설정 된 보안 정책**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-141">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="0fb4c-142">ATP 보호와는 다른 사용자에 게 EOP 보호를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-142">Note that you can apply EOP protections to different users than ATP protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="0fb4c-143">미리 설정 된 보안 정책의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0fb4c-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="0fb4c-144">보호 프로필에서 정책 설정은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="0fb4c-145">**표준** 및 **엄격한** 정책 설정 값은 [EOP 및 Office 365 ATP 보안에 대 한 권장 설정](recommended-settings-for-eop-and-office365-atp.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="0fb4c-146">미리 설정 된 보안 정책 및 기타 정책의 우선 순위 순서</span><span class="sxs-lookup"><span data-stu-id="0fb4c-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="0fb4c-147">여러 정책이 사용자에 게 적용 되는 경우 다음 순서는 가장 높은 우선 순위에서 가장 낮은 우선 순위로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="0fb4c-148">**엄격한 보호** 사전 설정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="0fb4c-149">**표준 보호** 사전 설정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="0fb4c-150">사용자 지정 보안 정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-150">Custom security policies</span></span>
4. <span data-ttu-id="0fb4c-151">기본 보안 정책</span><span class="sxs-lookup"><span data-stu-id="0fb4c-151">Default security policies</span></span>

<span data-ttu-id="0fb4c-152">즉, **엄격한 보호** 정책 설정은 기본 정책의 설정을 재정의 하는 사용자 지정 정책의 설정을 재정의 하는 **표준 보호** 정책의 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="0fb4c-153">사용자에 게 미리 설정 된 보안 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0fb4c-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0fb4c-154">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0fb4c-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0fb4c-155"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0fb4c-156">**미리 설정 된 보안 정책** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/presetSecurityPolicies> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="0fb4c-157">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0fb4c-158">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-158">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="0fb4c-159">미리 설정 된 보안 정책을 구성 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-159">To configure preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0fb4c-160">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-160">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0fb4c-161">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-161">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="0fb4c-162">미리 설정 된 보안 정책에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-162">For read-only access to preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0fb4c-163">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-163">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0fb4c-164">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-164">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="0fb4c-165">보안 & 준수 센터를 사용 하 여 사용자에 게 미리 설정 된 보안 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0fb4c-165">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="0fb4c-166">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **미리 설정 된 보안 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="0fb4c-167">**표준 보호** 또는 **엄격한 보호**에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-167">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="0fb4c-168">**표준 보호 적용** 또는 **엄격한 보호 적용** 마법사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-168">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="0fb4c-169">**EOP 보호 적용** 단계에서 [EOP 보호](#policies-in-preset-security-policies) 를 적용할 내부 받는 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-169">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="0fb4c-170">**조건 추가를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-170">Click **Add a condition**.</span></span> <span data-ttu-id="0fb4c-171">표시 되는 드롭다운 목록에서 다음의 **경우 적용**아래의 조건을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-171">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="0fb4c-172">**받는 사람이**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-172">**The recipients are**</span></span>
      - <span data-ttu-id="0fb4c-173">**받는 사람이 다음 구성원 인 경우**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-173">**The recipients are members of**</span></span>
      - <span data-ttu-id="0fb4c-174">**받는 사람 도메인이**</span><span class="sxs-lookup"><span data-stu-id="0fb4c-174">**The recipient domains are**</span></span>

      <span data-ttu-id="0fb4c-175">조건을 한 번만 사용할 수 있지만 조건에 대해 여러 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-175">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="0fb4c-176">동일한 조건 사용 또는 논리의 여러 값 (예: _\<recipient1\>_ or _\<recipient2\>_ )</span><span class="sxs-lookup"><span data-stu-id="0fb4c-176">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="0fb4c-177">선택한 조건이 음영 처리 된 구역에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-177">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="0fb4c-178">해당 섹션에서 **다음 상자 중 하나** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-178">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="0fb4c-179">잠시 기다리면 값을 선택할 수 있는 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-179">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="0fb4c-180">또는 값을 입력 하 여 목록을 필터링 하 고 값을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-180">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="0fb4c-181">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="0fb4c-182">개별 값을 제거 하려면 값에서 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-182">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="0fb4c-183">전체 조건을 제거 하려면 **Remove** ![ 조건에서 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-183">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="0fb4c-184">다른 조건을 추가 하려면 **조건 추가** 를 클릭 하 고 나머지 조건에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-184">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="0fb4c-185">서로 다른 조건 및 논리가 사용 됩니다 (예: _\<recipient1\>_ and _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="0fb4c-185">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="0fb4c-186">이전 단계를 반복 하 여 조건에 값을 추가 하 고, 필요에 따라 또는 조건이 없어질 때까지이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-186">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="0fb4c-187">예외를 추가 하려면 **조건 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-187">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="0fb4c-188">표시 되는 드롭다운 목록에서 **When 제외**아래의 조건을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-188">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="0fb4c-189">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-189">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0fb4c-190">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0fb4c-191">조직에 Office 365 ATP가 있는 경우 **ATP 보호를 적용** 하 여 [office 365 atp 보호가](#policies-in-preset-security-policies) 적용 되는 내부 받는 사람을 식별 하는 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-191">If your organization has Office 365 ATP, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Office 365 ATP protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="0fb4c-192">설정 및 동작은 **EOP 보호 적용** 단계와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-192">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="0fb4c-193">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0fb4c-194">**확인** 단계에서 선택한 항목을 확인 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-194">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="0fb4c-195">보안 & 준수 센터를 사용 하 여 미리 설정 된 보안 정책의 할당 수정</span><span class="sxs-lookup"><span data-stu-id="0fb4c-195">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="0fb4c-196">**표준 보호** 또는 **엄격한 보호** 보안 정책에 대 한 할당을 수정 하는 단계는 [미리 설정 된 보안 정책을 사용자에 게 처음 할당](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)했을 때와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-196">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="0fb4c-197">기존 조건 및 예외를 유지 하면서 **표준 보호** 또는 **엄격한 보호** 보안 정책을 사용 하지 않도록 설정 하려면 슬라이드를 **사용 안 함으로**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-197">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="0fb4c-198">정책을 사용 하도록 설정 하려면 설정/해제를 **사용**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-198">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0fb4c-199">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="0fb4c-199">How do you know these procedures worked?</span></span>

<span data-ttu-id="0fb4c-200">사용자에 게 **표준 보호** 또는 **엄격한 보호** 보안 정책이 할당 되었는지 확인 하려면 기본 값이 **표준 보호** 설정과 다른 경우 ( **엄격한 보호** 설정과는 다름) 보호 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-200">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="0fb4c-201">예를 들어 스팸이 아닌 스팸으로 검색 되는 전자 메일 (신뢰도가 높은 스팸 아님)의 경우 메시지가 **표준 보호** 사용자에 대 한 정크 메일 폴더로 배달 되 고 **엄격한 보호** 사용자에 대해 격리 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-201">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="0fb4c-202">또는 [대량 전자 메일](bulk-complaint-level-values.md)의 경우, bcl 값 6 이상이 **표준 보호** 사용자의 정크 메일 폴더에 메시지를 전달 하 고, Bcl 값 4 이상이 **엄격한 보호** 사용자에 대 한 메시지를 설정별 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fb4c-202">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
