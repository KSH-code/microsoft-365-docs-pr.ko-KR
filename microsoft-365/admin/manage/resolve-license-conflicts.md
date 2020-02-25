---
title: 비즈니스용 Office 365의 라이선스 충돌 문제 해결
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Office 365 for business 구독에 대 한 라이선스 충돌을 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: c96f9e38b3799cb8b77f9422c72a7aec9d001eae
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254883"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a><span data-ttu-id="604c2-103">비즈니스용 Office 365의 라이선스 충돌 문제 해결</span><span class="sxs-lookup"><span data-stu-id="604c2-103">Resolve license conflicts in Office 365 for business</span></span>

<span data-ttu-id="604c2-104">새 사용자를 만들기 전에 구독에 필요한 라이선스를 구입 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="604c2-105">이렇게 하면 사용자 계정이 만들어지므로 라이선스를 새 사용자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="604c2-106">이미 사용자에게 라이선스를 모두 할당했지만 일부 라이선스가 만료되었거나 사용자에게 이미 할당한 라이선스를 제거하려면 라이선스 충돌이 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="604c2-107">자세한 내용은 [구독에서 라이선스 제거](../../commerce/licenses/remove-licenses-from-subscription.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="604c2-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="604c2-108">라이선스 충돌을 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="604c2-108">How do I view license conflicts?</span></span>

1. <span data-ttu-id="604c2-109">관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-109">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="604c2-110">Office 365 독일을 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-110">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="604c2-111">21Vianet에서 운영 하는 Office 365을 사용 중인 경우이 <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-111">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="604c2-112">충돌에 대한 자세한 내용은 **상태** 열을 확인해보세요.</span><span class="sxs-lookup"><span data-stu-id="604c2-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="604c2-113">충돌이 발생 하는 경우 하나 이상의 사용자에 게 유효한 라이선스가 필요 하다 고 알리는 경고 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="604c2-114">충돌이 없는 경우에는 **상태** 열이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="604c2-115">라이선스 충돌을 해결하는 방법</span><span class="sxs-lookup"><span data-stu-id="604c2-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="604c2-116">추가 라이선스를 [구입](../../commerce/licenses/buy-licenses.md) 하거나 [더 이상 필요 하지 않은 사용자의 라이선스를 제거](remove-licenses-from-users.md)하 여 라이선스 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="604c2-117">경우에 따라 [사용자 계정을 삭제하여 라이선스를 확보](../add-users/delete-a-user.md)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604c2-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="604c2-118">관련 문서</span><span class="sxs-lookup"><span data-stu-id="604c2-118">Related articles</span></span> 

[<span data-ttu-id="604c2-119">사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="604c2-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="604c2-120">사용자의 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="604c2-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)