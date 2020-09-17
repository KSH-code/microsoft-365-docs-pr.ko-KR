---
title: 관리자 전송
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
description: 관리자는 보안 & 준수 센터에서 전송 포털을 사용 하 여 의심 스러운 전자 메일, 의심 되는 피싱 메일, 스팸 및 기타 해로운 메시지, Url 및 파일을 검색을 위해 Microsoft에 제출 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: ef401f34bb0bc7a9a9718443101924ad09bca8a0
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947975"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="e5792-103">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="e5792-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="e5792-104">Exchange Online의 사서함이 있는 Microsoft 365 조 직에서는 관리자가 보안 & 준수 센터의 전송 포털을 사용 하 여 검색을 위해 전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="e5792-105">전자 메일을 제출 하면 메일에 포함 된 Url 및 첨부 파일을 검사 하는 것은 물론 수신 전자 메일을 허용 했을 수 있는 모든 정책에 대 한 정보를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="e5792-106">메일을 허용할 수 있는 정책에는 개별 사용자의 수신 허용-보낸 사람 목록 뿐 아니라 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)과 같은 테 넌 트 수준 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="e5792-107">전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 전송 하는 다른 방법에 대 한 자세한 내용은 [Report messages and files In microsoft](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5792-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e5792-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="e5792-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e5792-109"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e5792-110">**제출** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/reportsubmission> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="e5792-111">메시지 및 파일을 Microsoft에 전송 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="e5792-112">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="e5792-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="e5792-113">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**</span><span class="sxs-lookup"><span data-stu-id="e5792-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="e5792-114">이 항목의 뒷부분에 설명 된 대로 사용자 [지정 사서함에 대 한 사용자 제출을 확인](#view-user-submissions-to-the-custom-mailbox) 하려면이 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="e5792-115">사용자가 메시지 및 파일을 Microsoft에 전송 하는 방법에 대 한 자세한 내용은 [Report messages and files In microsoft를](report-junk-email-messages-to-microsoft.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5792-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="e5792-116">의심 스러운 콘텐츠를 Microsoft에 보고</span><span class="sxs-lookup"><span data-stu-id="e5792-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="e5792-117">보안 & 준수 센터에서 **위협 관리** \> **전송**으로 이동 하 여 **관리자의 제안** 탭에 있는지 확인 하 고 **새 제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="e5792-118">다음 섹션에 설명 된 대로 메시지, URL 또는 첨부 파일을 전송 하는 것 처럼 보이는 **새 전송** 플라이 아웃을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="e5792-119">Microsoft에 의심 스러운 전자 메일 제출</span><span class="sxs-lookup"><span data-stu-id="e5792-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="e5792-120">**개체 유형** 섹션에서 **전자 메일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="e5792-121">**전송 형식** 섹션에서 다음 옵션 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="e5792-122">**네트워크 메시지 id**: 메시지의 **X-Exchange-네트워크 메시지 ID** 헤더에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="e5792-123">**파일**: **파일 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="e5792-124">대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="e5792-125">**받는 사람** 섹션에서 정책을 확인 하기 위해 실행할 받는 사람을 한 명 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="e5792-126">정책 확인에서는 사용자 또는 조직 정책으로 인해 전자 메일에서 검색을 통과 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="e5792-127">**제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e5792-128">**차단 되지 않아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e5792-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e5792-129">**차단 됨**: **스팸**, **피싱**또는 **맬웨어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="e5792-130">확실히 모르겠으면 가장 좋은 판단을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5792-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="e5792-131">전송 시 정책으로 인해 필터가 생략 되 면 해당 정책에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="e5792-132">하나 이상의 정책으로 인해 필터가 무시 되지 않으면 몇 분 안에 검색이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="e5792-133">상태 링크를 클릭 하 여 전송에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="e5792-134">여기에는 정책 확인 및 다시 검사 결과의 결과가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="e5792-135">참고 Office 365 ATP 전체 필터링 스택을 통해 전자 메일을 다시 실행 하지만 메일, URL 또는 파일의 특정 특성에 따라 부분 다시 검사를 실행 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="e5792-136">작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-136">When you're finished, click the **Submit** button.</span></span>

![URL 전송 예](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="e5792-138">Microsoft에 의심 스러운 URL 보내기</span><span class="sxs-lookup"><span data-stu-id="e5792-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="e5792-139">**개체 유형** 섹션에서 **URL**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="e5792-140">상자가 나타나면 전체 URL (예:)을 입력 합니다 `https://www.fabrikam.com/marketing.html` .</span><span class="sxs-lookup"><span data-stu-id="e5792-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="e5792-141">**제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e5792-142">**차단 되지 않아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e5792-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e5792-143">**차단 되어야**하는 경우: **피싱** 또는 **맬웨어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="e5792-144">작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-144">When you're finished, click the **Submit** button.</span></span>

![전자 메일 전송 예](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="e5792-146">Microsoft에 의심 스러운 파일 제출</span><span class="sxs-lookup"><span data-stu-id="e5792-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="e5792-147">**개체 유형** 섹션에서 **첨부 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="e5792-148">**파일 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-148">Click **Choose File**.</span></span> <span data-ttu-id="e5792-149">대화 상자가 열리면 파일을 찾아 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="e5792-150">**제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e5792-151">**차단 되지 않아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e5792-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e5792-152">**차단 됨**: **맬웨어가** 유일한 선택 항목 이며 자동으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="e5792-153">작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-153">When you're finished, click the **Submit** button.</span></span>

![첨부 파일 전송 예](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="e5792-155">관리자 전송 보기</span><span class="sxs-lookup"><span data-stu-id="e5792-155">View admin submissions</span></span>

<span data-ttu-id="e5792-156">보안 & 준수 센터에서 **위협 관리** \> **전송**으로 이동 하 여 **관리자의 제안** 탭에 있는지 확인 하 고 **새 제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="e5792-157">페이지 맨 위에 있는 시작 날짜와 끝 날짜를 입력할 수 있으며, 기본적으로 상자에 값을 입력 하 고 새로 고침 단추를 클릭 하 여 **전송 ID** (모든 전송에 할당 된 GUID 값)를 기준으로 필터링 할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="e5792-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e5792-158">Update</span><span class="sxs-lookup"><span data-stu-id="e5792-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e5792-159">필터 조건을 변경 하려면 **제출 ID** 단추를 클릭 하 고 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="e5792-160">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="e5792-160">**Sender**</span></span>
- <span data-ttu-id="e5792-161">**제목/u i/파일 이름**</span><span class="sxs-lookup"><span data-stu-id="e5792-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="e5792-162">**제출한 사람**</span><span class="sxs-lookup"><span data-stu-id="e5792-162">**Submitted by**</span></span>
- <span data-ttu-id="e5792-163">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="e5792-163">**Submission type**</span></span>
- <span data-ttu-id="e5792-164">**상태**</span><span class="sxs-lookup"><span data-stu-id="e5792-164">**Status**</span></span>

![관리자 전송에 대 한 필터 옵션](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="e5792-166">결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e5792-167">대화 상자가 나타나면 .csv 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="e5792-168">그래프 아래에는 **전자 메일** (기본값), **URL**및 **첨부 파일**의 세 가지 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="e5792-169">관리자 전자 메일 전송 보기</span><span class="sxs-lookup"><span data-stu-id="e5792-169">View admin email submissions</span></span>

<span data-ttu-id="e5792-170">**전자 메일** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-170">Click the **Email** tab.</span></span>

<span data-ttu-id="e5792-171">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5792-172">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e5792-172">**Date**</span></span>
- <span data-ttu-id="e5792-173">**전송 ID**: 모든 전송에 할당 되는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="e5792-174">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-175">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-176">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="e5792-176">**Sender**</span></span>
- <span data-ttu-id="e5792-177">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-178">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="e5792-178">**Submission type**</span></span>
- <span data-ttu-id="e5792-179">**배달 이유**</span><span class="sxs-lookup"><span data-stu-id="e5792-179">**Delivery reason**</span></span>
- <span data-ttu-id="e5792-180">**상태별**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-181">**컨트롤 형식**</span><span class="sxs-lookup"><span data-stu-id="e5792-181">**Control type**</span></span>
- <span data-ttu-id="e5792-182">**컨트롤 원본**</span><span class="sxs-lookup"><span data-stu-id="e5792-182">**Control source**</span></span>

  <span data-ttu-id="e5792-183"><sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="e5792-184">관리자 URL 전송 보기</span><span class="sxs-lookup"><span data-stu-id="e5792-184">View admin URL submissions</span></span>

<span data-ttu-id="e5792-185">**URL** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-185">Click the **URL** tab.</span></span>

<span data-ttu-id="e5792-186">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5792-187">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e5792-187">**Date**</span></span>
- <span data-ttu-id="e5792-188">**전송 ID**</span><span class="sxs-lookup"><span data-stu-id="e5792-188">**Submission ID**</span></span>
- <span data-ttu-id="e5792-189">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-191">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="e5792-191">**Submission type**</span></span>
- <span data-ttu-id="e5792-192">**상태별**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e5792-193"><sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="e5792-194">관리자 첨부 파일 전송 보기</span><span class="sxs-lookup"><span data-stu-id="e5792-194">View admin attachment submissions</span></span>

<span data-ttu-id="e5792-195">**첨부 파일** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="e5792-196">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5792-197">**날짜**</span><span class="sxs-lookup"><span data-stu-id="e5792-197">**Date**</span></span>
- <span data-ttu-id="e5792-198">**전송 ID**</span><span class="sxs-lookup"><span data-stu-id="e5792-198">**Submission ID**</span></span>
- <span data-ttu-id="e5792-199">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-200">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-201">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="e5792-201">**Submission type**</span></span>
- <span data-ttu-id="e5792-202">**상태별**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e5792-203"><sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="e5792-204">Microsoft에 대 한 사용자 제출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="e5792-205">[보고서 메시지 추가 기능](enable-the-report-message-add-in.md)을 배포 했거나 사용자가 [웹에서 Outlook의 기본 제공 보고](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)를 사용 하는 경우 **사용자 전송** 탭에서 사용자에 게 보고 하는 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="e5792-206">보안 & 준수 센터에서 **위협 관리** \> **전송**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="e5792-207">**사용자 전송** 탭을 선택한 다음 **새 제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="e5792-208">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5792-209">**제출 된 날짜**</span><span class="sxs-lookup"><span data-stu-id="e5792-209">**Submitted on**</span></span>
- <span data-ttu-id="e5792-210">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-211">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-212">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="e5792-212">**Sender**</span></span>
- <span data-ttu-id="e5792-213">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-214">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="e5792-214">**Submission type**</span></span>

<span data-ttu-id="e5792-215"><sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="e5792-216">페이지 맨 위에 있는 시작 날짜와 끝 날짜를 입력할 수 있으며, 기본적으로 상자에 값을 입력 하 고 새로 고침 단추를 클릭 하 여 **보낸 사람** 을 기준으로 필터링 할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="e5792-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e5792-217">Update</span><span class="sxs-lookup"><span data-stu-id="e5792-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e5792-218">필터 조건을 변경 하려면 **보낸 사람** 단추를 클릭 하 고 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="e5792-219">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="e5792-219">**Sender domain**</span></span>
- <span data-ttu-id="e5792-220">**제목**</span><span class="sxs-lookup"><span data-stu-id="e5792-220">**Subject**</span></span>
- <span data-ttu-id="e5792-221">**제출한 사람**</span><span class="sxs-lookup"><span data-stu-id="e5792-221">**Submitted by**</span></span>
- <span data-ttu-id="e5792-222">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="e5792-222">**Submission type**</span></span>
- <span data-ttu-id="e5792-223">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="e5792-223">**Sender IP**</span></span>

![사용자 전송에 대 한 필터 옵션](../../media/user-submissions-filter-options.png)

<span data-ttu-id="e5792-225">결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e5792-226">대화 상자가 나타나면 .csv 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="e5792-227">사용자 지정 사서함에 대 한 사용자 전송 보기</span><span class="sxs-lookup"><span data-stu-id="e5792-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="e5792-228">사용자가 보고 한 메시지를 수신 하도록 [사용자 지정 사서함을 구성한](user-submission.md) **경우** 보고 사서함으로 배달 된 메시지를 확인 하 고 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="e5792-229">보안 & 준수 센터에서 **위협 관리** \> **전송**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="e5792-230">**사용자 지정 사서함** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="e5792-231">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5792-232">**제출 된 날짜**</span><span class="sxs-lookup"><span data-stu-id="e5792-232">**Submitted on**</span></span>
- <span data-ttu-id="e5792-233">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-234">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-235">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="e5792-235">**Sender**</span></span>
- <span data-ttu-id="e5792-236">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5792-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e5792-237">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="e5792-237">**Submission type**</span></span>

<span data-ttu-id="e5792-238">페이지 위쪽에 있는 시작 날짜, 종료 날짜를 입력 하 고 상자에 값을 입력 하 고 새로 고침 단추를 **클릭 하 여** 필터링 하 여 필터할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="e5792-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e5792-239">Update</span><span class="sxs-lookup"><span data-stu-id="e5792-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e5792-240">결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e5792-241">대화 상자가 나타나면 .csv 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="e5792-242">사용자 지정 사서함에서 Microsoft로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="e5792-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="e5792-243">Microsoft에 메시지를 보내지 않고 사용자가 보고 한 메시지를 가로채는 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아서 Microsoft로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="e5792-244">이렇게 하면 사용자 제출을 관리자 제출으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="e5792-245">**사용자 지정 사서함** 탭의 목록에서 메시지를 선택 하 고 **실행** 단추를 클릭 한 후 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5792-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="e5792-246">**보고서 정리**</span><span class="sxs-lookup"><span data-stu-id="e5792-246">**Report clean**</span></span>
- <span data-ttu-id="e5792-247">**신고 피싱**</span><span class="sxs-lookup"><span data-stu-id="e5792-247">**Report phishing**</span></span>
- <span data-ttu-id="e5792-248">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="e5792-248">**Report malware**</span></span>
- <span data-ttu-id="e5792-249">**스팸 보고**</span><span class="sxs-lookup"><span data-stu-id="e5792-249">**Report spam**</span></span>

![실행 단추 옵션](../../media/user-submission-custom-mailbox-action-button.png)
