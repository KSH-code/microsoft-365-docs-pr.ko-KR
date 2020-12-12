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
description: 관리자는 메일 흐름 규칙(전송 규칙)을 사용하여 사용자가 Microsoft에 보고하는 메시지의 복사본을 받는 방법을 배울 수 있습니다.
ms.openlocfilehash: 0f3046c9d1962366ffd75353347b6cf7b72afd14
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659859"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="d45e8-103">메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인</span><span class="sxs-lookup"><span data-stu-id="d45e8-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d45e8-104">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 보고서 메시지 및 파일에 설명된 바와 같이 사용자가 분석을 위해 Microsoft에 메시지를 보고하는 여러 가지 방법이 [있습니다.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d45e8-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="d45e8-105">사용자가 Microsoft에 보고하는 메시지를 받도록 메일 흐름 규칙(전송 규칙)을 만들 수 있으며, 이러한 보고된 메시지의 복사본을 받도록 Bcc 받는 사람을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="d45e8-106">EAC(Exchange 관리 센터) 및 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell)에서 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d45e8-107">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d45e8-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d45e8-108">이 문서의 절차를 수행하려면 먼저 Exchange Online 또는 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-108">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="d45e8-109">특히 조직 관리,  준수 관리(전역 관리자) 및  **레코드** 관리 역할 그룹에 기본적으로 할당되는 전송 규칙 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-109">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="d45e8-110">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d45e8-110">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="d45e8-111">Exchange Online의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d45e8-111">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="d45e8-112">독립 실행형 EOP의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d45e8-112">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="d45e8-113">EAC를 사용하여 역할 그룹의 구성원 목록 수정</span><span class="sxs-lookup"><span data-stu-id="d45e8-113">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="d45e8-114">Exchange Online에서 EAC를 열하려면 [Exchange Online의 Exchange 관리 센터를 참조하세요.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="d45e8-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="d45e8-115">독립 실행형 EOP에서 EAC를 열하려면 독립 실행형 [EOP의 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="d45e8-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="d45e8-116">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d45e8-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d45e8-117">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d45e8-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d45e8-118">Exchange Online 및 독립 실행형 EOP의 메일 흐름 규칙에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d45e8-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="d45e8-119">Exchange Online의 메일 흐름 규칙(전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="d45e8-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="d45e8-120">Exchange Online의 메일 흐름 규칙 조건 및 예외(조건자)</span><span class="sxs-lookup"><span data-stu-id="d45e8-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="d45e8-121">Exchange Online의 메일 흐름 규칙 작업</span><span class="sxs-lookup"><span data-stu-id="d45e8-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="d45e8-122">EAC를 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="d45e8-122">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="d45e8-123">EAC에서 **메일 흐름** \> **규칙** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-123">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d45e8-124">추가 **아이콘을** 클릭한 다음 새 규칙 ![ ](../../media/ITPro-EAC-AddIcon.png) **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d45e8-124">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="d45e8-125">새 **규칙** 페이지가 열리면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-125">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d45e8-126">**이름:** 규칙에 대해 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-126">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="d45e8-127">예를 들어 Microsoft에 Bcc 메시지 보고</span><span class="sxs-lookup"><span data-stu-id="d45e8-127">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="d45e8-128">다른 **옵션을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d45e8-128">Click **More Options**.</span></span>

   - <span data-ttu-id="d45e8-129">**다음의** 경우 이  규칙을 적용합니다. 받는 사람 주소에 다음 단어가 포함된 경우 선택: 나타나는 단어 또는 구 지정 대화 상자에서 다음 값 중 하나를 입력하고 아이콘 추가를 클릭한 다음 모든 값을 입력할 때까지 \>    ![ ](../../media/ITPro-EAC-AddIcon.png) 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-129">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="d45e8-130">항목을 편집하려면 해당 항목을  선택하고 편집 ![ 아이콘을 ](../../media/ITPro-EAC-EditIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-130">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="d45e8-131">항목을 제거하려면 해당 항목을 선택하고 **제거** ![ 아이콘을 ](../../media/ITPro-EAC-DeleteIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-131">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="d45e8-132">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-132">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="d45e8-133">**다음을 선택합니다.** Bcc 상자에  \> **받는 사람 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d45e8-133">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="d45e8-134">대화 상자가 나타나면 추가할 받는 사람을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-134">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="d45e8-135">작업을 마친 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-135">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="d45e8-136">규칙을 감사하고, 규칙을 테스트하고, 특정 기간 동안 규칙을 활성화하고, 기타 설정을 추가로 선택하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-136">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="d45e8-137">규칙을 적용하기 전에 규칙을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-137">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="d45e8-138">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-138">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="d45e8-139">PowerShell을 사용하여 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="d45e8-139">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="d45e8-140">이 예에서는 이 문서에 설명된 방법을 사용하여 Microsoft에 보고되는 전자 메일 메시지를 헌트하는 Bcc Messages Reported라는 새 메일 흐름 규칙을 만들고, Bcc 받는 사람으로 laura@contoso.com julia@contoso.com 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-140">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="d45e8-141">자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d45e8-141">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d45e8-142">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="d45e8-142">How do you know this worked?</span></span>

<span data-ttu-id="d45e8-143">보고된 메시지의 복사본을 받도록 메일 흐름 규칙을 구성 했 는 확인, 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-143">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="d45e8-144">EAC에서 메일 흐름 **규칙으로** 이동하여 편집 아이콘을 클릭하는 규칙을 선택하고 설정을 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-144">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="d45e8-145">PowerShell에서 다음 명령을 실행하여 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-145">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="d45e8-146">테스트 메시지를 보고 전자 메일 주소 중 하나에 보내고 결과를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="d45e8-146">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
