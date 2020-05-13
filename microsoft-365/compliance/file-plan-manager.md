---
title: 파일 계획 관리자 개요
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 파일 계획 관리자는 보존 레이블 및 보존 레이블 정책에 대한 고급 관리 기능을 제공하고, 생성부터 공동 작업, 레코드 선언, 보존 및 최종 처리에 이르는 전체 콘텐츠 수명 주기 동안 레이블 및 레이블-콘텐츠 간 활동을 트래버스하는 통합 방법을 제공합니다.
ms.openlocfilehash: 78a012b4ecc3401a664fba5e270e7cd67a5dce49
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208122"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="4e840-103">파일 계획 관리자 개요</span><span class="sxs-lookup"><span data-stu-id="4e840-103">Overview of file plan manager</span></span>

><span data-ttu-id="4e840-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4e840-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4e840-105">파일 계획 관리자는 보존 레이블 및 보존 레이블 정책에 대한 고급 관리 기능을 제공하고, 생성부터 공동 작업, 레코드 선언, 보존 및 최종 처리에 이르는 전체 콘텐츠 수명 주기 동안 레이블 및 레이블-콘텐츠 간 활동을 트래버스하는 통합 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-105">File plan manager provides advanced management capabilities for retention labels, retention label policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span> 

<span data-ttu-id="4e840-106">보안 및 준수 센터에서 파일 계획 관리자에 액세스하려면 **레코드 관리** > **파일 계획**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-106">To access file plan manager in the security and compliance center, go to **Records management** > **File plan**.</span></span>

![파일 계획 페이지](../media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="4e840-108">파일 계획 관리자 액세스</span><span class="sxs-lookup"><span data-stu-id="4e840-108">Accessing file plan manager</span></span>

<span data-ttu-id="4e840-109">파일 계획 관리자에 액세스하려면 다음과 같은 관리자 역할 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-109">To access file plan manager, you must have one of the following admin roles:</span></span>
    
- <span data-ttu-id="4e840-110">보존 관리자</span><span class="sxs-lookup"><span data-stu-id="4e840-110">Retention Manager</span></span>

- <span data-ttu-id="4e840-111">보기 전용 보존 관리자</span><span class="sxs-lookup"><span data-stu-id="4e840-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="4e840-112">기본 보존 레이블 및 레이블 정책</span><span class="sxs-lookup"><span data-stu-id="4e840-112">Default retention labels and label policy</span></span>

<span data-ttu-id="4e840-113">보안 및 규정 준수 센터에 보존 레이블이 없는 경우, 왼쪽 탐색에서 **파일 계획**을 처음 선택하면 **Default Data Governance Publishing Policy**라는 레이블 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="4e840-114">이 레이블 정책에는 세 가지 보존 레이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="4e840-115">**운영 프로시저**</span><span class="sxs-lookup"><span data-stu-id="4e840-115">**Operational procedure**</span></span>
- <span data-ttu-id="4e840-116">**비즈니스 일반**</span><span class="sxs-lookup"><span data-stu-id="4e840-116">**Business general**</span></span>
- <span data-ttu-id="4e840-117">**계약**</span><span class="sxs-lookup"><span data-stu-id="4e840-117">**Contract agreement**</span></span>

<span data-ttu-id="4e840-118">이 보존 레이블은 콘텐츠를 삭제하지 않고 보존하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="4e840-119">이 레이블 정책은 전체 조직에 게시되고 비활성화하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="4e840-120">**보존 정책을 만들었습니다** 및 **보존 정책에 대한 보존 구성을 만들었습니다**와 같은 활동에 대한 감사 로그를 검토하여 파일 계획 관리자를 열고 첫 번째 실행 환경을 시작한 사용자를 판별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="4e840-121">고객 피드백으로 인해, 위에 언급된 기본 보존 레이블과 보존 레이블 정책을 만드는 이 기능을 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-121">Due to customer feedback, we have removed this feature that creates the default retention labels and retention label policy mentioned above.</span></span> <span data-ttu-id="4e840-122">2019년 4월 11일 이전에 파일 계획 관리자를 연 경우에만 이러한 보존 레이블과 보존 레이블 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-122">You will only see these retention labels and retention label policy if you opened file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="4e840-123">파일 계획 탐색</span><span class="sxs-lookup"><span data-stu-id="4e840-123">Navigating your file plan</span></span>

<span data-ttu-id="4e840-124">파일 계획 관리자를 사용하면 하나의 보기에서 모든 보존 레이블 및 정책의 설정을 보다 쉽게 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="4e840-125">파일 계획 외부에서 만들어진 보존 레이블도 파일 계획에서 사용할 수 있고 그 반대의 경우도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="4e840-126">**파일 계획 레이블** 탭에서 다음과 같은 추가 정보 및 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-126">On the file plan **Labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="4e840-127">레이블 설정 열</span><span class="sxs-lookup"><span data-stu-id="4e840-127">Label settings columns</span></span>

- <span data-ttu-id="4e840-p103">**기준**은 보존 기간을 시작할 트리거 유형을 식별합니다. 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="4e840-130">이벤트</span><span class="sxs-lookup"><span data-stu-id="4e840-130">Event</span></span>
    - <span data-ttu-id="4e840-131">만든 날짜</span><span class="sxs-lookup"><span data-stu-id="4e840-131">When created</span></span>
    - <span data-ttu-id="4e840-132">마지막으로 수정한 날짜</span><span class="sxs-lookup"><span data-stu-id="4e840-132">When last modified</span></span>
    - <span data-ttu-id="4e840-133">레이블을 지정한 날짜</span><span class="sxs-lookup"><span data-stu-id="4e840-133">When labeled</span></span>
- <span data-ttu-id="4e840-p104">**레코드**는 레이블이 적용될 때 항목이 선언된 레코드가 될지를 식별합니다. 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="4e840-136">아니요</span><span class="sxs-lookup"><span data-stu-id="4e840-136">No</span></span>
    - <span data-ttu-id="4e840-137">예</span><span class="sxs-lookup"><span data-stu-id="4e840-137">Yes</span></span>
    - <span data-ttu-id="4e840-138">예(규정)</span><span class="sxs-lookup"><span data-stu-id="4e840-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="4e840-p105">**보존**은 보존 유형을 식별합니다. 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="4e840-141">유지</span><span class="sxs-lookup"><span data-stu-id="4e840-141">Keep</span></span>
    - <span data-ttu-id="4e840-142">유지 및 삭제</span><span class="sxs-lookup"><span data-stu-id="4e840-142">Keep and delete</span></span>
    - <span data-ttu-id="4e840-143">삭제</span><span class="sxs-lookup"><span data-stu-id="4e840-143">Delete</span></span>
- <span data-ttu-id="4e840-p106">**처리**는 보존 기간이 끝날 때 콘텐츠에 대해 수행할 작업을 식별합니다. 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="4e840-146">null</span><span class="sxs-lookup"><span data-stu-id="4e840-146">null</span></span>
    - <span data-ttu-id="4e840-147">작업 없음</span><span class="sxs-lookup"><span data-stu-id="4e840-147">No action</span></span>
    - <span data-ttu-id="4e840-148">자동 삭제</span><span class="sxs-lookup"><span data-stu-id="4e840-148">Auto-delete</span></span>
    - <span data-ttu-id="4e840-149">검토 필요(즉, 처리 검토)</span><span class="sxs-lookup"><span data-stu-id="4e840-149">Review required (aka Disposition review)</span></span>

![파일 계획의 레이블 설정](../media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="4e840-151">보존 레이블 파일 계획 설명자 열</span><span class="sxs-lookup"><span data-stu-id="4e840-151">Retention label file plan descriptors columns</span></span>

<span data-ttu-id="4e840-152">이제 보존 레이블 구성에 더 많은 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-152">You can now include more information in the configuration of your retention labels.</span></span> <span data-ttu-id="4e840-153">보존 레이블에 파일 계획 설명자를 삽입하면 파일 계획의 관리 효율성과 구성이 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-153">Inserting file plan descriptors into retention  labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="4e840-154">시작하기 위해 파일 계획 관리자에서는 직무/부서, 범주, 권한 유형 및 프로비저닝/인용에 대한 기본 제공 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-154">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation.</span></span> <span data-ttu-id="4e840-155">보존 레이블을 만들거나 편집할 때 새 파일 계획 설명자 값을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-155">You can add new file plan descriptor values when creating or editing a retention label.</span></span> <span data-ttu-id="4e840-156">파일 계획에 보존 레이블을 가져올 때 파일 계획 설명자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-156">You can also specify file plan descriptors when importing retention labels into your file plan.</span></span> 

<span data-ttu-id="4e840-157">보존 레이블을 만들거나 편집할 때의 파일 계획 설명자 단계 보기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-157">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![파일 계획 설명자](../media/file-plan-descriptors.png)

<span data-ttu-id="4e840-159">파일 계획 관리자의 **레이블** 탭에 표시되는 파일 계획 설명자 열 보기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-159">Here's a view of the file plan descriptors columns on the **Labels** tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="4e840-161">모든 기존 보존 레이블을 내보내어 오프라인 검토를 분석 및/또는 수행</span><span class="sxs-lookup"><span data-stu-id="4e840-161">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="4e840-162">파일 계획 관리자에서 모든 보존 레이블의 세부 정보를 .csv 파일로 내보내 조직의 데이터 거버넌스 이해 관계자와 함께 정기적인 검토를 편리하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-162">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="4e840-163">모든 보존 레이블의 내보내려면 **파일 계획** 페이지, **파일 계획 작업** \> **레이블 내보내기**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-163">To export all retention labels: On the **File plan** page, **File plan actions** \> **Export labels**.</span></span>

![파일 계획 내보내기 옵션](../media/file-plan-export-labels-option.png)

<span data-ttu-id="4e840-165">모든 기존 보존 레이블을 포함하는 \*.csv 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-165">A \*.csv file containing all existing retention labels will open.</span></span>

![모든 보존 레이블이 표시되는 CSV 파일](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="4e840-167">파일 계획에 보존 레이블 가져오기</span><span class="sxs-lookup"><span data-stu-id="4e840-167">Import retention labels into your file plan</span></span>

<span data-ttu-id="4e840-168">파일 계획 관리자에서 기존 보존 레이블을 수정할 수 있을 뿐만 아니라 새 보존 레이블을 대량으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-168">In the File plan manager, you can bulk import new retention labels and modify existing retention labels.</span></span>

<span data-ttu-id="4e840-169">새 보존 레이블을 가져오고 기존 보존 레이블을 수정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-169">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="4e840-170">**파일 계획** 페이지에서 **파일 계획 작업** > **레이블 가져오기**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-170">On the **File plan** page, go to **File plan actions** > **Import labels**.</span></span>

   ![파일 계획 가져오기 옵션](../media/file-plan-import-labels-option.png)

   ![빈 파일 계획 서식 파일 다운로드 옵션](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="4e840-173">새 보존 레이블을 가져오려면 빈 서식 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-173">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="4e840-174">또는 조직에서 기존 보존 레이블을 내보낼 때 내보낸 .csv 파일로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-174">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![Excel에서 빈 파일 계획 서식 파일 열기](../media/file-plan-blank-template.png)

3. <span data-ttu-id="4e840-176">서식 파일 채우기</span><span class="sxs-lookup"><span data-stu-id="4e840-176">Fill-out the template.</span></span> <span data-ttu-id="4e840-177">다음에서는 파일 계획 서식 파일의 각 속성에 대한 속성 및 유효한 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-177">The following describes the properties and valid values for each property in the file plan template.</span></span> <span data-ttu-id="4e840-178">가져오기의 경우 각 값의 길이는 최대 64자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-178">For import, each value has a maximum length of 64 characters.</span></span> <br/>

   |<span data-ttu-id="4e840-179">**속성**</span><span class="sxs-lookup"><span data-stu-id="4e840-179">**Property**</span></span>|<span data-ttu-id="4e840-180">**유형**</span><span class="sxs-lookup"><span data-stu-id="4e840-180">**Type**</span></span>|<span data-ttu-id="4e840-181">**유효한 값**</span><span class="sxs-lookup"><span data-stu-id="4e840-181">**Valid values**</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="4e840-182">LabelName</span><span class="sxs-lookup"><span data-stu-id="4e840-182">LabelName</span></span>|<span data-ttu-id="4e840-183">String</span><span class="sxs-lookup"><span data-stu-id="4e840-183">String</span></span>|<span data-ttu-id="4e840-184">이 속성은 보존 레이블의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-184">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="4e840-185">Comment</span><span class="sxs-lookup"><span data-stu-id="4e840-185">Comment</span></span>|<span data-ttu-id="4e840-186">String</span><span class="sxs-lookup"><span data-stu-id="4e840-186">String</span></span>|<span data-ttu-id="4e840-187">관리자의 보존 레이블에 대한 설명을 추가하려면 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-187">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="4e840-188">이 설명은 보안 및 준수 센터에서 레이블을 관리하는 관리자에게만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-188">This description appears only to admins who manage the label in the security and compliance center.</span></span>|
   |<span data-ttu-id="4e840-189">Notes</span><span class="sxs-lookup"><span data-stu-id="4e840-189">Notes</span></span>|<span data-ttu-id="4e840-190">String</span><span class="sxs-lookup"><span data-stu-id="4e840-190">String</span></span>|<span data-ttu-id="4e840-191">사용자의 보존 레이블에 대한 설명을 추가하려면 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-191">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="4e840-192">이 설명은 Outlook, SharePoint 및 OneDrive와 같은 앱에서 사용자가 레이블을 가리킬 때 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-192">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="4e840-193">이 속성을 비워 두면 레이블의 보존 설정을 설명하는 기본 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-193">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="4e840-194">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="4e840-194">IsRecordLabel</span></span>|<span data-ttu-id="4e840-195">String</span><span class="sxs-lookup"><span data-stu-id="4e840-195">String</span></span>|<span data-ttu-id="4e840-196">이 속성은 레이블이 레코드 레이블인지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-196">This property specifies whether the label is a record label.</span></span> <span data-ttu-id="4e840-197">레코드 레이블로 태그가 지정된 항목은 레코드로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-197">Items tagged with a record label are declared as records.</span></span> <span data-ttu-id="4e840-198">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-198">Valid values are:</span></span></br><span data-ttu-id="4e840-199">**TRUE**: 레이블이 레코드 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-199">**TRUE**: The label is a record label.</span></span> <span data-ttu-id="4e840-200">레코드로 선언된 항목은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-200">Note that items that are declared as a record can't be deleted.</span></span> </br><span data-ttu-id="4e840-201">**FALSE**: 레이블이 레코드 레이블이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-201">**FALSE**: The label isn't a record label.</span></span> <span data-ttu-id="4e840-202">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-202">This is the default value.</span></span>|
   |<span data-ttu-id="4e840-203">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="4e840-203">RetentionAction</span></span>|<span data-ttu-id="4e840-204">String</span><span class="sxs-lookup"><span data-stu-id="4e840-204">String</span></span>|<span data-ttu-id="4e840-205">이 속성은 RetentionDuration 속성에 지정된 값이 만료되는 경우 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-205">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="4e840-206">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-206">Valid values are:</span></span></br><span data-ttu-id="4e840-207">**Delete**: RetentionDuration 속성에 지정된 값보다 오래된 항목이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-207">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="4e840-208">**Keep**: RetentionDuration 속성에 지정된 기간 동안 항목을 보존하고, 해당 기간이 만료되면 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-208">**Keep**: Retain items for the duration specified by the RetentionDuration property and then doing nothing when the duration period expires.</span></span> </br><span data-ttu-id="4e840-209">**KeepAndDelete**: RetentionDuration 속성에 지정된 기간 동안 항목을 보존하고, 해당 기간이 만료되면 항목을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-209">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="4e840-210">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="4e840-210">RetentionDuration</span></span>|<span data-ttu-id="4e840-211">문자열</span><span class="sxs-lookup"><span data-stu-id="4e840-211">String</span></span>|<span data-ttu-id="4e840-212">이 속성은 콘텐츠를 보관할 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-212">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="4e840-213">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-213">Valid values are:</span></span></br><span data-ttu-id="4e840-214">**Unlimited**: 항목이 무기한 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-214">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="4e840-215">***n***: 양의 정수입니다(예: **365**).</span><span class="sxs-lookup"><span data-stu-id="4e840-215">***n***: A positive integer; for example, **365**.</span></span> 
   |<span data-ttu-id="4e840-216">RetentionType</span><span class="sxs-lookup"><span data-stu-id="4e840-216">RetentionType</span></span>|<span data-ttu-id="4e840-217">String</span><span class="sxs-lookup"><span data-stu-id="4e840-217">String</span></span>|<span data-ttu-id="4e840-218">이 속성은 콘텐츠 작성 날짜, 이벤트 날짜, 레이블이(태그가) 지정된 날짜 또는 마지막으로 수정한 날짜에서 보존 기간을 계산하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-218">This property specifies whether the retention duration is calculated from the content creation date, event date, labeled (tagged) date, or last modified date.</span></span> <span data-ttu-id="4e840-219">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-219">Valid values are:</span></span></br><span data-ttu-id="4e840-220">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4e840-220">**CreationAgeInDays**</span></span></br><span data-ttu-id="4e840-221">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4e840-221">**EventAgeInDays**</span></span></br><span data-ttu-id="4e840-222">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4e840-222">**TaggedAgeInDays**</span></span></br><span data-ttu-id="4e840-223">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4e840-223">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="4e840-224">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="4e840-224">ReviewerEmail</span></span>|<span data-ttu-id="4e840-225">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="4e840-225">SmtpAddress</span></span>|<span data-ttu-id="4e840-226">이 속성을 채울 때 보존 기간이 만료되면 처리 검토가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-226">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="4e840-227">이 속성은 **Delete**와 **KeepAndDelete** 보존 작업에 대한 검토자의 전자 메일 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-227">This property specifies the email address of a reviewer for **Delete** and **KeepAndDelete** retention actions.</span></span> <span data-ttu-id="4e840-228">개별 사용자, 배포 또는 보안 그룹의 전자 메일 주소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-228">You can include the email address of individual users, distribution, or security groups.</span></span> <span data-ttu-id="4e840-229">전자 메일 주소가 여러 개인 경우 각 주소를 세미콜론으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-229">You can specify multiple email addresses separated by semicolons.</span></span>|
   |<span data-ttu-id="4e840-230">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="4e840-230">ReferenceId</span></span>|<span data-ttu-id="4e840-231">String</span><span class="sxs-lookup"><span data-stu-id="4e840-231">String</span></span>|<span data-ttu-id="4e840-232">이 속성은 **참조 ID** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-232">This property specifies the value that's displayed in the **Reference Id** file plan descriptor.</span></span>| 
   |<span data-ttu-id="4e840-233">DepartmentName</span><span class="sxs-lookup"><span data-stu-id="4e840-233">DepartmentName</span></span>|<span data-ttu-id="4e840-234">String</span><span class="sxs-lookup"><span data-stu-id="4e840-234">String</span></span>|<span data-ttu-id="4e840-235">이 속성은 **기능/부서** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-235">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="4e840-236">Category</span><span class="sxs-lookup"><span data-stu-id="4e840-236">Category</span></span>|<span data-ttu-id="4e840-237">String</span><span class="sxs-lookup"><span data-stu-id="4e840-237">String</span></span>|<span data-ttu-id="4e840-238">이 속성은 **범주** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-238">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="4e840-239">SubCategory</span><span class="sxs-lookup"><span data-stu-id="4e840-239">SubCategory</span></span>|<span data-ttu-id="4e840-240">String</span><span class="sxs-lookup"><span data-stu-id="4e840-240">String</span></span>|<span data-ttu-id="4e840-241">이 속성은 **하위 범주** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-241">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="4e840-242">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="4e840-242">AuthorityType</span></span>|<span data-ttu-id="4e840-243">String</span><span class="sxs-lookup"><span data-stu-id="4e840-243">String</span></span>|<span data-ttu-id="4e840-244">이 속성은 **기관 유형** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-244">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="4e840-245">CitationName</span><span class="sxs-lookup"><span data-stu-id="4e840-245">CitationName</span></span>|<span data-ttu-id="4e840-246">String</span><span class="sxs-lookup"><span data-stu-id="4e840-246">String</span></span>|<span data-ttu-id="4e840-247">이 속성은 **조항/인용** 파일 계획 설명자에 표시된 인용의 이름을 지정합니다(예: "Sarbanes-Oxley Act or 2002").</span><span class="sxs-lookup"><span data-stu-id="4e840-247">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor; for example "Sarbanes-Oxley Act or 2002".</span></span> |
   |<span data-ttu-id="4e840-248">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="4e840-248">CitationUrl</span></span>|<span data-ttu-id="4e840-249">String</span><span class="sxs-lookup"><span data-stu-id="4e840-249">String</span></span>|<span data-ttu-id="4e840-250">이 속성은 **조항/인용** 파일 계획 설명자에 표시되는 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-250">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="4e840-251">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="4e840-251">CitationJurisdiction</span></span>|<span data-ttu-id="4e840-252">String</span><span class="sxs-lookup"><span data-stu-id="4e840-252">String</span></span>|<span data-ttu-id="4e840-253">이 속성은 **조항/인용** 파일 계획 설명자에 표시되는 관할지 또는 에이전시를 지정합니다(예: "미국 SEC(증권 거래 위원회").</span><span class="sxs-lookup"><span data-stu-id="4e840-253">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor; for example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="4e840-254">Regulatory</span><span class="sxs-lookup"><span data-stu-id="4e840-254">Regulatory</span></span>|<span data-ttu-id="4e840-255">String</span><span class="sxs-lookup"><span data-stu-id="4e840-255">String</span></span>|<span data-ttu-id="4e840-256">공백으로 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-256">Leave blank.</span></span> <span data-ttu-id="4e840-257">현재, 이 속성은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-257">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="4e840-258">EventType</span><span class="sxs-lookup"><span data-stu-id="4e840-258">EventType</span></span>|<span data-ttu-id="4e840-259">문자열</span><span class="sxs-lookup"><span data-stu-id="4e840-259">String</span></span>|<span data-ttu-id="4e840-260">이 속성은 레이블과 연결된 보존 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-260">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="4e840-261">규칙을 고유하게 식별하는 모든 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-261">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="4e840-262">예:</span><span class="sxs-lookup"><span data-stu-id="4e840-262">For example:</span></span></br><span data-ttu-id="4e840-263">**이름**</span><span class="sxs-lookup"><span data-stu-id="4e840-263">**Name**</span></span></br><span data-ttu-id="4e840-264">**DN(고유 이름)**</span><span class="sxs-lookup"><span data-stu-id="4e840-264">**Distinguished name (DN)**</span></span></br><span data-ttu-id="4e840-265">**GUID**</span><span class="sxs-lookup"><span data-stu-id="4e840-265">**GUID**</span></span> </br><span data-ttu-id="4e840-266">[Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet를 사용하여 사용 가능한 보존 규칙을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-266">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="4e840-267">한 조직에서 레이블을 내보낼 경우 레이블을 다른 조직으로 가져올 때 해당 조직의 EventType 속성 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-267">Note that if you export labels from one organization, you can't use the values for the EventType  property from that organization when importing labels to a different organization.</span></span> <span data-ttu-id="4e840-268">EventType 값은 조직마다 고유하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-268">That because the EventType values are unique to an organization.</span></span> |
   |||

   <span data-ttu-id="4e840-269">다음은 보존 레이블에 대한 정보가 포함된 서식 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-269">Here's an example the template containing the information about retention labels.</span></span>

   ![정보가 채워진 파일 계획 서식 파일](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="4e840-271">파일 계획 가져오기 마법사 페이지의 3단계에서 **파일 찾아보기**를 클릭하여 데이터를 입력한 서식 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-271">Under step 3 on the import file plan wizard page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="4e840-272">파일 계획 관리자에서 항목의 유효성을 검사하고 가져오기 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-272">File plan manager will validate the entries and display the import statistics.</span></span>

   ![파일 계획 가져오기 통계](../media/file-plan-import-statistics.png)

   <span data-ttu-id="4e840-274">유효성 검사 오류가 발생하면 파일 계획 가져오기가 가져오기 파일로 돌아가서 해당 오류를 손쉽게 수정할 수 있도록 계속해서 가져오기 파일의 모든 항목에 대한 유효성 검사를 수행하고 가져오기 파일의 줄/행 번호를 참조하는 모든 오류를 표시하며, 표시된 오류 결과를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-274">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easily return to the import file and correct the errors.</span></span>

5. <span data-ttu-id="4e840-275">가져오기가 완료되면 파일 계획 관리자로 돌아가서 새 보존 레이블을 새 보존 레이블 및 기존 보존 레이블 정책과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4e840-275">When the import is complete, return to file plan manager to associate the new retention labels to new or existing retention label policies.</span></span>

   ![레이블 게시 옵션](../media/file-plan-publish-labels-option.png)
