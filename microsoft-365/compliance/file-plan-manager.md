---
title: 파일 계획을 사용하여 컨텐츠 라이프사이클 전체에 걸쳐 보존 레이블 관리
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
description: 파일 계획은 보존 라벨에 대한 고급 관리 기능을 제공한다.
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 422a76db5705e80c67803b798275e1faedd1d7aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906878"
---
# <a name="use-file-plan-to-manage-retention-labels"></a><span data-ttu-id="f5b2d-103">파일 계획을 사용하여 보존 레이블 관리</span><span class="sxs-lookup"><span data-stu-id="f5b2d-103">Use file plan to manage retention labels</span></span>

><span data-ttu-id="f5b2d-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="f5b2d-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="f5b2d-105">Microsoft 365 규정 준수 센터의 **정보 거버넌스** 에서 보존 레이블을 생성하고 관리할 수 있지만 **관리 기록** 의 파일 계획에는 추가적인 관리 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-105">Although you can create and manage retention labels from **Information governance** in the Microsoft 365 compliance center, file plan from **Records management** has additional management capabilities:</span></span>

- <span data-ttu-id="f5b2d-106">스프레드시트에서 관련 정보를 가져와 보존 레이블을 대량 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-106">You can bulk-create retention labels by importing the relevant information from a spreadsheet.</span></span>

- <span data-ttu-id="f5b2d-107">분석 및 오프라인 공동작업 또는 대량 편집을 위해 기존 보존 레이블에서 정보를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-107">You can export the information from existing retention labels for analysis and offline collaboration, or for bulk-editing.</span></span>

- <span data-ttu-id="f5b2d-108">보존 레이블에 대한 자세한 정보가 표시되므로 한 뷰에서 모든 보존 레이블 설정을 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-108">More information about the retention labels is displayed to make it easier to see into and across the settings of all your retention labels from one view.</span></span>

- <span data-ttu-id="f5b2d-109">파일 계획 설명자는 각 레이블에 대한 추가 및 선택적 정보를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-109">File plan descriptors support additional and optional information for each label.</span></span>

<span data-ttu-id="f5b2d-110">내용을 레코드로 표시하지 않더라도 모든 보존 레이블에 파일 계획을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-110">File plan can be used for all retention labels, even if they don't mark content as a record.</span></span>

![파일 계획 페이지](../media/compliance-file-plan.png)

<span data-ttu-id="f5b2d-112">보존 레이블의 정의와 사용 방법에 대한 자세한 내용은 [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-112">For information about what retention labels are and how to use them, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="accessing-file-plan"></a><span data-ttu-id="f5b2d-113">파일 계획 액세스</span><span class="sxs-lookup"><span data-stu-id="f5b2d-113">Accessing file plan</span></span>

<span data-ttu-id="f5b2d-114">파일 계획에 액세스하려면 다음 관리자 역할 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-114">To access file plan, you must have one of the following admin roles:</span></span>
    
- <span data-ttu-id="f5b2d-115">Retention Manager</span><span class="sxs-lookup"><span data-stu-id="f5b2d-115">Retention Manager</span></span>

- <span data-ttu-id="f5b2d-116">보기 전용 보존 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-116">View-only Retention Manager</span></span>

<span data-ttu-id="f5b2d-117">Microsoft 365 규정 준수 센터에서 **솔루션** > **레코드* 관리*\* > **파일 계획** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-117">In the Microsoft 365 compliance center, go to **Solutions** > **Records management** > **File plan**.</span></span> 

<span data-ttu-id="f5b2d-118">**관리 기록** 이 탐색 창에 표시되지 않으면 먼저 아래로 스크롤하고 **모두 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-118">If **Records management** doesn't display in the navigation pane, first scroll down, and select **Show all**.</span></span>

![파일 계획 페이지](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a><span data-ttu-id="f5b2d-120">파일 계획 탐색</span><span class="sxs-lookup"><span data-stu-id="f5b2d-120">Navigating your file plan</span></span>

<span data-ttu-id="f5b2d-121">Microsoft 365 규정 준수 센터의 **정보 거버넌스** 에서 보존 레이블을 이미 생성한 경우 이러한 레이블이 파일 계획에 자동으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-121">If you've already created retention labels from **Information governance** in the Microsoft 365 compliance center, these labels automatically display in your file plan.</span></span> 

<span data-ttu-id="f5b2d-122">마찬가지로, 파일 계획에 보존 레이블을 생성하는 경우, 레이블이 내용을 레코드로 표시하도록 구성되지 않은 경우 **정보 거버넌스** 에서도 해당 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-122">Similarly, if you now create retention labels in file plan, they are also available from **Information governance** if the labels aren't configured to mark content as a record.</span></span>

<span data-ttu-id="f5b2d-123">**파일 계획** 페이지에서 상태 및 설정이 포함된 모든 레이블, 선택적 파일 계획 설명자, 레이블의 오프라인 검토를 분석하거나 사용하도록 설정하는 내보내기 옵션, 보존 레이블을 만드는 가져오기 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-123">On the **File plan** page, you see all your labels with their status and settings, optional file plan descriptors, an export option to analyze or enable offline reviews of your labels, and an import option to create retention labels.</span></span> 

### <a name="label-settings-columns"></a><span data-ttu-id="f5b2d-124">레이블 설정 열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-124">Label settings columns</span></span>

<span data-ttu-id="f5b2d-125">**열 사용자 지정** 옵션을 선택하여 **이름** 레이블을 제외한 모든 열을 표시하거나 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-125">All columns except the label **Name** can be displayed or hidden by selecting the **Customize columns** option.</span></span> <span data-ttu-id="f5b2d-126">그러나 기본적으로 처음 몇 개의 열에는 레이블 상태 및 해당 설정에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-126">But by default, the first few columns display information about the label status and its settings:</span></span> 

- <span data-ttu-id="f5b2d-127">**상태** 는 레이블이 레이블 정책 또는 자동 적용 정책에 포함되어 있는지 여부(**활성화** 또는 **비활성화**)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-127">**Status** identifies whether the label is included in a label policy or auto-apply policy (**Active**) or not (**Inactive**).</span></span>

- <span data-ttu-id="f5b2d-128">**기준** 에 따라 보존 기간이 시작되는 방법 또는 시기를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-128">**Based on** identifies how or when the retention period begins.</span></span> <span data-ttu-id="f5b2d-129">올바른 값</span><span class="sxs-lookup"><span data-stu-id="f5b2d-129">Valid values:</span></span>
    - <span data-ttu-id="f5b2d-130">이벤트</span><span class="sxs-lookup"><span data-stu-id="f5b2d-130">Event</span></span>
    - <span data-ttu-id="f5b2d-131">만든 날짜</span><span class="sxs-lookup"><span data-stu-id="f5b2d-131">When created</span></span>
    - <span data-ttu-id="f5b2d-132">마지막으로 수정한 날짜</span><span class="sxs-lookup"><span data-stu-id="f5b2d-132">Last modified</span></span>
    - <span data-ttu-id="f5b2d-133">레이블을 지정한 날짜</span><span class="sxs-lookup"><span data-stu-id="f5b2d-133">When labeled</span></span>

- <span data-ttu-id="f5b2d-134">**현재 레코드** 는 레이블이 적용될 때 항목이 레코드로 표시되는지 여부를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-134">**Is record** identifies if the item is marked as a record when the label is applied.</span></span> <span data-ttu-id="f5b2d-135">올바른 값</span><span class="sxs-lookup"><span data-stu-id="f5b2d-135">Valid values:</span></span>
    - <span data-ttu-id="f5b2d-136">아니요</span><span class="sxs-lookup"><span data-stu-id="f5b2d-136">No</span></span>
    - <span data-ttu-id="f5b2d-137">예</span><span class="sxs-lookup"><span data-stu-id="f5b2d-137">Yes</span></span>
    - <span data-ttu-id="f5b2d-138">예(규정)</span><span class="sxs-lookup"><span data-stu-id="f5b2d-138">Yes(Regulatory)</span></span>

- <span data-ttu-id="f5b2d-139">**보존 기간** 은 보존 기간을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-139">**Retention duration** identifies the retention period.</span></span> <span data-ttu-id="f5b2d-140">올바른 값</span><span class="sxs-lookup"><span data-stu-id="f5b2d-140">Valid values:</span></span>
    - <span data-ttu-id="f5b2d-141">일</span><span class="sxs-lookup"><span data-stu-id="f5b2d-141">Days</span></span>
    - <span data-ttu-id="f5b2d-142">월</span><span class="sxs-lookup"><span data-stu-id="f5b2d-142">Months</span></span>
    - <span data-ttu-id="f5b2d-143">년 후에 삭제</span><span class="sxs-lookup"><span data-stu-id="f5b2d-143">Years</span></span>
    - <span data-ttu-id="f5b2d-144">기한 없음</span><span class="sxs-lookup"><span data-stu-id="f5b2d-144">Forever</span></span>
    - <span data-ttu-id="f5b2d-145">없음</span><span class="sxs-lookup"><span data-stu-id="f5b2d-145">None</span></span>

- <span data-ttu-id="f5b2d-146">**처리 유형** 은 보존 기간이 끝날 때 컨텐츠에 발생하는 작업을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-146">**Disposition type** identifies what happens to the content at the end of the retention period.</span></span> <span data-ttu-id="f5b2d-147">올바른 값</span><span class="sxs-lookup"><span data-stu-id="f5b2d-147">Valid values:</span></span>
    - <span data-ttu-id="f5b2d-148">작업 없음</span><span class="sxs-lookup"><span data-stu-id="f5b2d-148">No action</span></span>
    - <span data-ttu-id="f5b2d-149">자동 삭제</span><span class="sxs-lookup"><span data-stu-id="f5b2d-149">Auto-delete</span></span>
    - <span data-ttu-id="f5b2d-150">검토 필요</span><span class="sxs-lookup"><span data-stu-id="f5b2d-150">Review required</span></span>

### <a name="file-plan-descriptors-columns"></a><span data-ttu-id="f5b2d-151">파일 계획 설명자 열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-151">File plan descriptors columns</span></span>

<span data-ttu-id="f5b2d-152">파일 계획을 사용하면 더 많은 정보를 보존 레이블의 일부로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-152">File plan lets you include more information as part of your retention labels.</span></span> <span data-ttu-id="f5b2d-153">이러한 파일 계획 설명자는 레이블을 지정해야 하는 콘텐츠의 관리성 및 구성을 개선하기 위한 더 많은 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-153">These file plan descriptors provide more options to improve the manageability and organization of the content you need to label.</span></span>

<span data-ttu-id="f5b2d-154">기본적으로 **참조 ID** 로 시작하는 다음 몇 개의 열에는 보존 레이블을 생성하거나 기존 레이블을 편집할 때 지정할 수 있는 이러한 파일 계획 설명자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-154">By default, starting with **Reference ID**, the next few columns display these file plan descriptors that you can specify when you create a retention label, or edit an existing label.</span></span> 

<span data-ttu-id="f5b2d-155">시작하려면 다음 파일 계획 설명자에 대한 기본 제공 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-155">To get you started, there are some out-of-box values for the following file plan descriptors:</span></span> 
- <span data-ttu-id="f5b2d-156">업무/부서</span><span class="sxs-lookup"><span data-stu-id="f5b2d-156">Business function/department</span></span>
- <span data-ttu-id="f5b2d-157">범주</span><span class="sxs-lookup"><span data-stu-id="f5b2d-157">Category</span></span>
- <span data-ttu-id="f5b2d-158">권한 유형</span><span class="sxs-lookup"><span data-stu-id="f5b2d-158">Authority type</span></span>
- <span data-ttu-id="f5b2d-159">프로비전/인용</span><span class="sxs-lookup"><span data-stu-id="f5b2d-159">Provision/citation</span></span> 

<span data-ttu-id="f5b2d-160">보존 레이블을 만들거나 편집할 때 수행 하는 파일 계획 설명자의 예</span><span class="sxs-lookup"><span data-stu-id="f5b2d-160">Example of file plan descriptors when you create or edit a retention label:</span></span>

![보존 레이블을 만들거나 편집할 때 수행 하는 파일 계획 설명](../media/file-plan-descriptors.png)

<span data-ttu-id="f5b2d-162">파일 계획 설명자 열에 대한 예시 보기</span><span class="sxs-lookup"><span data-stu-id="f5b2d-162">Example view of the file plan descriptors columns:</span></span>

![파일 계획 설명자 열](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a><span data-ttu-id="f5b2d-164">오프라인 검토를 분석하거나 활성화하기 위해 모든 보존 레이블을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-164">Export all retention labels to analyze or enable offline reviews</span></span>

<span data-ttu-id="f5b2d-165">파일 계획에서 모든 보존 레이블의 세부 정보를 .csv 파일로 내보내 조직 내 데이터 거버넌스 이해 관계자와 정기적으로 컴플라이언스 검토를 수행할 수 있도록 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-165">From your file plan, you can export the details of all retention labels into a .csv file to help you facilitate periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="f5b2d-166">모든 보존 레이블을 내보내려면 다음을 수행합니다. **파일 계획** 페이지에서 **내보내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-166">To export all retention labels: On the **File plan** page, click **Export**:</span></span>

![파일 계획 내보내기 옵션](../media/compliance-file-plan-export-labels.png)

<span data-ttu-id="f5b2d-168">기존의 모든 보존 레이블을 포함하는 \*.csv 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-168">A \*.csv file that contains all existing retention labels opens.</span></span> <span data-ttu-id="f5b2d-169">예시:</span><span class="sxs-lookup"><span data-stu-id="f5b2d-169">For example:</span></span>

![모든 보존 레이블이 표시되는 CSV 파일](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="f5b2d-171">파일 계획에 보존 레이블 가져오기</span><span class="sxs-lookup"><span data-stu-id="f5b2d-171">Import retention labels into your file plan</span></span>

<span data-ttu-id="f5b2d-172">파일 계획에서 새 보존 레이블을 대량으로 가져오고 동일한 방법을 사용하여 기존 보존 레이블을 대량으로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-172">In file plan, you can bulk-import new retention labels, and use the same method to bulk-modify existing retention labels.</span></span>

<span data-ttu-id="f5b2d-173">새 보존 레이블을 가져오고 기존 보존 레이블을 수정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-173">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="f5b2d-174">**파일 계획** 페이지에서 **가져오기** 를 클릭하여 **파일 계획 작성 및 가져오기** 페이지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-174">On the **File plan** page, click **Import** to use the **Fill out and import your file plan** page:</span></span>

   ![파일 계획 가져오기 옵션](../media/compliance-file-plan-import-labels.png)

   ![빈 파일 계획 서식 파일 다운로드 옵션](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="f5b2d-177">새 보존 레이블을 가져오려면 빈 서식 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-177">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="f5b2d-178">또는 조직에서 기존 보존 레이블을 내보낼 때 내보낸 .csv 파일로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-178">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![빈 파일 계획 템플릿이 Excel에서 열립니다.](../media/file-plan-blank-template.png)

3. <span data-ttu-id="f5b2d-180">각 속성의 속성 및 올바른 값을 설명하는 다음 정보를 사용하여 템플릿을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-180">Fill out the template, using the following information that describes the properties and valid values for each property.</span></span> <span data-ttu-id="f5b2d-181">가져오기의 경우 일부 값에는 최대 길이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-181">For import, some values have a maximum length:</span></span>
    
    - <span data-ttu-id="f5b2d-182">**LabelName**: 최대 길이 64자</span><span class="sxs-lookup"><span data-stu-id="f5b2d-182">**LabelName**: Maximum length of 64 characters</span></span>
    - <span data-ttu-id="f5b2d-183">**설명** 및 **메모**: 최대 길이 1024자</span><span class="sxs-lookup"><span data-stu-id="f5b2d-183">**Comment** and **Notes**: Maximum length of 1024 characters</span></span>
    - <span data-ttu-id="f5b2d-184">기타 모든 값: 무제한 길이</span><span class="sxs-lookup"><span data-stu-id="f5b2d-184">All other values: Unlimited length</span></span>
    <br/>
    
   |<span data-ttu-id="f5b2d-185">속성</span><span class="sxs-lookup"><span data-stu-id="f5b2d-185">Property</span></span>|<span data-ttu-id="f5b2d-186">유형</span><span class="sxs-lookup"><span data-stu-id="f5b2d-186">Type</span></span>|<span data-ttu-id="f5b2d-187">유효한 값</span><span class="sxs-lookup"><span data-stu-id="f5b2d-187">Valid values</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="f5b2d-188">LabelName</span><span class="sxs-lookup"><span data-stu-id="f5b2d-188">LabelName</span></span>|<span data-ttu-id="f5b2d-189">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-189">String</span></span>|<span data-ttu-id="f5b2d-190">이 속성은 보존 레이블의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-190">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="f5b2d-191">Comment</span><span class="sxs-lookup"><span data-stu-id="f5b2d-191">Comment</span></span>|<span data-ttu-id="f5b2d-192">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-192">String</span></span>|<span data-ttu-id="f5b2d-193">관리자의 보존 레이블에 대한 설명을 추가하려면 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-193">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="f5b2d-194">이 설명은 규정 준수 센터에서 보존 레이블을 관리하는 관리자에게만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-194">This description appears only to admins who manage the retention label in the compliance center.</span></span>|
   |<span data-ttu-id="f5b2d-195">Notes</span><span class="sxs-lookup"><span data-stu-id="f5b2d-195">Notes</span></span>|<span data-ttu-id="f5b2d-196">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-196">String</span></span>|<span data-ttu-id="f5b2d-197">사용자의 보존 레이블에 대한 설명을 추가하려면 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-197">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="f5b2d-198">이 설명은 Outlook, SharePoint 및 OneDrive와 같은 앱에서 사용자가 레이블을 가리킬 때 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-198">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="f5b2d-199">이 속성을 비워 두면 레이블의 보존 설정을 설명하는 기본 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-199">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="f5b2d-200">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="f5b2d-200">IsRecordLabel</span></span>|<span data-ttu-id="f5b2d-201">문자열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-201">String</span></span>|<span data-ttu-id="f5b2d-202">이 속성은 레이블이 내용을 레코드로 표시할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-202">This property specifies whether the label marks the content as a record.</span></span> <span data-ttu-id="f5b2d-203">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-203">Valid values are:</span></span> </br><span data-ttu-id="f5b2d-204">**참**: 레이블에 항목을 레코드로 표시하므로 항목을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-204">**TRUE**: The label marks the item as a record and as a result, the item can't be deleted.</span></span> </br><span data-ttu-id="f5b2d-205">**거짓**: 레이블에 내용이 레코드로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-205">**FALSE**: The label doesn't mark the content as a record.</span></span> <span data-ttu-id="f5b2d-206">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-206">This is the default value.</span></span>|
   |<span data-ttu-id="f5b2d-207">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="f5b2d-207">RetentionAction</span></span>|<span data-ttu-id="f5b2d-208">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-208">String</span></span>|<span data-ttu-id="f5b2d-209">이 속성은 RetentionDuration 속성에 지정된 값이 만료되는 경우 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-209">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="f5b2d-210">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-210">Valid values are:</span></span> </br><span data-ttu-id="f5b2d-211">**Delete**: RetentionDuration 속성에 지정된 값보다 오래된 항목이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-211">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="f5b2d-212">**유지**: 보존 기간 속성에 지정된 기간 동안 항목을 보존한 다음 기간이 만료되면 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-212">**Keep**: Retain items for the duration specified by the RetentionDuration property and then do nothing when the duration period expires.</span></span> </br><span data-ttu-id="f5b2d-213">**KeepAndDelete**: RetentionDuration 속성에 지정된 기간 동안 항목을 보존하고, 해당 기간이 만료되면 항목을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-213">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="f5b2d-214">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="f5b2d-214">RetentionDuration</span></span>|<span data-ttu-id="f5b2d-215">문자열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-215">String</span></span>|<span data-ttu-id="f5b2d-216">이 속성은 콘텐츠를 보관할 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-216">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="f5b2d-217">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-217">Valid values are:</span></span> </br><span data-ttu-id="f5b2d-218">**Unlimited**: 항목이 무기한 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-218">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="f5b2d-219">\**_n_*_: 양의 정수(예: _\* 365\*\*)</span><span class="sxs-lookup"><span data-stu-id="f5b2d-219">\**_n_*_: A positive integer; for example, _\* 365\*\*.</span></span> 
   |<span data-ttu-id="f5b2d-220">RetentionType</span><span class="sxs-lookup"><span data-stu-id="f5b2d-220">RetentionType</span></span>|<span data-ttu-id="f5b2d-221">문자열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-221">String</span></span>|<span data-ttu-id="f5b2d-222">이 속성은 내용 작성 날짜, 이벤트 날짜, 레이블이 지정된 경우 또는 마지막으로 수정된 날짜로부터 보존 기간을 계산할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-222">This property specifies whether the retention duration is calculated from the content creation date, event date, when labeled date, or last modified date.</span></span> <span data-ttu-id="f5b2d-223">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-223">Valid values are:</span></span> </br><span data-ttu-id="f5b2d-224">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="f5b2d-224">**CreationAgeInDays**</span></span></br><span data-ttu-id="f5b2d-225">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="f5b2d-225">**EventAgeInDays**</span></span></br><span data-ttu-id="f5b2d-226">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="f5b2d-226">**TaggedAgeInDays**</span></span></br><span data-ttu-id="f5b2d-227">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="f5b2d-227">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="f5b2d-228">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="f5b2d-228">ReviewerEmail</span></span>|<span data-ttu-id="f5b2d-229">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="f5b2d-229">SmtpAddress</span></span>|<span data-ttu-id="f5b2d-230">이 속성을 채울 때 보존 기간이 만료되면 처리 검토가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-230">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="f5b2d-231">이 속성은 **KeepAndDelete** 보존 작업에 대한 검토자의 전자 메일 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-231">This property specifies the email address of a reviewer for the **KeepAndDelete** retention action.</span></span> <span data-ttu-id="f5b2d-232">개별 사용자, 배포 그룹 또는 보안 그룹의 전자 메일 주소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-232">You can include the email address of individual users, distribution groups, or security groups.</span></span> <span data-ttu-id="f5b2d-233">전자 메일 주소가 여러 개인 경우 각 주소를 세미콜론으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-233">You can specify multiple email addresses separated by semicolons.</span></span>|
   |<span data-ttu-id="f5b2d-234">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="f5b2d-234">ReferenceId</span></span>|<span data-ttu-id="f5b2d-235">문자열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-235">String</span></span>|<span data-ttu-id="f5b2d-236">이 속성은 조직의 고유한 값으로 사용할 수 있는 **참조 ID** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-236">This property specifies the value that's displayed in the **Reference Id** file plan descriptor, which you can use as a unique value to your organization.</span></span>| 
   |<span data-ttu-id="f5b2d-237">DepartmentName</span><span class="sxs-lookup"><span data-stu-id="f5b2d-237">DepartmentName</span></span>|<span data-ttu-id="f5b2d-238">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-238">String</span></span>|<span data-ttu-id="f5b2d-239">이 속성은 **기능/부서** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-239">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="f5b2d-240">Category</span><span class="sxs-lookup"><span data-stu-id="f5b2d-240">Category</span></span>|<span data-ttu-id="f5b2d-241">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-241">String</span></span>|<span data-ttu-id="f5b2d-242">이 속성은 **범주** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-242">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="f5b2d-243">SubCategory</span><span class="sxs-lookup"><span data-stu-id="f5b2d-243">SubCategory</span></span>|<span data-ttu-id="f5b2d-244">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-244">String</span></span>|<span data-ttu-id="f5b2d-245">이 속성은 **하위 범주** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-245">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="f5b2d-246">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="f5b2d-246">AuthorityType</span></span>|<span data-ttu-id="f5b2d-247">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-247">String</span></span>|<span data-ttu-id="f5b2d-248">이 속성은 **기관 유형** 파일 계획 설명자에 표시되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-248">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="f5b2d-249">CitationName</span><span class="sxs-lookup"><span data-stu-id="f5b2d-249">CitationName</span></span>|<span data-ttu-id="f5b2d-250">문자열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-250">String</span></span>|<span data-ttu-id="f5b2d-251">이 속성은 **프로비저닝/인용** 파일 계획 설명자에 표시되는 인용문의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-251">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="f5b2d-252">예를 들어, "2002년 Sarbanes-Oxley Act"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-252">For example, "Sarbanes-Oxley Act of 2002".</span></span> |
   |<span data-ttu-id="f5b2d-253">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="f5b2d-253">CitationUrl</span></span>|<span data-ttu-id="f5b2d-254">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-254">String</span></span>|<span data-ttu-id="f5b2d-255">이 속성은 **조항/인용** 파일 계획 설명자에 표시되는 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-255">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="f5b2d-256">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="f5b2d-256">CitationJurisdiction</span></span>|<span data-ttu-id="f5b2d-257">문자열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-257">String</span></span>|<span data-ttu-id="f5b2d-258">이 속성은 **프로비저닝/인용** 파일 계획 설명자에 표시되는 관할권 또는 기관을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-258">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="f5b2d-259">예를 들면, SEC(증권 거래 위원회)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-259">For example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="f5b2d-260">Regulatory</span><span class="sxs-lookup"><span data-stu-id="f5b2d-260">Regulatory</span></span>|<span data-ttu-id="f5b2d-261">String</span><span class="sxs-lookup"><span data-stu-id="f5b2d-261">String</span></span>|<span data-ttu-id="f5b2d-262">공백으로 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-262">Leave blank.</span></span> <span data-ttu-id="f5b2d-263">현재, 이 속성은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-263">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="f5b2d-264">EventType</span><span class="sxs-lookup"><span data-stu-id="f5b2d-264">EventType</span></span>|<span data-ttu-id="f5b2d-265">문자열</span><span class="sxs-lookup"><span data-stu-id="f5b2d-265">String</span></span>|<span data-ttu-id="f5b2d-266">이 속성은 레이블과 연결된 보존 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-266">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="f5b2d-267">규칙을 고유하게 식별하는 모든 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-267">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="f5b2d-268">예:</span><span class="sxs-lookup"><span data-stu-id="f5b2d-268">For example:</span></span></br><span data-ttu-id="f5b2d-269">**이름**</span><span class="sxs-lookup"><span data-stu-id="f5b2d-269">**Name**</span></span></br><span data-ttu-id="f5b2d-270">**DN(고유 이름)**</span><span class="sxs-lookup"><span data-stu-id="f5b2d-270">**Distinguished name (DN)**</span></span></br><span data-ttu-id="f5b2d-271">**GUID**</span><span class="sxs-lookup"><span data-stu-id="f5b2d-271">**GUID**</span></span> </br><span data-ttu-id="f5b2d-272">[Get-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancerule) cmdlet를 사용하여 사용 가능한 보존 규칙을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-272">You can use the [Get-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancerule) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="f5b2d-273">EventType 값은 조직에 고유한 값이기 때문에 한 조직에서 레이블을 내보내는 경우 해당 조직에서 EventType 속성에 대한 값을 사용하여 레이블을 다른 조직으로 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-273">Note that because the EventType values are unique to an organization, if you export labels from one organization, you can't use the values for the EventType property from that organization to import labels into a different organization.</span></span>|
   |||

   <span data-ttu-id="f5b2d-274">다음은 보존 레이블에 대한 정보를 포함하는 템플릿의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-274">Here's an example of the template containing the information about retention labels.</span></span>

   ![정보가 채워진 파일 계획 서식 파일](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="f5b2d-276">**파일 계획** 페이지의 3단계에서 **파일 찾아보기** 를 클릭하여 채워진 템플릿을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-276">Under step 3 on the **Fill out and import your file plan** page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="f5b2d-277">파일 계획에서 항목을 확인하고 가져오기 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-277">File plan validates the entries and displays the import statistics.</span></span>

   ![파일 계획 가져오기 통계](../media/file-plan-import-statistics.png)

   <span data-ttu-id="f5b2d-279">유효성 검사 오류가 있는 경우 파일 계획 가져오기는 가져오기 파일의 모든 항목의 유효성을 계속 검사하고 가져오기 파일의 행 및 행 번호를 참조하는 모든 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-279">If there's a validation error, file plan import continues to validate every entry in the import file and displays all errors  referencing the line and row numbers in the import file.</span></span> <span data-ttu-id="f5b2d-280">표시된 오류 결과를 복사하여 가져오기 파일로 돌아갈 때 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-280">Copy the displayed error results so you can correct them when you return to the import file.</span></span>

<span data-ttu-id="f5b2d-281">가져오기가 완료되면 보존 레이블을 새 보존 레이블 정책에 추가하거나 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-281">When the import is complete, you can now add the retention labels to a new retention label policy, or auto-apply them.</span></span> <span data-ttu-id="f5b2d-282">**+ 레이블 생성** 에서 드롭다운을 선택한 다음 **레이블 게시 정책** 또는 **레이블 자동 적용 정책** 을 선택하여 **파일 계획** 에서 에서 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-282">You can do this right from the **File plan** page by selecting the dropdown from **+ Create a label** and then **Policy to publish labels**, or **Policy to auto-apply a label**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5b2d-283">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f5b2d-283">Next steps</span></span>

<span data-ttu-id="f5b2d-284">보존 레이블 및 해당 정책을 만들고 편집하는 방법에 대한 자세한 내용은 다음 지침을을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5b2d-284">For more information about creating and editing retention labels and their policies, see the following guidance:</span></span>
- [<span data-ttu-id="f5b2d-285">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="f5b2d-285">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="f5b2d-286">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="f5b2d-286">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)