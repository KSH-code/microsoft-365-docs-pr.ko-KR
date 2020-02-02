---
title: 고급 eDiscovery 보고서
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 736117f62877bd0b33ae1007f00d5a32680963fb
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662264"
---
# <a name="advanced-ediscovery-reports-preview"></a><span data-ttu-id="54db5-102">고급 eDiscovery 보고서 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="54db5-102">Advanced eDiscovery reports (preview)</span></span>

<span data-ttu-id="54db5-103">고급 eDiscovery 보고서는 조직 전체의 사례 데이터를 집계 하 여 데이터 분석 및 조직 보고를 간소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-103">Advanced eDiscovery reports help you aggregate case data across your organization to streamline data analysis and organizational reporting.</span></span> <span data-ttu-id="54db5-104">고급 eDiscovery 보고서 기능에는 다음과 같은 질문에 답할 수 있도록 몇 가지 기본 제공 보고서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-104">The Advanced eDiscovery reports feature includes several built-in reports to help you answer questions like:</span></span>

- <span data-ttu-id="54db5-105">조직의 모든 사례에 대 한 활성 custodians 수</span><span class="sxs-lookup"><span data-stu-id="54db5-105">How many active custodians are there for all cases in my organization?</span></span>

- <span data-ttu-id="54db5-106">내 조직의 모든 경우에 대해 보류 중인 데이터 원본 수</span><span class="sxs-lookup"><span data-stu-id="54db5-106">How many data sources are on hold for all cases in my organization?</span></span>

- <span data-ttu-id="54db5-107">조직의 모든 경우에 대해 지난 달에 실행 된 보류 알림 개수</span><span class="sxs-lookup"><span data-stu-id="54db5-107">How many hold notifications have been issued in the last month for all cases in my organization?</span></span>

- <span data-ttu-id="54db5-108">조직에 있는 활성 및 닫힌 사례는 몇 개입니까?</span><span class="sxs-lookup"><span data-stu-id="54db5-108">How many active and closed cases are there in my organization?</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="54db5-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="54db5-109">Before you begin</span></span>

- <span data-ttu-id="54db5-110">고급 eDiscovery 보고서에 액세스 하려면 eDiscovery 관리 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-110">To access Advanced eDiscovery reports, you must be a member of the eDiscovery Admin role group.</span></span> <span data-ttu-id="54db5-111">이 역할 그룹의 구성원 인 경우 보고서의 데이터를 보고, 필터링 하 고, 내보내야 하는 데 필요한 권한이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-111">Being a member of this role group provides you with the necessary permissions to view, filter, and export the data in the reports.</span></span> <span data-ttu-id="54db5-112">자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54db5-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="54db5-113">고급 eDiscovery 보고서는 매일 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-113">Advanced eDiscovery reports are refreshed daily.</span></span> <span data-ttu-id="54db5-114">따라서 새로운 사례, custodians, 데이터 원본 및 통신이 만들어지고 해당 보고서에 표시 될 때 지연이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-114">As a result, there may be a delay when new cases, custodians, data sources, and communications are created and when they appear in the corresponding report.</span></span>

<span data-ttu-id="54db5-115">고급 eDiscovery 보고서에 액세스 하려면:</span><span class="sxs-lookup"><span data-stu-id="54db5-115">To access the Advanced eDiscovery reports:</span></span>

1. <span data-ttu-id="54db5-116">https://protection.office.com으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-116">Go to https://protection.office.com</span></span>
  
2. <span data-ttu-id="54db5-117">회사 또는 학교 계정을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-117">Sign into Office 365 using your work or school account.</span></span>
  
3. <span data-ttu-id="54db5-118">보안 & 준수 센터에서 **eDiscovery > Advanced eDiscovery**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-118">In the Security & Compliance Center, click **eDiscovery > Advanced eDiscovery**.</span></span>
  
   <span data-ttu-id="54db5-119">**고급 eDiscovery** 홈 페이지에서는 사례, Custodian, 데이터 원본 및 통신 보고서 탭이 페이지 위쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-119">On the **Advanced eDiscovery** home page, the Case, Custodian, Data Source, and Communications report tabs are displayed across the top of the page.</span></span> 
  
   ![홈 페이지의 고급 eDiscovery 보고서](media/report-home.png)

5. <span data-ttu-id="54db5-121">보고서를 보려면 보고서 탭을 클릭 하 고 필요한 경우 다음 작업 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-121">To view a report, click a report tab, and then if necessary you can do one of the following things:</span></span>

   ![보고서 데이터를 필터링 하거나 다운로드할 수 있습니다.](media/AeDReportsFilterDownload.png)

   <span data-ttu-id="54db5-123">a.</span><span class="sxs-lookup"><span data-stu-id="54db5-123">a.</span></span> <span data-ttu-id="54db5-124">**필터** 를 클릭 하 여 보고서 데이터의 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-124">Click **Filter** to narrow the report data.</span></span> <span data-ttu-id="54db5-125">각 보고서에 대해 서로 다른 속성을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-125">You can filter on different properties for each report.</span></span>
  
   <span data-ttu-id="54db5-126">b.</span><span class="sxs-lookup"><span data-stu-id="54db5-126">b.</span></span> <span data-ttu-id="54db5-127">**Csv로 다운로드** 를 클릭 하 여 보고서 데이터를 csv 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-127">Click **Download to CSV** to export the report data to a CSV file.</span></span>

## <a name="case-report"></a><span data-ttu-id="54db5-128">사례 보고서</span><span class="sxs-lookup"><span data-stu-id="54db5-128">Case report</span></span>

<span data-ttu-id="54db5-129">사례 보고서는 조직의 활성 및 닫힌 진행 중인 eDiscovery 사례에 대 한 정보를 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-129">The Case report aggregates information about active and closed Advance eDiscovery cases in your organization.</span></span>

|<span data-ttu-id="54db5-130">열</span><span class="sxs-lookup"><span data-stu-id="54db5-130">Column</span></span>        |<span data-ttu-id="54db5-131">설명</span><span class="sxs-lookup"><span data-stu-id="54db5-131">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="54db5-132">사례 ID</span><span class="sxs-lookup"><span data-stu-id="54db5-132">Case ID</span></span> | <span data-ttu-id="54db5-133">각 사례에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-133">The unique identifier for each case.</span></span>| 
|<span data-ttu-id="54db5-134">사례 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-134">Case name</span></span> | <span data-ttu-id="54db5-135">대/소문자를 구분 하는 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-135">User-defined name of the case.</span></span>|
|<span data-ttu-id="54db5-136">상태</span><span class="sxs-lookup"><span data-stu-id="54db5-136">Status</span></span> | <span data-ttu-id="54db5-137">케이스가 활성 상태 인지 닫혀 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-137">Indicates if the case is active or closed.</span></span>|
|<span data-ttu-id="54db5-138">만든 날짜</span><span class="sxs-lookup"><span data-stu-id="54db5-138">Date created</span></span> |<span data-ttu-id="54db5-139">사례를 만든 번째 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-139">Th date when the case was created.</span></span> <span data-ttu-id="54db5-140">날짜는 UTC 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-140">Dates are in UTC format.</span></span>|
|<span data-ttu-id="54db5-141">마지막으로 수정한 날짜</span><span class="sxs-lookup"><span data-stu-id="54db5-141">Last modified</span></span> |<span data-ttu-id="54db5-142">사례가 종료 되거나 마지막으로 업데이트 된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-142">The date when the case was closed or last updated.</span></span> <span data-ttu-id="54db5-143">날짜는 UTC 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-143">Dates are in UTC format.</span></span>| 
|||

## <a name="custodian-report"></a><span data-ttu-id="54db5-144">Custodian 보고서</span><span class="sxs-lookup"><span data-stu-id="54db5-144">Custodian report</span></span>

<span data-ttu-id="54db5-145">EDiscovery 워크플로에서 법적 사례 또는 조사를 수행 하는 사용자를 *데이터 custodians* (또는 *custodians*) 라고 하며 "문서 또는 전자 파일의 관리 제어 권한"으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-145">In the eDiscovery workflow, individuals who are the subject of a legal case or investigation are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="54db5-146">Custodian 보고서는 조직의 모든 경우에 대해 데이터 원본이 보존 되는 모든 custodians을 식별 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-146">The Custodian report helps you identify all the custodians whose data sources are placed on hold for all cases in your organization.</span></span>

|<span data-ttu-id="54db5-147">열</span><span class="sxs-lookup"><span data-stu-id="54db5-147">Column</span></span>         |<span data-ttu-id="54db5-148">설명</span><span class="sxs-lookup"><span data-stu-id="54db5-148">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="54db5-149">Custodian 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-149">Custodian name</span></span>| <span data-ttu-id="54db5-150">Active Directory에 있는 custodian의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-150">The name of the custodian in Active Directory.</span></span>|
|<span data-ttu-id="54db5-151">Custodian UPN</span><span class="sxs-lookup"><span data-stu-id="54db5-151">Custodian UPN</span></span> | <span data-ttu-id="54db5-152">Custodian의 사용자 계정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-152">The user principal name of the custodian.</span></span>|
|<span data-ttu-id="54db5-153">Custodian ID</span><span class="sxs-lookup"><span data-stu-id="54db5-153">Custodian ID</span></span> | <span data-ttu-id="54db5-154">지정 된 사례 내의 custodian에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-154">The unique identifier for the custodian within a given case.</span></span> |
|<span data-ttu-id="54db5-155">사례 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-155">Case name</span></span> | <span data-ttu-id="54db5-156">사례에 대 한 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-156">The user-defined name of the case.</span></span>|
|<span data-ttu-id="54db5-157">보류 상태</span><span class="sxs-lookup"><span data-stu-id="54db5-157">Hold status</span></span> | <span data-ttu-id="54db5-158">Custodian가 현재 보류 중인 상태 인지 또는 사례에서 해제 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-158">Indicates if the custodian is currently on hold or if they have been released from the case.</span></span>|
|<span data-ttu-id="54db5-159">사례 Id</span><span class="sxs-lookup"><span data-stu-id="54db5-159">Case Id</span></span> | <span data-ttu-id="54db5-160">사례에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-160">The unique identifier for the case.</span></span>|
|<span data-ttu-id="54db5-161">통신 상태</span><span class="sxs-lookup"><span data-stu-id="54db5-161">Communication status</span></span> |<span data-ttu-id="54db5-162">Custodian에서 법적 보존 알림을 실행 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-162">Indicates if the custodian was issued a legal hold notification or not.</span></span> |
|<span data-ttu-id="54db5-163">Custodian 추가 됨</span><span class="sxs-lookup"><span data-stu-id="54db5-163">Custodian added</span></span> | <span data-ttu-id="54db5-164">Custodian가 사례에 추가 된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-164">The date the custodian was added to the case.</span></span> <span data-ttu-id="54db5-165">날짜는 UTC 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-165">Dates are in UTC format.</span></span>|
|||

## <a name="data-source-report"></a><span data-ttu-id="54db5-166">데이터 원본 보고서</span><span class="sxs-lookup"><span data-stu-id="54db5-166">Data source report</span></span>

<span data-ttu-id="54db5-167">고급 eDiscovery 사례를 사용 하 여 서비스 케이스와 관련이 있을 수 있는 콘텐츠를 보존 하는 보류를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-167">You can use an Advanced eDiscovery case to create holds to preserve content that may be relevant to the case.</span></span> <span data-ttu-id="54db5-168">Advanced eDiscovery 보존 기능을 사용 하 여 custodians 및 해당 데이터 원본에 대해 보류를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-168">Using the Advanced eDiscovery hold capabilities, you can place holds on custodians and their data sources.</span></span> <span data-ttu-id="54db5-169">또한 사서함과 비즈니스용 OneDrive 계정에 custodial이 없는 보류를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-169">Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business accounts.</span></span> <span data-ttu-id="54db5-170">데이터 원본 보고서를 사용 하 여 조직의 모든 경우에 대해 보류 중인 콘텐츠 위치에 대 한 세부 정보를 집계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-170">You can use the data sources report to aggregate details about content locations on hold for all cases in your organization.</span></span>

|<span data-ttu-id="54db5-171">열</span><span class="sxs-lookup"><span data-stu-id="54db5-171">Column</span></span>        |<span data-ttu-id="54db5-172">설명</span><span class="sxs-lookup"><span data-stu-id="54db5-172">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="54db5-173">사례 ID</span><span class="sxs-lookup"><span data-stu-id="54db5-173">Case ID</span></span> |<span data-ttu-id="54db5-174">각 사례에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-174">The unique identifier for each case.</span></span> |
|<span data-ttu-id="54db5-175">작업량</span><span class="sxs-lookup"><span data-stu-id="54db5-175">Workload</span></span> |<span data-ttu-id="54db5-176">보류 된 콘텐츠 위치의 유형 (예: Exchange 또는 SharePoint)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-176">Indicates the type of content location placed on hold (for example, Exchange or SharePoint).</span></span>
|<span data-ttu-id="54db5-177">위치 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-177">Location name</span></span> |<span data-ttu-id="54db5-178">Exchange 사서함의 SMTP 주소 또는 콘텐츠 위치의 URL (SharePoint 사이트용)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-178">Indicates the SMTP address (for Exchange mailboxes) or the URL (for SharePoint sites) of the content location.</span></span> | 
|<span data-ttu-id="54db5-179">Custodian ID</span><span class="sxs-lookup"><span data-stu-id="54db5-179">Custodian ID</span></span> |<span data-ttu-id="54db5-180">데이터 원본이 custodian에 속하는 경우이 열에는 지정 된 사례의 custodian에 대 한 고유 식별자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-180">If the data source belongs to a custodian, this column shows the unique identifier for the custodian in a given case.</span></span> <span data-ttu-id="54db5-181">Custodial가 아닌 위치에 대해서는이 열이 null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-181">This column will be null for non-custodial locations.</span></span>|
|<span data-ttu-id="54db5-182">Custodian 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-182">Custodian name</span></span> |<span data-ttu-id="54db5-183">Active Directory에 있는 custodian의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-183">The name of the custodian in Active Directory.</span></span>| 
|<span data-ttu-id="54db5-184">사례 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-184">Case name</span></span> |<span data-ttu-id="54db5-185">사례에 대 한 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-185">The user-defined name of the case.</span></span>| 
|<span data-ttu-id="54db5-186">상태</span><span class="sxs-lookup"><span data-stu-id="54db5-186">Status</span></span> |<span data-ttu-id="54db5-187">콘텐츠 위치가 현재 보류 상태 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-187">Indicates if the content location is currently on hold.</span></span> | 
|<span data-ttu-id="54db5-188">보존 정책 ID</span><span class="sxs-lookup"><span data-stu-id="54db5-188">Hold policy ID</span></span> |<span data-ttu-id="54db5-189">콘텐츠 위치를 포함 하는 보류에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-189">The unique identifier for the hold that contains the content location.</span></span> | 
|<span data-ttu-id="54db5-190">만든 날짜 유지</span><span class="sxs-lookup"><span data-stu-id="54db5-190">Hold created date</span></span> |<span data-ttu-id="54db5-191">보류 정책이 만들어진 날짜를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-191">Indicates the date when the hold policy was created.</span></span> <span data-ttu-id="54db5-192">날짜는 UTC 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-192">Dates are in UTC format.</span></span> | 
|<span data-ttu-id="54db5-193">보류 정책 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-193">Hold policy name</span></span> |<span data-ttu-id="54db5-194">콘텐츠 위치를 포함 하는 보류의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-194">The name of the hold that contains the content location.</span></span> |
|<span data-ttu-id="54db5-195">수정 된 날짜 유지</span><span class="sxs-lookup"><span data-stu-id="54db5-195">Hold modified date</span></span> |<span data-ttu-id="54db5-196">보류를 마지막으로 수정한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-196">The date when the hold was last modified.</span></span> <span data-ttu-id="54db5-197">날짜는 UTC 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-197">Dates are in UTC format.</span></span>| 
|<span data-ttu-id="54db5-198">마지막으로 수정한 사람 보존</span><span class="sxs-lookup"><span data-stu-id="54db5-198">Hold last modified by</span></span>|<span data-ttu-id="54db5-199">보류를 마지막으로 수정한 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-199">The name of the user that last modified the hold.</span></span>| 
|||

## <a name="communication-report"></a><span data-ttu-id="54db5-200">통신 보고서</span><span class="sxs-lookup"><span data-stu-id="54db5-200">Communication report</span></span>

<span data-ttu-id="54db5-201">조직은 법적 정보 보호를 위해 법적 고 지 사항에 대 한 의무를 custodians 사용자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-201">Your organization may issue legal hold notices to notify custodians of their obligation to preserve relevant information as part of legal case or investigation.</span></span> <span data-ttu-id="54db5-202">통신 보고서를 사용 하 여 승인, 미리 알림, 에스컬레이션 및 기타 유형의 통신에 대 한 집계 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-202">You can use the communications report to view aggregate data on acknowledgments, reminders, escalations, and other types of communications.</span></span>

|<span data-ttu-id="54db5-203">열</span><span class="sxs-lookup"><span data-stu-id="54db5-203">Column</span></span>         |<span data-ttu-id="54db5-204">설명</span><span class="sxs-lookup"><span data-stu-id="54db5-204">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="54db5-205">사례 ID</span><span class="sxs-lookup"><span data-stu-id="54db5-205">Case ID</span></span> | <span data-ttu-id="54db5-206">사례에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-206">The unique identifier for the case.</span></span>|
|<span data-ttu-id="54db5-207">사례 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-207">Case name</span></span> | <span data-ttu-id="54db5-208">대/소문자를 구분 하는 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-208">User-defined name of the case.</span></span>|
|<span data-ttu-id="54db5-209">Custodian ID</span><span class="sxs-lookup"><span data-stu-id="54db5-209">Custodian ID</span></span> |<span data-ttu-id="54db5-210">지정 된 사례에서 custodian에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-210">The unique identifier for the custodian in a given case.</span></span>|
|<span data-ttu-id="54db5-211">Custodian 이름</span><span class="sxs-lookup"><span data-stu-id="54db5-211">Custodian name</span></span> |<span data-ttu-id="54db5-212">Custodian의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-212">The name of the custodian.</span></span>|
|<span data-ttu-id="54db5-213">알림 유형</span><span class="sxs-lookup"><span data-stu-id="54db5-213">Notice type</span></span> |<span data-ttu-id="54db5-214">Custodian에 대해 실행 된 알림의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-214">Indicates the type of notice that was issued to the custodian.</span></span>|
|<span data-ttu-id="54db5-215">관리자 발급</span><span class="sxs-lookup"><span data-stu-id="54db5-215">Issuing officer</span></span> |<span data-ttu-id="54db5-216">법적 보존 알림을 실행 한 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-216">The name of the user that issued the legal hold notification.</span></span>|
|<span data-ttu-id="54db5-217">알림 이벤트</span><span class="sxs-lookup"><span data-stu-id="54db5-217">Notification event</span></span>|<span data-ttu-id="54db5-218">사용자에 게 전송 된 법적 보존 알림 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-218">Indicates the legal hold notification message sent to the user.</span></span> <span data-ttu-id="54db5-219">가능한 값은 미리 알림, 에스컬레이션, 확인 및 유지 발급입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-219">Possible values include: Reminder, Escalation, Acknowledgment, and Hold Issuance.</span></span>|
|<span data-ttu-id="54db5-220">보낸 날짜</span><span class="sxs-lookup"><span data-stu-id="54db5-220">Date sent</span></span> |<span data-ttu-id="54db5-221">통신이 실행 된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-221">The date when the communication was issued.</span></span> <span data-ttu-id="54db5-222">감사의 경우이 열에는 custodian에서 통지가 승인 된 시간이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-222">For acknowledgments, this column indicates the time that the notice was acknowledged by the custodian.</span></span> <span data-ttu-id="54db5-223">날짜는 UTC 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="54db5-223">Dates are in UTC format.</span></span>|
|||
