---
title: Microsoft 365 끝점
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Microsoft 365 트래픽의 대상 IP 주소 및 URL의 경우 다른 Microsoft 365 클라우드의 인터넷 끝점에 대한 이 문서 목록을 사용합니다.
ms.openlocfilehash: 159c8e7dea6fe241ab44b283b1193397c3ad70e3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787906"
---
# <a name="microsoft-365-endpoints"></a><span data-ttu-id="efc51-103">Microsoft 365 끝점</span><span class="sxs-lookup"><span data-stu-id="efc51-103">Microsoft 365 endpoints</span></span>

<span data-ttu-id="efc51-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="efc51-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="efc51-105">끝점은 인터넷의 Microsoft 365 트래픽에 대한 대상 IP 주소, DNS 도메인 이름 및 URL 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-105">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Microsoft 365 traffic on the Internet.</span></span> 

<span data-ttu-id="efc51-106">Microsoft 365 클라우드 기반 서비스에 대한 성능을 최적화하려면 클라이언트 브라우저 및 에지 네트워크의 장치를 통해 이러한 끝점을 특별하게 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-106">To optimize performance to Microsoft 365 cloud-based services, these endpoints need special handling by your client browsers and the devices in your edge network.</span></span> <span data-ttu-id="efc51-107">이러한 장치에는 방화벽, SSL 중단 및 조사 및 패킷 검사 장치, 데이터 손실 방지 시스템이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-107">These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="efc51-108">자세한 [내용은 Microsoft 365 끝점](managing-office-365-endpoints.md) 관리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-108">See [Managing Microsoft 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="efc51-109">현재 5개의 다른 Microsoft 365 클라우드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-109">There are currently five different Microsoft 365 clouds.</span></span> <span data-ttu-id="efc51-110">이 표에서는 각 끝점의 목록으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-110">This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="efc51-111">클라우드</span><span class="sxs-lookup"><span data-stu-id="efc51-111">Cloud</span></span> | <span data-ttu-id="efc51-112">설명</span><span class="sxs-lookup"><span data-stu-id="efc51-112">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="efc51-113">전 세계 끝점</span><span class="sxs-lookup"><span data-stu-id="efc51-113">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="efc51-114">미국 GCC(정부 커뮤니티 클라우드)가 포함된 전 세계 Microsoft 365 구독의 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-114">The endpoints for worldwide Microsoft 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="efc51-115">미국 정부 DoD 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="efc51-115">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="efc51-116">미국 DoD(국방부) 구독의 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-116">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="efc51-117">미국 정부 GCC High 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="efc51-117">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="efc51-118">미국 GCC(정부 커뮤니티 클라우드) High 구독의 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-118">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="efc51-119">21Vianet 끝점에서 운영하는 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="efc51-119">Microsoft 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="efc51-120">21Vianet에서 운영하는 Microsoft 365의 끝점으로, 중국의 Microsoft 365에 대한 요구 사항을 충족하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-120">The endpoints for Microsoft 365 operated by 21Vianet, which is designed to meet the needs for Microsoft 365 in China.</span></span> |
| [<span data-ttu-id="efc51-121">Microsoft 365 Germany 끝점</span><span class="sxs-lookup"><span data-stu-id="efc51-121">Microsoft 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="efc51-122">독일, EU(유럽 연합), EFTA(유럽 자유 무역 연합)의 가장 규제를 많이 받는 고객을 위해 유럽에 있는 별도 클라우드의 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-122">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="efc51-123">Microsoft 365 클라우드에 대한 최신 끝점 목록을 자동화하기 위해 [Office 365 IP](microsoft-365-ip-web-service.md)주소 및 URL 웹 서비스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efc51-123">To automate getting the latest list of endpoints for your Microsoft 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="efc51-124">엔드포인트에 대한 추가 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efc51-124">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="efc51-125">웹 서비스에 포함되지 않는 추가 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="efc51-125">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="efc51-126">Mac용 Office 2016의 네트워크 요청</span><span class="sxs-lookup"><span data-stu-id="efc51-126">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)

<span data-ttu-id="efc51-127">네트워크 장비 공급업체인 경우 [Office 365](microsoft-365-networking-partner-program.md)네트워킹 파트너 프로그램에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-127">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="efc51-128">프로그램에 등록하여 제품 및 솔루션에 Microsoft 365 네트워크 연결 원칙을 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="efc51-128">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 
