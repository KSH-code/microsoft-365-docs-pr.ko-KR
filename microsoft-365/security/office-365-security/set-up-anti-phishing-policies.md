---
title: 피싱 방지 정책
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
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection) 및 Office 365 Advanced Threat Protection (Office 365 ATP)에서 사용할 수 있는 피싱 방지 정책에 대해 알아볼 수 있습니다.
ms.openlocfilehash: b492d37bea6135bccb770571f9984f9866c7cfd3
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804281"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="e88b5-103">Microsoft 365의 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="e88b5-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="e88b5-104">피싱 방지 보호 설정을 구성 하는 정책은 Exchange Online 사서함, 독립 실행형 EOP (Exchange Online Protection), Exchange Online 사서함이 없는 조직, Office 365 Advanced Threat Protection (Office 365 ATP) 조직이 있는 Microsoft 365 조직에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="e88b5-105">ATP 피싱 방지 정책은 Office 365 ATP가 있는 조직 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="e88b5-106">예제:</span><span class="sxs-lookup"><span data-stu-id="e88b5-106">For example:</span></span>

- <span data-ttu-id="e88b5-107">Microsoft 365 Enterprise E5, Microsoft 365 교육 A5 등입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="e88b5-108">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e88b5-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="e88b5-109">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e88b5-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="e88b5-110">Office 365 ATP를 추가 기능으로 사용</span><span class="sxs-lookup"><span data-stu-id="e88b5-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="e88b5-111">다른 모든 조직에는 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="e88b5-112">피싱 방지 정책과 ATP 피싱 방지 정책 간의 높은 수준의 차이점은 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

****

|<span data-ttu-id="e88b5-113">기능</span><span class="sxs-lookup"><span data-stu-id="e88b5-113">Feature</span></span>|<span data-ttu-id="e88b5-114">피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="e88b5-114">Anti-phishing policies</span></span>|<span data-ttu-id="e88b5-115">ATP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="e88b5-115">ATP anti-phishing policies</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="e88b5-116">자동으로 만들어진 기본 정책</span><span class="sxs-lookup"><span data-stu-id="e88b5-116">Automatically created default policy</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="e88b5-119">사용자 지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e88b5-119">Create custom policies</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="e88b5-122">정책 설정<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e88b5-122">Policy settings<sup>\*</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="e88b5-125">가장 설정</span><span class="sxs-lookup"><span data-stu-id="e88b5-125">Impersonation settings</span></span>||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="e88b5-127">스푸핑 설정</span><span class="sxs-lookup"><span data-stu-id="e88b5-127">Spoof settings</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="e88b5-130">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="e88b5-130">Advanced phishing thresholds</span></span>||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="e88b5-132"><sup>\*</sup> 기본 정책에서 정책 이름과 설명은 읽기 전용이 고 (설명은 비어 있음) 정책이 적용 되는 사용자를 지정할 수 없습니다 (기본 정책은 모든 받는 사람에 게 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="e88b5-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="e88b5-133">피싱 방지 정책을 구성 하려면 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-133">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="e88b5-134">EOP에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="e88b5-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="e88b5-135">Microsoft 365에서 ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="e88b5-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="e88b5-136">이 문서의 나머지 부분에서는 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있는 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-136">The rest of this article describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="e88b5-137">정책 설정</span><span class="sxs-lookup"><span data-stu-id="e88b5-137">Policy settings</span></span>

<span data-ttu-id="e88b5-138">피싱 방지 정책 및 ATP 피싱 방지 정책에서는 다음과 같은 정책 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-138">The following policy settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="e88b5-139">**이름**: 기본 피싱 방지 정책의 이름은 바꿀 수 없지만 직접 만든 사용자 지정 정책의 이름을 바꾸거나 이름을 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-139">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="e88b5-140">**설명** 기본 피싱 방지 정책에 설명을 추가할 수는 없지만 만든 사용자 지정 정책에 대 한 설명을 추가 및 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-140">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="e88b5-141">**적용 대상**: 피싱 방지 정책이 적용 되는 내부 받는 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-141">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="e88b5-142">이 값은 사용자 지정 정책에 필요 하며 기본 정책에서는 사용할 수 없습니다 (기본 정책은 모든 받는 사람에 게 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="e88b5-142">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="e88b5-143">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-143">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="e88b5-144">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e88b5-144">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e88b5-145">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e88b5-145">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="e88b5-146">**받는 사람**: 조직에 있는 하나 이상의 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-146">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="e88b5-147">**받는 사람은**조직에 있는 하나 이상의 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-147">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="e88b5-148">**받는 사람 도메인**: Microsoft 365에서 구성 된 허용 도메인 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-148">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="e88b5-149">다음의 **경우를 제외 하**고 규칙에 대 한 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-149">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="e88b5-150">설정 및 동작은 다음과 같은 조건과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-150">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="e88b5-151">**받는 사람은**</span><span class="sxs-lookup"><span data-stu-id="e88b5-151">**Recipient is**</span></span>
    - <span data-ttu-id="e88b5-152">**받는 사람이 다음의 구성원임**</span><span class="sxs-lookup"><span data-stu-id="e88b5-152">**Recipient is a member of**</span></span>
    - <span data-ttu-id="e88b5-153">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="e88b5-153">**The recipient domain is**</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="e88b5-154">스푸핑 설정</span><span class="sxs-lookup"><span data-stu-id="e88b5-154">Spoof settings</span></span>

<span data-ttu-id="e88b5-155">스푸핑 이란 전자 메일 메시지의 보낸 사람 주소 (전자 메일 클라이언트에 표시 되는 발신자 주소가 전자 메일 원본의 도메인)와 일치 하지 않는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-155">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="e88b5-156">스푸핑에 대 한 자세한 내용은 [Microsoft 365에서 스푸핑 방지 보호](anti-spoofing-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-156">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="e88b5-157">피싱 방지 정책 및 ATP 피싱 방지 정책에서는 다음과 같은 스푸핑 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-157">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="e88b5-158">**스푸핑 방지 보호**: 스푸핑 방지 보호 기능을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-158">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="e88b5-159">이 옵션을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-159">We recommend that you leave it enabled.</span></span> <span data-ttu-id="e88b5-160">스푸핑 **인텔리전스 정책을** 사용 하 여 특정 스푸핑된 내부 및 외부 보낸 사람을 허용 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-160">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="e88b5-161">자세한 내용은 [Microsoft 365에 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-161">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e88b5-162">스푸핑 설정은 기본적으로 EOP의 기본 피싱 방지 정책, 기본 ATP 피싱 방지 정책 및 새로 만든 피싱 방지 정책 또는 ATP 피싱 방지 정책에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-162">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="e88b5-163">MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용 하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대 한 향상 된 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-163">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="e88b5-164">자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e88b5-164">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="e88b5-165">차단 된 스푸핑된 보낸 사람에 게 보내는 메시지에 대해 수행할 작업을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-165">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="e88b5-166">**정크 메일 폴더로 메시지 이동**:이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-166">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="e88b5-167">메시지가 사서함에 배달 되 고 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-167">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="e88b5-168">Exchange Online에서 사서함에 대해 정크 메일 규칙을 사용 하도록 설정 되어 있으면 메시지가 정크 메일 폴더로 이동 됩니다 (기본적으로 사용 하도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="e88b5-168">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="e88b5-169">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-169">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="e88b5-170">**격리 메시지**: 의도 하지 않은 받는 사람 대신 메시지를 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-170">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="e88b5-171">격리에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-171">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="e88b5-172">Microsoft 365의 격리</span><span class="sxs-lookup"><span data-stu-id="e88b5-172">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="e88b5-173">Microsoft 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리</span><span class="sxs-lookup"><span data-stu-id="e88b5-173">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="e88b5-174">Microsoft 365에서 사용자로 격리 된 메시지 찾기 및 릴리스</span><span class="sxs-lookup"><span data-stu-id="e88b5-174">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="e88b5-175">**인증 되지 않은 보낸 사람**: 다음 섹션의 설명을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-175">**Unauthenticated Sender**: See the description in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="e88b5-176">인증 되지 않은 보낸 사람</span><span class="sxs-lookup"><span data-stu-id="e88b5-176">Unauthenticated Sender</span></span>

<span data-ttu-id="e88b5-177">인증 되지 않은 보낸 사람 id는 이전 섹션에 설명 된 것 처럼 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있는 [스푸핑 설정](#spoof-settings) 의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-177">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies and ATP anti-phishing policies as described in the previous section.</span></span>

<span data-ttu-id="e88b5-178">**인증 되지 않은 보낸 사람** 설정은 Outlook에서 미확인 보낸 사람 id를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-178">The **Unauthenticated Sender** setting enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="e88b5-179">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-179">Specifically:</span></span>

- <span data-ttu-id="e88b5-180">메시지가 SPF 또는 DKIM **검사를 통과 하지 않고 메시지가** DMARC 또는 [복합 인증](email-validation-and-authentication.md#composite-authentication)을 통과 하지 않는 경우 보낸 사람의 사진에 물음표 (?)가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-180">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

- <span data-ttu-id="e88b5-181">From 태그 (chris@contoso.com <u>via</u> michelle@fabrikam.com)는 보낸 사람 주소 (전자 메일 클라이언트에 표시 되는 메시지 발신자)가 dkim 서명 또는 **메일 원본** 주소에 있는 도메인과 다른 경우에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-181">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="e88b5-182">이러한 주소에 대 한 자세한 내용은 [전자 메일 메시지 표준 개요](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-182">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

<span data-ttu-id="e88b5-183">이러한 식별자가 특정 보낸 사람의 메시지에 추가 되지 않도록 하려면 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-183">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="e88b5-184">보낸 사람이 스푸핑 인텔리전스 정책에서 스푸핑할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-184">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="e88b5-185">자세한 내용은 [Microsoft 365에서 스푸핑 인텔리전스를 구성](learn-about-spoof-intelligence.md)합니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e88b5-185">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="e88b5-186">보낸 사람 도메인에 대 한 [전자 메일 인증을 구성](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-186">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
  - <span data-ttu-id="e88b5-187">보낸 사람의 사진에 있는 물음표의 경우 SPF 또는 DKIM이 가장 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-187">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="e88b5-188">Via 태그의 경우 DKIM 서명에서 도메인을 확인 하거나 보낸 **사람 주소에서** from 주소에 있는 도메인을 검색 합니다 (또는 하위 도메인의 하위 도메인이 됨).</span><span class="sxs-lookup"><span data-stu-id="e88b5-188">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="e88b5-189">자세한 내용은 [Outlook.com 및 웹용 Outlook에서 의심 스러운 메시지 식별](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-189">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="e88b5-190">ATP 피싱 방지 정책에서 배타적 설정</span><span class="sxs-lookup"><span data-stu-id="e88b5-190">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="e88b5-191">이 섹션에서는 ATP 피싱 방지 정책 에서만 사용할 수 있는 정책 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-191">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="e88b5-192">기본적으로 ATP 배타적 설정은 기본 정책 에서도 구성 되거나 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-192">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="e88b5-193">이러한 기능을 활용 하려면 기본 ATP 피싱 방지 정책에서 사용 하도록 설정 및 구성 하거나 사용자 지정 ATP 피싱 방지 정책을 만들고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-193">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="e88b5-194">ATP 피싱 방지 정책의 가장 설정</span><span class="sxs-lookup"><span data-stu-id="e88b5-194">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="e88b5-195">가장은 메시지의 보낸 사람 또는 보낸 사람의 전자 메일 도메인이 실제 보낸 사람이 나 도메인과 비슷한 모습입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-195">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="e88b5-196">도메인 contoso.com 가장의 예는 ćóntoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-196">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="e88b5-197">사용자 michelle@contoso.com 가장의 예는 michele@contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-197">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="e88b5-198">그렇지 않은 경우에는 받는 사람을 속이기 위한 것을 제외 하면 가장 된 도메인이 합법적 (등록 된 도메인, 구성 된 전자 메일 인증 레코드 등)으로 간주 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-198">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="e88b5-199">다음 가장 설정은 ATP 피싱 방지 정책 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-199">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="e88b5-200">**보호할 사용자**: 지정 된 내부 또는 외부 사용자가 가장 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-200">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="e88b5-201">예를 들어 임원 (내부) 및 보드 구성원 (외부) 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-201">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="e88b5-202">내부 및 외부 주소를 최대 60 개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-202">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="e88b5-203">이 보호 된 사용자 목록은 **적용** 된 설정에서 정책이 적용 되는 받는 사람 목록과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-203">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="e88b5-204">예를 들어 Apodaca 그룹에 적용 되는 정책에서 Felipe (felipea@contoso.com)을 보호 된 사용자로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-204">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="e88b5-205">Felipe Apodaca 가장이 구성 된 임원 그룹의 구성원에 게 전송 되는 인바운드 메시지는 정책 (가장 한 사용자를 위해 구성한 작업)에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-205">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="e88b5-206">**보호할 도메인**: 지정 된 도메인이 가장 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-206">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="e88b5-207">예를 들어 소유한 모든 도메인 ([허용 도메인](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 또는 특정 도메인 (사용자가 소유한 도메인 또는 파트너 도메인)</span><span class="sxs-lookup"><span data-stu-id="e88b5-207">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="e88b5-208">이 보호 된 도메인 목록은 **적용** 된 설정에서 정책을 적용 하는 도메인 목록과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-208">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="e88b5-209">예를 들어 tailspintoys.com 라는 그룹의 구성원에 게 적용 되는 정책에서 보호 된 도메인으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-209">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="e88b5-210">Tailspintoys.com이 가장 된 임원 그룹의 구성원에 게 전송 되는 인바운드 메시지는 정책 (가장 한 도메인에 대해 구성한 작업)에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-210">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="e88b5-211">**보호 된 사용자 또는 도메인에 대 한 작업**: 정책의 보호 된 사용자 및 보호 된 도메인에 대 한 가장 시도를 포함 하는 인바운드 메시지에 대해 수행할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-211">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="e88b5-212">보호 된 사용자의 가장에 대해 서로 다른 작업을 지정 하 고 보호 된 도메인의 가장을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-212">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="e88b5-213">**작업 적용 안 함**</span><span class="sxs-lookup"><span data-stu-id="e88b5-213">**Don't apply any action**</span></span>

  - <span data-ttu-id="e88b5-214">**메시지를 다른 전자 메일 주소로 리디렉션**: 받는 사람 대신 지정 된 받는 사람에 게 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-214">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="e88b5-215">**정크 메일 폴더로 메시지 이동**: 메시지가 사서함에 배달 되 고 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-215">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="e88b5-216">Exchange Online에서 사서함에 대해 정크 메일 규칙을 사용 하도록 설정 되어 있으면 메시지가 정크 메일 폴더로 이동 됩니다 (기본적으로 사용 하도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="e88b5-216">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="e88b5-217">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-217">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="e88b5-218">**격리 메시지**: 의도 하지 않은 받는 사람 대신 메시지를 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-218">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="e88b5-219">격리에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e88b5-219">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="e88b5-220">Microsoft 365의 격리</span><span class="sxs-lookup"><span data-stu-id="e88b5-220">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="e88b5-221">Microsoft 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리</span><span class="sxs-lookup"><span data-stu-id="e88b5-221">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="e88b5-222">Microsoft 365에서 사용자로 격리 된 메시지 찾기 및 릴리스</span><span class="sxs-lookup"><span data-stu-id="e88b5-222">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="e88b5-223">**메시지를 배달 하 고 숨은 참조 줄에 다른 주소 추가**: 받는 사람에 게 메시지를 배달 하 고 자동으로 지정한 받는 사람에 게 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-223">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="e88b5-224">**메시지를 배달 하기 전에 삭제**: 모든 첨부 파일을 포함 하 여 전체 메시지를 자동으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-224">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="e88b5-225">**안전 팁**: 가장 검사에 실패 하는 메시지를 표시 하는 다음과 같은 가장 안전 팁을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-225">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="e88b5-226">**가장 한 사용자**: 보낸 사람 주소에는 보호 된 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-226">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="e88b5-227">**가장 한 도메인**: 보낸 사람 주소에는 보호 된 도메인이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-227">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="e88b5-228">**이상한 문자**: 보낸 사람 주소에는 제한 된 발신자 또는 도메인에 이상한 기호, 텍스트 또는 대/소문자가 혼합 된 예외적인 문자 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-228">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="e88b5-229">**사서함 인텔리전스**: 자주 대화 상대와 사용자 전자 메일 패턴을 결정 하는 인공 지능 (인공 지능)을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-229">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="e88b5-230">이 설정을 사용 하면 이러한 연락처에서 합법적인 전자 메일과 위장 된 메일을 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-230">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="e88b5-231">사서함 인텔리전스는 Exchange Online 사서함에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-231">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="e88b5-232">**사서함 인텔리전스 기반 가장 보호**: 각 사용자의 개별 보낸 사람 맵에 따라 향상 된 가장 결과를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-232">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="e88b5-233">이 인텔리전스를 사용 하면 Microsoft 365에서 사용자 가장 검색을 사용자 지정 하 고 가양성을 보다 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-233">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="e88b5-234">사용자 가장이 검색 되 면 메시지에 대해 수행할 특정 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-234">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="e88b5-235">**작업 적용 안 함**</span><span class="sxs-lookup"><span data-stu-id="e88b5-235">**Don't apply any action**</span></span>
  - <span data-ttu-id="e88b5-236">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="e88b5-236">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="e88b5-237">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="e88b5-237">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="e88b5-238">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="e88b5-238">**Quarantine the message**</span></span>
  - <span data-ttu-id="e88b5-239">**메시지를 배달 하 고 숨은 참조 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="e88b5-239">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="e88b5-240">**메시지를 배달 하기 전에 삭제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e88b5-240">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="e88b5-241">**신뢰할 수 있는 보낸 사람 및 도메인**: 가장 보호 설정에 대 한 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-241">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="e88b5-242">지정 된 보낸 사람 및 보낸 사람 도메인의 메시지는 정책의 가장 기반 공격으로 분류 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-242">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="e88b5-243">즉, 보호 된 보낸 사람, 보호 된 도메인 또는 사서함 인텔리전스 보호에 대 한 작업은 이러한 신뢰할 수 있는 보낸 사람 또는 보낸 사람 도메인에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-243">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="e88b5-244">이러한 목록의 최대 제한은 약 1000 엔트리입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-244">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="e88b5-245">ATP 피싱 방지 정책의 고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="e88b5-245">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="e88b5-246">다음 advanced 피싱 임계값은 ATP 피싱 사기 정책 에서만 사용할 수 있으며,이는 피싱 결과을 확인 하기 위해 메시지에 기계 학습 모델을 적용할 민감도를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-246">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="e88b5-247">**1-Standard**:이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-247">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="e88b5-248">메시지에 대해 수행 되는 작업의 심각도는 메시지가 피싱 인 신뢰도 (낮음, 중간, 높음, 높음 신뢰도)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-248">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="e88b5-249">예를 들어 매우 높은 확신을 가진 피싱으로 식별 되는 메시지는 가장 심각 하 게 적용 되는 작업을 수행 하지만 낮은 수준의 확신을 가진 피싱으로 식별 된 메시지에는 덜 심각한 작업이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-249">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="e88b5-250">**2-적극적인**: 높은 확신을 가진 피싱으로 식별 되는 메시지는 높은 신뢰도로 식별 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-250">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="e88b5-251">**3-적극적인**신뢰도를 확인 하는 피싱으로 식별 되는 메시지는 높은 수준의 신뢰도로 식별 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-251">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="e88b5-252">**최대 적극적인**: 낮음, 중간 또는 높은 신뢰도의 피싱으로 식별 되는 메시지는 높은 신뢰도로 식별 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-252">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="e88b5-253">가양성 (잘못 된 것으로 표시 되는 메시지 양호)이 증가 하면이 설정이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88b5-253">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="e88b5-254">권장 설정에 대 한 자세한 내용은 [OFFICE ATP 피싱 방지 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e88b5-254">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>
