---
title: 메일 흐름 규칙을 사용하여 대량 전자 메일 필터링
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 관리자는 EOP(Exchange Online Protection)에서 메일 흐름 규칙(전송 규칙)을 사용하여 대량 메일(회색 메일)을 식별하고 필터링하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f88358973648846d650700bb5939c052851c789
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615639"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="28751-103">메일 흐름 규칙을 사용하여 EOP에서 대량 전자 메일 필터링</span><span class="sxs-lookup"><span data-stu-id="28751-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="28751-104">Exchange Online 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 사서함이 있는 Microsoft 365 조직에서 EOP는 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용하여 인바운드 메시지에서 스팸 및 대량 메일(회색 메일)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="28751-105">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28751-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="28751-106">대량 메일을 필터링하는 더 많은 옵션을 사용하려는 경우 메일 흐름 규칙(전송 규칙)을 만들어 대량 메일에서 자주 발견되는 텍스트 패턴 또는 구를 검색하고 해당 메시지를 스팸으로 표시하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28751-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="28751-107">대량 메일에 대한 자세한 [](what-s-the-difference-between-junk-email-and-bulk-email.md) 내용은 EOP의 정크 메일과 대량 전자 메일의 차이점과 [BCL(대량 불만 수준)을 참조하세요.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="28751-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="28751-108">이 항목에서는 EAC(Exchange 관리 센터) 및 PowerShell(Exchange Online에 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell)에서 이러한 메일 흐름 규칙을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="28751-109">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="28751-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="28751-110">다음 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="28751-111">Exchange Online에서 Exchange Online의 기능 사용 권한에서 "메일 흐름" [항목을 참조하세요.](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)</span><span class="sxs-lookup"><span data-stu-id="28751-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>

  - <span data-ttu-id="28751-112">독립 실행형 EOP에는 기본적으로 OrganizationManagement, ComplianceManagement 및 RecordsManagement 역할에 할당되는 전송 규칙 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="28751-113">자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한을 참조하고 EAC를 사용하여 역할 그룹의 구성원 목록을 [수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="28751-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="28751-114">Exchange Online에서 EAC를 열하려면 [Exchange Online의 Exchange 관리 센터를 참조하세요.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="28751-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="28751-115">독립 실행형 EOP에서 EAC를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="28751-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="28751-116">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28751-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="28751-117">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28751-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="28751-118">Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28751-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="28751-119">Exchange Online의 메일 흐름 규칙(전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="28751-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="28751-120">Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)</span><span class="sxs-lookup"><span data-stu-id="28751-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="28751-121">Exchange Online의 메일 흐름 규칙 작업</span><span class="sxs-lookup"><span data-stu-id="28751-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="28751-122">예제에서 대량 메일을 식별하는 데 사용되는 단어 및 텍스트 패턴 목록은 전체적인 것이 아니며, 항목을 필요한 경우 추가하고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28751-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="28751-123">그러나 이러한 두 가지는 좋은 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="28751-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="28751-p107">ASCII 텍스트의 SMTP 서버 간에 바이너리 메시지를 전송하는 데 사용되는 MIME 콘텐츠 전송 인코딩 메서드에서 메시지가 디코딩된 *후* 메시지의 제목이나 다른 머리글 필드에 있는 단어 또는 텍스트 패턴이 검색됩니다. 조건이나 예외를 사용하여 메시지의 제목이나 다른 머리글 필드에 있는 원시(일반적으로, Base64) 인코딩된 값을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28751-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="28751-126">다음 절차에서는 전체 조직에 대해 대량 메시지를 스팸으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="28751-127">그러나 다른 조건을 추가하여 특정 받는 사람에게만 이러한 규칙을 적용할 수 있으므로 적극적인 필터링을 소수의 높은 대상 사용자에 대해 사용할 수 있지만 나머지 사용자(주로 등록한 대량 전자 메일을 받는 사용자)는 영향을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28751-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="28751-128">EAC를 사용하여 대량 전자 메일을 필터링하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="28751-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="28751-129">EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="28751-130">추가 **아이콘을** 클릭한 다음 새 규칙 ![ ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="28751-131">새 **규칙** 페이지가 열리면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="28751-132">**이름:** 규칙에 대해 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="28751-133">다른 **옵션을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-133">Click **More Options**.</span></span>

   - <span data-ttu-id="28751-134">**다음의 경우** 이 규칙을 적용합니다. 다음 설정 중 하나를 구성하여 정규식(RegEx) 또는 단어 또는 구를 사용하여 메시지의 콘텐츠를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="28751-135">**제목 또는 본문** \> **제목 또는 본문이** 다음 텍스트  패턴과 일치합니다. 나타나는 단어 또는 구 지정  대화 상자에서 다음 값 중 하나를 입력하고 아이콘 추가를 클릭한 다음 모든 값을 입력할 때까지 ![ ](../../media/ITPro-EAC-AddIcon.png) 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="28751-136">항목을 편집하려면 해당 항목을  선택하고 편집 ![ 아이콘을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="28751-137">항목을 제거하려면 해당 항목을 선택하고 **제거** ![ 아이콘을 ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="28751-138">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="28751-139">**제목 또는 본문** \> **제목이나 본문에** 다음 단어가  포함됩니다. 나타나는 단어 또는 구 지정 대화 상자에서  다음 값 중 하나를 입력하고 아이콘 추가를 클릭한 다음 모든 값을 입력할 때까지 ![ 반복합니다. ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="28751-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="28751-140">항목을 편집하려면 해당 항목을  선택하고 편집 ![ 아이콘을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="28751-141">항목을 제거하려면 해당 항목을 선택하고 **제거** ![ 아이콘을 ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="28751-142">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="28751-143">**다음을 선택합니다.** SCL(스팸 **지수)을** 설정하는 메시지 속성 \> **수정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="28751-144">나타나는 **SCL 지정** 대화 상자에서 다음 설정 중 하나를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="28751-145">메시지를 스팸으로 **표시하려면** **6을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="28751-146">스팸 방지 정책에서 스팸  필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**</span><span class="sxs-lookup"><span data-stu-id="28751-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="28751-147">메시지를 높은 신뢰도 **스팸으로 표시하려면** **9를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="28751-148">스팸 방지 정책에서 높은  신뢰도 스팸 필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**</span><span class="sxs-lookup"><span data-stu-id="28751-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="28751-149">SCL 값에 대한 자세한 내용은 [EOP의 SCL(스팸 지수)을 참조하세요.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="28751-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="28751-150">완료되면 **저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="28751-151">PowerShell을 사용하여 대량 전자 메일을 필터링하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="28751-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="28751-152">다음 구문을 사용하여 메일 흐름 규칙(정규식과 단어)을 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28751-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="28751-153">이 예에서는 항목의 앞부분에서와 동일한 정규식 목록을 사용하여 메시지를 Spam으로 설정하는 "대량 전자 메일 필터링 - RegEx"라는 새 규칙을 **만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="28751-154">이 예에서는 항목 앞부분의 동일한 단어 목록을 사용하여 메시지를 높은 신뢰도 스팸으로 설정하는 "대량 전자 메일 필터링 - 단어"라는 새 규칙을 **만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="28751-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="28751-155">자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28751-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="28751-156">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="28751-156">How do you know this worked?</span></span>

<span data-ttu-id="28751-157">대량 전자 메일을 필터링하도록 메일 흐름 규칙이 구성되어 있는지 확인을 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="28751-158">EAC에서 메일 흐름 **규칙으로** 이동하여 편집 아이콘을 클릭하는 규칙을 선택하고 \>  \> 설정을 \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="28751-159">PowerShell에서 규칙 이름으로 바꾸고 다음 명령을 실행하여 설정을 \<Rule Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="28751-160">외부 계정에서 구 또는 텍스트 패턴 중 하나를 포함하는 영향을 받는 사람에게 테스트 메시지를 보내고 결과를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="28751-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
