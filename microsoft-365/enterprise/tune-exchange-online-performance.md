---
title: Exchange Online 성능 조정
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: 이 문서에는 일반적인 팁과 다른 리소스에 대한 링크가 포함되어 있으며, 이 링크를 통해 사용자 관리의 성능을 Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909445"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="2de98-103">Exchange Online 성능 조정</span><span class="sxs-lookup"><span data-stu-id="2de98-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="2de98-104">이 문서에는 일반적인 팁과 기타 리소스에 대한 링크가 포함되어 있으며, 특히 마이그레이션 앞에서 Exchange Online 성능 향상 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="2de98-105">이 문서는 프로젝트의 네트워크 계획 및 성능 [Office 365](./network-planning-and-performance.md) 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="2de98-106">성능 향상을 위해 고려할 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="2de98-107">마이그레이션 속도를 개선하고 조직의 대역폭 제한을 Exchange Online 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="2de98-108">**사서함 크기를 줄입니다.**</span><span class="sxs-lookup"><span data-stu-id="2de98-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="2de98-109">사서함 크기가 작을 경우 마이그레이션 속도가 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="2de98-110">**하이브리드 배포에서 사서함 이동 Exchange 사용**</span><span class="sxs-lookup"><span data-stu-id="2de98-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="2de98-111">하이브리드 Exchange 오프라인 메일(형식)을 사용할 수 있습니다. OST 파일)을 사용하여 마이그레이션할 때 다시 다운로드할 필요가 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2de98-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="2de98-112">이렇게 하면 다운로드 대역폭 요구 사항이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="2de98-113">**인터넷 트래픽이 적고, 낮은 인터넷 트래픽이 발생하는 동안 사서함 이동이 발생할 수 Exchange 예약합니다.**</span><span class="sxs-lookup"><span data-stu-id="2de98-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="2de98-114">이동을 위한 경우 마이그레이션 요청이 사서함 복제 프록시로 전송되어 즉시 수행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="2de98-115">**웹에서 사용할 수 있는 Outlook 팝업을 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2de98-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="2de98-116">작은 팝업은 서버에서 일부 구성 요소를 렌더링하여 Microsoft Edge 또는 Internet Explorer 전자 메일 메시지의 메모리를 많이 사용하는 더 작고 적은 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="2de98-117">자세한 내용은 린트 팝업을 사용하여 메일 메시지를 읽을 때 사용되는 메모리 [줄이기를 참조하세요.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)</span><span class="sxs-lookup"><span data-stu-id="2de98-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="2de98-118">일반 조언</span><span class="sxs-lookup"><span data-stu-id="2de98-118">General advice</span></span>

- <span data-ttu-id="2de98-119">사용자 위치에 대한 DNS outlook.office.com 논리적 입력 위치에 MS-datacenter를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="2de98-120">사서함 캐싱을 조사하고 적절한 옵션(다시)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="2de98-121">캐싱 기간, 공유 사서함 캐싱, et cetera).</span><span class="sxs-lookup"><span data-stu-id="2de98-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="2de98-122">인터넷을 Outlook VPN 연결이 중앙 사무실로 전달되지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="2de98-123">사서함 데이터가 폴더 및 항목, 금액에 대한 제한을 준수하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2de98-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="2de98-124">마이그레이션 성능 Exchange 대한 자세한 내용은 Office 365 성능 및 [모범 사례를 참조하세요.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="2de98-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
