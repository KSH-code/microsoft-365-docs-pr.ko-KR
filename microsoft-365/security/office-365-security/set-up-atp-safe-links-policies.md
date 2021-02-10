---
title: Office 365용 Microsoft Defender에서 안전한 링크 정책 설정
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
description: 관리자는 Office 365용 Microsoft Defender에서 안전한 링크 정책 및 전역 안전 링크 설정을 보고, 만들고, 수정하고, 삭제하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71ea33f1f6fbebf6d87a4b42ad3bd96a60597b90
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166270"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="819d3-103">Office 365용 Microsoft Defender에서 안전한 링크 정책 설정</span><span class="sxs-lookup"><span data-stu-id="819d3-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="819d3-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="819d3-104">**Applies to**</span></span>
- [<span data-ttu-id="819d3-105">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="819d3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="819d3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="819d3-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="819d3-107">이 문서는 [Office 365용 Microsoft Defender](office-365-atp.md)가 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="819d3-108">Outlook의 Safelinks에 대한 정보를 찾고 있는 가정용 사용자인 경우 고급 보안 [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="819d3-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="819d3-109">안전한 링크는 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색을 제공하는 [Office 365용 Microsoft Defender의](office-365-atp.md) 기능으로, 전자 메일 메시지 및 다른 위치에서 URL 및 링크의 클릭 확인 시간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="819d3-110">자세한 내용은 [Office 365용 Microsoft Defender의 안전한 링크를 참조하세요.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="819d3-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="819d3-111">기본 제공 또는 기본 안전 링크 정책이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="819d3-112">URL을 안전한 링크로 검색하려면 이 문서에 설명된 하나 이상의 안전 링크 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="819d3-113">안전한 링크 정책 외부에서 안전한 링크 **보호에 대한** 전역 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="819d3-114">자세한 내용은 [Office 365용 Microsoft Defender에서 안전한](configure-global-settings-for-safe-links.md)링크에 대한 전역 설정 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="819d3-115">보안 & 준수 센터 또는 PowerShell에서 안전한 링크 정책을 구성할 수 있습니다(Exchange Online에 사서함이 있는 적격 Microsoft 365 조직, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell, Office 365 추가 기능 구독용 Microsoft Defender 사용).</span><span class="sxs-lookup"><span data-stu-id="819d3-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="819d3-116">안전한 링크 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="819d3-117">**안전한** 링크 정책: 안전한 링크 보호를 켜고, 실시간 URL 검색을 켜고, 메시지를 배달하기 전에 실시간 검색이 완료될 때까지 기다릴지 여부를 지정하고, 내부 메시지 검색을 켜고, URL에서 사용자 클릭을 추적할지 여부를 지정하고, 사용자가 휴지통을 원래 URL로 클릭하도록 허용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="819d3-118">**안전한 링크 규칙:** 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="819d3-119">보안 및 준수 센터에서 안전한 링크 & 경우 이러한 두 요소의 차이는 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="819d3-120">안전한 링크 정책을 만들면 실제로 동일한 이름을 사용하여 안전한 링크 규칙과 연결된 안전한 링크 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="819d3-121">안전한 링크 정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 안전한 링크 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="819d3-122">다른 모든 설정은 연결된 안전한 링크 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="819d3-123">안전한 링크 정책을 제거하면 안전한 링크 규칙 및 연결된 안전한 링크 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="819d3-124">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="819d3-125">자세한 내용은 이 문서 부분의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 사용하여 안전한 링크 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="819d3-126">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="819d3-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="819d3-127"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="819d3-128">안전한 링크 페이지로 직접 **이동하기** 위해 다음을 <https://protection.office.com/safelinksv2> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="819d3-129">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="819d3-130">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="819d3-131">이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="819d3-132">안전한 링크 정책을 만들고 수정하고 삭제하려면 Security & Compliance  **Center에서** 조직 관리 또는 보안 관리자 역할 그룹의 구성원이자  Exchange Online의 조직 관리 역할 그룹의 구성원이 되거나 삭제해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="819d3-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="819d3-133">안전 링크 정책에 대한 읽기 전용 액세스 권한을 사용하려면 전역 읽기 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나, </span><span class="sxs-lookup"><span data-stu-id="819d3-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="819d3-134">자세한 내용은 Exchange Online의 보안 및 & [및](permissions-in-the-security-and-compliance-center.md) 사용 권한을 [참조하세요.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="819d3-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="819d3-135">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="819d3-136">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-136">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  <span data-ttu-id="819d3-137">.</span><span class="sxs-lookup"><span data-stu-id="819d3-137">.</span></span> <span data-ttu-id="819d3-138">- [Exchange Online의](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 보기 **전용 조직** 관리 역할 그룹은 기능에 대한 읽기 전용 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-138">- The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="819d3-139">안전한 링크 정책에 대한 권장 설정은 안전 링크 정책 [설정을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="819d3-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="819d3-140">새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="819d3-141">[Office 365용 Microsoft Defender에](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)새로운 기능이 지속적으로 추가되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-141">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="819d3-142">새 기능이 추가될 때 기존 안전 링크 정책을 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="819d3-143">보안 및 & 센터를 사용하여 안전한 링크 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="819d3-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="819d3-144">보안 및 준수 센터에서 사용자 지정 안전 링크 정책을 & 동일한 이름을 사용하여 안전한 링크 규칙과 연결된 안전한 링크 정책을 동시에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="819d3-145">보안 및 & 센터에서 **위협 관리** \>  \> **정책 ATP 안전한 링크로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="819d3-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="819d3-146">안전한 링크 **페이지에서** 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="819d3-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="819d3-147">새 **안전 링크 정책 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="819d3-148">정책 **이름 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="819d3-149">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="819d3-150">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="819d3-151">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="819d3-152">나타나는 **설정** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="819d3-153">**메시지의** 알 수 없는 악의적인 URL에  대한 작업 선택: 전자 메일 메시지의 링크에 대해 안전한 링크 보호를 사용하도록 설정하려면 설정 선택</span><span class="sxs-lookup"><span data-stu-id="819d3-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="819d3-154">**Microsoft Teams 내에서** 알 수 없는 URL 또는 악의적인 URL에 대한 작업을 선택합니다. 사용을 선택하여 Teams의 링크에 대해 안전한 링크 보호를 사용하도록 설정하세요. </span><span class="sxs-lookup"><span data-stu-id="819d3-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="819d3-155">**파일을 지정하는** 의심스러운 링크 및 링크에 대한 실시간 URL 검색 적용: 전자 메일 메시지의 링크를 실시간으로 검색할 수 있도록 설정하려면 이 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="819d3-156">**메시지를 배달하기** 전에 URL 검색이 완료될 때까지 기다렸다가 다음 설정을 선택합니다. 메시지를 배달하기 전에 실시간 URL 검색이 완료될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="819d3-157">**조직 내에서** 전송된 전자 메일 메시지에 안전한 링크 적용: 내부 보낸 사람과 내부 받는 사람 간의 메시지에 안전 링크 정책을 적용하려면 이 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="819d3-158">**사용자 클릭 추적** 안 하세요. 추적 사용자가 전자 메일 메시지의 URL을 클릭할 수 있도록 설정하려면 이 설정을 선택하지 않은 것으로 하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="819d3-159">**사용자가 원래 URL을 클릭할** 수 있도록 허용하지 않습니다. 사용자가 경고 페이지에서 원래 URL을 클릭하지 못하도록 차단하려면 이 설정을 [선택합니다.](atp-safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="819d3-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="819d3-160">**다음 URL을** 다시 덮어치지 않습니다. 그렇지 않으면 안전한 링크로 차단되는 지정된 URL에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="819d3-161">상자에 원하는 URL 또는 값을 입력한 다음</span><span class="sxs-lookup"><span data-stu-id="819d3-161">In the box, type the URL or value that you want, and then click</span></span> ![단추 추가 아이콘](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="819d3-163">.</span><span class="sxs-lookup"><span data-stu-id="819d3-163">.</span></span>

     <span data-ttu-id="819d3-164">기존 항목을 제거하려면 해당 항목을 선택하고</span><span class="sxs-lookup"><span data-stu-id="819d3-164">To remove an existing entry, select it and then click</span></span> ![삭제 단추 아이콘](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="819d3-166">.</span><span class="sxs-lookup"><span data-stu-id="819d3-166">.</span></span>

     <span data-ttu-id="819d3-167">항목 구문은 "다음 URL을 다시 입력하지 않습니다." 목록에 대한 항목 구문을 [참조하세요.](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="819d3-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="819d3-168">이러한 설정에 대한 자세한 내용은 전자 메일 메시지에 대한 [안전한](atp-safe-links.md#safe-links-settings-for-email-messages) 링크 설정 및 Microsoft Teams의 안전한 링크 설정을 [참조하세요.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="819d3-168">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="819d3-169">표준 및 엄격 정책 설정에 대한 권장 값은 안전 링크 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="819d3-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="819d3-170">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="819d3-171">적용 **대상** 페이지가 나타나면 정책이 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="819d3-172">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="819d3-173">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="819d3-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="819d3-174">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="819d3-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="819d3-175">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="819d3-175">Click **Add a condition**.</span></span> <span data-ttu-id="819d3-176">나타나는 드롭다운에서 적용된 조건(다음의 **경우)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="819d3-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="819d3-177">**받는 사람:** 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="819d3-178">**받는 사람이 다음의 구성원인** 경우 조직에서 하나 이상의 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="819d3-179">**받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="819d3-180">조건을 선택하면 다음 상자와 함께 해당 **드롭다운이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="819d3-181">상자를 클릭하고 선택할 값 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="819d3-182">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="819d3-183">값을 더 추가하려면 상자의 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="819d3-184">개별 항목을 제거하려면  값에서 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="819d3-185">전체 조건을 제거하려면 **조건에서** 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="819d3-186">조건을 더 추가하려면 **조건** 추가를 클릭하고 적용된 경우 나머지 **값을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="819d3-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="819d3-187">예외를 추가하려면 **조건** 추가를 클릭하고 다음의 예외를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="819d3-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="819d3-188">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="819d3-189">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="819d3-190">나타나는 **설정** 검토 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="819d3-191">각 **설정에서** 편집을 클릭하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="819d3-192">완료되면 마쳤습니다. </span><span class="sxs-lookup"><span data-stu-id="819d3-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="819d3-193">보안 및 & 센터를 사용하여 안전한 링크 정책 보기</span><span class="sxs-lookup"><span data-stu-id="819d3-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="819d3-194">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP 안전한 링크로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="819d3-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="819d3-195">안전한 링크 **페이지에서** 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="819d3-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="819d3-196">정책 세부 정보가 플라이아웃에 표시</span><span class="sxs-lookup"><span data-stu-id="819d3-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="819d3-197">보안 및 & 센터를 사용하여 안전한 링크 정책 수정</span><span class="sxs-lookup"><span data-stu-id="819d3-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="819d3-198">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP 안전한 링크로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="819d3-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="819d3-199">안전한 링크 **페이지에서** 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="819d3-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="819d3-200">나타나는 정책 세부 정보에서 정책 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="819d3-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="819d3-201">플라이아웃에서 사용할 수 있는 설정은 보안 및 준수 센터를 사용하여 안전한 링크 정책 섹션을 & 설명된 설정과 [동일합니다.](#use-the-security--compliance-center-to-create-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="819d3-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="819d3-202">정책을 사용 또는 사용하지 않도록 설정하거나 정책 우선 순위 순서를 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="819d3-203">안전한 링크 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="819d3-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="819d3-204">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP 안전한 링크로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="819d3-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="819d3-205">상태 열의 **값을** 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="819d3-206">토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-206">Move the toggle to the left to disable the policy:</span></span> ![정책 끄기](../../media/scc-toggle-off.png)<span data-ttu-id="819d3-208">.</span><span class="sxs-lookup"><span data-stu-id="819d3-208">.</span></span>

   - <span data-ttu-id="819d3-209">토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-209">Move the toggle to the right to enable the policy:</span></span> ![정책 켜기](../../media/scc-toggle-on.png)<span data-ttu-id="819d3-211">.</span><span class="sxs-lookup"><span data-stu-id="819d3-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="819d3-212">안전한 링크 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="819d3-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="819d3-213">기본적으로 안전한 링크 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="819d3-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="819d3-214">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="819d3-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="819d3-215">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="819d3-216">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="819d3-217">안전한 링크 정책은 처리되는 순서대로 표시됩니다(첫 번째  정책의 우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="819d3-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="819d3-218">보안 & 준수 센터에서는 안전한 링크 정책의 우선 순위를 만든 후에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="819d3-219">PowerShell에서 안전한 링크 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="819d3-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="819d3-220">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="819d3-221">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP 안전한 링크로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="819d3-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="819d3-222">안전한 링크 **페이지에서** 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="819d3-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="819d3-223">정책 세부 정보가 나타나는 플라이아웃에서 사용 가능한 우선 순위 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="819d3-224">우선 순위 값이  **0인** 안전 링크 정책에는 우선 순위 감소 단추만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="819d3-225">우선 순위 값이 가장  낮은 안전 링크 정책(예: **3)에는** 우선 순위 늘리기 단추만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="819d3-226">안전 링크 정책이 세 개 이상 있는 경우 우선 순위가  가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 단추를 모두 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="819d3-227">우선 **순위 늘리기 또는** 우선 순위 **감소를** 클릭하여 우선 순위 값을 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="819d3-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="819d3-228">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="819d3-229">보안 및 & 센터를 사용하여 안전한 링크 정책 제거</span><span class="sxs-lookup"><span data-stu-id="819d3-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="819d3-230">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP 안전한 링크로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="819d3-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="819d3-231">안전한 링크 **페이지에서** 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="819d3-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="819d3-232">정책 세부 정보가 나타나는 플라이아웃에서 정책 삭제를  클릭한 다음 나타나는 경고 대화 상자에서 예를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="819d3-233">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 안전한 링크 정책 구성</span><span class="sxs-lookup"><span data-stu-id="819d3-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="819d3-234">앞서 설명한 바와 같이 안전한 링크 정책은 안전한 링크 정책과 안전한 링크 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="819d3-235">PowerShell에서 안전한 링크 정책과 안전한 링크 규칙의 차이는 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="819d3-236">**\* -SafeLinksPolicy** cmdlet을 사용하여 안전한 링크 정책을 관리하고 **\* -SafeLinksRule** cmdlet을 사용하여 안전한 링크 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="819d3-237">PowerShell에서 먼저 안전한 링크 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 안전한 링크 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="819d3-238">PowerShell에서 안전한 링크 정책 및 안전한 링크 규칙의 설정을 개별적으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="819d3-239">PowerShell에서 안전한 링크 정책을 제거하면 해당 안전 링크 규칙이 자동으로 제거되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="819d3-240">PowerShell을 사용하여 안전한 링크 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="819d3-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="819d3-241">PowerShell에서 안전한 링크 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="819d3-242">안전한 링크 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="819d3-243">규칙이 적용되는 안전한 링크 정책을 지정하는 안전한 링크 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="819d3-244">새 안전한 링크 규칙을 만들고 연결되지 않은 기존 안전한 링크 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="819d3-245">안전한 링크 규칙은 두 개 이상의 안전한 링크 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="819d3-246">정책을 만든 후 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새 안전한 링크 정책에 대해 다음 설정을 구성할 수 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="819d3-247">새 정책을 사용할 수 `$false` **없습니다(New-SafeLinksRule** cmdlet에서 사용).</span><span class="sxs-lookup"><span data-stu-id="819d3-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="819d3-248"> _\<Number\>_ **New-SafeLinksRule** cmdlet에서 만들기 중 정책의 우선 순위(우선 순위)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="819d3-249">PowerShell에서 만든 새 안전한 링크 정책은 안전한 링크 규칙에 정책을 할당할 때까지 보안 & 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="819d3-250">1단계: PowerShell을 사용하여 안전한 링크 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="819d3-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="819d3-251">안전한 링크 정책을 만들 수 있도록 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="819d3-252">_DoNotRewriteUrls_ 매개 변수에 사용할 항목 구문에 대한 자세한 내용은 ["다음 URL을](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)다시 입력하지 않습니다." 목록에 대한 항목 구문을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="819d3-253">**Set-SafeLinksPolicy** cmdlet을 사용하여 기존 안전 링크 정책을 수정할 때 _DoNotRewriteUrls_ 매개 변수에 사용할 수 있는 추가 구문은 [PowerShell을](#use-powershell-to-modify-safe-links-policies) 사용하여 이 문서의 부분에 있는 안전한 링크 정책 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="819d3-254">이 예에서는 다음 값을 가지는 Contoso All이라는 안전한 링크 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="819d3-255">전자 메일 메시지에서 URL 검색 및 다시 덮기 기능을 켜세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="819d3-256">Teams에서 URL 검색을 켜세요(TAP 미리 보기만 해당).</span><span class="sxs-lookup"><span data-stu-id="819d3-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="819d3-257">파일을 포인트로 하는 클릭된 링크를 포함하여 클릭한 URL의 실시간 검색을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="819d3-258">URL 검색이 완료될 때까지 기다렸다가 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="819d3-259">내부 메시지에 대해 URL 검색 및 다시 덮기 기능을 켜세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="819d3-260">안전한 링크 보호와 관련된 사용자 클릭을 _추적합니다(DoNotTrackUserClicks_ 매개 변수를 사용하지 않습니다. 기본값은 $false, 즉 사용자 클릭이 추적됩니다).</span><span class="sxs-lookup"><span data-stu-id="819d3-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="819d3-261">사용자가 원래 URL을 클릭할 수 있도록 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="819d3-262">구문과 매개 변수에 대한 자세한 내용은 [New-SafeLinksPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="819d3-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="819d3-263">2단계: PowerShell을 사용하여 안전한 링크 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="819d3-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="819d3-264">안전한 링크 규칙을 만들 수 있도록 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="819d3-265">이 예에서는 다음 조건을 통해 Contoso All이라는 안전한 링크 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="819d3-266">이 규칙은 Contoso All이라는 안전한 링크 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="819d3-267">이 규칙은 도메인의 모든 받는 사람에게 contoso.com 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="819d3-268">Priority 매개 변수를  사용하지 않는 경우 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="819d3-269">이 규칙은 사용하도록 설정됩니다(Enabled  매개 변수를 사용하지 않습니다. 기본값은 `$true` ).</span><span class="sxs-lookup"><span data-stu-id="819d3-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="819d3-270">구문과 매개 변수에 대한 자세한 내용은 [New-SafeLinksRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="819d3-270">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="819d3-271">PowerShell을 사용하여 안전한 링크 정책 보기</span><span class="sxs-lookup"><span data-stu-id="819d3-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="819d3-272">기존의 안전한 링크 정책을 보시고 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="819d3-273">이 예에서는 모든 안전한 링크 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="819d3-274">이 예에서는 Contoso Executives라는 안전한 링크 정책에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="819d3-275">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeLinksPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="819d3-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="819d3-276">PowerShell을 사용하여 안전한 링크 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="819d3-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="819d3-277">기존의 안전한 링크 규칙을 보시고 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="819d3-278">이 예에서는 모든 안전한 링크 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="819d3-279">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="819d3-280">이 예에서는 Contoso Executives라는 안전한 링크 규칙에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="819d3-281">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeLinksRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="819d3-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="819d3-282">PowerShell을 사용하여 안전한 링크 정책 수정</span><span class="sxs-lookup"><span data-stu-id="819d3-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="819d3-283">PowerShell에서 안전한 링크 정책의 이름을 다시 설정할 수 **없습니다(Set-SafeLinksPolicy** cmdlet에는 Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="819d3-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="819d3-284">보안 및 준수 센터에서 안전한 링크 정책의 이름을 & 안전한 링크 규칙의 이름만 다시 _고치게 됩니다._</span><span class="sxs-lookup"><span data-stu-id="819d3-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="819d3-285">PowerShell에서 안전한 링크 정책을 수정하기 위한 유일한 추가 고려 사항은 _DoNotRewriteUrls_ 매개 변수에 사용할 수 있는 구문입니다("다음 URL을 다시 덮지 [않습니다." 목록).](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="819d3-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="819d3-286">기존 항목을 대체할 값을 추가하기 위해 다음 구문을 `"Entry1","Entry2,..."EntryN"` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="819d3-287">다른 기존 항목에 영향을 주지 않고 값을 추가하거나 제거하려면 다음 구문을 사용합니다. `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="819d3-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="819d3-288">그렇지 않으면 이 문서 앞부분의 PowerShell을 사용하여 안전한 링크 정책 섹션을 만드는 [1단계에](#step-1-use-powershell-to-create-a-safe-links-policy) 설명된 대로 안전한 링크 정책을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="819d3-289">안전한 링크 정책을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="819d3-290">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="819d3-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="819d3-291">PowerShell을 사용하여 안전한 링크 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="819d3-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="819d3-292">PowerShell에서 안전한 링크 규칙을 수정할 때 사용할 수 없는 유일한 설정은 _사용되지_ 않는 규칙을 만들 수 있는 Enabled 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="819d3-293">기존 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="819d3-294">그렇지 않으면 [2단계: PowerShell을](#step-2-use-powershell-to-create-a-safe-links-rule) 사용하여 이 문서의 앞부분에서 설명한 대로 규칙을 만들 때 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="819d3-295">안전한 링크 규칙을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="819d3-296">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="819d3-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="819d3-297">PowerShell을 사용하여 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="819d3-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="819d3-298">PowerShell에서 안전한 링크 규칙을 설정하거나 사용하지 않도록 설정하면 전체 안전 링크 정책(안전한 링크 규칙 및 할당된 안전한 링크 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="819d3-299">PowerShell에서 안전한 링크 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="819d3-300">이 예에서는 Marketing Department라는 안전한 링크 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="819d3-301">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="819d3-302">구문과 매개 변수에 대한 자세한 내용은 [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 및 [Disable-SafeLinksRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="819d3-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="819d3-303">PowerShell을 사용하여 안전한 링크 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="819d3-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="819d3-304">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="819d3-305">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="819d3-306">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="819d3-307">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="819d3-308">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="819d3-309">PowerShell에서 안전한 링크 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="819d3-310">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-310">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="819d3-311">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="819d3-311">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="819d3-312">새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-SafeLinksRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="819d3-313">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeLinksRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="819d3-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="819d3-314">PowerShell을 사용하여 안전한 링크 정책 제거</span><span class="sxs-lookup"><span data-stu-id="819d3-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="819d3-315">PowerShell을 사용하여 안전한 링크 정책을 제거하면 해당 안전 링크 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="819d3-316">PowerShell에서 안전한 링크 정책을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="819d3-317">이 예에서는 Marketing Department라는 안전한 링크 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="819d3-318">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeLinksPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="819d3-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="819d3-319">PowerShell을 사용하여 안전한 링크 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="819d3-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="819d3-320">PowerShell을 사용하여 안전한 링크 규칙을 제거하면 해당 안전한 링크 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="819d3-321">PowerShell에서 안전한 링크 규칙을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="819d3-322">이 예에서는 Marketing Department라는 안전한 링크 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="819d3-323">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeLinksRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="819d3-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="819d3-324">안전한 링크가 메시지를 검사하는지 확인을 위해 사용 가능한 Microsoft Defender for Office 365 보고서를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="819d3-325">자세한 내용은 보안 및 준수 센터에서 [Office 365용 Defender](view-reports-for-atp.md) [및 탐색기 사용에 대한 & 참조하세요.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="819d3-325">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="819d3-326">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="819d3-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="819d3-327">안전한 링크 정책을 성공적으로 만들거나 수정 또는 제거한 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="819d3-328">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP 안전한 링크로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="819d3-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="819d3-329">정책 목록, 정책  상태 값 및 **우선** 순위 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="819d3-330">자세한 내용을 확인하려면 목록에서 정책을 선택하고 플라이아웃에서 세부 정보를 하세요.</span><span class="sxs-lookup"><span data-stu-id="819d3-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="819d3-331">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="819d3-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
