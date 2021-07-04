---
title: 배포 및 업데이트 채널 예제 구성
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: 예시 조직이 채널을 사용하여를 배포하고 업데이트하는 방법입니다.
ms.openlocfilehash: 8d75d9e0a546b5bfc0dd8493e9b85e7e98b41b12
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288542"
---
# <a name="deployment-and-update-channel-example-configurations"></a><span data-ttu-id="2624f-103">배포 및 업데이트 채널 예제 구성</span><span class="sxs-lookup"><span data-stu-id="2624f-103">Deployment and update channel example configurations</span></span>

<span data-ttu-id="2624f-104">Windows 10 및 Microsoft 365 앱에 사용할 업데이트 채널을 선택하는 것은 조직의 유형과 배포하려는 개발 주기에 따라 달라질 수 있으며 새로운 기능과 기능을 사용할 위치에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-104">Choosing which update channels to use for Windows 10 and Microsoft 365 Apps can depend on your type of organization and where on the development cycle you want to be deploying and using new features and capabilities.</span></span> <span data-ttu-id="2624f-105">요구 사항에 가장 잘 맞는 체험판 및 프로덕션 채널을 찾아보세요.</span><span class="sxs-lookup"><span data-stu-id="2624f-105">Find the pre-release and production channels that best fit your needs.</span></span>

## <a name="pre-release-channels"></a><span data-ttu-id="2624f-106">시험판 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-106">Pre-release channels</span></span>

<br>

****

|<span data-ttu-id="2624f-107">고객/채널 제공</span><span class="sxs-lookup"><span data-stu-id="2624f-107">Customer/Channel Offering</span></span>|<span data-ttu-id="2624f-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2624f-108">Windows 10</span></span>|<span data-ttu-id="2624f-109">엔터프라이즈용 Microsoft 365 앱(Windows 10)</span><span class="sxs-lookup"><span data-stu-id="2624f-109">Microsoft 365 Apps for Enterprise (Windows 10)</span></span>|
|:-------|:-------|:-----|
|<span data-ttu-id="2624f-110">탁월한 기술 사용자와 개발자에게 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-110">Right for highly technical users and developers.</span></span> <p> <span data-ttu-id="2624f-111">개발 주기에서 가장 먼저 최신 코드로 개발 주기의 최신 빌드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-111">Be the first to access the latest builds earliest in the development cycle with the new newest code.</span></span> <p> <span data-ttu-id="2624f-112">이 경우 대략적인 가장자리와 일부 불안정성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-112">There will be rough edges and some instability.</span></span>|<span data-ttu-id="2624f-113">Dev</span><span class="sxs-lookup"><span data-stu-id="2624f-113">Dev</span></span>|<span data-ttu-id="2624f-114">해당 없음</span><span class="sxs-lookup"><span data-stu-id="2624f-114">N/A</span></span>|
|<span data-ttu-id="2624f-115">아직 개발 중이라 신뢰할 수 있는 빌드를 원하는 초기 채택자 및 IT Pro에게 적합한 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-115">Right for early adopters and IT Pros who want more reliable builds that are still in development.</span></span> <p> <span data-ttu-id="2624f-116">다음에 나올 내용을 보고 새로운 기능을 검증하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-116">See what’s coming up next and help validate new features.</span></span>|<span data-ttu-id="2624f-117">베타 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-117">Beta Channel</span></span>|<span data-ttu-id="2624f-118">베타 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-118">Beta Channel</span></span>|
|<span data-ttu-id="2624f-119">사용자에게 예정된 릴리스에 빠르게 액세스하려는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-119">Right for those who want early access to upcoming releases.</span></span> <p> <span data-ttu-id="2624f-120">회사에서 광범위한 배포 전에 예정된 릴리스를 미리 보고 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-120">Where companies preview and validate upcoming releases before broad deployment.</span></span> <p> <span data-ttu-id="2624f-121">이 기능은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-121">These are supported.</span></span>|<span data-ttu-id="2624f-122">릴리스 미리 보기</span><span class="sxs-lookup"><span data-stu-id="2624f-122">Release Preview</span></span>|<span data-ttu-id="2624f-123">현재 채널(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2624f-123">Current Channel (Preview)</span></span> <p> <span data-ttu-id="2624f-124">반기 엔터프라이즈 채널(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2624f-124">Semi-Annual Enterprise Channel (Preview)</span></span>|
|

## <a name="production-channels-for-broad-deployment"></a><span data-ttu-id="2624f-125">광범위한 배포를 위한 프로덕션 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-125">Production channels for broad deployment</span></span>

<span data-ttu-id="2624f-126">**예제** 열에 있는 링크를 클릭하여 예제 조직을 위한 배포 단계와 그룹을 단계적으로 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-126">Click the link in the **Example** column to step through deployment stages and groups for an example organization.</span></span>

<br>

****

|<span data-ttu-id="2624f-127">고객/채널 제공</span><span class="sxs-lookup"><span data-stu-id="2624f-127">Customer/Channel Offering</span></span>|<span data-ttu-id="2624f-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2624f-128">Windows 10</span></span>|<span data-ttu-id="2624f-129">엔터프라이즈용 Microsoft 365 앱(Windows 10)</span><span class="sxs-lookup"><span data-stu-id="2624f-129">Microsoft 365 Apps for Enterprise (Windows 10)</span></span>|<span data-ttu-id="2624f-130">예제</span><span class="sxs-lookup"><span data-stu-id="2624f-130">Example</span></span>|
|:-------|:-------|:-----|:-------|
|<span data-ttu-id="2624f-131">최신 릴리스를 원하는 고객은 준비가 되는 즉시 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-131">Right for customers who want the latest releases as soon as they are ready.</span></span>|<span data-ttu-id="2624f-132">반기 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-132">Semi-Annual Channel</span></span>|[<span data-ttu-id="2624f-133">현재 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-133">Current Channel</span></span>](/deployoffice/overview-update-channels#current-channel-overview)|[<span data-ttu-id="2624f-134">최신 릴리스</span><span class="sxs-lookup"><span data-stu-id="2624f-134">Latest releases</span></span>](deploy-update-channels-examples-rapid-deploy.md)|
|<span data-ttu-id="2624f-135">최신 릴리스를 추가 예측 가능성이 있는 기업을 위한 권한을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-135">Right for enterprises who want the latest release with additional predictability.</span></span>|<span data-ttu-id="2624f-136">반기 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-136">Semi-Annual Channel</span></span>|[<span data-ttu-id="2624f-137">월 단위 엔터프라이즈 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-137">Monthly Enterprise Channel</span></span>](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)||
|<span data-ttu-id="2624f-138">각 업데이트 이전에 광범위한 IT 테스트를 수행해야 하는 기업에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2624f-138">Right for enterprises with need for extensive IT testing before each update.</span></span>|<span data-ttu-id="2624f-139">반기 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-139">Semi-Annual Channel</span></span>|[<span data-ttu-id="2624f-140">반기 엔터프라이즈 채널</span><span class="sxs-lookup"><span data-stu-id="2624f-140">Semi-Annual Enterprise Channel</span></span>](/deployoffice/overview-update-channels#semi-annual-enterprise-channel-overview)||
|

## <a name="see-also"></a><span data-ttu-id="2624f-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2624f-141">See also</span></span>

[<span data-ttu-id="2624f-142">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="2624f-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2624f-143">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="2624f-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)