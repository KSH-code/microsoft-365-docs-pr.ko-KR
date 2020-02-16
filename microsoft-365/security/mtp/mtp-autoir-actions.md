---
title: 자동화된 검사 후 대기 중인 작업 승인 또는 거부
description: 자동화된 조사 및 대응과 관련된 조치를 관리하는 작업 센터의 사용
keywords: 조치, 센터, 자동 공기, 자동화, 조사, 대응, 수정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: fa572e71ec5b6613e5db7751e0341ea94fb9bf5f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087545"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="6baea-104">자동화된 검사에서 대기 중인 작업 승인 또는 거부</span><span class="sxs-lookup"><span data-stu-id="6baea-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="6baea-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6baea-105">**Applies to:**</span></span>
- <span data-ttu-id="6baea-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="6baea-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6baea-107">자동화 조사가 실행되면 승인이 필요한 [수정 작업](mtp-action-center.md#remediation-actions)이 하나 이상 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-107">When an automated investigation runs, it can result in one or more [remediation actions](mtp-action-center.md#remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="6baea-108">예를 들어 전자 메일 메시지의 클러스터를 삭제 하거나 격리된 파일을 제거해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="6baea-109">자동화된 조사가 진행되고 적시에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 승인하거나 거부하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="6baea-110">Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="6baea-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="6baea-111">[Microsoft Threat Protection에서 자동 조사 및 응답 (AIR) 기능을 통해 허위 긍정/네거티브를 보고 하는 방법을](mtp-autoir-report-false-positives-negatives.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6baea-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="6baea-112">여러 방법 중 하나를 사용하여 보류 중인 작업을 검토하고 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-112">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="6baea-113">알림 센터를 이용</span><span class="sxs-lookup"><span data-stu-id="6baea-113">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- [<span data-ttu-id="6baea-114">조사 세부 정보 보기를 이용</span><span class="sxs-lookup"><span data-stu-id="6baea-114">Use the investigation details view</span></span>](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> <span data-ttu-id="6baea-115">수정 작업을 승인하거나 거부하려면 [적절한 사용 권한](mtp-action-center.md#required-permissions-for-action-center-tasks)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-115">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="6baea-116">알림 센터에서 대기 중인 작업 검토</span><span class="sxs-lookup"><span data-stu-id="6baea-116">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="6baea-117">[https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="6baea-118">탐색 창에서 **알림 센터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="6baea-119">알림 센터의 **보류 중인** 탭의 목록에서 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="6baea-120">**조사 번호** 열에서 항목을 선택하면 조사 세부 정보 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-120">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="6baea-121">거기에서 조사 결과를 보고 권장 조치를 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-121">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="6baea-122">목록에서 행을 선택하면 플라이 아웃이 열리면서 해당 항목에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-122">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![조치 승인 또는 거부](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="6baea-124">링크를 사용하여 연결 된 경고나 확인을 보고 작업을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-124">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="6baea-125">조사 세부 정보 보기에서 보류 중인 작업을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-125">Review a pending action in the investigation details view</span></span>

![조사 세부 정보](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="6baea-127">[조사 세부 정보](mtp-autoir-results.md) 페이지에서 **보류 중인 작업** (또는 **작업**) 탭을 선택합니다. 승인이 보류 중인 항목은 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-127">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="6baea-128">목록에서 항목을 선택한 다음 **승인** 또는 **거부**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6baea-128">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6baea-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6baea-129">Next steps</span></span>

- [<span data-ttu-id="6baea-130">알림 센터에 대한 자세한 정보 알아보기</span><span class="sxs-lookup"><span data-stu-id="6baea-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="6baea-131">인시던트에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6baea-131">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="6baea-132">헌팅에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="6baea-132">Learn about hunting</span></span>](advanced-hunting-overview.md)
