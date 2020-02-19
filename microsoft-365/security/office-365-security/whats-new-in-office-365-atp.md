---
title: Office 365 Advanced Threat Protection의 새로운 기능
description: Office 365 ATP의 새로운 기능 및 기능을 소개 합니다.
keywords: Office 365 atp, ga, 일반적으로 사용 가능, 기능, 사용 가능, 신규의 새로운 기능
search.appverid: met150
ms.service: O365-seccomp
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 01/28/2020
ms.openlocfilehash: acb6dbf69033b97f2899738a5ca17182ac9942c6
ms.sourcegitcommit: ee18bdd08e85b1262b91c180ccf61df59c19dab2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42106851"
---
# <a name="whats-new-in-office-365-atp"></a><span data-ttu-id="40879-104">Office 365 ATP의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="40879-104">What's new in Office 365 ATP</span></span>

<span data-ttu-id="40879-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="40879-105">**Applies to:**</span></span>

- [<span data-ttu-id="40879-106">Office 365 Advanced Threat Protection (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="40879-106">Office 365 Advanced Threat Protection (Office 365 ATP)</span></span>](office-365-atp.md)

<span data-ttu-id="40879-107">이 문서에서는 최신 Office 365 ATP 버전의 새로운 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="40879-107">This article lists new features in the latest release of Office 365 ATP.</span></span> <span data-ttu-id="40879-108">현재 미리 보기 상태인 기능은 **(미리 보기)** 로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40879-108">Features that are currently in preview are denoted with **(preview)**.</span></span>

> [!TIP]
> <span data-ttu-id="40879-109">아직 Office 365 ATP가 없습니까?</span><span class="sxs-lookup"><span data-stu-id="40879-109">Don't have Office 365 ATP yet?</span></span> <span data-ttu-id="40879-110">[영업 담당자에 게 문의 하 여 평가판을 시작](https://go.microsoft.com/fwlink/p/?LinkId=518644)합니다.</span><span class="sxs-lookup"><span data-stu-id="40879-110">[Contact sales to start a trial](https://go.microsoft.com/fwlink/p/?LinkId=518644).</span></span>

## <a name="januaryfebruary-2020"></a><span data-ttu-id="40879-111">1 월/2 월 2020 일</span><span class="sxs-lookup"><span data-stu-id="40879-111">January/February 2020</span></span>

- <span data-ttu-id="40879-112">보안 운영 팀이 [전자 메일을 조사](investigate-malicious-email-that-was-delivered.md)하는 동안 여러 필드를 검색 및 필터링 할 수 있도록 [위협 탐색기](threat-explorer.md) 가 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40879-112">Enhancements to [Threat Explorer](threat-explorer.md) to enable security operations teams to search and filter on multiple fields while [investigating email](investigate-malicious-email-that-was-delivered.md):</span></span>
    - <span data-ttu-id="40879-113">배달 위치 및 특수 작업</span><span class="sxs-lookup"><span data-stu-id="40879-113">Delivery location and special actions</span></span>
    - <span data-ttu-id="40879-114">방향성 (인바운드, 아웃 바운드 또는 조직 내)</span><span class="sxs-lookup"><span data-stu-id="40879-114">Directionality (inbound, outbound, or intra-org)</span></span>
    - <span data-ttu-id="40879-115">재정의 (사용자 차단 또는 허용)</span><span class="sxs-lookup"><span data-stu-id="40879-115">Overrides (user blocking or allowing)</span></span>
    - <span data-ttu-id="40879-116">URL 위협 (맬웨어, 피싱, 스팸 또는 없음)</span><span class="sxs-lookup"><span data-stu-id="40879-116">URL threat (malware, phish, spam, or none)</span></span>
    - <span data-ttu-id="40879-117">고급 필터 (포함 하지 않는 고급 필터링 옵션, 포함 하지 않음 등)</span><span class="sxs-lookup"><span data-stu-id="40879-117">Advanced NOT filters (these are advanced filtering options that include does not contain, does not include, etc.)</span></span>
    - <span data-ttu-id="40879-118">자세한 시간 필터 (일, 시간, 30 분)</span><span class="sxs-lookup"><span data-stu-id="40879-118">Granular time filters (day, hour, half-hour)</span></span> 

- <span data-ttu-id="40879-119">**문제** 위젯은 이제 **동작 센터** 위젯입니다.</span><span class="sxs-lookup"><span data-stu-id="40879-119">The **Incidents** widget is now the **Action Center** widget.</span></span> <span data-ttu-id="40879-120">보안 위젯을 보려면 Office 365 보안 & 준수 센터에서 **위협 관리** > **검토**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="40879-120">(To view your security widgets, in the Office 365 Security & Compliance Center, go to **Threat management** > **Review**.)</span></span>

## <a name="december-2019"></a><span data-ttu-id="40879-121">2019년 12월</span><span class="sxs-lookup"><span data-stu-id="40879-121">December 2019</span></span>

- <span data-ttu-id="40879-122">[URL 내보내기 오프 라인 분석을 위한 데이터 클릭](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (OFFICE 365 ATP 계획 1 또는 계획 2)</span><span class="sxs-lookup"><span data-stu-id="40879-122">[Export URL click data for offline analysis](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Office 365 ATP Plan 1 or Plan 2)</span></span>

- [<span data-ttu-id="40879-123">Office 365 ATP에서 캠페인 보기 사용 (**미리 보기**)</span><span class="sxs-lookup"><span data-stu-id="40879-123">Use Campaign Views in Office 365 ATP (**preview**)</span></span>](campaigns.md)

## <a name="november-2019"></a><span data-ttu-id="40879-124">2019년 11월</span><span class="sxs-lookup"><span data-stu-id="40879-124">November 2019</span></span>

- <span data-ttu-id="40879-125">[새로운 손상 된 사용자 검색 및 응답 기능](address-compromised-users-quickly.md) (**미리 보기**) (Office 365 ATP 계획 2)을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="40879-125">[Check out new compromised user detection and response capabilities](address-compromised-users-quickly.md) (**preview**) (Office 365 ATP Plan 2)</span></span>

## <a name="september-2019"></a><span data-ttu-id="40879-126">2019년 9월</span><span class="sxs-lookup"><span data-stu-id="40879-126">September 2019</span></span>

- <span data-ttu-id="40879-127">[Office 365의 자동화 된 조사 및 응답 기능](automated-investigation-response-office.md) 사용 (OFFICE 365 ATP 계획 2)</span><span class="sxs-lookup"><span data-stu-id="40879-127">[Employ automated investigation and response capabilities in Office 365](automated-investigation-response-office.md) (Office 365 ATP Plan 2)</span></span>

- <span data-ttu-id="40879-128">Office [365 관리 활동 API를 사용 하는 office 365 atp 자동 조사 및 응답 이벤트와 통합](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (OFFICE 365 ATP 계획 2)</span><span class="sxs-lookup"><span data-stu-id="40879-128">[Integrate with Office 365 ATP automated investigation and response events using the Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Office 365 ATP Plan 2)</span></span>

- <span data-ttu-id="40879-129">[전자 메일 머리글 보기 및 전자 메일 본문 다운로드](investigate-malicious-email-that-was-delivered.md) (OFFICE 365 ATP 계획 1 또는 계획 2)</span><span class="sxs-lookup"><span data-stu-id="40879-129">[View the email headers and download the email body](investigate-malicious-email-that-was-delivered.md) (Office 365 ATP Plan 1 or Plan 2)</span></span>

## <a name="august-2019"></a><span data-ttu-id="40879-130">2019년 8월</span><span class="sxs-lookup"><span data-stu-id="40879-130">August 2019</span></span>

- <span data-ttu-id="40879-131">[전자 메일의 시간 표시 막대 보기](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (OFFICE 365 ATP 계획 1 또는 계획 2)</span><span class="sxs-lookup"><span data-stu-id="40879-131">[View the timeline of email](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Office 365 ATP Plan 1 or Plan 2)</span></span>

## <a name="july-2019"></a><span data-ttu-id="40879-132">2019년 7월</span><span class="sxs-lookup"><span data-stu-id="40879-132">July 2019</span></span>

- <span data-ttu-id="40879-133">[배달 작업 및 전자 메일 메시지의 위치 확인](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (OFFICE 365 ATP 계획 1 또는 2)</span><span class="sxs-lookup"><span data-stu-id="40879-133">[Check the delivery action and location of email messages](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Office 365 ATP Plan 1 or 2)</span></span>

## <a name="june-2019"></a><span data-ttu-id="40879-134">2019년 6월</span><span class="sxs-lookup"><span data-stu-id="40879-134">June 2019</span></span>

- <span data-ttu-id="40879-135">[피싱 url에 대 한 데이터를 보고 결과](threat-explorer.md#view-data-about-phishing-urls-and-click-verdict) (OFFICE 365 ATP 계획 1 또는 계획 2)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="40879-135">[View data about phishing URLs and click verdict](threat-explorer.md#view-data-about-phishing-urls-and-click-verdict) (Office 365 ATP Plan 1 or Plan 2)</span></span>

## <a name="office-365-atp-plan-1-and-plan-2"></a><span data-ttu-id="40879-136">Office 365 ATP 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="40879-136">Office 365 ATP Plan 1 and Plan 2</span></span>

<span data-ttu-id="40879-137">Office 365 ATP를 두 가지 요금제로 사용할 수 있다는 사실을 알고 계십니까?</span><span class="sxs-lookup"><span data-stu-id="40879-137">Did you know that Office 365 ATP is available in two plans?</span></span> <span data-ttu-id="40879-138">[각 계획에 포함 된 내용에 대해 자세히 알아보세요](office-365-atp.md#office-365-atp-plan-1-and-plan-2).</span><span class="sxs-lookup"><span data-stu-id="40879-138">[Learn more about what each plan includes](office-365-atp.md#office-365-atp-plan-1-and-plan-2).</span></span>

## <a name="see-also"></a><span data-ttu-id="40879-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40879-139">See also</span></span>

[<span data-ttu-id="40879-140">Microsoft 365 로드맵</span><span class="sxs-lookup"><span data-stu-id="40879-140">Microsoft 365 roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap)

[<span data-ttu-id="40879-141">Office 365 ATP 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="40879-141">Office 365 ATP Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="40879-142">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="40879-142">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
