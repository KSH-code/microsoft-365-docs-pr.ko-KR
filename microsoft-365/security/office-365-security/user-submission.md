---
title: 사용자 제출 정책
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 사용자가 보고하는 스팸 및 피싱 전자 메일을 수집하도록 사서함을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a23f27478d01092705a47d49884f200478348182
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583715"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="5d90d-103">사용자 제출 정책</span><span class="sxs-lookup"><span data-stu-id="5d90d-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5d90d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="5d90d-104">**Applies to**</span></span>
- [<span data-ttu-id="5d90d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5d90d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5d90d-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="5d90d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5d90d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d90d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5d90d-108">사서함이 Microsoft 365 조직에서 Exchange Online 악의적이거나 악의적이지 않은 것으로 보고하는 메시지를 받을 사서함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="5d90d-109">사용자가 다양한 보고 옵션을 사용하여 메시지를 전송할 때 이 사서함을 사용하여 메시지를 가로채거나(사용자 지정 사서함으로만 보내기) 메시지 복사본(사용자 지정 사서함 및 Microsoft로 보내기)을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="5d90d-110">이 기능은 다음 메시지 보고 옵션과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="5d90d-111">보고서 메시지 추가 기능</span><span class="sxs-lookup"><span data-stu-id="5d90d-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="5d90d-112">피싱 보고 추가 기능</span><span class="sxs-lookup"><span data-stu-id="5d90d-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="5d90d-113">[웹용 Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 기본 제공 보고(이전의 Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="5d90d-113">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="5d90d-114">iOS 및 Android용 Outlook 기본 제공 보고</span><span class="sxs-lookup"><span data-stu-id="5d90d-114">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="5d90d-115">웹용 웹 Outlook 보고를 사용하지 않도록 설정한 경우 [여기에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)사용자 제출을 사용하도록 설정하면 해당 설정이 다시 Outlook 웹에서 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="5d90d-116">지정한 사서함으로 메시지를 전달하도록 타사 메시지 보고 도구를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-116">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="5d90d-117">사용자가 보고한 메시지를 Microsoft에 직접 전달하는 대신 사용자 지정 사서함으로 배달하면 관리자가 관리자 제출을 사용하여 메시지를 선택적으로 수동으로 Microsoft에 보고할 [수 있습니다.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5d90d-117">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="5d90d-118">사용자 지정 사서함 선행 준비</span><span class="sxs-lookup"><span data-stu-id="5d90d-118">Custom mailbox prerequisites</span></span>

<span data-ttu-id="5d90d-119">다음 문서를 사용하여 사용자가 보고한 메시지가 사용자 지정 사서함으로 이동하도록 필수 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-119">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="5d90d-120">스팸 지수 설정 Exchange 메일 흐름 규칙을 만들어 사용자 지정 사서함에서 스팸 필터링을 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="5d90d-120">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="5d90d-121">SCL을 스팸 필터링 무시로 설정하는 [메시지의 SCL을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 설정하는 메일 흐름 규칙 만들기를 **참조합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-121">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **Bypass spam filtering**.</span></span>

- <span data-ttu-id="5d90d-122">사용자 지정 사서함에서 맬웨어에 대한 첨부 파일 검색을 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-122">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="5d90d-123">[Defender에서](set-up-safe-attachments-policies.md) 안전한 첨부 파일 정책 Office 365 설정 을 사용하여 안전한 첨부  파일 알 수 없는 맬웨어 응답에 대해 끄기 설정을 사용하여 안전한 첨부 파일 정책을 **만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-123">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="5d90d-124">사용자 지정 사서함의 메시지에 대해 URL 검색을 끄세요.</span><span class="sxs-lookup"><span data-stu-id="5d90d-124">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="5d90d-125">Defender에서 안전한 링크 정책 Office 365 설정 을 사용하여 메시지의 알  수 없는 악의적인 URL에 대한 작업 선택을 [해제로](set-up-safe-links-policies.md) 설정하여 안전한 링크 정책을 **만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-125">Use [Set up Safe Links policies in Defender for Office 365](set-up-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="5d90d-126">맬웨어 방지 정책을 만들어 맬웨어 제로 아워 자동 제거를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-126">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="5d90d-127">보안 [및 준수 &](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 사용하여 맬웨어 방지 정책을 만들어 맬웨어 제로 아워 자동 제거를 끄기로 **설정합니다.** </span><span class="sxs-lookup"><span data-stu-id="5d90d-127">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="5d90d-128">스팸 필터 정책을 만들어 사용자 지정 사서함에서 스팸 및 피싱에 대해 ZAP(제로 아워 자동 제거)를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-128">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="5d90d-129">보안 및 준수 & 사용하여 스팸 방지 정책 만들기를  참조하고 스팸 ZAP 및 [피싱](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) **ZAP에** 대한 On 확인란 선택을 **취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-129">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="5d90d-130">사용자 지정 사서함에서 정크 메일 규칙을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5d90d-130">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="5d90d-131">사서함에서 [정크 메일 Exchange Online 구성을 사용하여](configure-junk-email-settings-on-exo-mailboxes.md) 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-131">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="5d90d-132">이 기능을 사용하지 않도록 설정하면 EOP에서 스팸 필터링 판정 동작에 따라  메시지를 정크 메일 폴더로 이동하거나 사서함의 수신할 수 있는 목록 모음으로 메시지를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-132">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="5d90d-133">사서함이 적용 가능한 모든 선행 요구 사항을 충족하는지 확인한 후 보안 & 준수 센터를 사용하여 사용자 제출 사서함을 구성합니다(이 문서). [](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox)</span><span class="sxs-lookup"><span data-stu-id="5d90d-133">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5d90d-134">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="5d90d-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5d90d-135"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5d90d-136">사용자 제출 **페이지로** 직접 이동하기 위해 를 <https://protection.office.com/userSubmissionsReportMessage> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5d90d-136">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="5d90d-137">사용자 제출에 대한 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-137">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="5d90d-138">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="5d90d-138">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="5d90d-139">**에서 조직** [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="5d90d-139">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="5d90d-140">PowerShell을 사용하려면 Exchange Online 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-140">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="5d90d-141">사용하려는 계정에 Exchange Online PowerShell에 액세스할 수 없는 경우 제출 사서함을 지정할 때 다음과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-141">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="5d90d-142">도메인에서 전자 메일 주소 지정</span><span class="sxs-lookup"><span data-stu-id="5d90d-142">Specify an email address in your domain</span></span>

  <span data-ttu-id="5d90d-143">PowerShell에 대한 액세스를 활성화하거나 Exchange Online 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d90d-143">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="5d90d-144">PowerShell에 대한 액세스 Exchange Online 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5d90d-144">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="5d90d-145">클라이언트 액세스 규칙의 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5d90d-145">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="5d90d-146">보안 및 & 센터를 사용하여 사용자 제출 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="5d90d-146">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="5d90d-147">보안 및 & 센터에서 **위협** 관리 정책 \> **사용자** \> **제출으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="5d90d-148">나타나는 **사용자 제출** 페이지에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-148">In the **User submissions** page that appears, select one of the following options:</span></span>

      1. <span data-ttu-id="5d90d-149">**보고서 메시지** 기능에 Outlook 기능 사용(권장) : 보고서 메시지 추가 기능, 피싱 보고 추가 기능 또는 웹용 Outlook 기본 제공 보고를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-149">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

    - <span data-ttu-id="5d90d-150">**최종 사용자 확인 메시지 사용자** 지정: 이 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-150">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="5d90d-151">나타나는 **확인 메시지** 사용자 지정 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-151">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

        - <span data-ttu-id="5d90d-152">**제출 전:**  제목  및 확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고하기 전에 사용자에게 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-152">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="5d90d-153">%type% 변수를 사용하여 제출 유형(정크, 피싱 등이 아님)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-153">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

          <span data-ttu-id="5d90d-154">앞서 설명한처럼 보고된 메시지를 Microsoft로 보내는 옵션을 선택하면 알림에 다음 텍스트도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-154">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="5d90d-155">분석을 위해 전자 메일이 Microsoft에 있는 동안 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-155">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="5d90d-156">일부 전자 메일에는 개인 또는 중요한 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-156">Some emails might contain personal or sensitive information.</span></span>

        - <span data-ttu-id="5d90d-157">**제출 후**: 확장 ![ 아이콘 ](../../media/scc-expand-icon.png) 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-157">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="5d90d-158">제목 **및**  확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고한 후 사용자에게 표시될 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-158">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="5d90d-159">%type% 변수를 사용하여 제출 유형을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-159">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="5d90d-160">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-160">When you're finished, click **Save**.</span></span> <span data-ttu-id="5d90d-161">이러한 값을 지우려면 사용자 제출 **페이지에서** **복원을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-161">To clear these values, click **Restore** back on the **User submissions** page.</span></span>
    
    - <span data-ttu-id="5d90d-162">**최종 사용자 보고 옵션 사용자** 지정: 이 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-162">**Customize the end-user reporting options**: Click this link.</span></span> <span data-ttu-id="5d90d-163">나타나는 **최종 사용자** 보고 옵션 사용자 지정 플라이아웃에서 정크 메일 보고 옵션에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-163">In the **Customize end-user reporting options** flyout that appears, enter the descriptive text for Junk email reporting options.</span></span> 
    
      <span data-ttu-id="5d90d-164">메시지가 **보고된 경우를** 표시하는 옵션 아래에서 다음 옵션 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-164">Under **Options to show when messages are reported**, select at least one among the following options:</span></span>
        - <span data-ttu-id="5d90d-165">**보고서를 보내기 전에 질문하기**</span><span class="sxs-lookup"><span data-stu-id="5d90d-165">**Ask me before sending a report**</span></span>
        - <span data-ttu-id="5d90d-166">**자동으로 보고서 보내기**</span><span class="sxs-lookup"><span data-stu-id="5d90d-166">**Automatically send reports**</span></span>
        - <span data-ttu-id="5d90d-167">**보고서를 보내지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-167">**Never send reports**</span></span>
       
      <span data-ttu-id="5d90d-168">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-168">When you're finished, click **Save**.</span></span>

        - <span data-ttu-id="5d90d-169">**보고된 메시지를** 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-169">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="5d90d-170">**Microsoft(권장)**: 사용자 제출 사서함이 사용되지 않습니다(보고된 모든 메시지는 Microsoft로 이동).</span><span class="sxs-lookup"><span data-stu-id="5d90d-170">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="5d90d-171">**Microsoft 및** 사용자 지정 사서함 모두: 나타나는 상자에 기존 사서함의 전자 메일 Exchange Online 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-171">**Both Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="5d90d-172">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-172">Distribution groups are not allowed.</span></span> <span data-ttu-id="5d90d-173">사용자 제출은 분석을 위해 Microsoft로 이동하고 관리자 또는 보안 운영 팀이 분석할 사용자 지정 사서함으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-173">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="5d90d-174">**사용자 지정 사서함만:** 나타나는 상자에 기존 사서함의 전자 메일 주소를 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5d90d-174">**Custom mailbox only**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="5d90d-175">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-175">Distribution groups are not allowed.</span></span> <span data-ttu-id="5d90d-176">메시지를 먼저 분석하기 위해 관리자 또는 보안 운영 팀으로 이동하려는 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-176">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="5d90d-177">관리자가 메시지를 직접 전달하지 않으면 메시지가 Microsoft로 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-177">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!NOTE]
          > <span data-ttu-id="5d90d-178">미국 정부 조직(GCC, GCC-H 및 DoD)은 사용자 지정 사서함만 **구성할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-178">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="5d90d-179">다른 두 옵션은 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-179">The other two options are disabled.</span></span>

          > [!NOTE]
          > <span data-ttu-id="5d90d-180">조직이 사용자 지정 사서함으로만 보내도록 구성된 경우 보고된 메시지는 다시 검색을 위해 전송되지 않습니다. 사용자 보고 메시지 포털의 결과는 항상 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-180">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

      <span data-ttu-id="5d90d-181">완료되면 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-181">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="5d90d-182">웹 사서함 [](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정책의 Outlook 사용하여 웹의 Outlook에서 정크 메일 보고를 사용하지 않도록 설정했지만 Microsoft에 메시지를 보고하도록 이전 설정을 구성한 경우 사용자는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 웹의 Outlook Microsoft에 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-182">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>


    2. <span data-ttu-id="5d90d-183">Outlook 보고서 메시지 기능 사용 안 하도록 설정 **:** 보고서 메시지 추가 기능 Outlook, 피싱 보고 추가 기능 또는 웹용 보고서의 기본 제공 보고 대신 타사 보고 도구를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-183">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

       <span data-ttu-id="5d90d-184">이 **사용자 지정 사서함을 사용하여 사용자가 보고한 제출을 받습니다.를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-184">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="5d90d-185">상자가 나타나면 이미 사서함에 있는 기존 사서함의 전자 메일 주소를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d90d-185">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="5d90d-186">이 사서함은 전자 메일을 받을 수 Exchange Online 사서함의 기존 사서함이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-186">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

       <span data-ttu-id="5d90d-187">완료되면 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d90d-187">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="5d90d-188">메시지 전송 형식</span><span class="sxs-lookup"><span data-stu-id="5d90d-188">Message submission format</span></span>

<span data-ttu-id="5d90d-189">사용자 지정 사서함으로 전송되는 메시지는 특정 전송 메일 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-189">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="5d90d-190">제출의 제목(봉투 제목)은 다음 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-190">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="5d90d-191">여기서 SafetyAPIAction은 다음 정수 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-191">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="5d90d-192">1: 정크</span><span class="sxs-lookup"><span data-stu-id="5d90d-192">1: Junk</span></span>
- <span data-ttu-id="5d90d-193">2: 정크 아님</span><span class="sxs-lookup"><span data-stu-id="5d90d-193">2: Not junk</span></span>
- <span data-ttu-id="5d90d-194">3: 피싱</span><span class="sxs-lookup"><span data-stu-id="5d90d-194">3: Phishing</span></span>

<span data-ttu-id="5d90d-195">다음 예제에서는 다음을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-195">In the following example:</span></span>

- <span data-ttu-id="5d90d-196">메시지가 피싱으로 보고되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-196">The message is being reported as phishing.</span></span>
- <span data-ttu-id="5d90d-197">네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-197">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="5d90d-198">보낸 사람 IP는 167.220.232.101입니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-198">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="5d90d-199">From 주소가 test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5d90d-199">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="5d90d-200">메시지의 제목 줄이 "테스트 피싱 제출"입니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-200">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="5d90d-201">이 형식을 따르지 않는 메시지는 제출 포털에 제대로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d90d-201">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
