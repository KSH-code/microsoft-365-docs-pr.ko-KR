---
title: 끝점용 Microsoft Defender에서 사용자 계정 조사
description: 조사하는 동안 사용자 계정에서 잠재적으로 손상된 자격 증명을 조사하거나 관련 사용자 계정을 피벗합니다.
keywords: 조사, 계정, 사용자, 사용자 엔터티, 경고, 끝점용 Microsoft Defender
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
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935068"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7d6ef-104">끝점용 Microsoft Defender에서 사용자 계정 조사</span><span class="sxs-lookup"><span data-stu-id="7d6ef-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d6ef-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7d6ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="7d6ef-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7d6ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7d6ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d6ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="7d6ef-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7d6ef-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7d6ef-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="7d6ef-110">사용자 계정 엔터티 조사</span><span class="sxs-lookup"><span data-stu-id="7d6ef-110">Investigate user account entities</span></span>

<span data-ttu-id="7d6ef-111">가장 활발한 경고(대시보드에 "위험 상태의 사용자"로 표시)가 있는 사용자 계정을 식별하고 잠재적으로 손상된 자격 증명의 사례를 조사하거나 경고 또는 장치를 조사할 때 관련 사용자 계정을 피벗하여 해당 사용자 계정이 있는 장치 간에 가능한 측면 이동을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="7d6ef-112">다음 보기에서 사용자 계정 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="7d6ef-113">대시보드</span><span class="sxs-lookup"><span data-stu-id="7d6ef-113">Dashboard</span></span>
- <span data-ttu-id="7d6ef-114">경고 큐</span><span class="sxs-lookup"><span data-stu-id="7d6ef-114">Alert queue</span></span>
- <span data-ttu-id="7d6ef-115">장치 세부 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="7d6ef-115">Device details page</span></span>

<span data-ttu-id="7d6ef-116">이러한 보기에서는 사용자 계정에 대한 자세한 정보가 표시되는 사용자 계정 세부 정보 페이지로 이동하는 클릭 가능한 사용자 계정 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="7d6ef-117">사용자 계정 엔터티를 조사하면 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="7d6ef-118">사용자 계정 세부 정보, ID에 대한 Microsoft Defender 경고 및 로그온 장치, 역할, 로그온 유형 및 기타 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7d6ef-118">User account details, Microsoft Defender for Identity alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="7d6ef-119">인시던트 및 사용자 장치 개요</span><span class="sxs-lookup"><span data-stu-id="7d6ef-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="7d6ef-120">이 사용자와 관련된 알림</span><span class="sxs-lookup"><span data-stu-id="7d6ef-120">Alerts related to this user</span></span>
- <span data-ttu-id="7d6ef-121">조직에서 관찰된(로그온한 장치)</span><span class="sxs-lookup"><span data-stu-id="7d6ef-121">Observed in organization (devices logged on to)</span></span>

![사용자 계정 엔터티 세부 정보 페이지의 이미지](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="7d6ef-123">사용자 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7d6ef-123">User details</span></span>

<span data-ttu-id="7d6ef-124">왼쪽의 사용자 세부 정보 창에서는 관련된 공개 인시던트, 활성 경고, SAM 이름, SID, ID 알림용 Microsoft Defender 경고, 사용자가 로그온한 장치 수, 사용자가 처음 및 마지막으로 본 때, 역할 및 로그온 유형과 같은 사용자에 대한 정보를 제공합니다. </span><span class="sxs-lookup"><span data-stu-id="7d6ef-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Microsoft Defender for Identity alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="7d6ef-125">사용하도록 설정한 통합 기능에 따라 다른 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="7d6ef-126">예를 들어 비즈니스용 Skype 사용하도록 설정하면 포털에서 사용자에게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="7d6ef-127">**Azure ATP 경고** 섹션에는 Id에 대한 Microsoft Defender 기능을 사용하도록 설정한 경우 Id에 대한 Microsoft Defender 페이지로 이동하는 링크가 포함되어 있으며 사용자와 관련된 알림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-127">The **Azure ATP alerts** section contains a link that will take you to the Microsoft Defender for Identity page, if you have enabled the Microsoft Defender for Identity feature, and there are alerts related to the user.</span></span> <span data-ttu-id="7d6ef-128">Microsoft Defender for Identity 페이지에서 경고에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-128">The Microsoft Defender for Identity page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="7d6ef-129">이 기능을 사용하려면 ID용 Microsoft Defender 및 Endpoint용 Defender에서 통합을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-129">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="7d6ef-130">Endpoint용 Defender에서 고급 기능에서 이 기능을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="7d6ef-131">고급 기능을 사용하도록 설정하는 방법에 대한 자세한 내용은 고급 기능 [켜기 를 참조하세요.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="7d6ef-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="7d6ef-132">조직에서 개요, 경고 및 관찰된 탭은 사용자 계정에 대한 다양한 특성을 표시하는 서로 다른 탭입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="7d6ef-133">개요</span><span class="sxs-lookup"><span data-stu-id="7d6ef-133">Overview</span></span>

<span data-ttu-id="7d6ef-134">개요 **탭에는** 인시던트 세부 정보 및 사용자가 로그온한 장치 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="7d6ef-135">이러한 이벤트를 확장하여 각 장치에 대한 로그온 이벤트에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="7d6ef-136">경고</span><span class="sxs-lookup"><span data-stu-id="7d6ef-136">Alerts</span></span>

<span data-ttu-id="7d6ef-137">경고 **탭에서는** 사용자 계정과 연결된 경고 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="7d6ef-138">이 목록은 경고 큐의 [](alerts-queue.md)필터링된 보기로, 사용자 컨텍스트가 선택된 사용자 계정, 마지막 활동이 검색된 날짜, 경고에 대한 간단한 설명, 경고와 연결된 장치, 경고의 심각도, 큐의 경고 상태 및 경고가 할당된 사용자를 보여 주며, 경고가 할당된 경고를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="7d6ef-139">조직에서 관찰</span><span class="sxs-lookup"><span data-stu-id="7d6ef-139">Observed in organization</span></span>

<span data-ttu-id="7d6ef-140">**조직에서** 관찰 탭을 사용하면 이 사용자가 로그온한 것으로 관찰된 장치 목록, 이러한 각 장치에 대해 가장 자주 로그온한 사용자 계정 및 각 장치에서 관찰된 총 사용자 목록을 볼 수 있는 날짜 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="7d6ef-141">조직에서 관찰 표에서 항목을 선택하면 항목이 확장되고 장치에 대한 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="7d6ef-142">항목 내의 링크를 직접 선택하면 해당 페이지로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="7d6ef-143">특정 사용자 계정 검색</span><span class="sxs-lookup"><span data-stu-id="7d6ef-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="7d6ef-144">검색 **표시줄** **드롭다운** 메뉴에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="7d6ef-145">검색 필드에 사용자 계정을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d6ef-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="7d6ef-146">검색 아이콘을 클릭하거나 Enter를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d6ef-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="7d6ef-147">쿼리 텍스트와 일치하는 사용자 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="7d6ef-148">사용자 계정의 도메인 및 이름, 사용자 계정이 마지막으로 확인된 경우 및 지난 30일 동안 로그온한 것으로 관찰된 총 장치 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="7d6ef-149">다음 기간에 따라 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6ef-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="7d6ef-150">1일</span><span class="sxs-lookup"><span data-stu-id="7d6ef-150">1 day</span></span>
- <span data-ttu-id="7d6ef-151">3일</span><span class="sxs-lookup"><span data-stu-id="7d6ef-151">3 days</span></span>
- <span data-ttu-id="7d6ef-152">7일</span><span class="sxs-lookup"><span data-stu-id="7d6ef-152">7 days</span></span>
- <span data-ttu-id="7d6ef-153">30일</span><span class="sxs-lookup"><span data-stu-id="7d6ef-153">30 days</span></span>
- <span data-ttu-id="7d6ef-154">6개월</span><span class="sxs-lookup"><span data-stu-id="7d6ef-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="7d6ef-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7d6ef-155">Related topics</span></span>

- [<span data-ttu-id="7d6ef-156">끝점 경고 큐에 대한 Microsoft Defender 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="7d6ef-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="7d6ef-157">끝점 경고에 대한 Microsoft Defender 관리</span><span class="sxs-lookup"><span data-stu-id="7d6ef-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="7d6ef-158">끝점 경고에 대한 Microsoft Defender 조사</span><span class="sxs-lookup"><span data-stu-id="7d6ef-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="7d6ef-159">끝점 경고에 대한 Defender와 관련된 파일 조사</span><span class="sxs-lookup"><span data-stu-id="7d6ef-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="7d6ef-160">Endpoint 장치용 Defender 목록에서 장치 조사</span><span class="sxs-lookup"><span data-stu-id="7d6ef-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="7d6ef-161">끝점 경고에 대한 Defender와 연결된 IP 주소 조사</span><span class="sxs-lookup"><span data-stu-id="7d6ef-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="7d6ef-162">끝점 경고에 대한 Defender와 연결된 도메인 조사</span><span class="sxs-lookup"><span data-stu-id="7d6ef-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
