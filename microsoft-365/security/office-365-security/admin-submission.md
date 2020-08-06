---
title: 관리자 전송
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터에서 전송 포털을 사용 하 여 의심 스러운 전자 메일, 의심 되는 피싱 메일, 스팸 및 기타 해로운 메시지, Url 및 파일을 검색을 위해 Microsoft에 제출 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577873"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="b3d1d-103">관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출</span><span class="sxs-lookup"><span data-stu-id="b3d1d-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="b3d1d-104">Exchange Online의 사서함이 있는 Microsoft 365 조 직에서는 관리자가 보안 & 준수 센터의 전송 포털을 사용 하 여 검색을 위해 전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="b3d1d-105">전자 메일을 제출 하면 메일에 포함 된 Url 및 첨부 파일을 검사 하는 것은 물론 수신 전자 메일을 허용 했을 수 있는 모든 정책에 대 한 정보를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="b3d1d-106">메일을 허용할 수 있는 정책에는 개별 사용자의 수신 허용-보낸 사람 목록 뿐 아니라 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)과 같은 테 넌 트 수준 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="b3d1d-107">전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 전송 하는 다른 방법에 대 한 자세한 내용은 [Report messages and files In microsoft](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b3d1d-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="b3d1d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b3d1d-109"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b3d1d-110">**제출** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/reportsubmission> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="b3d1d-111">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="b3d1d-112">메시지 및 파일을 Microsoft에 전송 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b3d1d-113">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b3d1d-114">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="b3d1d-115">서브 미션 포털에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b3d1d-116">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b3d1d-117">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="b3d1d-118">사용자가 메시지 및 파일을 Microsoft에 전송 하는 방법에 대 한 자세한 내용은 [Report messages and files In microsoft를](report-junk-email-messages-to-microsoft.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="b3d1d-119">의심 스러운 콘텐츠를 Microsoft에 보고</span><span class="sxs-lookup"><span data-stu-id="b3d1d-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="b3d1d-120">보안 & 준수 센터에서 **위협 관리** \> **검토** \> **관리자 전송 메시지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b3d1d-121">**제출** 페이지가 나타나면 **새로 제출** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="b3d1d-122">다음 섹션에 설명 된 대로 메시지, URL 또는 첨부 파일을 전송 하는 것 처럼 보이는 **새 전송** 플라이 아웃을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="b3d1d-123">Microsoft에 의심 스러운 전자 메일 제출</span><span class="sxs-lookup"><span data-stu-id="b3d1d-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="b3d1d-124">**개체 유형** 섹션에서 **전자 메일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="b3d1d-125">**전송 형식** 섹션에서 다음 옵션 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="b3d1d-126">**네트워크 메시지 id**: 메시지의 **X-Exchange-네트워크 메시지 ID** 헤더에서 사용할 수 있는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="b3d1d-127">**파일**: **파일 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="b3d1d-128">대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="b3d1d-129">**받는 사람** 섹션에서 정책을 확인 하기 위해 실행할 받는 사람을 한 명 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="b3d1d-130">정책 확인에서는 사용자 또는 조직 정책으로 인해 전자 메일에서 검색을 통과 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="b3d1d-131">**제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b3d1d-132">**차단 되지 않아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b3d1d-133">**차단 됨**: **스팸**, **피싱**또는 **맬웨어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="b3d1d-134">확실히 모르겠으면 가장 좋은 판단을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="b3d1d-135">전송 시 정책으로 인해 필터가 생략 되 면 해당 정책에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="b3d1d-136">하나 이상의 정책으로 인해 필터가 무시 되지 않으면 몇 분 안에 검색이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="b3d1d-137">상태 링크를 클릭 하 여 전송에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="b3d1d-138">여기에는 정책 확인 및 다시 검사 결과의 결과가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="b3d1d-139">참고 Office 365 ATP 전체 필터링 스택을 통해 전자 메일을 다시 실행 하지만 메일, URL 또는 파일의 특정 특성에 따라 부분 다시 검사를 실행 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="b3d1d-140">작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-140">When you're finished, click the **Submit** button.</span></span>

![URL 전송 예](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="b3d1d-142">Microsoft에 의심 스러운 URL 보내기</span><span class="sxs-lookup"><span data-stu-id="b3d1d-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="b3d1d-143">**개체 유형** 섹션에서 **URL**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="b3d1d-144">상자가 나타나면 전체 URL (예:)을 입력 합니다 <https://www.fabrikam.com/marketing.html> .</span><span class="sxs-lookup"><span data-stu-id="b3d1d-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="b3d1d-145">**제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b3d1d-146">**차단 되지 않아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b3d1d-147">**차단 되어야**하는 경우: **피싱** 또는 **맬웨어**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="b3d1d-148">작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-148">When you're finished, click the **Submit** button.</span></span>

![전자 메일 전송 예](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="b3d1d-150">Microsoft에 의심 스러운 파일 제출</span><span class="sxs-lookup"><span data-stu-id="b3d1d-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="b3d1d-151">**개체 유형** 섹션에서 **첨부 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="b3d1d-152">**파일 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-152">Click **Choose File**.</span></span> <span data-ttu-id="b3d1d-153">대화 상자가 열리면 파일을 찾아 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="b3d1d-154">**제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b3d1d-155">**차단 되지 않아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b3d1d-156">**차단 됨**: **맬웨어가** 유일한 선택 항목 이며 자동으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="b3d1d-157">작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-157">When you're finished, click the **Submit** button.</span></span>

![첨부 파일 전송 예](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="b3d1d-159">관리자 전송 보기</span><span class="sxs-lookup"><span data-stu-id="b3d1d-159">View admin submissions</span></span>

1. <span data-ttu-id="b3d1d-160">보안 & 준수 센터에서 **위협 관리** \> **검토** \> **관리자 전송 메시지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b3d1d-161">**제출** 페이지가 나타나면 **관리자 제출** 탭이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="b3d1d-162">페이지 맨 위에 있는 시작 날짜와 끝 날짜를 입력할 수 있으며, 기본적으로 상자에 값을 입력 하 고 새로 고침 단추를 클릭 하 여 **전송 ID** (모든 전송에 할당 된 GUID 값)를 기준으로 필터링 할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="b3d1d-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b3d1d-163">Update</span><span class="sxs-lookup"><span data-stu-id="b3d1d-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b3d1d-164">필터 조건을 변경 하려면 **제출 ID** 단추를 클릭 하 고 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="b3d1d-165">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-165">**Sender**</span></span>
- <span data-ttu-id="b3d1d-166">**제목/u i/파일 이름**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="b3d1d-167">**제출한 사람**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-167">**Submitted by**</span></span>
- <span data-ttu-id="b3d1d-168">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-168">**Submission type**</span></span>
- <span data-ttu-id="b3d1d-169">**상태**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-169">**Status**</span></span>

![관리자 전송에 대 한 필터 옵션](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="b3d1d-171">결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b3d1d-172">대화 상자가 나타나면 .csv 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="b3d1d-173">그래프 아래에는 **전자 메일** (기본값), **URL**및 **첨부 파일**의 세 가지 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="b3d1d-174">관리자 전자 메일 전송 보기</span><span class="sxs-lookup"><span data-stu-id="b3d1d-174">View admin email submissions</span></span>

<span data-ttu-id="b3d1d-175">**전자 메일** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-175">Click the **Email** tab.</span></span>

<span data-ttu-id="b3d1d-176">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b3d1d-177">**날짜**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-177">**Date**</span></span>
- <span data-ttu-id="b3d1d-178">**전송 ID**: 모든 전송에 할당 되는 GUID 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="b3d1d-179">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-180">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-181">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-181">**Sender**</span></span>
- <span data-ttu-id="b3d1d-182">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-183">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-183">**Submission type**</span></span>
- <span data-ttu-id="b3d1d-184">**배달 이유**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-184">**Delivery reason**</span></span>
- <span data-ttu-id="b3d1d-185">**상태별**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-186">**컨트롤 형식**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-186">**Control type**</span></span>
- <span data-ttu-id="b3d1d-187">**컨트롤 원본**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-187">**Control source**</span></span>

  <span data-ttu-id="b3d1d-188"><sup>\*</sup>이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="b3d1d-189">관리자 URL 전송 보기</span><span class="sxs-lookup"><span data-stu-id="b3d1d-189">View admin URL submissions</span></span>

<span data-ttu-id="b3d1d-190">**URL** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-190">Click the **URL** tab.</span></span>

<span data-ttu-id="b3d1d-191">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b3d1d-192">**날짜**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-192">**Date**</span></span>
- <span data-ttu-id="b3d1d-193">**전송 ID**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-193">**Submission ID**</span></span>
- <span data-ttu-id="b3d1d-194">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-196">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-196">**Submission type**</span></span>
- <span data-ttu-id="b3d1d-197">**상태별**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b3d1d-198"><sup>\*</sup>이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="b3d1d-199">관리자 첨부 파일 전송 보기</span><span class="sxs-lookup"><span data-stu-id="b3d1d-199">View admin attachment submissions</span></span>

<span data-ttu-id="b3d1d-200">**첨부 파일** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="b3d1d-201">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b3d1d-202">**날짜**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-202">**Date**</span></span>
- <span data-ttu-id="b3d1d-203">**전송 ID**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-203">**Submission ID**</span></span>
- <span data-ttu-id="b3d1d-204">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-205">**파일 이름**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-206">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-206">**Submission type**</span></span>
- <span data-ttu-id="b3d1d-207">**상태별**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b3d1d-208"><sup>\*</sup>이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="b3d1d-209">Microsoft에 대 한 사용자 제출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="b3d1d-210">[보고서 메시지 추가 기능](enable-the-report-message-add-in.md)을 배포 했거나 사용자가 [웹에서 Outlook의 기본 제공 보고](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)를 사용 하는 경우 **사용자 전송** 탭에서 사용자에 게 보고 하는 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="b3d1d-211">보안 & 준수 센터에서 **위협 관리** \> **검토** \> **관리자 전송 메시지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b3d1d-212">**제출** 페이지가 나타나면 **사용자 제출 서류** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="b3d1d-213">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b3d1d-214">**제출 된 날짜**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-214">**Submitted on**</span></span>
- <span data-ttu-id="b3d1d-215">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-216">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-217">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-217">**Sender**</span></span>
- <span data-ttu-id="b3d1d-218">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-219">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-219">**Submission type**</span></span>

<span data-ttu-id="b3d1d-220"><sup>\*</sup>이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="b3d1d-221">페이지 맨 위에 있는 시작 날짜와 끝 날짜를 입력할 수 있으며, 기본적으로 상자에 값을 입력 하 고 새로 고침 단추를 클릭 하 여 **보낸 사람** 을 기준으로 필터링 할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="b3d1d-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b3d1d-222">Update</span><span class="sxs-lookup"><span data-stu-id="b3d1d-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b3d1d-223">필터 조건을 변경 하려면 **보낸 사람** 단추를 클릭 하 고 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="b3d1d-224">**보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-224">**Sender domain**</span></span>
- <span data-ttu-id="b3d1d-225">**제목**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-225">**Subject**</span></span>
- <span data-ttu-id="b3d1d-226">**제출한 사람**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-226">**Submitted by**</span></span>
- <span data-ttu-id="b3d1d-227">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-227">**Submission type**</span></span>
- <span data-ttu-id="b3d1d-228">**보낸 사람 IP**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-228">**Sender IP**</span></span>

![사용자 전송에 대 한 필터 옵션](../../media/user-submissions-filter-options.png)

<span data-ttu-id="b3d1d-230">결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b3d1d-231">대화 상자가 나타나면 .csv 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="b3d1d-232">사용자 지정 사서함에 대 한 사용자 전송 보기</span><span class="sxs-lookup"><span data-stu-id="b3d1d-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="b3d1d-233">사용자가 보고 한 메시지를 수신 하도록 [사용자 지정 사서함을 구성한](user-submission.md) 경우 보고 사서함으로 배달 된 메시지를 확인 하 고 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="b3d1d-234">보안 & 준수 센터에서 **위협 관리** \> **검토** \> **관리자 전송 메시지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b3d1d-235">**제출** 페이지가 나타나면 **사용자 지정 사서함** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="b3d1d-236">페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b3d1d-237">**제출 된 날짜**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-237">**Submitted on**</span></span>
- <span data-ttu-id="b3d1d-238">**제출한 사람**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-239">**제목**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-240">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-240">**Sender**</span></span>
- <span data-ttu-id="b3d1d-241">**보낸 사람 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3d1d-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b3d1d-242">**전송 유형**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-242">**Submission type**</span></span>

<span data-ttu-id="b3d1d-243">페이지 위쪽에 있는 시작 날짜, 종료 날짜를 입력 하 고 상자에 값을 입력 하 고 새로 고침 단추를 **클릭 하 여** 필터링 하 여 필터할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="b3d1d-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b3d1d-244">Update</span><span class="sxs-lookup"><span data-stu-id="b3d1d-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b3d1d-245">결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b3d1d-246">대화 상자가 나타나면 .csv 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="b3d1d-247">사용자 지정 사서함에서 Microsoft로 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="b3d1d-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="b3d1d-248">Microsoft에 메시지를 보내지 않고 사용자가 보고 한 메시지를 가로채는 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아서 Microsoft로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="b3d1d-249">이렇게 하면 사용자 제출을 관리자 제출으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="b3d1d-250">**사용자 지정 사서함** 탭의 목록에서 메시지를 선택 하 고 **실행** 단추를 클릭 한 후 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d1d-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="b3d1d-251">**보고서 정리**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-251">**Report clean**</span></span>
- <span data-ttu-id="b3d1d-252">**신고 피싱**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-252">**Report phishing**</span></span>
- <span data-ttu-id="b3d1d-253">**맬웨어 보고**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-253">**Report malware**</span></span>
- <span data-ttu-id="b3d1d-254">**스팸 보고**</span><span class="sxs-lookup"><span data-stu-id="b3d1d-254">**Report spam**</span></span>

![실행 단추 옵션](../../media/user-submission-custom-mailbox-action-button.png)
