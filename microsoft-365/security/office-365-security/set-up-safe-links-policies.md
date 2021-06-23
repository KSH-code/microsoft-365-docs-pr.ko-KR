---
title: Microsoft Defender에서 금고 링크 정책 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 관리자는 Microsoft Defender for 금고 링크 정책 및 전역 금고 링크 설정을 보고, 만들고, 수정하고 삭제하는 방법을 Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4254d62cfa5844756392c00686e7b93c466d160
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082759"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f64b4-103">Microsoft Defender에서 금고 링크 정책 Office 365</span><span class="sxs-lookup"><span data-stu-id="f64b4-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f64b4-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f64b4-104">**Applies to**</span></span>
- [<span data-ttu-id="f64b4-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="f64b4-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f64b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f64b4-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="f64b4-107">이 문서는 [Office 365용 Microsoft Defender](defender-for-office-365.md)가 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="f64b4-108">사용자 계정의 Safelinks에 대한 정보를 찾는 가정용 사용자인 Outlook [고급 Outlook.com 보안 을 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="f64b4-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f64b4-109">금고 Microsoft [Defender for Office 365](defender-for-office-365.md) 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색과 전자 메일 메시지 및 기타 위치에서 URL 및 링크 확인을 클릭하는 시간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="f64b4-110">자세한 내용은 microsoft [Defender에서](safe-links.md)금고 링크를 참조하세요Office 365.</span><span class="sxs-lookup"><span data-stu-id="f64b4-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="f64b4-111">기본 제공 또는 기본 금고 정책이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="f64b4-112">URL의 금고 검색하려면 이 문서에 설명된 하나 이상의 금고 링크 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="f64b4-113">링크 정책 외부에서 금고 링크 **보호에** 대한 전역 금고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="f64b4-114">자세한 내용은 [Configure global settings for 금고 Links in Microsoft Defender for Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="f64b4-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="f64b4-115">관리자는 링크에 대한 다양한 구성 금고 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="f64b4-116">사용 가능한 옵션 중 하나는 링크에 사용자 식별 정보를 금고 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="f64b4-117">이 기능을 사용하면 *보안 Ops* 팀에서 잠재적인 사용자 손상을 조사하고, 수정 조치를 취하고, 비용이 많이 드는 위반을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="f64b4-118">금고 Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online PowerShell)에서 Exchange Online 사서함이 있는 적격 Microsoft 365 조직, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell( Exchange Online 추가 기능 구독의 경우 Microsoft Defender)에서 Office 365 링크 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="f64b4-119">링크 정책의 금고 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="f64b4-120">안전한 링크 **정책:** 금고 링크 보호를 켜고, 실시간 URL 검색을 켜고, 메시지를 배달하기 전에 실시간 검색이 완료될 때까지 기다릴지 여부를 지정하고, 내부 메시지 검색을 켜고, URL에서 사용자 클릭을 추적할지 여부를 지정하고, 사용자가 원래 URL로 휴지통을 클릭할 수 있도록 허용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="f64b4-121">**안전한 링크 규칙:** 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="f64b4-122">이러한 두 요소 간의 차이는 금고 포털에서 링크 Microsoft 365 Defender 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f64b4-123">금고 링크 정책을 만들면 실제로 동일한 이름을 사용하여 안전한 링크 규칙과 연결된 안전한 링크 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="f64b4-124">링크 정책을 금고, 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 안전한 링크 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="f64b4-125">다른 모든 설정은 연결된 안전한 링크 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="f64b4-126">링크 금고 제거하면 안전한 링크 규칙 및 연결된 안전한 링크 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="f64b4-127">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="f64b4-128">자세한 내용은 이 문서의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 사용하여 금고 링크 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f64b4-129">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f64b4-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f64b4-130"><https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="f64b4-131">링크 페이지로 직접 금고 **를** <https://security.microsoft.com/safelinksv2> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="f64b4-132">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f64b4-133">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f64b4-134">이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f64b4-135">금고 링크 정책을 만들고 수정하고 삭제하려면 Microsoft 365 Defender 포털에서 조직 관리 또는  보안 관리자 역할 그룹의 구성원이자  조직의 조직  관리 역할 그룹의 구성원인 Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="f64b4-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="f64b4-136">링크 정책에 금고 읽기 전용으로 액세스하려면 전역 읽기 사용자  또는 보안 읽기 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f64b4-137">자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 및 [Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="f64b4-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="f64b4-138">Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한 및 Microsoft 365 Defender 포털의  다른 기능에 대한 사용 권한이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f64b4-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f64b4-139">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="f64b4-140">.</span><span class="sxs-lookup"><span data-stu-id="f64b4-140">.</span></span> <span data-ttu-id="f64b4-141">- 조직의 보기 전용 **조직** 관리 [역할 Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 기능에 대한 읽기 전용 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="f64b4-142">링크 정책에 대한 권장 금고 링크 정책 금고 [설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="f64b4-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="f64b4-143">새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="f64b4-144">[새로운 기능은 계속해서](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f64b4-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="f64b4-145">새 기능이 추가될 때 기존 링크 정책에 대한 조정을 금고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="f64b4-146">Microsoft 365 Defender 포털을 사용하여 금고 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f64b4-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="f64b4-147">Microsoft 365 Defender 포털에서 사용자 지정 금고 링크 정책을 만들면 동일한 이름을 사용하여 안전한 링크 규칙과 연결된 안전한 링크 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f64b4-148">Microsoft 365 Defender 포털에서 정책 & 정책  정책 섹션에서 금고 \>  \>  \> **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f64b4-149">링크 **금고 만들기** ![ 아이콘 ](../../media/m365-cc-sc-create-icon.png) **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="f64b4-150">새 **금고 링크 정책 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="f64b4-151">정책 **이름 지정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="f64b4-152">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="f64b4-153">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f64b4-154">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f64b4-155">나타나는 **사용자 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람을 식별합니다(받는 사람 조건).</span><span class="sxs-lookup"><span data-stu-id="f64b4-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="f64b4-156">**사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f64b4-157">**그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="f64b4-158">**도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="f64b4-159">적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="f64b4-160">이 프로세스를 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="f64b4-161">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-161">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="f64b4-163">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-163">next to the value.</span></span>

   <span data-ttu-id="f64b4-164">사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="f64b4-165">사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="f64b4-166">동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="f64b4-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f64b4-167">서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="f64b4-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="f64b4-168">**다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="f64b4-169">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f64b4-170">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f64b4-171">나타나는 **보호 설정** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="f64b4-172">**메시지의** 알 수 없는 악의적인 URL에  대한 작업 선택: 전자 메일 메시지의 링크에 대한 금고 보호를 사용하도록 설정하려면 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="f64b4-173">이 설정을 켜면 다음 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="f64b4-174">**파일을 지정하는** 의심스러운 링크 및 링크에 대한 실시간 URL 검색 적용: 전자 메일 메시지의 링크를 실시간으로 검색할 수 있도록 설정하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="f64b4-175">이 설정을 켜면 다음 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="f64b4-176">**메시지를 배달하기** 전에 URL 검색이 완료될 때까지 기다렸다가 : 메시지를 배달하기 전에 실시간 URL 검색이 완료될 때까지 기다리는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="f64b4-177">**조직 금고** 보내는 전자 메일 메시지에 대한 링크 적용: 내부 보낸 사람과 내부 받는 사람 간의 메시지에 금고 링크 정책을 적용하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="f64b4-178">**내 알 수 없는 URL** 또는 잠재적으로 악의적인  URL에 대한 작업을 Microsoft Teams: 을 선택하여 금고 링크 보호를 사용하도록 Teams.</span><span class="sxs-lookup"><span data-stu-id="f64b4-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="f64b4-179">**사용자 클릭 추적 안** 하세요. 추적 사용자가 전자 메일 메시지의 URL을 클릭할 수 있도록 설정하려면 이 설정을 선택하지 않은 그대로 하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="f64b4-180">**사용자가 원래 URL을 클릭할** 수 있도록 허용 안 하도록 허용: 사용자가 경고 페이지에서 원래 URL을 클릭하지 못하도록 차단하려면 이 [옵션을 선택합니다.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="f64b4-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="f64b4-181">**다음 URL을** 다시 덮어치지 않습니다. 링크에서 차단할 지정된 URL에 액세스할 금고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="f64b4-182">상자에 원하는 URL 또는 값을 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="f64b4-183">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="f64b4-184">기존 항목을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="f64b4-184">To remove an existing entry, click</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="f64b4-186">항목 옆의</span><span class="sxs-lookup"><span data-stu-id="f64b4-186">next to the entry.</span></span>

     <span data-ttu-id="f64b4-187">항목 구문은 "다음 URL을 다시 덮어치지 않습니다." 목록의 항목 [구문을 참조하세요.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="f64b4-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="f64b4-188">이러한 설정에 대한 자세한 내용은 전자 [메일 메시지에](safe-links.md#safe-links-settings-for-email-messages) 대한 금고 링크 설정 및 금고 링크 설정을 [Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="f64b4-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="f64b4-189">표준 및 엄격한 정책 설정에 대한 권장 값은 금고 링크 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="f64b4-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="f64b4-190">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f64b4-191">알림 **페이지가** 나타나면 사용자에게 어떻게 알리시겠습니까?에 대해 다음 값 중 하나를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="f64b4-192">**기본 알림 텍스트 사용**</span><span class="sxs-lookup"><span data-stu-id="f64b4-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="f64b4-193">**사용자 지정 알림 텍스트 사용:** 이 값을 선택하면 다음 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-193">**Use custom notification text**: If you select this value, the following settings appear:</span></span>
     - <span data-ttu-id="f64b4-194">**자동 Microsoft 번역기 설정 사용**</span><span class="sxs-lookup"><span data-stu-id="f64b4-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="f64b4-195">**사용자 지정 알림 텍스트:** 이 상자에 사용자 지정 알림 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="f64b4-196">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f64b4-197">표시되는 **검토** 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="f64b4-198">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="f64b4-199">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="f64b4-200">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="f64b4-201">표시되는 확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="f64b4-202">Microsoft 365 Defender 포털을 사용하여 금고 정책 보기</span><span class="sxs-lookup"><span data-stu-id="f64b4-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="f64b4-203">Microsoft 365 Defender 포털에서 정책 & 정책  정책 섹션에서 금고 \>  \>  \> **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f64b4-204">금고  링크 페이지에는 다음 속성이 링크 정책 금고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="f64b4-205">**이름**</span><span class="sxs-lookup"><span data-stu-id="f64b4-205">**Name**</span></span>
   - <span data-ttu-id="f64b4-206">**상태**</span><span class="sxs-lookup"><span data-stu-id="f64b4-206">**Status**</span></span>
   - <span data-ttu-id="f64b4-207">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="f64b4-207">**Priority**</span></span>

3. <span data-ttu-id="f64b4-208">이름을 클릭하여 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="f64b4-209">Microsoft 365 Defender 포털을 사용하여 링크 금고 수정</span><span class="sxs-lookup"><span data-stu-id="f64b4-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="f64b4-210">Microsoft 365 Defender 포털에서 정책 & 정책  정책 섹션에서 금고 \>  \>  \> **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f64b4-211">링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f64b4-212">표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="f64b4-213">설정에 대한 자세한 내용은 이 문서의 이전 Microsoft 365 Defender [포털을 사용하여](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) 금고 링크 정책 만들기 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="f64b4-214">정책을 사용하도록 설정하거나 사용하지 않도록 설정하거나 정책 우선 순위를 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="f64b4-215">링크 정책 금고 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f64b4-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="f64b4-216">Microsoft 365 Defender 포털에서 Email & **Collaboration** Policies & \> **Rules** \> **Threat policies(규칙** 위협 정책 금고 정책) \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f64b4-217">링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f64b4-218">표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="f64b4-219">**정책 끄기**: 정책을 켜려면 ![켜기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="f64b4-220">**정책**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="f64b4-221">표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="f64b4-222">정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="f64b4-223">기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="f64b4-224">링크 정책의 금고 설정</span><span class="sxs-lookup"><span data-stu-id="f64b4-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="f64b4-225">기본적으로 금고 링크에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="f64b4-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="f64b4-226">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="f64b4-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f64b4-227">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="f64b4-228">정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(Microsoft 365 Defender 포털에서 **우선 순위** 번호를 직접 수정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="f64b4-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="f64b4-229">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="f64b4-230">**참고**:</span><span class="sxs-lookup"><span data-stu-id="f64b4-230">**Note**:</span></span>

- <span data-ttu-id="f64b4-231">Microsoft 365 Defender 포털에서 만든 후 금고 링크 정책의 우선 순위만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="f64b4-232">PowerShell에서 안전한 링크 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="f64b4-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="f64b4-233">금고 링크 정책은 표시되는 순서대로 처리됩니다(첫 번째 정책의  우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="f64b4-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f64b4-234">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="f64b4-235">Microsoft 365 Defender 포털에서 Email & **Collaboration** Policies & \> **Rules** \> **Threat policies(규칙** 위협 정책 금고 정책) \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f64b4-236">링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f64b4-237">표시되는 정책 세부 정보 플라이아웃 맨 위에 현재 우선 순위 값 및 사용자 지정 정책 수를 기준으로 **우선순위 증가** 또는 **우선순위 감소** 가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="f64b4-238">우선 순위  값이 **0인** 정책에는 우선 순위 감소 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="f64b4-239">우선 순위 값이 가장 **낮은** 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="f64b4-240">세 개 이상의 정책이 있는 경우 우선 순위가 가장  높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="f64b4-241">![우선순위 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선순위** 또는 ![우선순위 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위** 를 클릭하여 **우선순위** 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="f64b4-242">작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="f64b4-243">Microsoft 365 Defender 포털을 사용하여 링크 금고 제거</span><span class="sxs-lookup"><span data-stu-id="f64b4-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="f64b4-244">Microsoft 365 Defender 포털에서 Email & **Collaboration** Policies & \> **Rules** \> **Threat policies(규칙** 위협 정책 금고 정책) \>  \> **섹션으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f64b4-245">링크 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="f64b4-246">표시되는 정책 세부 정보 플라이아웃의 맨 위에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)**추가 작업**\>![정책 삭제 아이콘](../../media/m365-cc-sc-delete-icon.png)**정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="f64b4-247">확인 대화 상자가 나타나면 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="f64b4-248">PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 금고 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f64b4-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="f64b4-249">앞서 설명한 금고 링크 정책은 안전한 링크 정책과 안전한 링크 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="f64b4-250">PowerShell에서 안전한 링크 정책과 안전한 링크 규칙의 차이는 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="f64b4-251">**\* -SafeLinksPolicy** cmdlet을 사용하여 안전한 링크 정책을 관리하고 **\* -SafeLinksRule** cmdlet을 사용하여 안전한 링크 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="f64b4-252">PowerShell에서 먼저 안전한 링크 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 안전한 링크 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f64b4-253">PowerShell에서는 안전한 링크 정책 및 안전한 링크 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="f64b4-254">PowerShell에서 안전한 링크 정책을 제거하면 해당 안전 링크 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="f64b4-255">PowerShell을 사용하여 금고 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f64b4-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="f64b4-256">PowerShell에서 금고 링크 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f64b4-257">안전한 링크 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="f64b4-258">규칙이 적용되는 안전한 링크 정책을 지정하는 안전한 링크 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f64b4-259">새 안전한 링크 규칙을 만들고 연결되지 않은 기존 안전한 링크 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="f64b4-260">안전한 링크 규칙은 두 개 이상의 안전한 링크 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="f64b4-261">정책을 만든 후까지 Microsoft 365 Defender 포털에서 사용할 수 없는 PowerShell의 새 안전한 링크 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="f64b4-262">새 정책을 사용하지 않도록 `$false` **설정(New-SafeLinksRule** cmdlet에서 사용)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="f64b4-263"> _\<Number\>_ **New-SafeLinksRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="f64b4-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="f64b4-264">PowerShell에서 만든 새 안전한 링크 정책은 안전한 링크 규칙에 정책을 할당할 때까지 Microsoft 365 Defender 포털에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="f64b4-265">1단계: PowerShell을 사용하여 안전한 링크 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f64b4-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="f64b4-266">안전한 링크 정책을 만들 수 있도록 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="f64b4-267">_DoNotRewriteUrls_ 매개 변수에 사용할 항목 구문에 대한 자세한 내용은 "다음 URL을 다시 덮어치지 않습니다" 목록의 항목 구문을 [참조하세요.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="f64b4-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="f64b4-268">**Set-SafeLinksPolicy** cmdlet을 사용하여 기존 안전한 링크 정책을 수정할 때 _DoNotRewriteUrls_ 매개 변수에 사용할 수 있는 추가 구문은 이 문서 의 부분에 있는 [PowerShell을](#use-powershell-to-modify-safe-links-policies) 사용하여 안전한 링크 정책 수정 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="f64b4-269">이 예에서는 다음 값을 지정하여 Contoso All이라는 안전한 링크 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="f64b4-270">전자 메일 메시지에서 URL 검색 및 다시 끄기</span><span class="sxs-lookup"><span data-stu-id="f64b4-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="f64b4-271">탭에서 URL 검색을 Teams 탭 미리 보기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="f64b4-272">파일을 지점하는 클릭된 링크를 포함하여 클릭한 URL에 대한 실시간 검색을 하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="f64b4-273">URL 검색이 완료될 때까지 기다렸다가 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="f64b4-274">내부 메시지에 대해 URL 검색 및 다시 덮기 기능을 켜세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="f64b4-275">금고 링크 보호와 관련된 사용자 클릭 _추적(DoNotTrackUserClicks_ 매개 변수를 사용하지는 않습니다. 기본값은 $false, 즉 사용자 클릭이 추적됩니다.)입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="f64b4-276">사용자가 원래 URL을 클릭할 수 있도록 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="f64b4-277">구문과 매개 변수에 대한 자세한 내용은 [New-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="f64b4-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="f64b4-278">2단계: PowerShell을 사용하여 안전한 링크 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="f64b4-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="f64b4-279">안전한 링크 규칙을 만들 수 있도록 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="f64b4-280">이 예에서는 다음 조건을 통해 Contoso All이라는 안전한 링크 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="f64b4-281">이 규칙은 Contoso All이라는 안전한 링크 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="f64b4-282">이 규칙은 도메인의 모든 받는 사람에게 contoso.com 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="f64b4-283">Priority 매개 변수를  사용하지 않을 것이기 때문에 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="f64b4-284">이 규칙은 사용하도록 설정됩니다(Enabled  매개 변수를 사용하지 않습니다. 기본값은 `$true` 입니다).</span><span class="sxs-lookup"><span data-stu-id="f64b4-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="f64b4-285">구문과 매개 변수에 대한 자세한 내용은 [New-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="f64b4-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="f64b4-286">PowerShell을 사용하여 안전한 링크 정책 보기</span><span class="sxs-lookup"><span data-stu-id="f64b4-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="f64b4-287">기존 안전한 링크 정책을 보시고 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f64b4-288">이 예에서는 모든 안전한 링크 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="f64b4-289">이 예에서는 Contoso Executives라는 안전한 링크 정책에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="f64b4-290">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="f64b4-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="f64b4-291">PowerShell을 사용하여 안전한 링크 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="f64b4-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="f64b4-292">기존 안전한 링크 규칙을 보시고 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f64b4-293">이 예에서는 모든 안전한 링크 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="f64b4-294">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="f64b4-295">이 예에서는 Contoso Executives라는 안전한 링크 규칙에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="f64b4-296">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeLinksRule 을 참조하십시오.](/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="f64b4-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="f64b4-297">PowerShell을 사용하여 안전한 링크 정책 수정</span><span class="sxs-lookup"><span data-stu-id="f64b4-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="f64b4-298">PowerShell에서 안전한 링크 정책의 이름을 다시 설정할 수 **없습니다(Set-SafeLinksPolicy** cmdlet에는 _Name_ 매개 변수가 없음).</span><span class="sxs-lookup"><span data-stu-id="f64b4-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f64b4-299">금고 포털에서 금고 정책의 이름을 Microsoft 365 Defender 안전한 링크 규칙의 이름만 다시 _매기게 됩니다._</span><span class="sxs-lookup"><span data-stu-id="f64b4-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="f64b4-300">PowerShell에서 안전한 링크 정책을 수정할 때 고려해야 할 유일한 추가 고려 사항은 _DoNotRewriteUrls_ 매개 변수("다음 URL을 다시 덮어 두지 [않습니다" 목록)에](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)사용할 수 있는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="f64b4-301">기존 항목을 대체할 값을 추가하기 위해 다음 구문을 `"Entry1","Entry2,..."EntryN"` 사용합니다. .</span><span class="sxs-lookup"><span data-stu-id="f64b4-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="f64b4-302">다른 기존 항목에 영향을 주지 않고 값을 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="f64b4-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="f64b4-303">그렇지 않으면 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-a-safe-links-policy) 사용하여 안전한 링크 정책 만들기 섹션에 설명된 대로 안전한 링크 정책을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="f64b4-304">안전한 링크 정책을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f64b4-305">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="f64b4-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="f64b4-306">PowerShell을 사용하여 안전한 링크 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="f64b4-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="f64b4-307">PowerShell에서 안전한 링크 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용하지 않도록 설정된 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f64b4-308">기존 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="f64b4-309">그렇지 않으면 이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-a-safe-links-rule) 사용하여 안전한 링크 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="f64b4-310">안전한 링크 규칙을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f64b4-311">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="f64b4-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="f64b4-312">PowerShell을 사용하여 안전한 링크 규칙을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f64b4-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="f64b4-313">PowerShell에서 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 금고 링크 정책(안전한 링크 규칙 및 할당된 안전한 링크 정책)을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="f64b4-314">PowerShell에서 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="f64b4-315">이 예에서는 Marketing Department라는 안전한 링크 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f64b4-316">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f64b4-317">구문과 매개 변수에 대한 자세한 내용은 [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) 및 [Disable-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="f64b4-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="f64b4-318">PowerShell을 사용하여 안전한 링크 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="f64b4-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="f64b4-319">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-319">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f64b4-320">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-320">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f64b4-321">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-321">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f64b4-322">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-322">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f64b4-323">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-323">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f64b4-324">PowerShell에서 안전한 링크 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f64b4-325">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-325">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="f64b4-326">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="f64b4-326">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="f64b4-327">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-SafeLinksRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="f64b4-328">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="f64b4-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="f64b4-329">PowerShell을 사용하여 안전한 링크 정책 제거</span><span class="sxs-lookup"><span data-stu-id="f64b4-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="f64b4-330">PowerShell을 사용하여 안전한 링크 정책을 제거하면 해당 안전한 링크 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="f64b4-331">PowerShell에서 안전한 링크 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f64b4-332">이 예에서는 Marketing Department라는 안전한 링크 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f64b4-333">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeLinksPolicy를 참조하십시오.](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="f64b4-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="f64b4-334">PowerShell을 사용하여 안전한 링크 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="f64b4-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="f64b4-335">PowerShell을 사용하여 안전한 링크 규칙을 제거하면 해당 안전한 링크 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="f64b4-336">PowerShell에서 안전한 링크 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="f64b4-337">이 예에서는 Marketing Department라는 안전한 링크 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f64b4-338">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeLinksRule을 참조하십시오.](/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="f64b4-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="f64b4-339">링크가 금고 검사하는지 확인을 위해 사용 가능한 Microsoft Defender에서 보고서의 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="f64b4-340">자세한 내용은 Office 365 포털에서 [Defender에](view-reports-for-mdo.md) 대한 보고서 Office 365 [탐색기 Microsoft 365 Defender 참조하세요.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="f64b4-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f64b4-341">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="f64b4-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="f64b4-342">링크 정책이 만들어지거나 수정 또는 제거 금고 다음 단계를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="f64b4-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="f64b4-343">Microsoft 365 Defender 포털에서 정책 & 위협  정책 금고 \>  \> **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="f64b4-344">정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="f64b4-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f64b4-345">자세한 내용을 확인하려면 목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 하세요.</span><span class="sxs-lookup"><span data-stu-id="f64b4-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="f64b4-346">PowerShell Exchange Online PowerShell Exchange Online Protection PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f64b4-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
