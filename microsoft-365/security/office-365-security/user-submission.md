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
ms.openlocfilehash: f565a71b44d27076ea6ff0b25be5d5b3932913c9
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052990"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="68332-103">사용자 제출 정책</span><span class="sxs-lookup"><span data-stu-id="68332-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="68332-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="68332-104">**Applies to**</span></span>
- [<span data-ttu-id="68332-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="68332-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="68332-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="68332-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="68332-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68332-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="68332-108">사서함이 Microsoft 365 조직에서 Exchange Online 악의적이거나 악의적이지 않은 것으로 보고하는 메시지를 받을 사서함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="68332-109">사용자가 다양한 보고 옵션을 사용하여 메시지를 전송할 때 이 사서함을 사용하여 메시지를 가로채거나(사용자 지정 사서함으로만 보내기) 메시지 복사본(사용자 지정 사서함 및 Microsoft로 보내기)을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="68332-110">이 기능은 다음 메시지 보고 옵션과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="68332-111">보고서 메시지 추가 기능</span><span class="sxs-lookup"><span data-stu-id="68332-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)
- [<span data-ttu-id="68332-112">피싱 보고 추가 기능</span><span class="sxs-lookup"><span data-stu-id="68332-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)
- [<span data-ttu-id="68332-113">타사 보고 도구</span><span class="sxs-lookup"><span data-stu-id="68332-113">Third-party reporting tools</span></span>](#third-party-reporting-tools)

<span data-ttu-id="68332-114">사용자가 보고한 메시지를 Microsoft에 직접 전달하는 대신 사용자 지정 사서함으로 배달하면 관리자가 관리자 제출을 사용하여 메시지를 선택적으로 수동으로 Microsoft에 보고할 [수 있습니다.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="68332-114">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="68332-115">웹용 Outlook 보고를 사용하지 않도록 설정한 경우 [여기에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)사용자 제출을 사용하도록 설정하면 해당 설정이 다시 웹용 Outlook 합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="68332-116">사용자 지정 사서함 선행 준비</span><span class="sxs-lookup"><span data-stu-id="68332-116">Custom mailbox prerequisites</span></span>

<span data-ttu-id="68332-117">다음 문서를 사용하여 사용자가 보고한 메시지가 사용자 지정 사서함으로 이동하도록 필수 구성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-117">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="68332-118">스팸 지수 설정 Exchange 메일 흐름 규칙을 만들어 사용자 지정 사서함에서 스팸 필터링을 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="68332-118">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="68332-119">SCL을 스팸 필터링 무시로 설정하는 [메시지의 SCL을](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 설정하는 메일 흐름 규칙 만들기를 **참조합니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-119">See [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **Bypass spam filtering**.</span></span>

- <span data-ttu-id="68332-120">[첨부 금고](set-up-safe-attachments-policies.md) 검사가 꺼져 있는 사용자 지정 사서함이 포함된 금고 첨부 파일 정책을 만들 수 있습니다(금고 알 수 없는 맬웨어 응답 섹션 \> 해제).</span><span class="sxs-lookup"><span data-stu-id="68332-120">[Create a Safe Attachments policy](set-up-safe-attachments-policies.md) that includes the custom mailbox where Safe Attachments scanning is turned off (**Safe Attachments unknown malware response** section \> **Off**).</span></span>

- <span data-ttu-id="68332-121">[금고](set-up-safe-links-policies.md) 링크 검색이 꺼져 있는 사용자 지정 사서함을 포함하는 금고 링크 정책을 만드십시오( 메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택 섹션 \> **끄기).**</span><span class="sxs-lookup"><span data-stu-id="68332-121">[Create a Safe Links policy](set-up-safe-links-policies.md) that includes the custom mailbox where Safe Links scanning is turned off (**Select the action for unknown potentially malicious URLs in messages** section \> **Off**).</span></span>

- <span data-ttu-id="68332-122">[맬웨어에](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) 대한 ZAP(제로 아워 자동 제거)가 꺼져 있는 사용자 지정 사서함을 포함하는 맬웨어 방지 정책을 만들 수 있습니다(**보호** 설정 섹션 맬웨어에 대한 제로 아워 자동 제거 사용이 선택되어 있지 \>  않습니다).</span><span class="sxs-lookup"><span data-stu-id="68332-122">[Create an anti-malware policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where zero-hour auto purge (ZAP) for malware is turned off (**Protection settings** section \> **Enable zero-hour auto purge for malware** is not selected).</span></span>

- <span data-ttu-id="68332-123">[스팸에](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) 대한 ZAP 및 피싱용 ZAP가 꺼져 있는 사용자 지정 사서함을 포함하는 스팸 방지 정책을 만들 수 **있습니다(** 제로 아워 자동 제거 섹션 사용 제로 아워 자동 제거(ZAP)를 선택하지 \>  않았습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-123">[Create an anti-spam policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where ZAP for spam and ZAP for phishing are turned off (**Zero-hour auto purge** section \> **Enabled zero-hour auto purge (ZAP)** is not selected).</span></span>

- <span data-ttu-id="68332-124">사용자 지정 사서함에서 정크 메일 규칙을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="68332-124">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="68332-125">사서함에서 [정크 메일 Exchange Online 구성을 사용하여](configure-junk-email-settings-on-exo-mailboxes.md) 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-125">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="68332-126">이 기능을 사용하지 않도록 설정한 후 EOP는 스팸 필터링 판정 동작에 따라 메시지를  정크 메일 폴더로 이동하거나 사서함의 수신할 수 있는 목록 모음으로 메시지를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-126">After it's disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="68332-127">사서함이 적용 가능한 모든 선행 요구 사항을 충족하는지 확인한 후 이 문서의 절차에 따라 사용자 전송 사서함을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-127">After you've verified that your mailbox meets all applicable prerequisites, you can use the procedures in this article to configure the user submissions mailbox.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="68332-128">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="68332-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="68332-129"><https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="68332-129">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="68332-130">제출 **페이지로** 직접 이동하기 위해 를 <https://security.microsoft.com/reportsubmission> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="68332-130">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="68332-131">사용자 제출에 대한 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-131">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="68332-132">**조직 포털의** 조직 [관리 또는 보안 Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md) </span><span class="sxs-lookup"><span data-stu-id="68332-132">**Organization Management** or **Security Administrator** in the [Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="68332-133">**에서 조직** [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="68332-133">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="68332-134">PowerShell을 사용하려면 Exchange Online 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-134">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="68332-135">사용하려는 계정에 Exchange Online PowerShell에 액세스할 수 없는 경우 제출 사서함을 지정할 때 다음과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="68332-135">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="68332-136">도메인에서 전자 메일 주소 지정</span><span class="sxs-lookup"><span data-stu-id="68332-136">Specify an email address in your domain</span></span>

  <span data-ttu-id="68332-137">PowerShell에 대한 액세스를 활성화하거나 Exchange Online 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68332-137">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="68332-138">PowerShell에 대한 액세스 Exchange Online 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="68332-138">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="68332-139">클라이언트 액세스 규칙의 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="68332-139">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="68332-140">Microsoft 365 Defender 포털을 사용하여 사용자 제출 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="68332-140">Use the Microsoft 365 Defender portal to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="68332-141">Microsoft 365 Defender 포털에서 정책 **정책** & 규칙 위협 정책 기타 섹션 사용자가 메시지 설정을 보고했습니다 사용자 제출 \>  \>  \>  \> **으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-141">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings** \> **User submissions**.</span></span>

2. <span data-ttu-id="68332-142">사용자 **제출 페이지에서는** Microsoft Outlook 메시지 단추 설정이 꺼지거나 으로 설정되어 **있는지** **여부에** 따라 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-142">On the **User submissions** page, what you see is determined by whether the **Microsoft Outlook Report Message button** setting is **Off** or **On**:</span></span>

   - <span data-ttu-id="68332-143">**Microsoft Outlook 메시지 단추** \> **On** ![ 토글: 보고서 메시지 추가 기능, 피싱 보고 추가 기능 또는 기본 제공 보고 기능을 웹용 Outlook 다음 설정을 구성하려면 이 ](../../media/scc-toggle-on.png) 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-143">**Microsoft Outlook Report Message button** \> **On** ![Toggle on](../../media/scc-toggle-on.png): Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="68332-144">**보고된 메시지를** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-144">**Send the reported messages to**: Select one of the following options:</span></span>
       - <span data-ttu-id="68332-145">**Microsoft:** 사용자 전송 사서함이 사용되지 않습니다(보고된 모든 메시지는 Microsoft로 이동).</span><span class="sxs-lookup"><span data-stu-id="68332-145">**Microsoft**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>
       - <span data-ttu-id="68332-146">**Microsoft 및 내** 조직의 사서함: 나타나는 상자에 기존 사서함의 전자 메일 주소를 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68332-146">**Microsoft and my organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="68332-147">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-147">Distribution groups are not allowed.</span></span> <span data-ttu-id="68332-148">사용자 제출은 분석을 위해 Microsoft로 이동하고 관리자 또는 보안 운영 팀이 분석할 사용자 지정 사서함으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="68332-148">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>
       - <span data-ttu-id="68332-149">**조직의 사서함:** 나타나는 상자에 기존 사서함의 전자 메일 주소를 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68332-149">**My organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="68332-150">메일 그룹은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-150">Distribution groups are not allowed.</span></span> <span data-ttu-id="68332-151">메시지를 먼저 분석하기 위해 관리자 또는 보안 운영 팀으로 이동하려는 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-151">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="68332-152">관리자가 메시지를 직접 전달하지 않으면 메시지가 Microsoft로 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-152">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!IMPORTANT]
          >
          > <span data-ttu-id="68332-153">미국 정부 조직(GCC, GCC High 및 DoD)은 내 조직의 사서함만 **구성할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-153">U.S. Government organizations (GCC, GCC High, and DoD) can only configure **My organization's mailbox**.</span></span> <span data-ttu-id="68332-154">다른 두 옵션은 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="68332-154">The other two options are disabled.</span></span>
          >
          > <span data-ttu-id="68332-155">조직이 사용자 지정 사서함으로만 보내도록 구성된 경우 보고된 메시지는 다시 검색을 위해 전송되지 않습니다. 사용자 보고 메시지 포털의 결과는 항상 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-155">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

       <span data-ttu-id="68332-156">보고된 메시지를 보내기 위해 선택한 값에 관계없이 다음 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-156">Regardless of the value you selected for **Send the reported messages to**, the following settings are available:</span></span>

       - <span data-ttu-id="68332-157">**사용자가 Microsoft에 메시지를 보고할지 선택할 수 있도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-157">**Let users choose if they want to report their message to Microsoft**</span></span>
       - <span data-ttu-id="68332-158">**사용자가 사용할 수 있는** 보고 옵션 선택 섹션: 다음 옵션 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-158">**Select reporting options that are available to users** section: Select at least one among the following options:</span></span>
         - <span data-ttu-id="68332-159">**메시지를 보내기 전에 질문하기**</span><span class="sxs-lookup"><span data-stu-id="68332-159">**Ask me before sending the message**</span></span>
         - <span data-ttu-id="68332-160">**항상 메시지 보고**</span><span class="sxs-lookup"><span data-stu-id="68332-160">**Always report the message**</span></span>
         - <span data-ttu-id="68332-161">**메시지를 보고하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-161">**Never report the message**</span></span>

          > [!CAUTION]
          > <span data-ttu-id="68332-162">웹용 Outlook 사서함 [](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정책을 사용하여 웹용 Outlook 웹용 Outlook 정크 메일 보고를 사용하지 않도록 설정했지만 Microsoft에 메시지를 보고하도록 이전 설정을 구성한 경우 사용자는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 웹용 Outlook Microsoft에 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-162">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configured any of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>

     - <span data-ttu-id="68332-163">**사용자 보고 환경 섹션**</span><span class="sxs-lookup"><span data-stu-id="68332-163">**User reporting experience section**</span></span>
       - <span data-ttu-id="68332-164">**보고 탭** 전에:  제목  및 메시지 본문 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고하기 전에 사용자에게 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-164">**Before reporting** tab: In the **Title** and **Message body** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="68332-165">%type% 변수를 사용하여 제출 유형(정크, 피싱 등이 아님)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-165">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>
       - <span data-ttu-id="68332-166">**보고 탭** 후:  제목  및 확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고한 후 사용자에게 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-166">**After reporting** tab: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="68332-167">%type% 변수를 사용하여 제출 유형을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-167">You can use the variable %type% to include the submission type.</span></span>

       <span data-ttu-id="68332-168">페이지에 표시된 것 처럼 보고된 메시지를 Microsoft로 보내는 옵션을 선택하면 알림에 다음 텍스트도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="68332-168">As shown on the page, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="68332-169">분석을 위해 전자 메일이 Microsoft에 있는 동안 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="68332-169">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="68332-170">일부 전자 메일에는 개인 또는 중요한 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-170">Some emails might contain personal or sensitive information.</span></span>

   - <span data-ttu-id="68332-171">**Microsoft Outlook 메시지 단추** \> **끄기** ![ 토글 해제: 보고서 메시지 추가 기능, 피싱 보고 추가 기능 또는 기본 제공 보고 기능 대신 타사 보고 도구를 사용하는 경우 웹용 Outlook 다음 설정을 ](../../media/scc-toggle-off.png) 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-171">**Microsoft Outlook Report Message button** \> **Off** ![Toggle off](../../media/scc-toggle-off.png): Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="68332-172">이 **사용자 지정 사서함을 사용하여 사용자가 보고한 제출을 받습니다.를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-172">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="68332-173">나타나는 상자에 전자 메일을 받을 수 있는 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-173">In the box that appears, enter the email address of an existing Exchange Online mailbox that can receive email.</span></span>

   <span data-ttu-id="68332-174">완료되면 확인 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-174">When you're finished, click **Confirm**.</span></span> <span data-ttu-id="68332-175">이러한 값을 지우려면 **복원을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68332-175">To clear these values, click **Restore**</span></span>

## <a name="third-party-reporting-tools"></a><span data-ttu-id="68332-176">타사 보고 도구</span><span class="sxs-lookup"><span data-stu-id="68332-176">Third-party reporting tools</span></span>

<span data-ttu-id="68332-177">보고된 메시지를 사용자 지정 사서함으로 보내도록 타사 메시지 보고 도구를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-177">You can configure third-party message reporting tools to send reported messages to the custom mailbox.</span></span> <span data-ttu-id="68332-178">**Microsoft** Outlook 보고 메시지 단추 설정을 끄기로  설정하고 내  조직의 사서함을 원하는 사서함으로 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-178">You would do this by setting the **Microsoft Outlook Report Message button** setting to **Off** and setting the **My organization's mailbox** to an Office 365 mailbox of your choice.</span></span>

<span data-ttu-id="68332-179">유일한 요구 사항은 원본 메시지가 로 포함되는 것입니다. EML 또는 . 사용자 지정 사서함으로 전송된 메시지의 MSG 첨부 파일(압축되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="68332-179">The only requirement is that the original message is included as a .EML or .MSG attachment (not compressed) in the message that's sent to the custom mailbox (don't just forward the original message to the custom mailbox).</span></span>

<span data-ttu-id="68332-180">메시지 서식 요구 사항은 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-180">The message formatting requirements are described in the next section.</span></span> <span data-ttu-id="68332-181">서식은 선택 사항이지만 정해진 형식을 따르지 않는 경우 보고서는 항상 피싱으로 제출됩니다.</span><span class="sxs-lookup"><span data-stu-id="68332-181">The formatting is optional, but if it does not follow the prescribed format, the reports will always be submitted as phish.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="68332-182">메시지 전송 형식</span><span class="sxs-lookup"><span data-stu-id="68332-182">Message submission format</span></span>

<span data-ttu-id="68332-183">원래 첨부된 메시지를 올바르게 식별하려면 사용자 지정 사서함으로 전송되는 메시지에 특정 서식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-183">To correctly identify the original attached messages, messages that are sent to the custom mailbox require specific formatting.</span></span> <span data-ttu-id="68332-184">메시지가 이 형식을 사용하지 않는 경우 원래 첨부된 메시지는 항상 피싱 전송으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="68332-184">If the messages don't use this format, the original attached messages are always identified as phishing submissions.</span></span>

<span data-ttu-id="68332-185">원래 첨부된 메시지를 올바르게 식별하려면 사용자 지정 사서함으로 전송되는 메시지는 제목(봉투 제목)에 대해 다음 구문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-185">For correct identification of the original attached messages, messages that are sent to the custom mailbox need to use the following syntax for the Subject (Envelope Title):</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="68332-186">여기서 SafetyAPIAction은 다음 정수 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="68332-186">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="68332-187">1: 정크</span><span class="sxs-lookup"><span data-stu-id="68332-187">1: Junk</span></span>
- <span data-ttu-id="68332-188">2: 정크 아님</span><span class="sxs-lookup"><span data-stu-id="68332-188">2: Not junk</span></span>
- <span data-ttu-id="68332-189">3: 피싱</span><span class="sxs-lookup"><span data-stu-id="68332-189">3: Phishing</span></span>

<span data-ttu-id="68332-190">이 예제에서는 다음 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68332-190">This example uses the following values:</span></span>

- <span data-ttu-id="68332-191">메시지가 피싱으로 보고되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-191">The message is being reported as phishing.</span></span>
- <span data-ttu-id="68332-192">네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.</span><span class="sxs-lookup"><span data-stu-id="68332-192">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="68332-193">보낸 사람 IP는 167.220.232.101입니다.</span><span class="sxs-lookup"><span data-stu-id="68332-193">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="68332-194">From 주소가 test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="68332-194">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="68332-195">메시지의 제목 줄이 "테스트 피싱 제출"입니다.</span><span class="sxs-lookup"><span data-stu-id="68332-195">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="68332-196">이 형식을 따르지 않는 메시지는 제출 포털에 제대로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68332-196">Messages that don't follow this format will not display properly in the Submissions portal.</span></span>
