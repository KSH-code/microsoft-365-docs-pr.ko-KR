---
title: 공유 사서함에서 라이선스 제거
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: '공유 사서함에서 라이선스를 제거 하 여 다른 사용자에 게 할당 합니다. '
ms.openlocfilehash: 43d32744afe42a8f244160ace20c1d989f501b28
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445498"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="f96e9-103">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="f96e9-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f96e9-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-104">The admin center is changing.</span></span> <span data-ttu-id="f96e9-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f96e9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="f96e9-106">일반적으로 공유 사서함에는 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="f96e9-107">다음 지침에 따라 공유 사서함에서 라이선스를 제거 하 여 사용자에 게 할당 하거나 필요 하지 않은 라이선스에 대 한 비용을 지불 하지 않도록 라이선스를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="f96e9-108">라이선스는 다음과 같은 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="f96e9-109">공유 사서함에 사용 중인 저장소의 저장소가 50 개 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="f96e9-110">공유 사서함에서 원본 위치 보관을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="f96e9-111">공유 사서함은 소송 보존에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="f96e9-112">라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="f96e9-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f96e9-113">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f96e9-114">활성 사용자 페이지에서 라이선스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f96e9-115">라이선스가 사용자 설정 이므로 공유 사서함 페이지에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="f96e9-116">공유 사서함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="f96e9-117">**라이선스 및 앱** 탭 중 하나에서 **라이선스** 를 확장 하 고 제거할 라이선스에 대 한 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="f96e9-118">**변경 내용 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="f96e9-119">**활성 사용자** 페이지로 돌아가면 공유 사서함의 상태가 사용 **허가**되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f96e9-120">여전히 라이선스에 대 한 비용을 지불 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-120">You're still paying for the license.</span></span> <span data-ttu-id="f96e9-121">이에 대 한 비용 지불을 중지 하려면 [구독에서 라이선스를 제거](../../commerce/licenses/remove-licenses-from-subscription.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="f96e9-122">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f96e9-123">활성 사용자 페이지에서 라이선스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f96e9-124">라이선스가 사용자 설정 이므로 공유 사서함 페이지에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f96e9-125">공유 사서함을 선택 하 고 **제품 라이선스**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f96e9-126">**제품 라이선스** 페이지에서 제거 하려는 라이선스에 대 한 토글을 **해제** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f96e9-127">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-127">Select **Save**.</span></span>

5. <span data-ttu-id="f96e9-128">**활성 사용자** 페이지로 돌아가면 공유 사서함의 상태가 사용 **허가**되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f96e9-129">여전히 라이선스에 대 한 비용을 지불 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-129">You're still paying for the license.</span></span> <span data-ttu-id="f96e9-130">이에 대 한 비용 지불을 중지 하려면 [구독에서 라이선스를 제거](../../commerce/licenses/remove-licenses-from-subscription.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="f96e9-131">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f96e9-132">활성 사용자 페이지에서 라이선스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="f96e9-133">라이선스가 사용자 설정 이므로 공유 사서함 페이지에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="f96e9-134">공유 사서함을 선택 하 고 **제품 라이선스**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="f96e9-135">**제품 라이선스** 페이지에서 제거 하려는 라이선스에 대 한 토글을 **해제** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="f96e9-136">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-136">Select **Save**.</span></span>

5. <span data-ttu-id="f96e9-137">**활성 사용자** 페이지로 돌아가면 공유 사서함의 상태가 사용 **허가**되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="f96e9-138">여전히 라이선스에 대 한 비용을 지불 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-138">You're still paying for the license.</span></span> <span data-ttu-id="f96e9-139">이에 대 한 비용 지불을 중지 하려면 [구독에서 라이선스를 제거](../../commerce/licenses/remove-licenses-from-subscription.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f96e9-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="f96e9-140">관련 문서</span><span class="sxs-lookup"><span data-stu-id="f96e9-140">Related articles</span></span>

[<span data-ttu-id="f96e9-141">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="f96e9-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f96e9-142">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="f96e9-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f96e9-143">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="f96e9-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f96e9-144">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="f96e9-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f96e9-145">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f96e9-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
