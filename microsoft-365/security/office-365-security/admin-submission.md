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
description: 관리자는 보안 및 준수 센터의 제출 포털을 사용하여 의심스러운 전자 메일, 의심스러운 피싱 메일, 스팸 및 기타 유해한 메시지, URL 및 파일을 검색을 위해 Microsoft에 제출하는 방법을 배울 수 있습니다. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029517"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="63c60-103">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="63c60-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="63c60-104">Exchange Online에 사서함이 있는 Microsoft 365 조직에서 관리자는 보안 및 준수 센터의 제출 포털을 & 전자 메일 메시지, URL 및 첨부 파일을 검사하기 위해 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="63c60-105">전자 메일 메시지를 제출하면 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="63c60-106">**전자 메일 인증 확인**: 전자 메일 인증이 전달될 때 통과 또는 실패한 경우의 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="63c60-107">**정책 적중:** 테넌트로 들어오는 전자 메일을 허용하거나 차단할 수 있는 모든 정책에 대한 정보로, 서비스 필터 판정을 의회합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="63c60-108">**페이로드 신뢰도/확인:** 메시지의 URL 및 첨부 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="63c60-109">**등급 분석:** 메시지가 악성인지 여부를 확인하기 위해 휴먼 등급의 검토</span><span class="sxs-lookup"><span data-stu-id="63c60-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63c60-110">페이로드 신뢰도/분석 및 등급 분석은 모든 테넌트에서 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="63c60-111">데이터가 규정 준수를 위해 테넌트 경계를 떠날 수 없는 경우 정보가 조직 외부로 나가지 못하도록 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="63c60-112">Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 제출하는 다른 방법은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="63c60-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="63c60-113">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="63c60-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="63c60-114"><https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="63c60-115">제출 페이지로 직접 **이동하기** 위해 <https://protection.office.com/reportsubmission> 다음을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="63c60-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="63c60-116">메시지와 파일을 Microsoft에 제출하려면 다음 역할 그룹 중 하나의 구성원이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="63c60-117">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="63c60-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="63c60-118"> [Exchange Online의 조직 관리.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="63c60-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="63c60-119">이 역할 그룹의 구성원 자격은 [](#view-user-submissions-to-the-custom-mailbox) 이 문서의 부분에서 설명하는 사용자 지정 사서함으로의 사용자 제출을 보는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="63c60-120">사용자가 Microsoft에 메시지와 파일을 제출하는 방법에 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="63c60-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="63c60-121">Microsoft에 의심스러운 콘텐츠 보고</span><span class="sxs-lookup"><span data-stu-id="63c60-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="63c60-122">보안 & 준수 센터에서 **위협** 관리 제출으로 이동하여 관리자 제출 탭에 있는지 확인한 다음 새 제출을 \>  **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="63c60-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="63c60-123">다음 **섹션에** 설명된 메시지, URL 또는 첨부 파일을 제출하는 것으로 나타나는 새 제출 플라이아웃을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="63c60-124">Microsoft에 질문이 있는 전자 메일 제출</span><span class="sxs-lookup"><span data-stu-id="63c60-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="63c60-125">개체 유형 **섹션에서** 전자 메일을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="63c60-126">제출 형식 **섹션에서** 다음 옵션 중 하나를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="63c60-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="63c60-127">네트워크 메시지 **ID:** 메시지의 **X-MS-Exchange-Organization-Network-Message-Id** 헤더 또는 **X-MS-Office365-Filtering-Correlation-Id** 헤더에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="63c60-128">**파일**: 파일 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="63c60-129">대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="63c60-130">Office 365 요금제 1 또는 계획 2에 대한 Defender를 가진 관리자는 30일 이전의 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="63c60-131">다른 관리자는 7일만 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="63c60-132">받는 사람 **섹션에서** 정책 검사를 실행할 받는 사람을 하나 이상 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="63c60-133">정책 검사는 사용자 또는 조직 정책으로 인해 전자 메일이 검사를 무시한지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="63c60-134">제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="63c60-135">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="63c60-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="63c60-136">**차단된 경우**: **스팸,** 피싱 또는 맬웨어를 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="63c60-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="63c60-137">확실하지 않은 경우 최상의 판단을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="63c60-138">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-138">When you're finished, click the **Submit** button.</span></span>

   ![URL 제출 예제](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="63c60-140">의심되는 URL을 Microsoft로 보내기</span><span class="sxs-lookup"><span data-stu-id="63c60-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="63c60-141">개체 유형 **섹션에서** **URL을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="63c60-142">상자가 나타나면 전체 URL(예: )을 `https://www.fabrikam.com/marketing.html` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="63c60-143">제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="63c60-144">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="63c60-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="63c60-145">**차단된 경우**: **피싱** 또는 맬웨어를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="63c60-146">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-146">When you're finished, click the **Submit** button.</span></span>

   ![전자 메일 제출 예제](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="63c60-148">의심되는 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="63c60-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="63c60-149">개체 유형 **섹션에서** 첨부 파일을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="63c60-150">파일 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-150">Click **Choose File**.</span></span> <span data-ttu-id="63c60-151">대화 상자가 열리면 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="63c60-152">제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="63c60-153">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="63c60-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="63c60-154">**차단된 경우:**  맬웨어만 선택할 수 있으며 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="63c60-155">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-155">When you're finished, click the **Submit** button.</span></span>

   ![첨부 파일 제출 예제](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="63c60-157">관리자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="63c60-157">View admin submissions</span></span>

<span data-ttu-id="63c60-158">보안 & 준수 센터에서 **위협** 관리 제출으로 이동하여 관리자 제출 탭에 있는지 확인한 다음 새 제출을 \>  **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="63c60-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="63c60-159">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며(기본적으로) 상자에 값을 입력하고 새로 고침 단추를 클릭하여 제출 **ID(모든** 제출에 할당된 GUID 값)를 필터링할 수 ![ ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="63c60-160">Update</span><span class="sxs-lookup"><span data-stu-id="63c60-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="63c60-161">필터 조건을 변경하려면 제출 **ID** 단추를 클릭하고 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="63c60-162">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="63c60-162">**Sender**</span></span>
- <span data-ttu-id="63c60-163">**주체/URL/파일 이름**</span><span class="sxs-lookup"><span data-stu-id="63c60-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="63c60-164">**제출자**</span><span class="sxs-lookup"><span data-stu-id="63c60-164">**Submitted by**</span></span>
- <span data-ttu-id="63c60-165">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="63c60-165">**Submission type**</span></span>
- <span data-ttu-id="63c60-166">**상태**</span><span class="sxs-lookup"><span data-stu-id="63c60-166">**Status**</span></span>

![관리자 제출에 대한 필터 옵션](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="63c60-168">결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="63c60-169">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="63c60-170">그래프 아래에는 전자 메일(기본값), URL 및 첨부 파일 등 세 개의 **탭이** **있습니다.** </span><span class="sxs-lookup"><span data-stu-id="63c60-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="63c60-171">관리자 전자 메일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="63c60-171">View admin email submissions</span></span>

<span data-ttu-id="63c60-172">전자 메일 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-172">Click the **Email** tab.</span></span>

<span data-ttu-id="63c60-173">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="63c60-174">**날짜**</span><span class="sxs-lookup"><span data-stu-id="63c60-174">**Date**</span></span>
- <span data-ttu-id="63c60-175">**제출 ID:** 모든 제출에 할당된 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="63c60-176">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-177">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-178">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="63c60-178">**Sender**</span></span>
- <span data-ttu-id="63c60-179">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-180">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="63c60-180">**Submission type**</span></span>
- <span data-ttu-id="63c60-181">**배달 이유**</span><span class="sxs-lookup"><span data-stu-id="63c60-181">**Delivery reason**</span></span>
- <span data-ttu-id="63c60-182">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="63c60-183"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="63c60-184">관리자 제출 세부 정보 다시 검색</span><span class="sxs-lookup"><span data-stu-id="63c60-184">Admin submission rescan details</span></span>

<span data-ttu-id="63c60-185">관리자 제출에 제출된 메시지는 다시 검색된 후 세부 정보 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="63c60-186">배달 시 보낸 사람 전자 메일 인증에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="63c60-187">메시지의 판정에 영향을 주거나 은(는) 있을 수 있는 정책 적중에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="63c60-188">현재 검색 결과는 메시지에 포함된 URL 또는 파일이 악의적이지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="63c60-189">학년으로부터의 피드백.</span><span class="sxs-lookup"><span data-stu-id="63c60-189">Feedback from graders.</span></span>

<span data-ttu-id="63c60-190">다시 검색된 재지정은 몇 분 후 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="63c60-191">전자 메일 인증에 문제가 없는 경우 또는 배달에 대한 오버라이드의 영향을 받지 않은 경우 학년의 피드백이 하루가 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="63c60-192">관리자 URL 제출 보기</span><span class="sxs-lookup"><span data-stu-id="63c60-192">View admin URL submissions</span></span>

<span data-ttu-id="63c60-193">URL **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-193">Click the **URL** tab.</span></span>

<span data-ttu-id="63c60-194">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="63c60-195">**날짜**</span><span class="sxs-lookup"><span data-stu-id="63c60-195">**Date**</span></span>
- <span data-ttu-id="63c60-196">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="63c60-196">**Submission ID**</span></span>
- <span data-ttu-id="63c60-197">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-199">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="63c60-199">**Submission type**</span></span>
- <span data-ttu-id="63c60-200">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="63c60-201"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="63c60-202">관리자 첨부 파일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="63c60-202">View admin attachment submissions</span></span>

<span data-ttu-id="63c60-203">첨부 **파일 탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="63c60-204">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="63c60-205">**날짜**</span><span class="sxs-lookup"><span data-stu-id="63c60-205">**Date**</span></span>
- <span data-ttu-id="63c60-206">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="63c60-206">**Submission ID**</span></span>
- <span data-ttu-id="63c60-207">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-208">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-209">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="63c60-209">**Submission type**</span></span>
- <span data-ttu-id="63c60-210">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="63c60-211"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="63c60-212">Microsoft에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="63c60-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="63c60-213">보고서 메시지 추가 기능, 피싱 보고 [](enable-the-report-phish-add-in.md)추가 기능을 배포한 경우 또는 사용자가 웹용 [Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)기본 제공 보고를 사용하는 경우 사용자 제출  탭에서 보고하는 사용자를 볼 수 있습니다. [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="63c60-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="63c60-214">보안 및 & 센터에서 **위협** 관리 \> **제출로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="63c60-215">사용자 제출 **탭을** 선택한 다음 새 **제출을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="63c60-216">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="63c60-217">**제출 시**</span><span class="sxs-lookup"><span data-stu-id="63c60-217">**Submitted on**</span></span>
- <span data-ttu-id="63c60-218">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-219">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-220">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="63c60-220">**Sender**</span></span>
- <span data-ttu-id="63c60-221">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-222">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="63c60-222">**Submission type**</span></span>

<span data-ttu-id="63c60-223"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="63c60-224">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며(기본적으로) 상자에  값을 입력하고 새로 고침 단추를 클릭하여 보낸 사람으로 필터링할 ![ 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="63c60-225">Update</span><span class="sxs-lookup"><span data-stu-id="63c60-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="63c60-226">필터 조건을 변경하려면 보낸  사람 단추를 클릭하고 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="63c60-227">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="63c60-227">**Sender domain**</span></span>
- <span data-ttu-id="63c60-228">**제목**</span><span class="sxs-lookup"><span data-stu-id="63c60-228">**Subject**</span></span>
- <span data-ttu-id="63c60-229">**제출자**</span><span class="sxs-lookup"><span data-stu-id="63c60-229">**Submitted by**</span></span>
- <span data-ttu-id="63c60-230">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="63c60-230">**Submission type**</span></span>
- <span data-ttu-id="63c60-231">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="63c60-231">**Sender IP**</span></span>

![사용자 제출에 대한 필터 옵션](../../media/user-submissions-filter-options.png)

<span data-ttu-id="63c60-233">결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="63c60-234">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="63c60-235">사용자 지정 사서함에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="63c60-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="63c60-236">**사용자가** 보고한 [](user-submission.md) 메시지를 받도록 사용자 지정 사서함을 구성한 경우 보고 사서함으로 배달된 메시지를 보고하고 전송할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="63c60-237">보안 및 & 센터에서 **위협** 관리 \> **제출로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="63c60-238">사용자 **지정 사서함 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="63c60-239">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="63c60-240">**제출 시**</span><span class="sxs-lookup"><span data-stu-id="63c60-240">**Submitted on**</span></span>
- <span data-ttu-id="63c60-241">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-242">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-243">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="63c60-243">**Sender**</span></span>
- <span data-ttu-id="63c60-244">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="63c60-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="63c60-245">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="63c60-245">**Submission type**</span></span>

<span data-ttu-id="63c60-246">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며 상자에 값을 입력하고 새로 고침 단추를 클릭하여 **제출로** 필터링할 ![ 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="63c60-247">Update</span><span class="sxs-lookup"><span data-stu-id="63c60-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="63c60-248">결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="63c60-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="63c60-249">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="63c60-250">사용자 제출 취소</span><span class="sxs-lookup"><span data-stu-id="63c60-250">Undo user submissions</span></span>

<span data-ttu-id="63c60-251">사용자가 의심스러운 전자 메일을 사용자 지정 사서함에 제출하면 사용자와 관리자는 제출을 취소할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="63c60-252">사용자가 전자 메일을 복구하려면 지우기 항목 또는 정크 메일 폴더에서 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="63c60-253">사용자 지정 사서함에서 Microsoft로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="63c60-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="63c60-254">Microsoft로 메시지를 보내지 않고 사용자가 보고한 메시지를 가로채도록 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아 Microsoft로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="63c60-255">그러면 사용자 제출이 관리자 제출로 효과적으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="63c60-256">사용자 **지정 사서함 탭의** 목록에서 메시지를 선택하고  작업 단추를 클릭한 다음 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63c60-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="63c60-257">**정리 보고**</span><span class="sxs-lookup"><span data-stu-id="63c60-257">**Report clean**</span></span>
- <span data-ttu-id="63c60-258">**피싱 보고**</span><span class="sxs-lookup"><span data-stu-id="63c60-258">**Report phishing**</span></span>
- <span data-ttu-id="63c60-259">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="63c60-259">**Report malware**</span></span>
- <span data-ttu-id="63c60-260">**스팸 보고**</span><span class="sxs-lookup"><span data-stu-id="63c60-260">**Report spam**</span></span>

![작업 단추의 옵션](../../media/user-submission-custom-mailbox-action-button.png)
