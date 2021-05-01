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
description: 관리자는 보안 & 준수 센터의 제출 포털을 사용하여 의심스러운 전자 메일, 피싱 메일, 스팸 및 기타 유해한 메시지, URL 및 파일을 검색을 위해 Microsoft에 제출하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0b91808aa9008f467f66b8200f2c05a120fbcd9
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107233"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="3fdbb-103">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="3fdbb-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3fdbb-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-104">**Applies to**</span></span>
- [<span data-ttu-id="3fdbb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3fdbb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3fdbb-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="3fdbb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="3fdbb-107">Microsoft 365 사서함이 있는 Exchange Online 조직에서 관리자는 보안 & 준수 센터의 제출 포털을 사용하여 검색을 위해 전자 메일 메시지, URL 및 첨부 파일을 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="3fdbb-108">전자 메일 메시지를 제출하면 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="3fdbb-109">**전자 메일 인증 확인:** 전자 메일 인증이 전달될 때 통과 또는 실패한 경우의 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="3fdbb-110">**정책 적중:** 테넌트로 들어오는 전자 메일을 허용하거나 차단할 수 있는 정책에 대한 정보로, 서비스 필터 판정을 어버렸다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="3fdbb-111">**페이로드 신뢰도/확인:** 메시지의 URL 및 첨부 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="3fdbb-112">**성적 분석:** 휴먼 등급이 수행한 검토를 통해 메시지가 악성인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fdbb-113">페이로드 신뢰도/분석 및 등급 분석은 모든 테넌트에서 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="3fdbb-114">데이터가 규정 준수를 위해 테넌트 경계를 떠날 수 없는 경우 정보가 조직 외부로 나가지 못하도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="3fdbb-115">Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 제출하는 다른 방법은 Microsoft에 메시지 및 파일 보고를 [참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="3fdbb-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3fdbb-116">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="3fdbb-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3fdbb-117"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3fdbb-118">제출 페이지로 직접 **이동하기** 위해 를 <https://protection.office.com/reportsubmission> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="3fdbb-119">메시지와 파일을 Microsoft에 제출하려면 다음 역할 그룹 중 하나의 구성원이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="3fdbb-120">**보안** 및 **준수** 센터의 [조직 관리 & 보안 읽기](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="3fdbb-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="3fdbb-121">**에서 조직** [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="3fdbb-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="3fdbb-122">이 역할 그룹의 구성원 자격은 [](#view-user-submissions-to-the-custom-mailbox) 이 문서의 부분에서 설명하는 사용자 지정 사서함에 대한 사용자 전송 보기에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="3fdbb-123">사용자가 Microsoft에 메시지와 파일을 제출하는 방법에 대한 자세한 내용은 Microsoft에 메시지 및 파일 [보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="3fdbb-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="3fdbb-124">Microsoft에 의심스러운 콘텐츠 보고</span><span class="sxs-lookup"><span data-stu-id="3fdbb-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="3fdbb-125">보안 & 준수 센터에서 위협 관리  제출로 이동하여 관리 제출 탭에 있는지 확인한 다음 \> 새 제출 **을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="3fdbb-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="3fdbb-126">다음 **섹션에** 설명된 메시지, URL 또는 첨부 파일을 제출하는 것으로 나타나는 새 제출 플라이아웃을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="3fdbb-127">Microsoft에 질문이 있는 전자 메일 제출</span><span class="sxs-lookup"><span data-stu-id="3fdbb-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="3fdbb-128">개체 **유형 섹션에서** 전자 메일을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="3fdbb-129">제출 **형식 섹션에서** 다음 옵션 중 하나를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="3fdbb-130">네트워크 메시지 **ID:** 이 값은 메시지의 **X-MS-Exchange-Organization-Network-Message-Id** 헤더 또는 **X-MS-Office365-Filtering-Correlation-Id** 헤더에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="3fdbb-131">**파일**: 파일 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="3fdbb-132">대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3fdbb-133">30일이 지난 메시지를 전송하는 능력은 모든 고객에 대해 Defender에 대해 Office 365 일시적으로 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="3fdbb-134">관리자는 7일만 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="3fdbb-135">받는 **사람 섹션에서** 정책 검사를 실행할 받는 사람을 한명 이상 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="3fdbb-136">정책 검사는 사용자 또는 조직 정책으로 인해 전자 메일이 검사를 무시한지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="3fdbb-137">제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3fdbb-138">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3fdbb-139">**차단된 경우:** **스팸,** **피싱** 또는 맬웨어를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="3fdbb-140">확실하지 않은 경우 최상의 판단을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="3fdbb-141">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-141">When you're finished, click the **Submit** button.</span></span>

   ![새 URL 제출 예제](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="3fdbb-143">의심되는 URL을 Microsoft로 보내기</span><span class="sxs-lookup"><span data-stu-id="3fdbb-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="3fdbb-144">개체 **유형 섹션에서** **URL 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="3fdbb-145">나타나는 상자에 전체 URL(예: )을 `https://www.fabrikam.com/marketing.html` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="3fdbb-146">제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3fdbb-147">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3fdbb-148">**차단된 경우**: **피싱** 또는 맬웨어를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="3fdbb-149">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-149">When you're finished, click the **Submit** button.</span></span>

   ![새 전자 메일 제출 예제](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="3fdbb-151">의심되는 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="3fdbb-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="3fdbb-152">개체 **유형 섹션에서** 첨부 파일을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="3fdbb-153">파일 **선택 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-153">Click **Choose File**.</span></span> <span data-ttu-id="3fdbb-154">대화 상자가 열리면 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="3fdbb-155">제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3fdbb-156">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3fdbb-157">**차단된 경우:** **맬웨어만** 선택할 수 있으며 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="3fdbb-158">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-158">When you're finished, click the **Submit** button.</span></span>

   ![새 첨부 파일 제출 예제](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="3fdbb-160">분석을 위해 제출된 항목 보기</span><span class="sxs-lookup"><span data-stu-id="3fdbb-160">View items Submitted for analysis</span></span>

<span data-ttu-id="3fdbb-161">보안 & 준수 센터에서 위협 관리  제출로 이동하여 분석을 위해 제출된 탭에 \> 있는지 확인 </span><span class="sxs-lookup"><span data-stu-id="3fdbb-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="3fdbb-162">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며(기본적으로) 상자에 값을 입력하고 새로 고침 단추 를 클릭하여 제출 **ID(모든** 제출에 할당된 GUID 값)를 필터링할 수 ![ ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3fdbb-163">Update</span><span class="sxs-lookup"><span data-stu-id="3fdbb-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3fdbb-164">필터 조건을 변경하려면 제출 ID 단추를 **클릭하고** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="3fdbb-165">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-165">**Sender**</span></span>
- <span data-ttu-id="3fdbb-166">**주체/URL/파일 이름**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="3fdbb-167">**제출한 인원**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-167">**Submitted by**</span></span>
- <span data-ttu-id="3fdbb-168">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-168">**Submission type**</span></span>
- <span data-ttu-id="3fdbb-169">**상태**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-169">**Status**</span></span>

![관리자 제출에 대한 새 필터 옵션](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="3fdbb-171">결과를 내보내려면 페이지 **위쪽에서** 내보내기 를 클릭하고 차트 데이터 또는 **테이블을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3fdbb-172">나타나는 대화 상자에서 파일 .csv 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="3fdbb-173">그래프 아래에는 전자 메일(기본값), URL 및 첨부 파일 3개의 **탭이** **있습니다.** </span><span class="sxs-lookup"><span data-stu-id="3fdbb-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="3fdbb-174">관리자 전자 메일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="3fdbb-174">View admin email submissions</span></span>

<span data-ttu-id="3fdbb-175">전자 메일 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-175">Click the **Email** tab.</span></span>

<span data-ttu-id="3fdbb-176">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3fdbb-177">**날짜**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-177">**Date**</span></span>
- <span data-ttu-id="3fdbb-178">**제출 ID:** 모든 제출에 할당된 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="3fdbb-179">**제출한 인원**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-180">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-181">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-181">**Sender**</span></span>
- <span data-ttu-id="3fdbb-182">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-183">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-183">**Submission type**</span></span>
- <span data-ttu-id="3fdbb-184">**배달 이유**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-184">**Delivery reason**</span></span>
- <span data-ttu-id="3fdbb-185">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3fdbb-186"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="3fdbb-187">관리자 제출 세부 정보 다시 검색</span><span class="sxs-lookup"><span data-stu-id="3fdbb-187">Admin submission rescan details</span></span>

<span data-ttu-id="3fdbb-188">관리자 제출에 제출된 메시지는 다시 검색된 후 세부 정보 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="3fdbb-189">전송 시 보낸 사람의 전자 메일 인증에 오류가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="3fdbb-190">메시지의 평가 결과에 영향을 주거나 재정의할 수 있는 정책 조회에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="3fdbb-191">메시지에 포함된 URL 또는 파일이 악의적인지 여부를 확인하는 현재 데토네이션 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="3fdbb-192">성적에 대한 피드백</span><span class="sxs-lookup"><span data-stu-id="3fdbb-192">Feedback from graders.</span></span>

<span data-ttu-id="3fdbb-193">재정의가 발견되면 몇 분 후에 다시 검색이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="3fdbb-194">전자 메일 인증에 문제가 없는 경우 또는 배달이 오버라이드의 영향을 받지 않은 경우 등급의 피드백이 하루까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="3fdbb-195">관리자 URL 제출 보기</span><span class="sxs-lookup"><span data-stu-id="3fdbb-195">View admin URL submissions</span></span>

<span data-ttu-id="3fdbb-196">URL **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-196">Click the **URL** tab.</span></span>

<span data-ttu-id="3fdbb-197">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3fdbb-198">**날짜**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-198">**Date**</span></span>
- <span data-ttu-id="3fdbb-199">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-199">**Submission ID**</span></span>
- <span data-ttu-id="3fdbb-200">**제출한 인원**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-202">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-202">**Submission type**</span></span>
- <span data-ttu-id="3fdbb-203">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3fdbb-204"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="3fdbb-205">관리자 첨부 파일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="3fdbb-205">View admin attachment submissions</span></span>

<span data-ttu-id="3fdbb-206">첨부 **파일 탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="3fdbb-207">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3fdbb-208">**날짜**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-208">**Date**</span></span>
- <span data-ttu-id="3fdbb-209">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-209">**Submission ID**</span></span>
- <span data-ttu-id="3fdbb-210">**제출한 인원**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-211">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-212">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-212">**Submission type**</span></span>
- <span data-ttu-id="3fdbb-213">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3fdbb-214"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="3fdbb-215">Microsoft에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="3fdbb-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="3fdbb-216">보고서 메시지 추가 [기능,](enable-the-report-message-add-in.md)피싱 보고 [](enable-the-report-phish-add-in.md)추가 기능을 배포한 경우 또는 사용자가 웹의 Outlook 기본 제공 보고를 사용하는 경우 [사용자](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)제출 탭에서 보고하는 사용자를 볼 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="3fdbb-217">보안 및 & 센터에서 위협 관리 **제출으로** \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3fdbb-218">사용자 **제출 탭을** 선택한 다음 새 제출 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3fdbb-219">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3fdbb-220">**제출 시**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-220">**Submitted on**</span></span>
- <span data-ttu-id="3fdbb-221">**제출한 인원**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-222">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-223">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-223">**Sender**</span></span>
- <span data-ttu-id="3fdbb-224">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-225">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-225">**Submission type**</span></span>

<span data-ttu-id="3fdbb-226"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="3fdbb-227">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며 기본적으로 상자에  값을 입력하고 새로 고침 단추 를 클릭하여 보낸 사람에 의해 필터링할 ![ 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3fdbb-228">Update</span><span class="sxs-lookup"><span data-stu-id="3fdbb-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3fdbb-229">필터 조건을 변경하려면 보낸  사람 단추를 클릭하고 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="3fdbb-230">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-230">**Sender domain**</span></span>
- <span data-ttu-id="3fdbb-231">**제목**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-231">**Subject**</span></span>
- <span data-ttu-id="3fdbb-232">**제출한 인원**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-232">**Submitted by**</span></span>
- <span data-ttu-id="3fdbb-233">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-233">**Submission type**</span></span>
- <span data-ttu-id="3fdbb-234">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-234">**Sender IP**</span></span>

![사용자 제출에 대한 새 필터 옵션](../../media/user-submissions-filter-options.png)

<span data-ttu-id="3fdbb-236">결과를 내보내려면 페이지 **위쪽에서** 내보내기 를 클릭하고 차트 데이터 또는 **테이블을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3fdbb-237">나타나는 대화 상자에서 파일 .csv 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="3fdbb-238">사용자 지정 사서함에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="3fdbb-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="3fdbb-239">**사용자가** 보고한 [](user-submission.md) 메시지를 받도록 사용자 지정 사서함을 구성한 경우 보고 사서함으로 배달된 메시지를 보고하고 전송할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="3fdbb-240">보안 및 & 센터에서 위협 관리 **제출으로** \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3fdbb-241">사용자 **지정 사서함 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="3fdbb-242">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3fdbb-243">**제출 시**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-243">**Submitted on**</span></span>
- <span data-ttu-id="3fdbb-244">**제출한 인원**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-245">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-246">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-246">**Sender**</span></span>
- <span data-ttu-id="3fdbb-247">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fdbb-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3fdbb-248">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-248">**Submission type**</span></span>

<span data-ttu-id="3fdbb-249">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며 상자에 값을 입력하고 새로 고침 단추 를 클릭하여 **제출로** ![ 필터링할 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3fdbb-250">Update</span><span class="sxs-lookup"><span data-stu-id="3fdbb-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3fdbb-251">결과를 내보내려면 페이지 **위쪽에서** 내보내기 를 클릭하고 차트 데이터 또는 **테이블을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3fdbb-252">나타나는 대화 상자에서 파일 .csv 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="3fdbb-253">조직이 사용자 지정 사서함으로만 보내도록 구성된 경우 보고된 메시지는 다시 검색을 위해 전송되지 않습니다. 사용자 보고 메시지 포털의 결과는 항상 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="3fdbb-254">사용자 제출 취소</span><span class="sxs-lookup"><span data-stu-id="3fdbb-254">Undo user submissions</span></span>

<span data-ttu-id="3fdbb-255">사용자가 의심스러운 전자 메일을 사용자 지정 사서함에 제출하면 사용자와 관리자는 제출을 취소할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="3fdbb-256">사용자가 전자 메일을 복구하려면 지우기 항목 또는 정크 메일 폴더에서 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="3fdbb-257">사용자 지정 사서함에서 Microsoft로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="3fdbb-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="3fdbb-258">Microsoft로 메시지를 보내지 않고 사용자가 보고한 메시지를 가로채도록 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아 Microsoft로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="3fdbb-259">그러면 사용자 제출이 관리자 제출로 효과적으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="3fdbb-260">사용자가 **보고한 메시지** 탭의 목록에서 메시지를 선택하고  작업 단추를 클릭한 후 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdbb-260">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="3fdbb-261">**정리 보고**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-261">**Report clean**</span></span>
- <span data-ttu-id="3fdbb-262">**피싱 보고**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-262">**Report phishing**</span></span>
- <span data-ttu-id="3fdbb-263">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-263">**Report malware**</span></span>
- <span data-ttu-id="3fdbb-264">**스팸 보고**</span><span class="sxs-lookup"><span data-stu-id="3fdbb-264">**Report spam**</span></span>

![동작 단추의 새 옵션](../../media/user-submission-custom-mailbox-action-button.png)
