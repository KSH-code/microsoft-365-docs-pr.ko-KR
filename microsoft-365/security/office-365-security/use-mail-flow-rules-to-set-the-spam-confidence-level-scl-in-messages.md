---
title: 메시지의 SCL에 메일 흐름 규칙 사용
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 메일 흐름 규칙 (전송 규칙)을 만들어 메시지를 식별 하 고 Exchange Online Protection에서 메시지의 SCL (스팸 지 수)을 설정 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 444a7f2a8342102c2222cc734b2592f46632f8d3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035013"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="4a419-103">메일 흐름 규칙을 사용하여 메시지의 스팸 신뢰 수준(SCL) 설정</span><span class="sxs-lookup"><span data-stu-id="4a419-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="4a419-104">Exchange online 사서함이 없는 Microsoft 365 고객이 나 독립 실행형 EOP (Exchange Online Protection) 고객 인 경우 EOP에서는 스팸 방지 정책 (스팸 필터 정책 또는 콘텐츠 필터 정책이 라고도 함)을 사용 하 여 스팸 메일에 대 한 인바운드 메시지를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="4a419-105">자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a419-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="4a419-106">특정 메시지를 스팸으로 표시 하 여 스팸 필터링으로 검색 하거나 메시지를 표시 하 여 스팸 필터링을 건너뛰도록 하려면 메시지를 식별 하 고 SCL (스팸 지 수)을 설정 하는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="4a419-107">SCL에 대 한 자세한 내용은 [Office 365에서 scl (스팸](spam-confidence-levels.md)지 수)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a419-107">For more information about the SCL, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4a419-108">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="4a419-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4a419-109">이러한 절차를 수행 하려면 먼저 Exchange Online에서 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="4a419-110">특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="4a419-111">자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a419-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="4a419-112">Exchange Online에서 EAC를 열려면 exchange [online의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a419-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="4a419-113">Exchange Online의 메일 흐름 규칙에 대 한 자세한 내용은 [Exchange online의 메일 흐름 규칙 (전송 규칙)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a419-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="4a419-114">EAC를 사용 하 여 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="4a419-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="4a419-115">EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="4a419-116">![](../../media/ITPro-EAC-AddIcon.png) 추가 **아이콘 추가를 클릭 한** 다음 **새 규칙 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="4a419-117">**새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="4a419-118">**이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="4a419-119">**기타 옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-119">Click **More Options**.</span></span>

   - <span data-ttu-id="4a419-120">다음의 **경우이 규칙 적용**: 메시지를 식별할 조건을 하나 이상 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="4a419-121">자세한 내용은 [메일 흐름 규칙 조건 및 예외 (조건자)에서 Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a419-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="4a419-122">**다음을 수행**합니다. **메시지 속성** \> 수정을 선택 하 여 **SCL (스팸 지 수)을 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="4a419-123">**SCL 지정** 대화 상자가 나타나면 다음 값 중 하나를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="4a419-124">**스팸 필터링 바이패스**: 그러면 SCL이-1로 설정 되므로 메시지는 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-124">**Bypass spam filtering**: This sets the SCL to -1, which means the messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="4a419-125">스팸 필터링을 건너뛰도록 메시지를 허용 하는 경우에 특히 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="4a419-126">공격자는이 보안 문제를 사용 하 여 피싱 및 기타 악의적인 메시지를 조직에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="4a419-127">메일 흐름 규칙은 보낸 사람의 전자 메일 주소 또는 도메인을 초과 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="4a419-128">자세한 내용은 [Office 365에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a419-128">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="4a419-129">**0 ~ 4**: 추가 처리를 위해 스팸 필터링을 통해 메시지가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="4a419-130">**5 또는 6**: 메시지가 **스팸으로**표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="4a419-131">스팸 방지 정책에서 **스팸** 필터링 verdicts에 대해 구성한 작업이 메시지에 적용 됩니다 (기본값은 **정크 메일 폴더로 메시지 이동**).</span><span class="sxs-lookup"><span data-stu-id="4a419-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="4a419-132">**7-9**: 메시지가 **높은 신뢰도 스팸으로**표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="4a419-133">스팸 방지 정책에서 **높은 신뢰도의 스팸** 필터링 verdicts에 대해 구성한 작업은 메시지에 적용 됩니다 (기본값은 **정크 메일 폴더로 메시지 이동**).</span><span class="sxs-lookup"><span data-stu-id="4a419-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="4a419-134">규칙에 대해 원하는 추가 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="4a419-135">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4a419-136">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="4a419-136">How do you know this worked?</span></span>

<span data-ttu-id="4a419-137">이 프로시저가 제대로 작동 하는지 확인 하려면 조직 내부의 사람에 게 전자 메일 메시지를 보내고 메시지에 대해 수행 된 작업이 예상 대로 진행 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="4a419-138">예를 들어 **SCL (스팸** 지 수)이 **스팸 필터링을 무시**하도록 설정 하는 경우 메시지를 지정 된 받는 사람의 받은 편지 함으로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="4a419-139">그러나 **SCL (스팸** 지 수)을 **9**로 설정 하 고 해당 콘텐츠 필터 정책에 대 한 **신뢰도가 높은 스팸** 작업을 정크 메일 폴더로 이동 하는 경우에는 해당 메시지를 지정 된 받는 사람의 정크 메일 폴더로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a419-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
