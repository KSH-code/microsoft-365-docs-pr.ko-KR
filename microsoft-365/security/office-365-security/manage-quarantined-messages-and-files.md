---
title: 관리자로 격리된 메시지 및 파일 관리
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
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
description: 관리자는 EOP(Exchange Online Protection)의 모든 사용자에 대해 고지된 메시지를 보고 관리하는 방법을 배울 수 있습니다. Office 365용 Microsoft Defender를 가진 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 분리된 파일을 관리할 수도 있습니다.
ms.openlocfilehash: 5f4d63576e57ac50abe1ec1eb378221c4d457280
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659989"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="06faa-104">EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기</span><span class="sxs-lookup"><span data-stu-id="06faa-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="06faa-105">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="06faa-106">자세한 내용은 [EOP에서 Quarantined 전자 메일 메시지를 참조하세요.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="06faa-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="06faa-107">관리자는 모든 사용자에 대해 모든 유형의 메시지를 보고, 해제하고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="06faa-108">관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙(전송 규칙)의 결과로 고지된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="06faa-109">관리자는 Microsoft에 가짓 긍정을 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="06faa-110">Office 365용 Microsoft Defender를 가진 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 분리된 파일을 보고, 다운로드하고, 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="06faa-111">보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 독립 실행형 메시지를 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="06faa-112">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="06faa-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="06faa-113">보안 및 준수 센터를 열려면 <https://protection.office.com>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="06faa-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="06faa-114">격리 페이지를 바로 열려면 <https://protection.office.com/quarantine>으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="06faa-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="06faa-115">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06faa-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="06faa-116">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06faa-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="06faa-117">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="06faa-118">모든 사용자에 대해 분리된 메시지에 대해 작업을 수행하려면 조직 **관리,** 보안 관리자 또는 **Quarantine Administrator** 역할 그룹의 <sup>\*</sup> 구성원이면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-118">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="06faa-119">모든 사용자에 대해 정식으로 전송된 메시지에 대한 읽기 전용 액세스의  경우 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나,</span><span class="sxs-lookup"><span data-stu-id="06faa-119">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="06faa-120">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06faa-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="06faa-121">**참고**:</span><span class="sxs-lookup"><span data-stu-id="06faa-121">**Notes**:</span></span>

  - <span data-ttu-id="06faa-122">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="06faa-123">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06faa-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="06faa-124">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="06faa-125"><sup>\*</sup>Exchange Online PowerShell에서 절차를 수행하려면 **Quarantine Administrator** 역할 그룹의 구성원도 [Exchange Online의](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) **Hygiene Management** 역할 그룹의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-125"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="06faa-126">Quarantined messages are retained for a default period of time before they're automatically deleted:</span><span class="sxs-lookup"><span data-stu-id="06faa-126">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="06faa-127">스팸 방지 정책(스팸, 피싱 및 대량 전자 메일)으로 차단된 메시지의 경우 30일</span><span class="sxs-lookup"><span data-stu-id="06faa-127">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="06faa-128">이 값은 기본값 및 최대값입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-128">This is the default and maximum value.</span></span> <span data-ttu-id="06faa-129">이 값을 구성(더 낮음)하도록 설정하는 내용은 [스팸 방지 정책 구성을 참조합니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="06faa-129">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="06faa-130">맬웨어가 포함된 메시지의 경우 15일</span><span class="sxs-lookup"><span data-stu-id="06faa-130">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="06faa-131">Office 365용 Defender의 SharePoint, OneDrive 및 Microsoft Teams에 대해 ATP에서 분리한 파일의 경우 15일</span><span class="sxs-lookup"><span data-stu-id="06faa-131">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="06faa-132">메시지가 비정기에서 만료되면 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-132">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="06faa-133">보안 및 & 센터를 사용하여 전송된 전자 메일 메시지 관리</span><span class="sxs-lookup"><span data-stu-id="06faa-133">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="06faa-134">메일이 전송된 경우 보기</span><span class="sxs-lookup"><span data-stu-id="06faa-134">View quarantined email</span></span>

1. <span data-ttu-id="06faa-135">보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-135">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="06faa-136">View **quarantined가** 기본값 전자 메일로 설정되어 있는지 **확인**</span><span class="sxs-lookup"><span data-stu-id="06faa-136">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="06faa-137">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-137">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="06faa-138">**열 수정** 을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-138">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="06faa-139">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-139">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="06faa-140">**수신됨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-140">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-141">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-141">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-142">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-142">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-143">**격리 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-143">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-144">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-144">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-145">**정책 유형**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-145">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-146">**만료**</span><span class="sxs-lookup"><span data-stu-id="06faa-146">**Expires**</span></span>
   - <span data-ttu-id="06faa-147">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="06faa-147">**Recipient**</span></span>
   - <span data-ttu-id="06faa-148">**메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="06faa-148">**Message ID**</span></span>
   - <span data-ttu-id="06faa-149">**정책 이름**</span><span class="sxs-lookup"><span data-stu-id="06faa-149">**Policy name**</span></span>
   - <span data-ttu-id="06faa-150">**크기**</span><span class="sxs-lookup"><span data-stu-id="06faa-150">**Size**</span></span>
   - <span data-ttu-id="06faa-151">**방향**</span><span class="sxs-lookup"><span data-stu-id="06faa-151">**Direction**</span></span>

   <span data-ttu-id="06faa-152">작업을 마쳤으면 **저장** 을 클릭하거나 **기본으로 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-152">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="06faa-153">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-153">To filter the results, click **Filter**.</span></span> <span data-ttu-id="06faa-154">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="06faa-154">The available filters are:</span></span>

   - <span data-ttu-id="06faa-155">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="06faa-155">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="06faa-156">**오늘**</span><span class="sxs-lookup"><span data-stu-id="06faa-156">**Today**</span></span>
     - <span data-ttu-id="06faa-157">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="06faa-157">**Next 2 days**</span></span>
     - <span data-ttu-id="06faa-158">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="06faa-158">**Next 7 days**</span></span>
     - <span data-ttu-id="06faa-159">**사용자 지정**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-159">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="06faa-160">**받은 시간**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-160">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="06faa-161">**격리 이유**:</span><span class="sxs-lookup"><span data-stu-id="06faa-161">**Quarantine reason**:</span></span>
     - <span data-ttu-id="06faa-162">**정책:** 메시지가 메일 흐름 규칙의 조건과 일치합니다(전송 규칙).</span><span class="sxs-lookup"><span data-stu-id="06faa-162">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="06faa-163">**대량 전자 메일**</span><span class="sxs-lookup"><span data-stu-id="06faa-163">**Bulk**</span></span>
     - <span data-ttu-id="06faa-164">**피싱**: 스팸 필터  판정이 메시지(스푸핑 설정 또는 가장 보호)를 통해 스팸 전자 메일 또는 피싱 방지 보호를 통해 [확인되었습니다.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)[](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="06faa-164">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="06faa-165">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="06faa-165">**Malware**</span></span>
     - <span data-ttu-id="06faa-166">**스팸**</span><span class="sxs-lookup"><span data-stu-id="06faa-166">**Spam**</span></span>
     - <span data-ttu-id="06faa-167">**높은 신뢰도 피싱**</span><span class="sxs-lookup"><span data-stu-id="06faa-167">**High Confidence Phish**</span></span>

   - <span data-ttu-id="06faa-168">**정책 유형**: 정책 유형별로 메시지를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-168">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="06faa-169">**맬웨어 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="06faa-169">**Anti-malware policy**</span></span>
     - <span data-ttu-id="06faa-170">**안전한 첨부 파일 정책**</span><span class="sxs-lookup"><span data-stu-id="06faa-170">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="06faa-171">**피싱 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="06faa-171">**Anti-phish policy**</span></span>
     - <span data-ttu-id="06faa-172">**호스트된 필터 정책**(스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="06faa-172">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="06faa-173">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="06faa-173">**Transport rule**</span></span>

   - <span data-ttu-id="06faa-174">**전자 메일 받는** 사람: 모든 사용자 또는 사용자에게 보낸 메시지만</span><span class="sxs-lookup"><span data-stu-id="06faa-174">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="06faa-175">최종 사용자는 해당 메시지에 전송된 메시지만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-175">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="06faa-176">필터를 지우려면 **지우기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="06faa-177">필터 플라이아웃을 숨기려면 다시 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-177">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="06faa-178">특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="06faa-179">와일드카드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-179">Wildcards aren't supported.</span></span> <span data-ttu-id="06faa-180">다음 값을 기준으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-180">You can search by the following values:</span></span>

   - <span data-ttu-id="06faa-181">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-181">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="06faa-182">예를 들어 메시지 [](message-trace-scc.md) 추적을 사용하여 조직의 사용자에게 전송된 메시지를 찾아 메시지가 배달되지 않고 2016년 6월에 중단된 것으로 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-182">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="06faa-183">괄호()를 포함할 수 있는 전체 메시지 ID 값을 포함해야 \<\> 합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-183">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="06faa-184">예를 들면 다음과 `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-184">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="06faa-185">**보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-185">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="06faa-186">**정책 이름**: 메시지의 전체 정책 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-186">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="06faa-187">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-187">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="06faa-188">**받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-188">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="06faa-189">**제목**: 메시지의 전체 제목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-189">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="06faa-190">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-190">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="06faa-191">**정책 이름:** 메시지를 대리하는 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-191">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="06faa-192">검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침** 을 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-192">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="06faa-193">격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).</span><span class="sxs-lookup"><span data-stu-id="06faa-193">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="06faa-194">격리된 메시지 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="06faa-194">View quarantined message details</span></span>

<span data-ttu-id="06faa-195">목록에서 전자 메일 메시지를 선택하면 **세부 정보** 플라이아웃 창에 다음 메시지 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-195">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="06faa-196">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-196">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="06faa-197">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="06faa-197">**Sender address**</span></span>

- <span data-ttu-id="06faa-198">**수신됨**: 메시지를 수신한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-198">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="06faa-199">**제목**</span><span class="sxs-lookup"><span data-stu-id="06faa-199">**Subject**</span></span>

- <span data-ttu-id="06faa-200">**Quarantine reason**: 메시지가 **스팸,** **대량,** 피싱, 메일 흐름 규칙(전송규칙)에 일치했거나 맬웨어가 포함된 것으로 식별된 경우를 **보여줍니다.** </span><span class="sxs-lookup"><span data-stu-id="06faa-200">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="06faa-201">**받는 사람 수**</span><span class="sxs-lookup"><span data-stu-id="06faa-201">**Recipient count**</span></span>

- <span data-ttu-id="06faa-202">**받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기** 를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-202">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="06faa-203">**만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-203">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="06faa-204">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-204">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="06faa-205">**아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-205">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="06faa-206">격리된 전자 메일에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="06faa-206">Take action on quarantined email</span></span>

<span data-ttu-id="06faa-207">메시지를 선택한 후 세부 정보 플라이아웃 창에서 메시지에  대해 어떤 작업을 할지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-207">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="06faa-208">**릴리스 메시지:** 나타나는 플라이아웃 창에서 다음 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-208">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="06faa-209">**분석을 위해 Microsoft에** 메시지 보고: 이 설정은 기본적으로 선택되어 있으며, Microsoft에 잘못된 긍정으로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-209">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="06faa-210">메시지가 스팸, 대량, 피싱 또는 맬웨어를 포함하는 것으로 확인된 경우 메시지도 Microsoft 스팸 분석 팀에 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-210">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="06faa-211">분석에 따라 메시지 통과를 허용하도록 서비스 전체 스팸 필터 규칙이 조정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-211">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="06faa-212">다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-212">Choose one of the following options:</span></span>
    - <span data-ttu-id="06faa-213">**모든 받는 사람에게 메시지 릴리스**</span><span class="sxs-lookup"><span data-stu-id="06faa-213">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="06faa-214">**특정 받는 사람에게 메시지 릴리스**</span><span class="sxs-lookup"><span data-stu-id="06faa-214">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="06faa-215">**다른 사람에게** 메시지 릴리스: 원래 받는 사람이 아닌 다른 사람에게 맬웨어 메시지를 릴리스하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-215">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="06faa-216">작업을 마쳤으면 **메시지 해제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-216">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="06faa-217">메시지 표시에 대한 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="06faa-217">Notes about releasing messages:</span></span>

  - <span data-ttu-id="06faa-218">같은 받는 사람에게 메시지를 두 번 이상 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-218">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="06faa-219">메시지를 받지 않은 받는 사람만 잠재적인 받는 사람 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-219">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="06faa-220">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-220">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="06faa-221">헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기** 를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기** 를 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="06faa-221">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="06faa-222">메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-222">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="06faa-223">**메시지 미리 보기**: 표시되는 플라이아웃 창에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-223">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="06faa-224">**원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-224">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="06faa-225">**텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-225">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="06faa-226">**Quarantine에서** 제거: 나타나는 경고에서 **예를** 클릭하면 메시지가 원래 받는 사람에게 전송되지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-226">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="06faa-227">**메시지 다운로드하기**: 표시되는 플라이아웃 창에서 **이 메시지를 다운로드하는 데 따르는 위험을 알고 있습니다.** 를 선택하여 메시지의 로컬 복사본을 .eml 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-227">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="06faa-228">**메시지 제출:** 나타나는 플라이아웃 창에서 다음 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-228">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="06faa-229">**개체 유형:** **전자 메일(기본값),** **URL** 또는 첨부 **파일.**</span><span class="sxs-lookup"><span data-stu-id="06faa-229">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="06faa-230">**전송 형식:** **네트워크 메시지** ID(기본값, 네트워크 메시지 **ID** 상자에 해당 값 사용) 또는 **파일(로컬** .eml 또는 .msg 파일 찾아보기)입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-230">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="06faa-231">파일을 선택한 **다음** 네트워크 메시지 **ID를** 선택하면 초기 값이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-231">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="06faa-232">**받는 사람:** 메시지를 원래 받는 사람 한 명을 임대할 때 입력하거나 모두 선택을 클릭하여 모든 받는 사람을 식별합니다. </span><span class="sxs-lookup"><span data-stu-id="06faa-232">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="06faa-233">모두 선택을 **클릭한** 다음 개별 받는 사람을 선택적으로 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-233">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="06faa-234">**제출 사유:** **차단되지** 않은 경우(기본값) 또는 **차단된 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="06faa-234">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="06faa-235">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06faa-235">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="06faa-236">메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-236">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="06faa-237">여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="06faa-237">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="06faa-238">목록에서 격리된 메시지를 여러 개(최대 100개) 선택하면 다음 **대량 전자 메일 작업** 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-238">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="06faa-239">**메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기** 를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기** 만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-239">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="06faa-240">다음 시나리오를 고려합니다. john@gmail.com 메시지는 faith@contoso.com john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06faa-240">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="06faa-241">Gmail은 이 메시지를 Microsoft에서 피싱으로 두 개의 복사본으로 이중으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-241">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="06faa-242">관리자는 이러한 두 메시지를 모두 해제하여 admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06faa-242">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="06faa-243">관리자 사서함에 도달하는 첫 번째 릴리스된 메시지가 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-243">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="06faa-244">두 번째 릴리스된 메시지는 중복 배달으로 식별되어 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-244">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="06faa-245">메시지 ID와 수신 시간이 같은 메시지는 중복된 것으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-245">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="06faa-246">**메시지 삭제:** 나타나는 경고에서 **예를** 클릭하면 메시지가 원래 받는 사람에게 전송되지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-246">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="06faa-247">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-247">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="06faa-248">Microsoft Defender for Office 365만 해당: 보안 & 준수 센터를 사용하여 분리된 파일 관리</span><span class="sxs-lookup"><span data-stu-id="06faa-248">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="06faa-249">이 섹션의 각 파일에 대한 절차는 Office 365 계획 1 및 계획 2 구독자용 Microsoft Defender에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-249">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="06faa-250">Office 365용 Defender가 있는 조직에서 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 분리된 파일을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-250">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="06faa-251">이러한 파일에 대한 보호를 사용하도록 설정하려면 [SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP 켜기를 참조합니다.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="06faa-251">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="06faa-252">Quarantined 파일 보기</span><span class="sxs-lookup"><span data-stu-id="06faa-252">View quarantined files</span></span>

1. <span data-ttu-id="06faa-253">보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-253">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="06faa-254">값 **파일로 quarantined 보기를** **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="06faa-254">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="06faa-255">사용 가능한 열 헤더를 클릭하여 필드를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-255">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="06faa-256">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-256">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="06faa-257">**열 수정** 을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-257">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="06faa-258">기본 열은 다음으로 표시되어 있습니다. <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-258">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="06faa-259">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-259">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-260">**위치**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-260">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-261">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-261">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-262">**파일 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-262">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-263">**파일 크기**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-263">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-264">**만료**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-264">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-265">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="06faa-265">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="06faa-266">**검색한 경우**</span><span class="sxs-lookup"><span data-stu-id="06faa-266">**Detected by**</span></span>
   - <span data-ttu-id="06faa-267">**시간으로 수정**</span><span class="sxs-lookup"><span data-stu-id="06faa-267">**Modified by time**</span></span>

4. <span data-ttu-id="06faa-268">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-268">To filter the results, click **Filter**.</span></span> <span data-ttu-id="06faa-269">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="06faa-269">The available filters are:</span></span>

   - <span data-ttu-id="06faa-270">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="06faa-270">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="06faa-271">**오늘**</span><span class="sxs-lookup"><span data-stu-id="06faa-271">**Today**</span></span>
     - <span data-ttu-id="06faa-272">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="06faa-272">**Next 2 days**</span></span>
     - <span data-ttu-id="06faa-273">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="06faa-273">**Next 7 days**</span></span>
     - <span data-ttu-id="06faa-274">사용자 지정 날짜/시간 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-274">A custom date/time range.</span></span>
   - <span data-ttu-id="06faa-275">**받은 시간**</span><span class="sxs-lookup"><span data-stu-id="06faa-275">**Received time**</span></span>
   - <span data-ttu-id="06faa-276">**Quarantine reason**: the only available value is **Malware.**</span><span class="sxs-lookup"><span data-stu-id="06faa-276">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="06faa-277">**정책 유형**</span><span class="sxs-lookup"><span data-stu-id="06faa-277">**Policy type**</span></span>

<span data-ttu-id="06faa-278">특정 고지된 파일을 찾은 후 해당 파일에 대한 세부 정보를 보고 메시지 보기, 릴리스, 다운로드 또는 삭제와 같은 작업을 수행하려면 해당 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-278">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="06faa-279">각 파일 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="06faa-279">View quarantined file details</span></span>

<span data-ttu-id="06faa-280">목록에서 파일을 선택하면 세부 정보 플라이아웃 창에 다음 파일 **세부** 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-280">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="06faa-281">**File Name**</span><span class="sxs-lookup"><span data-stu-id="06faa-281">**File Name**</span></span>
- <span data-ttu-id="06faa-282">**파일 URL**: 파일 위치(예: SharePoint Online)를 정의하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-282">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="06faa-283">**검색된 악성 콘텐츠** 파일이 중단된 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-283">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="06faa-284">**만료 날짜:** 파일이 Quarantine에서 삭제되는 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-284">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="06faa-285">**검색:** Office 365용 Defender 또는 Microsoft의 맬웨어 방지 엔진</span><span class="sxs-lookup"><span data-stu-id="06faa-285">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="06faa-286">**해제되었나요?**</span><span class="sxs-lookup"><span data-stu-id="06faa-286">**Released?**</span></span>
- <span data-ttu-id="06faa-287">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="06faa-287">**Malware Name**</span></span>
- <span data-ttu-id="06faa-288">**문서 ID**: 문서의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-288">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="06faa-289">**파일 크기:** KB(킬로바이트)</span><span class="sxs-lookup"><span data-stu-id="06faa-289">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="06faa-290">**조직** 조직의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-290">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="06faa-291">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="06faa-291">**Last modified**</span></span>
- <span data-ttu-id="06faa-292">**수정한 사람:** 파일을 마지막으로 수정한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-292">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="06faa-293">**보안 해시 알고리즘 256비트(SHA-256)** 값: 이 해시 값을 사용하여 다른 신뢰도 저장소 또는 환경의 다른 위치에서 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-293">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="06faa-294">고지된 파일에 대한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="06faa-294">Take action on quarantined files</span></span>

<span data-ttu-id="06faa-295">목록에서 파일을 선택하면 세부 정보 플라이아웃 창의 파일에 대해 다음 작업을 **수행할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-295">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="06faa-296">**릴리스 파일:** 분석을 위해 **Microsoft에** 보고서 파일을 선택(기본값)하거나 선택을 해제한 다음 **파일 릴리스를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="06faa-296">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="06faa-297">**파일 다운로드**</span><span class="sxs-lookup"><span data-stu-id="06faa-297">**Download file**</span></span>
- <span data-ttu-id="06faa-298">**파일 제거**</span><span class="sxs-lookup"><span data-stu-id="06faa-298">**Remove file from quarantine**</span></span>

<span data-ttu-id="06faa-299">파일을 해제하거나 제거하지 않는 경우 기본 분리 보존 기간이 만료된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-299">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="06faa-300">여러 개의 고지된 파일에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="06faa-300">Actions on multiple quarantined files</span></span>

<span data-ttu-id="06faa-301">목록에서 여러 개의 고지된 파일(최대 100개)을 선택하면 대량 작업 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="06faa-301">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="06faa-302">**파일 해제**</span><span class="sxs-lookup"><span data-stu-id="06faa-302">**Release files**</span></span>
- <span data-ttu-id="06faa-303">**파일 삭제:** 나타나는 경고에서 **예를** 클릭하면 파일이 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-303">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="06faa-304">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 독립 실행형 메시지 및 파일 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="06faa-304">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="06faa-305">메시지 및 파일을 보고 관리하는 데 사용하는 cmdlet은 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-305">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="06faa-306">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="06faa-306">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="06faa-307">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="06faa-307">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="06faa-308">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="06faa-308">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="06faa-309">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)이 cmdlet은 SharePoint Online, 비즈니스용 OneDrive 또는 Teams에 대한 ATP의 맬웨어 파일이 아니라 메시지에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06faa-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="06faa-310">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="06faa-310">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
