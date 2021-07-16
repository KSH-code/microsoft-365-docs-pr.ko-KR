---
title: 앱 정책 관리
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱 거버넌스 정책을 관리합니다.
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420401"
---
# <a name="manage-app-policies"></a><span data-ttu-id="7a1eb-103">앱 정책 관리</span><span class="sxs-lookup"><span data-stu-id="7a1eb-103">Manage app policies</span></span>

><span data-ttu-id="7a1eb-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7a1eb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7a1eb-105">조직에서 사용 중인 최신 앱을 파악하고, 새 앱 기반 공격에 대응하고, 앱 준수 요구 사항에 대한 지속적인 변경을 위해 다음과 같은 방법으로 앱 정책을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="7a1eb-106">새 앱을 대상으로 하는 새 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7a1eb-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="7a1eb-107">기존 정책의 상태 변경(활성, 비활성, 감사 모드)</span><span class="sxs-lookup"><span data-stu-id="7a1eb-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="7a1eb-108">기존 정책의 조건 변경</span><span class="sxs-lookup"><span data-stu-id="7a1eb-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="7a1eb-109">경고 자동 수정을 위한 기존 정책의 작업 변경</span><span class="sxs-lookup"><span data-stu-id="7a1eb-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="7a1eb-110">기존 정책을 관리하는 프로세스의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="7a1eb-111">정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-111">Edit the policy:</span></span>

  - <span data-ttu-id="7a1eb-112">정책 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="7a1eb-113">필요한 경우 테스트를 위해 상태를 **감사 모드** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="7a1eb-114">생성된 경고와 같은 예상 동작을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="7a1eb-115">동작이 예상되지 않는 경우 1단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="7a1eb-116">동작이 필요한 경우 정책을 편집하고 상태를 활성으로 변경합니다(필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="7a1eb-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![앱 정책 관리 워크플로](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="7a1eb-118">앱 정책 구성 편집</span><span class="sxs-lookup"><span data-stu-id="7a1eb-118">Editing an app policy configuration</span></span>

<span data-ttu-id="7a1eb-119">기존 앱 정책의 구성을 변경하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="7a1eb-120">정책 목록에서 정책을 선택한 다음, 앱 정책 창에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="7a1eb-121">세로 타원을 사용하여 목록에서 정책을 선택한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="7a1eb-122">**편집 정책** 페이지의 경우 페이지를 단계별로 실행하고 적절하게 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="7a1eb-123">**설명**: 정책의 목적을 더 쉽게 이해할 수 있도록 설명을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="7a1eb-124">**심각도**</span><span class="sxs-lookup"><span data-stu-id="7a1eb-124">**Severity**</span></span>
- <span data-ttu-id="7a1eb-125">**정책 설정**: 정책이 적용되는 앱 집합을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="7a1eb-126">기존 조건을 사용하거나 조건을 수정하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="7a1eb-127">**작업**: 정책에 의해 생성된 경고의 자동 수정 작업을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="7a1eb-128">**상태**: 정책 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="7a1eb-129">앱 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="7a1eb-129">Deleting an app policy</span></span>

<span data-ttu-id="7a1eb-130">앱 정책을 삭제하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="7a1eb-131">정책 목록에서 정책을 선택한 다음, 앱 정책 창에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="7a1eb-132">세로 타원을 사용하여 목록에서 정책을 선택한 다음 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="7a1eb-133">앱 정책을 삭제하는 대신 상태를 비활성으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="7a1eb-134">비활성 상태가 되면 경고가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="7a1eb-135">예를 들어 향후 정책에 유용한 특정 조건 집합이 있는 앱에 대한 앱 정책을 삭제하는 대신 앱 정책의 이름을 변경하여 유용성을 나타내고 상태를 비활성으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="7a1eb-136">나중에 정책으로 돌아가서 비슷한 앱을 수정하고 상태를 감사 모드 또는 비활성으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1eb-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
