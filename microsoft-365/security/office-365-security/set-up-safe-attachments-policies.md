---
title: Microsoft Defender에서 금고 첨부 파일 정책 설정 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 전자 메일의 악성 금고 보호하기 위해 첨부 파일 정책을 정의하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108226"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ea703-103">Microsoft Defender에서 금고 첨부 파일 정책 설정 Office 365</span><span class="sxs-lookup"><span data-stu-id="ea703-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ea703-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="ea703-104">**Applies to**</span></span>
- [<span data-ttu-id="ea703-105">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="ea703-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ea703-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea703-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="ea703-107">이 문서는 [Office 365용 Microsoft Defender](whats-new-in-defender-for-office-365.md)가 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="ea703-108">가정용 사용자인 경우 Outlook 고급 [Outlook.com 보안 을 참조하세요.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="ea703-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="ea703-109">금고 첨부 파일은 [EOP(Exchange Online Protection)에서](whats-new-in-defender-for-office-365.md) 맬웨어 방지 보호를 통해 검색된 후 받는 사람에게 배달되기 전에 [](anti-malware-protection.md)가상 환경을 사용하여 인바운드 전자 메일 메시지의 첨부 파일을 검사하는 Office 365 Microsoft Defender의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="ea703-110">자세한 내용은 microsoft [Defender에서](safe-attachments.md)금고 첨부 파일을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea703-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="ea703-111">첨부 파일 정책에 대한 기본 금고 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="ea703-112">전자 메일 금고 첨부 파일 검색을 시작하려면 이 문서에 설명된 금고 첨부 파일 정책을 하나 이상 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="ea703-113">Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online PowerShell)에서 Exchange Online 사서함이 있는 적합한 Microsoft 365 조직, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell( Office 365 추가 기능 구독용 Defender)에서 Office 365 첨부 파일 정책을 구성할 수 있습니다. 금고</span><span class="sxs-lookup"><span data-stu-id="ea703-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="ea703-114">첨부 파일 정책의 금고 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="ea703-115">**안전한** 첨부 파일 정책: 알 수 없는 맬웨어 검색에 대한 작업, 맬웨어 첨부 파일이 첨부된 메시지를 지정된 전자 메일 주소로 보낼지 여부, 금고 첨부 파일 검색을 완료할 수 없는 경우 메시지를 배달할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="ea703-116">**안전한 첨부 파일 규칙:** 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="ea703-117">이러한 두 요소 간의 차이는 금고 포털에서 첨부 파일 정책을 관리할 때 명확하지 Microsoft 365 Defender 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="ea703-118">첨부 파일 금고 만들면 실제로 동일한 이름을 사용하여 안전한 첨부 파일 규칙과 연결된 안전한 첨부 파일 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ea703-119">첨부 파일 정책을 금고, 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 안전한 첨부 파일 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="ea703-120">다른 모든 설정은 연결된 안전한 첨부 파일 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="ea703-121">첨부 파일 금고 제거하면 안전한 첨부 파일 규칙 및 연결된 안전한 첨부 파일 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="ea703-122">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ea703-123">자세한 내용은 이 문서의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 사용하여 금고 첨부 파일 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="ea703-124">첨부 파일 설정의 전역 설정 금고 첨부 파일 정책에 종속되지 않는 금고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="ea703-125">자세한 내용은 [금고 에서 SharePoint,](turn-on-mdo-for-spo-odb-and-teams.md) OneDrive 및 Microsoft Teams 금고 [문서에](safe-docs.md)대한 첨부 파일 Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ea703-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ea703-126">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="ea703-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ea703-127"><https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="ea703-128">첨부 파일 **페이지로** 직접 금고 를 <https://security.microsoft.com/safeattachmentv2> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ea703-129">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ea703-130">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ea703-131">이 문서의 절차를 수행하려면 먼저 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ea703-132">금고 첨부 파일 정책을 만들고 수정하고 삭제하려면 Microsoft 365 Defender 포털에서 조직 관리 또는  보안 관리자 역할 그룹의 구성원이자 조직의  조직 관리 역할 그룹의 구성원이 Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="ea703-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="ea703-133">첨부 파일 정책에 금고 읽기 전용으로 액세스하려면 Microsoft 365 Defender 포털에서  전역  읽기 그룹 또는 보안 읽기 Microsoft 365 Defender 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="ea703-134">자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 및 [Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="ea703-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ea703-135">**참고:**</span><span class="sxs-lookup"><span data-stu-id="ea703-135">**Notes**:</span></span>

  - <span data-ttu-id="ea703-136">Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 관리 센터 포털에서 필요한 사용 권한 및 Microsoft 365 Defender 포털의  다른 기능에 대한 사용 권한이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea703-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ea703-137">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ea703-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ea703-139">첨부 파일 정책에 대한 권장 금고 첨부 파일 금고 [참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="ea703-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="ea703-140">새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="ea703-141">Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 만들기</span><span class="sxs-lookup"><span data-stu-id="ea703-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="ea703-142">Microsoft 365 Defender 포털에서 사용자 지정 금고 첨부 파일 정책을 만들면 동일한 이름을 사용하여 안전한 첨부 파일 규칙과 연결된 안전한 첨부 파일 정책이 동시에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="ea703-143">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 정책 섹션에서 금고 \>  \>  \>  \> **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ea703-144">첨부 **금고 페이지에서** 만들기 ![ 아이콘 만들기 ](../../media/m365-cc-sc-create-icon.png) **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="ea703-145">정책 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-145">The policy wizard opens.</span></span> <span data-ttu-id="ea703-146">정책 **이름 지정 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="ea703-147">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="ea703-148">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ea703-149">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ea703-150">나타나는 **사용자 및 도메인** 페이지에서 정책이 적용되는 내부 받는 사람을 식별합니다(받는 사람 조건).</span><span class="sxs-lookup"><span data-stu-id="ea703-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="ea703-151">**사용자**: 조직의 지정된 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ea703-152">**그룹**: 조직에서 지정한 메일 그룹, 메일 사용이 가능한 보안 그룹 또는 Microsoft 365 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="ea703-153">**도메인**: 조직에서 지정한 [허용 도메인](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)의 모든 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="ea703-154">적절한 상자를 클릭하고, 값 입력을 시작하고, 결과에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="ea703-155">이 프로세스를 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="ea703-156">기존 값을 제거하려면 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-156">To remove an existing value, click remove</span></span> ![아이콘 제거](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="ea703-158">값 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-158">next to the value.</span></span>

   <span data-ttu-id="ea703-159">사용자 또는 그룹의 경우 대부분의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 사용할 수 있지만 해당 표시 이름은 결과에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="ea703-160">사용자의 경우 별표(\*)만 입력하여 사용 가능한 모든 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="ea703-161">동일한 조건의 여러 값은 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="ea703-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ea703-162">서로 다른 조건은 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ea703-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="ea703-163">**다음 사용자, 그룹 및 도메인 제외**: 정책이 적용되는 내부 받는 사람에 대한 예외를 추가하려면(받는 사람 예외) 이 옵션을 선택하고 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="ea703-164">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ea703-165">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ea703-166">설정 **페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="ea703-167">금고 알 수 없는 **맬웨어 응답**: 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="ea703-168">**Off:** 일반적으로 이 값은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="ea703-169">**모니터링**</span><span class="sxs-lookup"><span data-stu-id="ea703-169">**Monitor**</span></span>
     - <span data-ttu-id="ea703-170">**Block**: 이 값은 기본값으로, Standard 및 Strict 미리 설정 보안 정책의 [권장 값입니다.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ea703-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="ea703-171">**바꾸기**</span><span class="sxs-lookup"><span data-stu-id="ea703-171">**Replace**</span></span>
     - <span data-ttu-id="ea703-172">**동적 배달(미리 보기 기능)**</span><span class="sxs-lookup"><span data-stu-id="ea703-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="ea703-173">이러한 값은 첨부 파일 [정책 금고 설명되어 있습니다.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="ea703-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="ea703-174">**검색된** 첨부 파일이 있는 메시지 리디렉션: 리디렉션 사용 을 선택하면 지정된 전자 메일 주소 상자에 **차단,** 모니터링 또는 대체된 첨부 파일이 포함된 전자 메일 주소를 지정하여 분석 및 조사를 위해 맬웨어 첨부 파일이 포함된 메시지를 보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="ea703-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="ea703-175">표준 및 엄격한 정책 설정에 대한 권장은 리디렉션을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="ea703-176">자세한 내용은 첨부 [파일 금고 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="ea703-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="ea703-177">**검색을** 완료할 수 없는 경우(시간 제한 또는 오류) 금고 금고 첨부 파일  검색 응답 적용 : 첨부 파일 검색을 완료할 수 없는 경우에도 금고 첨부 파일 알 수 없는 맬웨어 응답이 메시지에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="ea703-178">이 옵션을 선택한 경우  항상 리디렉션 사용 을 선택하고 맬웨어 첨부 파일이 포함된 메시지를 보낼 전자 메일 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="ea703-179">그렇지 않으면 메시지가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="ea703-180">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="ea703-181">표시되는 **검토** 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="ea703-182">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ea703-183">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="ea703-184">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="ea703-185">표시되는 확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="ea703-186">Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 보기</span><span class="sxs-lookup"><span data-stu-id="ea703-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="ea703-187">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 정책 섹션에서 금고 \>  \>  \>  \> **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-187">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ea703-188">첨부 **금고** 페이지에 다음 속성이 정책 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="ea703-189">**이름**</span><span class="sxs-lookup"><span data-stu-id="ea703-189">**Name**</span></span>
   - <span data-ttu-id="ea703-190">**상태**</span><span class="sxs-lookup"><span data-stu-id="ea703-190">**Status**</span></span>
   - <span data-ttu-id="ea703-191">**우선 순위**</span><span class="sxs-lookup"><span data-stu-id="ea703-191">**Priority**</span></span>

3. <span data-ttu-id="ea703-192">이름을 클릭하여 정책을 선택하면 정책 설정이 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="ea703-193">Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 수정</span><span class="sxs-lookup"><span data-stu-id="ea703-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="ea703-194">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 정책 섹션에서 금고 \>  \>  \>  \> **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-194">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ea703-195">첨부 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ea703-196">표시되는 정책 세부 정보 플라이아웃에서 각 섹션에서 **편집** 을 선택하여 섹션 내의 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ea703-197">설정에 대한 자세한 내용은 [](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) 이 문서 앞부분의 Microsoft 365 Defender 포털을 사용하여 금고 정책 만들기 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea703-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="ea703-198">정책을 사용하도록 설정하거나 사용하지 않도록 설정하거나 정책 우선 순위를 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="ea703-199">첨부 파일 금고 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ea703-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="ea703-200">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 정책 섹션에서 금고 \>  \>  \>  \> **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-200">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ea703-201">첨부 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ea703-202">표시되는 정책 세부 정보 플라이아웃 맨 위에 다음 값 중 하나가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="ea703-203">**정책 끄기**: 정책을 켜려면 ![켜기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **켜기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="ea703-204">**정책**: 정책을 끄려면 ![끄기 아이콘](../../media/m365-cc-sc-turn-on-off-icon.png) **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="ea703-205">표시되는 확인 대화 상자에서 **켜기** 또는 **끄기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="ea703-206">정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="ea703-207">기본 정책 페이지로 돌아가면 정책의 **상태** 값이 **켜짐** 또는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="ea703-208">첨부 파일 정책의 금고 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="ea703-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="ea703-209">기본적으로 금고 첨부 파일 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="ea703-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ea703-210">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="ea703-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ea703-211">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ea703-212">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ea703-213">금고 첨부 파일 정책은 처리되는 순서대로 표시됩니다(첫 번째  정책의 우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="ea703-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="ea703-214">**참고:** Microsoft 365 Defender 포털에서 첨부 파일 정책을 만든 금고 정책의 우선 순위만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="ea703-215">PowerShell에서 안전한 첨부 파일 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="ea703-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ea703-216">정책의 우선 순위를 변경하려면 정책 속성에서 **우선 순위를 높이** 거나 **우선 순위를 낮춥** 니다(Microsoft 365 Defender 포털에서 **우선 순위** 번호를 직접 수정할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="ea703-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="ea703-217">정책의 우선 순위를 변경하는 것은 여러 정책이 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ea703-218">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 정책 섹션에서 금고 \>  \>  \>  \> **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-218">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ea703-219">첨부 **금고** 페이지에서 이름을 클릭하여 목록에서 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="ea703-220">정책 세부 정보 플라이아웃이 나타나면 현재 우선  순위 값  및 정책 수에 따라 우선 순위 늘리기 또는 우선 순위 감소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="ea703-221">우선 순위  값이 **0인** 정책에는 우선 순위 감소 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="ea703-222">우선 순위 값이 가장 **낮은** 정책(예: **3)에는** 우선 순위 늘리기 옵션만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="ea703-223">세 개 이상의 정책이 있는 경우 우선 순위가 가장  높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 옵션을 모두 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="ea703-224">![우선순위 아이콘](../../media/m365-cc-sc-increase-icon.png) **우선순위** 또는 ![우선순위 아이콘](../../media/m365-cc-sc-decrease-icon.png) **우선순위** 를 클릭하여 **우선순위** 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="ea703-225">작업을 마쳤으면 정책 세부 정보 플라이아웃에서 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="ea703-226">Microsoft 365 Defender 포털을 사용하여 첨부 파일 금고 제거</span><span class="sxs-lookup"><span data-stu-id="ea703-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="ea703-227">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 정책 섹션에서 금고 \>  \>  \>  \> **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-227">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="ea703-228">첨부 **금고** 페이지에서 정책 이름을 클릭하여 목록에서 사용자 지정 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="ea703-229">표시되는 정책 세부 정보 플라이아웃의 맨 위에서 ![추가 작업 아이콘](../../media/m365-cc-sc-more-actions-icon.png)**추가 작업**\>![정책 삭제 아이콘](../../media/m365-cc-sc-delete-icon.png)**정책 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="ea703-230">확인 대화 상자가 나타나면 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="ea703-231">PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 금고 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ea703-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="ea703-232">앞서 설명한 금고 첨부 파일 정책은 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="ea703-233">PowerShell에서는 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙의 차이점이 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="ea703-234">**\* -SafeAttachmentPolicy** cmdlet을 사용하여 안전한 첨부 파일 정책을 관리하고 **\* -SafeAttachmentRule** cmdlet을 사용하여 안전한 첨부 파일 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="ea703-235">PowerShell에서 먼저 안전한 첨부 파일 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 안전한 첨부 파일 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ea703-236">PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙의 설정을 별도로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="ea703-237">PowerShell에서 안전한 첨부 파일 정책을 제거하면 해당 안전 첨부 파일 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="ea703-238">PowerShell을 사용하여 첨부 파일 금고 만들기</span><span class="sxs-lookup"><span data-stu-id="ea703-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="ea703-239">PowerShell에서 금고 첨부 파일 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ea703-240">안전한 첨부 파일 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="ea703-241">규칙이 적용되는 안전한 첨부 파일 정책을 지정하는 안전한 첨부 파일 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="ea703-242">**참고:**</span><span class="sxs-lookup"><span data-stu-id="ea703-242">**Notes**:</span></span>

- <span data-ttu-id="ea703-243">새 안전한 첨부 파일 규칙을 만들고 연결되지 않은 기존 안전 첨부 파일 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="ea703-244">안전한 첨부 파일 규칙은 두 개 이상의 안전한 첨부 파일 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="ea703-245">정책을 만든 후까지 Microsoft 365 Defender 포털에서 사용할 수 없는 PowerShell의 새 안전 첨부 파일 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="ea703-246">새 정책을 사용하지 않도록 `$false` **설정합니다(New-SafeAttachmentRule** cmdlet에서 사용).</span><span class="sxs-lookup"><span data-stu-id="ea703-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="ea703-247"> _\<Number\>_ **New-SafeAttachmentRule** cmdlet에서 만들 때 정책의 우선 순위( 우선 순위)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea703-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="ea703-248">PowerShell에서 만든 새 안전한 첨부 파일 정책은 안전한 첨부 파일 규칙에 정책을 할당할 때까지 Microsoft 365 Defender 포털에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="ea703-249">1단계: PowerShell을 사용하여 안전한 첨부 파일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ea703-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="ea703-250">안전한 첨부 파일 정책을 만들 수 있도록 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="ea703-251">이 예에서는 다음 값을 가지는 Contoso All이라는 안전한 첨부 파일 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="ea703-252">문서 검색을 금고 맬웨어가 포함된 것으로 확인된 메시지를 차단합니다(Action  매개 변수를 사용하지 않습니다. 기본값은 `Block` 입니다).</span><span class="sxs-lookup"><span data-stu-id="ea703-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="ea703-253">리디렉션이 사용하도록 설정되어 있으며 맬웨어가 포함된 것으로 확인된 메시지는 분석 및 조사를 위해 sec-ops@contoso.com 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="ea703-254">금고 첨부 파일 검색을 사용할 수 없는 경우 메시지를 배달하지 _않습니다(ActionOnError_ 매개 변수를 사용하지 않습니다. 기본값은 `$true` 입니다).</span><span class="sxs-lookup"><span data-stu-id="ea703-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="ea703-255">구문과 매개 변수에 대한 자세한 내용은 [New-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ea703-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="ea703-256">2단계: PowerShell을 사용하여 안전한 첨부 파일 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="ea703-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="ea703-257">안전한 첨부 파일 규칙을 만들 수 있도록 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="ea703-258">이 예에서는 다음 조건을 통해 Contoso All이라는 안전한 첨부 파일 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="ea703-259">이 규칙은 Contoso All이라는 안전한 첨부 파일 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="ea703-260">이 규칙은 도메인의 모든 받는 사람에게 contoso.com 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="ea703-261">Priority 매개 변수를  사용하지 않을 것이기 때문에 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="ea703-262">이 규칙은 사용하도록 설정됩니다(Enabled  매개 변수를 사용하지 않습니다. 기본값은 `$true` 입니다).</span><span class="sxs-lookup"><span data-stu-id="ea703-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="ea703-263">구문과 매개 변수에 대한 자세한 내용은 [New-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/new-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ea703-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="ea703-264">PowerShell을 사용하여 안전한 첨부 파일 정책 보기</span><span class="sxs-lookup"><span data-stu-id="ea703-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="ea703-265">기존의 안전한 첨부 파일 정책을 보시고 다음 구문을 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ea703-266">이 예에서는 모든 안전한 첨부 파일 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="ea703-267">이 예에서는 Contoso Executives라는 안전 첨부 파일 정책에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ea703-268">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ea703-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="ea703-269">PowerShell을 사용하여 안전한 첨부 파일 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="ea703-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="ea703-270">기존의 안전한 첨부 파일 규칙을 보시고 다음 구문을 사용하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ea703-271">이 예에서는 모든 안전한 첨부 파일 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="ea703-272">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="ea703-273">이 예에서는 Contoso Executives라는 안전한 첨부 파일 규칙에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="ea703-274">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeAttachmentRule 을 참조하십시오.](/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ea703-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="ea703-275">PowerShell을 사용하여 안전한 첨부 파일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="ea703-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="ea703-276">PowerShell에서 안전한 첨부 파일 정책의 이름을 다시 설정할 수 **없습니다(Set-SafeAttachmentPolicy** cmdlet에는 _Name_ 매개 변수가 없음).</span><span class="sxs-lookup"><span data-stu-id="ea703-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ea703-277">금고 포털에서 Microsoft 365 Defender 정책의 이름을 바에는 안전한 첨부 파일 규칙의 이름만 _바입니다._</span><span class="sxs-lookup"><span data-stu-id="ea703-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="ea703-278">그렇지 않으면 이 문서 앞부분의 [1단계: PowerShell을](#step-1-use-powershell-to-create-a-safe-attachment-policy) 사용하여 안전한 첨부 파일 정책 만들기 섹션에 설명된 대로 안전한 첨부 파일 정책을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="ea703-279">안전한 첨부 파일 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ea703-280">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/set-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ea703-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="ea703-281">PowerShell을 사용하여 안전한 첨부 파일 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="ea703-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="ea703-282">PowerShell에서 안전한 첨부 파일 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용되지 않는 규칙을 만들 수 있는 _Enabled_ 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ea703-283">기존 안전 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="ea703-284">그렇지 않으면 이 문서 앞부분의 [2단계: PowerShell을](#step-2-use-powershell-to-create-a-safe-attachment-rule) 사용하여 안전한 첨부 파일 규칙 만들기 섹션에 설명된 대로 규칙을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="ea703-285">안전한 첨부 파일 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ea703-286">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ea703-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="ea703-287">PowerShell을 사용하여 안전한 첨부 파일 규칙을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="ea703-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="ea703-288">PowerShell에서 안전한 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하면 전체 금고 첨부 파일 정책(안전한 첨부 파일 규칙 및 할당된 안전한 첨부 파일 정책)을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="ea703-289">PowerShell에서 안전한 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="ea703-290">이 예에서는 Marketing Department라는 안전 첨부 파일 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ea703-291">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ea703-292">구문과 매개 변수에 대한 자세한 내용은 [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) 및 [Disable-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ea703-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="ea703-293">PowerShell을 사용하여 안전한 첨부 파일 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="ea703-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="ea703-294">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-294">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ea703-295">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-295">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ea703-296">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-296">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ea703-297">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-297">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ea703-298">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-298">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ea703-299">PowerShell에서 안전한 첨부 파일 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ea703-300">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-300">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ea703-301">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="ea703-301">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ea703-302">**참고:** 새 규칙을 만들 때 새 규칙의 우선  순위를 설정하기 위해 **New-SafeAttachmentRule** cmdlet에서 Priority 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="ea703-303">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentRule을 참조하십시오.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ea703-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="ea703-304">PowerShell을 사용하여 안전한 첨부 파일 정책 제거</span><span class="sxs-lookup"><span data-stu-id="ea703-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="ea703-305">PowerShell을 사용하여 안전한 첨부 파일 정책을 제거하면 해당 안전 첨부 파일 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="ea703-306">PowerShell에서 안전한 첨부 파일 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ea703-307">이 예에서는 Marketing Department라는 안전 첨부 파일 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ea703-308">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeAttachmentPolicy를 참조하십시오.](/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="ea703-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="ea703-309">PowerShell을 사용하여 안전한 첨부 파일 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="ea703-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="ea703-310">PowerShell을 사용하여 안전한 첨부 파일 규칙을 제거하면 해당 안전 첨부 파일 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="ea703-311">PowerShell에서 안전한 첨부 파일 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="ea703-312">이 예에서는 Marketing Department라는 안전 첨부 파일 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="ea703-313">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeAttachmentRule 을 참조하십시오.](/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="ea703-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ea703-314">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="ea703-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="ea703-315">첨부 파일 정책을 만들거나 수정하거나 제거한 금고 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="ea703-316">Microsoft 365 Defender 포털에서 전자 메일 **&** 정책 & 규칙 위협 정책 페이지 정책 섹션에서 금고 \>  \>  \>  \> **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-316">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="ea703-317">정책 목록, 해당 **상태 값** 및 우선 순위 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea703-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ea703-318">자세한 내용을 보려면 이름을 클릭하여 목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea703-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="ea703-319">PowerShell Exchange Online PowerShell Exchange Online Protection PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="ea703-320">첨부 파일이 금고 검사하는지 확인을 위해 사용 가능한 Defender에서 보고서의 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea703-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="ea703-321">자세한 내용은 Office 365 포털에서 [Defender에](view-reports-for-mdo.md) 대한 보고서 Office 365 [탐색기 Microsoft 365 Defender 참조하세요.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="ea703-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
