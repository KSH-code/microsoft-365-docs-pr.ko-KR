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
description: 관리자는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 사용 하 여 사용자가 Microsoft에 보고 하는 메시지의 복사본을 수신 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 9798e808470a506da3d6dff65a5ea91934c1690d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195870"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="3a4bb-103">메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인</span><span class="sxs-lookup"><span data-stu-id="3a4bb-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3a4bb-104">Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (exchange online Protection) 조직에 사서함이 있는 경우 사용자가 [보고서 메시지 및 파일](report-junk-email-messages-to-microsoft.md)에 설명 된 대로 microsoft에 분석을 위해 microsoft에 메시지를 보고 하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="3a4bb-105">사용자가 Microsoft에 보고 하는 메시지를 찾는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들 수 있으며, 이러한 보고 된 메시지의 복사본을 받도록 숨은 참조 받는 사람을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="3a4bb-106">EAC (exchange 관리 센터) 및 PowerShell (exchange online 사서함이 없는 조직에 대 한 사서함이 있는 Microsoft 365 조 직의 경우 exchange online PowerShell을 사용 하는 경우, 독립 실행형 EOP PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3a4bb-107">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="3a4bb-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3a4bb-108">이러한 절차를 수행 하려면 먼저 Exchange Online 또는 EOP에서 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="3a4bb-109">특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="3a4bb-110">자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="3a4bb-111">EAC를 열려면 [독립 실행형 EOP에서 Exchange Online 또는 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md) [의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3a4bb-112">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3a4bb-113">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3a4bb-114">Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="3a4bb-115">Exchange Online의 메일 흐름 규칙 (전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="3a4bb-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="3a4bb-116">메일 흐름 규칙 조건 및 예외 (조건자)가 Exchange Online에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="3a4bb-117">Exchange Online의 메일 흐름 규칙 동작</span><span class="sxs-lookup"><span data-stu-id="3a4bb-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="3a4bb-118">EAC를 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="3a4bb-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="3a4bb-119">EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="3a4bb-120">추가 아이콘 추가를 **클릭 한** ![ ](../../media/ITPro-EAC-AddIcon.png) 다음 **새 규칙 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="3a4bb-121">**새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3a4bb-122">**이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="3a4bb-123">예를 들어 숨은 참조 메시지는 Microsoft에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="3a4bb-124">**기타 옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-124">Click **More Options**.</span></span>

   - <span data-ttu-id="3a4bb-125">다음의 **경우에이 규칙 적용**: 표시 되 **는 단어** \> **address includes any of these words** **또는 구 지정** 대화 상자에 다음 값 중 하나를 입력 하 고 추가 아이콘 **추가** ![ 를 클릭 ](../../media/ITPro-EAC-AddIcon.png) 한 다음 모든 값을 입력할 때까지 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="3a4bb-126">항목을 편집 하려면 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-EditIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="3a4bb-127">항목을 제거 하려면 선택 하 고 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-DeleteIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="3a4bb-128">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="3a4bb-129">**다음을 수행**합니다. **Add recipients** \> **숨은 참조 상자에**받는 사람 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="3a4bb-130">대화 상자가 나타나면 추가 하려는 받는 사람을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="3a4bb-131">작업을 마친 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="3a4bb-132">규칙을 감사 하 고 규칙을 테스트 하며 특정 기간 동안 규칙을 활성화 하 고 기타 설정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="3a4bb-133">규칙을 적용 하기 전에 테스트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="3a4bb-134">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="3a4bb-135">PowerShell을 사용 하 여 보고 된 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="3a4bb-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="3a4bb-136">이 예에서는이 항목에 설명 된 방법을 사용 하 여 Microsoft에 보고 되는 전자 메일 메시지를 찾아서 사용자 laura@contoso.com 및 julia@contoso.com를 숨은 참조 받는 사람으로 추가 하는 숨은 참조 메시지 라는 이름의 새 메일 흐름 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="3a4bb-137">자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3a4bb-138">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="3a4bb-138">How do you know this worked?</span></span>

<span data-ttu-id="3a4bb-139">보고 된 메시지의 복사본을 수신 하도록 메일 흐름 규칙을 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="3a4bb-140">EAC에서 **메일 흐름** \> **규칙** 을 \> 선택 하 \> **Edit** ![ 고 편집 아이콘 편집 ](../../media/ITPro-EAC-EditIcon.png) 을 클릭 한 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="3a4bb-141">PowerShell에서 다음 명령을 실행 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="3a4bb-142">보고 전자 메일 주소 중 하나로 테스트 메시지를 보내 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4bb-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
