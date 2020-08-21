---
title: 메시지에서 SCL로 메일 전송 규칙 사용
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
description: Exchange Online Protection에서 메일 흐름 규칙(전송 규칙)을 사용하여 메시지를 식별하고 메시지의 SCL(스팸 지수)을 설정하는 방법을 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827376"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="aa540-103">메일 흐름 규칙을 사용하여 EOP 메시지의 스팸 신뢰 수준(SCL) 설정</span><span class="sxs-lookup"><span data-stu-id="aa540-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

<span data-ttu-id="aa540-104">Exchange Online 사서함이 있는 Microsoft 365 조직에서 EOP는 스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)을 사용하여 인바운드 메시지에서 스팸을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="aa540-105">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa540-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="aa540-106">특정 메시지가 스팸 필터링으로 검색되기 전에 도와도 스팸으로 표시하거나 스팸 필터링을 건너뛰기 위해 메시지를 표시하려는 경우 메일 흐름 규칙(전송 규칙이라고도 함)을 만들고 메시지를 식별하고 SCL(스팸 지수)을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="aa540-107">SCL에 대한 자세한 내용은 [EOP의 SCL(스팸 지수)을 참조하세요.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="aa540-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aa540-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="aa540-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aa540-109">이러한 절차를 수행하려면 Exchange Online에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="aa540-110">특히 조직 **관리,** 준수 관리 및 **레코드** 관리 **역할에는**할당된 전송 규칙 역할을 **할당받아도 기본적으로 할당되어** 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="aa540-111">자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa540-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="aa540-112">Exchange Online에서 EAC를 열려면 Exchange Online의 [Exchange 관리 센터를 참조하세요.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="aa540-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="aa540-113">Exchange Online의 메일 흐름 규칙에 대한 자세한 내용은 Exchange [Online의 메일 흐름 규칙(전송 규칙)을 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="aa540-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="aa540-114">EAC를 사용하여 메시지의 SCL을 설정하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="aa540-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="aa540-115">EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="aa540-116">아이콘 **추가를** ![ 클릭한 다음 새 규칙 ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aa540-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="aa540-117">\*\* 새\*\* 규칙 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="aa540-118">**이름:** 규칙을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="aa540-119">기타 **옵션을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="aa540-119">Click **More Options**.</span></span>

   - <span data-ttu-id="aa540-120">**다음의 경우 이 규칙을**적용하려면 하나 이상의 조건을 선택하여 메시지를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="aa540-121">자세한 내용은 [Exchange Online에서 메일 흐름 규칙 조건 및 예외(조건자)를 참조하세요.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="aa540-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="aa540-122">**다음 단계를** **수행합니다. 메시지** \> **속성을 선택하면 SCL(스팸 지수)이 설정되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="aa540-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="aa540-123">**나타나는 SCL** 지정 대화 상자에서 다음 값 중 하나를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="aa540-124">**스팸 필터링 무시**: 메시지가 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="aa540-125">메시지가 스팸 필터링을 건너뛸 수 있도록 하는 경우 매우 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="aa540-126">공격자는 이 취약성을 사용하여 피싱 및 기타 악성 메시지를 조직에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="aa540-127">메일 흐름 규칙에는 보낸 사람의 전자 메일 주소 또는 도메인 만 둘 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="aa540-128">자세한 내용은 [EOP에서 수신 허용 - 보낸 사람 목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="aa540-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="aa540-129">**0 ~ 4:** 메시지가 추가 처리를 위해 스팸 필터링을 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="aa540-130">**5 또는 6**: 메시지가 스팸으로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="aa540-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="aa540-131">스팸 방지 정책에서 스팸 필터링 **결과에** 대해 구성한 작업은 메시지에 적용됩니다(기본값은 **메시지를 정크 메일 폴더로 이동).**</span><span class="sxs-lookup"><span data-stu-id="aa540-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="aa540-132">**7~9:** 메시지가 높은 **신뢰도의 스팸으로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="aa540-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="aa540-133">스팸 방지 정책에서 높은 **스팸** 필터링 결과에 대해 구성한 작업은 메시지에 적용됩니다(기본값은 **메시지를 정크 메일 폴더로 이동).**</span><span class="sxs-lookup"><span data-stu-id="aa540-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="aa540-134">규칙에 사용할 추가 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="aa540-135">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="aa540-136">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="aa540-136">How do you know this worked?</span></span>

<span data-ttu-id="aa540-137">이 절차가 제대로 작동하는지 확인하려면 조직 내부의 누재자에게 전자 메일 메시지를 보내고 메시지에 대해 수행된 작업이 예상대로 수행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="aa540-138">예를 들어 **스팸 필터링 무시하도록 SCL(스팸 지수)을** **설정한**경우 해당 메시지는 지정된 받는 사람의 받은 편지함으로 보내지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa540-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="aa540-139">그러나 해당 스팸 방지 정책에 대한 스팸 지수(SCL)를 **High confidence spam** **9로**설정하고 해당 스팸 방지 정책에 대한 높은 신뢰도 스팸 작업을 설정한 경우 지정된 받는 사람의 정크 메일 폴더로 메시지가 전송됩니다. **set the spam confidence level (SCL)**</span><span class="sxs-lookup"><span data-stu-id="aa540-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
