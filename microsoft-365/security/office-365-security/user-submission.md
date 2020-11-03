---
title: 사용자 전송 정책
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 사용자가 보고 하는 스팸 및 피싱 전자 메일을 수집 하도록 사서함을 구성 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: d39614c2cafd3469625c4a01bdc63a1e60fead85
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842907"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="fb0ef-103">사용자 전송 정책</span><span class="sxs-lookup"><span data-stu-id="fb0ef-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fb0ef-104">Exchange Online 사서함이 있는 Microsoft 365 조 직에서는 사용자가 악성 메일로 보고 하는 메시지를 수신 하는 사서함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="fb0ef-105">사용자가 다양 한 보고 옵션을 사용 하 여 메시지를 전송 하는 경우이 사서함을 사용 하 여 메시지를 가로채 며 (사용자 지정 사서함에만 보냄) 메시지 복사본을 받을 수 있습니다 (사용자 지정 사서함 및 Microsoft로 보내기).</span><span class="sxs-lookup"><span data-stu-id="fb0ef-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="fb0ef-106">이 기능은 다음과 같은 메시지 보고 옵션에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="fb0ef-107">보고서 메시지 추가 기능</span><span class="sxs-lookup"><span data-stu-id="fb0ef-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="fb0ef-108">웹용 Outlook (이전의 Outlook Web App) [에 기본적으로 제공 되는 보고 기능](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)</span><span class="sxs-lookup"><span data-stu-id="fb0ef-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="fb0ef-109">IOS 및 Android 용 Outlook의 기본 제공 보고</span><span class="sxs-lookup"><span data-stu-id="fb0ef-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="fb0ef-110">[웹에서 outlook에서 보고를 사용 하지 않도록](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)설정한 경우 여기서 사용자 제출을 사용 하도록 설정 하면 해당 설정이 무시 되 고 사용자가 웹에서 Outlook에서 메시지를 다시 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="fb0ef-111">또한 타사 메시지 보고 도구를 구성 하 여 지정한 사서함에 메시지를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="fb0ef-112">사용자가 보고 한 메시지를 Microsoft에 직접 배포 하는 대신 사용자 지정 사서함에 전달 하면 관리자가 [관리 제출을](admin-submission.md)사용 하 여 메시지를 선택적으로 수동으로 microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="fb0ef-113">사용자 지정 사서함 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fb0ef-113">Custom mailbox prerequisites</span></span>

<span data-ttu-id="fb0ef-114">다음 문서를 사용 하 여 사용자가 보고 한 메시지를 사용자 지정 사서함으로 이동 하는 데 필요한 필수 구성 요소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-114">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="fb0ef-115">Exchange 메일 흐름 규칙을 만들어 scl (스팸 지 수)을 설정 하 여 사용자 지정 사서함에 대 한 스팸 필터링을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-115">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="fb0ef-116">EAC를 사용 하 여 SCL을 **-1** 로 설정 하 [는 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기를](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-116">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="fb0ef-117">사용자 지정 사서함에서 맬웨어에 대 한 첨부 파일 검색을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-117">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="fb0ef-118">안전 **첨부 파일** 에 대 한이 설정을 **해제** 하는 안전 첨부 파일 정책을 만들려면 [Defender for Office 365에서 안전한 첨부 파일 정책 설치](set-up-atp-safe-attachments-policies.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-118">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-atp-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="fb0ef-119">사용자 지정 사서함에서 메시지에 대해 URL 검색을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-119">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="fb0ef-120">**메시지에서 알 수 없는 잠재적 악성 url에 대 한 작업을 선택** 하려면 [Defender for Office 365에서](set-up-atp-safe-links-policies.md) 안전한 링크 **정책 설정을 사용** 하 여 안전한 링크 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-120">Use [Set up Safe Links policies in Defender for Office 365](set-up-atp-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="fb0ef-121">맬웨어 방지 정책을 만들어 맬웨어 제로 시간 자동 삭제를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-121">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="fb0ef-122">[보안 & 준수 센터를 사용 하 여 맬웨어 방지 정책 만들기](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 를 참조 하 여 **맬웨어가 있는 맬웨어 자동 삭제** 를 **설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fb0ef-122">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="fb0ef-123">사용자 지정 사서함에서 스팸 및 피싱 사기에 대해 제로 시간 자동 삭제 (ZAP)를 사용 하지 않도록 설정 하는 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-123">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="fb0ef-124">스팸 방지 정책을 만들고 **스팸 ZAP** 및 **피싱 ZAP** **에 대 한 확인란의** 선택을 취소 [하려면 보안 & 준수 센터 사용을](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-124">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="fb0ef-125">사용자 지정 사서함에서 정크 메일 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-125">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="fb0ef-126">정크 메일 규칙을 사용 하지 않도록 설정 하려면 [Exchange Online 사서함에서 정크 메일 구성 설정을](configure-junk-email-settings-on-exo-mailboxes.md) 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-126">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="fb0ef-127">사용 하지 않도록 설정 되 면 EOP에서 스팸 필터링 결과 동작 **메시지를 정크 메일** 폴더로 이동 하거나 사서함에서 수신 허용 목록 모음으로 이동 하 여 정크 메일 폴더로 메시지를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-127">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="fb0ef-128">사서함이 해당 하는 모든 필수 구성 요소를 충족 하는지 확인 한 후에는 [보안 & 준수 센터를 사용 하 여이 문서의 사용자 전송 사서함을 구성](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-128">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fb0ef-129">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="fb0ef-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fb0ef-130"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fb0ef-131">**사용자 전송** 페이지로 직접 이동 하려면를 사용 <https://protection.office.com/userSubmissionsReportMessage> 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-131">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="fb0ef-132">사용자 전송에 대 한 구성을 수정 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-132">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="fb0ef-133">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="fb0ef-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="fb0ef-134">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**</span><span class="sxs-lookup"><span data-stu-id="fb0ef-134">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="fb0ef-135">보안 & 준수 센터를 사용 하 여 사용자 전송 사서함을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-135">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="fb0ef-136">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **사용자 전송** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-136">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="fb0ef-137">**사용자 제출** 페이지가 나타나면 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-137">In the **User submissions** page that appears, select one of the following options:</span></span>

   1. <span data-ttu-id="fb0ef-138">**Outlook에 대 한 보고서 메시지 기능 사용 (권장)** : 웹에서 보고서 메시지 추가 기능 또는 기본 제공 보고를 사용 하는 경우이 옵션을 선택 하 고 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-138">**Enable the Report Message feature for Outlook (Recommended)** : Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="fb0ef-139">**최종 사용자에 게 확인 메시지를 사용자 지정** :이 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-139">**Customize the end-user confirmation message** : Click this link.</span></span> <span data-ttu-id="fb0ef-140">표시 되는 **확인 메시지 플라이 아웃 사용자 지정** 에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-140">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="fb0ef-141">**제출 전** : **제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 하기 전에 표시 되는 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-141">**Before submission** : In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="fb0ef-142">전송 유형 (정크, 정크 메일 아님, 피싱 등)을 포함 하 여% type% 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-142">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="fb0ef-143">앞에서 설명한 것 처럼, 보고 된 메시지를 Microsoft로 보내는 옵션을 선택 하면 다음과 같은 텍스트도 알림에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-143">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="fb0ef-144">전자 메일이 분석을 위해 Microsoft에 게 제출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-144">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="fb0ef-145">일부 전자 메일에는 개인 정보나 중요 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-145">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="fb0ef-146">**제출 후** ![ 확장 아이콘을 클릭 ](../../media/scc-expand-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-146">**After submission** : Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="fb0ef-147">**제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 한 후에 표시 되는 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-147">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="fb0ef-148">전송 유형을 포함 하기 위해% type% 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-148">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="fb0ef-149">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-149">When you're finished, click **Save**.</span></span> <span data-ttu-id="fb0ef-150">이러한 값을 지우려면 **사용자 전송** 페이지에서 다시 **복원을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-150">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="fb0ef-151">**보고 된 메시지를 보낼** 위치: 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-151">**Send the reported messages to** : Make one of the following selections:</span></span>

        - <span data-ttu-id="fb0ef-152">**Microsoft (권장)** : 사용자 제출 사서함이 사용 되지 않습니다 (보고 된 모든 메시지는 Microsoft로 이동 됨).</span><span class="sxs-lookup"><span data-stu-id="fb0ef-152">**Microsoft (Recommended)** : The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="fb0ef-153">**Microsoft 및 사용자 지정 사서함** : 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-153">**Microsoft and a custom mailbox** : In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="fb0ef-154">메일 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-154">Distribution groups are not allowed.</span></span> <span data-ttu-id="fb0ef-155">사용자 제출은 Microsoft for analysis와 관리자 또는 보안 운영 팀이 분석 하기 위한 사용자 지정 사서함으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-155">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="fb0ef-156">**사용자 지정 사서함** : 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-156">**Custom mailbox** : In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="fb0ef-157">메일 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-157">Distribution groups are not allowed.</span></span> <span data-ttu-id="fb0ef-158">이 옵션을 사용 하 여 메시지를 먼저 분석을 위해 관리자 또는 보안 운영 팀 으로만 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-158">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="fb0ef-159">관리자가 메시지를 직접 전달 하지 않으면 메시지가 Microsoft로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-159">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="fb0ef-160">미국 정부 기관 (GCC, GCC-H 및 DoD)은 **사용자 지정 사서함** 만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-160">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="fb0ef-161">다른 두 옵션은 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-161">The other two options are disabled.</span></span> 

      <span data-ttu-id="fb0ef-162">작업이 완료 되 면 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-162">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="fb0ef-163">웹 사서함 정책에서 Outlook을 사용 하 여 [웹용 outlook에서 정크 메일 보고를 사용 하지 않도록 설정](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 했지만 microsoft에 메시지를 보고 하는 이전 설정 중 하나를 구성 하는 경우 사용자는 보고서 메시지 추가 기능을 사용 하 여 웹용 Outlook에서 Microsoft에 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-163">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="fb0ef-164">**Outlook에 대 한 보고서 메시지 기능 사용 안 함** :이 옵션을 선택 하면 보고서 메시지 추가 기능 대신 타사 보고 도구를 사용 하거나, 웹에서 Outlook에서 기본 제공 되는 보고를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-164">**Disable the Report Message feature for Outlook** : Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="fb0ef-165">**사용자가 보고 한 제출을 수신 하려면이 사용자 지정 사서함 사용을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-165">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="fb0ef-166">상자가 나타나면 이미 Office 365에 있는 기존 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-166">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="fb0ef-167">이는 전자 메일을 받을 수 있는 Exchange Online의 기존 사서함 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-167">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="fb0ef-168">작업이 완료 되 면 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-168">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="fb0ef-169">메시지 전송 형식</span><span class="sxs-lookup"><span data-stu-id="fb0ef-169">Message submission format</span></span>

<span data-ttu-id="fb0ef-170">사용자 지정 사서함에 전송 된 메시지는 특정 전송 메일 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-170">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="fb0ef-171">제출 서류의 제목 (봉투 제목)은 다음과 같은 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-171">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="fb0ef-172">여기에서 기능 \ Etyapiaction은 다음 정수 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-172">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="fb0ef-173">1: 정크</span><span class="sxs-lookup"><span data-stu-id="fb0ef-173">1: Junk</span></span>
- <span data-ttu-id="fb0ef-174">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="fb0ef-174">2: NotJunk</span></span>
- <span data-ttu-id="fb0ef-175">3: 피싱</span><span class="sxs-lookup"><span data-stu-id="fb0ef-175">3: Phish</span></span>

<span data-ttu-id="fb0ef-176">다음 예제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-176">In the following example:</span></span>

- <span data-ttu-id="fb0ef-177">메시지가 피싱으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-177">The message is being reported as Phish.</span></span>
- <span data-ttu-id="fb0ef-178">네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-178">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="fb0ef-179">보낸 사람 IP는 167.220.232.101입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-179">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="fb0ef-180">보낸 사람 주소는 test@contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-180">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="fb0ef-181">메시지의 제목 줄이 "test 피싱"입니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-181">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="fb0ef-182">이 형식을 따르지 않는 메시지는 제출 포털에서 올바르게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0ef-182">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
