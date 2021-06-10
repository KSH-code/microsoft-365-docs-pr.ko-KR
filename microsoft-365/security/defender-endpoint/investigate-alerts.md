---
title: 끝점 경고에 대한 Microsoft Defender 조사
description: 조사 옵션을 사용하여 네트워크에 영향을 주는 경고, 경고의 의미 및 경고를 해결하는 방법에 대한 세부 정보를 얻을 수 있습니다.
keywords: 조사, 조사, 장치, 장치, 경고 큐, 대시보드, IP 주소, 파일, 제출, 심층 분석, 타임라인, 검색, 도메인, URL, IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841093"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="82ebf-104">Microsoft Defender에서 끝점에 대한 경고 조사</span><span class="sxs-lookup"><span data-stu-id="82ebf-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82ebf-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="82ebf-105">**Applies to:**</span></span>
- [<span data-ttu-id="82ebf-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="82ebf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82ebf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82ebf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="82ebf-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="82ebf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82ebf-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="82ebf-110">네트워크에 영향을 주는 경고를 조사하고 해당 경고의 의미와 경고를 해결하는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="82ebf-111">경고 큐에서 경고를 선택하여 경고 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="82ebf-112">이 보기에는 경고 제목, 영향을 받는 자산, 세부 정보 쪽 창 및 경고 스토리가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="82ebf-113">경고 페이지에서 경고 스토리 트리 보기에서 영향을 받는 자산 또는 엔터티를 선택하여 조사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="82ebf-114">세부 정보 창에는 선택한 내용에 대한 추가 정보가 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="82ebf-115">여기에서 볼 수 있는 정보의 종류를 표시하기 위해 [끝점용 Microsoft Defender의 경고 검토를 참조하세요.](/microsoft-365/security/defender-endpoint/review-alerts)</span><span class="sxs-lookup"><span data-stu-id="82ebf-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="82ebf-116">경고 스토리를 사용하여 조사</span><span class="sxs-lookup"><span data-stu-id="82ebf-116">Investigate using the alert story</span></span>

<span data-ttu-id="82ebf-117">경고 스토리에서는 경고가 트리거된 이유, 전후에 발생된 관련 이벤트 및 기타 관련 엔터티에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="82ebf-118">엔터티는 클릭할 수 있으며 경고가 아닌 모든 엔터티는 해당 엔터티 카드 오른쪽의 확장 아이콘을 사용하여 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="82ebf-119">포커스에 있는 엔터티는 해당 엔터티 카드 왼쪽에 파란색 스트라이프로 표시되고 제목의 경고가 처음에 포커스를 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="82ebf-120">엔터티를 확장하여 세부 정보를 한눈에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="82ebf-121">엔터티를 선택하면 세부 정보 창의 컨텍스트가 이 엔터티로 전환됩니다. 그러면 추가 정보를 검토하고 해당 엔터티를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="82ebf-122">엔터티 카드 오른쪽에서 *...를* 선택하면 해당 엔터티에 사용할 수 있는 모든 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="82ebf-123">이러한 동일한 작업은 해당 엔터티가 포커스에 있는 경우 세부 정보 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="82ebf-124">경고 스토리 섹션에는 두 개 이상의 경고가 포함될 수 있습니다. 이 섹션에서는 선택한 경고 전후에 동일한 실행 트리와 관련된 추가 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![포커스가 있는 경고와 일부 확장된 카드가 있는 경고 스토리의 예](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="82ebf-126">세부 정보 창에서 작업 수행</span><span class="sxs-lookup"><span data-stu-id="82ebf-126">Take action from the details pane</span></span>

<span data-ttu-id="82ebf-127">관심 있는 엔터티를 선택하면 세부 정보 창이 변경되어 선택한 엔터티 유형, 사용 가능한 기록 정보 및 경고 페이지에서  직접 이 엔터티에 대한 작업을 수행하기 위한 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="82ebf-128">조사가 완료되면 시작한 경고로 돌아가 경고 상태를 **해결된** 것으로 표시하고 **False** 경고 또는 True 경고로 **분류합니다.**</span><span class="sxs-lookup"><span data-stu-id="82ebf-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="82ebf-129">경고를 분류하면 보다 실제 경고와 거짓 경고를 줄이기 위해 이 기능을 조정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="82ebf-130">이를 실제 경고로 분류하는 경우 아래 이미지에 표시된 같이 결정도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![해결된 경고 및 결정 드롭다운이 확장된 세부 정보 창의 스니킷](images/alert-details-resolved-true.png)

<span data-ttu-id="82ebf-132">업무용 응용 프로그램에서 거짓 경고가 발생하는 경우 향후 이러한 유형의 경고를 방지하는 제거 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ebf-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![제거 규칙이 강조 표시된 세부 정보 창의 작업 및 분류](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="82ebf-134">위에서 설명하지 않은 문제가 발생하는 경우 단추를 사용하여 피드백을 제공하거나 지원 🙂 티켓을 여십시오.</span><span class="sxs-lookup"><span data-stu-id="82ebf-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="82ebf-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="82ebf-135">Related topics</span></span>
- [<span data-ttu-id="82ebf-136">끝점 경고 큐에 대한 Microsoft Defender 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="82ebf-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="82ebf-137">끝점 경고에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="82ebf-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="82ebf-138">끝점 경고에 대한 Defender와 관련된 파일 조사</span><span class="sxs-lookup"><span data-stu-id="82ebf-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="82ebf-139">Endpoint 장치용 Defender 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="82ebf-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="82ebf-140">끝점 경고에 대한 Defender와 연결된 IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="82ebf-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="82ebf-141">끝점 경고에 대한 Defender와 연결된 도메인 조사</span><span class="sxs-lookup"><span data-stu-id="82ebf-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="82ebf-142">Defender에서 끝점에 대한 사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="82ebf-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


