---
title: 도메인 추가
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 조직에 여러 도메인이 필요할 수 있으므로 고객이 찾을 수 있습니다. 구독에 다른 도메인을 추가하는 방법을 배워야 합니다.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706433"
---
# <a name="add-another-domain"></a><span data-ttu-id="4f6e0-104">다른 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="4f6e0-104">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="4f6e0-105">회사에서 다른 용도로 여러 도메인 이름이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-105">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="4f6e0-106">예를 들어 고객이 이미 회사 이름을 사용하고 있으며 통신이 연락하지 못했기 때문에 회사 이름의 다른 맞춤법을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-106">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="4f6e0-107">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="4f6e0-107">Try it!</span></span>

1. <span data-ttu-id="4f6e0-108">In the Microsoft 365 admin center, choose **Setup**.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-108">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="4f6e0-109">사용자 **지정 도메인 설정에서** 보기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-109">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="4f6e0-110">관리 **를** 선택한 다음 도메인 **추가 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-110">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="4f6e0-111">추가할 새 도메인 이름을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-111">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="4f6e0-112">도메인 등록 기관에 로그인합니다. 이 경우 GoDaddy를 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-112">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="4f6e0-113">메시지가 표시될 경우 등록 기관에 로그인한 다음 **승인을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-113">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="4f6e0-114">내 **DNS 레코드 추가를 선택하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-114">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="4f6e0-115">새 도메인에 대한 서비스를 선택하고 다른 도메인에서 처리할 서비스에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-115">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="4f6e0-116">예를 들어 전자 메일에 새 도메인을 사용하려는 경우 를 선택하고 Exchange 및  에 대한 비즈니스용 Skype **선택을 Office 365용 모바일 장치 관리.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-116">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="4f6e0-117">**다음,** **승인,** **다음,** 마친 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-117">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="4f6e0-118">새 도메인이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-118">Your new domain has been added.</span></span>

<span data-ttu-id="4f6e0-119">새 도메인에서 전자 메일을 받으하려면 각 사용자에 대해 새 전자 메일 별칭을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-119">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="4f6e0-120">**사용자,** **활성 사용자** 를 선택한 다음 새 별칭을 할당할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-120">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="4f6e0-121">전자 **메일 별칭** 관리 를 선택한 다음 **별칭 추가 를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="4f6e0-121">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="4f6e0-122">사용자 이름을 입력한 다음 드롭다운 목록에서 새 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-122">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="4f6e0-123">변경 **내용 저장을** 선택한 다음 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-123">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="4f6e0-124">새 도메인에서 전자 메일을 수신해야 하는 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6e0-124">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="4f6e0-125">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="4f6e0-125">Related content</span></span>

<span data-ttu-id="4f6e0-126">[도메인을 도메인에](../admin/setup/add-domain.md) Microsoft 365(문서)</span><span class="sxs-lookup"><span data-stu-id="4f6e0-126">[Add a domain to Microsoft 365](../admin/setup/add-domain.md) (article)</span></span>\
<span data-ttu-id="4f6e0-127">[도메인을 연결하기](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 위해 DNS 레코드 추가(문서)</span><span class="sxs-lookup"><span data-stu-id="4f6e0-127">[Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="4f6e0-128">[모든 도메인 등록 기관에서 Microsoft 365를 설정하도록 네임 서버 변경](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="4f6e0-128">[Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="4f6e0-129">[도메인 FAQ](../admin/setup/domains-faq.yml) (문서)</span><span class="sxs-lookup"><span data-stu-id="4f6e0-129">[Domains FAQ](../admin/setup/domains-faq.yml) (article)</span></span>