---
title: Office 365 ATP에서 안전한 링크 설정에 대 한 전역 설정 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Office 365 ATP (Advanced Threat Protection)에서 안전한 링크에 대 한 전역 설정 확인 및 구성 방법 (' Office 365 앱에 대 한 다음 Url의 차단 및 보호 기능)을 확인할 수 있습니다.
ms.openlocfilehash: 6ca18bfb555419a8f4a61b55715f328ed7da5e88
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328564"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="7e838-103">Office 365 ATP의 안전한 링크에 대 한 전역 설정 구성</span><span class="sxs-lookup"><span data-stu-id="7e838-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="7e838-104">이 문서는 [Office 365 Advanced Threat Protection](office-365-atp.md)이 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="7e838-105">Outlook에서 Safelinks에 대 한 정보를 검색 하는 개인 사용자는 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e838-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="7e838-106">안전한 링크는 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색을 제공 하 고 전자 메일 메시지와 다른 위치의 Url 및 링크 확인을 클릭 하는 경우 [Office 365 ATP (Advanced Threat Protection)](office-365-atp.md) 의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="7e838-107">자세한 내용은 [Office 365 ATP의 안전한 링크](atp-safe-links.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e838-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="7e838-108">안전한 링크 정책에서 가장 안전한 링크 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="7e838-109">자세한 내용은 [Office 365 ATP에서 안전한 링크 정책 설정을](set-up-atp-safe-links-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e838-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="7e838-110">그러나 안전한 링크는 활성 안전한 링크 정책에 포함 된 모든 사용자에 게 적용 되는 전역 설정도 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="7e838-111">다음 전역 설정 영역:</span><span class="sxs-lookup"><span data-stu-id="7e838-111">These global settings area:</span></span>

- <span data-ttu-id="7e838-112">**다음 url에 대 한 차단** 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="7e838-113">자세한 내용은 [안전한 링크에 대 한 "다음 Url 차단" 목록을](atp-safe-links.md#block-the-following-urls-list-for-safe-links) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e838-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="7e838-114">Office 365 앱에 대 한 안전한 링크 보호</span><span class="sxs-lookup"><span data-stu-id="7e838-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="7e838-115">자세한 내용은 [Office 365 앱에 대 한 안전한 링크 설정](atp-safe-links.md#safe-links-settings-for-office-365-apps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e838-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="7e838-116">보안 & 준수 센터 또는 PowerShell (exchange online에 사서함이 있는 적격 Microsoft 365 조직에 대 한 Exchange Online PowerShell, exchange online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell, Office 365 ATP 추가 기능 구독이 있는 경우)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7e838-117">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="7e838-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7e838-118">안전한 링크에 대 한 전역 설정에서 제공 되는 기능은 활성 안전한 링크 정책에 포함 된 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="7e838-119">기본 제공 또는 기본 안전 링크 정책이 없기 때문에 이러한 전역 설정을 활성화 하려면 하나 이상의 안전한 링크 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="7e838-120">자세한 내용은 [Office 365 ATP에서 안전한 링크 정책 설정을](set-up-atp-safe-links-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e838-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="7e838-121"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7e838-122">**ATP 안전한 링크** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/safelinksv2> 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="7e838-123">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e838-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7e838-124">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e838-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7e838-125">안전한 링크에 대 한 전역 설정을 보고 구성 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="7e838-126">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="7e838-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="7e838-127">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**</span><span class="sxs-lookup"><span data-stu-id="7e838-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="7e838-128">안전한 링크에 대 한 전역 설정에 대 한 권장 값은 [안전한 링크 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e838-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="7e838-129">새 정책이 나 업데이트 된 정책을 적용할 최대 30 분을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="7e838-130">[새 기능은 ATP에 계속 추가 됩니다](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="7e838-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="7e838-131">새 기능을 추가 하면 기존 안전한 링크 정책을 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="7e838-132">보안 & 준수 센터에서 "다음 Url 차단" 목록 구성</span><span class="sxs-lookup"><span data-stu-id="7e838-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="7e838-133">**다음 Url 차단** 목록에는 지원 되는 앱의 안전한 링크 검색에서 항상 차단 해야 하는 링크를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="7e838-134">자세한 내용은 [안전한 링크에 대 한 "다음 Url 차단" 목록을](atp-safe-links.md#block-the-following-urls-list-for-safe-links)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e838-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="7e838-135">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동한 다음 **전역 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="7e838-136">**조직에 대 한 안전 링크 정책이** 표시 되 면 **다음 url 차단** 상자로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="7e838-137">["다음 Url 차단" 목록의 항목 구문](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)에 설명 된 대로 하나 이상의 항목을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="7e838-138">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="7e838-139">PowerShell에서 "다음 Url 차단" 목록 구성</span><span class="sxs-lookup"><span data-stu-id="7e838-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="7e838-140">항목 구문에 대 한 자세한 내용은 ["다음 Url 차단" 목록의 항목 구문을](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e838-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="7e838-141">**AtpPolicyForO365** cmdlet을 사용 하 여 _blockurls_ 속성의 기존 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="7e838-142">기존 항목을 대체 하는 값을 추가 하려면 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="7e838-143">이 예제에서는 다음 항목을 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="7e838-144">Domain, 하위 도메인 및 fabrikam.com의 경로를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="7e838-145">Tailspintoys.com의 상위 도메인 이나 다른 하위 도메인이 아닌, 하위 도메인 조사를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="7e838-146">기존의 다른 항목에 영향을 주지 않고 값을 추가 하거나 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="7e838-147">이 예제에서는 adatum.com에 대 한 새 항목을 추가 하 고 fabrikam.com에 대 한 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="7e838-148">보안 & 준수 센터에서 Office 365 앱에 대 한 안전한 링크 보호 구성</span><span class="sxs-lookup"><span data-stu-id="7e838-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="7e838-149">안전한 링크 보호 Office 365 앱은 지원 되는 Office 데스크톱, 모바일 및 웹 앱의 문서에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="7e838-150">자세한 내용은 [Office 365 앱에 대 한 안전한 링크 설정](atp-safe-links.md#safe-links-settings-for-office-365-apps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e838-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="7e838-151">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동한 다음 **전역 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="7e838-152">**조직에 대 한 안전한 링크 정책이** 표시 되 면 **전자 메일을 제외한 콘텐츠에 적용 되는 설정** 에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="7e838-153">**Office 365 응용 프로그램**: 설정/해제가 올바른 office 365 앱에 대 한 안전한 링크를 사용 하도록 설정 하려면 켜기: 켜 둡니다 .를 확인 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="7e838-154">**사용자가 안전한 링크 클릭 시 추적 안 함**: 지원 되는 Office 365 apps에서 차단 된 url과 관련 된 사용자 클릭을 추적 하려면 왼쪽으로 토글을 이동 ![ 합니다. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="7e838-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="7e838-155">**사용자가 원본 URL에 대 한 안전한 링크를 클릭**하는 것을 허용 하지 않습니다. 설정/해제가 사용자가 지원 되는 Office 365 앱: ![ 켜기/끄기에서 원래 차단 된 URL로 클릭 하지 못하게 하는 것을 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="7e838-156">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="7e838-157">PowerShell에서 Office 365 앱에 대 한 안전한 링크 보호 구성</span><span class="sxs-lookup"><span data-stu-id="7e838-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="7e838-158">PowerShell을 사용 하 여 Office 365 앱에 대해 안전한 링크 보호를 구성 하려면 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="7e838-159">이 예에서는 Office 365 앱의 안전한 링크 보호에 대 한 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="7e838-160">Office 365 앱에 대 한 안전한 링크는 켜져 있으며 ( _EnableSafeLinksForO365Clients_ 매개 변수를 사용 하지 않으며 기본값은 $true)입니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="7e838-161">사용자가 클릭 하는 경우 지원 되는 Office 365 앱의 차단 된 Url과 관련 된 내용을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="7e838-162">사용자가 지원 되는 Office 365 앱 ( _Allowclickthrough 광고_ 매개 변수는 사용 하지 않음)에서 원래 차단 된 URL로 클릭 하는 것이 허용 되지 않으며 기본값은 $false입니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="7e838-163">구문 및 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e838-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7e838-164">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="7e838-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="7e838-165">안전한 링크에 대 한 전역 설정을 성공적으로 구성 했는지 확인 하려면 ( **다음 url** 목록 및 Office 365 앱 보호 설정 차단) 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="7e838-166">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 하 고, **전역 설정을**클릭 하 고, 표시 되는 즉시 설정이 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="7e838-167">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 다음 명령을 실행 하 고 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e838-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="7e838-168">구문과 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e838-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
