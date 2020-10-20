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
description: 관리자는 EOP (Exchange Online Protection)에서 모든 사용자에 대해 격리 된 메시지를 확인 하 고 관리 하는 방법을 확인할 수 있습니다. Office 365 Advanced Threat Protection (Office 365 ATP)을 사용 하는 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀에서 격리 된 파일을 관리할 수도 있습니다.
ms.openlocfilehash: 5e1115157ef7d67bc7a3f626eb61d01ecc0986cb
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600544"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="ade9e-104">EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기</span><span class="sxs-lookup"><span data-stu-id="ade9e-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ade9e-105">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="ade9e-106">자세한 내용은 [EOP에서 격리 된 전자 메일 메시지](quarantine-email-messages.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ade9e-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="ade9e-107">관리자는 모든 사용자에 대해 모든 유형의 격리 된 메시지를 보고, 해제 하 고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="ade9e-108">관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)의 결과로 격리 된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ade9e-109">관리자는 가양성을 Microsoft에 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="ade9e-110">Office 365, 고급 위협 방지 (Office 365 ATP)를 사용 하는 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀에서 격리 된 파일을 보고 다운로드 하 고 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="ade9e-111">격리 된 메시지는 보안 & 준수 센터 또는 PowerShell (exchange online 사서함이 없는 조직에 대 한 사서함이 있는 Microsoft 365 조 직의 경우 exchange 온라인 PowerShell)에서 확인 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ade9e-112">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="ade9e-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ade9e-113">보안 및 준수 센터를 열려면 <https://protection.office.com>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="ade9e-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="ade9e-114">격리 페이지를 바로 열려면 <https://protection.office.com/quarantine>으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="ade9e-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="ade9e-115">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ade9e-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ade9e-116">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ade9e-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ade9e-117">관리자로 격리를 관리 하려면 먼저 사용 권한을 할당 받아야 합니다. 사용 권한은 보안 & 준수 센터에서 **격리** 역할에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="ade9e-118">기본적으로이 역할은 보안 & 준수 센터의 **조직 관리** (전역 관리자), **격리 관리자**및 **보안 관리자** 역할 그룹에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="ade9e-119">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ade9e-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="ade9e-120">격리 된 메시지는 자동으로 삭제 되기 전에 기본 기간 동안 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="ade9e-121">스팸 방지 정책 (스팸, 피싱 및 대량 전자 메일)에 의해 격리 된 메시지: 30 일</span><span class="sxs-lookup"><span data-stu-id="ade9e-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="ade9e-122">이 값은 기본값 및 최대값입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-122">This is the default and maximum value.</span></span> <span data-ttu-id="ade9e-123">이 값을 구성 하려면 [스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ade9e-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="ade9e-124">맬웨어가 포함 된 메시지: 15 일</span><span class="sxs-lookup"><span data-stu-id="ade9e-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="ade9e-125">메시지가 격리에서 만료 되는 경우에는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="ade9e-126">보안 & 준수 센터를 사용 하 여 격리 된 전자 메일 메시지 관리</span><span class="sxs-lookup"><span data-stu-id="ade9e-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="ade9e-127">격리 된 전자 메일 보기</span><span class="sxs-lookup"><span data-stu-id="ade9e-127">View quarantined email</span></span>

1. <span data-ttu-id="ade9e-128">보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="ade9e-129">격리 된 **보기가** 기본값 **전자 메일로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="ade9e-130">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="ade9e-131">**열 수정**을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="ade9e-132">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="ade9e-133">**수신됨**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-133">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-134">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-134">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-135">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-135">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-136">**격리 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-136">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-137">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-137">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-138">**정책 유형**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-138">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-139">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="ade9e-139">**Recipient**</span></span>
   - <span data-ttu-id="ade9e-140">**메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="ade9e-140">**Message ID**</span></span>
   - <span data-ttu-id="ade9e-141">**정책 이름**</span><span class="sxs-lookup"><span data-stu-id="ade9e-141">**Policy name**</span></span>
   - <span data-ttu-id="ade9e-142">**크기**</span><span class="sxs-lookup"><span data-stu-id="ade9e-142">**Size**</span></span>
   - <span data-ttu-id="ade9e-143">**방향**</span><span class="sxs-lookup"><span data-stu-id="ade9e-143">**Direction**</span></span>

   <span data-ttu-id="ade9e-144">작업을 마쳤으면 **저장**을 클릭하거나 **기본으로 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="ade9e-145">결과를 필터링하려면 **필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="ade9e-146">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="ade9e-146">The available filters are:</span></span>

   - <span data-ttu-id="ade9e-147">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="ade9e-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="ade9e-148">**오늘**</span><span class="sxs-lookup"><span data-stu-id="ade9e-148">**Today**</span></span>
     - <span data-ttu-id="ade9e-149">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="ade9e-149">**Next 2 days**</span></span>
     - <span data-ttu-id="ade9e-150">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="ade9e-150">**Next 7 days**</span></span>
     - <span data-ttu-id="ade9e-151">**사용자 지정**: **시작 날짜**와 **종료 날짜**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="ade9e-152">**받은 시간**: **시작 날짜**와 **종료 날짜**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="ade9e-153">**격리 이유**:</span><span class="sxs-lookup"><span data-stu-id="ade9e-153">**Quarantine reason**:</span></span>
     - <span data-ttu-id="ade9e-154">**정책**: 메시지가 메일 흐름 규칙 (전송 규칙이 라고도 함)의 조건과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="ade9e-155">**대량 메일**</span><span class="sxs-lookup"><span data-stu-id="ade9e-155">**Bulk**</span></span>
     - <span data-ttu-id="ade9e-156">**피싱**: 스팸 필터 결과 **피싱 전자 메일** 또는 피싱 방지 보호 기능이 메시지를 격리 했습니다 ([스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings) 또는 [가장 보호](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)).</span><span class="sxs-lookup"><span data-stu-id="ade9e-156">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)).</span></span>
     - <span data-ttu-id="ade9e-157">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="ade9e-157">**Malware**</span></span>
     - <span data-ttu-id="ade9e-158">**스팸**</span><span class="sxs-lookup"><span data-stu-id="ade9e-158">**Spam**</span></span>
     - <span data-ttu-id="ade9e-159">**높은 신뢰도 피싱**</span><span class="sxs-lookup"><span data-stu-id="ade9e-159">**High Confidence Phish**</span></span>
     
   - <span data-ttu-id="ade9e-160">**정책 유형**: 정책 유형별로 메시지를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-160">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="ade9e-161">**맬웨어 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="ade9e-161">**Anti-malware policy**</span></span>
     - <span data-ttu-id="ade9e-162">**안전한 첨부 파일 정책**</span><span class="sxs-lookup"><span data-stu-id="ade9e-162">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="ade9e-163">**피싱 정책**</span><span class="sxs-lookup"><span data-stu-id="ade9e-163">**Anti-phish policy**</span></span>
     - <span data-ttu-id="ade9e-164">**호스팅된 콘텐츠 필터 정책**</span><span class="sxs-lookup"><span data-stu-id="ade9e-164">**Hosted content filter policy**</span></span>
     - <span data-ttu-id="ade9e-165">**전송 규칙**</span><span class="sxs-lookup"><span data-stu-id="ade9e-165">**Transport rule**</span></span>

   - <span data-ttu-id="ade9e-166">**전자 메일 받는 사람**: 모든 사용자 또는 자신에 게 전송 되는 메시지에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-166">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="ade9e-167">최종 사용자가 보낸 격리 된 메시지만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-167">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="ade9e-168">필터를 지우려면 **지우기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-168">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="ade9e-169">필터 플라이아웃을 숨기려면 다시 **필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-169">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="ade9e-170">특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-170">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="ade9e-171">와일드카드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-171">Wildcards aren't supported.</span></span> <span data-ttu-id="ade9e-172">다음 값을 기준으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-172">You can search by the following values:</span></span>

   - <span data-ttu-id="ade9e-173">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-173">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="ade9e-174">예를 들어 [메시지 추적](message-trace-scc.md) 을 사용 하 여 조직의 사용자에 게 전송 된 메시지를 찾고 메시지가 배달 되지 않고 격리 되었음을 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-174">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="ade9e-175">전체 메시지 ID 값에는 꺾쇠 괄호 ()가 포함 될 수 있습니다 \<\> .</span><span class="sxs-lookup"><span data-stu-id="ade9e-175">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="ade9e-176">예: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="ade9e-176">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="ade9e-177">**보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-177">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="ade9e-178">**정책 이름**: 메시지의 전체 정책 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-178">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="ade9e-179">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-179">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="ade9e-180">**받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-180">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="ade9e-181">**제목**: 메시지의 전체 제목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-181">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="ade9e-182">검색은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-182">The search is not case-sensitive.</span></span>

   <span data-ttu-id="ade9e-183">검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침**을 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-183">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="ade9e-184">격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).</span><span class="sxs-lookup"><span data-stu-id="ade9e-184">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="ade9e-185">메시지 결과 내보내기</span><span class="sxs-lookup"><span data-stu-id="ade9e-185">Export message results</span></span>

1. <span data-ttu-id="ade9e-186">원하는 메시지를 선택하고 **결과 내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-186">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="ade9e-187">브라우저를 열어 두라고 경고하는 확인 메시지에서 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-187">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="ade9e-188">내보내기가 준비되면 .csv 파일에 이름을 지정하고 다운로드 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-188">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="ade9e-189">격리된 메시지 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ade9e-189">View quarantined message details</span></span>

<span data-ttu-id="ade9e-190">목록에서 전자 메일 메시지를 선택하면 **세부 정보** 플라이아웃 창에 다음 메시지 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-190">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="ade9e-191">**메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-191">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="ade9e-192">**보낸 사람 주소**</span><span class="sxs-lookup"><span data-stu-id="ade9e-192">**Sender address**</span></span>

- <span data-ttu-id="ade9e-193">**수신됨**: 메시지를 수신한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-193">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="ade9e-194">**제목**</span><span class="sxs-lookup"><span data-stu-id="ade9e-194">**Subject**</span></span>

- <span data-ttu-id="ade9e-195">**격리 이유**: 메시지가 **스팸으로**식별 되었는지, **대량**, **피싱**, 일치 하는 메일 흐름 규칙 (**전송 규칙**) 인지 또는 **악성 프로그램**을 포함 하는 것으로 확인 된 경우를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-195">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="ade9e-196">**받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기**를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-196">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="ade9e-197">**만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-197">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="ade9e-198">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-198">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="ade9e-199">**아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-199">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="ade9e-200">격리된 전자 메일에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="ade9e-200">Take action on quarantined email</span></span>

<span data-ttu-id="ade9e-201">메시지를 선택한 후에는 **세부 정보** 플라이 아웃 창에서 메시지에 대해 수행할 작업을 여러 가지 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-201">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="ade9e-202">**릴리스 메시지**: 표시 된 플라이 아웃 창에서 다음 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-202">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="ade9e-203">**Microsoft에 분석을 위해 메시지를 보고**:이 기능은 기본적으로 선택 되며 잘못 격리 된 메시지를 microsoft에 가양성으로 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-203">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="ade9e-204">메시지가 스팸으로, 대량, 피싱 또는 맬웨어를 포함 하는 것으로 격리 된 경우 메시지는 Microsoft 스팸 분석 팀에도 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-204">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="ade9e-205">분석에 따라 서비스 전체 스팸 필터 규칙이 메시지를 통과 하도록 조정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-205">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="ade9e-206">다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-206">Choose one of the following options:</span></span>
    - <span data-ttu-id="ade9e-207">**모든 받는 사람에 게 메시지를 놓습니다.**</span><span class="sxs-lookup"><span data-stu-id="ade9e-207">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="ade9e-208">**특정 받는 사람에 게 메시지를 놓습니다.**</span><span class="sxs-lookup"><span data-stu-id="ade9e-208">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="ade9e-209">**다른 사람에 게 메시지를 놓습니다.**</span><span class="sxs-lookup"><span data-stu-id="ade9e-209">**Release messages to other people**</span></span>

  <span data-ttu-id="ade9e-210">작업을 마쳤으면 **메시지 해제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-210">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="ade9e-211">메시지 해제에 대 한 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="ade9e-211">Notes about releasing messages:</span></span>

  - <span data-ttu-id="ade9e-212">메시지를 동일한 받는 사람에 게 두 번 이상 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-212">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="ade9e-213">메시지를 받지 않은 받는 사람만 잠재 받는 사람 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-213">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="ade9e-214">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-214">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="ade9e-215">헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기**를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기**를 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="ade9e-215">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="ade9e-216">메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-216">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="ade9e-217">**메시지 미리 보기**: 표시되는 플라이아웃 창에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-217">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="ade9e-218">**원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-218">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="ade9e-219">**텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-219">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="ade9e-220">**격리에서 제거**: 표시 되는 경고에서 **예** 를 클릭 하면 메시지가 원래 받는 사람에 게 전송 되지 않고 즉시 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-220">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="ade9e-221">**메시지 다운로드하기**: 표시되는 플라이아웃 창에서 **이 메시지를 다운로드하는 데 따르는 위험을 알고 있습니다.** 를 선택하여 메시지의 로컬 복사본을 .eml 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-221">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="ade9e-222">**전송 메시지**: 표시 된 플라이 아웃 창에서 다음 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-222">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="ade9e-223">**개체 유형**: **Email** (기본값), **URL**또는 **Attachment**</span><span class="sxs-lookup"><span data-stu-id="ade9e-223">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="ade9e-224">**전송 형식**: **네트워크 메시지 id** (기본값으로, **네트워크 메시지 id** 상자의 해당 값 포함) 또는 **파일** (로컬 .eml 또는 .msg 파일 찾아보기)</span><span class="sxs-lookup"><span data-stu-id="ade9e-224">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="ade9e-225">**파일** 을 선택한 다음 **네트워크 메시지 ID**를 선택 하면 초기 값이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-225">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="ade9e-226">**받는 사람**: 메시지의 원래 받는 사람 하나를 임대에 입력 하거나, **모두 선택을** 클릭 하 여 모든 받는 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-226">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="ade9e-227">**모두 선택을** 클릭 한 다음 개별 받는 사람을 선택적으로 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-227">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="ade9e-228">**전송 사유**: **차단** 되지 않았거나 (기본값) **차단**되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-228">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="ade9e-229">작업이 완료 되 면 **제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-229">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="ade9e-230">메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-230">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="ade9e-231">여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기</span><span class="sxs-lookup"><span data-stu-id="ade9e-231">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="ade9e-232">목록에서 격리된 메시지를 여러 개(최대 100개) 선택하면 다음 **대량 전자 메일 작업** 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-232">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="ade9e-233">**메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기**를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기**만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-233">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ade9e-234">John@gmail.com에서 faith@contoso.com 및 john@subsidiary.contoso.com에 메시지를 전송 하는 시나리오를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-234">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="ade9e-235">Gmail 분기가 수행이 메시지는 모두 Microsoft의 피싱으로 격리로 라우팅되는 두 개의 복사본으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-235">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="ade9e-236">관리자가 이러한 메시지를 모두 admin@contoso.com에 게 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-236">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="ade9e-237">관리자 사서함에 도달 하는 첫 번째로 릴리스된 메시지가 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-237">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="ade9e-238">두 번째로 릴리스된 메시지는 중복 배달으로 식별 되며 건너 뜁니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-238">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="ade9e-239">메시지 ID가 같고 시간이 받은 경우 메시지는 중복 항목으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-239">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="ade9e-240">**메시지 삭제하기**: 표시되는 경고에서 **예**를 클릭하면 메시지는 원래 받는 사람에게 보내지지 않고 즉시 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-240">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="ade9e-241">작업을 마쳤으면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-241">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="ade9e-242">ATP 전용: 보안 & 준수 센터를 사용 하 여 격리 된 파일 관리</span><span class="sxs-lookup"><span data-stu-id="ade9e-242">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="ade9e-243">이 섹션에서 격리 된 파일의 절차는 ATP 계획 1 및 계획 2 구독자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-243">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="ade9e-244">ATP가 있는 조직에서는 관리자가 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀에서 격리 된 파일을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-244">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="ade9e-245">격리 된 파일 보기</span><span class="sxs-lookup"><span data-stu-id="ade9e-245">View quarantined files</span></span>

1. <span data-ttu-id="ade9e-246">보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-246">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="ade9e-247">**격리 된 보기** 를 기본 값 **파일로**변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-247">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="ade9e-248">사용 가능한 열 머리글을 클릭 하 여 필드를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-248">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="ade9e-249">사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-249">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="ade9e-250">**열 수정**을 클릭하여 최대 7개의 열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-250">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="ade9e-251">기본 열에는 별표 ()가 표시 됩니다 <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="ade9e-251">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="ade9e-252">**사용자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-252">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-253">**위치나**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-253">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-254">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-254">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-255">**파일 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-255">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-256">**파일 크기**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-256">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-257">**만료**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-257">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-258">**해제되었나요?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ade9e-258">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="ade9e-259">**검색 기준**</span><span class="sxs-lookup"><span data-stu-id="ade9e-259">**Detected by**</span></span>
   - <span data-ttu-id="ade9e-260">**시간별로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="ade9e-260">**Modified by time**</span></span>

4. <span data-ttu-id="ade9e-261">결과를 필터링하려면 **필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-261">To filter the results, click **Filter**.</span></span> <span data-ttu-id="ade9e-262">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="ade9e-262">The available filters are:</span></span>

   - <span data-ttu-id="ade9e-263">**만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:</span><span class="sxs-lookup"><span data-stu-id="ade9e-263">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="ade9e-264">**오늘**</span><span class="sxs-lookup"><span data-stu-id="ade9e-264">**Today**</span></span>
     - <span data-ttu-id="ade9e-265">**다음 2일**</span><span class="sxs-lookup"><span data-stu-id="ade9e-265">**Next 2 days**</span></span>
     - <span data-ttu-id="ade9e-266">**다음 7일**</span><span class="sxs-lookup"><span data-stu-id="ade9e-266">**Next 7 days**</span></span>
     - <span data-ttu-id="ade9e-267">사용자 지정 날짜/시간 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-267">A custom date/time range.</span></span>
   - <span data-ttu-id="ade9e-268">**받은 시간**</span><span class="sxs-lookup"><span data-stu-id="ade9e-268">**Received time**</span></span>
   - <span data-ttu-id="ade9e-269">**격리 이유**: **맬웨어**는 사용 가능한 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-269">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="ade9e-270">격리 된 특정 파일을 찾은 후 파일을 선택 하 여 자세한 정보를 확인 하 고 메시지에 대 한 작업을 수행 (예: 보기, 릴리스, 다운로드 또는 삭제) 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-270">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="ade9e-271">파일 내보내기 결과</span><span class="sxs-lookup"><span data-stu-id="ade9e-271">Export file results</span></span>

1. <span data-ttu-id="ade9e-272">관심 있는 파일을 선택 하 고 **결과 내보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-272">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="ade9e-273">브라우저를 열어 두라고 경고하는 확인 메시지에서 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-273">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="ade9e-274">내보내기가 준비되면 .csv 파일에 이름을 지정하고 다운로드 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-274">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="ade9e-275">격리 된 파일 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ade9e-275">View quarantined file details</span></span>

<span data-ttu-id="ade9e-276">목록에서 파일을 선택 하면 **세부 정보** 플라이 아웃 창에 다음과 같은 파일 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-276">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="ade9e-277">**File Name**</span><span class="sxs-lookup"><span data-stu-id="ade9e-277">**File Name**</span></span>
- <span data-ttu-id="ade9e-278">**파일 URL**: 파일의 위치 (예: SharePoint Online)를 정의 하는 url입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-278">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="ade9e-279">**에서 발견 된 악의적인 콘텐츠** 파일을 격리 한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-279">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="ade9e-280">**Expires**: 파일이 격리에서 삭제 되는 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-280">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="ade9e-281">**검색 한 사람**: ATP (Advanced Threat Protection) 또는 Microsoft의 맬웨어 방지 엔진</span><span class="sxs-lookup"><span data-stu-id="ade9e-281">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="ade9e-282">**해제되었나요?**</span><span class="sxs-lookup"><span data-stu-id="ade9e-282">**Released?**</span></span>
- <span data-ttu-id="ade9e-283">**맬웨어 이름**</span><span class="sxs-lookup"><span data-stu-id="ade9e-283">**Malware Name**</span></span>
- <span data-ttu-id="ade9e-284">**문서 ID**: 문서에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-284">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="ade9e-285">**파일 크기**(kb)입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-285">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="ade9e-286">**조직** 조직의 고유한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-286">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="ade9e-287">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="ade9e-287">**Last modified**</span></span>
- <span data-ttu-id="ade9e-288">**수정한 사람**: 파일을 마지막으로 수정한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-288">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="ade9e-289">**보안 해시 알고리즘 256 비트 (SHA-256) 값**:이 해시 값을 사용 하 여 다른 신뢰도 저장소 또는 환경의 다른 위치에서 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-289">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="ade9e-290">격리 된 파일에 대 한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="ade9e-290">Take action on quarantined files</span></span>

<span data-ttu-id="ade9e-291">목록에서 파일을 선택 하면 **세부 정보** 플라이 아웃 창에서 파일에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-291">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="ade9e-292">**파일 릴리스**: **분석을 위해 Microsoft에 보고서 파일을**선택 하거나 선택을 취소 한 다음 **파일 릴리스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-292">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="ade9e-293">**파일 다운로드**</span><span class="sxs-lookup"><span data-stu-id="ade9e-293">**Download file**</span></span>
- <span data-ttu-id="ade9e-294">**격리에서 파일 제거**</span><span class="sxs-lookup"><span data-stu-id="ade9e-294">**Remove file from quarantine**</span></span>

<span data-ttu-id="ade9e-295">파일을 해제 하거나 제거 하지 않으면 기본 격리 보존 기간이 만료 된 후에 파일이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-295">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="ade9e-296">여러 격리 된 파일에 대 한 작업</span><span class="sxs-lookup"><span data-stu-id="ade9e-296">Actions on multiple quarantined files</span></span>

<span data-ttu-id="ade9e-297">목록에서 격리 된 파일을 여러 개 선택 하면 (최대 100) 다음과 같은 작업을 수행할 수 있는 **대량 작업** 플라이 아웃 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-297">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="ade9e-298">**파일 릴리스**</span><span class="sxs-lookup"><span data-stu-id="ade9e-298">**Release files**</span></span>
- <span data-ttu-id="ade9e-299">**파일 삭제**: 표시 되는 경고에서 **예** 를 클릭 하면 파일이 즉시 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-299">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="ade9e-300">조직에서 전역 관리자 권한 (또는 적절 한 보안 & 준수 센터 역할)이 있는 회사 또는 학교 계정을 사용 하 여 로그인 하 고 [보안 & 준수 센터로 이동](../../compliance/go-to-the-securitycompliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-300">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="ade9e-301">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 격리 된 메시지 및 파일 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="ade9e-301">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="ade9e-302">격리에서 메시지와 파일을 보고 관리 하는 데 사용 하는 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-302">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="ade9e-303">Delete-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="ade9e-303">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="ade9e-304">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="ade9e-304">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="ade9e-305">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="ade9e-305">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="ade9e-306">[Preview-get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage):이 Cmdlet은 SharePoint Online, 비즈니스용 OneDrive 또는 팀에 대 한 ATP 파일이 아닌 메시지에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade9e-306">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="ade9e-307">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="ade9e-307">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
