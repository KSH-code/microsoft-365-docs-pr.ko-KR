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
ms.openlocfilehash: 6022d2ca0e4357b422a20490fee7486affefa09c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287272"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="e1fb9-103">사용자 제출 정책</span><span class="sxs-lookup"><span data-stu-id="e1fb9-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e1fb9-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-104">**Applies to**</span></span>
- [<span data-ttu-id="e1fb9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e1fb9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e1fb9-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="e1fb9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e1fb9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1fb9-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e1fb9-108">Exchange Online 사서함이 있는 Microsoft 365 조직에서는 사용자가 악의적 또는 악의적이지 않은 것으로 보고하는 메시지를 받을 사서함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="e1fb9-109">사용자가 다양한 보고 옵션을 사용하여 메시지를 전송할 때 이 사서함을 사용하여 메시지를 가로채거나(사용자 지정 사서함으로만 보내기만) 메시지 복사본을 받을 수 있습니다(사용자 지정 사서함 및 Microsoft로 보내기).</span><span class="sxs-lookup"><span data-stu-id="e1fb9-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="e1fb9-110">이 기능은 다음 메시지 보고 옵션과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="e1fb9-111">보고서 메시지 추가 기능</span><span class="sxs-lookup"><span data-stu-id="e1fb9-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="e1fb9-112">피싱 보고서 추가 기능</span><span class="sxs-lookup"><span data-stu-id="e1fb9-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="e1fb9-113">[웹용 Outlook의](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 기본 제공 보고(이전의 웹 Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="e1fb9-113">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="e1fb9-114">iOS 및 Android용 Outlook의 기본 제공 보고</span><span class="sxs-lookup"><span data-stu-id="e1fb9-114">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="e1fb9-115">웹용 Outlook에서 보고를 사용하지 않도록 설정한 경우 여기에서 사용자 제출을 사용하도록 설정하면 해당 설정이 다시 설정되고 사용자가 웹용 [Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)메시지를 다시 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="e1fb9-116">지정한 사서함으로 메시지를 전달하도록 타사 메시지 보고 도구를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-116">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="e1fb9-117">사용자가 보고한 메시지를 Microsoft에 직접 전달하는 대신 사용자 지정 사서함으로 배달하면 관리자가 관리자 제출을 사용하여 메시지를 선택적으로 수동으로 Microsoft에 보고할 [수 있습니다.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="e1fb9-117">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="e1fb9-118">사용자 지정 사서함의 선행 준비</span><span class="sxs-lookup"><span data-stu-id="e1fb9-118">Custom mailbox prerequisites</span></span>

<span data-ttu-id="e1fb9-119">다음 문서를 사용하여 사용자가 보고한 메시지가 사용자 지정 사서함으로 이동하도록 필수 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-119">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="e1fb9-120">스팸 지수 설정에 대한 Exchange 메일 흐름 규칙을 만들어 사용자 지정 사서함에서 스팸 필터링을 건너뜁합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-120">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="e1fb9-121">SCL을 **-1로** 설정하는 [메시지의 SCL을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 설정하는 메일 흐름 규칙을 만들 때 EAC를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-121">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="e1fb9-122">사용자 지정 사서함에서 맬웨어에 대한 첨부 파일 검색을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-122">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="e1fb9-123">[Office 365용 Defender에서](set-up-atp-safe-attachments-policies.md) 안전 첨부 파일 설정 정책을 사용하여 안전  첨부 파일 알 수 없는 맬웨어 응답에 대해 해제 설정을 사용하여 안전한 첨부 파일 정책을 만들 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-123">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-atp-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="e1fb9-124">사용자 지정 사서함의 메시지에 대한 URL 검색을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-124">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="e1fb9-125">[Office 365용 Defender에서](set-up-atp-safe-links-policies.md) 안전한 링크 설정 정책을 사용하여 메시지의  알 수 없는 악의적인 URL에 대한 작업 선택을 해제로 설정하여 안전한 링크 정책을 만들 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-125">Use [Set up Safe Links policies in Defender for Office 365](set-up-atp-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="e1fb9-126">맬웨어 방지 정책을 만들어 맬웨어 제로 아워 자동 제거를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-126">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="e1fb9-127">보안 및 준수 [&](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 맬웨어 방지 정책을 만들어 **맬웨어** 제로 아워 자동 제거를 해제로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-127">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="e1fb9-128">스팸 필터 정책을 만들어 사용자 지정 사서함에서 스팸 및 피싱에 대해 ZAP(제로 아워 자동 제거)를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-128">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="e1fb9-129">보안 [및](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 준수 & 사용하여 스팸 방지 정책을 만들고  스팸 ZAP 및 피싱 **ZAP에** 대한 On 확인란의 **선택을 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-129">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="e1fb9-130">사용자 지정 사서함에서 정크 메일 규칙을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e1fb9-130">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="e1fb9-131">[Exchange Online 사서함에서](configure-junk-email-settings-on-exo-mailboxes.md) 정크 메일 설정을 구성하여 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-131">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="e1fb9-132">이 기능을 사용하지 않도록 설정하면 EOP는 스팸 필터링 판정 동작에 따라  메시지를 정크 메일 폴더로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-132">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="e1fb9-133">사서함이 적용 가능한 모든 선행 요구 사항을 충족하는지 확인한 후 보안 & 준수 센터를 사용하여 사용자 제출 사서함을 구성합니다(이 문서의). [](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox)</span><span class="sxs-lookup"><span data-stu-id="e1fb9-133">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e1fb9-134">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="e1fb9-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e1fb9-135"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e1fb9-136">사용자 제출 **페이지로** 직접 이동하기 위해 다음을 <https://protection.office.com/userSubmissionsReportMessage> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-136">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="e1fb9-137">사용자 제출에 대한 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-137">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="e1fb9-138">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-138">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="e1fb9-139"> [Exchange Online의 조직 관리.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="e1fb9-139">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="e1fb9-140">Exchange Online PowerShell에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-140">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="e1fb9-141">사용하려는 계정에 Exchange Online PowerShell에 액세스할 수 없는 경우 제출 사서함을 지정할 때 다음과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-141">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="e1fb9-142">도메인에서 전자 메일 주소 지정</span><span class="sxs-lookup"><span data-stu-id="e1fb9-142">Specify an email address in your domain</span></span>

  <span data-ttu-id="e1fb9-143">Exchange Online PowerShell에 대한 액세스를 활성화 또는 사용 안 하는 데 대한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-143">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="e1fb9-144">Exchange Online PowerShell 액세스 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e1fb9-144">Enable or disable access to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="e1fb9-145">Exchange Online의 클라이언트 액세스 규칙</span><span class="sxs-lookup"><span data-stu-id="e1fb9-145">Client Access Rules in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="e1fb9-146">보안 및 & 센터를 사용하여 사용자 제출 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="e1fb9-146">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="e1fb9-147">보안 & 준수 센터에서 **위협 관리** 정책 \> **사용자** \> **제출로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="e1fb9-148">나타나는 **사용자 제출** 페이지에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-148">In the **User submissions** page that appears, select one of the following options:</span></span>

   1. <span data-ttu-id="e1fb9-149">Outlook에 보고서 메시지 기능 **사용(권장)**: 보고서 메시지 추가 기능, 피싱 보고서 추가 기능 또는 웹용 Outlook의 기본 제공 보고를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-149">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="e1fb9-150">**최종 사용자 확인 메시지** 사용자 지정 : 이 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-150">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="e1fb9-151">나타나는 **확인 메시지** 플라이아웃 사용자 지정에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-151">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="e1fb9-152">**제출 전에**:  제목  및 확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 사용하여 메시지를 보고하기 전에 사용자에게 표시하는 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-152">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="e1fb9-153">%type 변수를 사용하여 제출 유형(정크, 피싱 아님 등)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-153">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="e1fb9-154">앞서 설명한 것 처럼 보고된 메시지를 Microsoft로 보내는 옵션을 선택하면 알림에 다음 텍스트도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-154">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="e1fb9-155">분석을 위해 전자 메일이 Microsoft에 있는 동안 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-155">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="e1fb9-156">일부 전자 메일에는 개인 또는 중요한 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-156">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="e1fb9-157">**제출 후**: 확장 ![ ](../../media/scc-expand-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-157">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="e1fb9-158">제목 **및**  확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 사용하여 메시지를 보고한 후 사용자에게 표시하는 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-158">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="e1fb9-159">%type 변수를 사용하여 제출 형식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-159">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="e1fb9-160">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-160">When you're finished, click **Save**.</span></span> <span data-ttu-id="e1fb9-161">이러한 값을 지우려면 사용자 제출 **페이지에서** **복원을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-161">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="e1fb9-162">**보고된 메시지를** 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-162">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="e1fb9-163">**Microsoft(권장)**: 사용자 제출 사서함이 사용되지 않습니다(보고된 모든 메시지는 Microsoft로 이동).</span><span class="sxs-lookup"><span data-stu-id="e1fb9-163">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="e1fb9-164">**Microsoft 및 사용자** 지정 사서함: 나타나는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-164">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="e1fb9-165">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-165">Distribution groups are not allowed.</span></span> <span data-ttu-id="e1fb9-166">사용자 제출은 분석을 위해 Microsoft와 관리자 또는 보안 운영 팀이 분석할 사용자 지정 사서함으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-166">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="e1fb9-167">**사용자 지정 사서함:** 상자가 나타나면 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-167">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="e1fb9-168">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-168">Distribution groups are not allowed.</span></span> <span data-ttu-id="e1fb9-169">메시지를 먼저 분석하기 위해 관리자 또는 보안 운영 팀으로 이동하려는 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-169">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="e1fb9-170">관리자가 직접 메시지를 전달하지 않으면 메시지가 Microsoft로 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-170">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="e1fb9-171">미국 정부 조직(GCC, GCC-H 및 DoD)은 사용자 지정 사서함만 **구성할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-171">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="e1fb9-172">다른 두 옵션은 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-172">The other two options are disabled.</span></span>

      <span data-ttu-id="e1fb9-173">완료되면 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-173">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="e1fb9-174">웹용 Outlook 사서함 정책을 사용하여 웹용 [Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정크 메일 보고를 사용하지 않도록 설정했지만 Microsoft에 메시지를 보고하도록 이전 설정을 구성한 경우 사용자는 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 사용하여 웹용 Outlook의 Microsoft에 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-174">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>

   - <span data-ttu-id="e1fb9-175">**Outlook에** 대해 보고서 메시지 기능을 사용하지 않도록 설정 : 보고서 메시지 추가 기능, 피싱 보고서 추가 기능 또는 웹용 Outlook의 기본 제공 보고 대신 타사 보고 도구를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-175">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="e1fb9-176">이 사용자 지정 사서함을 사용하여 사용자가 **보고한 제출을 받습니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-176">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="e1fb9-177">상자가 나타나면 Office 365에 이미 있는 기존 사서함의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-177">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="e1fb9-178">이 사서함은 전자 메일을 받을 수 있는 Exchange Online의 기존 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-178">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="e1fb9-179">완료되면 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1fb9-179">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="e1fb9-180">메시지 전송 형식</span><span class="sxs-lookup"><span data-stu-id="e1fb9-180">Message submission format</span></span>

<span data-ttu-id="e1fb9-181">사용자 지정 사서함으로 전송되는 메시지는 특정 전송 메일 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-181">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="e1fb9-182">제출의 제목(봉투 제목)은 다음 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-182">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="e1fb9-183">여기서 SafetyAPIAction은 다음 정수 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-183">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="e1fb9-184">1: 정크</span><span class="sxs-lookup"><span data-stu-id="e1fb9-184">1: Junk</span></span>
- <span data-ttu-id="e1fb9-185">2: 정크 아님</span><span class="sxs-lookup"><span data-stu-id="e1fb9-185">2: Not junk</span></span>
- <span data-ttu-id="e1fb9-186">3: 피싱</span><span class="sxs-lookup"><span data-stu-id="e1fb9-186">3: Phishing</span></span>

<span data-ttu-id="e1fb9-187">다음 예제에서는 다음을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-187">In the following example:</span></span>

- <span data-ttu-id="e1fb9-188">메시지가 피싱으로 보고되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-188">The message is being reported as phishing.</span></span>
- <span data-ttu-id="e1fb9-189">네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-189">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="e1fb9-190">보낸 사람 IP는 167.220.232.101입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-190">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="e1fb9-191">From 주소가 test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-191">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="e1fb9-192">메시지의 제목 줄이 "피싱 제출 테스트"입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-192">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="e1fb9-193">이 형식을 따르지 않는 메시지는 제출 포털에 제대로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fb9-193">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
