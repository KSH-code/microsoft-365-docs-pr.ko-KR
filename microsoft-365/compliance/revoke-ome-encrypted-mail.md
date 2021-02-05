---
title: 고급 메시지 암호화로 암호화된 전자 메일 해지
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 관리자 및 메시지 보낸 사람은 Office 365 고급 메시지 암호화로 암호화된 특정 전자 메일을 해지할 수 있습니다.
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105143"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="0b30e-103">고급 메시지 암호화로 암호화된 전자 메일 해지</span><span class="sxs-lookup"><span data-stu-id="0b30e-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="0b30e-104">전자 메일 해지는 Office 365 고급 메시지 암호화의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="0b30e-105">Office 365 고급 메시지 암호화는 [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5(비영리 직원 가격), Office 365 Enterprise E5(비영리 직원 가격 책정) 및 Office 365 Education A5에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="0b30e-106">조직에 Office 365 고급 메시지 암호화를 포함하지 않는 구독이 있는 경우 Microsoft 365 E3, Microsoft 365 E3(비영리 직원 가격) 또는 Microsoft 365 E3, Microsoft 365 E3(비영리 직원 가격) 또는 Office 365 SKU용 Office 365 고급 준수 SKU 추가 기능으로 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="0b30e-107">이 문서는 Office 365 메시지 암호화에 대한 보다 많은 문서 [시리즈의 일부입니다.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="0b30e-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="0b30e-108">Office 365 고급 메시지 암호화를 사용하여 메시지를 암호화한 경우 Microsoft 365 관리자 또는 메시지를 보낸 사람인 경우 특정 조건에서 메시지를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="0b30e-109">관리자는 PowerShell을 사용하여 메시지를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="0b30e-110">보낸 사람이 웹에서 Outlook에서 직접 보낸 메시지를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="0b30e-111">이 문서에서는 해지가 가능한 상황과 해지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="0b30e-112">해지할 수 있는 암호화된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="0b30e-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="0b30e-113">받는 사람이 링크 기반의 브랜드로 암호화된 전자 메일을 받은 경우 관리자 및 메시지 보낸 사람은 암호화된 전자 메일을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="0b30e-114">받는 사람이 지원되는 Outlook 클라이언트에서 기본 인라인 환경을 받은 경우 메시지를 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="0b30e-115">받는 사람이 링크 기반 환경을 받는지 인라인 환경인지 여부는 받는 사람 ID 유형에 따라 다릅니다. Office 365 및 Microsoft 계정 받는 사람(예: outlook.com 사용자)은 지원되는 Outlook 클라이언트에서 인라인 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="0b30e-116">Gmail 및 Yahoo 받는 사람과 같은 다른 모든 받는 사람 유형은 링크 기반 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="0b30e-117">관리자와 메시지 보낸 사람이 웹용 Outlook에서 직접 적용한 암호화를 사용하여 암호화된 메시지를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="0b30e-118">예를 들어 암호화 전용 옵션을 사용하여 암호화된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot showing Encrypt Only option in Outlook on the web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="0b30e-120">해지된 암호화된 전자 메일의 받는 사람 환경</span><span class="sxs-lookup"><span data-stu-id="0b30e-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="0b30e-121">전자 메일이 해지된 후 받는 사람은 Office 365 메시지 암호화 포털을 통해 암호화된 전자 메일에 액세스할 때 "보낸 사람이 메시지를 해지했습니다."라는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![해지된 암호화된 전자 메일을 보여 주는 스크린샷.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="0b30e-123">전송한 암호화된 메시지를 해지하는 방법</span><span class="sxs-lookup"><span data-stu-id="0b30e-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="0b30e-124">단일 받는 사람에게 보낸 메일(예: gmail.com 또는 사용자 계정)을 해지할 수 yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="0b30e-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="0b30e-125">즉, 링크 기반 환경을 수신한 단일 받는 사람에게 전송된 전자 메일을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="0b30e-126">Office 365 또는 Microsoft 365에서 직장 또는 학교 계정을 사용하는 받는 사람 또는 Microsoft 계정을 사용하는 사용자(예: outlook.com 계정)에게 보낸 메일은 해지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="0b30e-127">전송한 암호화된 메시지를 해지하기 위해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="0b30e-128">웹에서 Outlook의 **Sent** 폴더에서 해지할 메시지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="0b30e-129">메일을 해지할 수 있는 경우 메시지 맨 위에 "외부 액세스 제거" 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="웹에서 Outlook에서 해지하려는 암호화된 메일을 보여 주는 스크린샷.":::

2. <span data-ttu-id="0b30e-131">외부 **액세스 제거를 클릭하여** 메시지를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="0b30e-132">메시지에 해당 상태가 해지된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot showing revoked encrypted message in Outlook on the web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="0b30e-134">관리자 권한으로 암호화된 메시지를 해지하는 방법</span><span class="sxs-lookup"><span data-stu-id="0b30e-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="0b30e-135">Microsoft 365 관리자는 다음과 같은 일반적인 단계에 따라 적합한 암호화된 전자 메일을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="0b30e-136">전자 메일의 메시지 ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="0b30e-137">메시지를 취소할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="0b30e-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="0b30e-138">메일을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="0b30e-139">1단계.</span><span class="sxs-lookup"><span data-stu-id="0b30e-139">Step 1.</span></span> <span data-ttu-id="0b30e-140">전자 메일의 메시지 ID 얻기</span><span class="sxs-lookup"><span data-stu-id="0b30e-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="0b30e-141">암호화된 메일을 해지하기 전에 메일의 메시지 ID를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="0b30e-142">MessageId는 일반적으로 다음 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="0b30e-143">해지할 전자 메일의 메시지 ID를 찾는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="0b30e-144">이 섹션에서는 몇 가지 옵션에 대해 설명하지만 ID를 제공하는 모든 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="0b30e-145">보안 준수 센터에서 메시지 추적을 사용하여 해지하려는 전자 메일의 메시지 ID를 &amp; 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="0b30e-146">보안 및 준수 센터에서 새 메시지 추적을 사용하여 보낸 [& 검색합니다.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="0b30e-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="0b30e-147">전자 메일을 들은 후 선택 하 고 메시지 추적 세부 **정보** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="0b30e-148">추가 **정보를 확장하여** 메시지 ID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="0b30e-149">보안 준수 센터에서 Office 메시지 암호화 보고서를 사용하여 해지할 전자 메일의 메시지 ID를 &amp; 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="0b30e-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="0b30e-150">보안 준수 센터에서 메시지 &amp; 암호화 **보고서로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b30e-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="0b30e-151">이 보고서에 대한 자세한 내용은 보안 준수 센터에서 전자 메일 보안 보고서 [ &amp; 보기를 참조하세요.](../security/office-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="0b30e-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="0b30e-152">세부 **정보 보기 테이블을** 선택하고 취소할 메시지를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="0b30e-153">메시지를 두 번 클릭하여 메시지 ID가 포함된 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="0b30e-154">2단계.</span><span class="sxs-lookup"><span data-stu-id="0b30e-154">Step 2.</span></span> <span data-ttu-id="0b30e-155">메일이 해지 가능한지 확인</span><span class="sxs-lookup"><span data-stu-id="0b30e-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="0b30e-156">메시지를 해지할 수 있는지 확인을 위해 보안 준수 센터의 세부 정보 표에 있는  암호화 보고서에 해지 상태 필드가 표시되는지 &amp; 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="0b30e-157">전자 메일 메시지를 사용하여 특정 전자 메일 메시지를 취소할 수 있는지 여부를 확인 Windows PowerShell 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="0b30e-158">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 Exchange Online에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="0b30e-159">지침을 확인하려면 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b30e-159">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="0b30e-160">다음과 Get-OMEMessageStatus cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="0b30e-161">이 명령은 메시지의 제목과 메시지를 취소할 수 있는지 여부를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="0b30e-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="0b30e-163">3단계.</span><span class="sxs-lookup"><span data-stu-id="0b30e-163">Step 3.</span></span> <span data-ttu-id="0b30e-164">메일 해지</span><span class="sxs-lookup"><span data-stu-id="0b30e-164">Revoke the mail</span></span>

<span data-ttu-id="0b30e-165">해지할 전자 메일의 메시지 ID를 알고 메시지를 해지할 수 있는 것으로 확인되면 보안 준수 센터 또는 해지 방법을 사용하여 전자 메일을 &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b30e-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="0b30e-166">보안 준수 센터를 사용하여 메시지를 &amp; 해지</span><span class="sxs-lookup"><span data-stu-id="0b30e-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="0b30e-167">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 보안 및 준수 & 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="0b30e-168">암호화 **보고서의** **메시지에** 대한 세부 정보 표에서 메시지 **취소를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="0b30e-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="0b30e-169">사용자 계정을 사용하여 전자 메일을 Windows PowerShell Set-OMEMessageRevocation cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0b30e-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="0b30e-170">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://aka.ms/exopowershell)</span><span class="sxs-lookup"><span data-stu-id="0b30e-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="0b30e-171">다음과 Set-OMEMessageRevocation cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="0b30e-172">전자 메일이 해지되어 있는지 확인을 위해 다음과 Get-OMEMessageStatus cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="0b30e-173">해지에 성공하면 cmdlet은 다음 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b30e-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="0b30e-174">Office 365 고급 메시지 암호화에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="0b30e-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="0b30e-175">Office 365 고급 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="0b30e-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="0b30e-176">Office 365 고급 메시지 암호화 - 전자 메일 만료</span><span class="sxs-lookup"><span data-stu-id="0b30e-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="0b30e-177">메시지 정책 및 규정 준수 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="0b30e-177">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
