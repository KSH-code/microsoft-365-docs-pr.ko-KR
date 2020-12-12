---
title: 메시지에서 SCL에 메일 흐름 규칙 사용
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Exchange Online Protection에서 메시지를 식별하고 메시지의 SCL(스팸 지수)을 설정하는 메일 흐름 규칙(전송 규칙)을 만드는 방법을 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659840"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="3819f-103">메일 흐름 규칙을 사용하여 EOP의 메시지에서 SCL(스팸 지수) 설정</span><span class="sxs-lookup"><span data-stu-id="3819f-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3819f-104">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용하여 인바운드 메시지에서 스팸을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="3819f-105">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3819f-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3819f-106">스팸 필터링을 통해 검색되기 전에 특정 메시지를 스팸으로 표시하거나 스팸 필터링을 건너뛰게 하려는 경우 메일 흐름 규칙(전송 규칙)을 만들어 메시지를 식별하고 SCL(스팸 지수)을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="3819f-107">SCL에 대한 자세한 내용은 [EOP의 SCL(스팸 지수)을 참조하세요.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="3819f-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3819f-108">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="3819f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3819f-109">이 문서의 절차를 수행하려면 먼저 Exchange Online 또는 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-109">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="3819f-110">특히 조직 관리,  준수 관리(전역 관리자) 및  **레코드** 관리 역할 그룹에 기본적으로 할당되는 전송 규칙 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-110">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="3819f-111">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3819f-111">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="3819f-112">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="3819f-112">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="3819f-113">독립 실행형 EOP의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="3819f-113">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="3819f-114">EAC를 사용하여 역할 그룹의 구성원 목록 수정</span><span class="sxs-lookup"><span data-stu-id="3819f-114">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="3819f-115">Exchange Online에서 EAC를 열하려면 [Exchange Online의 Exchange 관리 센터를 참조하세요.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="3819f-115">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="3819f-116">독립 실행형 EOP에서 EAC를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="3819f-116">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3819f-117">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3819f-117">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3819f-118">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3819f-118">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3819f-119">Exchange Online 및 Exchange Online Protection의 메일 흐름 규칙에 대한 자세한 내용은 Exchange Online의 메일 흐름 [규칙(전송 규칙)을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="3819f-119">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="3819f-120">EAC를 사용하여 메시지의 SCL을 설정하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="3819f-120">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="3819f-121">EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-121">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="3819f-122">추가 **아이콘을** 클릭한 다음 새 규칙 ![ ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3819f-122">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="3819f-123">새 **규칙** 페이지가 열리면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-123">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3819f-124">**이름:** 규칙에 대해 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-124">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="3819f-125">다른 **옵션을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3819f-125">Click **More Options**.</span></span>

   - <span data-ttu-id="3819f-126">**다음의 경우** 이 규칙을 적용합니다. 메시지를 식별하는 조건을 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-126">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="3819f-127">자세한 내용은 Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)를 [참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="3819f-127">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="3819f-128">**다음을 선택합니다.** SCL(스팸 지수)을 설정하는 메시지 속성  \> **수정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3819f-128">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="3819f-129">나타나는 **SCL 지정** 대화 상자에서 다음 값 중 하나를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-129">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="3819f-130">**스팸 필터링 무시:** 메시지는 스팸 필터링을 건너뜁습니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-130">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="3819f-131">메시지에서 스팸 필터링을 건너뛸 수 있도록 허용하는 데 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-131">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="3819f-132">공격자는 이 취약성을 사용하여 피싱 및 기타 악성 메시지를 조직으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-132">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="3819f-133">메일 흐름 규칙에는 보낸 사람 전자 메일 주소나 도메인만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-133">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="3819f-134">자세한 내용은 [EOP에서 수신이 가능한 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="3819f-134">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="3819f-135">**0~4:** 메시지가 추가 처리를 위해 스팸 필터링을 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-135">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="3819f-136">**5 또는 6:** 메시지가 스팸으로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3819f-136">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="3819f-137">스팸 방지 정책에서 스팸  필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**</span><span class="sxs-lookup"><span data-stu-id="3819f-137">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="3819f-138">**7~9:** 메시지가 높은 신뢰도 **스팸으로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="3819f-138">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="3819f-139">스팸 방지 정책에서 높은  신뢰도 스팸 필터링 판정에 대해 구성한 작업이 메시지에 적용됩니다(기본값은 정크 메일 폴더로 메시지 **이동).**</span><span class="sxs-lookup"><span data-stu-id="3819f-139">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="3819f-140">규칙에 대해 원하는 추가 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-140">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="3819f-141">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-141">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3819f-142">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="3819f-142">How do you know this worked?</span></span>

<span data-ttu-id="3819f-143">이 절차가 올바르게 작동하고 있는지 확인하려면 조직 내부의 사람에게 전자 메일 메시지를 보내고 메시지에 대해 수행된 작업이 예상대로 수행된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-143">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="3819f-144">예를 들어 **SCL(스팸** 지수)을 스팸 필터링 무시로 설정한 경우 지정된 받는 사람의 받은 편지함으로 메시지를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-144">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="3819f-145">그러나 **SCL(스팸** 지수)을 **9로** 설정하고  적용 가능한 스팸 방지 정책에 대해 높은 신뢰도 스팸 작업을 수행하여 메시지를 정크 메일 폴더로 이동하는 경우 지정된 받는 사람의 정크 메일 폴더로 메시지가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="3819f-145">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
