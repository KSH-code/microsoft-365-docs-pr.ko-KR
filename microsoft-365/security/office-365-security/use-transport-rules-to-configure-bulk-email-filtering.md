---
title: 메일 흐름 규칙을 사용하여 대량 전자 메일 필터링
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)에서 메일 흐름 규칙(전송 규칙)을 사용하여 대량 메일(회색 메일)을 식별하고 필터링하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8632a0b583ec0457ea1146f0e197321890414ce3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926681"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="de327-103">메일 흐름 규칙을 사용하여 EOP에서 대량 전자 메일 필터링</span><span class="sxs-lookup"><span data-stu-id="de327-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="de327-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="de327-104">**Applies to**</span></span>
- [<span data-ttu-id="de327-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="de327-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="de327-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="de327-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="de327-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de327-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="de327-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용하여 인바운드 메시지에서 스팸 및 대량 메일(회색 메일)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="de327-109">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de327-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="de327-110">대량 메일을 필터링하는 더 많은 옵션을 원하는 경우 메일 흐름 규칙(전송 규칙)을 만들어 대량 메일에서 자주 발견되는 텍스트 패턴 또는 구를 검색하고 이러한 메시지를 스팸으로 표시하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de327-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="de327-111">대량 메일에 대한 자세한 내용은 정크 메일과 대량 전자 메일의 차이점은 [무엇입니까?](what-s-the-difference-between-junk-email-and-bulk-email.md) 및 [EOP의 BCL(대량 불만 수준)을 참조하세요.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="de327-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="de327-112">이 항목에서는 EAC(Exchange 관리 센터) 및 PowerShell(Exchange Online에 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell)에서 이러한 메일 흐름 규칙을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de327-113">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="de327-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de327-114">이 문서의 절차를 수행하려면 먼저 Exchange Online 또는 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="de327-115">특히 조직 관리, 준수 관리(전역 관리자) 및  레코드 관리 역할 그룹에  기본적으로 할당되는 전송 규칙 역할이 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="de327-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="de327-116">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de327-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="de327-117">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="de327-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="de327-118">독립 실행형 EOP의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="de327-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="de327-119">EAC를 사용하여 역할 그룹의 구성원 목록 수정</span><span class="sxs-lookup"><span data-stu-id="de327-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="de327-120">Exchange Online에서 EAC를 열하려면 [Exchange Online의 Exchange 관리 센터를 참조하세요.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="de327-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="de327-121">독립 실행형 EOP에서 EAC를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="de327-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="de327-122">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de327-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="de327-123">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de327-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="de327-124">Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de327-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="de327-125">Exchange Online의 메일 흐름 규칙(전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="de327-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="de327-126">Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)</span><span class="sxs-lookup"><span data-stu-id="de327-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="de327-127">Exchange Online의 메일 흐름 규칙 작업</span><span class="sxs-lookup"><span data-stu-id="de327-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="de327-128">예제에서 대량 메일을 식별하는 데 사용되는 단어 및 텍스트 패턴 목록은 전체가 아니며, 필요한 경우 항목을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de327-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="de327-129">그러나 이 두 가지는 좋은 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="de327-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="de327-p107">ASCII 텍스트의 SMTP 서버 간에 바이너리 메시지를 전송하는 데 사용되는 MIME 콘텐츠 전송 인코딩 메서드에서 메시지가 디코딩된 *후* 메시지의 제목이나 다른 머리글 필드에 있는 단어 또는 텍스트 패턴이 검색됩니다. 조건이나 예외를 사용하여 메시지의 제목이나 다른 머리글 필드에 있는 원시(일반적으로, Base64) 인코딩된 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de327-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="de327-132">다음 절차에서는 전체 조직의 대량 메시지를 스팸으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="de327-133">그러나 이러한 규칙을 특정 받는 사람에게만 적용하는 또 다른 조건을 추가할 수 있으므로 대상이 높은 소수의 사용자에 대해 적극적인 필터링을 사용할 수 있지만 나머지 사용자(주로 등록한 대량 전자 메일을 받는 사용자)는 영향을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de327-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="de327-134">EAC를 사용하여 대량 전자 메일을 필터링하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="de327-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="de327-135">EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="de327-136">추가 **아이콘** ![ 추가를 ](../../media/ITPro-EAC-AddIcon.png) 클릭한 다음 새 규칙 만들기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="de327-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="de327-137">새 **규칙** 페이지가 열리면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="de327-138">**이름:** 규칙에 대한 설명이 있는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="de327-139">다른 **옵션을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de327-139">Click **More Options**.</span></span>

   - <span data-ttu-id="de327-140">**다음의 경우** 이 규칙을 적용합니다. 다음 설정 중 하나를 구성하여 정규식(RegEx) 또는 단어 또는 구를 사용하여 메시지의 콘텐츠를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="de327-141">**제목 또는 본문** \> **제목 또는 본문이** 다음 텍스트  패턴과 일치합니다. 나타나는 단어 또는 구 지정  대화 상자에서 다음 값 중 하나를 입력하고 아이콘 추가를 클릭한 다음 모든 값을 입력할 때까지 ![ ](../../media/ITPro-EAC-AddIcon.png) 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="de327-142">항목을 편집하려면 해당 항목을 선택하고 편집 편집 **아이콘 을** ![ ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="de327-143">항목을 제거하려면 해당 항목을 선택하고 제거 **아이콘 제거를** ![ ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="de327-144">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="de327-145">**제목 또는 본문** \> **제목 또는 본문에는** 다음 단어가  포함됩니다. 나타나는 단어 또는 구 지정 대화 상자에서  다음 값 중 하나를 입력하고 아이콘 추가를 클릭한 다음 모든 값을 입력할 때까지 ![ ](../../media/ITPro-EAC-AddIcon.png) 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="de327-146">항목을 편집하려면 해당 항목을 선택하고 편집 편집 **아이콘 을** ![ ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="de327-147">항목을 제거하려면 해당 항목을 선택하고 제거 **아이콘 제거를** ![ ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="de327-148">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="de327-149">**다음 작업을 합니다.** **메시지 속성** 수정 \> **SCL(스팸 지수)** 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="de327-150">나타나는 **SCL 지정** 대화 상자에서 다음 설정 중 하나를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="de327-151">메시지를 스팸으로 **표시하려면** **6 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="de327-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="de327-152">스팸 방지 정책에서 스팸  필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**</span><span class="sxs-lookup"><span data-stu-id="de327-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="de327-153">메시지를 높은 신뢰도 **스팸으로 표시하려면** **9 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="de327-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="de327-154">스팸 방지 정책에서 높은  지수의 스팸 필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 이동). </span><span class="sxs-lookup"><span data-stu-id="de327-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="de327-155">SCL 값에 대한 자세한 내용은 [EOP의 SCL(스팸 지수)을 참조하세요.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="de327-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="de327-156">완료되면 **저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de327-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="de327-157">PowerShell을 사용하여 대량 전자 메일을 필터링하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="de327-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="de327-158">다음 구문을 사용하여 메일 흐름 규칙(정규식과 단어)을 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de327-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="de327-159">이 예에서는 항목의 앞부분에서와 동일한 정규식 목록을 사용하여 메시지를 Spam으로 설정하는 "대량 전자 메일 필터링 - RegEx"라는 새 규칙을 **만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="de327-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="de327-160">이 예에서는 항목 앞부분의 동일한 단어 목록을 사용하여 메시지를 높은 지수 스팸으로 설정하는 "대량 전자 메일 필터링 - 단어"라는 새 규칙을 **만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="de327-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="de327-161">자세한 구문 및 매개변수 정보 [New-TransportRule](/powershell/module/exchange/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de327-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de327-162">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="de327-162">How do you know this worked?</span></span>

<span data-ttu-id="de327-163">대량 전자 메일을 필터링하도록 메일 흐름 규칙을 구성했는지 확인하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="de327-164">EAC에서 메일 흐름 **규칙으로** 이동하여 규칙 편집 편집 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 아이콘을 클릭하고 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="de327-165">PowerShell에서 규칙 이름으로 바꾸고 다음 명령을 실행하여 \<Rule Name\> 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="de327-166">외부 계정에서 구 또는 텍스트 패턴 중 하나를 포함하는 영향을 받는 사람에게 테스트 메시지를 보내고 결과를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="de327-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>