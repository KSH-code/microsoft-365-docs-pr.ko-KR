---
title: 활동 탐색기 시작하기
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
search.appverid:
- MOE150
- MET150
description: 활동 탐색기는 사용자가 레이블이 지정된 콘텐츠에 대해 수행하는 작업을 확인하고 필터링하여 데이터 분류 기능을 자세히 설명합니다.
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327844"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="fc888-103">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="fc888-103">Get started with activity explorer</span></span>

<span data-ttu-id="fc888-104">데이터 분류 개요 및 콘텐츠 탐색기 탭을 통해 검색된 후 레이블이 지정된 콘텐츠와 해당 콘텐츠의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="fc888-105">활동 탐색기는 사용자가 레이블이 지정된 콘텐츠로 수행한 작업을 모니터링할 수 있도록 하여 이 기능 제품군을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="fc888-106">활동 탐색기는 기록 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-106">Activity explorer provides a historical view.</span></span>

![자리 표시자 스크린샷 개요 활동 탐색기](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="fc888-108">사용할 수 있는 30개가 넘는 여러 가지 필터가 있습니다. 예를 들면:</span><span class="sxs-lookup"><span data-stu-id="fc888-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="fc888-109">날짜 범위</span><span class="sxs-lookup"><span data-stu-id="fc888-109">date range</span></span>
- <span data-ttu-id="fc888-110">활동 유형</span><span class="sxs-lookup"><span data-stu-id="fc888-110">activity type</span></span>
- <span data-ttu-id="fc888-111">위치</span><span class="sxs-lookup"><span data-stu-id="fc888-111">location</span></span>
- <span data-ttu-id="fc888-112">사용자</span><span class="sxs-lookup"><span data-stu-id="fc888-112">user</span></span>
- <span data-ttu-id="fc888-113">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="fc888-113">sensitivity label</span></span>
- <span data-ttu-id="fc888-114">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="fc888-114">retention label</span></span>
- <span data-ttu-id="fc888-115">파일 경로</span><span class="sxs-lookup"><span data-stu-id="fc888-115">file path</span></span>
- <span data-ttu-id="fc888-116">DLP 정책</span><span class="sxs-lookup"><span data-stu-id="fc888-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="fc888-117">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fc888-117">Prerequisites</span></span>

<span data-ttu-id="fc888-118">테이터 분류에 액세스하고 이를 사용하는 모든 계정에는 다음 구독 중 하나에서 할당된 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="fc888-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="fc888-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="fc888-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="fc888-120">Office 365 (E5)</span></span>
- <span data-ttu-id="fc888-121">고급 규정 준수 (E5) 추가 기능</span><span class="sxs-lookup"><span data-stu-id="fc888-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="fc888-122">고급 위협 인텔리전스 (E5) 추가 기능</span><span class="sxs-lookup"><span data-stu-id="fc888-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="fc888-123">권한</span><span class="sxs-lookup"><span data-stu-id="fc888-123">Permissions</span></span>

 <span data-ttu-id="fc888-124">활동 탐색기 탭에 액세스하려면 계정에 다음 역할이나 역할 그룹 중 하나의 구성원 자격이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="fc888-125">**Microsoft 365 역할 그룹**</span><span class="sxs-lookup"><span data-stu-id="fc888-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="fc888-126">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="fc888-126">Global administrator</span></span>
- <span data-ttu-id="fc888-127">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="fc888-127">Compliance administrator</span></span>
- <span data-ttu-id="fc888-128">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="fc888-128">Security administrator</span></span>
- <span data-ttu-id="fc888-129">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="fc888-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="fc888-130">활동 유형</span><span class="sxs-lookup"><span data-stu-id="fc888-130">Activity type</span></span>

<span data-ttu-id="fc888-131">Microsoft 365는 SharePoint Online, OneDrive에서 다음과 같은 유형의 활동을 모니터링하고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="fc888-132">레이블을 적용함</span><span class="sxs-lookup"><span data-stu-id="fc888-132">label applied</span></span>
- <span data-ttu-id="fc888-133">레이블을 변경함(업그레이드, 다운그레이드 또는 제거함)</span><span class="sxs-lookup"><span data-stu-id="fc888-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="fc888-134">자동 레이블 지정 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="fc888-134">auto-labeling simulation</span></span>

<span data-ttu-id="fc888-135">중요 레이블이 지정된 콘텐츠에 어떤 작업이 수행되고 있는지 파악하면 사용자가 이미 적용한 제어(예: [데이터 손실 방지 정책](data-loss-prevention-policies.md))이 유효한지를 파악할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="fc888-136">그렇지 않고, 많은 수의 항목이 `highly confidential` 레이블이 지정되었다가 `general`로 다운그레이드되는 것과 같은 예기치 않은 상황이 발생하는 경우, 다양한 정책을 관리하고 새로운 작업을 수행하여 원치 않은 동작을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="fc888-137">현재 활동 탐색기에서는 Exchange Online의 보존 활동을 모니터링하고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc888-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc888-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc888-138">See also</span></span>
- [<span data-ttu-id="fc888-139">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="fc888-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="fc888-140">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="fc888-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="fc888-141">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="fc888-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="fc888-142">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="fc888-142">Overview of retention policies</span></span>](retention-policies.md)
