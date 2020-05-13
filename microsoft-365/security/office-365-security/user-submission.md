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
ms.openlocfilehash: 7b4b913a29c3eb16286d5a2874fe48bbc1c121fe
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208504"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="30816-103">Exchange Online에서 스팸 및 피싱 메시지의 사용자 제출을 위한 사서함 지정</span><span class="sxs-lookup"><span data-stu-id="30816-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="30816-104">Exchange Online 사서함이 있는 Microsoft 365 조 직에서는 사용자가 악성 메일로 보고 하는 메시지를 수신 하는 사서함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="30816-105">사용자가 다양 한 보고 옵션을 사용 하 여 메시지를 전송 하는 경우이 사서함을 사용 하 여 메시지를 가로채 며 (사용자 지정 사서함에만 보냄) 메시지 복사본을 받을 수 있습니다 (사용자 지정 사서함 및 Microsoft로 보내기).</span><span class="sxs-lookup"><span data-stu-id="30816-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="30816-106">이 기능은 다음과 같은 메시지 보고 옵션에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="30816-107">보고서 메시지 추가 기능</span><span class="sxs-lookup"><span data-stu-id="30816-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="30816-108">웹용 Outlook (이전의 Outlook Web App) [에 기본적으로 제공 되는 보고 기능](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)</span><span class="sxs-lookup"><span data-stu-id="30816-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="30816-109">또한 타사 메시지 보고 도구를 구성 하 여 지정한 사서함에 메시지를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="30816-110">사용자가 보고 한 메시지를 Microsoft에 직접 배포 하는 대신 사용자 지정 사서함에 전달 하면 관리자가 [관리 제출을](admin-submission.md)사용 하 여 메시지를 선택적으로 수동으로 microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="30816-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="30816-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="30816-112"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="30816-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="30816-113">**사용자 전송** 페이지로 직접 이동 하려면를 사용 <https://protection.office.com/userSubmissionsReportMessage> 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="30816-114">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30816-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="30816-115">Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30816-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="30816-116">이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="30816-117">사용자 제출을 위한 사서함을 구성 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="30816-118">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30816-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="30816-119">보안 & 준수 센터를 사용 하 여 사용자 전송 사서함을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="30816-120">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **사용자 전송**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="30816-121">**사용자 제출** 페이지가 나타나면 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="30816-122">**Outlook에 대 한 보고서 메시지 기능 사용 (권장)**: 웹에서 보고서 메시지 추가 기능 또는 기본 제공 보고를 사용 하는 경우이 옵션을 선택 하 고 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="30816-123">**최종 사용자에 게 확인 메시지를 사용자 지정**:이 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="30816-124">표시 되는 **확인 메시지 플라이 아웃 사용자 지정** 에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="30816-125">**제출 전**: **제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 하기 전에 표시 되는 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="30816-126">전송 유형 (정크, 정크 메일 아님, 피싱 등)을 포함 하 여% type% 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="30816-127">설명 했 듯이 다음과 같은 텍스트도 알림에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30816-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="30816-128">전자 메일이 분석을 위해 Microsoft에 게 제출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30816-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="30816-129">일부 전자 메일에는 개인 정보나 중요 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="30816-130">**제출 후** ![ 확장 아이콘을 클릭 ](../../media/scc-expand-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="30816-131">**제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 한 후에 표시 되는 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="30816-132">전송 유형을 포함 하기 위해% type% 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="30816-133">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="30816-134">이러한 값을 지우려면 **사용자 전송** 페이지에서 다시 **복원을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="30816-135">**보고 된 메시지를 보낼**위치: 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="30816-136">**Microsoft (권장)**: 사용자 제출 사서함이 사용 되지 않습니다 (보고 된 모든 메시지는 Microsoft로 이동 됨).</span><span class="sxs-lookup"><span data-stu-id="30816-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="30816-137">**Microsoft 및 사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="30816-138">메일 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-138">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="30816-139">**사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-139">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="30816-140">메일 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-140">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="30816-141">작업이 완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-141">When you're finished, click **Confirm**.</span></span>

     ![보고 된 메시지를 Microsoft 및 사용자 지정 사서함으로 보내기](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="30816-143">**Outlook에 대 한 보고서 메시지 기능 사용 안 함**:이 옵션을 선택 하면 보고서 메시지 추가 기능 대신 타사 보고 도구를 사용 하거나, 웹에서 Outlook에서 기본 제공 되는 보고를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30816-143">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="30816-144">**사용자가 보고 한 제출을 수신 하려면이 사용자 지정 사서함 사용을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-144">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="30816-145">상자가 나타나면 기존 사서함의 전자 메일 주소 또는 만들려는 사서함의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-145">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="30816-146">작업이 완료 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30816-146">When you're finished, click **Confirm**.</span></span>

     ![타사 도구를 사용 하 여 보고 된 메시지를 사용자 지정 사서함으로 보내기](../../media/user-submission-disable-outlook-report-message.png)
