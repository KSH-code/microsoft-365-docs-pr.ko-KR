---
title: Office 365용 Defender에서 안전한 링크 설정에 대한 전역 설정 구성
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Office 365용 Microsoft Defender에서 안전한 링크에 대한 전역 설정(Office 365 앱에 대한 '다음 URL 차단' 목록 및 보호)을 보고 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165730"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c19bf-103">Office 365용 Microsoft Defender에서 안전한 링크에 대한 전역 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c19bf-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c19bf-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="c19bf-104">**Applies to**</span></span>
- [<span data-ttu-id="c19bf-105">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="c19bf-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c19bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c19bf-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="c19bf-107">이 문서는 [Office 365용 Microsoft Defender](office-365-atp.md)가 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="c19bf-108">Outlook의 Safelinks에 대한 정보를 찾고 있는 가정용 사용자는 고급 보안 [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="c19bf-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="c19bf-109">안전한 링크는 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색을 제공하는 [Office 365용 Microsoft Defender의](office-365-atp.md) 기능으로, 전자 메일 메시지 및 기타 위치에서 URL 및 링크의 클릭 확인 시간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="c19bf-110">자세한 내용은 [Office 365용 Microsoft Defender의 안전한 링크를 참조하세요.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="c19bf-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="c19bf-111">안전한 링크 정책에서 대부분의 안전 링크 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="c19bf-112">자세한 내용은 [Office 365용 Microsoft Defender에서 안전한](set-up-atp-safe-links-policies.md)링크 정책 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="c19bf-113">그러나 안전한 링크는 모든 활성 안전 링크 정책에 포함된 모든 사용자에게 적용되는 전역 설정도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="c19bf-114">이러한 전역 설정 영역:</span><span class="sxs-lookup"><span data-stu-id="c19bf-114">These global settings area:</span></span>

- <span data-ttu-id="c19bf-115">다음 **URL 차단 목록**</span><span class="sxs-lookup"><span data-stu-id="c19bf-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="c19bf-116">자세한 내용은 안전한 링크에 [대한 "다음 URL 차단" 목록을 참조하세요.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="c19bf-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="c19bf-117">Office 365 앱에 대한 안전한 링크 보호.</span><span class="sxs-lookup"><span data-stu-id="c19bf-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="c19bf-118">자세한 내용은 [Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps)앱에 대한 안전한 링크 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="c19bf-119">보안 & 준수 센터 또는 PowerShell에서 전역 안전 링크 설정을 구성할 수 있습니다(Exchange Online에 사서함이 있는 적격 Microsoft 365 조직, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell, Office 365 추가 기능 구독용 Microsoft Defender 사용).</span><span class="sxs-lookup"><span data-stu-id="c19bf-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c19bf-120">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c19bf-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c19bf-121">안전 링크에 대한 전역 설정에서 제공하는 기능은 활성 안전 링크 정책에 포함된 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="c19bf-122">기본 제공 또는 기본 안전 링크 정책이 있으므로 이러한 전역 설정이 활성화될 수 있도록 안전 링크 정책을 하나 이상 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="c19bf-123">자세한 내용은 [Office 365용 Microsoft Defender에서 안전한](set-up-atp-safe-links-policies.md)링크 정책 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="c19bf-124"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c19bf-125">안전한 링크 페이지로 직접 **이동하기** 위해 다음을 <https://protection.office.com/safelinksv2> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="c19bf-126">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c19bf-127">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c19bf-128">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c19bf-129">안전한 링크에 대한 전역 설정을 구성하려면 조직 관리  또는 보안 관리자 역할 그룹의 **구성원이** 되거나,</span><span class="sxs-lookup"><span data-stu-id="c19bf-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c19bf-130">안전한 링크에 대한 전역 설정에 대한 읽기 전용 액세스를 사용하려면 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나, </span><span class="sxs-lookup"><span data-stu-id="c19bf-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c19bf-131">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="c19bf-132">**참고**:</span><span class="sxs-lookup"><span data-stu-id="c19bf-132">**Notes**:</span></span>

  - <span data-ttu-id="c19bf-133">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c19bf-134">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="c19bf-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="c19bf-136">안전한 링크에 대한 전역 설정에 대한 권장 값은 안전한 링크 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="c19bf-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="c19bf-137">새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c19bf-138">[Office 365용 Microsoft Defender에](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)새로운 기능이 지속적으로 추가되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="c19bf-139">새 기능이 추가될 때 기존 안전 링크 정책을 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="c19bf-140">보안 및 준수 센터에서 "다음 URL 차단" & 구성</span><span class="sxs-lookup"><span data-stu-id="c19bf-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="c19bf-141">다음 URL 차단 **목록은** 지원되는 앱에서 안전한 링크 검색을 통해 항상 차단해야 하는 링크를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="c19bf-142">자세한 내용은 안전한 링크에 [대한 "다음 URL 차단" 목록을 참조하세요.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="c19bf-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="c19bf-143">보안 & 준수 센터에서 **위협** 관리 정책 ATP 안전한 \>  \> **링크로** 이동한 다음 전역 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c19bf-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="c19bf-144">조직의 **안전 링크** 정책에 나타나는 플라이아웃에서 다음 URL 차단 **상자로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="c19bf-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="c19bf-145">"다음 URL 차단" 목록에 대한 항목 구문에 설명된 하나 이상의 항목을 [구성합니다.](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="c19bf-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="c19bf-146">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="c19bf-147">PowerShell에서 "다음 URL 차단" 목록 구성</span><span class="sxs-lookup"><span data-stu-id="c19bf-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="c19bf-148">항목 구문에 대한 자세한 내용은 ["다음 URL 차단"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)목록의 항목 구문을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="c19bf-149">**Get-AtpPolicyForO365** cmdlet을 사용하여 _BlockURLs_ 속성의 기존 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="c19bf-150">기존 항목을 대체할 값을 추가하기 위해 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="c19bf-151">다음은 목록에 다음 항목을 추가하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="c19bf-152">도메인, 하위 도메인 및 도메인에 대한 경로를 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="c19bf-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="c19bf-153">하위 도메인 연구를 차단하지만 하위 도메인의 상위 도메인이나 다른 하위 도메인은 tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="c19bf-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="c19bf-154">다른 기존 항목에 영향을 주지 않고 값을 추가하거나 제거하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="c19bf-155">이 예제에서는 새 adatum.com 항목을 추가하고 새 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="c19bf-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="c19bf-156">보안 및 준수 센터에서 Office 365 앱에 대한 안전한 & 구성</span><span class="sxs-lookup"><span data-stu-id="c19bf-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="c19bf-157">Office 365 앱의 안전한 링크 보호는 지원되는 Office 데스크톱, 모바일 및 웹앱의 문서에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="c19bf-158">자세한 내용은 [Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps)앱에 대한 안전한 링크 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="c19bf-159">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP** 안전한 링크로 이동한 다음 전역 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c19bf-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="c19bf-160">조직의 **안전 링크** 정책이 나타나면 플라이아웃이 표시되면 전자 메일 섹션을 제외한 콘텐츠에 적용되는 설정에서 다음 설정을 **구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="c19bf-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="c19bf-161">**Office 365 응용 프로그램:** 지원되는 Office 365 앱에 대해 안전한 링크를 사용하도록 설정하려면 토글이 오른쪽에 있는지 ![ 확인: 설정/설정/ 설정 ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="c19bf-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="c19bf-162">**사용자가 안전한** 링크를 클릭하는 경우를 추적하지 않습니다. 토글을 왼쪽으로 이동하여 지원되는 Office 365 앱에서 차단된 URL과 관련된 사용자 클릭을 추적합니다. ![ 토글 끄기. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="c19bf-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="c19bf-163">**사용자가 원래 URL에** 대한 안전한 링크를 클릭할 수 없습니다. 사용자가 지원되는 Office 365 앱에서 원래 차단된 URL을 클릭하지 못하게 설정하려면 토글이 오른쪽에 있는지 확인합니다. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="c19bf-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="c19bf-164">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="c19bf-165">PowerShell에서 Office 365 앱에 대한 안전한 링크 보호 구성</span><span class="sxs-lookup"><span data-stu-id="c19bf-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="c19bf-166">PowerShell을 사용하여 Office 365 앱에 대해 안전한 링크 보호를 구성하는 경우 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c19bf-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="c19bf-167">이 예에서는 Office 365 앱에서 안전한 링크 보호에 대한 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="c19bf-168">Office 365 앱에 대한 안전한 링크가 켜져 _있습니다(EnableSafeLinksForO365Clients_ 매개 변수를 사용하지 않습니다. 기본값은 $true.</span><span class="sxs-lookup"><span data-stu-id="c19bf-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="c19bf-169">지원되는 Office 365 앱에서 차단된 URL과 관련된 사용자 클릭이 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="c19bf-170">사용자는 지원되는 Office 365 앱에서 원래 차단된 URL을 클릭할 수 _없습니다(AllowClickThrough_ 매개 변수를 사용하지 않습니다. 기본값은 $false).</span><span class="sxs-lookup"><span data-stu-id="c19bf-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="c19bf-171">구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="c19bf-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c19bf-172">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="c19bf-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="c19bf-173">안전한 링크에 대한 전역 설정(다음 **URL** 목록 및 Office 365 앱 보호 설정 차단)을 성공적으로 구성한지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="c19bf-174">보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP 안전한** 링크로 이동하여 전역 설정을 클릭하고 플라이아웃에 나타나는 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="c19bf-175">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 다음 명령을 실행하고 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c19bf-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="c19bf-176">구문과 매개 변수에 대한 자세한 내용은 [Get-AtpPolicyForO365를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="c19bf-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
