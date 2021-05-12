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
description: '공유 사서함에서 라이선스를 제거하여 다른 사용자에게 할당합니다. '
ms.openlocfilehash: 873b50b34b9887ada92cc56f7083e3b748a52035
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327225"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="eab94-103">공유 사서함에서 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="eab94-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="eab94-104">공유 사서함에는 일반적으로 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="eab94-105">다음 지침에 따라 공유 사서함에서 라이선스를 제거하여 사용자에게 라이선스를 할당하거나 필요하지 않은 라이선스 비용을 지불하지 않을 수 있도록 라이선스를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="eab94-106">다음과 같은 시나리오에서는 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="eab94-107">공유 사서함에 사용 중이 50GB가 넘는 저장소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="eab94-108">공유 사서함은 인바운드 보관을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="eab94-109">공유 사서함은 소송 보류에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="eab94-110">공유 사서함에 Microsoft Defender 라이선스가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="eab94-111">라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="eab94-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="eab94-112">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="eab94-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="eab94-113">활성 사용자 페이지에서 라이선스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-113">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="eab94-114">라이선스는 사용자 설정이기 때문에 공유 사서함 페이지에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-114">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="eab94-115">공유 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-115">Select the shared mailbox.</span></span>

3. <span data-ttu-id="eab94-116">라이선스 **및** 앱 탭 중  하나에서 라이선스를 확장하고 제거할 라이선스의 확인란을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-116">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="eab94-117">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-117">Select **Save changes**.</span></span>

5. <span data-ttu-id="eab94-118">활성 사용자 페이지로 **돌아오면** 공유 사서함의 상태가 라이선스가 없는 **상태가 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="eab94-118">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="eab94-119">라이선스 비용은 계속 지불하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-119">You're still paying for the license.</span></span> <span data-ttu-id="eab94-120">요금 지불을 중지하려면 구독에서 [라이선스를 제거합니다.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="eab94-120">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="eab94-121">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="eab94-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eab94-122">활성 사용자 페이지에서 라이선스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-122">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="eab94-123">라이선스는 사용자 설정이기 때문에 공유 사서함 페이지에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-123">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="eab94-124">공유 사서함을 선택한 다음 제품 **라이선스** 옆에 있는 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eab94-124">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="eab94-125">제품 라이선스 **페이지 중** 하나를 제거하려는  라이선스에 대해 토글을 해제로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="eab94-125">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="eab94-126">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-126">Select **Save**.</span></span>

5. <span data-ttu-id="eab94-127">활성 사용자 페이지로 **돌아오면** 공유 사서함의 상태가 라이선스가 없는 **상태가 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="eab94-127">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="eab94-128">라이선스 비용은 계속 지불하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-128">You're still paying for the license.</span></span> <span data-ttu-id="eab94-129">요금 지불을 중지하려면 구독에서 [라이선스를 제거합니다.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="eab94-129">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="eab94-130">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..</span><span class="sxs-lookup"><span data-stu-id="eab94-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eab94-131">활성 사용자 페이지에서 라이선스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-131">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="eab94-132">라이선스는 사용자 설정이기 때문에 공유 사서함 페이지에서 라이선스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-132">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="eab94-133">공유 사서함을 선택한 다음 제품 **라이선스** 옆에 있는 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eab94-133">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="eab94-134">제품 라이선스 **페이지 중** 하나를 제거하려는  라이선스에 대해 토글을 해제로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="eab94-134">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="eab94-135">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-135">Select **Save**.</span></span>

5. <span data-ttu-id="eab94-136">활성 사용자 페이지로 **돌아오면** 공유 사서함의 상태가 라이선스가 없는 **상태가 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="eab94-136">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="eab94-137">라이선스 비용은 계속 지불하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab94-137">You're still paying for the license.</span></span> <span data-ttu-id="eab94-138">요금 지불을 중지하려면 구독에서 [라이선스를 제거합니다.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="eab94-138">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="eab94-139">관련 문서</span><span class="sxs-lookup"><span data-stu-id="eab94-139">Related articles</span></span>

[<span data-ttu-id="eab94-140">공유 사서함 정보</span><span class="sxs-lookup"><span data-stu-id="eab94-140">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="eab94-141">공유 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="eab94-141">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="eab94-142">공유 사서함 구성</span><span class="sxs-lookup"><span data-stu-id="eab94-142">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="eab94-143">사용자 사서함을 공유 사서함으로 변환</span><span class="sxs-lookup"><span data-stu-id="eab94-143">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="eab94-144">공유 사서함의 문제 해결</span><span class="sxs-lookup"><span data-stu-id="eab94-144">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)