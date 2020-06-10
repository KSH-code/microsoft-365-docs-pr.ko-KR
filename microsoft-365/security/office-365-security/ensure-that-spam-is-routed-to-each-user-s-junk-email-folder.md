---
title: 하이브리드 환경에서 EOP을 정크 스팸으로 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online Protection 하이브리드 환경에서 스팸을 사용자 정크 메일 폴더로 라우팅하는 방법을 알 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d8ba6aae599ee4dd327bd1ec82b46e8f3ee3ca8
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679123"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="242d0-103">하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP 구성</span><span class="sxs-lookup"><span data-stu-id="242d0-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="242d0-104">이 항목은 독립 실행형 EOP 고객을 위한 하이브리드 환경의 경우에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="242d0-105">이 항목은 Exchange Online 사서함이 있는 Microsoft 365 고객에 게는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="242d0-106">하이브리드 환경에서 독립 실행형 EOP (Exchange Online Protection) 고객 인 경우 온-프레미스 Exchange 조직을 구성 하 여 온-프레미스 사서함의 정크 메일 규칙이 정크 메일 폴더로 메시지를 이동할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="242d0-107">특히 다음과 같은 EOP의 스팸 지 수 헤더 및 값을 사용 하 여 메시지를 찾고 해당 메시지의 SCL (스팸 지 수)을 6으로 설정 하는 동작을 사용 하 여 온-프레미스 Exchange 조직에 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="242d0-108">`X-Forefront-Antispam-Report: SFV:SPM`(스팸 필터링을 통해 스팸으로 표시 된 메시지)</span><span class="sxs-lookup"><span data-stu-id="242d0-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="242d0-109">`X-Forefront-Antispam-Report: SFV:SKS`(스팸 필터링 전에 EOP의 메일 흐름 규칙에 따라 스팸으로 표시 된 메시지)</span><span class="sxs-lookup"><span data-stu-id="242d0-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="242d0-110">`X-Forefront-Antispam-Report: SFV:SKB`보낸 사람의 전자 메일 주소 또는 전자 메일 도메인이 EOP의 차단 된 보낸 사람 목록에 있거나 차단 된 도메인 목록에 있기 때문에 스팸 필터링에 의해 스팸으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="242d0-111">이러한 헤더 값에 대 한 자세한 내용은 [스팸 방지 메시지 헤더](anti-spam-message-headers.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="242d0-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="242d0-112">이 항목에서는 Exchange 관리 센터 (EAC) 및 온-프레미스 Exchange 조직의 exchange 관리 셸 (exchange PowerShell)에서 이러한 메일 흐름 규칙을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="242d0-113">온-프레미스 사용자의 정크 메일 폴더로 메시지를 배달 하는 대신 EOP에서 스팸 방지 정책을 구성 하 여 EOP의 스팸 메시지를 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="242d0-114">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="242d0-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="242d0-115">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="242d0-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="242d0-116">이러한 절차를 수행 하려면 먼저 온-프레미스 Exchange 환경에서 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="242d0-117">특히 **조직 관리**, **규정 준수 관리**및 **레코드 관리** 역할에 할당 되는 **전송 규칙** 역할을 기본적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="242d0-118">자세한 내용은 [역할 그룹에 구성원을 추가 합니다.](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="242d0-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="242d0-119">온-프레미스 Exchange 조직의 정크 메일 폴더로 배달 되는 메시지는 다음 설정을 조합 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="242d0-120">Exchange 관리 셸에서 [set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet에 대 한 _SCLJunkThreshold_ 매개 변수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="242d0-121">기본값은 4 이며이 값은 SCL 5 이상이 사용자의 정크 메일 폴더로 메시지를 배달 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="242d0-122">Exchange 관리 셸에서 [설정 된 사서함](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) Cmdlet의 _SCLJunkThreshold_ 매개 변수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="242d0-123">기본값은 비어 있음 ($null) 이며,이 값은 조직 설정이 사용 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="242d0-124">자세한 내용은 [EXCHANGE SCL (스팸 지 수) 임계값](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="242d0-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="242d0-125">사서함에서 정크 메일 규칙을 사용할 수 있는지 여부 (Exchange 관리 셸에서 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) Cmdlet의 _enabled_ 매개 변수 값이 $true)</span><span class="sxs-lookup"><span data-stu-id="242d0-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="242d0-126">배달 후 실제로 메시지를 정크 메일 폴더로 이동 하는 정크 메일 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="242d0-127">기본적으로 사서함에서는 정크 메일 규칙이 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="242d0-128">자세한 내용은 [사서함에 대 한 Exchange 스팸 방지 설정 구성을](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="242d0-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="242d0-129">Exchange 서버에서 EAC를 열려면 exchange [server의 exchange 관리 센터](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="242d0-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="242d0-130">Exchange 관리 셸을 열려면 [Exchange 관리 셸을 엽니다](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="242d0-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="242d0-131">온-프레미스 Exchange의 메일 흐름 규칙에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="242d0-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="242d0-132">Exchange Server의 메일 흐름 규칙</span><span class="sxs-lookup"><span data-stu-id="242d0-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="242d0-133">Exchange Server의 메일 흐름 규칙 조건 및 예외 (조건자)</span><span class="sxs-lookup"><span data-stu-id="242d0-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="242d0-134">Exchange Server의 메일 흐름 규칙 동작</span><span class="sxs-lookup"><span data-stu-id="242d0-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="242d0-135">EAC를 사용 하 여 EOP 스팸 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="242d0-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="242d0-136">EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="242d0-137">추가 아이콘 추가를 **클릭 하** ![ ](../../media/ITPro-EAC-AddIcon.png) 고 표시 되는 드롭다운에서 **새 규칙 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="242d0-138">**새 규칙** 페이지가 열리면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="242d0-139">**이름**: 규칙에 대 한 설명이 포함 된 고유 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="242d0-140">예시:</span><span class="sxs-lookup"><span data-stu-id="242d0-140">For example:</span></span>

     - <span data-ttu-id="242d0-141">EOP SFV:, SCL 6에 게 SPM</span><span class="sxs-lookup"><span data-stu-id="242d0-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="242d0-142">EOP SFV: SKS-SCL 6</span><span class="sxs-lookup"><span data-stu-id="242d0-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="242d0-143">EOP SFV: SKB-SCL 6</span><span class="sxs-lookup"><span data-stu-id="242d0-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="242d0-144">**기타 옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-144">Click **More Options**.</span></span>

   - <span data-ttu-id="242d0-145">다음의 **경우이 규칙 적용**: **메시지 헤더** 에 \> **다음 단어 포함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="242d0-146">**입력 텍스트 헤더** 에 표시 되는 단어 문장 입력에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="242d0-147">**텍스트 입력**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-147">Click **Enter text**.</span></span> <span data-ttu-id="242d0-148">표시 되는 **헤더 이름 지정** 대화 상자에서 **스팸 방지-Report** 를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="242d0-149">**단어 입력**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-149">Click  **Enter words**.</span></span> <span data-ttu-id="242d0-150">**단어 또는 구 지정** 대화 상자가 나타나면 EOP 스팸 헤더 값 (**SFV: SPM**, **Sfv: SKS**또는 **sfv: SKB**) 중 하나를 입력 하 고 추가 아이콘 추가를 **클릭 한** ![ ](../../media/ITPro-EAC-AddIcon.png) 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="242d0-151">**다음을 수행**합니다. **메시지 속성 수정을** 선택 하 여 \> **SCL (스팸 지 수)을 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="242d0-152">**SCL 지정** 대화 상자가 나타나면 **6** (기본값은 **5**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="242d0-153">작업이 끝나면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="242d0-154">남은 EOP 스팸 결과 값 (**Sfv: SPM**, **SFV: SKS**또는 **sfv: SKB**)에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="242d0-155">Exchange 관리 셸을 사용 하 여 EOP 스팸 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="242d0-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="242d0-156">세 가지 메일 흐름 규칙을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="242d0-157">예시:</span><span class="sxs-lookup"><span data-stu-id="242d0-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="242d0-158">자세한 구문 및 매개변수 정보 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="242d0-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="242d0-159">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="242d0-159">How do you know this worked?</span></span>

<span data-ttu-id="242d0-160">하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP를 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="242d0-161">EAC에서 **메일 흐름** 규칙으로 이동 하 고 \> **Rules**규칙을 선택한 다음 **Edit** ![ 편집 아이콘 편집을 클릭 하 여 ](../../media/ITPro-EAC-EditIcon.png) 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="242d0-162">Exchange 관리 셸에서 \<RuleName\> 메일 흐름 규칙의 이름으로 바꾸고 다음 명령을 사용 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="242d0-163">**스팸 메일에 대 한 아웃 바운드 메시지를 검사 하지**않는 외부 전자 메일 시스템에서, 해당 받는 사람에 게 요청 하지 않은 대량 전자 메일 (gtube) 메시지에 대 한 일반 테스트를 보낸 다음 해당 메시지가 정크 메일 폴더로 배달 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="242d0-164">GTUBE 메시지는 맬웨어 설정을 테스트하기 위한 EICAR(European Institute for Computer Antivirus Research) 텍스트 파일과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="242d0-165">GTUBE 메시지를 보내려면 전자 메일 메시지 본문에 공백이 나 줄 바꿈 없이 다음 텍스트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
