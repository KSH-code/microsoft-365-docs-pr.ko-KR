---
title: 앱 컨트롤 시작
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170712"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="bce4a-103">앱 컨트롤 시작</span><span class="sxs-lookup"><span data-stu-id="bce4a-103">Get started with app control</span></span>

<span data-ttu-id="bce4a-104">사용자 환경에서 앱 컨트롤을 사용 하도록 설정 하기 전에 [Microsoft Managed Desktop이이를 구현 하는 방법](../service-description/app-control.md) 및 사용자의 역할과 책임을 검토 하 고 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="bce4a-105">Microsoft Managed Desktop은 보안 기본 정책 가져오기에 대 한 보다 까다로운 측면을 고려 하 여 앱 제어를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="bce4a-106">IT 관리자는 여전히 테스트 링에서 앱을 테스트 하 고 경고 또는 오류에 대 한 로그를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="bce4a-107">앱에 제외가 필요한 경우에는 요청을 파일 하거나 먼저 검색 한 데스크톱 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="bce4a-108">초기 앱 배포</span><span class="sxs-lookup"><span data-stu-id="bce4a-108">Initial deployment of apps</span></span>

<span data-ttu-id="bce4a-109">앱을 처음 배포할 때 Microsoft Managed Desktop은 현재 동작을 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="bce4a-110">앱 컨트롤을 사용 하도록 설정 하는 정확한 단계는 장치를 환경에 이미 배포 했는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="bce4a-111">장치가 이미 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-111">Devices already in use</span></span>

<span data-ttu-id="bce4a-112">이미 하나 이상의 Microsoft Managed Desktop 장치를 사용 하 고 있는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="bce4a-113">앱 제어권을 켜시겠습니까 Microsoft Managed Desktop 작업을 사용 하 여 서비스 티켓을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="bce4a-114">작업은 모든 장치에 [감사 정책을](../service-description/app-control.md#audit-policy) 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="bce4a-115">[응용 프로그램을 테스트](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 하 여 차단 된 프로그램이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="bce4a-116">응용 프로그램이 차단 되 면 [서명자 요청](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="bce4a-117">테스트를 완료 한 후에는 작업을 알리고 보류 중인 서명자 요청을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="bce4a-118">작업에서는 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="bce4a-119">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="bce4a-119">Deployment group</span></span>  |<span data-ttu-id="bce4a-120">정책 유형</span><span class="sxs-lookup"><span data-stu-id="bce4a-120">Policy type</span></span>  |<span data-ttu-id="bce4a-121">출시 시기</span><span class="sxs-lookup"><span data-stu-id="bce4a-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bce4a-122">테스트</span><span class="sxs-lookup"><span data-stu-id="bce4a-122">Test</span></span>     |  <span data-ttu-id="bce4a-123">감사</span><span class="sxs-lookup"><span data-stu-id="bce4a-123">Audit</span></span>       |  <span data-ttu-id="bce4a-124">일 0</span><span class="sxs-lookup"><span data-stu-id="bce4a-124">Day 0</span></span>       |
|<span data-ttu-id="bce4a-125">가장</span><span class="sxs-lookup"><span data-stu-id="bce4a-125">First</span></span>     | <span data-ttu-id="bce4a-126">Enforced</span><span class="sxs-lookup"><span data-stu-id="bce4a-126">Enforced</span></span>        | <span data-ttu-id="bce4a-127">1일</span><span class="sxs-lookup"><span data-stu-id="bce4a-127">Day 1</span></span>        |
|<span data-ttu-id="bce4a-128">신속한</span><span class="sxs-lookup"><span data-stu-id="bce4a-128">Fast</span></span>     | <span data-ttu-id="bce4a-129">Enforced</span><span class="sxs-lookup"><span data-stu-id="bce4a-129">Enforced</span></span>        |  <span data-ttu-id="bce4a-130">3일</span><span class="sxs-lookup"><span data-stu-id="bce4a-130">Day 3</span></span>       |
|<span data-ttu-id="bce4a-131">폭</span><span class="sxs-lookup"><span data-stu-id="bce4a-131">Broad</span></span>     | <span data-ttu-id="bce4a-132">Enforced</span><span class="sxs-lookup"><span data-stu-id="bce4a-132">Enforced</span></span>        |  <span data-ttu-id="bce4a-133">7일</span><span class="sxs-lookup"><span data-stu-id="bce4a-133">Day 7</span></span>       |

<span data-ttu-id="bce4a-134">롤아웃 중에 언제 든 지이 배포의 일부를 일시 중지 하거나 롤백하는 다른 서비스 요청을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="bce4a-135">아직 사용 되지 않은 장치</span><span class="sxs-lookup"><span data-stu-id="bce4a-135">Devices not yet in use</span></span>

<span data-ttu-id="bce4a-136">아직 사용 중인 장치가 없는 경우 앱 제어권을 켜시겠습니까 Microsoft Managed Desktop 작업을 사용 하 여 서비스 티켓을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="bce4a-137">작업에서는 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="bce4a-138">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="bce4a-138">Deployment group</span></span>  |<span data-ttu-id="bce4a-139">정책 유형</span><span class="sxs-lookup"><span data-stu-id="bce4a-139">Policy type</span></span>  |<span data-ttu-id="bce4a-140">출시 시기</span><span class="sxs-lookup"><span data-stu-id="bce4a-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bce4a-141">테스트</span><span class="sxs-lookup"><span data-stu-id="bce4a-141">Test</span></span>     |  <span data-ttu-id="bce4a-142">감사</span><span class="sxs-lookup"><span data-stu-id="bce4a-142">Audit</span></span>       |  <span data-ttu-id="bce4a-143">일 0</span><span class="sxs-lookup"><span data-stu-id="bce4a-143">Day 0</span></span>       |
|<span data-ttu-id="bce4a-144">가장</span><span class="sxs-lookup"><span data-stu-id="bce4a-144">First</span></span>     | <span data-ttu-id="bce4a-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="bce4a-145">Enforced</span></span>        | <span data-ttu-id="bce4a-146">1일</span><span class="sxs-lookup"><span data-stu-id="bce4a-146">Day 1</span></span>        |
|<span data-ttu-id="bce4a-147">신속한</span><span class="sxs-lookup"><span data-stu-id="bce4a-147">Fast</span></span>     | <span data-ttu-id="bce4a-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="bce4a-148">Enforced</span></span>        |  <span data-ttu-id="bce4a-149">3일</span><span class="sxs-lookup"><span data-stu-id="bce4a-149">Day 3</span></span>       |
|<span data-ttu-id="bce4a-150">폭</span><span class="sxs-lookup"><span data-stu-id="bce4a-150">Broad</span></span>     | <span data-ttu-id="bce4a-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="bce4a-151">Enforced</span></span>        |  <span data-ttu-id="bce4a-152">7일</span><span class="sxs-lookup"><span data-stu-id="bce4a-152">Day 7</span></span>       |

<span data-ttu-id="bce4a-153">롤아웃 중에 언제 든 지이 배포의 일부를 일시 중지 하거나 롤백하는 다른 서비스 요청을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce4a-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

