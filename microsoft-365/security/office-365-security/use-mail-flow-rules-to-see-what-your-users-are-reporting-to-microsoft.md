---
title: 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 관리자는 메일 흐름 규칙(전송 규칙이라고도 함)을 사용하여 사용자가 Microsoft에 보고하는 메시지 복사본을 수신하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827388"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="2de21-103">메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인</span><span class="sxs-lookup"><span data-stu-id="2de21-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="2de21-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에는 여러 가지 방법으로 Microsoft에 보고 메시지와 파일에 설명된 방식으로 Microsoft에 메시지를 [분석하도록 Microsoft에 보고할 수 있습니다.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2de21-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="2de21-105">사용자가 Microsoft에 보고하는 메시지를 찾는 메일 흐름 규칙(전송 규칙이라고도 함)을 만들 수 있고, 숨은 참조 수신자가 보고된 이러한 메시지의 복사본을 받도록 Bcc 를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="2de21-106">EAC(Exchange 관리 센터) 및 PowerShell(Exchange Online 사서함을 사용하는 조직의 경우 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2de21-107">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2de21-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2de21-108">이러한 절차를 수행하려면 먼저 Exchange Online 또는 EOP에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="2de21-109">특히 조직 **관리,** 준수 관리 및 **레코드** 관리 **역할에는**할당된 전송 규칙 역할을 **할당받아도 기본적으로 할당되어** 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="2de21-110">자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2de21-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="2de21-111">EAC를 열려면 [Exchange Online 또는 Exchange 관리 센터의 Exchange](https://docs.microsoft.com/Exchange/exchange-admin-center) [관리 센터(독립 실행형 EOP)를 참조하십시오.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="2de21-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2de21-112">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2de21-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2de21-113">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2de21-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2de21-114">Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2de21-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="2de21-115">Exchange Online의 메일 흐름 규칙(전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="2de21-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="2de21-116">Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)</span><span class="sxs-lookup"><span data-stu-id="2de21-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="2de21-117">Exchange Online의 메일 흐름 규칙 동작</span><span class="sxs-lookup"><span data-stu-id="2de21-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="2de21-118">EAC를 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="2de21-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="2de21-119">EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="2de21-120">아이콘 **추가를** ![ 클릭한 다음 새 규칙 ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2de21-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="2de21-121">\*\* 새\*\* 규칙 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2de21-122">**이름:** 규칙을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="2de21-123">예를 들어 Microsoft에 보고된 BCC 메시지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="2de21-124">기타 **옵션을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2de21-124">Click **More Options**.</span></span>

   - <span data-ttu-id="2de21-125">**다음 단어의 경우 이**규칙 적용 : **받는** 사람 주소에 다음 단어 중 하나를 포함 합니다. 나타나는 단어 또는 구 지정 대화 상자에서 다음 값 중 하나를 입력하고, 아이콘 추가를 클릭한 후 모든 값을 입력할 때까지 \> **address includes any of these words** **Specify words or phrases** **Add** ![ ](../../media/ITPro-EAC-AddIcon.png) 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="2de21-126">항목을 편집하려면 항목을 선택한 후 편집 **아이콘을** ![ 클릭합니다. ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="2de21-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="2de21-127">항목을 제거하려면 항목을 선택한 다음 제거 아이콘 **제거를** ![ 클릭합니다. ](../../media/ITPro-EAC-DeleteIcon.png)</span><span class="sxs-lookup"><span data-stu-id="2de21-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="2de21-128">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="2de21-129">**다음 작업을 수행합니다.** **Add recipients** \> **숨은 참조 상자에 받는 사람 추가**상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="2de21-130">대화 상자가 나타나면 추가할 받는 사람을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="2de21-131">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="2de21-132">규칙을 감사 및 테스트하고 특정 기간 동안 규칙을 활성화하는 등 다른 설정을 추가로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="2de21-133">규칙을 적용하기 전에 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="2de21-134">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="2de21-135">PowerShell을 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="2de21-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="2de21-136">이 예에서는 이 항목에 설명된 방법을 사용하여 Microsoft에 보고된 전자 메일 메시지를 찾는 Microsoft에 숨은 편지함이라는 새 메일 흐름 규칙을 만들고, 숨은 참조로 laura@contoso.com 및 julia@contoso.com 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="2de21-137">자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2de21-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2de21-138">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="2de21-138">How do you know this worked?</span></span>

<span data-ttu-id="2de21-139">보고된 메시지의 복사본을 받도록 메일 흐름 규칙을 구성되었는지 확인하려면 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="2de21-140">EAC에서 메일 흐름 **Mail flow** 규칙으로 \> **이동하여 규칙** \> 편집 \> 아이콘을 선택한 **다음** ![ ](../../media/ITPro-EAC-EditIcon.png) 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="2de21-141">PowerShell에서 다음 명령을 실행하여 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="2de21-142">보고 전자 메일 주소 중 하나로 테스트 메시지를 보내고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2de21-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
