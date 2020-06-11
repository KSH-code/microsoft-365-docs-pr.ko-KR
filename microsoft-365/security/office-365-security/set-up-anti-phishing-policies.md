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
ms.openlocfilehash: 4cf727cd7d232baac13f44e008a509934f55d895
ms.sourcegitcommit: efd4dd29af0ea2b71b674534de3b2dcbfd7482db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689281"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="b1af8-103">Microsoft 365의 피싱 방지 정책</span><span class="sxs-lookup"><span data-stu-id="b1af8-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="b1af8-104">피싱 방지 보호 설정을 구성 하는 정책은 Exchange Online 사서함, 독립 실행형 EOP (Exchange Online Protection), Exchange Online 사서함이 없는 조직, Office 365 Advanced Threat Protection (Office 365 ATP) 조직이 있는 Microsoft 365 조직에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="b1af8-105">ATP 피싱 방지 정책은 Office 365 ATP가 있는 조직 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="b1af8-106">예시:</span><span class="sxs-lookup"><span data-stu-id="b1af8-106">For example:</span></span>

- <span data-ttu-id="b1af8-107">Microsoft 365 Enterprise E5, Microsoft 365 교육 A5 등입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="b1af8-108">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b1af8-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="b1af8-109">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b1af8-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="b1af8-110">Office 365 ATP를 추가 기능으로 사용</span><span class="sxs-lookup"><span data-stu-id="b1af8-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="b1af8-111">다른 모든 조직에는 피싱 방지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="b1af8-112">피싱 방지 정책과 ATP 피싱 방지 정책 간의 높은 수준의 차이점은 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

||||
|---|:---:|:---:|
|<span data-ttu-id="b1af8-113">**기능**</span><span class="sxs-lookup"><span data-stu-id="b1af8-113">**Feature**</span></span>|<span data-ttu-id="b1af8-114">**피싱 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="b1af8-114">**Anti-phishing policies**</span></span>|<span data-ttu-id="b1af8-115">**ATP 피싱 방지 정책**</span><span class="sxs-lookup"><span data-stu-id="b1af8-115">**ATP anti-phishing policies**</span></span>|
|<span data-ttu-id="b1af8-116">자동으로 만들어진 기본 정책</span><span class="sxs-lookup"><span data-stu-id="b1af8-116">Automatically created default policy</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b1af8-119">사용자 지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b1af8-119">Create custom policies</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b1af8-122">정책 설정<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b1af8-122">Policy settings<sup>\*</sup></span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b1af8-125">가장 설정</span><span class="sxs-lookup"><span data-stu-id="b1af8-125">Impersonation settings</span></span>||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b1af8-127">스푸핑 설정</span><span class="sxs-lookup"><span data-stu-id="b1af8-127">Spoof settings</span></span>|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b1af8-130">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="b1af8-130">Advanced phishing thresholds</span></span>||![확인 표시](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="b1af8-132"><sup>\*</sup>기본 정책에서 정책 이름과 설명은 읽기 전용이 고 (설명은 비어 있음) 정책이 적용 되는 사용자를 지정할 수 없습니다 (기본 정책은 모든 받는 사람에 게 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="b1af8-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="b1af8-133">피싱 방지 정책을 구성 하려면 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1af8-133">To configure anti-phishing policies, see the following topics:</span></span>

- [<span data-ttu-id="b1af8-134">EOP에서 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="b1af8-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="b1af8-135">Microsoft 365에서 ATP 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="b1af8-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="b1af8-136">이 항목의 나머지 부분에서는 피싱 방지 정책 및 ATP 피싱 방지 정책에서 사용할 수 있는 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-136">The rest of this topic describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="b1af8-137">스푸핑 설정</span><span class="sxs-lookup"><span data-stu-id="b1af8-137">Spoof settings</span></span>

<span data-ttu-id="b1af8-138">스푸핑 이란 전자 메일 메시지의 보낸 사람 주소 (전자 메일 클라이언트에 표시 되는 발신자 주소가 전자 메일 원본의 도메인)와 일치 하지 않는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-138">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="b1af8-139">스푸핑에 대 한 자세한 내용은 [Microsoft 365에서 스푸핑 방지 보호](anti-spoofing-protection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-139">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b1af8-140">피싱 방지 정책 및 ATP 피싱 방지 정책에서는 다음과 같은 스푸핑 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-140">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b1af8-141">**스푸핑 방지 보호**: 스푸핑 방지 보호 기능을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-141">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="b1af8-142">이 옵션을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-142">We recommend that you leave it enabled.</span></span> <span data-ttu-id="b1af8-143">스푸핑 **인텔리전스 정책을** 사용 하 여 특정 스푸핑된 내부 및 외부 보낸 사람을 허용 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-143">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="b1af8-144">자세한 내용은 [Microsoft 365에 스푸핑 인텔리전스 구성](learn-about-spoof-intelligence.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-144">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b1af8-145">스푸핑 설정은 기본적으로 EOP의 기본 피싱 방지 정책, 기본 ATP 피싱 방지 정책 및 새로 만든 피싱 방지 정책 또는 ATP 피싱 방지 정책에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-145">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="b1af8-146">MX 레코드가 Microsoft 365를 가리키지 않는 경우 스푸핑 방지 보호를 사용 하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대 한 향상 된 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-146">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="b1af8-147">자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1af8-147">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="b1af8-148">차단 된 스푸핑된 보낸 사람에 게 보내는 메시지에 대해 수행할 작업을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-148">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="b1af8-149">**정크 메일 폴더로 메시지 이동**:이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-149">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="b1af8-150">메시지가 사서함에 배달 되 고 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-150">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b1af8-151">Exchange Online에서 사서함에 대해 정크 메일 규칙을 사용 하도록 설정 되어 있으면 메시지가 정크 메일 폴더로 이동 됩니다 (기본적으로 사용 하도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="b1af8-151">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b1af8-152">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-152">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="b1af8-153">**격리 메시지**: 의도 하지 않은 받는 사람 대신 메시지를 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-153">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b1af8-154">격리에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-154">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="b1af8-155">Microsoft 365의 격리</span><span class="sxs-lookup"><span data-stu-id="b1af8-155">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b1af8-156">Microsoft 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리</span><span class="sxs-lookup"><span data-stu-id="b1af8-156">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b1af8-157">Microsoft 365에서 사용자로 격리 된 메시지 찾기 및 릴리스</span><span class="sxs-lookup"><span data-stu-id="b1af8-157">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="b1af8-158">**인증 되지 않은 보낸 사람**: Outlook에서 미확인 보낸 사람 id를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-158">**Unauthenticated Sender**: Enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="b1af8-159">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-159">Specifically:</span></span>

  - <span data-ttu-id="b1af8-160">메시지가 SPF 또는 DKIM **검사를 통과 하지 않고 메시지가** DMARC 또는 [복합 인증](email-validation-and-authentication.md#composite-authentication)을 통과 하지 않는 경우 보낸 사람의 사진에 물음표 (?)가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-160">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

  - <span data-ttu-id="b1af8-161">From 태그 (chris@contoso.com <u>via</u> michelle@fabrikam.com)는 보낸 사람 주소 (전자 메일 클라이언트에 표시 되는 메시지 발신자)가 dkim 서명 또는 **메일 원본** 주소에 있는 도메인과 다른 경우에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-161">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="b1af8-162">이러한 주소에 대 한 자세한 내용은 [전자 메일 메시지 표준 개요](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-162">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

  <span data-ttu-id="b1af8-163">이러한 식별자가 특정 보낸 사람의 메시지에 추가 되지 않도록 하려면 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-163">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

  - <span data-ttu-id="b1af8-164">보낸 사람이 스푸핑 인텔리전스 정책에서 스푸핑할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-164">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="b1af8-165">자세한 내용은 [Microsoft 365에서 스푸핑 인텔리전스를 구성](learn-about-spoof-intelligence.md)합니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1af8-165">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  - <span data-ttu-id="b1af8-166">보낸 사람 도메인에 대 한 [전자 메일 인증을 구성](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-166">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
    - <span data-ttu-id="b1af8-167">보낸 사람의 사진에 있는 물음표의 경우 SPF 또는 DKIM이 가장 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-167">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
    - <span data-ttu-id="b1af8-168">Via 태그의 경우 DKIM 서명에서 도메인을 확인 하거나 보낸 **사람 주소에서** from 주소에 있는 도메인을 검색 합니다 (또는 하위 도메인의 하위 도메인이 됨).</span><span class="sxs-lookup"><span data-stu-id="b1af8-168">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

  <span data-ttu-id="b1af8-169">자세한 내용은 [Outlook.com 및 웹용 Outlook에서 의심 스러운 메시지 식별](https://support.office.com/article/3d44102b-6ce3-4f7c-a359-b623bec82206) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-169">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.office.com/article/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b1af8-170">ATP 피싱 방지 정책에서 배타적 설정</span><span class="sxs-lookup"><span data-stu-id="b1af8-170">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b1af8-171">이 섹션에서는 ATP 피싱 방지 정책 에서만 사용할 수 있는 정책 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-171">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b1af8-172">기본적으로 ATP 배타적 설정은 기본 정책 에서도 구성 되거나 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-172">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="b1af8-173">이러한 기능을 활용 하려면 기본 ATP 피싱 방지 정책에서 사용 하도록 설정 및 구성 하거나 사용자 지정 ATP 피싱 방지 정책을 만들고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-173">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="policy-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b1af8-174">ATP 피싱 방지 정책의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b1af8-174">Policy settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b1af8-175">다음 정책 설정은 ATP 피싱 방지 정책 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-175">The following policy settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b1af8-176">**이름**: 기본 피싱 방지 정책의 이름은 바꿀 수 없지만 직접 만든 사용자 지정 정책의 이름을 바꾸거나 이름을 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-176">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="b1af8-177">**설명** 기본 피싱 방지 정책에 설명을 추가할 수는 없지만 만든 사용자 지정 정책에 대 한 설명을 추가 및 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-177">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="b1af8-178">**적용 대상**: ATP 피싱 방지 정책이 적용 되는 내부 받는 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-178">**Applied to**: Identifies internal recipients that the ATP anti-phishing policy applies to.</span></span> <span data-ttu-id="b1af8-179">이 값은 사용자 지정 정책에 필요 하며 기본 정책에서는 사용할 수 없습니다 (기본 정책은 모든 받는 사람에 게 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="b1af8-179">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

    <span data-ttu-id="b1af8-180">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-180">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b1af8-181">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="b1af8-181">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b1af8-182">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b1af8-182">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="b1af8-183">**받는 사람**: 조직에 있는 하나 이상의 사서함, 메일 사용자 또는 메일 연락처입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-183">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="b1af8-184">**받는 사람은**조직에 있는 하나 이상의 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-184">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="b1af8-185">**받는 사람 도메인**: Microsoft 365에서 구성 된 허용 도메인 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-185">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="b1af8-186">다음의 **경우를 제외 하**고 규칙에 대 한 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-186">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="b1af8-187">설정 및 동작은 다음과 같은 조건과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-187">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="b1af8-188">**받는 사람은**</span><span class="sxs-lookup"><span data-stu-id="b1af8-188">**Recipient is**</span></span>
    - <span data-ttu-id="b1af8-189">**받는 사람이 다음의 구성원임**</span><span class="sxs-lookup"><span data-stu-id="b1af8-189">**Recipient is a member of**</span></span>
    - <span data-ttu-id="b1af8-190">**받는 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="b1af8-190">**The recipient domain is**</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b1af8-191">ATP 피싱 방지 정책의 가장 설정</span><span class="sxs-lookup"><span data-stu-id="b1af8-191">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b1af8-192">가장은 메시지의 보낸 사람 또는 보낸 사람의 전자 메일 도메인이 실제 보낸 사람이 나 도메인과 비슷한 모습입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-192">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="b1af8-193">도메인 contoso.com 가장의 예는 ćóntoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-193">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>

- <span data-ttu-id="b1af8-194">사용자 michelle@contoso.com 가장의 예는 michele@contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-194">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="b1af8-195">그렇지 않은 경우에는 받는 사람을 속이기 위한 것을 제외 하면 가장 된 도메인이 합법적 (등록 된 도메인, 구성 된 전자 메일 인증 레코드 등)으로 간주 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-195">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="b1af8-196">다음 가장 설정은 ATP 피싱 방지 정책 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-196">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b1af8-197">**보호할 사용자**: 지정 된 내부 또는 외부 사용자가 가장 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-197">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="b1af8-198">예를 들어 임원 (내부) 및 보드 구성원 (외부) 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-198">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="b1af8-199">내부 및 외부 주소를 최대 60 개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-199">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="b1af8-200">이 보호 된 사용자 목록은 **적용** 된 설정에서 정책이 적용 되는 받는 사람 목록과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-200">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b1af8-201">예를 들어 Apodaca 그룹에 적용 되는 정책에서 Felipe (felipea@contoso.com)을 보호 된 사용자로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-201">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="b1af8-202">Felipe Apodaca 가장이 구성 된 임원 그룹의 구성원에 게 전송 되는 인바운드 메시지는 정책 (가장 한 사용자를 위해 구성한 작업)에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-202">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="b1af8-203">**보호할 도메인**: 지정 된 도메인이 가장 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-203">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="b1af8-204">예를 들어 소유한 모든 도메인 ([허용 도메인](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 또는 특정 도메인 (사용자가 소유한 도메인 또는 파트너 도메인)</span><span class="sxs-lookup"><span data-stu-id="b1af8-204">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="b1af8-205">이 보호 된 도메인 목록은 **적용** 된 설정에서 정책을 적용 하는 도메인 목록과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-205">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b1af8-206">예를 들어 tailspintoys.com 라는 그룹의 구성원에 게 적용 되는 정책에서 보호 된 도메인으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-206">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="b1af8-207">Tailspintoys.com이 가장 된 임원 그룹의 구성원에 게 전송 되는 인바운드 메시지는 정책 (가장 한 도메인에 대해 구성한 작업)에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-207">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="b1af8-208">**보호 된 사용자 또는 도메인에 대 한 작업**: 정책의 보호 된 사용자 및 보호 된 도메인에 대 한 가장 시도를 포함 하는 인바운드 메시지에 대해 수행할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-208">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="b1af8-209">보호 된 사용자의 가장에 대해 서로 다른 작업을 지정 하 고 보호 된 도메인의 가장을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-209">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="b1af8-210">**작업 적용 안 함**</span><span class="sxs-lookup"><span data-stu-id="b1af8-210">**Don't apply any action**</span></span>

  - <span data-ttu-id="b1af8-211">**메시지를 다른 전자 메일 주소로 리디렉션**: 받는 사람 대신 지정 된 받는 사람에 게 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-211">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="b1af8-212">**정크 메일 폴더로 메시지 이동**: 메시지가 사서함에 배달 되 고 정크 메일 폴더로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-212">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b1af8-213">Exchange Online에서 사서함에 대해 정크 메일 규칙을 사용 하도록 설정 되어 있으면 메시지가 정크 메일 폴더로 이동 됩니다 (기본적으로 사용 하도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="b1af8-213">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b1af8-214">자세한 내용은 [Microsoft 365에서 Exchange Online 사서함의 정크 메일 설정 구성을](configure-junk-email-settings-on-exo-mailboxes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-214">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="b1af8-215">**격리 메시지**: 의도 하지 않은 받는 사람 대신 메시지를 격리로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-215">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b1af8-216">격리에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1af8-216">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="b1af8-217">Microsoft 365의 격리</span><span class="sxs-lookup"><span data-stu-id="b1af8-217">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b1af8-218">Microsoft 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리</span><span class="sxs-lookup"><span data-stu-id="b1af8-218">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b1af8-219">Microsoft 365에서 사용자로 격리 된 메시지 찾기 및 릴리스</span><span class="sxs-lookup"><span data-stu-id="b1af8-219">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="b1af8-220">**메시지를 배달 하 고 숨은 참조 줄에 다른 주소 추가**: 받는 사람에 게 메시지를 배달 하 고 자동으로 지정한 받는 사람에 게 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-220">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="b1af8-221">**메시지를 배달 하기 전에 삭제**: 모든 첨부 파일을 포함 하 여 전체 메시지를 자동으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-221">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="b1af8-222">**안전 팁**: 가장 검사에 실패 하는 메시지를 표시 하는 다음과 같은 가장 안전 팁을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-222">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="b1af8-223">**가장 한 사용자**: 보낸 사람 주소에는 보호 된 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-223">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="b1af8-224">**가장 한 도메인**: 보낸 사람 주소에는 보호 된 도메인이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-224">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="b1af8-225">**이상한 문자**: 보낸 사람 주소에는 제한 된 발신자 또는 도메인에 이상한 기호, 텍스트 또는 대/소문자가 혼합 된 예외적인 문자 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-225">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="b1af8-226">**사서함 인텔리전스**: 자주 대화 상대와 사용자 전자 메일 패턴을 결정 하는 인공 지능 (인공 지능)을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-226">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="b1af8-227">이 설정을 사용 하면 이러한 연락처에서 합법적인 전자 메일과 위장 된 메일을 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-227">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="b1af8-228">사서함 인텔리전스는 Exchange Online 사서함에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-228">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="b1af8-229">**사서함 인텔리전스 기반 가장 보호**: 각 사용자의 개별 보낸 사람 맵에 따라 향상 된 가장 결과를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-229">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="b1af8-230">이 인텔리전스를 사용 하면 Microsoft 365에서 사용자 가장 검색을 사용자 지정 하 고 가양성을 보다 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-230">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="b1af8-231">사용자 가장이 검색 되 면 메시지에 대해 수행할 특정 작업을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-231">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="b1af8-232">**작업 적용 안 함**</span><span class="sxs-lookup"><span data-stu-id="b1af8-232">**Don't apply any action**</span></span>
  - <span data-ttu-id="b1af8-233">**메시지를 다른 전자 메일 주소로 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="b1af8-233">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="b1af8-234">**정크 메일 폴더로 메시지 이동**</span><span class="sxs-lookup"><span data-stu-id="b1af8-234">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="b1af8-235">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="b1af8-235">**Quarantine the message**</span></span>
  - <span data-ttu-id="b1af8-236">**메시지를 배달 하 고 숨은 참조 줄에 다른 주소 추가**</span><span class="sxs-lookup"><span data-stu-id="b1af8-236">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="b1af8-237">**메시지를 배달 하기 전에 삭제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b1af8-237">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="b1af8-238">**신뢰할 수 있는 보낸 사람 및 도메인**: 가장 보호 설정에 대 한 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-238">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="b1af8-239">지정 된 보낸 사람 및 보낸 사람 도메인의 메시지는 정책의 가장 기반 공격으로 분류 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-239">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="b1af8-240">즉, 보호 된 보낸 사람, 보호 된 도메인 또는 사서함 인텔리전스 보호에 대 한 작업은 이러한 신뢰할 수 있는 보낸 사람 또는 보낸 사람 도메인에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-240">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="b1af8-241">이러한 목록의 최대 제한은 약 1000 엔트리입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-241">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="b1af8-242">ATP 피싱 방지 정책의 고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="b1af8-242">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="b1af8-243">다음 advanced 피싱 임계값은 ATP 피싱 사기 정책 에서만 사용할 수 있으며,이는 피싱 결과을 확인 하기 위해 메시지에 기계 학습 모델을 적용할 민감도를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-243">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="b1af8-244">**1-Standard**:이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-244">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="b1af8-245">메시지에 대해 수행 되는 작업의 심각도는 메시지가 피싱 인 신뢰도 (낮음, 중간, 높음, 높음 신뢰도)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-245">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="b1af8-246">예를 들어 매우 높은 확신을 가진 피싱으로 식별 되는 메시지는 가장 심각 하 게 적용 되는 작업을 수행 하지만 낮은 수준의 확신을 가진 피싱으로 식별 된 메시지에는 덜 심각한 작업이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-246">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="b1af8-247">**2-적극적인**: 높은 확신을 가진 피싱으로 식별 되는 메시지는 높은 신뢰도로 식별 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-247">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b1af8-248">**3-적극적인**신뢰도를 확인 하는 피싱으로 식별 되는 메시지는 높은 수준의 신뢰도로 식별 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-248">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b1af8-249">**최대 적극적인**: 낮음, 중간 또는 높은 신뢰도의 피싱으로 식별 되는 메시지는 높은 신뢰도로 식별 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-249">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="b1af8-250">가양성 (잘못 된 것으로 표시 되는 메시지 양호)이 증가 하면이 설정이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1af8-250">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="b1af8-251">권장 설정에 대 한 자세한 내용은 [OFFICE ATP 피싱 방지 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1af8-251">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>