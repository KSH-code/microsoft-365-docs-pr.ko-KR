---
title: Office 365, 재구성, 보상, 관리, 위협 방지, 위협 탐색기, 보호에서 제공 되는 악성 전자 메일 찾기 및 조사
keywords: TIMailData-Inline, Security 인시던트, 인시던트, ATP PowerShell, 전자 메일 맬웨어, 손상 된 사용자, 전자 메일 피싱, 전자 메일 맬웨어, 읽기 전자 메일 머리글, 읽기 헤더, 공개 전자 메일 헤더
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 위협 조사 및 응답 기능을 사용 하 여 악성 전자 메일을 찾고 조사 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ec70bc585d4067357c9871cffc7475357fbfb5bb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634137"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="290f5-104">Office 365에서 제공 된 악성 전자 메일 조사 및 재구성</span><span class="sxs-lookup"><span data-stu-id="290f5-104">Investigate and remediate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="290f5-105">[Office 365 Advanced Threat Protection](office-365-atp.md) 을 사용 하면 조직에 사용자를 추가 하 고 조직을 보호 하기 위한 작업을 수행 하는 활동을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="290f5-106">예를 들어 조직의 보안 팀에 속한 경우 배달 된 의심 스러운 전자 메일 메시지를 찾아서 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="290f5-107">[위협 탐색기 (또는 실시간 검색)](threat-explorer.md)를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="290f5-108">시작하기 전에...</span><span class="sxs-lookup"><span data-stu-id="290f5-108">Before you begin...</span></span>

<span data-ttu-id="290f5-109">다음 조건이 충족되었는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="290f5-109">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="290f5-110">조직에 [Office 365 Advanced Threat Protection](office-365-atp.md) 이 있고 [라이선스가 사용자에 게 할당 되어](../../admin/manage/assign-licenses-to-users.md)있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-110">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
    
- <span data-ttu-id="290f5-111">조직에 대해 [감사 로깅이](../../compliance/turn-audit-log-search-on-or-off.md) 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-111">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="290f5-112">조직에 스팸 방지, 맬웨어 방지, 피싱 방지 등을 위한 정책이 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-112">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="290f5-113">[Office 365에서 위협 으로부터 보호를](protect-against-threats.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="290f5-113">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="290f5-114">전역 관리자 이거나 보안 관리자 이거나 보안 &amp; 및 준수 센터에서 검색 및 제거 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-114">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="290f5-115">[보안 &amp; 및 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="290f5-115">See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="290f5-116">일부 작업의 경우 새 미리 보기 역할이 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-116">For some actions, you must also have a new Preview role assigned.</span></span> 

#### <a name="preview-role-permissions"></a><span data-ttu-id="290f5-117">미리 보기 역할 권한</span><span class="sxs-lookup"><span data-stu-id="290f5-117">Preview role permissions</span></span>

<span data-ttu-id="290f5-118">메시지 헤더를 보거나 전자 메일 메시지 콘텐츠를 다운로드 하는 등의 특정 작업을 수행 하려면 다른 적절 한 역할 그룹에 *Preview* 라는 새 역할이 추가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-118">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="290f5-119">다음 표에서는 필요한 역할 및 사용 권한을 명확 하 게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-119">The following table clarifies required roles and permissions.</span></span>

|<span data-ttu-id="290f5-120">활동</span><span class="sxs-lookup"><span data-stu-id="290f5-120">Activity</span></span>  |<span data-ttu-id="290f5-121">역할 그룹</span><span class="sxs-lookup"><span data-stu-id="290f5-121">Role group</span></span> |<span data-ttu-id="290f5-122">미리 보기 역할이 필요 하나요?</span><span class="sxs-lookup"><span data-stu-id="290f5-122">Preview role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="290f5-123">위협 탐색기 (및 실시간 검색)를 사용 하 여 위협 분석</span><span class="sxs-lookup"><span data-stu-id="290f5-123">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |<span data-ttu-id="290f5-124">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="290f5-124">Global Administrator</span></span> <br> <span data-ttu-id="290f5-125">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="290f5-125">Security Administrator</span></span> <br> <span data-ttu-id="290f5-126">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="290f5-126">Security Reader</span></span>     | <span data-ttu-id="290f5-127">아니요</span><span class="sxs-lookup"><span data-stu-id="290f5-127">No</span></span>   |
|<span data-ttu-id="290f5-128">위협 탐색기 (및 실시간 검색)를 사용 하 여 전자 메일 메시지의 헤더 보기 및 격리 된 전자 메일 메시지 미리 보기 및 다운로드</span><span class="sxs-lookup"><span data-stu-id="290f5-128">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>    |<span data-ttu-id="290f5-129">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="290f5-129">Global Administrator</span></span> <br> <span data-ttu-id="290f5-130">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="290f5-130">Security Administrator</span></span> <br><span data-ttu-id="290f5-131">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="290f5-131">Security Reader</span></span>   |       <span data-ttu-id="290f5-132">아니요</span><span class="sxs-lookup"><span data-stu-id="290f5-132">No</span></span>  |
|<span data-ttu-id="290f5-133">위협 탐색기를 사용 하 여 머리글 보기 및 사서함으로 배달 된 전자 메일 메시지 다운로드</span><span class="sxs-lookup"><span data-stu-id="290f5-133">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>     |<span data-ttu-id="290f5-134">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="290f5-134">Global Administrator</span></span> <br><span data-ttu-id="290f5-135">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="290f5-135">Security Administrator</span></span> <br> <span data-ttu-id="290f5-136">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="290f5-136">Security Reader</span></span> <br> <span data-ttu-id="290f5-137">미리 보기</span><span class="sxs-lookup"><span data-stu-id="290f5-137">Preview</span></span>   |   <span data-ttu-id="290f5-138">예</span><span class="sxs-lookup"><span data-stu-id="290f5-138">Yes</span></span>      |

> [!NOTE]
> <span data-ttu-id="290f5-139">*미리 보기* 는 역할 그룹이 아니라 역할입니다. 미리 보기 역할은 Office 365의 기존 역할 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-139">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="290f5-140">전역 관리자 역할은 Microsoft 365 관리 센터 ([https://admin.microsoft.com](https://admin.microsoft.com))에 할당 되며 보안 관리자 및 보안 독자 역할은 보안 & 준수 센터 ([https://protection.office.com](https://protection.office.com))에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-140">The Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="290f5-141">역할 및 사용 권한에 대 한 자세한 내용은 [보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="290f5-141">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="290f5-142">배달 된 의심 스러운 전자 메일 찾기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="290f5-142">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="290f5-143">위협 탐색기는 메시지 찾기 및 삭제, 악의적인 전자 메일 보낸 사람의 IP 주소 식별, 추가 조사를 위해 인시던트 시작 등의 여러 용도로 사용할 수 있는 강력한 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-143">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="290f5-144">다음 절차에서는 탐색기를 사용 하 여 받는 사람의 사서함에서 악성 전자 메일을 찾아서 삭제 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-144">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="290f5-145">탐색기의 기본 검색에는 Zapped 항목이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-145">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="290f5-146">이는 맬웨어 또는 피싱 보기와 같은 모든 보기에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-146">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="290f5-147">Zapped 항목을 포함 하려면 ' 삭제에 의해 제거 '를 포함 하도록 설정 된 ' 배달 작업 ' 집합을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-147">To include Zapped items you need to add a 'Delivery action' set to include 'Removed by ZAP'.</span></span> <span data-ttu-id="290f5-148">모든 옵션을 포함 하는 경우 Zapped 항목을 포함 하 여 모든 배달 작업 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-148">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="290f5-149">**위협 탐색기** [https://protection.office.com](https://protection.office.com) 로 이동 하 여 회사 또는 Office 365의 학교 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-149">**Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="290f5-150">이렇게 하면 보안 &amp; 및 준수 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-150">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="290f5-151">왼쪽 탐색 빠른 실행에서 **위협 관리** \> **탐색기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-151">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![배달 작업 및 배달 위치 필드가 있는 탐색기입니다.](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. <span data-ttu-id="290f5-153">**위협 탐색기의 보기**: **보기** 메뉴에서 **모든 전자 메일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-153">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![위협 탐색기 보기 메뉴 및 전자 메일-맬웨어, 피싱, 전송 및 모든 전자 메일 옵션 (콘텐츠-맬웨어)도 가능 합니다.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="290f5-155">*맬웨어* 보기는 현재 기본값으로, 맬웨어 위협이 검색 되는 전자 메일을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-155">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="290f5-156">*피싱* 보기는 피싱에 대해 동일한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-156">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="290f5-157">그러나 *모든 전자 메일* 보기에는 위협이 검색 되었는지 여부에 관계 없이 조직에서 받은 모든 메일이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-157">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="290f5-158">짐작할 수 있듯이이 보기에는 데이터의 양이 많기 때문에 필터를 적용 하 라는 자리 표시 자가 표시 되는 이유가 여기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-158">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="290f5-159">(이 보기는 ATP P2 고객만 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="290f5-159">(This view is only available for ATP P2 customers.)</span></span>

    <span data-ttu-id="290f5-160">*전송* 보기에는 관리자 또는 사용자가 Microsoft에 보고 한 모든 메일이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-160">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="290f5-161">**위협 탐색기의 검색 및 필터링**: 검색 표시줄의 페이지 맨 위에 필터를 표시 하 여 관리자의 조사 작업에 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-161">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="290f5-162">여러 필터를 동시에 적용 하 고 쉼표로 구분 된 여러 개의 값을 필터에 추가 하 여 검색 범위를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-162">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="290f5-163">항상</span><span class="sxs-lookup"><span data-stu-id="290f5-163">Remember:</span></span>
    - <span data-ttu-id="290f5-164">필터는 대부분의 필터 조건을 정확 하 게 일치 시키는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-164">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="290f5-165">제목 필터에 포함 된 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-165">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="290f5-166">URL 필터는 프로토콜과 함께 작동 하거나 사용 하지 않습니다 (예:</span><span class="sxs-lookup"><span data-stu-id="290f5-166">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="290f5-167">https)</span><span class="sxs-lookup"><span data-stu-id="290f5-167">https).</span></span>
    - <span data-ttu-id="290f5-168">URL 도메인, URL 경로 및 URL 도메인 및 경로 필터에는 필터링을 위한 프로토콜이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-168">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="290f5-169">관련 결과를 얻으려면 필터 값을 변경할 때마다 새로 고침 아이콘을 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-169">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="290f5-170">**고급 필터**: 이러한 필터를 사용 하 여 복잡 한 쿼리를 작성 하 고 데이터 집합을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-170">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="290f5-171">*고급 필터* 를 클릭 하면 옵션이 포함 된 플라이 아웃이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-171">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="290f5-172">고급 필터링은 검색 기능에 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-172">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="290f5-173">*받는 사람*, *보낸* 사람 및 *보낸 사람 도메인* 에 부울 **NOT** filter가 도입 되어 관리자는 값을 제외 하 여 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-173">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="290f5-174">이 옵션은 selection 매개 변수에 *없음이 포함*됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-174">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="290f5-175">**NOT** 관리자는 알림 사서함, 기본 회신 사서함을 조사에서 제외 하는 것을 허용 하지 않으며, 관리자가 특정 주체 (subject = "주의")를 검색 하 여 받는 사람을 *defaultMail@contoso.com*으로 설정할 수 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-175">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail@contoso.com*.</span></span> <span data-ttu-id="290f5-176">이 값은 정확한 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-176">This is an exact value search.</span></span>

   ![받는 사람-'에는 어떤 고급 필터도 포함 되어 있지 않습니다.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="290f5-178">*시간별로 필터링* 하면 조직의 보안 팀에서 빠르게 드릴 다운 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-178">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="290f5-179">허용 되는 가장 짧은 시간은 30 분입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-179">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="290f5-180">시간-프레임 (예: 3 시간 전에 발생)에 의해 의심 스러운 작업의 범위를 좁힐 수 있으면 컨텍스트가 제한 되 고 문제를 파악 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-180">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

  ![시간을 기준으로 필터링 옵션을 선택 하면 데이터 보안 팀이 처리 해야 하는 시간이 단축 되 고 가장 짧은 기간이 30 분으로 제한 됩니다.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="290f5-182">**위협 탐색기의 필드**: 위협 탐색기는 *배달 작업*, *배달 위치*, *특수 작업*, *방향성*, *오버라이드*및 *URL 위협과*같은 많은 보안 관련 메일 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-182">**Fields in threat explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="290f5-183">또한 조직의 보안 팀이 보다 높은 확신을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-183">It also allows your organization's security team to investigate with a higher certainty.</span></span> 

    <span data-ttu-id="290f5-184">*배달 작업* 은 기존 정책 또는 검색으로 인해 전자 메일에 대해 수행 되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-184">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="290f5-185">다음은 전자 메일에 사용할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-185">Here are the possible actions an email can take:</span></span>
    - <span data-ttu-id="290f5-186">**배달** 됨-전자 메일이 사용자의 받은 편지함 또는 폴더에 배달 되어 사용자가 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-186">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="290f5-187">**Junked** (정크로 배달)-사용자의 정크 메일 폴더 또는 지운 편지함에 전자 메일이 전송 되 고 사용자가 정크 또는 삭제 된 폴더에 있는 전자 메일 메시지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-187">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="290f5-188">**차단 됨** -격리 되거나, 실패 했거나, 삭제 된 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="290f5-188">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="290f5-189">(사용자가이를 액세스할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="290f5-189">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="290f5-190">**대체** 됨-첨부 파일이 악성 인 .txt 파일로 악성 첨부 파일이 교체 되는 모든 전자 메일</span><span class="sxs-lookup"><span data-stu-id="290f5-190">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="290f5-191">**배달 위치**: 관리자가 의심 스러운 악성 메일이 종료 되는 위치와 해당 작업에 대해 수행 된 조치를 이해 하도록 돕기 위해 배달 위치 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-191">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="290f5-192">결과 데이터를 스프레드시트로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-192">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="290f5-193">가능한 배달 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-193">Possible delivery locations are:</span></span>
    - <span data-ttu-id="290f5-194">**받은 편지함 또는 폴더** -전자 메일 규칙에 따라 받은 편지함 또는 특정 폴더에 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-194">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="290f5-195">**온-프레미스 또는 external** -사서함이 클라우드에는 없지만 온-프레미스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-195">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="290f5-196">**정크 메일 폴더** -전자 메일이 사용자의 정크 메일 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-196">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="290f5-197">**지운 편지함 폴더** -전자 메일이 사용자의 지운 편지함 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-197">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="290f5-198">**격리** -사용자의 사서함이 아닌 격리 된 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-198">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="290f5-199">**Failed** – 전자 메일이 사서함에 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-199">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="290f5-200">**삭제** 됨-메일 흐름에서 전자 메일이 손실 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-200">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="290f5-201">**방향성**:이 옵션을 사용 하면 보안 운영 팀이 메일을 보내거나 진행 중인 ' 방향 '으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-201">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="290f5-202">방향성 값은 *인바운드*, *아웃 바운드*및 조직 *내* 에서 전송 되는 메일에 해당 하는 외부에서, 조직 외부로 발송 되거나 조직에 내부적으로 전송 되는 사람에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-202">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="290f5-203">이 정보는 방향 값 (예: 보안 운영 팀)이 일치 하지 않으므로 가장 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-203">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="290f5-204">*인바운드*)이 있고 보낸 사람의 도메인 (내부 도메인으로 *표시* 됨)이 명백 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-204">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="290f5-205">방향성 값은 구분 되며 메시지 추적과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-205">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="290f5-206">결과를 스프레드시트로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-206">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="290f5-207">**재정의**:이 필터는 메일의 세부 정보 탭에 표시 되는 정보를 사용 하 여 조직 또는 사용자 정책에서 메일을 허용 하 고 차단 하는 작업을 *제공 합니다.*</span><span class="sxs-lookup"><span data-stu-id="290f5-207">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="290f5-208">이 필터에 대 한 가장 중요 한 점은 조직의 보안 팀이 구성으로 인해 전달 된 의심 스러운 전자 메일 수를 확인 하는 데 도움이 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-208">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="290f5-209">이를 통해 필요에 따라 허용 및 차단 하는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-209">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="290f5-210">이 필터의 결과 집합을 스프레드시트로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-210">This result set of this filter can be exported to spreadsheet.</span></span>

|<span data-ttu-id="290f5-211">위협 탐색기 재정의</span><span class="sxs-lookup"><span data-stu-id="290f5-211">Threat Explorer Overrides</span></span>  | <span data-ttu-id="290f5-212">의미</span><span class="sxs-lookup"><span data-stu-id="290f5-212">What they mean</span></span>  |
|---------|---------|
|<span data-ttu-id="290f5-213">조직 정책에서 허용</span><span class="sxs-lookup"><span data-stu-id="290f5-213">Allowed by Org Policy</span></span>     |   <span data-ttu-id="290f5-214">메일은 조직 정책이 지시 하는 대로 사서함에 허용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-214">Mail was allowed into the mailbox as directed by the organization policy.</span></span>       |
|<span data-ttu-id="290f5-215">조직 정책에 의해 차단 됨</span><span class="sxs-lookup"><span data-stu-id="290f5-215">Blocked by Org policy</span></span>      |  <span data-ttu-id="290f5-216">메일이 조직 정책에 의해 지시 된 대로 사서함에 배달 되지 못하도록 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-216">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>    |
|<span data-ttu-id="290f5-217">조직 정책에 의해 차단 된 파일 확장명</span><span class="sxs-lookup"><span data-stu-id="290f5-217">File extension blocked by Org Policy</span></span>     | <span data-ttu-id="290f5-218">조직 정책에 의해 전송 된 파일을 사서함에 배달 하지 못하도록 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-218">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>        |
|<span data-ttu-id="290f5-219">사용자 정책에 의해 허용 됨</span><span class="sxs-lookup"><span data-stu-id="290f5-219">Allowed by User Policy</span></span>     | <span data-ttu-id="290f5-220">메일은 사용자 정책에 의해 지시 된 대로 사서함에 허용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-220">Mail was allowed into the mailbox as directed by the user policy.</span></span>        |
|<span data-ttu-id="290f5-221">사용자 정책에 의해 차단 됨</span><span class="sxs-lookup"><span data-stu-id="290f5-221">Blocked by User Policy</span></span>     | <span data-ttu-id="290f5-222">메일이 사용자 정책에 의해 지시 된 대로 사서함에 배달 되지 못하도록 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-222">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>        |

<span data-ttu-id="290f5-223">**Url 위협**: url 위협 필드는 전자 메일의 *세부 정보* 탭에 포함 되어 url에서 제공 하는 위협을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-223">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="290f5-224">URL로 제공 되는 위협에는 *맬웨어*, *피싱*또는 *스팸*이 포함 될 수 있으며 위협 요소가 *없는* url은 위협 섹션에 *없음* 이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-224">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="290f5-225">**전자 메일 시간 표시 막대 보기**: 보안 운영 팀이 보다 자세히 조사 하기 위해 전자 메일 세부 정보를 심층적으로 파악 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-225">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="290f5-226">관리자는 전자 메일 시간 표시 막대를 사용 하 여 전자 메일에 대해 수행 된 작업을 배달 후에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-226">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="290f5-227">전자 메일 시간 표시 막대를 보려면 전자 메일 메시지의 제목을 클릭 하 고 전자 메일 시간 표시 막대를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-227">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="290f5-228">(이 탭은 요약 또는 세부 정보와 같은 패널의 다른 제목 사이에 표시 됩니다.) 이러한 결과를 스프레드시트로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-228">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="290f5-229">전자 메일 일정은 전자 메일에 대 한 모든 배달 및 배달 후 이벤트를 보여 주는 테이블에 열립니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-229">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="290f5-230">전자 메일에 추가 작업을 수행 하지 않으면 *차단*됨과 같이 결과를 표시 하는 원래 배달에 대 한 단일 이벤트 (예: 결과 like *피싱*)가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-230">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="290f5-231">관리자는 탭과 전자 메일 (예: 제목, 보낸 사람, 받는 사람, 네트워크, 메시지 ID)에 대 한 모든 세부 정보를 포함 하 여 전체 전자 메일 시간 표시줄을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-231">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="290f5-232">전자 메일이 도착 한 이후 발생 한 이벤트를 이해 하기 위해 다른 위치를 확인 하는 데 소요 되는 시간이 더 낮기 때문에 전자 메일 시간 표시 막대는 임의 변경에 따라 하향 합니다</span><span class="sxs-lookup"><span data-stu-id="290f5-232">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="290f5-233">전자 메일에서 여러 이벤트가 발생 하거나 같은 시간에 발생할 경우 이러한 이벤트는 시간 표시 막대 보기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-233">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="290f5-234">**미리 보기/다운로드**: 위협 탐색기에서는 의심 스러운 전자 메일을 조사 하는 데 필요한 세부 정보를 보안 운영 팀에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-234">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="290f5-235">보안 운영 팀은 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-235">Your security operations team can either:</span></span>

    - <span data-ttu-id="290f5-236">[배달 작업 및 위치를 확인](#check-the-delivery-action-and-location)합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-236">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="290f5-237">[전자 메일의 시간 표시 막대를 봅니다](#view-the-timeline-of-your-email).</span><span class="sxs-lookup"><span data-stu-id="290f5-237">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

    ##### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="290f5-238">배달 작업 및 위치 확인</span><span class="sxs-lookup"><span data-stu-id="290f5-238">Check the delivery action and location</span></span>

    <span data-ttu-id="290f5-239">[위협 탐색기 (및 실시간 검색)](threat-explorer.md)에서는 이제 이전 **배달 상태** 열 대신 **배달 작업** 및 **배달 위치** 열이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-239">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="290f5-240">이로 인해 전자 메일 메시지가 나타나는 위치를 보다 완전 하 게 파악할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-240">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="290f5-241">이 변경의 목표 중 일부는 보안 작업 팀에 게 더 쉽게 조사를 만들기 위해 발생 하지만 문제 전자 메일 메시지의 위치를 한눈에 파악 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-241">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

    <span data-ttu-id="290f5-242">배달 상태는 이제 다음과 같은 두 개의 열로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-242">Delivery Status is now broken out into two columns:</span></span>

    - <span data-ttu-id="290f5-243">**배달 작업** -이 전자 메일의 상태는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="290f5-243">**Delivery action** - What is the status of this email?</span></span>

    - <span data-ttu-id="290f5-244">**배달 위치** -이 전자 메일의 경로가 어떻게 설정 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="290f5-244">**Delivery location** - Where was this email routed as a result?</span></span>

    <span data-ttu-id="290f5-245">배달 작업은 기존 정책 또는 검색으로 인해 전자 메일에 대해 수행 되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-245">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="290f5-246">다음은 전자 메일에 사용할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-246">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="290f5-247">**배달** 됨-전자 메일이 사용자의 받은 편지함 또는 폴더에 배달 되어 사용자가 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-247">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

    - <span data-ttu-id="290f5-248">**Junked** – 전자 메일이 사용자의 정크 메일 폴더 또는 삭제 된 폴더에 전송 되었으며 사용자가 정크 또는 삭제 된 폴더에 있는 전자 메일 메시지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-248">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

    - <span data-ttu-id="290f5-249">**차단 됨** -격리 되거나, 실패 했거나, 삭제 된 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="290f5-249">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="290f5-250">(사용자가이를 액세스할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="290f5-250">(This is completely inaccessible by the user.)</span></span>

    - <span data-ttu-id="290f5-251">**대체** 됨-첨부 파일이 악성 인 .txt 파일로 악성 첨부 파일이 교체 되는 모든 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-251">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
    <span data-ttu-id="290f5-252">배달 위치는 배달 후 실행 되는 정책 및 검색의 결과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-252">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="290f5-253">배달 작업에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-253">It's linked to a Delivery Action.</span></span> <span data-ttu-id="290f5-254">이 필드는 문제 메일을 찾은 경우 수행 되는 작업에 대 한 통찰력을 제공 하기 위해 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-254">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="290f5-255">배달 위치의 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-255">Here are the possible values of delivery location:</span></span>

    - <span data-ttu-id="290f5-256">**받은 편지함 또는 폴더** -전자 메일이 받은 편지함 또는 폴더 (전자 메일 규칙에 따라 다름)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-256">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

    - <span data-ttu-id="290f5-257">**온-프레미스 또는 external** -사서함이 클라우드에는 없지만 온-프레미스에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="290f5-257">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

    - <span data-ttu-id="290f5-258">**정크 메일 폴더** -전자 메일이 사용자의 정크 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-258">**Junk folder** – The email is in a user's Junk folder.</span></span>

    - <span data-ttu-id="290f5-259">**지운 편지함 폴더** -전자 메일이 사용자의 지운 편지함 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-259">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

    - <span data-ttu-id="290f5-260">**격리** -사용자의 사서함이 아닌 격리 된 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-260">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

    - <span data-ttu-id="290f5-261">**Failed** – 전자 메일이 사서함에 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-261">**Failed** – The email failed to reach the mailbox.</span></span>

    - <span data-ttu-id="290f5-262">**삭제** 됨-메일 흐름의 어딘가에 전자 메일이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-262">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

     ##### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="290f5-263">전자 메일의 시간 표시 막대 보기</span><span class="sxs-lookup"><span data-stu-id="290f5-263">View the timeline of your email</span></span>
  
     <span data-ttu-id="290f5-264">**전자 메일 시간 표시 막대** 는 보안 운영 팀에서 더 쉽게 찾을 수 있도록 하는 위협 탐색기의 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-264">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="290f5-265">전자 메일에서 여러 이벤트가 발생 하거나 같은 시간에 발생할 경우 이러한 이벤트는 시간 표시 막대 보기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-265">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="290f5-266">전자 메일로 배달 후 발생 하는 일부 이벤트는 **특수 작업** 열에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-266">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="290f5-267">전자 메일 메시지의 시간 표시 막대와 정보를 결합 하 여 배달 후 발생 하는 모든 특수 작업을 통해 관리자는 정책 및 위협 처리 (예: 메일을 라우팅된 위치, 일부 경우에는 최종 평가)를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="290f5-267">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view. 
    
    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was. 

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body) 

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps: 

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center. 
    
2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table. 

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a><span data-ttu-id="290f5-268">관련 항목</span><span class="sxs-lookup"><span data-stu-id="290f5-268">Related topics</span></span>

[<span data-ttu-id="290f5-269">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="290f5-269">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)
  
[<span data-ttu-id="290f5-270">Office 365에서 위협 으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="290f5-270">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="290f5-271">Office 365 Advanced Threat Protection에 대 한 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="290f5-271">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
