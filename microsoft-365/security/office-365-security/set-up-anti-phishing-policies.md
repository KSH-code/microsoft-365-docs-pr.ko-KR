---
title: 피싱 방지 정책
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365 ATP(Office 365 Advanced Threat Protection)에서 사용할 수 있는 피싱 방지 정책에 대해 알아할 수 있습니다.
ms.openlocfilehash: f671588ff4232c6ca1c1342475f48802bf1a0076
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825104"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="cba9d-103">Microsoft 365의 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="cba9d-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="cba9d-104">Exchange Online 사서함이 있는 Microsoft 365 조직, Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직 및 Office 365 ATP(Advanced Threat Protection) 조직이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="cba9d-105">ATP 피싱 방지 정책은 Office 365 ATP가 있는 조직에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="cba9d-106">예제:</span><span class="sxs-lookup"><span data-stu-id="cba9d-106">For example:</span></span>

- <span data-ttu-id="cba9d-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5 등.</span><span class="sxs-lookup"><span data-stu-id="cba9d-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="cba9d-108">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cba9d-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="cba9d-109">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="cba9d-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="cba9d-110">추가 기능으로서의 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="cba9d-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="cba9d-111">다른 모든 조직에는 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="cba9d-112">다음 표에서는 피싱 방지 정책과 ATP 피싱 방지 정책 사이의 높은 수준의 차이를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

****

|<span data-ttu-id="cba9d-113">기능</span><span class="sxs-lookup"><span data-stu-id="cba9d-113">Feature</span></span>|<span data-ttu-id="cba9d-114">피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="cba9d-114">Anti-phishing policies</span></span>|<span data-ttu-id="cba9d-115">ATP 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="cba9d-115">ATP anti-phishing policies</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="cba9d-116">자동으로 만들어진 기본 정책</span><span class="sxs-lookup"><span data-stu-id="cba9d-116">Automatically created default policy</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cba9d-119">사용자 지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="cba9d-119">Create custom policies</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cba9d-122">정책 설정<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cba9d-122">Policy settings<sup>\*</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cba9d-125">가장 설정</span><span class="sxs-lookup"><span data-stu-id="cba9d-125">Impersonation settings</span></span>||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cba9d-127">스푸핑 설정</span><span class="sxs-lookup"><span data-stu-id="cba9d-127">Spoof settings</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cba9d-130">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="cba9d-130">Advanced phishing thresholds</span></span>||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="cba9d-132"><sup>\*</sup> 기본 정책에서 정책 이름 및 설명은 읽기 전용이며(설명은 비어 있음) 정책이 적용되는 대상을 지정할 수 없습니다(기본 정책은 모든 받는 사람에게 적용).</span><span class="sxs-lookup"><span data-stu-id="cba9d-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="cba9d-133">피싱 방지 정책을 구성하려면 다음 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cba9d-133">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="cba9d-134">EOP에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="cba9d-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="cba9d-135">Microsoft 365에서 ATP 피싱 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="cba9d-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="cba9d-136">이 문서의 나머지 부분에서는 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있는 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-136">The rest of this article describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="cba9d-137">정책 설정</span><span class="sxs-lookup"><span data-stu-id="cba9d-137">Policy settings</span></span>

<span data-ttu-id="cba9d-138">피싱 방지 정책 및 ATP 피싱 방지 정책에서 다음 정책 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-138">The following policy settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="cba9d-139">**이름:** 기본 피싱 방지 정책의 이름을 바를 수는 없지만 직접 만드는 사용자 지정 정책의 이름을 지정하고 이름을 바일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-139">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="cba9d-140">**설명** 기본 피싱 방지 정책에 설명을 추가할 수는 없지만 직접 만드는 사용자 지정 정책에 대한 설명을 추가하고 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-140">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="cba9d-141">**적용됨:** 피싱 방지 정책이 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-141">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="cba9d-142">이 값은 사용자 지정 정책에서 필요하며 기본 정책에서 사용할 수 없음(모든 받는 사람에게 기본 정책을 적용)합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-142">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="cba9d-143">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-143">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="cba9d-144">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="cba9d-144">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="cba9d-145">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="cba9d-145">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="cba9d-146">**받는 사람은**조직에 있는 하나 이상의 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-146">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="cba9d-147">**받는 사람이 조직의**그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-147">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="cba9d-148">**받는 사람 도메인은**다음을 나타냅니다. Microsoft 365에서 구성된 허용 도메인 중 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-148">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="cba9d-149">**제외: 규칙의**예외입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-149">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="cba9d-150">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-150">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="cba9d-151">**받는 사람은**</span><span class="sxs-lookup"><span data-stu-id="cba9d-151">**Recipient is**</span></span>
    - <span data-ttu-id="cba9d-152">**받는 사람이 다음의 구성원임**</span><span class="sxs-lookup"><span data-stu-id="cba9d-152">**Recipient is a member of**</span></span>
    - <span data-ttu-id="cba9d-153">**받는 사람의 도메인이 다음과 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="cba9d-153">**The recipient domain is**</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="cba9d-154">스푸핑 설정</span><span class="sxs-lookup"><span data-stu-id="cba9d-154">Spoof settings</span></span>

<span data-ttu-id="cba9d-155">스푸핑은 전자 메일 메시지의 보낸 사람 주소(전자 메일 클라이언트에 표시된 보낸 사람 주소)가 전자 메일 원본의 도메인과 일치하지 않는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-155">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="cba9d-156">스푸핑에 대한 자세한 내용은 [Microsoft 365의 스푸핑 방지 보호 기능을 참조하세요.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cba9d-156">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="cba9d-157">다음 스푸핑 설정은 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-157">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="cba9d-158">**스푸핑 방지 보호 기능:** 스푸핑 방지 보호 기능을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-158">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="cba9d-159">사용하도록 설정된 값을 그대로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-159">We recommend that you leave it enabled.</span></span> <span data-ttu-id="cba9d-160">스푸핑 **인텔리전스 정책을 사용하여** 스푸핑된 특정 내부 및 외부 보낸 사람을 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-160">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="cba9d-161">자세한 내용은 [Microsoft 365에 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cba9d-161">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cba9d-162">스푸핑 설정은 EOP의 기본 피싱 방지 정책, 기본 ATP 피싱 방지 정책, 새로 만들 사용자 지정 피싱 방지 정책 또는 ATP 피싱 방지 정책에서 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-162">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="cba9d-163">MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용하지 않을 필요가 없습니다. 대신 커넥터에 대한 향상된 필터링을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-163">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="cba9d-164">자세한 내용은 [Exchange Online에서 커넥터에 대한 향상된 필터링을 참조하세요.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="cba9d-164">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="cba9d-165">수신 거부시보낸 메시지의 경우 메시지에 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-165">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="cba9d-166">**정크 메일 폴더로 메시지 이동:** 이 것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-166">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="cba9d-167">메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-167">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="cba9d-168">Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있는 경우 메시지는 정크 메일 폴더로 이동됩니다(기본적으로 활성화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="cba9d-168">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="cba9d-169">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="cba9d-169">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="cba9d-170">**메시지 격리: 메시지를**의도된 받는 사람에게 보내는 대신 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-170">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="cba9d-171">격리에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cba9d-171">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="cba9d-172">Microsoft 365의 격리</span><span class="sxs-lookup"><span data-stu-id="cba9d-172">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="cba9d-173">Microsoft 365에서 관리자 권한으로 격리된 메시지 및 파일 관리</span><span class="sxs-lookup"><span data-stu-id="cba9d-173">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="cba9d-174">Microsoft 365에서 사용자로 격리된 메시지 검색 및 해제하기</span><span class="sxs-lookup"><span data-stu-id="cba9d-174">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="cba9d-175">**인증되지 않은 보낸 사람:** 다음 섹션에서 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cba9d-175">**Unauthenticated Sender**: See the description in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="cba9d-176">인증되지 않은 보낸 사람</span><span class="sxs-lookup"><span data-stu-id="cba9d-176">Unauthenticated Sender</span></span>

<span data-ttu-id="cba9d-177">인증되지 않은 발신자 식별은 이전 섹션에 [Spoof settings](#spoof-settings) 설명된 바와 같이 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있는 스푸핑 설정의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-177">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies and ATP anti-phishing policies as described in the previous section.</span></span>

<span data-ttu-id="cba9d-178">인증되지 **않은 보낸 사람** 설정은 Outlook에서 확인되지 않은 보낸 사람 ID를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-178">The **Unauthenticated Sender** setting enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="cba9d-179">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-179">Specifically:</span></span>

- <span data-ttu-id="cba9d-180">메시지가 SPF 또는 DKIM 확인을 통과하지 못하고 메시지가 DMARC 또는 복합 인증을 통과하지 못한 경우 보낸 사람의 사진에 물음표(?)가 [추가됩니다.](email-validation-and-authentication.md#composite-authentication) **and**</span><span class="sxs-lookup"><span data-stu-id="cba9d-180">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

- <span data-ttu-id="cba9d-181">보낸 사람 주소의 도메인(chris@contoso.commichelle@fabrikam.com)이 DKIM 서명 또는 MAIL FROM 주소의 도메인과 다른 경우 태그를 통한 <u>태그(chris@contoso.com)가</u> **추가됩니다.**</span><span class="sxs-lookup"><span data-stu-id="cba9d-181">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="cba9d-182">이러한 주소에 대한 자세한 내용은 전자 [메일 메시지 표준의 개요를 참조하십시오.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="cba9d-182">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

<span data-ttu-id="cba9d-183">특정 보낸 사람의 메시지에 이러한 식별자가 추가되지 않도록 하려면 다음 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-183">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="cba9d-184">보낸 사람이 스푸핑 인텔리전스 정책을 스푸핑할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-184">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="cba9d-185">자세한 지침은 [Microsoft 365에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="cba9d-185">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="cba9d-186">[보낸 사람 도메인에 대한](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 전자 메일 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-186">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
  - <span data-ttu-id="cba9d-187">보낸 사람 사진의 물음표가 들어오는 경우 SPF 또는 DKIM이 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-187">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="cba9d-188">For the via tag, confirm the domain in the domain in the MAIL FROM address or the **MAIL FROM** address matches(or a subdomain of) in the From address.</span><span class="sxs-lookup"><span data-stu-id="cba9d-188">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="cba9d-189">자세한 내용은 Outlook [및 웹용 Outlook에서 의심스러운 Outlook.com 확인](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="cba9d-189">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="cba9d-190">ATP 피싱 방지 정책의 독점 설정</span><span class="sxs-lookup"><span data-stu-id="cba9d-190">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="cba9d-191">이 섹션에서는 ATP 피싱 방지 정책에서만 사용할 수 있는 정책 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-191">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="cba9d-192">기본적으로 ATP 배타적 설정은 기본 정책에서도 구성되거나 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-192">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="cba9d-193">이러한 기능을 이용하려면 기본 ATP 피싱 방지 정책에서 이기능을 사용하도록 설정 및 구성하거나, 사용자 지정 ATP 피싱 방지 정책을 만들고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-193">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="cba9d-194">ATP 피싱 방지 정책의 가장 설정</span><span class="sxs-lookup"><span data-stu-id="cba9d-194">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="cba9d-195">가장으로, 메시지의 보낸 사람 또는 보낸 사람 전자 메일 도메인이 다른 모양으로, 다른 항목은 각 도메인으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-195">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="cba9d-196">도메인 의미 가장하는 contoso.com ćóntoso.com.</span><span class="sxs-lookup"><span data-stu-id="cba9d-196">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="cba9d-197">사용자 추가 기능의 michelle@contoso.com 가장하는 michele@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cba9d-197">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="cba9d-198">이 경우 가장된 도메인은 느의 한도(등록된 도메인, 구성된 전자 메일 인증 레코드 등)로 간주되어도 받는 사람에게는 해당 받는 사람에게 는 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-198">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="cba9d-199">다음 가장 설정은 ATP 피싱 방지 정책에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-199">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="cba9d-200">**사용자를 보호할**수 있습니다. 지정된 내부 또는 외부 사용자를 가장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-200">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="cba9d-201">예를 들어 임원(내부) 및 보드 구성원(외부)을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-201">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="cba9d-202">최대 60명의 내부 및 외부 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-202">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="cba9d-203">보호되는 사용자 목록은 적용 대상 설정에 적용되는 받는 사람 목록과 **다릅니다.**</span><span class="sxs-lookup"><span data-stu-id="cba9d-203">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="cba9d-204">예를 들어 Executives 그룹에 적용되는 정책에서 felipea@contoso.com(Felipe Apodaca)를 보호되는 사용자로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-204">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="cba9d-205">Executives 그룹의 구성원에게 전송된 인바운드 메시지에서 Felipe Apodaca가 가장된 경우 정책에 따라 작업을 수행합니다(가장된 사용자에 대해 구성한 작업).</span><span class="sxs-lookup"><span data-stu-id="cba9d-205">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="cba9d-206">**보호할**도메인: 지정된 도메인이 가장되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-206">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="cba9d-207">예를 들어 소유하고 있는 모든 도메인(허용 도메인)[또는 특정](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)도메인(소유인 도메인 또는 파트너 도메인)을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-207">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="cba9d-208">보호되는 도메인 목록은 적용 대상 설정에 적용되는 도메인 목록과 **다릅니다.**</span><span class="sxs-lookup"><span data-stu-id="cba9d-208">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="cba9d-209">예를 들어 tailspintoys.com 그룹의 구성원에 적용되는 정책에서 보호되는 도메인으로 바를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-209">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="cba9d-210">Executives 그룹의 구성원에게 tailspintoys.com 사용자가 가장하는 인바운드 메시지는 정책(가장된 도메인에 대해 구성한 작업)별로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-210">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="cba9d-211">**보호된 사용자 또는 도메인에 대한**작업 : 인바운드 메시지 중 위임 시도를 포함하는 인바운드 메시지에 수행할 작업을 선택합니다. 보호된 사용자를 대신하여 정책에 보호된 도메인을 오는 경우 수행할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-211">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="cba9d-212">보호되는 사용자를 가장할 때와 보호되는 도메인 가장을 위한 서로 다른 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-212">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="cba9d-213">**모든 작업 적용 금지**</span><span class="sxs-lookup"><span data-stu-id="cba9d-213">**Don't apply any action**</span></span>

  - <span data-ttu-id="cba9d-214">**다른 전자 메일 주소로 메시지 리디렉션**: 메시지를 받는 사람이 아닌 지정된 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-214">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="cba9d-215">**정크 메일 폴더로 메시지**이동: 메시지가 사서함으로 배달되고, 정크 메일 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-215">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="cba9d-216">Exchange Online에서 사서함에 정크 메일 규칙이 활성화되어 있는 경우 메시지는 정크 메일 폴더로 이동됩니다(기본적으로 활성화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="cba9d-216">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="cba9d-217">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함에 대한 정크 메일 설정 구성을 참조하세요.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="cba9d-217">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="cba9d-218">**메시지 격리: 메시지를**의도된 받는 사람에게 보내는 대신 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-218">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="cba9d-219">격리에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cba9d-219">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="cba9d-220">Microsoft 365의 격리</span><span class="sxs-lookup"><span data-stu-id="cba9d-220">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="cba9d-221">Microsoft 365에서 관리자 권한으로 격리된 메시지 및 파일 관리</span><span class="sxs-lookup"><span data-stu-id="cba9d-221">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="cba9d-222">Microsoft 365에서 사용자로 격리된 메시지 검색 및 해제하기</span><span class="sxs-lookup"><span data-stu-id="cba9d-222">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="cba9d-223">**메시지를 배달하고 숨은 참조 줄에**다른 주소를 추가: 메시지를 받는 사람에게 배달하고 지정된 받는 사람에게 자동으로 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-223">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="cba9d-224">**메시지가 배달되기 전에 삭제: 모든**첨부 파일을 포함하여 전체 메시지를 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-224">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="cba9d-225">**보안 팁: 가장 검사에**실패한 메시지를 표시하는 다음 가장 안전 팁을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-225">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="cba9d-226">**가장된 사용자: 시작**주소에 보호된 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-226">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="cba9d-227">**가장된 도메인**: From 주소에 보호된 도메인이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-227">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="cba9d-228">**비정상적 문자**: From 주소에 보호된 보낸 사람 또는 도메인의 비정상적 문자 집합(예: 수학 기호 및 텍스트 또는 대문자 및 소문자 혼합)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-228">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="cba9d-229">**사서함 인텔리전스:** 자주 연락하는 연락처와 상태의 사용자 메일 패턴을 확인하는 AI(인공 지능)를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-229">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="cba9d-230">이 설정을 사용하면 AI가 정당한 전자 메일과 스푸핑된 전자 메일을 해당 연락처와 복합적으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-230">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="cba9d-231">사서함 인텔리전스는 Exchange Online 사서함에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-231">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="cba9d-232">**사서함 인텔리전스 기반 가장 보호**: 각 사용자의 개별 보낸 사람 맵에 기반하여 향상된 가장 결과를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-232">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="cba9d-233">Microsoft 365에서는 이러한 인텔리전스를 통해 사용자 가장 탐지를 사용자 지정하여 가양성을 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-233">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="cba9d-234">사용자 가장이 감지되면 메시지에 대해 수행할 특정 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-234">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="cba9d-235">**모든 작업 적용 금지**</span><span class="sxs-lookup"><span data-stu-id="cba9d-235">**Don't apply any action**</span></span>
  - <span data-ttu-id="cba9d-236">**다른 전자 메일 주소로 메시지 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="cba9d-236">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="cba9d-237">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="cba9d-237">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="cba9d-238">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="cba9d-238">**Quarantine the message**</span></span>
  - <span data-ttu-id="cba9d-239">**메시지 배달 및 "Bcc 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="cba9d-239">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="cba9d-240">**메시지를 배달하기 전에 삭제**</span><span class="sxs-lookup"><span data-stu-id="cba9d-240">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="cba9d-241">**신뢰할 수 있는 보낸 사람 및**도메인: 가장 보호 설정에 대한 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-241">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="cba9d-242">지정된 발신자 및 보낸 사람 도메인에서 받은 메시지는 정책에 의해 가장을 기반으로 하는 공격으로 분류되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-242">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="cba9d-243">즉, 보호된 보낸 사람, 보호도메인 또는 사서함 인텔리전스 보호를 위한 작업은 이러한 신뢰할 수 있는 보낸 사람 또는 보낸 사람의 도메인에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-243">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="cba9d-244">이러한 목록에 대한 최대 제한은 약 1000개 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-244">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="cba9d-245">ATP 피싱 방지 정책의 고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="cba9d-245">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="cba9d-246">다음 고급 피싱 임계값은 피싱 프리티드 결과를 결정하기 위해 메시지에 기계 학습 모델을 적용하기 위한 민감도를 제어하는 ATP 피싱 방지 정책에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-246">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="cba9d-247">**1 - 표준**: 기본값</span><span class="sxs-lookup"><span data-stu-id="cba9d-247">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="cba9d-248">메시지에 대해 수행된 작업의 심각도는 메시지가 피싱(낮음, 보간, 높음 또는 매우 높은 신뢰도)의 신뢰도에 따라 달라지기를 달라냅니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-248">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="cba9d-249">예를 들어, 신뢰도가 매우 높은 피싱으로 식별된 메시지는 심각한 동작이 적용된 동시에, 낮은 신뢰도로 확인된 메시지는 심각도가 매우 낮은 메시지만 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-249">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="cba9d-250">**2 - 적극적:** 신뢰도가 높은 피싱으로 식별되는 메시지는 매우 높은 신뢰도로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-250">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="cba9d-251">**3 - 보다 적극적:** 중간 또는 높은 신뢰도로 피싱으로 식별되는 메시지는 매우 높은 신뢰도로 식별되는 것과 같이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-251">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="cba9d-252">**4 - 가장 최적상태:** 낮음, 중간 또는 높은 신뢰도로 피싱으로 식별되는 메시지는 매우 높은 신뢰도로 식별되는 것보다 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-252">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="cba9d-253">이 설정을 늘리면 가양성(정상 메시지가 좋지 않은 것으로 표시)이 늘어나면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba9d-253">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="cba9d-254">권장되는 설정에 대한 자세한 [내용은 Office ATP 피싱 방지 정책 설정을 참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="cba9d-254">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>
