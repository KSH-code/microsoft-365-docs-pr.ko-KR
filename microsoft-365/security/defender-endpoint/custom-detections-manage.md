---
title: Microsoft Defender ATP에서 사용자 지정 검색 규칙 보기 및 관리
ms.reviewer: ''
description: 사용자 지정 검색 규칙을 보고 관리하는 방법 학습
keywords: 사용자 지정 검색, 보기, 관리, 경고, 편집, 요청 시 실행, 감지 규칙, 고급 헌팅, 헌트, 쿼리, 응답 작업, mdatp, Microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498752"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="09ee5-104">사용자 지정 검색 규칙 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="09ee5-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09ee5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="09ee5-105">**Applies to:**</span></span>
- [<span data-ttu-id="09ee5-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="09ee5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="09ee5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09ee5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="09ee5-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="09ee5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="09ee5-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="09ee5-110">기존 사용자 지정 검색 [규칙을 관리하여](custom-detection-rules.md) 위협을 효과적으로 찾아 조치를 취하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="09ee5-111">규칙 목록을 보고, 이전 실행을 확인하고, 트리거한 경고를 검토하는 방법을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="09ee5-112">필요한 경우 규칙을 실행하고 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="09ee5-113">필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="09ee5-113">Required permissions</span></span>

<span data-ttu-id="09ee5-114">사용자 지정 검색을 만들거나 관리하려면 역할에 보안 설정 관리 **권한이 필요합니다.** [](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)</span><span class="sxs-lookup"><span data-stu-id="09ee5-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="09ee5-115">기존 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="09ee5-115">View existing rules</span></span>

<span data-ttu-id="09ee5-116">모든 기존 사용자 지정 검색 규칙을 보기 위해 설정 **사용자** 지정  >  **검색으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="09ee5-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="09ee5-117">이 페이지에는 다음 실행 정보가 있는 모든 규칙이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="09ee5-118">**마지막 실행**- 쿼리 일치를 확인하고 경고를 생성하기 위해 규칙을 마지막으로 실행한 경우</span><span class="sxs-lookup"><span data-stu-id="09ee5-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="09ee5-119">**마지막 실행 상태**- 규칙이 성공적으로 실행된지 여부</span><span class="sxs-lookup"><span data-stu-id="09ee5-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="09ee5-120">**다음 실행**-다음 예약된 실행</span><span class="sxs-lookup"><span data-stu-id="09ee5-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="09ee5-121">**상태**- 규칙이 켜져 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="09ee5-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="09ee5-122">규칙 세부 정보 보기, 규칙 수정 및 규칙 실행</span><span class="sxs-lookup"><span data-stu-id="09ee5-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="09ee5-123">사용자 지정 검색 규칙에 대한 포괄적인 정보를 표시하려면 설정 사용자 지정 검색의 규칙 목록에서 규칙  >  **이름을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="09ee5-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="09ee5-124">선택한 규칙에 대한 페이지에는 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="09ee5-125">경고, 실행 상태 및 범위 세부 정보를 포함하여 규칙에 대한 일반 정보</span><span class="sxs-lookup"><span data-stu-id="09ee5-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="09ee5-126">트리거된 경고 목록</span><span class="sxs-lookup"><span data-stu-id="09ee5-126">List of triggered alerts</span></span>
- <span data-ttu-id="09ee5-127">트리거된 작업 목록</span><span class="sxs-lookup"><span data-stu-id="09ee5-127">List of triggered actions</span></span>

<span data-ttu-id="09ee5-128">![사용자 지정 검색 규칙 페이지](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="09ee5-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="09ee5-129">*사용자 지정 검색 규칙 페이지*</span><span class="sxs-lookup"><span data-stu-id="09ee5-129">*Custom detection rule page*</span></span>

<span data-ttu-id="09ee5-130">이 페이지에서 규칙에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="09ee5-131">**를** 실행하여 규칙을 즉시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="09ee5-132">이 작업을 수행하면 다음 실행 간격도 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="09ee5-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="09ee5-133">**편집**- 쿼리를 변경하지 않고 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="09ee5-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="09ee5-134">**쿼리 수정**-고급 헌팅에서 쿼리 편집</span><span class="sxs-lookup"><span data-stu-id="09ee5-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="09ee5-135">**켜기**  /  **끄기**-규칙 사용 또는 실행 중지</span><span class="sxs-lookup"><span data-stu-id="09ee5-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="09ee5-136">**삭제**- 규칙을 끄고 제거</span><span class="sxs-lookup"><span data-stu-id="09ee5-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="09ee5-137">정보를 빠르게 보고 표의 항목에 대한 작업을 수행하기 위해 표 왼쪽에 있는 [&#10003;] 열을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="09ee5-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09ee5-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="09ee5-138">Related topics</span></span>
- [<span data-ttu-id="09ee5-139">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="09ee5-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="09ee5-140">검색 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="09ee5-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="09ee5-141">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="09ee5-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="09ee5-142">경고 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="09ee5-142">View and organize alerts</span></span>](alerts-queue.md)
