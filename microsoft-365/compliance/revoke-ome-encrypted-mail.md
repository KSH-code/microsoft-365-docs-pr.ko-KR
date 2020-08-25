---
title: 고급 메시지 암호화로 암호화 된 전자 메일 해지
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
description: 관리자 및 메시지 보낸 사람으로 서 Office 365 고급 메시지 암호화를 사용 하 여 암호화 된 특정 전자 메일을 해지할 수 있습니다.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868956"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="81ede-103">고급 메시지 암호화로 암호화 된 전자 메일 해지</span><span class="sxs-lookup"><span data-stu-id="81ede-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="81ede-104">전자 메일 해지가 Office 365 Advanced Message 암호화의 일부로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="81ede-105">Office 365 Advanced Message Encryption은 [microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (비영리 스태프 가격), Office 365 Enterprise E5 (비영리 스태프 가격) 및 Office 365 교육용 A5에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="81ede-106">조직에서 Office 365 고급 메시지 암호화를 포함 하지 않는 구독을 사용 하는 경우 microsoft 365 E3, microsoft 365 E3 (비영리 직원 가격) 또는 Microsoft 365 (고급 규정 준수) 용 microsoft 365 e3, Microsoft 365 E3 (비영리 스태프 가격) 또는 Office 365 Sku에 대 한 Office 준수 sku 추가 기능을 사용해 서 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="81ede-107">이 문서는 [Office 365 메시지 암호화](ome.md)에 대 한 보다 광범위 한 문서에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="81ede-108">메시지가 Office 365 고급 메시지 암호화를 사용 하 여 암호화 되었지만 Microsoft 365 관리자 이거나 메시지를 보낸 사용자 인 경우 특정 조건에 따라 메시지를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="81ede-109">관리자 PowerShell을 사용 하 여 메시지를 해지 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="81ede-110">보낸 사람은 웹에서 Outlook을 통해 직접 보낸 메시지를 해지 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="81ede-111">이 문서에서는 해지가 가능한 상황 및 수행 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="81ede-112">해지할 수 있는 암호화 된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="81ede-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="81ede-113">받는 사람이 링크 기반 브랜드의 암호화 된 전자 메일을 받은 경우 관리자 및 메시지 보낸 사람은 암호화 된 전자 메일을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="81ede-114">받는 사람이 지원 되는 Outlook 클라이언트에서 기본 인라인 환경을 받은 경우 메시지를 해지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="81ede-115">받는 사람이 링크 기반 환경이 나 인라인 환경을 수신 하는지 여부는 받는 사람 id 유형에 따라 다릅니다. Office 365 및 Microsoft 계정 받는 사람 (예: outlook.com users)은 지원 되는 Outlook 클라이언트에서 인라인 환경을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="81ede-116">Gmail 및 Yahoo 받는 사람과 같은 다른 모든 받는 사람 유형은 링크 기반 환경을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="81ede-117">관리자 및 메시지 보낸 사람은 웹용 Outlook에서 직접 암호화를 적용 하 여 암호화 된 메시지를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="81ede-118">예를 들어 암호화만 옵션을 사용 하 여 암호화 된 메시지</span><span class="sxs-lookup"><span data-stu-id="81ede-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="웹용 Outlook의 암호화만 옵션을 보여 주는 스크린샷":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="81ede-120">해지 된 암호화 전자 메일에 대 한 받는 사람 환경</span><span class="sxs-lookup"><span data-stu-id="81ede-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="81ede-121">전자 메일이 해지 되 면 Office 365 메시지 암호화 포털: "보낸 사람이 메시지를 철회 했습니다." 라는 오류가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![암호화 된 전자 메일을 해지 한 것을 보여 주는 스크린샷](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="81ede-123">보낸 암호화 된 메시지를 해지 하는 방법</span><span class="sxs-lookup"><span data-stu-id="81ede-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="81ede-124">보낸 암호화 된 메시지를 해지 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="81ede-125">웹용 Outlook의 **보낸** 편지함 폴더에서 해지할 메시지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="81ede-126">메일이 revocable 경우 메시지 맨 위에 "외부 액세스 제거" 링크가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="웹용 Outlook에서 해지할 암호화 된 메일을 보여 주는 스크린샷":::

2. <span data-ttu-id="81ede-128">**외부 액세스 제거** 를 클릭 하 여 메시지를 해지 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="81ede-129">메시지에 해당 상태가 해지 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="웹용 Outlook에서 해지 된 암호화 메시지를 보여 주는 스크린샷":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="81ede-131">암호화 된 메시지를 관리자로 해지 하는 방법</span><span class="sxs-lookup"><span data-stu-id="81ede-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="81ede-132">Microsoft 365 관리자는 다음과 같은 일반적인 단계를 수행 하 여 적합 한 암호화 된 전자 메일을 해지 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="81ede-133">전자 메일의 메시지 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="81ede-134">메시지를 해지할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="81ede-135">메일을 해지 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="81ede-136">1단계.</span><span class="sxs-lookup"><span data-stu-id="81ede-136">Step 1.</span></span> <span data-ttu-id="81ede-137">전자 메일의 메시지 ID 가져오기</span><span class="sxs-lookup"><span data-stu-id="81ede-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="81ede-138">암호화 된 메일을 해지 하려면 먼저 메일의 메시지 ID를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="81ede-139">MessageId는 대개 다음 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="81ede-140">해지할 전자 메일의 메시지 ID를 확인 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="81ede-141">이 섹션에서는 몇 가지 옵션에 대해 설명 하지만 ID를 제공 하는 모든 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="81ede-142">보안 및 준수 센터에서 메시지 추적을 사용 하 여 해지할 전자 메일의 메시지 ID를 식별 하려면 &amp;</span><span class="sxs-lookup"><span data-stu-id="81ede-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="81ede-143">[보안 & 준수 센터에서 새 메시지 추적을](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)사용 하 여 보낸 사람이 나 받는 사람에 게 전자 메일을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="81ede-144">전자 메일을 찾은 후에는이를 선택 하 여 **메시지 추적 세부 정보** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="81ede-145">**자세한 정보** 를 확장 하 여 메시지 ID를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="81ede-146">보안 및 준수 센터에서 Office 메시지 암호화 보고서를 사용 하 여 해지할 전자 메일의 메시지 ID를 식별 하려면 &amp;</span><span class="sxs-lookup"><span data-stu-id="81ede-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="81ede-147">보안 &amp; 및 준수 센터에서 **메시지 암호화 보고서**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="81ede-148">이 보고서에 대 한 자세한 내용은 [보안 및 &amp; 준수 센터의 전자 메일 보안 보고서 보기](../security/office-365-security/view-email-security-reports.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81ede-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="81ede-149">**정보 보기** 테이블을 선택 하 고 해지할 메시지를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="81ede-150">메시지를 두 번 클릭 하 여 메시지 ID를 포함 하는 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="81ede-151">2단계.</span><span class="sxs-lookup"><span data-stu-id="81ede-151">Step 2.</span></span> <span data-ttu-id="81ede-152">메일이 revocable 확인</span><span class="sxs-lookup"><span data-stu-id="81ede-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="81ede-153">메시지를 취소할 수 있는지 여부를 확인 하려면 보안 및 준수 센터의 **Details (정보** ) 테이블에서 암호화 보고서에 해지 상태 필드를 표시할지 여부를 확인 &amp; 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="81ede-154">Windows PowerShell을 사용 하 여 특정 전자 메일 메시지를 해지할 수 있는지 여부를 확인 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="81ede-155">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell 세션을 시작 하 고 Exchange Online에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="81ede-156">지침을 확인하려면 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81ede-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="81ede-157">다음과 같이 OMEMessageStatus cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="81ede-158">이 명령은 메시지의 제목과 메시지의 revocable 여부를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="81ede-159">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="81ede-160">3단계.</span><span class="sxs-lookup"><span data-stu-id="81ede-160">Step 3.</span></span> <span data-ttu-id="81ede-161">메일 해지</span><span class="sxs-lookup"><span data-stu-id="81ede-161">Revoke the mail</span></span>

<span data-ttu-id="81ede-162">해지할 전자 메일의 메시지 ID를 알고 있고 메시지가 revocable 확인 되 면 보안 &amp; 준수 센터 또는 Windows PowerShell을 사용 하 여 전자 메일을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="81ede-163">보안 및 준수 센터를 사용 하 여 메시지를 해지 하려면 &amp;</span><span class="sxs-lookup"><span data-stu-id="81ede-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="81ede-164">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 보안 & 준수 센터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="81ede-165">**암호화 보고서**의 메시지에 대 한 **세부 정보** 테이블에서 **메시지 취소**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="81ede-166">Windows PowerShell을 사용 하 여 전자 메일을 해지 하려면 OMEMessageRevocation cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="81ede-167">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하는 경우 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="81ede-168">다음과 같이 OMEMessageRevocation cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="81ede-169">전자 메일이 해지 되었는지 확인 하려면 다음과 같이 OMEMessageStatus cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="81ede-170">해지가 성공한 경우 cmdlet은 다음 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ede-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="81ede-171">Office 365 고급 메시지 암호화에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="81ede-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="81ede-172">Office 365 고급 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="81ede-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="81ede-173">Office 365 고급 메시지 암호화-전자 메일 만료</span><span class="sxs-lookup"><span data-stu-id="81ede-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="81ede-174">메시지 정책 및 규정 준수 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="81ede-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
