---
title: 참가자 위험 관리 사용자
description: Microsoft 365의 참가자 위험 관리 사용자에 대 한 자세한 정보
keywords: Microsoft 365, 참가자 위험 관리, 위험 관리, 규정 준수
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 322cd0aa8b72ea2c81792b36614e87d97db87d7c
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179109"
---
# <a name="insider-risk-management-users"></a><span data-ttu-id="b6d07-104">참가자 위험 관리 사용자</span><span class="sxs-lookup"><span data-stu-id="b6d07-104">Insider risk management users</span></span>

<span data-ttu-id="b6d07-105">참가자 위험 관리 사용자는 하나 이상의 참가자 위험 관리 정책에 포함 된 조직의 직원입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="b6d07-106">**사용자 대시보드** 를 사용 하 여 직원에 대 한 위험 정보를 신속 하 게 검토 하 고 기존 참가자 위험 관리 정책에 직원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="b6d07-107">참가자 위험 관리 정책에 포함 된 각 사용자는 **사용자 대시보드에**다음과 같은 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="b6d07-108">**사용자**: 사용자에 대 한 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-108">**Users**: The username for a user.</span></span>
- <span data-ttu-id="b6d07-109">**위험 수준**: 사용자의 현재 계산 된 위험 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-109">**Risk level**: The current calculated risk level of the user.</span></span> <span data-ttu-id="b6d07-110">이 점수는 24 시간 마다 계산 되며 사용자에 게 연결 된 모든 활성 알림의 경고 위험 점수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-110">This score is calculated every 24 hours and uses the alert risk scores from all active alerts associated to the user.</span></span>
- <span data-ttu-id="b6d07-111">**활성 경고**: 모든 정책에 대 한 활성 경고 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-111">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="b6d07-112">**확인 된 위반**: 사용자에 대 한 *확인 정책 위반* 으로 해결 되는 사례 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-112">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="b6d07-113">**사례**: 사용자의 현재 활성 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-113">**Case**: The current active case for the user.</span></span>

![참가자 위험 관리 사용자 대시보드](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="b6d07-115">사용자 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="b6d07-115">View user details</span></span>

<span data-ttu-id="b6d07-116">사용자에 대 한 위험 활동에 대 한 자세한 내용을 보려면 사용자 **대시보드에서**사용자를 두 번 클릭 하 여 사용자 세부 정보 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-116">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="b6d07-117">세부 정보 창에서 다음 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-117">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="b6d07-118">**사용자 프로필** 탭</span><span class="sxs-lookup"><span data-stu-id="b6d07-118">**User profile** tab</span></span>
    - <span data-ttu-id="b6d07-119">**이름 및 제목**: 사용자의 이름 및 직위 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-119">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="b6d07-120">**사용자 전자 메일**: 사용자의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-120">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="b6d07-121">**별칭**: 사용자의 네트워크 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-121">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="b6d07-122">**조직 또는 부서**: 사용자의 조직 또는 부서입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-122">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="b6d07-123">**사용자 활동** 탭</span><span class="sxs-lookup"><span data-stu-id="b6d07-123">**User activity** tab</span></span>
    - <span data-ttu-id="b6d07-124">**최근 사용자 활동 기록**: 이벤트를 트리거하는 정책 및 사용자 작업에 대 한 위험 표시기를 모두 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-124">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="b6d07-125">트리거하는 이벤트는 resignation 날짜 또는 직원의 마지막으로 예정 된 날짜에 대 한 승인 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-125">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="b6d07-126">위험 지표는 위험 요소가 있고 사용자가 포함 된 정책과 일치 하는 것으로 확인 된 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-126">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="b6d07-127">이벤트 및 위험 활동은 가장 최근에 나열 된 항목과 함께 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-127">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="b6d07-128">정책에 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="b6d07-128">Add a user to a policy</span></span>

<span data-ttu-id="b6d07-129">참가자 위험 관리 정책에 사용자를 추가 하려면 Microsoft 365 준수 센터의 **참가자 위험 관리** 솔루션에서 새 정책 마법사나 **사용자** 탭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-129">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="b6d07-130">기존 참가자 위험 정책에 사용자를 추가 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-130">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="b6d07-131">[Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **참가자 위험 관리** 로 이동 하 여 **사용자** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="b6d07-132">도구 모음에서 **정책에 사용자 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-132">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="b6d07-133">**새 사용자 추가** 대화 상자에서 **사용자** 필드에 사용자 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-133">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="b6d07-134">정책에 추가 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-134">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="b6d07-135">**정책** 필드의 드롭다운 화살표를 선택 하 여 구성 된 참가자 위험 관리 정책을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-135">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="b6d07-136">사용자를 추가할 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-136">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="b6d07-137">**정품 인증 창** 에서이 사용자에 대해 정책이 활성화 되는 기간을 정의 하 고 사용자가 정책과 일치 하는 첫 번째 활동을 수행할 때 트리거되는 경우에는이 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-137">Use the **Activation window** slider control to define how long the policy is active for this user and is triggered when the user performs the first activity matching the policy.</span></span> <span data-ttu-id="b6d07-138">모니터링 창의 범위는 5 ~ 30 일입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-138">The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="b6d07-139">**추가** 를 선택한 다음 사용자를 정책에 추가 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d07-139">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
