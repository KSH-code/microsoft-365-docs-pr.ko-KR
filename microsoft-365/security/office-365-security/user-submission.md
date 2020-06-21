---
title: 스팸 및 피싱 메시지의 사용자 제출을 위한 사서함 지정
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
ms.collection:
- M365-security-compliance
description: 관리자는 사용자가 보고 하는 스팸 및 피싱 전자 메일을 수집 하도록 사서함을 구성 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: e9550ce6357ddf19041e752c17e8bd844cba1a11
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726500"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="f4d67-103">Exchange Online에서 스팸 및 피싱 메시지의 사용자 제출을 위한 사서함 지정</span><span class="sxs-lookup"><span data-stu-id="f4d67-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="f4d67-104">Exchange Online 사서함이 있는 Microsoft 365 조 직에서는 사용자가 악성 메일로 보고 하는 메시지를 수신 하는 사서함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="f4d67-105">사용자가 다양 한 보고 옵션을 사용 하 여 메시지를 전송 하는 경우이 사서함을 사용 하 여 메시지를 가로채 며 (사용자 지정 사서함에만 보냄) 메시지 복사본을 받을 수 있습니다 (사용자 지정 사서함 및 Microsoft로 보내기).</span><span class="sxs-lookup"><span data-stu-id="f4d67-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="f4d67-106">이 기능은 다음과 같은 메시지 보고 옵션에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="f4d67-107">보고서 메시지 추가 기능</span><span class="sxs-lookup"><span data-stu-id="f4d67-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="f4d67-108">웹용 Outlook (이전의 Outlook Web App) [에 기본적으로 제공 되는 보고 기능](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f4d67-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="f4d67-109">[웹에서 outlook에서 보고를 사용 하지 않도록](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)설정한 경우 여기서 사용자 제출을 사용 하도록 설정 하면 해당 설정이 무시 되 고 사용자가 웹에서 Outlook에서 메시지를 다시 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="f4d67-110">또한 타사 메시지 보고 도구를 구성 하 여 지정한 사서함에 메시지를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="f4d67-111">사용자가 보고 한 메시지를 Microsoft에 직접 배포 하는 대신 사용자 지정 사서함에 전달 하면 관리자가 [관리 제출을](admin-submission.md)사용 하 여 메시지를 선택적으로 수동으로 microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4d67-112">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f4d67-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4d67-113"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f4d67-114">**사용자 전송** 페이지로 직접 이동 하려면를 사용 <https://protection.office.com/userSubmissionsReportMessage> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="f4d67-115">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4d67-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f4d67-116">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4d67-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f4d67-117">이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f4d67-118">사용자 전송에 대 한 구성을 수정 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-118">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f4d67-119">[보안 & 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="f4d67-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f4d67-120">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 또는 **바이러스 관리**</span><span class="sxs-lookup"><span data-stu-id="f4d67-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f4d67-121">사용자 전송에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-121">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f4d67-122">보안 [& 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 독자**</span><span class="sxs-lookup"><span data-stu-id="f4d67-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f4d67-123">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="f4d67-124">보안 & 준수 센터를 사용 하 여 사용자 전송 사서함을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-124">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="f4d67-125">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **사용자 전송**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="f4d67-126">**사용자 제출** 페이지가 나타나면 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-126">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="f4d67-127">a.</span><span class="sxs-lookup"><span data-stu-id="f4d67-127">a.</span></span> <span data-ttu-id="f4d67-128">**Outlook에 대 한 보고서 메시지 기능 사용 (권장)**: 웹에서 보고서 메시지 추가 기능 또는 기본 제공 보고를 사용 하는 경우이 옵션을 선택 하 고 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-128">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="f4d67-129">**최종 사용자에 게 확인 메시지를 사용자 지정**:이 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-129">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="f4d67-130">표시 되는 **확인 메시지 플라이 아웃 사용자 지정** 에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-130">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="f4d67-131">**제출 전**: **제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 하기 전에 표시 되는 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-131">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="f4d67-132">전송 유형 (정크, 정크 메일 아님, 피싱 등)을 포함 하 여% type% 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-132">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="f4d67-133">앞에서 설명한 것 처럼, 보고 된 메시지를 Microsoft로 보내는 옵션을 선택 하면 다음과 같은 텍스트도 알림에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-133">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="f4d67-134">전자 메일이 분석을 위해 Microsoft에 게 제출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-134">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="f4d67-135">일부 전자 메일에는 개인 정보나 중요 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-135">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="f4d67-136">**제출 후** ![ 확장 아이콘을 클릭 ](../../media/scc-expand-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-136">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="f4d67-137">**제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 한 후에 표시 되는 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-137">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="f4d67-138">전송 유형을 포함 하기 위해% type% 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-138">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="f4d67-139">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-139">When you're finished, click **Save**.</span></span> <span data-ttu-id="f4d67-140">이러한 값을 지우려면 **사용자 전송** 페이지에서 다시 **복원을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-140">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="f4d67-141">**보고 된 메시지를 보낼**위치: 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-141">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="f4d67-142">**Microsoft (권장)**: 사용자 제출 사서함이 사용 되지 않습니다 (보고 된 모든 메시지는 Microsoft로 이동 됨).</span><span class="sxs-lookup"><span data-stu-id="f4d67-142">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="f4d67-143">**Microsoft 및 사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-143">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="f4d67-144">메일 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-144">Distribution groups are not allowed.</span></span> <span data-ttu-id="f4d67-145">사용자 제출은 Microsoft for analysis와 관리자 또는 보안 운영 팀이 분석 하기 위한 사용자 지정 사서함으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-145">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="f4d67-146">**사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-146">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="f4d67-147">메일 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-147">Distribution groups are not allowed.</span></span> <span data-ttu-id="f4d67-148">이 옵션을 사용 하 여 메시지를 먼저 분석을 위해 관리자 또는 보안 운영 팀 으로만 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-148">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="f4d67-149">관리자가 메시지를 직접 전달 하지 않으면 메시지가 Microsoft로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-149">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f4d67-150">미국 정부 기관 (GCC, GCC-H 및 DoD)은 **사용자 지정 사서함**만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-150">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="f4d67-151">다른 두 옵션은 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-151">The other two options are disabled.</span></span> 

      <span data-ttu-id="f4d67-152">작업이 완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-152">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="f4d67-153">웹 사서함 정책에서 Outlook을 사용 하 여 [웹용 outlook에서 정크 메일 보고를 사용 하지 않도록 설정](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 했지만 microsoft에 메시지를 보고 하는 이전 설정 중 하나를 구성 하는 경우 사용자는 보고서 메시지 추가 기능을 사용 하 여 웹용 Outlook에서 Microsoft에 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-153">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="f4d67-154">**Outlook에 대 한 보고서 메시지 기능 사용 안 함**:이 옵션을 선택 하면 보고서 메시지 추가 기능 대신 타사 보고 도구를 사용 하거나, 웹에서 Outlook에서 기본 제공 되는 보고를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-154">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="f4d67-155">**사용자가 보고 한 제출을 수신 하려면이 사용자 지정 사서함 사용을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-155">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="f4d67-156">상자가 나타나면 이미 Office 365에 있는 기존 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-156">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="f4d67-157">이는 전자 메일을 받을 수 있는 Exchange Online의 기존 사서함 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-157">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="f4d67-158">작업이 완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-158">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="f4d67-159">메시지 전송 형식</span><span class="sxs-lookup"><span data-stu-id="f4d67-159">Message submission format</span></span>

<span data-ttu-id="f4d67-160">사용자 지정 사서함에 전송 된 메시지는 특정 전송 메일 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-160">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="f4d67-161">제출 서류의 제목 (봉투 제목)은 다음과 같은 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-161">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="f4d67-162">(으)로이 함수는 다음 정수 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-162">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="f4d67-163">1: 정크</span><span class="sxs-lookup"><span data-stu-id="f4d67-163">1: Junk</span></span>
- <span data-ttu-id="f4d67-164">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="f4d67-164">2: NotJunk</span></span>
- <span data-ttu-id="f4d67-165">3: 피싱</span><span class="sxs-lookup"><span data-stu-id="f4d67-165">3: Phish</span></span>

<span data-ttu-id="f4d67-166">다음 예제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-166">In the following example:</span></span>

- <span data-ttu-id="f4d67-167">메시지가 피싱으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-167">The message is being reported as Phish.</span></span>
- <span data-ttu-id="f4d67-168">네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-168">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="f4d67-169">보낸 사람 IP는 167.220.232.101입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-169">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="f4d67-170">보낸 사람 주소는 test@contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-170">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="f4d67-171">메시지의 제목 줄이 "test 피싱"입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-171">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="f4d67-172">이 형식을 따르지 않는 메시지는 제출 포털에서 올바르게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d67-172">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
