---
title: 앱 제어 시작하기
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430462"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="ae4ff-103">앱 제어 시작하기</span><span class="sxs-lookup"><span data-stu-id="ae4ff-103">Get started with app control</span></span>

<span data-ttu-id="ae4ff-104">환경에서 앱 컨트롤을 사용하도록 설정하기 전에 [Microsoft Managed Desktop이](../service-description/app-control.md) 앱 및 역할 및 책임을 구현하는 방법을 검토하고 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="ae4ff-105">Microsoft Managed Desktop은 보안 기본 정책을 확보하는 데 까다로워진 측면을 관리하여 앱 제어를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="ae4ff-106">IT 관리자는 테스트 링에서 앱을 계속 테스트하고 로그에서 경고 또는 오류를 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="ae4ff-107">앱에 면제가 필요한 경우 요청을 제출할 수 있습니다. 또는 Microsoft Managed Desktop Operation은 먼저 검색하는 사람에 따라 그럴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="ae4ff-108">앱의 초기 배포</span><span class="sxs-lookup"><span data-stu-id="ae4ff-108">Initial deployment of apps</span></span>

<span data-ttu-id="ae4ff-109">앱을 처음 배포할 때 Microsoft Managed Desktop은 현재 동작을 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="ae4ff-110">앱 제어를 사용하도록 설정하는 정확한 단계는 디바이스가 환경에 이미 배포되어 있는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="ae4ff-111">아직 사용되지 않는 장치</span><span class="sxs-lookup"><span data-stu-id="ae4ff-111">Devices not yet in use</span></span>

<span data-ttu-id="ae4ff-112">아직 사용 중이지 않은 디바이스가 없는 경우 앱 컨트롤을 켜야 하는 Microsoft Managed Desktop Operations가 있는 서비스 티켓을 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="ae4ff-113">작업은 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="ae4ff-114">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="ae4ff-114">Deployment group</span></span>  |<span data-ttu-id="ae4ff-115">정책 유형</span><span class="sxs-lookup"><span data-stu-id="ae4ff-115">Policy type</span></span>  |<span data-ttu-id="ae4ff-116">출시 시기</span><span class="sxs-lookup"><span data-stu-id="ae4ff-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ae4ff-117">테스트</span><span class="sxs-lookup"><span data-stu-id="ae4ff-117">Test</span></span>     |  <span data-ttu-id="ae4ff-118">감사</span><span class="sxs-lookup"><span data-stu-id="ae4ff-118">Audit</span></span>       |  <span data-ttu-id="ae4ff-119">0일</span><span class="sxs-lookup"><span data-stu-id="ae4ff-119">Day 0</span></span>       |
|<span data-ttu-id="ae4ff-120">첫 번째</span><span class="sxs-lookup"><span data-stu-id="ae4ff-120">First</span></span>     | <span data-ttu-id="ae4ff-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="ae4ff-121">Enforced</span></span>        | <span data-ttu-id="ae4ff-122">1일</span><span class="sxs-lookup"><span data-stu-id="ae4ff-122">Day 1</span></span>        |
|<span data-ttu-id="ae4ff-123">빠르기</span><span class="sxs-lookup"><span data-stu-id="ae4ff-123">Fast</span></span>     | <span data-ttu-id="ae4ff-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="ae4ff-124">Enforced</span></span>        |  <span data-ttu-id="ae4ff-125">2일</span><span class="sxs-lookup"><span data-stu-id="ae4ff-125">Day 2</span></span>       |
|<span data-ttu-id="ae4ff-126">광범위</span><span class="sxs-lookup"><span data-stu-id="ae4ff-126">Broad</span></span>     | <span data-ttu-id="ae4ff-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="ae4ff-127">Enforced</span></span>        |  <span data-ttu-id="ae4ff-128">3일</span><span class="sxs-lookup"><span data-stu-id="ae4ff-128">Day 3</span></span>       |

<span data-ttu-id="ae4ff-129">언제든지 다른 서비스 요청을 열어 이 배포의 일부를 일시 중지하거나 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="ae4ff-130">이미 사용 중인 장치</span><span class="sxs-lookup"><span data-stu-id="ae4ff-130">Devices already in use</span></span>

<span data-ttu-id="ae4ff-131">이미 하나 이상의 Microsoft Managed Desktop 장치가 사용 중이면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="ae4ff-132">앱 제어를 켜야 하는 Microsoft Managed Desktop Operations를 사용하여 서비스 티켓을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="ae4ff-133">작업에서는 감사 [정책을](../service-description/app-control.md#audit-policy) 모든 장치에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="ae4ff-134">[응용 프로그램을](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 테스트하여 차단된 응용 프로그램이 없는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="ae4ff-135">응용 프로그램이 차단된 경우 서명자 요청을 [열 수 있습니다.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)</span><span class="sxs-lookup"><span data-stu-id="ae4ff-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="ae4ff-136">테스트(결과)를 완료한 후 보류 중인 서명자 요청에 대해 알리고 Operations에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="ae4ff-137">작업은 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="ae4ff-138">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="ae4ff-138">Deployment group</span></span>  |<span data-ttu-id="ae4ff-139">정책 유형</span><span class="sxs-lookup"><span data-stu-id="ae4ff-139">Policy type</span></span>  |<span data-ttu-id="ae4ff-140">출시 시기</span><span class="sxs-lookup"><span data-stu-id="ae4ff-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ae4ff-141">테스트</span><span class="sxs-lookup"><span data-stu-id="ae4ff-141">Test</span></span>     |  <span data-ttu-id="ae4ff-142">감사</span><span class="sxs-lookup"><span data-stu-id="ae4ff-142">Audit</span></span>       |  <span data-ttu-id="ae4ff-143">0일</span><span class="sxs-lookup"><span data-stu-id="ae4ff-143">Day 0</span></span>       |
|<span data-ttu-id="ae4ff-144">첫 번째</span><span class="sxs-lookup"><span data-stu-id="ae4ff-144">First</span></span>     | <span data-ttu-id="ae4ff-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="ae4ff-145">Enforced</span></span>        | <span data-ttu-id="ae4ff-146">1일</span><span class="sxs-lookup"><span data-stu-id="ae4ff-146">Day 1</span></span>        |
|<span data-ttu-id="ae4ff-147">빠르기</span><span class="sxs-lookup"><span data-stu-id="ae4ff-147">Fast</span></span>     | <span data-ttu-id="ae4ff-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="ae4ff-148">Enforced</span></span>        |  <span data-ttu-id="ae4ff-149">일시 중지, 요청 시 롤아웃</span><span class="sxs-lookup"><span data-stu-id="ae4ff-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="ae4ff-150">광범위</span><span class="sxs-lookup"><span data-stu-id="ae4ff-150">Broad</span></span>     | <span data-ttu-id="ae4ff-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="ae4ff-151">Enforced</span></span>        |  <span data-ttu-id="ae4ff-152">일시 중지, 요청 시 롤아웃</span><span class="sxs-lookup"><span data-stu-id="ae4ff-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="ae4ff-153">언제든지 다른 서비스 요청을 열어 이 배포의 일부를 일시 중지하거나 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



