---
title: 라이선스 충돌 해결
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Microsoft 365 for business 구독에 대 한 라이선스 충돌을 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: 2270fd3ad831ec0ad92ac4eddec5f08a1d07f8be
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015974"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="70f86-103">라이선스 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="70f86-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="70f86-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-104">The admin center is changing.</span></span> <span data-ttu-id="70f86-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70f86-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="70f86-106">새 사용자를 만들기 전에 구독에 필요한 라이선스를 구입 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="70f86-107">이렇게 하면 사용자 계정이 만들어지므로 라이선스를 새 사용자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="70f86-108">이미 사용자에게 라이선스를 모두 할당했지만 일부 라이선스가 만료되었거나 사용자에게 이미 할당한 라이선스를 제거하려면 라이선스 충돌이 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="70f86-109">자세한 내용은 [구독에서 라이선스 제거](../../commerce/licenses/remove-licenses-from-subscription.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70f86-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="70f86-110">라이선스 충돌을 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="70f86-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="70f86-111">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="70f86-112">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70f86-113">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="70f86-114">충돌에 대한 자세한 내용은 **상태** 열을 확인해보세요.</span><span class="sxs-lookup"><span data-stu-id="70f86-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="70f86-115">충돌이 발생 하는 경우 하나 이상의 사용자에 게 유효한 라이선스가 필요 하다 고 알리는 경고 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70f86-116">충돌이 없는 경우에는 **상태** 열이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="70f86-117">라이선스 충돌을 해결하는 방법</span><span class="sxs-lookup"><span data-stu-id="70f86-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="70f86-118">추가 라이선스를 [구입](../../commerce/licenses/buy-licenses.md) 하거나 [더 이상 필요 하지 않은 사용자의 라이선스를 제거](remove-licenses-from-users.md)하 여 라이선스 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="70f86-119">경우에 따라 [사용자 계정을 삭제하여 라이선스를 확보](../add-users/delete-a-user.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f86-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="70f86-120">관련 문서</span><span class="sxs-lookup"><span data-stu-id="70f86-120">Related articles</span></span>

[<span data-ttu-id="70f86-121">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="70f86-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="70f86-122">사용자의 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="70f86-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
