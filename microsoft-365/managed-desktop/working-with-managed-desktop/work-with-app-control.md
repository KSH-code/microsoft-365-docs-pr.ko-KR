---
title: 앱 제어 작업
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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917643"
---
# <a name="work-with-app-control"></a><span data-ttu-id="9edb6-103">앱 제어 작업</span><span class="sxs-lookup"><span data-stu-id="9edb6-103">Work with app control</span></span>

<span data-ttu-id="9edb6-104">사용자 환경에 앱 컨트롤이 배포되면 사용자와 Microsoft Managed Desktop 작업 모두 지속적인 책임을 집니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="9edb6-105">예를 들어 환경에 새 앱을 추가하거나 신뢰할 수 있는 서명자(또는 제거)를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="9edb6-106">보안을 강화하기 위해 사용자에게 릴리스하기 전에 모든 앱에 코드 서명을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="9edb6-107">앱의 게시자 세부 정보에는 서명자에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="9edb6-108">새 앱 추가</span><span class="sxs-lookup"><span data-stu-id="9edb6-108">Add a new app</span></span>

<span data-ttu-id="9edb6-109">새 앱을 추가하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="9edb6-110">[Microsoft Intune에 앱을 추가합니다.](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="9edb6-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="9edb6-111">테스트 링의 모든 디바이스에 앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="9edb6-112">표준 비즈니스 프로세스에 따라 앱을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="9edb6-113">Application **and Services Logs\Microsoft\Windows\AppLocker에서** 이벤트 뷰어를 확인하여 **8003 또는 8006** 이벤트를 **찾아야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="9edb6-114">이러한 이벤트는 앱이 차단될 것 것 을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="9edb6-115">모든 앱 보관 이벤트 및 해당 의미에 대한 자세한 내용은 [AppLocker와 함께](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)이벤트 뷰어 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9edb6-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="9edb6-116">이러한 이벤트가 발견되는 경우 Microsoft Managed Desktop Operations를 사용하여 서명자 요청을 하세요.</span><span class="sxs-lookup"><span data-stu-id="9edb6-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="9edb6-117">신뢰할 수 있는 서명자 추가(또는 제거)</span><span class="sxs-lookup"><span data-stu-id="9edb6-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="9edb6-118">서명자 요청을 열면 먼저 몇 가지 중요한 게시자 세부 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="9edb6-119">그런 다음 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-119">Then follow these steps:</span></span>

1. <span data-ttu-id="9edb6-120">[게시자 세부 정보를 수집합니다.](#gather-publisher-details)</span><span class="sxs-lookup"><span data-stu-id="9edb6-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="9edb6-121">Microsoft Managed Desktop Operations를 사용하여 티켓을 열어 서명자 규칙을 요청하고 다음 세부 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="9edb6-122">응용 프로그램 이름</span><span class="sxs-lookup"><span data-stu-id="9edb6-122">Application name</span></span> 
    - <span data-ttu-id="9edb6-123">응용 프로그램 버전</span><span class="sxs-lookup"><span data-stu-id="9edb6-123">Application version</span></span> 
    - <span data-ttu-id="9edb6-124">설명</span><span class="sxs-lookup"><span data-stu-id="9edb6-124">Description</span></span> 
    - <span data-ttu-id="9edb6-125">변경 유형("추가" 또는 "제거")</span><span class="sxs-lookup"><span data-stu-id="9edb6-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="9edb6-126">게시자 세부 정보(예: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="9edb6-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="9edb6-127">앱에 대한 트러스트는 제거하려면 동일한 단계를 따르지만 변경 유형을 **설정하여** 를 *제거합니다.*</span><span class="sxs-lookup"><span data-stu-id="9edb6-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="9edb6-128">작업은 이 일정에 따라 배포 그룹에 정책을 점진적으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="9edb6-129">배포 그룹</span><span class="sxs-lookup"><span data-stu-id="9edb6-129">Deployment group</span></span>  |<span data-ttu-id="9edb6-130">정책 유형</span><span class="sxs-lookup"><span data-stu-id="9edb6-130">Policy type</span></span>  |<span data-ttu-id="9edb6-131">출시 시기</span><span class="sxs-lookup"><span data-stu-id="9edb6-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9edb6-132">테스트</span><span class="sxs-lookup"><span data-stu-id="9edb6-132">Test</span></span>     |  <span data-ttu-id="9edb6-133">감사</span><span class="sxs-lookup"><span data-stu-id="9edb6-133">Audit</span></span>       |  <span data-ttu-id="9edb6-134">0일</span><span class="sxs-lookup"><span data-stu-id="9edb6-134">Day 0</span></span>       |
|<span data-ttu-id="9edb6-135">첫 번째</span><span class="sxs-lookup"><span data-stu-id="9edb6-135">First</span></span>     | <span data-ttu-id="9edb6-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="9edb6-136">Enforced</span></span>        | <span data-ttu-id="9edb6-137">1일</span><span class="sxs-lookup"><span data-stu-id="9edb6-137">Day 1</span></span>        |
|<span data-ttu-id="9edb6-138">빠르기</span><span class="sxs-lookup"><span data-stu-id="9edb6-138">Fast</span></span>     | <span data-ttu-id="9edb6-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="9edb6-139">Enforced</span></span>        |  <span data-ttu-id="9edb6-140">2일</span><span class="sxs-lookup"><span data-stu-id="9edb6-140">Day 2</span></span>       |
|<span data-ttu-id="9edb6-141">광범위</span><span class="sxs-lookup"><span data-stu-id="9edb6-141">Broad</span></span>     | <span data-ttu-id="9edb6-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="9edb6-142">Enforced</span></span>        |  <span data-ttu-id="9edb6-143">3일</span><span class="sxs-lookup"><span data-stu-id="9edb6-143">Day 3</span></span>       |


<span data-ttu-id="9edb6-144">배포 중에는 배포를 일시 중지하거나 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="9edb6-145">이 작업을 수행하기 위해 Operations를 통해 다른 서비스 요청을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="9edb6-146">서명자 규칙 릴리스를 일시 중지하는 경우 다른 출시를 시작하기 전에 해당 규칙을 롤백하거나 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="9edb6-147">게시자 세부 정보 수집</span><span class="sxs-lookup"><span data-stu-id="9edb6-147">Gather publisher details</span></span>

<span data-ttu-id="9edb6-148">앱의 게시자 데이터에 액세스하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="9edb6-149">감사 모드 정책이 적용된 테스트 링에서 Microsoft Managed Desktop 장치를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="9edb6-150">디바이스에 앱을 설치하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="9edb6-151">디바이스에서 이벤트 뷰어를 니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="9edb6-152">이벤트 뷰어에서 응용 프로그램 및 서비스 **로그\Microsoft\Windows로** 이동한 다음 **AppLocker 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9edb6-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="9edb6-153">**8003** 또는 **8006 이벤트를 찾은** 다음 이벤트에서 정보를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9edb6-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="9edb6-154">응용 프로그램 이름</span><span class="sxs-lookup"><span data-stu-id="9edb6-154">Application name</span></span> 
    - <span data-ttu-id="9edb6-155">응용 프로그램 버전</span><span class="sxs-lookup"><span data-stu-id="9edb6-155">Application version</span></span> 
    - <span data-ttu-id="9edb6-156">설명</span><span class="sxs-lookup"><span data-stu-id="9edb6-156">Description</span></span> 
    - <span data-ttu-id="9edb6-157">게시자 세부 정보(예: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="9edb6-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>