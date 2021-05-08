---
title: 사용자에 대한 스케줄러 Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 사용자에 대한 스케줄러 Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286255"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="228ea-103">사용자에 대한 스케줄러 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="228ea-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="228ea-104">다음의 선행 Microsoft 365 스케줄러를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="228ea-105">**필요한 것**</span><span class="sxs-lookup"><span data-stu-id="228ea-105">**What do I need?**</span></span> |<span data-ttu-id="228ea-106">**설명**</span><span class="sxs-lookup"><span data-stu-id="228ea-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="228ea-107">Cortana 사서함</span><span class="sxs-lookup"><span data-stu-id="228ea-107">Cortana mailbox</span></span> |<span data-ttu-id="228ea-108">테넌트 관리자는 "Cortana" 사서함(즉, cortana@yourdomain.com) 역할을 하게 cortana@yourdomain.com.</span><span class="sxs-lookup"><span data-stu-id="228ea-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="228ea-109">Exchange Online 사서함</span><span class="sxs-lookup"><span data-stu-id="228ea-109">Exchange Online mailbox</span></span> |<span data-ttu-id="228ea-110">사용자에게 메일 및 Exchange Online 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="228ea-111">스케줄러 라이선스</span><span class="sxs-lookup"><span data-stu-id="228ea-111">Scheduler license</span></span> |<span data-ttu-id="228ea-112">라이선스 및 가격 정보는 에 대한 [스케줄러를 Microsoft 365.](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)</span><span class="sxs-lookup"><span data-stu-id="228ea-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="228ea-113">Cortana용 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="228ea-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="228ea-114">테넌트의 Exchange 사서함은 Cortana와의 전자 메일을 보내고 받을 테넌트의 Cortana 사서함 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="228ea-115">Cortana로 전송된 모든 전자 메일은 보존 정책에 따라 테넌트의 Cortana 사서함에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="228ea-116">새 Microsoft 365 관리 센터를 사용하여 새 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="228ea-117">30일 보존 정책이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="228ea-118">사서함의 기본 SMTP 주소에 Cortana 이름을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="228ea-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="228ea-119">"Cortana@yourdomain.com, 'CortanaScheduler@contoso.com' 또는 'Cortana.Scheduler@yourdomain.com' 같은 이름을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="228ea-120">Cortana 사서함을 scheduler_m365@microsoft.com Microsoft(scheduler_m365@microsoft.com)에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="228ea-121">스케줄러 서비스를 사용하도록 Cortana 사서함을 구성하려면 Microsoft에 문의해야 scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="228ea-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="228ea-122">Cortana 사서함을 사용하도록 설정하는 데 최대 2주가 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="228ea-123">Exchange Online 사서함</span><span class="sxs-lookup"><span data-stu-id="228ea-123">Exchange Online mailbox</span></span>
<span data-ttu-id="228ea-124">스케줄러는 사용자에 대한 추가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="228ea-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="228ea-125">모임 이끌이가 스케줄러가 작동하려면 Exchange Online 사서함 및 일정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="228ea-126">Exchange 요구 사항</span><span class="sxs-lookup"><span data-stu-id="228ea-126">Exchange requirements</span></span>

<span data-ttu-id="228ea-127">라이선싱 스케줄러 외에 다음 라이선스 중 하나도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="228ea-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="228ea-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="228ea-129">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="228ea-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="228ea-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="228ea-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="228ea-131">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="228ea-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="228ea-132">Exchange Online 계획 1 또는 계획 2 라이선스.</span><span class="sxs-lookup"><span data-stu-id="228ea-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="228ea-133">**Microsoft 365** 대한 스케줄러는 중국의 21Vianet에서 운영하는 Office 365 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="228ea-134">데이터 수탁자 German Telekom을 사용하는 Microsoft 365 클라우드를 사용하는 사용자도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="228ea-135">데이터 위치가 독일 데이터 센터가 아닌 독일 사용자의 경우에는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="228ea-136">GCC, Consumer, GCC High 또는 DoD를 비롯한 정부 클라우드 사용자에게도 이 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="228ea-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
