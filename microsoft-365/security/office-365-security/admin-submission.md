---
title: 관리자 제출
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터의 제출 포털을 사용하여 의심스러운 전자 메일, 의심스러운 피싱 메일, 스팸 및 기타 유해한 메시지, URL 및 파일을 검사하기 위해 Microsoft에 제출하는 방법을 배울 수 있습니다. &
ms.openlocfilehash: 7327768780e5db16e09e2b709c9c11344573c404
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659828"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="98730-103">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="98730-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="98730-104">Exchange Online에 사서함이 있는 Microsoft 365 조직에서 관리자는 보안 및 준수 센터의 제출 포털을 & 전자 메일 메시지, URL 및 첨부 파일을 검사하기 위해 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="98730-105">전자 메일을 제출하면 테넌트로 들어오는 전자 메일을 허용할 수 있는 모든 정책에 대한 정보와 메일의 URL 및 첨부 파일을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="98730-106">메일을 허용할 수 있는 정책에는 개별 사용자의 수신 허용 - 보낸 사람 목록과 Exchange 메일 흐름 규칙(전송 규칙라고도 알려지기)의 테넌트 수준 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="98730-107">Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 제출하는 다른 방법은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="98730-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="98730-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="98730-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="98730-109"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98730-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="98730-110">제출 페이지로 직접 **이동하기** 위해 <https://protection.office.com/reportsubmission> 다음을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="98730-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="98730-111">메시지와 파일을 Microsoft에 제출하려면 다음 역할 그룹 중 하나에 구성원이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="98730-112">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="98730-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="98730-113"> [Exchange Online의 조직 관리.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="98730-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="98730-114">이 역할 그룹의 구성원 자격은 [](#view-user-submissions-to-the-custom-mailbox) 이 문서의 부분에서 설명하는 사용자 지정 사서함으로의 사용자 제출을 보는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="98730-115">사용자가 Microsoft에 메시지와 파일을 제출하는 방법에 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="98730-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="98730-116">Microsoft에 의심스러운 콘텐츠 보고</span><span class="sxs-lookup"><span data-stu-id="98730-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="98730-117">보안 & 준수 센터에서 **위협** 관리 제출으로 이동하여 관리자 제출 탭에 있는지 확인한 다음 새 제출을 \>  **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="98730-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="98730-118">다음 **섹션에** 설명된 메시지, URL 또는 첨부 파일을 제출하는 것으로 나타나는 새 제출 플라이아웃을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="98730-119">Microsoft에 질문이 있는 전자 메일 제출</span><span class="sxs-lookup"><span data-stu-id="98730-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="98730-120">개체 유형 **섹션에서** 전자 메일을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="98730-121">제출 형식 **섹션에서** 다음 옵션 중 하나를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="98730-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="98730-122">네트워크 메시지 **ID:** 메시지의 **X-MS-Exchange-Organization-Network-Message-Id** 헤더 또는 **X-MS-Office365-Filtering-Correlation-Id** 헤더에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98730-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="98730-123">**파일**: 파일 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="98730-124">대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="98730-125">Office 365 계획 1 또는 계획 2에 대한 Defender를 가진 관리자는 30일 이전의 메시지를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="98730-126">다른 관리자는 7일만 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="98730-127">받는 사람 **섹션에서** 정책 검사를 실행할 받는 사람을 하나 이상 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="98730-128">정책 검사는 사용자 또는 조직 정책으로 인해 전자 메일이 검사를 무시한지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="98730-129">제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="98730-130">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="98730-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="98730-131">**차단된 경우**: **스팸,** 피싱 또는 맬웨어를 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="98730-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="98730-132">확실하지 않은 경우 최상의 판단을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="98730-133">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-133">When you're finished, click the **Submit** button.</span></span>

![URL 제출 예제](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="98730-135">의심되는 URL을 Microsoft로 보내기</span><span class="sxs-lookup"><span data-stu-id="98730-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="98730-136">개체 유형 **섹션에서** **URL을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="98730-137">상자가 나타나면 전체 URL(예: )을 `https://www.fabrikam.com/marketing.html` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="98730-138">제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="98730-139">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="98730-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="98730-140">**차단된 경우**: **피싱** 또는 맬웨어를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="98730-141">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-141">When you're finished, click the **Submit** button.</span></span>

![전자 메일 제출 예제](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="98730-143">의심되는 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="98730-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="98730-144">개체 유형 **섹션에서** 첨부 파일을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="98730-145">파일 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-145">Click **Choose File**.</span></span> <span data-ttu-id="98730-146">대화 상자가 열리면 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="98730-147">제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="98730-148">**차단되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="98730-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="98730-149">**차단된 경우:**  맬웨어만 선택할 수 있으며 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="98730-150">완료되면 제출 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-150">When you're finished, click the **Submit** button.</span></span>

![첨부 파일 제출 예제](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="98730-152">관리자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="98730-152">View admin submissions</span></span>

<span data-ttu-id="98730-153">보안 & 준수 센터에서 **위협** 관리 제출으로 이동하여 관리자 제출 탭에 있는지 확인한 다음 새 제출을 \>  **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="98730-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="98730-154">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며(기본적으로) 상자에 값을 입력하고 새로 고침 단추를 클릭하여 제출 **ID(모든** 제출에 할당된 GUID 값)를 필터링할 수 ![ ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="98730-155">Update</span><span class="sxs-lookup"><span data-stu-id="98730-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="98730-156">필터 조건을 변경하려면 제출 **ID** 단추를 클릭하고 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="98730-157">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98730-157">**Sender**</span></span>
- <span data-ttu-id="98730-158">**주체/URL/파일 이름**</span><span class="sxs-lookup"><span data-stu-id="98730-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="98730-159">**제출자**</span><span class="sxs-lookup"><span data-stu-id="98730-159">**Submitted by**</span></span>
- <span data-ttu-id="98730-160">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="98730-160">**Submission type**</span></span>
- <span data-ttu-id="98730-161">**상태**</span><span class="sxs-lookup"><span data-stu-id="98730-161">**Status**</span></span>

![관리자 제출에 대한 필터 옵션](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="98730-163">결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="98730-164">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="98730-165">그래프 아래에는 전자 메일(기본값), URL 및 첨부 파일 등 세 개의 **탭이** **있습니다.** </span><span class="sxs-lookup"><span data-stu-id="98730-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="98730-166">관리자 전자 메일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="98730-166">View admin email submissions</span></span>

<span data-ttu-id="98730-167">전자 메일 **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-167">Click the **Email** tab.</span></span>

<span data-ttu-id="98730-168">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="98730-169">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98730-169">**Date**</span></span>
- <span data-ttu-id="98730-170">**제출 ID:** 모든 제출에 할당된 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98730-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="98730-171">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-172">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-173">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98730-173">**Sender**</span></span>
- <span data-ttu-id="98730-174">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-175">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="98730-175">**Submission type**</span></span>
- <span data-ttu-id="98730-176">**배달 이유**</span><span class="sxs-lookup"><span data-stu-id="98730-176">**Delivery reason**</span></span>
- <span data-ttu-id="98730-177">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="98730-178"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="98730-179">관리자 제출 세부 정보 다시 검색</span><span class="sxs-lookup"><span data-stu-id="98730-179">Admin submission rescan details</span></span>

<span data-ttu-id="98730-180">관리자 제출에 제출된 메시지는 다시 검색된 후 세부 정보 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="98730-181">배달 시 보낸 사람 전자 메일 인증에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="98730-182">메시지의 판정에 영향을 주거나 의리가 있을 수 있는 정책 적중에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="98730-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="98730-183">메시지에 포함된 URL 또는 파일이 악의적이지 않은지의 현재 확인 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="98730-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="98730-184">학년으로부터의 피드백.</span><span class="sxs-lookup"><span data-stu-id="98730-184">Feedback from graders.</span></span>

<span data-ttu-id="98730-185">다시 검색된 재지정은 몇 분 후 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="98730-186">전자 메일 인증에 문제가 없는 경우 또는 배달에 대한 오버라이드의 영향을 받지 않은 경우 학년의 피드백이 하루가 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="98730-187">관리자 URL 제출 보기</span><span class="sxs-lookup"><span data-stu-id="98730-187">View admin URL submissions</span></span>

<span data-ttu-id="98730-188">URL **탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-188">Click the **URL** tab.</span></span>

<span data-ttu-id="98730-189">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="98730-190">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98730-190">**Date**</span></span>
- <span data-ttu-id="98730-191">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="98730-191">**Submission ID**</span></span>
- <span data-ttu-id="98730-192">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-194">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="98730-194">**Submission type**</span></span>
- <span data-ttu-id="98730-195">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="98730-196"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="98730-197">관리자 첨부 파일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="98730-197">View admin attachment submissions</span></span>

<span data-ttu-id="98730-198">첨부 **파일 탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="98730-199">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="98730-200">**날짜**</span><span class="sxs-lookup"><span data-stu-id="98730-200">**Date**</span></span>
- <span data-ttu-id="98730-201">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="98730-201">**Submission ID**</span></span>
- <span data-ttu-id="98730-202">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-203">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-204">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="98730-204">**Submission type**</span></span>
- <span data-ttu-id="98730-205">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="98730-206"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="98730-207">Microsoft에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="98730-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="98730-208">보고서 메시지 추가 기능을 [](enable-the-report-message-add-in.md)배포하거나 사용자가 웹용 [Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)기본 제공 보고를 사용하는 경우 사용자 제출 탭에서 보고하는 사용자를 볼 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="98730-209">보안 및 & 센터에서 **위협** 관리 \> **제출로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="98730-210">사용자 제출 **탭을** 선택한 다음 새 **제출을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="98730-211">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="98730-212">**제출 시**</span><span class="sxs-lookup"><span data-stu-id="98730-212">**Submitted on**</span></span>
- <span data-ttu-id="98730-213">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-214">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-215">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98730-215">**Sender**</span></span>
- <span data-ttu-id="98730-216">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-217">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="98730-217">**Submission type**</span></span>

<span data-ttu-id="98730-218"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="98730-219">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며(기본적으로) 상자에  값을 입력하고 새로 고침 단추를 클릭하여 보낸 사람으로 필터링할 ![ 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="98730-220">Update</span><span class="sxs-lookup"><span data-stu-id="98730-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="98730-221">필터 조건을 변경하려면 보낸  사람 단추를 클릭하고 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="98730-222">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="98730-222">**Sender domain**</span></span>
- <span data-ttu-id="98730-223">**제목**</span><span class="sxs-lookup"><span data-stu-id="98730-223">**Subject**</span></span>
- <span data-ttu-id="98730-224">**제출자**</span><span class="sxs-lookup"><span data-stu-id="98730-224">**Submitted by**</span></span>
- <span data-ttu-id="98730-225">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="98730-225">**Submission type**</span></span>
- <span data-ttu-id="98730-226">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="98730-226">**Sender IP**</span></span>

![사용자 제출에 대한 필터 옵션](../../media/user-submissions-filter-options.png)

<span data-ttu-id="98730-228">결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="98730-229">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="98730-230">사용자 지정 사서함에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="98730-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="98730-231">**사용자가** 보고한 [](user-submission.md) 메시지를 받도록 사용자 지정 사서함을 구성한 경우 보고 사서함으로 배달된 메시지를 보고하고 전송할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="98730-232">보안 및 & 센터에서 **위협** 관리 \> **제출로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="98730-233">사용자 **지정 사서함 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="98730-234">페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="98730-235">**제출 시**</span><span class="sxs-lookup"><span data-stu-id="98730-235">**Submitted on**</span></span>
- <span data-ttu-id="98730-236">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-237">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-238">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="98730-238">**Sender**</span></span>
- <span data-ttu-id="98730-239">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="98730-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="98730-240">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="98730-240">**Submission type**</span></span>

<span data-ttu-id="98730-241">페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며 상자에 값을 입력하고 새로 고침 단추를 클릭하여 **제출로** 필터링할 ![ 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="98730-242">Update</span><span class="sxs-lookup"><span data-stu-id="98730-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="98730-243">결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="98730-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="98730-244">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="98730-245">사용자 제출 취소</span><span class="sxs-lookup"><span data-stu-id="98730-245">Undo user submissions</span></span>

<span data-ttu-id="98730-246">사용자가 의심스러운 전자 메일을 사용자 지정 사서함에 제출하면 사용자와 관리자는 제출을 취소할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="98730-247">사용자가 전자 메일을 복구하려면 지우기 항목 또는 정크 메일 폴더에서 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="98730-248">사용자 지정 사서함에서 Microsoft로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="98730-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="98730-249">Microsoft로 메시지를 보내지 않고 사용자가 보고한 메시지를 가로채도록 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아 Microsoft로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98730-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="98730-250">그러면 사용자 제출이 관리자 제출로 효과적으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="98730-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="98730-251">사용자 **지정 사서함 탭의** 목록에서 메시지를 선택하고  작업 단추를 클릭한 다음 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98730-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="98730-252">**정리 보고**</span><span class="sxs-lookup"><span data-stu-id="98730-252">**Report clean**</span></span>
- <span data-ttu-id="98730-253">**피싱 보고**</span><span class="sxs-lookup"><span data-stu-id="98730-253">**Report phishing**</span></span>
- <span data-ttu-id="98730-254">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="98730-254">**Report malware**</span></span>
- <span data-ttu-id="98730-255">**스팸 보고**</span><span class="sxs-lookup"><span data-stu-id="98730-255">**Report spam**</span></span>

![작업 단추의 옵션](../../media/user-submission-custom-mailbox-action-button.png)
