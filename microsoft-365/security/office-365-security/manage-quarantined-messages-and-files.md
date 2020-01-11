---
title: Office 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 09/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: '관리자는 Office 365에서 허위 격리 된 메시지를 보고, 해제 하 고, 보고할 수 있습니다. Office 365에서 메시지를 필터링 하 여 격리에 전송 하는 경우 (예: 스팸, 대량, 피싱, 맬웨어 또는 메일 흐름 규칙과 일치 하는 경우)에는 정책을 설정할 수 있습니다. '
ms.openlocfilehash: b13b369383a44608bd74d8a92ea6eb40ce6284d0
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021864"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="04aea-104">Office 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리</span><span class="sxs-lookup"><span data-stu-id="04aea-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="04aea-105">관리자는 격리 된 메시지를 확인, 해제 및 삭제 하 고 Office 365에서 가양성 격리 된 메시지를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-105">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365.</span></span> <span data-ttu-id="04aea-106">또한 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀에 대 한 ATP (고급 위협 방지)에서 캡처한 격리 된 파일을 보고 다운로드 하 고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-106">You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="04aea-107">Office 365에서 메시지를 필터링 하 여 격리로 식별 하 고, 맬웨어를 포함 하는 스팸, 대량 메일, 피싱 메일 또는 메일 흐름 규칙과 일치 하도록 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-107">You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>

<span data-ttu-id="04aea-108">기본적으로 Office 365은 피싱 메시지와 맬웨어가 있는 메시지를 격리에 직접 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-108">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine.</span></span> <span data-ttu-id="04aea-109">필터링 된 기타 메시지는 격리를 보내도록 정책을 설정 하지 않은 경우 사용자의 정크 메일 폴더로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-109">Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>

<span data-ttu-id="04aea-110">격리 된 메시지 또는 격리 한 파일을 사용 하려면 Office 365에는 GA (전역 관리자) 권한이 있거나 하나 이상의 보안 & 준수 센터 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-110">You must have global administrator (GA) permissions in Office 365, or be a member of one or more Security & Compliance Center role groups, to work with quarantined messages or quarantined files.</span></span> <span data-ttu-id="04aea-111">자세한 내용은 [Office 365 보안 & 준수 센터의 사용 권한을](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04aea-111">See [Permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center) for more information.</span></span>

## <a name="what-permissions-are-needed-to-access-administrator-quarantine"></a><span data-ttu-id="04aea-112">관리자 격리에 액세스 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="04aea-112">What permissions are needed to access administrator quarantine?</span></span>

<span data-ttu-id="04aea-113">격리를 관리 하는 권한은 \**Security & 준수 센터* 역할 그룹의 구성원 자격을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-113">The permissions to manage quarantine are controlled by membership in \**Security  & Compliance Center* role groups.</span></span> <span data-ttu-id="04aea-114">보안 & 준수 센터의 역할 그룹에 대 한 자세한 내용은 [Permissions in The Office 365 Security & 준수 센터](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04aea-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

<span data-ttu-id="04aea-115">격리를 관리 하는 권한을 부여 하는 보안 & 준수 역할 그룹은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-115">The Security & Compliance role groups that give permissions to manage quarantine are:</span></span>

- <span data-ttu-id="04aea-116">**격리 관리자**</span><span class="sxs-lookup"><span data-stu-id="04aea-116">**Quarantine Administrator**</span></span>

- <span data-ttu-id="04aea-117">**보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="04aea-117">**Security Administrator**</span></span>

## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="04aea-118">조직의 격리 된 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="04aea-118">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="04aea-119">Office 365 조직에서 전역 관리자 권한 (또는 적절 한 보안 & 준수 센터 역할)이 포함 된 회사 또는 학교 계정을 사용 하 여 Office 365에 로그인 하 고 [보안 및 준수 센터로 이동](../../compliance/go-to-the-securitycompliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-119">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="04aea-120">왼쪽의 목록에서 **위협 관리**를 확장 하 고 **검토**를 선택한 다음 **격리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-120">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

    > [!TIP]
    > <span data-ttu-id="04aea-121">보안 & 준수 센터의 **격리** 페이지로 직접 이동 하려면 다음 URL을 사용 합니다. >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="04aea-121">To go directly to the **Quarantine** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

    <span data-ttu-id="04aea-122">기본적으로 보안 & 준수 센터에는 스팸으로 격리 된 모든 전자 메일 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-122">By default, the Security & Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="04aea-123">메시지를 수신한 **날짜**를 기준으로 최신 항목부터 가장 오래된 항목 순으로 메시지가 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-123">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="04aea-124">각 메시지의 **보낸 사람**, **제목**, 만료 날짜(**만료** 아래)도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-124">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="04aea-125">해당 열 머리글을 클릭하면 필드를 정렬할 수 있습니다. 열 머리글을 두 번 클릭하면 정렬 순서가 반대로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-125">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

3. <span data-ttu-id="04aea-126">격리 된 모든 메시지의 목록을 보거나 필터링을 통해 결과 집합을 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-126">You can view a list of all quarantined messages, or you can reduce the result set by filtering.</span></span> <span data-ttu-id="04aea-127">최대 100개 항목에 대해서만 대량 작업을 수행할 수 있으므로 항목이 100개보다 많을 경우 필터링하면 결과 집합을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-127">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="04aea-128">페이지 맨 위에 있는 필터에서 옵션을 선택 하 여 단일 격리 이유로 메시지를 빠르게 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-128">You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page.</span></span> <span data-ttu-id="04aea-129">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-129">Options include:</span></span>

   - <span data-ttu-id="04aea-130">스팸으로 식별 된 메일</span><span class="sxs-lookup"><span data-stu-id="04aea-130">Mail identified as spam</span></span>

   - <span data-ttu-id="04aea-131">메일이 메일 흐름 규칙 (전송 규칙이 라고도 함)에 의해 설정 된 정책과 일치 하기 때문에 격리 됨</span><span class="sxs-lookup"><span data-stu-id="04aea-131">Mail quarantined because it matched a policy set by a mail flow rule (also known as a transport rule)</span></span>

   - <span data-ttu-id="04aea-132">대량 메일로 확인 된 메일</span><span class="sxs-lookup"><span data-stu-id="04aea-132">Mail identified as bulk mail</span></span>

   - <span data-ttu-id="04aea-133">피싱 메일로 확인 된 메일</span><span class="sxs-lookup"><span data-stu-id="04aea-133">Mail identified as phishing mail</span></span>

   - <span data-ttu-id="04aea-134">전자 맬웨어가 포함 되어 있어 격리 된 메일</span><span class="sxs-lookup"><span data-stu-id="04aea-134">Mail quarantined because it contains malware</span></span>

<span data-ttu-id="04aea-135">또한 관리자는 조직에 대 한 모든 메시지 또는 사용자에 게 전송 된 메시지만 필터링 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-135">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you.</span></span> <span data-ttu-id="04aea-136">최종 사용자는 전송 된 메시지만 보고 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-136">End users can only view and work with messages sent to them.</span></span>

<span data-ttu-id="04aea-137">결과를 필터링 하 여 특정 메시지를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-137">You can also filter your results to find specific messages.</span></span> <span data-ttu-id="04aea-138">팁은이 문서에서 [결과 필터링 및 격리 된 메시지 및 파일 찾기를](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04aea-138">For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span>

<span data-ttu-id="04aea-139">격리 된 특정 메시지를 찾은 후에는 해당 메시지를 클릭 하 여 메시지에 대 한 세부 정보를 확인 하 고 다른 사람의 사서함으로 메시지가 해제 되는 것과 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-139">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's mailbox.</span></span>

## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="04aea-140">조직의 격리 된 파일 보기</span><span class="sxs-lookup"><span data-stu-id="04aea-140">View your organization's quarantined files</span></span>

1. <span data-ttu-id="04aea-141">Office 365 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정 (또는 적절 한 보안 & 준수 센터 역할)을 사용 하 여 Office 365에 로그인 하 고 [보안 및 준수 센터로 이동](../../compliance/go-to-the-securitycompliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-141">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="04aea-142">왼쪽에서 **위협 관리**를 펼치고 **검토**를 선택한 후, **격리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-142">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

   > [!TIP]
   > <span data-ttu-id="04aea-143">보안 & 준수 센터의 **격리** 페이지로 직접 이동 하려면 다음 URL을 사용 합니다. >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="04aea-143">To go directly to the **Quarantine** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

3. <span data-ttu-id="04aea-144">기본적으로이 페이지에는 격리 된 전자 메일 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-144">By default, the page displays quarantined email messages.</span></span> <span data-ttu-id="04aea-145">격리 된 파일을 보려면 페이지 맨 위에 있는 필터를 설정 하 여 **맬웨어로**인 한 **파일**을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-145">To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**.</span></span> <span data-ttu-id="04aea-146">격리 된 파일을 사용 하려면 Office 365에 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-146">You must have admin permissions in Office 365 to work with quarantined files.</span></span>

4. <span data-ttu-id="04aea-147">파일은 격리 된 날짜를 기준으로 최신 항목에서 가장 오래 된 항목 순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-147">The files are sorted from newest to oldest based on the date the file was quarantined.</span></span> <span data-ttu-id="04aea-148">파일을 마지막으로 수정한 **사용자** , 파일을 게시 한 **서비스** , 파일 **이름**, **위치**, **파일 크기**및 만료 날짜 ( **만료**)도 각 파일에 대해 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-148">The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file.</span></span> <span data-ttu-id="04aea-149">머리글을 클릭 하 여 필드를 정렬할 수 있습니다. 열 머리글을 두 번 클릭 하 여 정렬 순서를 거꾸로 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-149">You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>

<span data-ttu-id="04aea-150">격리 된 모든 파일의 목록을 볼 수도 있고 필터링을 통해 특정 파일을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-150">You can view a list of all quarantined files, or you can search for specific files by filtering.</span></span> <span data-ttu-id="04aea-151">메시지와 마찬가지로 최대 100 개의 항목에 대해서만 대량 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-151">Just like messages, you can only do bulk operations on up to 100 items.</span></span> <span data-ttu-id="04aea-152">현재 보안 & 준수 센터에서는 맬웨어를 포함 하는 것으로 식별 되어 격리 된 파일을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-152">Currently, the Security & Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware.</span></span> <span data-ttu-id="04aea-153">팁은이 문서에서 [결과 필터링 및 격리 된 메시지 및 파일 찾기를](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04aea-153">For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span>

## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="04aea-154">결과를 필터링 하 고 격리 된 메시지 및 파일을 찾으려면</span><span class="sxs-lookup"><span data-stu-id="04aea-154">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="04aea-155"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="04aea-155"></span></span>

<span data-ttu-id="04aea-156">설정에 따라 격리 된 메시지와 파일이 많이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-156">Depending on your settings, there may be a lot of quarantined messages and files.</span></span> <span data-ttu-id="04aea-157">특정 메시지, 메시지 또는 파일 집합을 찾으려면 다양 한 추가 정보를 기준으로 격리 된 항목을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-157">To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>

1. <span data-ttu-id="04aea-158">**격리** 페이지에서 필터의 맨 위 행이 적절 하 게 메시지나 파일을 표시 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-158">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span>

   - <span data-ttu-id="04aea-159">파일을 검색 하려면 **맬웨어로**인 한 격리 된 **파일** 을 표시 하도록 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-159">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span>

     <span data-ttu-id="04aea-160">격리 된 파일의 경우 표시 되는 내용에 관계 없이 격리 된 모든 파일이이 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-160">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>

   - <span data-ttu-id="04aea-161">격리 된 메시지를 검색 하려면 **all** 또는 **my** **email**만 표시 하도록 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-161">To search for quarantined messages, set filters to show **all** or **only my** **email**.</span></span> <span data-ttu-id="04aea-162">마지막 필터 찾으려는 격리 된 메시지 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-162">For the last filter choose the type of quarantined message that you're looking for.</span></span> <span data-ttu-id="04aea-163">메일 흐름 규칙 (**전송 규칙**), **대량** 메일, **피싱** 메일 또는 **맬웨어가**포함 된 메일과 일치 하는 메시지에 대해 **스팸으로**확인 된 격리 된 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-163">You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow rule (**transport rule**), **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>

2. <span data-ttu-id="04aea-164">**결과 정렬 기준**아래의 드롭다운 목록에서 검색에 사용할 필터를 하나 이상 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-164">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists.</span></span> <span data-ttu-id="04aea-165">옵션은 파일 또는 메시지를 검색 하는지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-165">The options vary based on whether you are searching for files or messages.</span></span> <span data-ttu-id="04aea-166">지금은 검색 필드에서 와일드 카드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-166">Wildcards are not supported in search fields at this time.</span></span>

   <span data-ttu-id="04aea-167">파일 및 메시지 둘 다에 대해 메시지 또는 파일이 격리로 전송 된 날짜를 기준으로 필터링 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-167">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine.</span></span> <span data-ttu-id="04aea-168">시간, 날짜, 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-168">You can specify the date or a date range, including the time.</span></span> <span data-ttu-id="04aea-169">파일 또는 메시지가 격리에서 삭제 되는 만료 날짜를 기준으로 검색 결과를 필터링 할 수도 있고, 필터 조합을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-169">You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters.</span></span> <span data-ttu-id="04aea-170">만료 날짜별로 검색 하려면 **고급 필터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-170">To search by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="04aea-171">**만료**되는 다음 24 시간 내에 격리에서 삭제할 메시지를 선택할 수 있습니다 ( **오늘**), 다음 48 시간 이내 ( **다음 2 일**), 다음 주 ( **다음 7 일**) 또는 사용자 지정 시간 간격을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-171">Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

   <span data-ttu-id="04aea-172">메시지의 경우 다음과 같은 추가 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-172">For messages, you have the following additional options:</span></span>

   - <span data-ttu-id="04aea-173">**메시지 id**:이를 사용 하 여 메시지 id를 알고 있는 경우 특정 메시지를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-173">**Message ID**: Use this to identify a specific message when you know the message ID.</span></span>

     <span data-ttu-id="04aea-174">예를 들어, 만약 조직내 사용자에게 메시지를 보내거나 받았어야 했는데 도달하지 않았다면 메시지 추적을 사용해서 메시지를 검색할 수 있습니다([메시지 추적 보안 및 준수 센터](message-trace-scc.md) 보기). </span><span class="sxs-lookup"><span data-stu-id="04aea-174">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Message trace in the Security & Compliance Center](message-trace-scc.md)).</span></span> <span data-ttu-id="04aea-175">메시지가 메일 흐름 규칙과 일치 하거나 스팸으로 식별 되어 격리로 전송 된 메시지를 발견 하면 해당 메시지 ID를 지정 하 여 격리에서이 메시지를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-175">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID.</span></span> <span data-ttu-id="04aea-176">전체 메시지 ID 문자열을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-176">Be sure to include the full message ID string.</span></span> <span data-ttu-id="04aea-177">다음과 같이 꺾쇠괄호(\<\>)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-177">This might include angle brackets (\<\>), for example:</span></span>

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - <span data-ttu-id="04aea-178">**보낸 사람 전자 메일 주소**: 보낸 사람 단일 전자 메일 주소로 필터링할 때 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-178">**Sender email address**: Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="04aea-179">**받는 사람 전자 메일 주소**: 받는 사람 단일 전자 메일 주소로 필터링하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-179">**Recipient email address**: Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="04aea-180">**제목**: 찾으려는 전자 메일 주소의 제목을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-180">**Subject**: Enter the subject of an email address you want to find.</span></span> <span data-ttu-id="04aea-181">와일드 카드 검색은 지원 되지 않으므로 검색을 위해 메시지의 전체 제목을 사용 하 여 결과에서 메시지를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-181">Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results.</span></span> <span data-ttu-id="04aea-182">검색에서 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-182">The search is not case-sensitive.</span></span>

## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="04aea-183">격리 된 메시지 및 파일에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="04aea-183">View details about quarantined messages and files</span></span>

<span data-ttu-id="04aea-184">격리 목록에 표시 된 항목을 선택 하면 보안 & 준수 센터 오른쪽의 **세부 정보** 창에 해당 속성에 대 한 요약이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-184">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security & Compliance Center.</span></span>

### <a name="details-displayed-for-quarantined-messages"></a><span data-ttu-id="04aea-185">격리 된 메시지에 대해 표시 되는 세부 정보</span><span class="sxs-lookup"><span data-stu-id="04aea-185">Details displayed for quarantined messages</span></span>

- <span data-ttu-id="04aea-186">**메시지 ID**: 메시지의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-186">**Message ID**: The unique identifier for the message.</span></span>

- <span data-ttu-id="04aea-187">**보낸 사람 주소**: 메시지를 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-187">**Sender Address**: Who sent the message.</span></span>

- <span data-ttu-id="04aea-188">**Received**: 메시지를 받은 날짜와 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-188">**Received**: The date and time the message was received.</span></span>

- <span data-ttu-id="04aea-189">**제목**: 메시지의 제목 줄 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-189">**Subject**: The text of the subject line of the message.</span></span>

- <span data-ttu-id="04aea-190">**Type**: 메시지가 **스팸으로**식별 되었는지, **대량**, **피싱**, 일치 하는 메일 흐름 규칙 (**전송 규칙**) 인지, **악성 프로그램**을 포함 하 고 있는 것으로 확인 된 경우를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-190">**Type**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="04aea-191">**Expires**: 메시지가 격리에서 자동으로 삭제 되는 날짜와 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-191">**Expires**: The date and time when the message will automatically be deleted from quarantine.</span></span>

- <span data-ttu-id="04aea-192">**해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-192">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="04aea-193">**아직 릴리스되지**않음: 메시지가 아직 릴리스되지 않은 모든 전자 메일 주소 (있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-193">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="details-displayed-for-quarantined-files"></a><span data-ttu-id="04aea-194">격리 된 파일에 대해 표시 되는 세부 정보</span><span class="sxs-lookup"><span data-stu-id="04aea-194">Details displayed for quarantined files</span></span>

- <span data-ttu-id="04aea-195">**파일 이름** 격리 된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-195">**File Name** The name of the file in quarantine.</span></span>

- <span data-ttu-id="04aea-196">**사이트 경로** Office 365에서 파일의 위치를 정의 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-196">**Site path** URL that defines the location of the file in Office 365.</span></span>

- <span data-ttu-id="04aea-197">**검색 된 날짜/시간** 파일이 격리 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-197">**Detected Date / Time** The date and time the file was quarantined.</span></span>

- <span data-ttu-id="04aea-198">**만료** 메시지가 격리에서 삭제 되는 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-198">**Expires** The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="04aea-199">**검색 기준** 파일에서 맬웨어를 검색 하는 데 사용 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-199">**Detected By** The method used to detect the malware in the file.</span></span> <span data-ttu-id="04aea-200">이는 ATP (Advanced Threat Protection) 또는 Microsoft의 맬웨어 방지 엔진 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-200">This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="04aea-201">**출시** 파일을 놓았음을 여부를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-201">**Released** Describes whether or not the file has been released.</span></span>

- <span data-ttu-id="04aea-202">**맬웨어 이름** 파일에서 검색 된 맬웨어 및 제품의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-202">**Malware Name** Family and name of the malware detected in the file.</span></span>

- <span data-ttu-id="04aea-203">**문서 ID** 문서에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-203">**Document ID** A unique identifier for the document.</span></span>

- <span data-ttu-id="04aea-204">**파일 크기** 파일 크기 (MB)입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-204">**File Size** The size of the file in KB.</span></span>

- <span data-ttu-id="04aea-205">**조직** Office 365에서 조직의 고유한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-205">**Organization** Your organization's unique ID in Office 365.</span></span>

- <span data-ttu-id="04aea-206">**수정한 사람** 파일을 마지막으로 수정한 사용자의 회사 또는 학교 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-206">**Modified By** The work or school account of the user who last modified the file.</span></span>

- <span data-ttu-id="04aea-207">**파일 크기** 파일 크기 (MB)입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-207">**File Size** The size of the file in KB.</span></span>

- <span data-ttu-id="04aea-208">**SHA256 해시** 파일의 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-208">**SHA256 Hash** The hash of the file.</span></span> <span data-ttu-id="04aea-209">이를 사용 하 여 다른 신뢰도 저장소를 조회 하거나 사용자 환경에서 파일을 사용할 수 있는 위치를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-209">You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span>

## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="04aea-210">격리에서 메시지 및 파일 관리</span><span class="sxs-lookup"><span data-stu-id="04aea-210">Managing messages and files in quarantine</span></span>
<span data-ttu-id="04aea-211"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="04aea-211"></span></span>

<span data-ttu-id="04aea-212">메시지 또는 메시지 그룹을 선택한 후 격리에서 메시지를 관리 하기 위한 몇 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-212">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>

- <span data-ttu-id="04aea-213">아무 작업도 하지 않음.</span><span class="sxs-lookup"><span data-stu-id="04aea-213">Do nothing.</span></span> <span data-ttu-id="04aea-214">아무 작업도 하지 않도록 선택하면 Office 365에서 만료 시 메시지를 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-214">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="04aea-215">기본적으로 스팸, 대량, 맬웨어, 피싱 및 메시지는 메일 흐름 규칙과 일치 하 여 격리 된 상태로 30 일 동안 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-215">By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days.</span></span> <span data-ttu-id="04aea-216">Office 365가 격리에서 메시지를 삭제하면 해당 메시지를 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-216">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> <span data-ttu-id="04aea-217">원하는 경우 스팸 방지 정책에서 **스팸 보존 기간 (일)** 설정을 구성 하 여 격리 된 메시지의 보존 기한을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-217">If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies.</span></span> <span data-ttu-id="04aea-218">자세한 내용은이 문서의 [격리 보존 기간 설정을](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04aea-218">For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span>

- <span data-ttu-id="04aea-219">**메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면이 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-219">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="04aea-220">머리글을 깊이로 분석 하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음, **Microsoft 메시지 헤더 분석기** 를 선택 하 여 원격 연결 분석기로 이동 합니다 (마우스 오른쪽 단추를 클릭 하 고 Office 365에서이 작업을 완료 하도록 하지 않으려는 경우 **새 탭에서 열기** 를 선택 합니다.). 메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여 넣은 다음 **헤더 분석**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-220">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="04aea-221">**메시지 미리 보기**: 메시지 본문 텍스트의 원시 또는 HTML 버전을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-221">**Preview message**: Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="04aea-222">HTML 보기에서는 링크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-222">In the HTML view, links are disabled.</span></span>

- <span data-ttu-id="04aea-223">**메시지 다운로드** 또는 **파일 다운로드**: 로컬 장치에 메시지 또는 파일의 복사본을 다운로드 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-223">**Download message** or **Download file**: Choose this option to download a copy of the message or file to your local device.</span></span> <span data-ttu-id="04aea-224">격리에서 항목을 다운로드 하는 것과 관련 된 위험을 이해 하기 전에 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-224">You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so.</span></span> <span data-ttu-id="04aea-225">메시지는 사용자가 지정한 폴더에 .eml 형식으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-225">Messages are saved in .eml format to a folder you specify.</span></span> <span data-ttu-id="04aea-226">격리 된 파일은 원래 형식으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-226">Quarantined files are saved in their original format.</span></span>

- <span data-ttu-id="04aea-227">**삭제**: 원하는 경우 Office 365에서 설정 된 만료 날짜를 기다리지 않고 격리 된 항목 (또는 항목 집합)을 즉시 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-227">**Delete**: If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365.</span></span> <span data-ttu-id="04aea-228">메시지 또는 파일을 삭제 하려면 격리 목록에서 항목을 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-228">To delete a message or file, in the quarantine list, select the item and then choose **Delete**.</span></span> <span data-ttu-id="04aea-229">여러 항목을 한 번에 삭제 하려면 격리 목록에서 항목 왼쪽에 있는 확인란을 선택한 다음, **대량 작업** 페이지가 나타나면 **선택한 메시지 삭제** 또는 **선택한 파일 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-229">To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>

- <span data-ttu-id="04aea-230">**Release**: 격리 된 항목 (또는 항목 집합)을 릴리스 하 고 항목을 Microsoft에 잘못 격리 된 (가양성)로 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-230">**Release**: Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span>

  <span data-ttu-id="04aea-231">단일 메시지나 파일을 해제 하 고 보고 하려면 격리 목록에서 항목을 선택 하 고 **파일 릴리스** 또는 **메시지 릴리스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-231">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**.</span></span> <span data-ttu-id="04aea-232">다음 페이지에서 분석을 **위해 microsoft에 대 한 보고서 메시지** 및 **분석용 microsoft에 대 한 보고서 파일** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-232">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

  <span data-ttu-id="04aea-233">여러 항목을 한 번에 해제 하려면 격리 목록에서 항목 왼쪽에 있는 확인란을 선택한 다음, **대량 작업** 페이지가 나타나면 **파일 릴리스** 또는 **메시지 릴리스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-233">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**.</span></span> <span data-ttu-id="04aea-234">다음 페이지에서 분석을 **위해 microsoft에 대 한 보고서 메시지** 및 **분석용 microsoft에 대 한 보고서 파일** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-234">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

<span data-ttu-id="04aea-235">메시지를 해제 하는 경우 다음 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="04aea-235">When you're releasing messages, be aware of the following:</span></span>

- <span data-ttu-id="04aea-236">동시에 여러 메시지의 대량 릴리스를 수행 하면 메시지는 원래 식별 된 모든 받는 사람에 게 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-236">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients.</span></span> <span data-ttu-id="04aea-237">특정 받는 사람 에게만 메시지를 릴리스하기만 하려면 한 번에 하나씩 메시지를 해제 하 고 받는 사람을 개별적으로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-237">If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>

- <span data-ttu-id="04aea-238">메시지를 동일한 받는 사람에 게 두 번 이상 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-238">A message cannot be released more than once to the same recipient.</span></span>

- <span data-ttu-id="04aea-239">두 명 이상의 받는 사람에 게 메시지를 출시할 때 이전에 메시지를 받지 않은 받는 사람만 잠재 받는 사람 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-239">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="04aea-240">가양성을 보고 하도록 선택한 경우, 메시지가 나 메시지가 스팸으로, 대량, 피싱 또는 맬웨어를 포함 하는 것으로 격리 된 경우 해당 메시지는 Microsoft 스팸 분석 팀에도 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-240">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="04aea-241">팀은 메시지를 평가 및 분석 하 고 분석 결과에 따라 메시지 통과를 허용 하도록 서비스 전반의 스팸 콘텐츠 필터 규칙을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-241">The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="04aea-242">격리 보존 기간 설정</span><span class="sxs-lookup"><span data-stu-id="04aea-242">Setting the quarantine retention period</span></span>
<span data-ttu-id="04aea-243"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="04aea-243"></span></span>

<span data-ttu-id="04aea-244">메시지와 파일이 만료 되기 전에 격리 상태를 유지 하는 기간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-244">You can configure how long messages and files will remain in quarantine before they expire.</span></span> <span data-ttu-id="04aea-245">기본적으로 격리 된 항목은 30 일 동안 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-245">By default, quarantined items are kept for 30 days.</span></span> <span data-ttu-id="04aea-246">사용자가 만드는 각 정책에 대해이 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-246">You configure this setting for each policy that you create.</span></span> <span data-ttu-id="04aea-247">이 문서에 설명 된 대로 기본 정책의 값을 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-247">You can also modify the value for the default policy as described in this article.</span></span>

### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="04aea-248">보안 및 준수 센터의 기본 스팸 필터 정책에 대 한 격리 보존 기간을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="04aea-248">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="04aea-249">Office 365 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정 (또는 적절 한 보안 & 준수 센터 역할)을 사용 하 여 Office 365에 로그인 하 고 [보안 및 준수 센터로 이동](../../compliance/go-to-the-securitycompliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-249">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="04aea-250">왼쪽에서 **위협 관리**를 확장 하 고 **정책을**선택한 다음 **스팸 방지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-250">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span>

    > [!TIP]
    > <span data-ttu-id="04aea-251">보안 & 준수 센터의 **스팸 방지** 페이지로 바로 이동 하려면 다음 URL을 사용 합니다. >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="04aea-251">To go directly to the **anti-spam** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>

3. <span data-ttu-id="04aea-252">**기본 스팸 필터 정책 (ALWAYS ON)** 행을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-252">Expand the **Default spam filter policy (always ON)** row.</span></span>

4. <span data-ttu-id="04aea-253">**정책 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-253">Choose **Edit policy**.</span></span> <span data-ttu-id="04aea-254">기본 스팸 필터 정책에 대 한 설정이 새 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-254">The settings for the default spam filter policy appear in a new page.</span></span>

5. <span data-ttu-id="04aea-255">**스팸 및 대량 작업을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-255">Expand **Spam and bulk actions**.</span></span>

6. <span data-ttu-id="04aea-256">**격리**의 **스팸 보존 기간 (일)** 텍스트 상자에 Office 365에서 메시지 및 파일을 격리로 유지할 시간을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-256">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine.</span></span> <span data-ttu-id="04aea-257">기본값은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-257">The default is 30 days.</span></span> <span data-ttu-id="04aea-258">이 항목도 최대입니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-258">This is also the maximum.</span></span>

7. <span data-ttu-id="04aea-259">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04aea-259">Choose **Save**.</span></span>
