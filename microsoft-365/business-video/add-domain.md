---
title: 도메인 추가
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 구독에 다른 도메인을 추가하는 방법을 학습합니다.
ms.openlocfilehash: a5df440f3b7e28c2bdbc69f9383a8399ef193ed0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927613"
---
# <a name="add-another-domain"></a><span data-ttu-id="b7148-103">다른 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="b7148-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="b7148-104">회사에서 여러 가지 용도의 도메인 이름이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="b7148-105">예를 들어 고객이 이미 회사 이름을 사용하고 있으며 커뮤니케이션이 연락하지 못했기 때문에 회사 이름의 다른 맞춤법을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="b7148-106">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="b7148-106">Try it!</span></span>

1. <span data-ttu-id="b7148-107">Microsoft 365 관리 센터에서 설치를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7148-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="b7148-108">사용자 **지정 도메인 설정 아래에서** 보기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7148-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="b7148-109">Choose **Manage,** and then **Add domain.**</span><span class="sxs-lookup"><span data-stu-id="b7148-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="b7148-110">추가할 새 도메인 이름을 입력하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7148-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="b7148-111">도메인 등록 기관에 로그인합니다( 이 경우 GoDaddy) 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7148-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="b7148-112">메시지가 표시될 경우 등록 기관에 로그인한 다음 **승인을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="b7148-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="b7148-113">Choose **Add the DNS records for me,** and then select **Next.**</span><span class="sxs-lookup"><span data-stu-id="b7148-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="b7148-114">새 도메인에 대한 서비스를 선택하고 다른 도메인에서 처리할 서비스의 확인란 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="b7148-115">예를 들어 전자 메일에 새 도메인을 사용하려는 경우 **Exchange를** 선택하고 비즈니스용 **Skype** 및 **Office 365용** 모바일 장치 관리 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="b7148-116">**다음,** **승인,** **다음,** 마친 **다음을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7148-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="b7148-117">새 도메인이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-117">Your new domain has been added.</span></span>

<span data-ttu-id="b7148-118">새 도메인에서 전자 메일을 받으하려면 각 사용자에 대해 새 전자 메일 별칭을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="b7148-119">**사용자,** **활성 사용자를** 선택한 다음 새 별칭을 할당할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="b7148-120">Choose **Manage email aliases,** and then **Add an alias**.</span><span class="sxs-lookup"><span data-stu-id="b7148-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="b7148-121">사용자 이름을 입력한 다음 드롭다운 목록에서 새 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="b7148-122">변경 **내용 저장을** 선택한 다음 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="b7148-123">새 도메인에서 전자 메일을 수신해야 하는 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b7148-123">Repeat these steps for each user who should receive email at the new domain.</span></span>