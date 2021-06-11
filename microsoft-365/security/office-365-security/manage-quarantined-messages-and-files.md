---
title: 관리자로 격리된 메시지 및 파일 관리
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(전자 메일 그룹)의 모든 사용자에 대해 분리된 메시지를 보고 관리하는 Exchange Online Protection 있습니다. Microsoft Defender for Office 365 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 파일에서 비즈니스용 OneDrive 관리할 Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d5011248d1c0fc0daab0d04e1cca39e26e34bd
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878895"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="cabed-104">EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기</span><span class="sxs-lookup"><span data-stu-id="cabed-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cabed-105">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="cabed-105">**Applies to**</span></span>
- [<span data-ttu-id="cabed-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cabed-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cabed-107">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="cabed-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cabed-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cabed-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cabed-109">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="cabed-110">자세한 내용은 [EOP에서 Quarantined email messages를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="cabed-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="cabed-111">관리자는 모든 사용자에 대해 모든 유형의 메시지를 보고, 해제하고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="cabed-112">관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙(전송 규칙)의 결과로 고지된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="cabed-113">관리자는 Microsoft에 가의성도 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="cabed-114">Microsoft Defender for Office 365 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 파일에서 분리된 파일을 보고 다운로드하고 삭제할 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cabed-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="cabed-115">Microsoft 365 Defender 포털 또는 PowerSh Exchange Online ell(Microsoft 365 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online, 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 Exchange Online 메시지를 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-115">You view and manage quarantined messages in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cabed-116">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="cabed-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cabed-117">Defender Microsoft 365 열기 위해 로 이동 <https://security.microsoft.com> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-117">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="cabed-118">격리 페이지를 바로 열려면 <https://security.microsoft.com/quarantine>(으)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-118">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="cabed-119">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cabed-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cabed-120">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cabed-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cabed-121">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cabed-122">모든 사용자에 대해 검역된 메시지에 대해 작업을 수행하려면 조직 **관리,** 보안 관리자 또는 **Quarantine Administrator** 역할 그룹의 <sup>\*</sup> 구성원일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="cabed-123">모든 사용자에 대해 정식으로 전송된 메시지에 대한 읽기 전용 액세스의  경우 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cabed-124">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cabed-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="cabed-125">**참고**:</span><span class="sxs-lookup"><span data-stu-id="cabed-125">**Notes**:</span></span>

  - <span data-ttu-id="cabed-126">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cabed-127">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cabed-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="cabed-128">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="cabed-129"><sup>\*</sup>또한 **PowerShell에서** 절차를 수행하려면 Exchange Online 관리자 역할  그룹의 구성원이 [](/Exchange/permissions-exo/permissions-exo#role-groups) Exchange Online 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="cabed-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span><span class="sxs-lookup"><span data-stu-id="cabed-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="cabed-131">스팸 방지 정책(스팸, 피싱 및 대량 전자 메일)으로 차단된 메시지에 대해 30일</span><span class="sxs-lookup"><span data-stu-id="cabed-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="cabed-132">이 값은 기본값 및 최대값입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-132">This is the default and maximum value.</span></span> <span data-ttu-id="cabed-133">이 값을 구성(더 낮음)으로 설정하는 내용은 스팸 방지 정책 [구성을 참조합니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cabed-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="cabed-134">맬웨어가 포함된 메시지의 경우 15일</span><span class="sxs-lookup"><span data-stu-id="cabed-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="cabed-135">SharePoint, OneDrive 및 Microsoft Teams에 대해 안전한 첨부 파일로 Microsoft Teams 15일 동안 Office 365.</span><span class="sxs-lookup"><span data-stu-id="cabed-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="cabed-136">메시지가 검지에서 만료되면 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-email-messages"></a><span data-ttu-id="cabed-137">Defender Microsoft 365 사용하여 고지된 전자 메일 메시지 관리</span><span class="sxs-lookup"><span data-stu-id="cabed-137">Use the Microsoft 365 Defender portal to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="cabed-138">quarantined email 보기</span><span class="sxs-lookup"><span data-stu-id="cabed-138">View quarantined email</span></span>

1. <span data-ttu-id="cabed-139">Microsoft 365 Defender 포털에서 전자 메일 전자 메일 & **검토** \>  \> **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="cabed-139">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cabed-140">**Quarantine** 페이지에서 **View quarantined가** 기본값 전자 메일로 설정되어 있는지 **확인하십시오.**</span><span class="sxs-lookup"><span data-stu-id="cabed-140">On the **Quarantine** page, verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="cabed-141">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cabed-142">**열 수정** 을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cabed-143">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cabed-144">**수신됨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-145">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-146">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-147">**격리 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-148">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-149">**정책 유형**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-150">**만료**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-150">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-151">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="cabed-151">**Recipient**</span></span>
   - <span data-ttu-id="cabed-152">**메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="cabed-152">**Message ID**</span></span>
   - <span data-ttu-id="cabed-153">**정책 이름**</span><span class="sxs-lookup"><span data-stu-id="cabed-153">**Policy name**</span></span>
   - <span data-ttu-id="cabed-154">**크기**</span><span class="sxs-lookup"><span data-stu-id="cabed-154">**Size**</span></span>
   - <span data-ttu-id="cabed-155">**방향**</span><span class="sxs-lookup"><span data-stu-id="cabed-155">**Direction**</span></span>

   <span data-ttu-id="cabed-156">작업을 마쳤으면 **저장** 을 클릭하거나 **기본으로 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="cabed-157">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cabed-158">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="cabed-158">The available filters are:</span></span>
   - <span data-ttu-id="cabed-159">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="cabed-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="cabed-160">**오늘**</span><span class="sxs-lookup"><span data-stu-id="cabed-160">**Today**</span></span>
     - <span data-ttu-id="cabed-161">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="cabed-161">**Next 2 days**</span></span>
     - <span data-ttu-id="cabed-162">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="cabed-162">**Next 7 days**</span></span>
     - <span data-ttu-id="cabed-163">**사용자 지정**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-163">**Custom**: Enter a **Start date** and **End date**.</span></span>
   - <span data-ttu-id="cabed-164">**받은 시간**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-164">**Received time**: Enter a **Start date** and **End date**.</span></span>
   - <span data-ttu-id="cabed-165">**격리 이유**:</span><span class="sxs-lookup"><span data-stu-id="cabed-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="cabed-166">**정책:** 메시지가 메일 흐름 규칙의 조건과 일치합니다(전송 규칙).</span><span class="sxs-lookup"><span data-stu-id="cabed-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="cabed-167">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="cabed-167">**Bulk**</span></span>
     - <span data-ttu-id="cabed-168">**피싱:** 스팸 필터 판정이 피싱 전자 메일 또는 피싱 방지 보호 [](set-up-anti-phishing-policies.md#spoof-settings) 기능으로 메시지(스푸핑 설정 또는 가장 보호)를 통해 [확인되었습니다.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) </span><span class="sxs-lookup"><span data-stu-id="cabed-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="cabed-169">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="cabed-169">**Malware**</span></span>
     - <span data-ttu-id="cabed-170">**스팸**</span><span class="sxs-lookup"><span data-stu-id="cabed-170">**Spam**</span></span>
     - <span data-ttu-id="cabed-171">**높은 신뢰도 피싱**</span><span class="sxs-lookup"><span data-stu-id="cabed-171">**High Confidence Phish**</span></span>
   - <span data-ttu-id="cabed-172">**정책 유형**: 정책 유형별로 메시지를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="cabed-173">**맬웨어 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="cabed-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="cabed-174">**안전한 첨부 파일 정책**</span><span class="sxs-lookup"><span data-stu-id="cabed-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="cabed-175">**피싱 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="cabed-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="cabed-176">**호스트된 필터 정책**(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="cabed-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="cabed-177">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="cabed-177">**Transport rule**</span></span>
   - <span data-ttu-id="cabed-178">**전자 메일 받는** 사람: 모든 사용자 또는 사용자에게 보낸 메시지만</span><span class="sxs-lookup"><span data-stu-id="cabed-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="cabed-179">최종 사용자는 해당 사용자에게 전송된 분리된 메시지만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="cabed-180">필터를 지우려면 **지우기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="cabed-181">필터 플라이아웃을 숨기려면 다시 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="cabed-182">특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="cabed-183">와일드카드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-183">Wildcards aren't supported.</span></span> <span data-ttu-id="cabed-184">다음 값을 기준으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-184">You can search by the following values:</span></span>
   - <span data-ttu-id="cabed-185">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="cabed-186">예를 들어 메시지 [](message-trace-scc.md) 추적을 사용하여 조직의 사용자에게 전송된 메시지를 찾아 메시지가 배달된 것이 아니라 메시지에 대해 중단된 것으로 확인한 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="cabed-187">괄호( )를 포함할 수 있는 전체 메시지 ID 값을 포함해야 \<\> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="cabed-188">예: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="cabed-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="cabed-189">**보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-189">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="cabed-190">**정책 이름**: 메시지의 전체 정책 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="cabed-191">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-191">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="cabed-192">**받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-192">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="cabed-193">**제목**: 메시지의 전체 제목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="cabed-194">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-194">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="cabed-195">**정책 이름:** 메시지를 대리한 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="cabed-196">검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침** 을 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="cabed-197">격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).</span><span class="sxs-lookup"><span data-stu-id="cabed-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="cabed-198">격리된 메시지 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="cabed-198">View quarantined message details</span></span>

<span data-ttu-id="cabed-199">목록에서 전자 메일 메시지를 선택하면 나타나는 세부 정보 플라이아웃에서 다음 메시지 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-199">When you select an email message in the list, the following message details are available in the details flyout that appears:</span></span>

- <span data-ttu-id="cabed-200">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-200">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="cabed-201">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="cabed-201">**Sender address**</span></span>
- <span data-ttu-id="cabed-202">**수신됨**: 메시지를 수신한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-202">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="cabed-203">**제목**</span><span class="sxs-lookup"><span data-stu-id="cabed-203">**Subject**</span></span>
- <span data-ttu-id="cabed-204">**Quarantine reason:** 메시지가 **스팸,** 대량,  **피싱,** 메일 흐름 **규칙(전송** 규칙)과 일치했거나 맬웨어가 포함된 것으로 확인된 **경우를 보여 주며,**</span><span class="sxs-lookup"><span data-stu-id="cabed-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>
- <span data-ttu-id="cabed-205">**받는 사람 수**</span><span class="sxs-lookup"><span data-stu-id="cabed-205">**Recipient count**</span></span>
- <span data-ttu-id="cabed-206">**받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기** 를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="cabed-207">**만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="cabed-208">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="cabed-209">**아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="cabed-210">격리된 전자 메일에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="cabed-210">Take action on quarantined email</span></span>

<span data-ttu-id="cabed-211">메시지를 선택한 후 세부 정보 플라이아웃에서 메시지로 할 작업을 위한 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-211">After you select a message, you have several options for what to do with the messages in the details flyout:</span></span>

- <span data-ttu-id="cabed-212">**릴리스 메시지:** 플라이아웃이 나타나면 다음 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-212">**Release message**: In the flyout that appears, choose the following options:</span></span>
  - <span data-ttu-id="cabed-213">**분석을 위해 Microsoft에** 메시지 보고: 이 설정은 기본적으로 선택되어 있으며, 잘못된 메시지는 오판정으로 Microsoft에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="cabed-214">메시지가 스팸, 대량, 피싱 또는 맬웨어를 포함하는 것으로 확인된 경우 메시지도 Microsoft 스팸 분석 팀에 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="cabed-215">분석에 따라 메시지 통과를 허용하도록 서비스 전체 스팸 필터 규칙이 조정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>
  - <span data-ttu-id="cabed-216">다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="cabed-217">**모든 받는 사람에게 메시지 릴리스**</span><span class="sxs-lookup"><span data-stu-id="cabed-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="cabed-218">**특정 받는 사람에게 메시지 릴리스**</span><span class="sxs-lookup"><span data-stu-id="cabed-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="cabed-219">**다른 사람에게** 메시지 릴리스: 원래 받는 사람이 아닌 다른 사람에게 맬웨어 메시지를 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="cabed-220">작업을 마쳤으면 **메시지 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="cabed-221">메시지 표시에 대한 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="cabed-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="cabed-222">같은 받는 사람에게 메시지를 두 번 이상 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="cabed-223">메시지를 받지 않은 받는 사람만 잠재적인 받는 사람 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="cabed-224">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="cabed-225">헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기** 를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기** 를 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="cabed-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="cabed-226">메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>
- <span data-ttu-id="cabed-227">**메시지 미리 보기:** 플라이아웃이 나타나면 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-227">**Preview message**: In the flyout that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="cabed-228">**원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="cabed-229">**텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-229">**Text view**: Shows the message body in plain text.</span></span>
- <span data-ttu-id="cabed-230">**분리에서** 제거: 나타나는 경고에서 **예를** 클릭하면 메시지가 원래 받는 사람에게 전송되지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>
- <span data-ttu-id="cabed-231">**메시지 다운로드:** 나타나는 플라이아웃에서  메시지의 로컬 복사본을 .eml 형식으로 저장하기 위해 이 메시지를 다운로드할 경우의 위험을 이해합니다.를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-231">**Download message**: In the flyout that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>
- <span data-ttu-id="cabed-232">**보낸 사람 차단**: 사서함의 수신 거부 목록에 보낸 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-232">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="cabed-233">자세한 내용은 [메일 보낸 사람 차단](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cabed-233">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>
- <span data-ttu-id="cabed-234">**메시지 제출:** 플라이아웃이 나타나면 다음 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-234">**Submit message**: In the flyout that appears, choose the following options:</span></span>
  - <span data-ttu-id="cabed-235">**개체 유형:** **전자 메일(기본값),** **URL** 또는 첨부 **파일입니다.**</span><span class="sxs-lookup"><span data-stu-id="cabed-235">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>
  - <span data-ttu-id="cabed-236">**전송 형식:** **네트워크 메시지** ID(기본값, 네트워크 메시지 **ID** 상자에 해당 값 사용) 또는 **파일(로컬** .eml 또는 .msg 파일 찾아보기)입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-236">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="cabed-237">파일을 **선택한** 다음 네트워크 메시지 **ID를** 선택하면 초기 값이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-237">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>
  - <span data-ttu-id="cabed-238">**받는 사람:** 메시지를 받는 사람 한 명을  임대할 때 입력하거나 모두 선택을 클릭하여 모든 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-238">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="cabed-239">모두 선택을 **클릭한** 다음 개별 받는 사람을 선택적으로 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-239">You can also click **Select All** and then selectively remove individual recipients.</span></span>
  - <span data-ttu-id="cabed-240">**제출 사유:** **차단되지** 않은 경우(기본값) 또는 **차단된 을(를) 차단해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cabed-240">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="cabed-241">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cabed-241">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="cabed-242">메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-242">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="cabed-243">여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="cabed-243">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="cabed-244">목록에서 여러 개의 고지된 메시지(최대 100개)를  선택하면 다음 작업을 수행할 수 있는 대량 작업 플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-244">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout appears where you can take the following actions:</span></span>

- <span data-ttu-id="cabed-245">**메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기** 를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기** 만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-245">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cabed-246">다음 시나리오를 고려합니다. john@gmail.com 메시지를 faith@contoso.com john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cabed-246">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="cabed-247">Gmail은 이 메시지를 Microsoft에서 피싱으로 모두 검역으로 라우팅된 두 개의 복사본으로 쌍으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-247">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="cabed-248">관리자는 이러한 두 메시지를 모두 릴리스하여 admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cabed-248">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="cabed-249">관리자 사서함에 도달하는 첫 번째 릴리스된 메시지가 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-249">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="cabed-250">두 번째 릴리스된 메시지는 중복 배달으로 식별되어 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-250">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="cabed-251">메시지는 동일한 메시지 ID와 수신 시간이 있는 경우 중복 항목으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-251">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="cabed-252">**메시지 삭제:** 나타나는 경고에서 **예를** 클릭하면 메시지가 원래 받는 사람에게 전송되지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-252">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="cabed-253">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-253">When you're finished, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365"></a><span data-ttu-id="cabed-254">Microsoft 365 Defender 포털을 사용하여 2016년 10월에 대한 Defender에서 quarantined files를 Office 365</span><span class="sxs-lookup"><span data-stu-id="cabed-254">Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="cabed-255">이 섹션의 quarantined files에 대한 절차는 Microsoft Defender for Office 365 Plan 1 및 Plan 2 구독자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-255">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="cabed-256">Defender for Office 365 조직에서 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 관리에서 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cabed-256">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="cabed-257">이러한 파일에 대한 보호를 사용하도록 설정하려면 에 대한 안전 첨부 파일 [SharePoint,](turn-on-mdo-for-spo-odb-and-teams.md)OneDrive 및 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cabed-257">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="cabed-258">quarantined files(Quarantined Files 보기)</span><span class="sxs-lookup"><span data-stu-id="cabed-258">View quarantined files</span></span>

1. <span data-ttu-id="cabed-259">Microsoft 365 Defender 포털에서 전자 메일 전자 메일 & **검토** \>  \> **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="cabed-259">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cabed-260">**Quarantine** 페이지에서 값 **파일로 quarantined 보기를** **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="cabed-260">On the **Quarantine** page, change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="cabed-261">사용 가능한 열 헤더를 클릭하여 필드를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-261">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="cabed-262">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-262">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cabed-263">**열 수정** 을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-263">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cabed-264">기본 열에는 다음이 표시되어 있습니다. <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-264">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>
   - <span data-ttu-id="cabed-265">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-265">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-266">**위치**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-266">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-267">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-267">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-268">**파일 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-268">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-269">**파일 크기**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-269">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-270">**만료**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-270">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-271">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cabed-271">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="cabed-272">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="cabed-272">**Detected by**</span></span>
   - <span data-ttu-id="cabed-273">**시간으로 수정**</span><span class="sxs-lookup"><span data-stu-id="cabed-273">**Modified by time**</span></span>

4. <span data-ttu-id="cabed-274">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-274">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cabed-275">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="cabed-275">The available filters are:</span></span>
   - <span data-ttu-id="cabed-276">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="cabed-276">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="cabed-277">**오늘**</span><span class="sxs-lookup"><span data-stu-id="cabed-277">**Today**</span></span>
     - <span data-ttu-id="cabed-278">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="cabed-278">**Next 2 days**</span></span>
     - <span data-ttu-id="cabed-279">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="cabed-279">**Next 7 days**</span></span>
     - <span data-ttu-id="cabed-280">사용자 지정 날짜/시간 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-280">A custom date/time range.</span></span>
   - <span data-ttu-id="cabed-281">**받은 시간**</span><span class="sxs-lookup"><span data-stu-id="cabed-281">**Received time**</span></span>
   - <span data-ttu-id="cabed-282">**Quarantine reason**: The only available value is **Malware**.</span><span class="sxs-lookup"><span data-stu-id="cabed-282">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="cabed-283">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="cabed-283">**Policy type**</span></span>

<span data-ttu-id="cabed-284">특정 고지된 파일을 찾은 후 해당 파일을 선택하여 해당 파일에 대한 세부 정보를 보고 메시지 보기, 릴리스, 다운로드 또는 삭제와 같은 작업을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="cabed-284">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="cabed-285">quarantined file details 보기</span><span class="sxs-lookup"><span data-stu-id="cabed-285">View quarantined file details</span></span>

<span data-ttu-id="cabed-286">목록에서 파일을 선택하면 열 수 있는 세부 정보 플라이아웃에서 다음 파일 세부 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-286">When you select a file in the list, the following file details are available in the details flyout that opens:</span></span>

- <span data-ttu-id="cabed-287">**File Name**</span><span class="sxs-lookup"><span data-stu-id="cabed-287">**File Name**</span></span>
- <span data-ttu-id="cabed-288">**파일 URL:** 파일의 위치를 정의하는 URL입니다(예: SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="cabed-288">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="cabed-289">**검색된 악성 콘텐츠** 파일이 대리된 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-289">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="cabed-290">**만료 날짜:** 파일이 검지에서 삭제되는 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-290">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="cabed-291">**검색:** 맬웨어 Office 365 맬웨어 방지 엔진에 대한 Defender.</span><span class="sxs-lookup"><span data-stu-id="cabed-291">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="cabed-292">**해제되었나요?**</span><span class="sxs-lookup"><span data-stu-id="cabed-292">**Released?**</span></span>
- <span data-ttu-id="cabed-293">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="cabed-293">**Malware Name**</span></span>
- <span data-ttu-id="cabed-294">**문서 ID:** 문서의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-294">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="cabed-295">**파일 크기:** KB(킬로바이트)</span><span class="sxs-lookup"><span data-stu-id="cabed-295">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="cabed-296">**조직** 조직의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-296">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="cabed-297">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="cabed-297">**Last modified**</span></span>
- <span data-ttu-id="cabed-298">**수정한 사람:** 파일을 마지막으로 수정한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-298">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="cabed-299">**Secure Hash Algorithm 256비트(SHA-256) 값:** 이 해시 값을 사용하여 다른 신뢰도 저장소 또는 환경의 다른 위치에서 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-299">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="cabed-300">고지된 파일에 대한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="cabed-300">Take action on quarantined files</span></span>

<span data-ttu-id="cabed-301">목록에서 파일을 선택하면 세부 정보 플라이아웃에서 파일에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-301">When you select a file in the list, you can take the following actions on the file in the details flyout:</span></span>

- <span data-ttu-id="cabed-302">**파일 릴리스:** 분석을 위해 **Microsoft에 보고** 파일 선택(기본값)을 선택하거나 선택을 해제한 다음 파일 **릴리스를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="cabed-302">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="cabed-303">**파일 다운로드**</span><span class="sxs-lookup"><span data-stu-id="cabed-303">**Download file**</span></span>
- <span data-ttu-id="cabed-304">**파일 제거**</span><span class="sxs-lookup"><span data-stu-id="cabed-304">**Remove file from quarantine**</span></span>

<span data-ttu-id="cabed-305">파일을 해제하거나 제거하지 않는 경우 기본 검지 보존 기간이 만료된 후 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-305">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="cabed-306">여러 개의 고지된 파일에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="cabed-306">Actions on multiple quarantined files</span></span>

<span data-ttu-id="cabed-307">목록에서 여러 개의 분리된 파일(최대 100개)을 선택하면 다음 작업을 수행할 수 있는 대량 작업  플라이아웃이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-307">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout appears where you can take the following actions:</span></span>

- <span data-ttu-id="cabed-308">**파일 릴리스**</span><span class="sxs-lookup"><span data-stu-id="cabed-308">**Release files**</span></span>
- <span data-ttu-id="cabed-309">**파일 삭제:** 나타나는 경고에서 **예를** 클릭하면 파일이 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-309">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="cabed-310">PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 독립 실행형 메시지 및 파일 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="cabed-310">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="cabed-311">메시지와 파일을 확인 및 관리하는 데 사용하는 cmdlet은 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cabed-311">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="cabed-312">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cabed-312">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="cabed-313">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cabed-313">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="cabed-314">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cabed-314">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="cabed-315">[Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)이 cmdlet은 메시지 전용으로, 메시지, SharePoint, OneDrive 및 메시지에 대해 안전한 첨부 파일에서 OneDrive 않습니다Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cabed-315">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not quarantined files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="cabed-316">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cabed-316">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
