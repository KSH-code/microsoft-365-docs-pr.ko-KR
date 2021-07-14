---
title: 가시성 및 인사이트에 대해 알아보기
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 가시성 및 인사이트에 대해 알아보세요.
ms.openlocfilehash: ee485c972193c515bafec55f58a7a89aa1f567f1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420259"
---
# <a name="learn-about-visibility-and-insights"></a><span data-ttu-id="54cb3-103">가시성 및 인사이트에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="54cb3-103">Learn about visibility and insights</span></span>

><span data-ttu-id="54cb3-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="54cb3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="54cb3-105">Microsoft 앱 거버넌스를 사용하면 Microsoft 365 애플리케이션 에코시스템에 대한 가시성과 의미 있는 인사이트를 빠르게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-105">With Microsoft app governance, you can quickly gain visibility and meaningful insights on your Microsoft 365 application ecosystem.</span></span> <span data-ttu-id="54cb3-106">사용자는 관리자의 주의가 필요한 테넌트에서 경고 및 앱에 대한 개략적인 요약을 제공하는 앱 거버넌스 대시보드에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-106">You start from the app governance dashboard that provides a high-level summary of the alerts and apps in your tenant that require administrator attention.</span></span>

<span data-ttu-id="54cb3-107">앱 거버넌스 가시성 및 인사이트를 통해 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-107">With app governance visibility and insights, you can see:</span></span>

- <span data-ttu-id="54cb3-108">Microsoft Graph API를 통해 Microsoft 365 데이터에 액세스하는 OAuth 사용 앱 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-108">A list of the OAuth-enabled apps that access Microsoft 365 data via Microsoft Graph APIs.</span></span>
- <span data-ttu-id="54cb3-109">반응하거나 응답하기 위한 앱 활동에 대한 풍부한 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-109">A rich view on app activities so that you can react or respond to them.</span></span>

>[!Note]
><span data-ttu-id="54cb3-110">Microsoft 365 리소스에 액세스할 수 있는 권한이 부여되지 않은 Azure 전용 앱은 앱 거버넌스에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-110">Azure-only apps that are not granted permissions to access Microsoft 365 resources are not displayed in app governance.</span></span>
>

<span data-ttu-id="54cb3-111">가시성 및 인사이트에 필요한 관리자 역할의 개요는 [관리자 역할](app-governance-get-started.md#administrator-roles)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54cb3-111">See [administrator roles](app-governance-get-started.md#administrator-roles) for an overview of required administrator roles for visibility and insights.</span></span>

<!--
From messaging doc, page 21:

View M365 App List & Metadata
View M365 App List of Consented Users
View M365 App Permissions
View M365 App Permission Usage
View Over permissioned Apps
Aggregate M365 API Usage Data by Workload (count, download/upload)
Per-App M365 API Usage Data by Workload (count, download/upload)
Per-User M365 API Usage Data by Workload (count, download/upload)
M365 API Usage Data For High-Value/Classified Assets (count, download/upload)
M365 API Error Analysis per App
-->

<span data-ttu-id="54cb3-112">앱 거버넌스를 사용하면 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-112">With app governance, you can see:</span></span>

- <span data-ttu-id="54cb3-113">모든 인사이트의 대시보드</span><span class="sxs-lookup"><span data-stu-id="54cb3-113">A dashboard of all insights.</span></span>
- <span data-ttu-id="54cb3-114">워크로드 및 사용자 수준 인사이트를 사용하여 단일 및 모든 앱에서 액세스하는 데이터</span><span class="sxs-lookup"><span data-stu-id="54cb3-114">Data accessed by single and all apps with workload and user level insights.</span></span>
- <span data-ttu-id="54cb3-115">앱 정보 및 메타데이터(예: 사용 권한, 등록 날짜 및 인증)</span><span class="sxs-lookup"><span data-stu-id="54cb3-115">App information and metadata, such as permissions, registration date, and certification.</span></span>
- <span data-ttu-id="54cb3-116">게시자 정보 및 메타데이터(예: 이름 및 확인 상태)</span><span class="sxs-lookup"><span data-stu-id="54cb3-116">Publisher information and metadata, such as name and verification status.</span></span>
- <span data-ttu-id="54cb3-117">테넌트 전체에서 상위 리소스(전자 메일 및 파일) 사용량</span><span class="sxs-lookup"><span data-stu-id="54cb3-117">Usage of top resources (emails and files) across the tenant.</span></span>
- <span data-ttu-id="54cb3-118">다음에 대한 인사이트:</span><span class="sxs-lookup"><span data-stu-id="54cb3-118">Insights on:</span></span>

  - <span data-ttu-id="54cb3-119">높은 권한이 있는 앱</span><span class="sxs-lookup"><span data-stu-id="54cb3-119">High-privileged apps.</span></span>
  - <span data-ttu-id="54cb3-120">과도한 권한이 있는 앱</span><span class="sxs-lookup"><span data-stu-id="54cb3-120">Overprivileged apps.</span></span>
  - <span data-ttu-id="54cb3-121">사용량이 높은 앱</span><span class="sxs-lookup"><span data-stu-id="54cb3-121">High-usage apps.</span></span>
  - <span data-ttu-id="54cb3-122">특정 앱에서 액세스할 수 있는 데이터에 동의한 상위 사용자</span><span class="sxs-lookup"><span data-stu-id="54cb3-122">Top consented users whose data a specific app can access.</span></span>
  - <span data-ttu-id="54cb3-123">특정 앱에서 액세스할 수 있는 데이터가 있는 우선 순위 계정</span><span class="sxs-lookup"><span data-stu-id="54cb3-123">Priority accounts who have data that a specific app can access.</span></span>

- <span data-ttu-id="54cb3-124">앱에 액세스하는 사용자의 누적 보기</span><span class="sxs-lookup"><span data-stu-id="54cb3-124">A cumulative view of users accessing apps.</span></span>
- <span data-ttu-id="54cb3-125">경고 인사이트</span><span class="sxs-lookup"><span data-stu-id="54cb3-125">Alerts insights.</span></span>
- <span data-ttu-id="54cb3-126">정책 목록 인사이트</span><span class="sxs-lookup"><span data-stu-id="54cb3-126">Policy list insights.</span></span>
<span data-ttu-id="54cb3-127"><!--></span><span class="sxs-lookup"><span data-stu-id="54cb3-127"><!--></span></span>
- <span data-ttu-id="54cb3-128">앱 거버넌스 포털의 MCAS에서 만든 정책</span><span class="sxs-lookup"><span data-stu-id="54cb3-128">Policies created in MCAS in the app governance portal.</span></span>
-->
- <span data-ttu-id="54cb3-129">앱 거버넌스 포털의 MCAS에서 생성된 OAuth 앱에 대한 경고</span><span class="sxs-lookup"><span data-stu-id="54cb3-129">Alerts for OAuth apps generated in MCAS, in the app governance portal.</span></span>

<span data-ttu-id="54cb3-130">또한 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-130">You can also:</span></span>

- <span data-ttu-id="54cb3-131">연결된 모든 인사이트를 사용하여 단일 앱(앱 페이지)으로 드릴다운합니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-131">Drill down to a single app (app page) with all its associated insights.</span></span>
- <span data-ttu-id="54cb3-132">단일 앱 내에서 데이터 및 우선 순위 계정별로 상위 사용자로 드릴다운합니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-132">Drill-down into top users by data, and priority accounts within a single app.</span></span>

## <a name="next-step"></a><span data-ttu-id="54cb3-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="54cb3-133">Next step</span></span>

[<span data-ttu-id="54cb3-134">Application Insights를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54cb3-134">Get started with application insights.</span></span>](app-governance-visibility-insights-get-started.md)
