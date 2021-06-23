---
title: 관리자 제출
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Microsoft 365 Defender 포털에서 제출 포털을 사용하여 의심스러운 전자 메일, 피싱 메일, 스팸 및 기타 유해한 메시지, URL 및 전자 메일 첨부 파일을 다시 검색하기 위해 Microsoft에 제출하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab25757c79b7978400e98fa36d48163e1681e7c1
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062000"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="5f06a-103">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="5f06a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f06a-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="5f06a-104">**Applies to**</span></span>
- [<span data-ttu-id="5f06a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5f06a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5f06a-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="5f06a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="5f06a-107">Microsoft 365 사서함이 Exchange Online 조직에서 관리자는 Microsoft 365 Defender 포털의 제출 포털을 사용하여 검색을 위해 전자 메일 메시지, URL 및 첨부 파일을 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="5f06a-108">전자 메일 메시지를 제출하면 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="5f06a-109">**전자 메일 인증 확인:** 전자 메일 인증이 전달될 때 통과 또는 실패한 경우의 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="5f06a-110">**정책 적중:** 테넌트로 들어오는 전자 메일을 허용하거나 차단할 수 있는 정책에 대한 정보로, 서비스 필터 판정을 어버렸다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="5f06a-111">**페이로드 신뢰도/확인:** 메시지의 URL 및 첨부 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="5f06a-112">**성적 분석:** 휴먼 등급이 수행한 검토를 통해 메시지가 악성인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f06a-113">페이로드 신뢰도/분석 및 등급 분석은 모든 테넌트에서 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="5f06a-114">데이터가 규정 준수를 위해 테넌트 경계를 떠날 수 없는 경우 정보가 조직 외부로 나가지 못하도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="5f06a-115">Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 제출하는 다른 방법은 Microsoft에 메시지 및 파일 보고를 [참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5f06a-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5f06a-116">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="5f06a-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5f06a-117"><https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5f06a-118">제출 **페이지로** 직접 이동하기 위해 를 <https://security.microsoft.com/reportsubmission> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5f06a-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="5f06a-119">메시지와 파일을 Microsoft에 제출하려면 다음 역할 그룹 중 하나의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="5f06a-120">**조직 포털의** 조직 관리 [또는 보안 Microsoft 365 Defender.](permissions-microsoft-365-security-center.md) </span><span class="sxs-lookup"><span data-stu-id="5f06a-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="5f06a-121">**에서 조직** [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="5f06a-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="5f06a-122">이 역할 그룹의 구성원 자격은 [](#view-user-submissions-to-microsoft) 이 문서의 부분에서 설명하는 사용자 지정 사서함에 대한 사용자 전송 보기에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="5f06a-123">사용자가 Microsoft에 메시지와 파일을 제출하는 방법에 대한 자세한 내용은 Microsoft에 메시지 및 파일 [보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5f06a-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="5f06a-124">Microsoft에 의심스러운 콘텐츠 보고</span><span class="sxs-lookup"><span data-stu-id="5f06a-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="5f06a-125">Microsoft 365 Defender 포털에서 전자 메일 &  \> **제출로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="5f06a-126">제출 **페이지에서** 분석용 **제출** 탭이 선택되어 있는지 확인한 다음 분석을 위해 Microsoft에 광고 아이콘 ![ ](../../media/m365-cc-sc-create-icon.png) **제출을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="5f06a-127">다음 **섹션에** 설명된 메시지, URL 또는 전자 메일 첨부 파일을 제출하는 것으로 나타나는 검토 플라이아웃을 위해 Microsoft에 제출을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="5f06a-128">Microsoft에 질문이 있는 전자 메일 제출</span><span class="sxs-lookup"><span data-stu-id="5f06a-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="5f06a-129">제출 **유형 선택 상자의** 드롭다운 목록에서 전자 메일이 선택되어 있는지 확인해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="5f06a-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="5f06a-130">네트워크 메시지 **ID 추가 또는** 전자 메일 파일 업로드 섹션에서 다음 옵션 중 하나를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5f06a-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="5f06a-131">**전자** 메일 네트워크 메시지 ID 추가: 이 값은 메시지의 **X-MS-Exchange-Organization-Network-Message-Id** 헤더 또는 분리된 메시지의 **X-MS-Office365-Filtering-Correlation-Id** 헤더에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="5f06a-132">**업로드 파일(.msg 또는 .eml)**: 파일 **찾아보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="5f06a-133">대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5f06a-134">30일이 지난 메시지를 전송하는 능력은 모든 고객에 대해 Defender에 대해 Office 365 일시적으로 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="5f06a-135">관리자는 7일만 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="5f06a-136">문제가 **있는** 받는 사람 선택 상자에서 정책을 실행할 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="5f06a-137">정책 검사는 사용자 또는 조직 정책으로 인해 전자 메일이 검사를 무시한지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="5f06a-138">**Microsoft에** 제출할 이유 선택 섹션에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="5f06a-139">**차단되지 않은 경우(가음성)**</span><span class="sxs-lookup"><span data-stu-id="5f06a-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="5f06a-140">**차단된** 경우: 전자  메일이 나타나는 섹션으로 분류되어 있습니다. 섹션에서 다음 값 중 하나를 선택합니다(확실하지 않은 경우 최상의 판단 사용).</span><span class="sxs-lookup"><span data-stu-id="5f06a-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="5f06a-141">**피싱**</span><span class="sxs-lookup"><span data-stu-id="5f06a-141">**Phish**</span></span>
     - <span data-ttu-id="5f06a-142">**스팸**</span><span class="sxs-lookup"><span data-stu-id="5f06a-142">**Spam**</span></span>
     - <span data-ttu-id="5f06a-143">**맬웨어**</span><span class="sxs-lookup"><span data-stu-id="5f06a-143">**Malware**</span></span>

5. <span data-ttu-id="5f06a-144">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-144">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f06a-145">![새 URL 제출 예제](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="5f06a-145">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="5f06a-146">의심되는 URL을 Microsoft로 보내기</span><span class="sxs-lookup"><span data-stu-id="5f06a-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="5f06a-147">제출 **유형 선택 상자의** **드롭다운** 목록에서 URL을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="5f06a-148">나타나는 **URL 상자에** 전체 URL(예: )을 `https://www.fabrikam.com/marketing.html` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="5f06a-149">**Microsoft에** 제출할 이유 선택 섹션에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="5f06a-150">**차단되지 않은 경우(가음성)**</span><span class="sxs-lookup"><span data-stu-id="5f06a-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="5f06a-151">**차단된 항목:** 이 **URL이** 나타나는 섹션으로 분류되어 있습니다. 섹션에서 피싱 또는 맬웨어를 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="5f06a-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="5f06a-152">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-152">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f06a-153">![새 전자 메일 제출 예제](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="5f06a-153">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="5f06a-154">의심되는 전자 메일 첨부 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="5f06a-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="5f06a-155">제출 **유형 선택 상자의** **드롭다운** 목록에서 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="5f06a-156">나타나는 **파일** 섹션에서 파일 **찾아보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="5f06a-157">대화 상자가 열리면 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="5f06a-158">**Microsoft에** 제출할 이유 선택 섹션에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="5f06a-159">**차단되지 않은 경우(가음성)**</span><span class="sxs-lookup"><span data-stu-id="5f06a-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="5f06a-160">**차단된** 항목: 이 **URL을** 나타나는 섹션으로 분류해야 합니다.  맬웨어만 선택할 수 있으며 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="5f06a-161">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-161">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f06a-162">![새 첨부 파일 제출 예제](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="5f06a-162">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="5f06a-163">Microsoft에 대한 관리자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="5f06a-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="5f06a-164">Microsoft 365 Defender 포털에서 전자 메일 &  \> **제출로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="5f06a-165">제출 **페이지에서** 분석을 위해 제출된 **탭이** 선택되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f06a-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="5f06a-166">사용 가능한 열 헤더를 클릭하여 항목을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="5f06a-167">열 **사용자 지정을 클릭하여** 최대 7개의 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="5f06a-168">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="5f06a-169">**제출 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-170">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-170">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-171">**제출된 날짜**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-172">**제출 유형**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-173">**제출 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-174">**상태 다시 검색**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-175">**결과 다시 검색**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-176">**필터 판정**</span><span class="sxs-lookup"><span data-stu-id="5f06a-176">**Filter verdict**</span></span>
     - <span data-ttu-id="5f06a-177">**배달/차단 이유**</span><span class="sxs-lookup"><span data-stu-id="5f06a-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="5f06a-178">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="5f06a-178">**Submission ID**</span></span>
     - <span data-ttu-id="5f06a-179">**네트워크 메시지 ID/개체 ID**</span><span class="sxs-lookup"><span data-stu-id="5f06a-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="5f06a-180">**방향**</span><span class="sxs-lookup"><span data-stu-id="5f06a-180">**Direction**</span></span>
     - <span data-ttu-id="5f06a-181">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="5f06a-181">**Sender IP**</span></span>
     - <span data-ttu-id="5f06a-182">**BCL(대량 규격 수준)**</span><span class="sxs-lookup"><span data-stu-id="5f06a-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="5f06a-183">**대상**</span><span class="sxs-lookup"><span data-stu-id="5f06a-183">**Destination**</span></span>
     - <span data-ttu-id="5f06a-184">**정책 작업**</span><span class="sxs-lookup"><span data-stu-id="5f06a-184">**Policy action**</span></span>
     - <span data-ttu-id="5f06a-185">**제출한 인원**</span><span class="sxs-lookup"><span data-stu-id="5f06a-185">**Submitted by**</span></span>

     <span data-ttu-id="5f06a-186">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="5f06a-187">항목을 필터링하려면 필터 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="5f06a-188">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="5f06a-188">The available filters are:</span></span>
     - <span data-ttu-id="5f06a-189">**제출 날짜:** **시작 날짜 및** 종료 **날짜입니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="5f06a-190">**제출 유형:** **전자 메일,** **URL** 또는 **파일입니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="5f06a-191">**제출 ID:** 모든 제출에 할당된 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="5f06a-192">**네트워크 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="5f06a-192">**Network Message ID**</span></span>
     - <span data-ttu-id="5f06a-193">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="5f06a-193">**Sender**</span></span>

     <span data-ttu-id="5f06a-194">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-194">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="5f06a-195">![관리자 제출에 대한 새 필터 옵션](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="5f06a-195">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="5f06a-196">항목을 그룹화하려면 그룹을 **클릭하고** 드롭다운 목록에서 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="5f06a-197">**없음**</span><span class="sxs-lookup"><span data-stu-id="5f06a-197">**None**</span></span>
     - <span data-ttu-id="5f06a-198">**유형**</span><span class="sxs-lookup"><span data-stu-id="5f06a-198">**Type**</span></span>
     - <span data-ttu-id="5f06a-199">**이유**</span><span class="sxs-lookup"><span data-stu-id="5f06a-199">**Reason**</span></span>
     - <span data-ttu-id="5f06a-200">**상태**</span><span class="sxs-lookup"><span data-stu-id="5f06a-200">**Status**</span></span>
     - <span data-ttu-id="5f06a-201">**결과 다시 검색**</span><span class="sxs-lookup"><span data-stu-id="5f06a-201">**Rescan result**</span></span>

   - <span data-ttu-id="5f06a-202">항목을 내보내려면 내보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="5f06a-203">나타나는 대화 상자에서 파일 .csv 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="5f06a-204">관리자 제출 세부 정보 다시 검색</span><span class="sxs-lookup"><span data-stu-id="5f06a-204">Admin submission rescan details</span></span>

<span data-ttu-id="5f06a-205">관리자 제출에 제출된 메시지는 검토 및 결과 제출 세부 정보 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-205">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="5f06a-206">전송 시 보낸 사람의 전자 메일 인증에 오류가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="5f06a-207">메시지의 평가 결과에 영향을 주거나 재정의할 수 있는 정책 조회에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="5f06a-208">메시지에 포함된 URL 또는 파일이 악의적인지 여부를 확인하는 현재 데토네이션 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="5f06a-209">성적에 대한 피드백</span><span class="sxs-lookup"><span data-stu-id="5f06a-209">Feedback from graders.</span></span>

<span data-ttu-id="5f06a-210">재정의가 발견되면 몇 분 후에 다시 검색이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="5f06a-211">전자 메일 인증에 문제가 없는 경우 또는 배달이 오버라이드의 영향을 받지 않은 경우 등급의 피드백이 하루까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="5f06a-212">Microsoft에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="5f06a-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="5f06a-213">보고서 메시지 추가 기능, 피싱 보고 [](enable-the-report-phish-add-in.md)추가 기능 또는 웹용 Outlook 기본 제공 [](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)보고를 사용하는 경우 사용자가 보고하는 메시지를 사용자 보고 탭에서 볼 수 **있습니다.** [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="5f06a-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="5f06a-214">Microsoft 365 Defender 포털에서 전자 메일 &  \> **제출로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="5f06a-215">제출 **페이지에서** 사용자가 보고한 **메시지 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="5f06a-216">사용 가능한 열 헤더를 클릭하여 항목을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="5f06a-217">열 **사용자 지정을 클릭하여** 최대 7개의 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="5f06a-218">기본값은 별표(<sup>\*</sup>)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="5f06a-219">**전자 메일 제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-220">**보고한**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-220">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-221">**보고된 날짜**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-222">**보낸 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-223">**보고된 이유**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-224">**결과 다시 검색**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f06a-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="5f06a-225">**보고된 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="5f06a-225">**Message reported ID**</span></span>
     - <span data-ttu-id="5f06a-226">**네트워크 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="5f06a-226">**Network Message ID**</span></span>
     - <span data-ttu-id="5f06a-227">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="5f06a-227">**Sender IP**</span></span>
     - <span data-ttu-id="5f06a-228">**피싱 시뮬레이션**</span><span class="sxs-lookup"><span data-stu-id="5f06a-228">**Phish simulation**</span></span>

     <span data-ttu-id="5f06a-229">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="5f06a-230">항목을 필터링하려면 필터 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="5f06a-231">사용 가능한 필터:</span><span class="sxs-lookup"><span data-stu-id="5f06a-231">The available filters are:</span></span>
     - <span data-ttu-id="5f06a-232">**보고된 날짜:** **시작 날짜 및** 종료 **날짜입니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="5f06a-233">**보고한**</span><span class="sxs-lookup"><span data-stu-id="5f06a-233">**Reported by**</span></span>
     - <span data-ttu-id="5f06a-234">**전자 메일 제목**</span><span class="sxs-lookup"><span data-stu-id="5f06a-234">**Email subject**</span></span>
     - <span data-ttu-id="5f06a-235">**보고된 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="5f06a-235">**Message reported ID**</span></span>
     - <span data-ttu-id="5f06a-236">**네트워크 메시지 ID**</span><span class="sxs-lookup"><span data-stu-id="5f06a-236">**Network Message ID**</span></span>
     - <span data-ttu-id="5f06a-237">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="5f06a-237">**Sender**</span></span>
     - <span data-ttu-id="5f06a-238">**보고된 이유:** **정크** 메일 아님, **피싱** **또는** 스팸 .</span><span class="sxs-lookup"><span data-stu-id="5f06a-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="5f06a-239">**피싱 시뮬레이션:** **예** 또는 **아니요**</span><span class="sxs-lookup"><span data-stu-id="5f06a-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="5f06a-240">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-240">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="5f06a-241">![사용자 제출에 대한 새 필터 옵션](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="5f06a-241">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="5f06a-242">항목을 그룹화하려면 그룹을 **클릭하고** 드롭다운 목록에서 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="5f06a-243">**없음**</span><span class="sxs-lookup"><span data-stu-id="5f06a-243">**None**</span></span>
     - <span data-ttu-id="5f06a-244">**이유**</span><span class="sxs-lookup"><span data-stu-id="5f06a-244">**Reason**</span></span>
     - <span data-ttu-id="5f06a-245">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="5f06a-245">**Sender**</span></span>
     - <span data-ttu-id="5f06a-246">**보고한**</span><span class="sxs-lookup"><span data-stu-id="5f06a-246">**Reported by**</span></span>
     - <span data-ttu-id="5f06a-247">**결과 다시 검색**</span><span class="sxs-lookup"><span data-stu-id="5f06a-247">**Rescan result**</span></span>
     - <span data-ttu-id="5f06a-248">**피싱 시뮬레이션**</span><span class="sxs-lookup"><span data-stu-id="5f06a-248">**Phish simulation**</span></span>

   - <span data-ttu-id="5f06a-249">항목을 내보내려면 내보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f06a-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="5f06a-250">나타나는 대화 상자에서 파일 .csv 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="5f06a-251">조직에서 사용자 지정 사서함으로만 사용자 보고 메시지를 보내도록 구성된 경우 보고된 메시지는 다시 검색을 위해 전송되지 않습니다. **사용자** 보고 메시지의 결과는 항상 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="5f06a-252">사용자 제출 취소</span><span class="sxs-lookup"><span data-stu-id="5f06a-252">Undo user submissions</span></span>

<span data-ttu-id="5f06a-253">사용자가 의심스러운 전자 메일을 사용자 지정 사서함에 제출하면 사용자와 관리자는 제출을 취소할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="5f06a-254">사용자가 전자 메일을 복구하려면 지우기 항목 또는 정크 메일 폴더에서 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="5f06a-255">사용자 지정 사서함에서 Microsoft로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="5f06a-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="5f06a-256">Microsoft로 메시지를 보내지 않고 사용자가 보고한 메시지를 가로채도록 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아 Microsoft로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="5f06a-257">그러면 사용자 제출이 관리자 제출로 효과적으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="5f06a-258">사용자 **보고** 메시지 탭의 목록에서 메시지를 선택하고 분석을 위해 **Microsoft에** 제출을 클릭한 다음 드롭다운 목록에서 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f06a-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="5f06a-259">**정리 보고**</span><span class="sxs-lookup"><span data-stu-id="5f06a-259">**Report clean**</span></span>
- <span data-ttu-id="5f06a-260">**피싱 보고**</span><span class="sxs-lookup"><span data-stu-id="5f06a-260">**Report phishing**</span></span>
- <span data-ttu-id="5f06a-261">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="5f06a-261">**Report malware**</span></span>
- <span data-ttu-id="5f06a-262">**스팸 보고**</span><span class="sxs-lookup"><span data-stu-id="5f06a-262">**Report spam**</span></span>
- <span data-ttu-id="5f06a-263">**조사 트리거**</span><span class="sxs-lookup"><span data-stu-id="5f06a-263">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f06a-264">![동작 단추의 새 옵션](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="5f06a-264">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
