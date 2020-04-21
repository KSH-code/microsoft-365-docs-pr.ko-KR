---
title: 액세스 차단 방법 비교
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 직원이 조직을 떠나는 경우 Microsoft 365에 대 한 액세스를 차단 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9383c970ea1c17d9116299d5788c8faf0ed0659f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627935"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="b607f-103">액세스 차단 방법 비교</span><span class="sxs-lookup"><span data-stu-id="b607f-103">Compare ways to block access</span></span>

<span data-ttu-id="b607f-104">직원이 조직을 떠나는 경우 좋은 용어나 나쁜 경우에는 Microsoft 365에 대 한 액세스를 차단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="b607f-105">이 작업을 수행할 수 있는 몇 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b607f-106">**액세스를 차단 하는 방법**</span><span class="sxs-lookup"><span data-stu-id="b607f-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="b607f-107">**정의**</span><span class="sxs-lookup"><span data-stu-id="b607f-107">**Definition**</span></span> <br/> |<span data-ttu-id="b607f-108">**모범 사례**</span><span class="sxs-lookup"><span data-stu-id="b607f-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="b607f-109">로그인 차단</span><span class="sxs-lookup"><span data-stu-id="b607f-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="b607f-110">사용자가 Microsoft 365에 액세스 하지 못하도록 차단 하는 한 가지 방법은 로그인 상태를 **로그인 차단**으로 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="b607f-111">이를 통해 이전에 다운로드 하거나 동기화 된 전자 메일과 문서를 볼 수는 있지만 컴퓨터 및 모바일 장치에서 Microsoft 365에 로그인 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="b607f-112">Blackberry Enterprise 서비스를 사용 하는 경우에는 해당 사용자의 액세스를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="b607f-113">직원이 조직을 탈퇴 하거나 장기간 휴가를 떠날 계획을 수립할 때 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="b607f-114">사용자 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="b607f-114">Reset user password</span></span>  <br/> |<span data-ttu-id="b607f-115">사용자가 Microsoft 365에 액세스 하지 못하도록 차단 하는 또 다른 방법은 암호를 다시 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="b607f-116">이렇게 하면 이전에 다운로드 하거나 동기화 된 전자 메일과 문서를 볼 수 있지만 계정을 사용 하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="b607f-117">그런 다음 로그인 하 여 원하는 암호를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="b607f-118">직원이 갑자기 영구적으로 나갈 때와 비즈니스 데이터에 대 한 관심이 있다고 생각 하는 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="b607f-119">할당 된 모든 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="b607f-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="b607f-120">또 다른 옵션은 사용자에 게 할당 된 Microsoft 365 라이선스를 제거 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="b607f-121">이를 통해 Office 제품군, 웹, Yammer 및 SharePoint Online 용 Office 앱과 같은 응용 프로그램 및 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="b607f-122">이러한 서비스는 계속 로그인 하지만 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="b607f-123">이 사용자가 더 이상 Microsoft 365의 특정 기능에 액세스할 필요가 없는 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="b607f-124">**중요:** 라이선스를 제거 하면 사용자의 사서함이 30 일 후에 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b607f-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="b607f-125">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b607f-125">Related articles</span></span>

[<span data-ttu-id="b607f-126">Offboard Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b607f-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="b607f-127">Microsoft 365에서 사용자 암호 다시 설정</span><span class="sxs-lookup"><span data-stu-id="b607f-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="b607f-128">비즈니스를 위해 Microsoft 365의 사용자에 게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="b607f-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="b607f-129">비즈니스에 대 한 Microsoft 365의 사용자 로부터 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="b607f-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

