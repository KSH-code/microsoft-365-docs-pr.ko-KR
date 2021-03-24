---
title: 끝점 제거 규칙에 대한 Microsoft Defender 관리
description: 제거 규칙을 사용하여 포털에 경고가 나타나지 않도록 해야 할 수 있습니다. Microsoft Defender ATP에서 제거 규칙을 관리하는 방법을 배워야 합니다.
keywords: 제거 관리, 규칙, 규칙 이름, 범위, 작업, 경고, 켜기, 끄기
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3b65b71cc90d8e79b5de02822a12d8a44cf6c0a6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072004"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="3038b-105">제거 규칙 관리</span><span class="sxs-lookup"><span data-stu-id="3038b-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3038b-106">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3038b-106">**Applies to:**</span></span>
- [<span data-ttu-id="3038b-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3038b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3038b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3038b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3038b-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="3038b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3038b-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="3038b-111">포털에 경고가 나타나지 않을 수 있는 시나리오가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="3038b-112">조직의 알려진 도구 또는 프로세스와 같이 무해한 것으로 알려진 특정 경고에 대한 제거 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="3038b-113">경고를 표시하지는 방법에 대한 자세한 내용은 경고 표시 안 [를 참조하세요.](manage-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3038b-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="3038b-114">모든 제거 규칙의 목록을 보고 한 장소에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="3038b-115">경고 제거 규칙을 설정하거나 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="3038b-116">탐색 창에서 설정 **경고**  >  **제거 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3038b-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="3038b-117">조직의 사용자가 만든 제거 규칙 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="3038b-118">규칙 이름 옆의 확인란을 클릭하여 규칙을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="3038b-119">규칙 **켜기, 규칙 편집** 또는 규칙  **삭제를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3038b-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="3038b-120">규칙을 변경할 때 이러한 경고가 새 기준과 일치하는지 여부에 관계없이 이미 표시하지 않은 경고를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="3038b-121">제거 규칙의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="3038b-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="3038b-122">탐색 창에서 설정 **경고**  >  **제거 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3038b-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="3038b-123">조직의 사용자가 만든 제거 규칙 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="3038b-124">규칙 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-124">Click on a rule name.</span></span> <span data-ttu-id="3038b-125">규칙의 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-125">Details of the rule is displayed.</span></span> <span data-ttu-id="3038b-126">상태, 범위, 작업, 일치하는 경고 수, 생성한 경고 수, 규칙을 만든 날짜 등의 규칙 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="3038b-127">관련 경고 및 규칙 조건을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3038b-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3038b-128">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3038b-128">Related topics</span></span>

- [<span data-ttu-id="3038b-129">경고 관리</span><span class="sxs-lookup"><span data-stu-id="3038b-129">Manage alerts</span></span>](manage-alerts.md)
