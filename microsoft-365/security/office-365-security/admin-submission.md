---
title: 관리자 제출
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 규정 준수 센터에서 제출 포털을 사용하여 의심스러운 전자 메일, 의심스러운 피싱 메일, 스팸 및 기타 잠재적으로 유해한 메시지, URL 및 파일을 검사하도록 Microsoft에 제출하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845969"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="96323-103">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="96323-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="96323-104">Exchange Online의 사서함이 있는 Microsoft 365 조직에서 관리자는 보안 & 준수 센터의 전송 포털을 사용하여 스캐시팅을 위해 Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="96323-105">전자 메일을 제출하면 테넌트로 받는 전자 메일을 허용한 정책과 메일의 URL 및 첨부 파일을 검사하는 방법에 대한 정보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="96323-106">메일이 허용될 수 있는 정책에는 개별 사용자의 수신 허용 - 보낸 사람 목록 및 테넌트 수준 정책(예: Exchange 메일 흐름 규칙이라고도 함)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="96323-107">Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 전송하는 다른 방법은 [Microsoft에 보고 메시지 및 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="96323-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96323-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="96323-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="96323-109"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96323-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="96323-110">제출 페이지로 직접 **이동하려면** 을 <https://protection.office.com/reportsubmission> 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="96323-111">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="96323-112">메시지와 파일을 Microsoft에 제출하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="96323-113">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="96323-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="96323-114">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="96323-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="96323-115">제출 포털에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="96323-116">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="96323-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="96323-117">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="96323-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="96323-118">사용자가 Microsoft에 메시지와 파일을 제출하는 방법에 대한 자세한 내용은 Microsoft에 [보고 메시지 및 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="96323-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="96323-119">Microsoft에 의심스러운 콘텐츠 보고</span><span class="sxs-lookup"><span data-stu-id="96323-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="96323-120">보안 규정 준수 & 제출로 이동하여 **위협 관리** \> **Submissions**제출로 이동하고 관리자 제출 **탭에 있는지** 확인한 후 새 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="96323-121">다음 **섹션의** 설명에 따라 메시지, URL 또는 첨부 파일을 전송하는 데 나타나는 새 전송 플라이아웃을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="96323-122">Microsoft에 질문할 수 있는 메일 제출</span><span class="sxs-lookup"><span data-stu-id="96323-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="96323-123">Section in the **Object type** section, select **Email.**</span><span class="sxs-lookup"><span data-stu-id="96323-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="96323-124">전송 형식 **섹션에서 다음** 옵션 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="96323-125">**네트워크 메시지 ID**: 메시지의 **X-MS-Exchange-Organization-Network-Message-Id 헤더에서** 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="96323-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="96323-126">**파일:** 파일 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="96323-127">대화 상자가 열리면 .eml 또는 .msg 파일을 찾아서 선택한 후 열기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="96323-128">받는 **사람** 섹션에서 정책 확인을 실행될 받는 사람을 한 명 이상 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="96323-129">정책 검사에서는 사용자 또는 조직 정책으로 인해 이메일 검사를 무시하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="96323-130">제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="96323-131">**차단하지 않아요**</span><span class="sxs-lookup"><span data-stu-id="96323-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="96323-132">**스팸, 피싱**또는 **맬웨어** **선택을 차단해야** **합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="96323-133">부합하지 않을 경우 최상의 조각을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="96323-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="96323-134">전송 시 정책으로 인해 필터가 무시된 경우 해당 정책에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="96323-135">하나 이상의 정책으로 인해 필터가 무시되지 않은 경우 몇 분 내에 검사가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="96323-136">상태 링크를 클릭하여 제출에 대한 추가 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="96323-137">여기에는 정책 검사 결과와 재검사 결과가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="96323-138">이 작업은 Office 365 ATP 전체 필터링 스택을 통해 다시 실행되지는 않지만 메일, URL 또는 파일의 특정 특성에 따라 부분 재검사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="96323-139">작업을 마치면 제출 단추를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-139">When you're finished, click the **Submit** button.</span></span>

![URL 제출 예제](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="96323-141">Microsoft에 의심스러운 URL 보내기</span><span class="sxs-lookup"><span data-stu-id="96323-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="96323-142">Section in the **Object type** section, select **URL.**</span><span class="sxs-lookup"><span data-stu-id="96323-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="96323-143">나타나는 상자에 전체 URL(예: )을 <https://www.fabrikam.com/marketing.html> 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="96323-144">제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="96323-145">**차단하지 않아요**</span><span class="sxs-lookup"><span data-stu-id="96323-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="96323-146">**피싱 또는**맬웨어 **선택을 차단한** **Malware**것</span><span class="sxs-lookup"><span data-stu-id="96323-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="96323-147">작업을 마치면 제출 단추를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-147">When you're finished, click the **Submit** button.</span></span>

![전자 메일 전송 예제](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="96323-149">Microsoft에 의심스러운 파일 제출</span><span class="sxs-lookup"><span data-stu-id="96323-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="96323-150">In the **Object type section,** select **Attachment.**</span><span class="sxs-lookup"><span data-stu-id="96323-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="96323-151">파일 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-151">Click **Choose File**.</span></span> <span data-ttu-id="96323-152">열리는 대화 상자에서 파일을 찾아 서 선택한 다음 열기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="96323-153">제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="96323-154">**차단하지 않아요**</span><span class="sxs-lookup"><span data-stu-id="96323-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="96323-155">**즉, 맬웨어만** **선택할** 수 있는 옵션이며 자동으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="96323-156">작업을 마치면 제출 단추를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-156">When you're finished, click the **Submit** button.</span></span>

![첨부 파일 전송 예제](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="96323-158">관리자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="96323-158">View admin submissions</span></span>

<span data-ttu-id="96323-159">보안 규정 준수 & 제출로 이동하여 **위협 관리** \> **Submissions**제출로 이동하고 관리자 제출 **탭에 있는지** 확인한 후 새 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="96323-160">페이지 위쪽에 있는 시작 날짜 및 종료 날짜를 입력할 수 있습니다. 기본적으로 제출 **ID(모든** 제출에 할당된 GUID 값)로 상자 상자에 값을 입력하고 새로 고침 단추를 ![ 클릭할 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="96323-161">Update</span><span class="sxs-lookup"><span data-stu-id="96323-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="96323-162">필터 조건을 변경하려면 제출 **ID 단추를** 클릭하고 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="96323-163">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="96323-163">**Sender**</span></span>
- <span data-ttu-id="96323-164">**제목/URL/파일 이름**</span><span class="sxs-lookup"><span data-stu-id="96323-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="96323-165">**제출자**</span><span class="sxs-lookup"><span data-stu-id="96323-165">**Submitted by**</span></span>
- <span data-ttu-id="96323-166">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="96323-166">**Submission type**</span></span>
- <span data-ttu-id="96323-167">**상태**</span><span class="sxs-lookup"><span data-stu-id="96323-167">**Status**</span></span>

![관리자 제출 옵션 필터링](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="96323-169">결과를 내보내려면 **페이지 위쪽에서** 내보내기를 클릭하고 차트 데이터 **또는 테이블을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="96323-170">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="96323-171">그래프 아래에 전자 메일(기본값), **URL,** 첨부 파일 **등** 세 개의 탭이 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="96323-172">관리자 전자 메일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="96323-172">View admin email submissions</span></span>

<span data-ttu-id="96323-173">Click the **Email** tab.</span><span class="sxs-lookup"><span data-stu-id="96323-173">Click the **Email** tab.</span></span>

<span data-ttu-id="96323-174">페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="96323-175">**날짜**</span><span class="sxs-lookup"><span data-stu-id="96323-175">**Date**</span></span>
- <span data-ttu-id="96323-176">**제출 ID:** 모든 제출에 할당된 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="96323-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="96323-177">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-178">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-179">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="96323-179">**Sender**</span></span>
- <span data-ttu-id="96323-180">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-181">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="96323-181">**Submission type**</span></span>
- <span data-ttu-id="96323-182">**배달 이유**</span><span class="sxs-lookup"><span data-stu-id="96323-182">**Delivery reason**</span></span>
- <span data-ttu-id="96323-183">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-184">**컨트롤 형식**</span><span class="sxs-lookup"><span data-stu-id="96323-184">**Control type**</span></span>
- <span data-ttu-id="96323-185">**제어 원본**</span><span class="sxs-lookup"><span data-stu-id="96323-185">**Control source**</span></span>

  <span data-ttu-id="96323-186"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="96323-187">관리 URL 제출 보기</span><span class="sxs-lookup"><span data-stu-id="96323-187">View admin URL submissions</span></span>

<span data-ttu-id="96323-188">URL 탭을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-188">Click the **URL** tab.</span></span>

<span data-ttu-id="96323-189">페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="96323-190">**날짜**</span><span class="sxs-lookup"><span data-stu-id="96323-190">**Date**</span></span>
- <span data-ttu-id="96323-191">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="96323-191">**Submission ID**</span></span>
- <span data-ttu-id="96323-192">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-194">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="96323-194">**Submission type**</span></span>
- <span data-ttu-id="96323-195">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="96323-196"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="96323-197">관리자 첨부 파일 제출 보기</span><span class="sxs-lookup"><span data-stu-id="96323-197">View admin attachment submissions</span></span>

<span data-ttu-id="96323-198">첨부 파일 **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="96323-199">페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="96323-200">**날짜**</span><span class="sxs-lookup"><span data-stu-id="96323-200">**Date**</span></span>
- <span data-ttu-id="96323-201">**제출 ID**</span><span class="sxs-lookup"><span data-stu-id="96323-201">**Submission ID**</span></span>
- <span data-ttu-id="96323-202">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-203">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-204">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="96323-204">**Submission type**</span></span>
- <span data-ttu-id="96323-205">**상태**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="96323-206"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="96323-207">Microsoft에 대한 사용자 제출 보기</span><span class="sxs-lookup"><span data-stu-id="96323-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="96323-208">보고서 메시지 추가 기능을 [배포하거나](enable-the-report-message-add-in.md)사용자가 웹용 [Outlook의 기본 제공 보고를 사용하는](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)경우 사용자 제출 탭에서 보고 **내용을 확인할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="96323-209">보안 센터에서 & 위협 관리 **제출로** \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="96323-210">사용자 제출 **탭을 선택한** 다음 새 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="96323-211">페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="96323-212">**제출됨**</span><span class="sxs-lookup"><span data-stu-id="96323-212">**Submitted on**</span></span>
- <span data-ttu-id="96323-213">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-214">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-215">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="96323-215">**Sender**</span></span>
- <span data-ttu-id="96323-216">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-217">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="96323-217">**Submission type**</span></span>

<span data-ttu-id="96323-218"><sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96323-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="96323-219">페이지 위쪽에 시작 날짜, 종료 날짜 및 기본값으로)을 입력할 수 있습니다. 상자에 값을 **입력하고** 새로 고침 단추를 클릭하여 보낸 사람을 ![ 필터링할 수 ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="96323-220">Update</span><span class="sxs-lookup"><span data-stu-id="96323-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="96323-221">필터 조건을 변경하려면 보낸 사람 **단추를 클릭하고** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="96323-222">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="96323-222">**Sender domain**</span></span>
- <span data-ttu-id="96323-223">**제목**</span><span class="sxs-lookup"><span data-stu-id="96323-223">**Subject**</span></span>
- <span data-ttu-id="96323-224">**제출자**</span><span class="sxs-lookup"><span data-stu-id="96323-224">**Submitted by**</span></span>
- <span data-ttu-id="96323-225">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="96323-225">**Submission type**</span></span>
- <span data-ttu-id="96323-226">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="96323-226">**Sender IP**</span></span>

![사용자 전송을 위한 옵션 필터링](../../media/user-submissions-filter-options.png)

<span data-ttu-id="96323-228">결과를 내보내려면 **페이지 위쪽에서** 내보내기를 클릭하고 차트 데이터 **또는 테이블을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="96323-229">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="96323-230">사용자 지정 사서함에 대한 사용자 전송 보기</span><span class="sxs-lookup"><span data-stu-id="96323-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="96323-231">사용자 보고된 [메시지를 받도록 사용자 지정](user-submission.md) 사서함을 구성한 경우에는 보고 사서함에 배달된 메시지를 보고 도용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="96323-232">보안 센터에서 & 위협 관리 **제출로** \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="96323-233">사용자 지정 **사서함 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="96323-234">페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="96323-235">**제출됨**</span><span class="sxs-lookup"><span data-stu-id="96323-235">**Submitted on**</span></span>
- <span data-ttu-id="96323-236">**제출자**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-237">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-238">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="96323-238">**Sender**</span></span>
- <span data-ttu-id="96323-239">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="96323-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="96323-240">**제출 유형**</span><span class="sxs-lookup"><span data-stu-id="96323-240">**Submission type**</span></span>

<span data-ttu-id="96323-241">페이지 위쪽에 있는 시작 날짜와 종료 날짜를 입력할 수 **Submitted by** ![ ](../../media/scc-quarantine-refresh.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="96323-242">Update</span><span class="sxs-lookup"><span data-stu-id="96323-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="96323-243">결과를 내보내려면 **페이지 위쪽에서** 내보내기를 클릭하고 차트 데이터 **또는 테이블을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="96323-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="96323-244">나타나는 대화 상자에서 .csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="96323-245">사용자 지정 사서함에서 Microsoft에 메시지 제출</span><span class="sxs-lookup"><span data-stu-id="96323-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="96323-246">Microsoft로 메시지를 보내지 않고 사용자가 보고한 메시지를 가로저할 수 있도록 사용자 지정 사서함을 구성한 경우, 분석을 위해 Microsoft에 특정 메시지를 검색하여 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96323-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="96323-247">사용자 제출을 관리자 제출로 효과적으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="96323-248">사용자 **지정 사서함** 탭의 목록에서 메시지를 선택한 후 **동작 단추를** 클릭하고 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96323-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="96323-249">**보고서 정리**</span><span class="sxs-lookup"><span data-stu-id="96323-249">**Report clean**</span></span>
- <span data-ttu-id="96323-250">**보고서 피싱**</span><span class="sxs-lookup"><span data-stu-id="96323-250">**Report phishing**</span></span>
- <span data-ttu-id="96323-251">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="96323-251">**Report malware**</span></span>
- <span data-ttu-id="96323-252">**보고서 스팸 보고서**</span><span class="sxs-lookup"><span data-stu-id="96323-252">**Report spam**</span></span>

![동작 단추의 옵션](../../media/user-submission-custom-mailbox-action-button.png)
