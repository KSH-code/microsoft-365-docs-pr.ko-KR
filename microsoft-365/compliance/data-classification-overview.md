---
title: 데이터 분류 시작하기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 데이터 분류 대시보드에서는 조직에서 검색 및 분류한 중요한 데이터의 양을 시각적으로 파악할 수 있습니다.
ms.openlocfilehash: 8f3bb2da1e7011fef334ec345a02d7facedc25fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922682"
---
# <a name="know-your-data---data-classification-overview"></a><span data-ttu-id="3f0f8-103">데이터 파악 - 데이터 분류 개요</span><span class="sxs-lookup"><span data-stu-id="3f0f8-103">Know your data - data classification overview</span></span>

<span data-ttu-id="3f0f8-104">Microsoft 365 관리자 또는 준수 관리자는 조직의 콘텐츠가 이동하는 위치를 제어하고, 위치에 관계없이 보호하고, 조직의 요구에 따라 보존 및 삭제하기 위해 콘텐츠를 평가하고 태그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according to your organizations needs.</span></span> <span data-ttu-id="3f0f8-105">이 작업은 [민감도 레이블](sensitivity-labels.md), [보존 레이블](retention.md#retention-labels) 및 중요한 정보 유형 분류를 적용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](retention.md#retention-labels), and sensitive information type classification.</span></span> <span data-ttu-id="3f0f8-106">검색, 평가 및 태그 지정을 수행하는 방법에는 여러 가지가 있지만, 결과적으로는 많은 수의 문서 및 전자 메일을 이러한 두 레이블 중 하나 또는 둘 다를 사용하여 태그를 지정하고 분류하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large number of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="3f0f8-107">보존 레이블 및 민감도 레이블을 적용한 후에는 테넌트 전체에서 레이블이 사용되는 방식과 해당 항목으로 수행 중인 작업을 확인하고자 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-107">After you apply your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="3f0f8-108">데이터 분류 페이지에는 해당 콘텐츠 본문이 표시됩니다. 특히 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="3f0f8-109">중요한 정보 유형으로 분류된 항목의 수와 사용된 분류</span><span class="sxs-lookup"><span data-stu-id="3f0f8-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="3f0f8-110">Microsoft 365 및 Azure Information Protection에서 가장 많이 적용한 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="3f0f8-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="3f0f8-111">가장 많이 적용한 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="3f0f8-111">the top applied retention labels</span></span>
- <span data-ttu-id="3f0f8-112">사용자가 중요한 콘텐츠에 대해 수행하는 활동 요약</span><span class="sxs-lookup"><span data-stu-id="3f0f8-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="3f0f8-113">중요한 데이터와 보존된 데이터의 위치</span><span class="sxs-lookup"><span data-stu-id="3f0f8-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="3f0f8-114">또한 데이터 분류 페이지에서 다음 기능을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-114">You also manage these features on the data classification page:</span></span>
- [<span data-ttu-id="3f0f8-115">학습 가능한 분류자</span><span class="sxs-lookup"><span data-stu-id="3f0f8-115">trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="3f0f8-116">중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="3f0f8-116">sensitive information types</span></span>](./sensitive-information-type-entity-definitions.md)

<span data-ttu-id="3f0f8-117">**Microsoft 365 규정 준수 센터** 또는 **Microsoft 365 보안 센터** > **분류** > **데이터 분류** 에서 데이터 분류를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-117">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

<span data-ttu-id="3f0f8-118">비디오를 시청하여 데이터 분류 기능에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-118">Take a video tour of our data classification features.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

<span data-ttu-id="3f0f8-119">정책을 만들기 전에 데이터 분류에서 중요한 콘텐츠와 레이블이 지정된 콘텐츠를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-119">Data classification will scan your sensitive content and labeled content before you create any policies.</span></span> <span data-ttu-id="3f0f8-120">이를 **제로 변경 관리** 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-120">This is called **zero change management**.</span></span> <span data-ttu-id="3f0f8-121">이를 통해 모든 보존 및 민감도 레이블이 환경에 미치는 영향을 확인하고, 보호 및 관리 정책 요구 사항을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-121">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f0f8-122">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3f0f8-122">Prerequisites</span></span>

<span data-ttu-id="3f0f8-123">다양한 구독에서 끝점 DLP를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-123">A number of different subscriptions support Endpoint DLP.</span></span> <span data-ttu-id="3f0f8-124">끝점 DLP 라이선스 옵션을 보려면 [지침에 관한 Information Protection](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-124">To see licensing options for Endpoint DLP see [Information Protection licensing for guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span> 

### <a name="permissions"></a><span data-ttu-id="3f0f8-125">권한</span><span class="sxs-lookup"><span data-stu-id="3f0f8-125">Permissions</span></span>

 <span data-ttu-id="3f0f8-126">테이터 분류 페이지에 액세스하려면 계정에 다음 역할이나 역할 그룹 중 하나의 구성원 자격이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-126">In order to get access to the data classification page, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="3f0f8-127">**Microsoft 365 역할 그룹**</span><span class="sxs-lookup"><span data-stu-id="3f0f8-127">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="3f0f8-128">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="3f0f8-128">Global administrator</span></span>
- <span data-ttu-id="3f0f8-129">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="3f0f8-129">Compliance administrator</span></span>
- <span data-ttu-id="3f0f8-130">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="3f0f8-130">Security administrator</span></span>
- <span data-ttu-id="3f0f8-131">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="3f0f8-131">Compliance data administrator</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="3f0f8-132">콘텐츠에 가장 많이 사용되는 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="3f0f8-132">Sensitive information types used most in your content</span></span>

<span data-ttu-id="3f0f8-133">Microsoft 365에는 사회 보장 번호 또는 신용 카드 번호를 포함하는 항목과 같은 중요한 정보 유형에 대한 다양한 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-133">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="3f0f8-134">중요한 정보 유형에 대한 자세한 내용은 [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-134">For more information on sensitive information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="3f0f8-135">중요한 정보 유형 카드는 조직 전체에서 검색되고 레이블이 지정된 상위 중요한 정보 유형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-135">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![상위 중요한 정보 유형](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="3f0f8-137">특정 분류 범주에 있는 항목의 수를 확인하려면 해당 범주에 대한 막대를 마우스로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-137">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![상위 중요한 정보 유형 가리키기 세부 정보](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="3f0f8-139">카드에 "중요한 정보가 포함된 데이터가 없습니다." 메시지가 표시되는 경우</span><span class="sxs-lookup"><span data-stu-id="3f0f8-139">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="3f0f8-140">조직에 중요한 정보 유형으로 분류된 항목이 없거나 크롤링된 항목이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-140">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="3f0f8-141">레이블을 시작하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-141">To get started with labels, see:</span></span>
>- [<span data-ttu-id="3f0f8-142">민감도 레이블 시작하기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-142">Get started with sensitivity labels</span></span>](get-started-with-sensitivity-labels.md)
>- [<span data-ttu-id="3f0f8-143">보존 정책 및 보존 레이블 시작하기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-143">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)
>- [<span data-ttu-id="3f0f8-144">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="3f0f8-144">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="3f0f8-145">콘텐츠에 적용되는 상위 민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="3f0f8-145">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="3f0f8-146">Microsoft 365 또는 AIP(Azure Information Protection)를 통해 항목에 민감도 레이블을 적용하면 다음과 같은 두 가지 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-146">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="3f0f8-147">조직에 항목의 값을 표시하는 태그가 문서에 포함되고, 문서가 이동할 때마다 함께 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-147">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="3f0f8-148">이 태그가 있으면 필수 워터마크 또는 암호화와 같은 다양한 보호 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-148">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="3f0f8-149">엔드포인트 보호를 사용하도록 설정한 경우 항목이 조직의 컨트롤을 벗어나지 않도록 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-149">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="3f0f8-150">민감도 레이블에 대한 자세한 내용은 [민감도 레이블 알아보기](sensitivity-labels.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-150">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="3f0f8-151">데이터 분류 페이지에서 해당 데이터를 표시하려면 SharePoint 및 OneDrive에 있는 파일에 민감도 레이블을 사용하도록 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-151">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="3f0f8-152">자세한 내용은 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-152">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="3f0f8-153">민감도 레이블 카드에는 민감도 레이블별 항목(전자 메일 또는 문서) 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-153">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![민감도 레이블 분류에 따른 콘텐츠 분석 자리 표시자 스크린샷](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="3f0f8-155">민감도 레이블을 생성 또는 게시하지 않았거나 민감도 레이블이 적용된 콘텐츠가 없는 경우 이 카드에 “검색된 민감도 레이블이 없음” 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-155">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="3f0f8-156">민감도 레이블을 시작하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-156">To get started with sensitivity labels, see:</span></span>
>- <span data-ttu-id="3f0f8-157">[민감도 레이블](get-started-with-sensitivity-labels.md) 또는 AIP [구성 Azure 정보 보호 정책](/azure/information-protection/configure-policy) 시작하기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-157">[Get started with sensitivity labels](get-started-with-sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="3f0f8-158">콘텐츠에 적용되는 상위 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="3f0f8-158">Top retention labels applied to content</span></span>

<span data-ttu-id="3f0f8-159">보존 레이블은 조직에서 콘텐츠의 보존과 처리를 관리하는데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-159">Retention labels are used to manage the retention and disposition of content in your organization.</span></span> <span data-ttu-id="3f0f8-160">적용되면 보존 기간 만료 후 삭제 전에 검토 되어야 하는지 및 기록으로 표시 되어야 하는지 여부 등 삭제 전 항목이 어떻게 저장 되는지 관리하는데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-160">When applied, they can be used to control how an item will be kept before deletion, whether it should be reviewed prior to deletion, when its retention period expires, and whether it should be marked as a record.</span></span> <span data-ttu-id="3f0f8-161">자세한 내용은 [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-161">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="3f0f8-162">적용되는 상위 보존 레이블 카드에는 보존 레이블이 지정된 항목 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-162">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![적용된 상위 보존 레이블 자리 표시자 스크린샷](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="3f0f8-164">이 카드에 “검색된 보존 레이블이 없음” 메시지가 표시되는 경우 사용자가 보존 레이블을 생성 또는 게시하지 않았거나, 보존 레이블이 적용된 콘텐츠가 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-164">If this card displays the message, "No retention labels detected", it means you haven't created or published any retention labels or no content has had a retention label applied.</span></span> <span data-ttu-id="3f0f8-165">보존 레이블을 시작하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-165">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="3f0f8-166">보존 정책 및 보존 레이블 시작하기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-166">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)

## <a name="top-activities-detected"></a><span data-ttu-id="3f0f8-167">검색된 상위 활동</span><span class="sxs-lookup"><span data-stu-id="3f0f8-167">Top activities detected</span></span>

<span data-ttu-id="3f0f8-168">이 카드는 사용자가 민감도 레이블이 지정된 항목에 대해 수행하는 가장 일반적인 작업을 빠르게 요약해서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-168">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="3f0f8-169">[활동 탐색기](data-classification-activity-explorer.md)를 사용하여 Microsoft 365에서 레이블이 지정된 콘텐츠 및 Windows 10 엔드포인트에 있는 콘텐츠에 대해 추적하는 8가지 다양한 활동을 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-169">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="3f0f8-170">이 카드에 “검색된 활동 없음" 메시지가 표시되는 경우 파일에 대한 활동이 없었거나 해당 사용자 및 관리자 감사가 켜져 있지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-170">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="3f0f8-171">감사 로그를 설정하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-171">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="3f0f8-172">보안 및 준수 센터에서 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="3f0f8-172">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="3f0f8-173">위치별 민감도 및 보존 레이블이 지정된 데이터</span><span class="sxs-lookup"><span data-stu-id="3f0f8-173">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="3f0f8-174">데이터 분류 보고 지점은 특정 레이블이 지정된 항목의 수와 해당 위치를 시각적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-174">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="3f0f8-175">이러한 카드를 사용하여 Exchange, SharePoint, OneDrive 등에 있는 레이블이 지정된 항목의 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-175">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="3f0f8-176">이 카드에 “검색된 위치가 없음” 메시지가 표시되는 경우 사용자가 민감도 레이블을 생성 또는 게시하지 않았거나, 보존 레이블이 적용된 콘텐츠가 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-176">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="3f0f8-177">민감도 레이블을 시작하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-177">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="3f0f8-178">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="3f0f8-178">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="3f0f8-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f0f8-179">See also</span></span>

- [<span data-ttu-id="3f0f8-180">레이블 활동 보기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-180">View label activity</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="3f0f8-181">레이블 지정된 콘텐츠 보기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-181">View labeled content</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="3f0f8-182">민감도 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-182">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="3f0f8-183">보존 정책 및 보존 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="3f0f8-183">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="3f0f8-184">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="3f0f8-184">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="3f0f8-185">학습 가능한 분류자에 대한 자세한 정 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="3f0f8-185">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)