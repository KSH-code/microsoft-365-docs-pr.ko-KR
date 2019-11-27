---
title: 데이터 분류 활동 탐색기 사용
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
search.appverid:
- MOE150
- MET150
description: 활동 탐색기는 사용자가 레이블이 지정된 콘텐츠에 대해 수행하는 작업을 확인하고 필터링하여 데이터 분류 기능을 자세히 설명합니다.
ms.openlocfilehash: 272de0400e89f9829b3ead5d4523db27789c0c44
ms.sourcegitcommit: 9d0a025ea9e265d515a034de0102eabcf47d11f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "39268976"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="b63ed-103">레이블이 지정된 콘텐츠의 활동 보기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="b63ed-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="b63ed-104">데이터 분류 개요 및 콘텐츠 탐색기 탭을 통해 검색된 후 레이블이 지정된 콘텐츠와 해당 콘텐츠의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="b63ed-105">활동 탐색기는 사용자가 레이블이 지정된 콘텐츠로 수행한 작업을 모니터링할 수 있도록 하여 이 기능 제품군을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="b63ed-106">활동 탐색기는 기록 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-106">Activity explorer provides a historical view.</span></span>

![자리 표시자 스크린샷 개요 활동 탐색기](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="b63ed-108">다음을 수행하여 데이터를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-108">You can filter the data by:</span></span>

- <span data-ttu-id="b63ed-109">날짜 범위</span><span class="sxs-lookup"><span data-stu-id="b63ed-109">Date range</span></span>
- <span data-ttu-id="b63ed-110">활동 유형</span><span class="sxs-lookup"><span data-stu-id="b63ed-110">Activity type</span></span>
- <span data-ttu-id="b63ed-111">위치</span><span class="sxs-lookup"><span data-stu-id="b63ed-111">Location</span></span>
- <span data-ttu-id="b63ed-112">사용자</span><span class="sxs-lookup"><span data-stu-id="b63ed-112">User</span></span>
- <span data-ttu-id="b63ed-113">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="b63ed-113">For sensitivity label usage:</span></span>
- <span data-ttu-id="b63ed-114">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="b63ed-114">For retention label usage:</span></span>


<span data-ttu-id="b63ed-115">데이터를 목록 또는 막대 그래프로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="activity-type"></a><span data-ttu-id="b63ed-116">활동 유형</span><span class="sxs-lookup"><span data-stu-id="b63ed-116">Activity type</span></span>

<span data-ttu-id="b63ed-117">Microsoft 365는 SharePoint Online, OneDrive 및 엔드포인트에서 12가지 유형의 활동을 모니터링하고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-117">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="b63ed-118">끝점은 Windows 10을 실행하는 사용자 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-118">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="b63ed-119">파일을 만들었음</span><span class="sxs-lookup"><span data-stu-id="b63ed-119">File is created</span></span>
- <span data-ttu-id="b63ed-120">파일을 수정함</span><span class="sxs-lookup"><span data-stu-id="b63ed-120">File modified</span></span>
- <span data-ttu-id="b63ed-121">파일 이름을 바꿈</span><span class="sxs-lookup"><span data-stu-id="b63ed-121">File renamed</span></span>
- <span data-ttu-id="b63ed-122">파일을 클라우드로 복사함</span><span class="sxs-lookup"><span data-stu-id="b63ed-122">File copied to cloud</span></span>
- <span data-ttu-id="b63ed-123">허용되지 않은 앱에서 파일에 액세스함</span><span class="sxs-lookup"><span data-stu-id="b63ed-123">File accessed by unallowed app</span></span>
- <span data-ttu-id="b63ed-124">파일을 인쇄함</span><span class="sxs-lookup"><span data-stu-id="b63ed-124">File printed</span></span>
- <span data-ttu-id="b63ed-125">이동식 미디어에 파일을 복사함</span><span class="sxs-lookup"><span data-stu-id="b63ed-125">File copied to removable media</span></span>
- <span data-ttu-id="b63ed-126">파일을 네트워크 공유에 복사함</span><span class="sxs-lookup"><span data-stu-id="b63ed-126">File copied to network share</span></span>
- <span data-ttu-id="b63ed-127">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="b63ed-127">File read</span></span>
- <span data-ttu-id="b63ed-128">파일을 클립보드로 복사함</span><span class="sxs-lookup"><span data-stu-id="b63ed-128">file copied to clipboard</span></span>
- <span data-ttu-id="b63ed-129">레이블을 적용함</span><span class="sxs-lookup"><span data-stu-id="b63ed-129">Label protection is applied</span></span>
- <span data-ttu-id="b63ed-130">레이블을 변경함(업그레이드, 다운그레이드 또는 제거함)</span><span class="sxs-lookup"><span data-stu-id="b63ed-130">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="b63ed-131">중요 레이블이 지정된 콘텐츠에 어떤 작업이 수행되고 있는지 파악하면 사용자가 이미 적용한 제어(예: [데이터 손실 방지 정책](data-loss-prevention-policies.md))이 유효한지를 파악할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-131">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="b63ed-132">그렇지 않고, 많은 수의 항목이 `highly confidential` 레이블이 지정되었다가 `general`로 다운그레이드되는 것과 같은 예기치 않은 상황이 발생하는 경우, 다양한 정책을 관리하고 새로운 작업을 수행하여 원치 않은 동작을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-132">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="b63ed-133">필터를 설정하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ed-133">Once your filters are set, you can:</span></span>

- <span data-ttu-id="b63ed-134">막대형 차트의 세그먼트에 마우스를 올려 놓으면 해당 범주에 속하는 항목의 수를 볼 수 있습니다. ![활동 탐색기 가리키기](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="b63ed-134">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="b63ed-135">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="b63ed-135">The variable to export  the data to.</span></span>
- <span data-ttu-id="b63ed-136">목록에서 지정된 항목을 선택하고 플라이아웃에서 작업 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="b63ed-136">select any given item from the list and view the details of the action in the fly-out</span></span>

![활동 탐색기 세부 정보 플라이아웃](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="b63ed-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b63ed-138">See also</span></span>
- [<span data-ttu-id="b63ed-139">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="b63ed-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="b63ed-140">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="b63ed-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="b63ed-141">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="b63ed-141">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="b63ed-142">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="b63ed-142">Overview of retention policies</span></span>](retention-policies.md)