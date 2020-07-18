---
title: 앱 컨트롤 사용
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
ms.openlocfilehash: 74cd1ec93058ed733e7d79da2d6932f04acfa5da
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170717"
---
# <a name="work-with-app-control"></a><span data-ttu-id="dc441-103">앱 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="dc441-103">Work with app control</span></span>

<span data-ttu-id="dc441-104">응용 프로그램 제어가 환경에 배포 되 면 사용자와 Microsoft의 관리 되는 데스크톱 작업에 모두 지속적인 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="dc441-105">예를 들어 환경에서 새 앱을 추가 하거나 신뢰할 수 있는 서명자를 추가 (또는 제거) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="dc441-106">보안을 향상 시키기 위해 모든 앱은 최종 사용자에 게 릴리스하기 전에 코드 서명 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-106">To improve security, all apps should be code-signed before you release them to end users.</span></span> <span data-ttu-id="dc441-107">앱의 게시자 세부 정보에는 서명자에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="dc441-108">새 앱 추가</span><span class="sxs-lookup"><span data-stu-id="dc441-108">Add a new app</span></span>

<span data-ttu-id="dc441-109">새 앱을 추가 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="dc441-110">[Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)에 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="dc441-111">테스트 링의 모든 장치에 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="dc441-112">표준 비즈니스 프로세스에 따라 앱을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="dc441-113">**응용 프로그램 및 서비스 Logs\Microsoft\Windows\AppLocker**에서 이벤트 뷰어를 확인 하 여 **8003** 또는 **8006** 이벤트를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="dc441-114">이러한 이벤트는 앱이 차단 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="dc441-115">모든 앱 락커 이벤트와 해당 의미에 대 한 자세한 내용은 [AppLocker와 함께 이벤트 뷰어 사용](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc441-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="dc441-116">이러한 이벤트가 발견 되 면 Microsoft Managed Desktop 작업을 사용 하 여 서명자 요청을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="dc441-117">신뢰할 수 있는 서명자 추가 (또는 제거)</span><span class="sxs-lookup"><span data-stu-id="dc441-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="dc441-118">서명자 요청을 열 때 먼저 몇 가지 중요 한 게시자 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="dc441-119">그런 후 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-119">Then follow these steps:</span></span>

1. <span data-ttu-id="dc441-120">[게시자 세부 정보를 수집](#gather-publisher-details)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="dc441-121">Microsoft Managed Desktop 작업을 사용 하 여 티켓을 열어 서명자 규칙을 요청 하 고 다음 세부 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="dc441-122">응용 프로그램 이름</span><span class="sxs-lookup"><span data-stu-id="dc441-122">Application name</span></span> 
    - <span data-ttu-id="dc441-123">응용 프로그램 버전</span><span class="sxs-lookup"><span data-stu-id="dc441-123">Application version</span></span> 
    - <span data-ttu-id="dc441-124">설명</span><span class="sxs-lookup"><span data-stu-id="dc441-124">Description</span></span> 
    - <span data-ttu-id="dc441-125">변경 유형 ("추가" 또는 "제거")</span><span class="sxs-lookup"><span data-stu-id="dc441-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="dc441-126">게시자 세부 정보 (예: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="dc441-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="dc441-127">앱에 대 한 트러스트를 제거 하려면 동일한 단계를 따르고 **변경 유형을** *제거*로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="dc441-128">작업에서는 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="dc441-129">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="dc441-129">Deployment group</span></span>  |<span data-ttu-id="dc441-130">정책 유형</span><span class="sxs-lookup"><span data-stu-id="dc441-130">Policy type</span></span>  |<span data-ttu-id="dc441-131">출시 시기</span><span class="sxs-lookup"><span data-stu-id="dc441-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="dc441-132">테스트</span><span class="sxs-lookup"><span data-stu-id="dc441-132">Test</span></span>     |  <span data-ttu-id="dc441-133">감사</span><span class="sxs-lookup"><span data-stu-id="dc441-133">Audit</span></span>       |  <span data-ttu-id="dc441-134">일 0</span><span class="sxs-lookup"><span data-stu-id="dc441-134">Day 0</span></span>       |
|<span data-ttu-id="dc441-135">가장</span><span class="sxs-lookup"><span data-stu-id="dc441-135">First</span></span>     | <span data-ttu-id="dc441-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="dc441-136">Enforced</span></span>        | <span data-ttu-id="dc441-137">1일</span><span class="sxs-lookup"><span data-stu-id="dc441-137">Day 1</span></span>        |
|<span data-ttu-id="dc441-138">신속한</span><span class="sxs-lookup"><span data-stu-id="dc441-138">Fast</span></span>     | <span data-ttu-id="dc441-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="dc441-139">Enforced</span></span>        |  <span data-ttu-id="dc441-140">3일</span><span class="sxs-lookup"><span data-stu-id="dc441-140">Day 3</span></span>       |
|<span data-ttu-id="dc441-141">폭</span><span class="sxs-lookup"><span data-stu-id="dc441-141">Broad</span></span>     | <span data-ttu-id="dc441-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="dc441-142">Enforced</span></span>        |  <span data-ttu-id="dc441-143">7일</span><span class="sxs-lookup"><span data-stu-id="dc441-143">Day 7</span></span>       |


<span data-ttu-id="dc441-144">롤아웃 중에 언제 든 지 배포를 일시 중지 하거나 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="dc441-145">이렇게 하려면 작업이 포함 된 다른 서비스 요청을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="dc441-146">서명자 규칙의 릴리스를 일시 중지 하는 경우에는 해당 규칙을 먼저 롤백하거나 완료 해야 다른 롤아웃을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="dc441-147">게시자 세부 정보 수집</span><span class="sxs-lookup"><span data-stu-id="dc441-147">Gather publisher details</span></span>

<span data-ttu-id="dc441-148">앱에 대 한 게시자 데이터에 액세스 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="dc441-149">감사 모드 정책이 적용 된 테스트 링에서 Microsoft Managed Desktop 장치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="dc441-150">장치에 앱을 설치 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="dc441-151">해당 장치에서 이벤트 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="dc441-152">이벤트 뷰어에서 **응용 프로그램 및 서비스 Logs\Microsoft\Windows**으로 이동한 다음 **AppLocker**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="dc441-153">**8003** 또는 **8006** 이벤트를 찾은 다음 이벤트에서 정보를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc441-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="dc441-154">응용 프로그램 이름</span><span class="sxs-lookup"><span data-stu-id="dc441-154">Application name</span></span> 
    - <span data-ttu-id="dc441-155">응용 프로그램 버전</span><span class="sxs-lookup"><span data-stu-id="dc441-155">Application version</span></span> 
    - <span data-ttu-id="dc441-156">설명</span><span class="sxs-lookup"><span data-stu-id="dc441-156">Description</span></span> 
    - <span data-ttu-id="dc441-157">게시자 세부 정보 (예: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="dc441-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 