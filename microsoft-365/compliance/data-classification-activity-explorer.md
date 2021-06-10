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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 활동 탐색기는 사용자가 레이블이 지정된 콘텐츠에 대해 수행하는 작업을 확인하고 필터링하여 데이터 분류 기능을 자세히 설명합니다.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114010"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="5bc6b-103">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="5bc6b-103">Get started with activity explorer</span></span>

<span data-ttu-id="5bc6b-104">데이터 [분류 개요 및](data-classification-overview.md) 콘텐츠 [탐색기](data-classification-content-explorer.md) 탭을 사용하면 검색되고 레이블이 지정되는 콘텐츠와 해당 콘텐츠의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="5bc6b-105">활동 탐색기는 사용자가 레이블이 지정된 콘텐츠로 수행한 작업을 모니터링할 수 있도록 하여 이 기능 제품군을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="5bc6b-106">활동 탐색기는 레이블이 지정한 콘텐츠에 대한 활동의 기록 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="5bc6b-107">활동 정보는 통합 감사 Microsoft 365 수집되어 활동 탐색기 UI에서 사용할 수 있도록 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![자리 표시자 스크린샷 개요 활동 탐색기](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="5bc6b-109">사용할 수 있는 30개가 넘는 여러 가지 필터가 있습니다. 예를 들면:</span><span class="sxs-lookup"><span data-stu-id="5bc6b-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="5bc6b-110">날짜 범위</span><span class="sxs-lookup"><span data-stu-id="5bc6b-110">date range</span></span>
- <span data-ttu-id="5bc6b-111">활동 유형</span><span class="sxs-lookup"><span data-stu-id="5bc6b-111">activity type</span></span>
- <span data-ttu-id="5bc6b-112">위치</span><span class="sxs-lookup"><span data-stu-id="5bc6b-112">location</span></span>
- <span data-ttu-id="5bc6b-113">사용자</span><span class="sxs-lookup"><span data-stu-id="5bc6b-113">user</span></span>
- <span data-ttu-id="5bc6b-114">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="5bc6b-114">sensitivity label</span></span>
- <span data-ttu-id="5bc6b-115">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="5bc6b-115">retention label</span></span>
- <span data-ttu-id="5bc6b-116">파일 경로</span><span class="sxs-lookup"><span data-stu-id="5bc6b-116">file path</span></span>
- <span data-ttu-id="5bc6b-117">DLP 정책</span><span class="sxs-lookup"><span data-stu-id="5bc6b-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="5bc6b-118">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5bc6b-118">Prerequisites</span></span>

<span data-ttu-id="5bc6b-119">테이터 분류에 액세스하고 이를 사용하는 모든 계정에는 다음 구독 중 하나에서 할당된 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="5bc6b-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5bc6b-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="5bc6b-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5bc6b-121">Office 365 (E5)</span></span>
- <span data-ttu-id="5bc6b-122">고급 규정 준수 (E5) 추가 기능</span><span class="sxs-lookup"><span data-stu-id="5bc6b-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="5bc6b-123">고급 위협 인텔리전스 (E5) 추가 기능</span><span class="sxs-lookup"><span data-stu-id="5bc6b-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="5bc6b-124">Microsoft 365 E5/A5 정보 보호 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="5bc6b-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="5bc6b-125">Microsoft 365 E5/A5 규정 준수</span><span class="sxs-lookup"><span data-stu-id="5bc6b-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="5bc6b-126">권한</span><span class="sxs-lookup"><span data-stu-id="5bc6b-126">Permissions</span></span>

 <span data-ttu-id="5bc6b-127">활동 탐색기 탭에 액세스하려면 계정이 이러한 역할 그룹 중 하나에서 멤버 자격을 명시적으로 할당하거나 역할을 명시적으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="5bc6b-128">**Microsoft 365 역할 그룹**</span><span class="sxs-lookup"><span data-stu-id="5bc6b-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="5bc6b-129">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="5bc6b-129">Global administrator</span></span>
- <span data-ttu-id="5bc6b-130">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="5bc6b-130">Compliance administrator</span></span>
- <span data-ttu-id="5bc6b-131">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="5bc6b-131">Security administrator</span></span>
- <span data-ttu-id="5bc6b-132">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="5bc6b-132">Compliance data administrator</span></span>

<span data-ttu-id="5bc6b-133">**Microsoft 365 역할**</span><span class="sxs-lookup"><span data-stu-id="5bc6b-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="5bc6b-134">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="5bc6b-134">Compliance administrator</span></span>
- <span data-ttu-id="5bc6b-135">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="5bc6b-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="5bc6b-136">활동 유형</span><span class="sxs-lookup"><span data-stu-id="5bc6b-136">Activity types</span></span>

<span data-ttu-id="5bc6b-137">활동 탐색기는 여러 활동 원본의 감사 로그에서 활동 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="5bc6b-138">활동 탐색기에서 사용할 수 있는 레이블 지정 활동에 대한 자세한 내용은 활동 탐색기에서 사용할 수 있는 이벤트 레이블 [지정을 참조하세요.](data-classification-activity-explorer-available-events.md)</span><span class="sxs-lookup"><span data-stu-id="5bc6b-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="5bc6b-139">**Office** 네이티브  응용 프로그램, Azure Information Protection 추가 기능, SharePoint Online, Exchange Online(민감도 레이블만 해당) 및 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="5bc6b-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-140">Some examples are:</span></span>

- <span data-ttu-id="5bc6b-141">레이블을 적용함</span><span class="sxs-lookup"><span data-stu-id="5bc6b-141">label applied</span></span>
- <span data-ttu-id="5bc6b-142">레이블을 변경함(업그레이드, 다운그레이드 또는 제거함)</span><span class="sxs-lookup"><span data-stu-id="5bc6b-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="5bc6b-143">자동 레이블 지정 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="5bc6b-143">auto-labeling simulation</span></span>
- <span data-ttu-id="5bc6b-144">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="5bc6b-144">file read</span></span> 

<span data-ttu-id="5bc6b-145">**AIP(Azure Information Protection) 스캐너 및 AIP 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="5bc6b-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="5bc6b-146">보호 적용</span><span class="sxs-lookup"><span data-stu-id="5bc6b-146">protection applied</span></span>
- <span data-ttu-id="5bc6b-147">보호가 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="5bc6b-147">protection changed</span></span>
- <span data-ttu-id="5bc6b-148">보호 제거됨</span><span class="sxs-lookup"><span data-stu-id="5bc6b-148">protection removed</span></span>
- <span data-ttu-id="5bc6b-149">검색된 파일</span><span class="sxs-lookup"><span data-stu-id="5bc6b-149">files discovered</span></span> 

<span data-ttu-id="5bc6b-150">또한 활동 탐색기는 Exchange Online, SharePoint Online, OneDrive, Teams 채팅 및 채널(미리 보기), SharePoint 폴더 및 라이브러리, Windows 10 파일 공유 및 끝점 **DLP(데이터** 손실 방지)를 통해 Windows 10 장치와 일치하는 이벤트를 수집합니다. </span><span class="sxs-lookup"><span data-stu-id="5bc6b-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="5bc6b-151">다음과 같은 Windows 10 예시가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="5bc6b-152">deletions</span><span class="sxs-lookup"><span data-stu-id="5bc6b-152">deletions</span></span>
- <span data-ttu-id="5bc6b-153">creations</span><span class="sxs-lookup"><span data-stu-id="5bc6b-153">creations</span></span>
- <span data-ttu-id="5bc6b-154">클립보드에 복사</span><span class="sxs-lookup"><span data-stu-id="5bc6b-154">copied to clipboard</span></span>
- <span data-ttu-id="5bc6b-155">수정됨</span><span class="sxs-lookup"><span data-stu-id="5bc6b-155">modified</span></span>
- <span data-ttu-id="5bc6b-156">읽기</span><span class="sxs-lookup"><span data-stu-id="5bc6b-156">read</span></span>
- <span data-ttu-id="5bc6b-157">인쇄</span><span class="sxs-lookup"><span data-stu-id="5bc6b-157">printed</span></span>
- <span data-ttu-id="5bc6b-158">이름 변경</span><span class="sxs-lookup"><span data-stu-id="5bc6b-158">renamed</span></span>
- <span data-ttu-id="5bc6b-159">네트워크 공유에 복사</span><span class="sxs-lookup"><span data-stu-id="5bc6b-159">copied to network share</span></span>
- <span data-ttu-id="5bc6b-160">허용되지 않은 앱에서 액세스</span><span class="sxs-lookup"><span data-stu-id="5bc6b-160">accessed by unallowed app</span></span> 

<span data-ttu-id="5bc6b-161">중요한 레이블이 지정되는 콘텐츠에 대해 수행되는 작업을 이해하면 데이터 손실 방지와 같이 이미 설정한 [](dlp-learn-about-dlp.md) 컨트롤이 효과적인지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="5bc6b-162">그렇지 않고, 많은 수의 항목이 `highly confidential` 레이블이 지정되었다가 `general`로 다운그레이드되는 것과 같은 예기치 않은 상황이 발생하는 경우, 다양한 정책을 관리하고 새로운 작업을 수행하여 원치 않은 동작을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="5bc6b-163">현재 활동 탐색기에서는 Exchange Online의 보존 활동을 모니터링하고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bc6b-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bc6b-164">See also</span></span>

- [<span data-ttu-id="5bc6b-165">민감도 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="5bc6b-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="5bc6b-166">보존 정책 및 보존 레이블에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="5bc6b-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="5bc6b-167">중요한 정보 유형에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="5bc6b-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="5bc6b-168">데이터 분류에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="5bc6b-168">Learn about data classification</span></span>](data-classification-overview.md)
