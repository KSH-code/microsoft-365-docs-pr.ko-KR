---
title: SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 0d93ff4a-8fbd-42b8-9227-d817dba0046d
description: 이 문서에서는 Azure 인프라 서비스에서 호스트되는 Sharepoint Server 2013 인터넷 사이트를 디자인하고 구현하기 위한 리소스를 제공합니다.
ms.openlocfilehash: 48e0ec38d315aae3d409c3319a4528430331bb94
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546621"
---
# <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a><span data-ttu-id="c6c97-103">SharePoint Server 2013을 사용하는 Microsoft Azure의 인터넷 사이트</span><span class="sxs-lookup"><span data-stu-id="c6c97-103">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>

 <span data-ttu-id="c6c97-104">SharePoint Server 2013을 사용하는 인터넷 사이트는 Azure 인프라 서비스에서 호스팅되는 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-104">Internet sites that use SharePoint Server 2013 benefit by being hosted in Azure Infrastructure Services.</span></span> <span data-ttu-id="c6c97-105">이 문서에서는 이 솔루션을 디자인하고 구현하기 위한 리소스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-105">This article provides resources for designing and implementing this solution.</span></span>

## <a name="using-azure-infrastructure-services-for-internet-sites"></a><span data-ttu-id="c6c97-106">인터넷 사이트에 Azure 인프라 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="c6c97-106">Using Azure Infrastructure Services for Internet sites</span></span>

<span data-ttu-id="c6c97-107">Microsoft Azure는 SharePoint Server 2013을 기반으로 인터넷 사이트를 호스팅하는 데 사용할 수 있는 좋은 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-107">Microsoft Azure provides a compelling option for hosting Internet sites based on SharePoint Server 2013.</span></span> <span data-ttu-id="c6c97-108">장점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-108">Advantages include the following:</span></span>

- <span data-ttu-id="c6c97-109">인프라를 구축하는 대신 멋진 사이트를 개발하는 데 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-109">Focus on developing a great site instead of building infrastructure.</span></span>

- <span data-ttu-id="c6c97-110">수리 및 확장을 통해 수요에 따라 솔루션을 확장할 수 있는 유연성.</span><span class="sxs-lookup"><span data-stu-id="c6c97-110">Flexibility to scale your solution based on demand by scaling out and in.</span></span>

- <span data-ttu-id="c6c97-111">필요한 리소스만 지불하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-111">Pay only for the resources that you need and use.</span></span>

- <span data-ttu-id="c6c97-112">고객 계정에 대해 Azure Active Directory를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-112">Take advantage of Azure Active Directory for customer accounts.</span></span>

- <span data-ttu-id="c6c97-113">현재 Microsoft 365에서 사용할 수 없는 기능(예: 심층 보고 및 분석)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-113">Add features that are not currently available in Microsoft 365, such as deep reporting and analytics.</span></span>

## <a name="resources"></a><span data-ttu-id="c6c97-114">리소스</span><span class="sxs-lookup"><span data-stu-id="c6c97-114">Resources</span></span>

<span data-ttu-id="c6c97-115">다음 기술 그림 및 문서에서는 SharePoint Server 2013을 사용하여 Azure에서 인터넷 사이트를 디자인하고 구현하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-115">The following technical illustrations and articles provide information about how to design and implement Internet sites in Azure by using SharePoint Server 2013.</span></span>

|<span data-ttu-id="c6c97-116">리소스</span><span class="sxs-lookup"><span data-stu-id="c6c97-116">Resource</span></span>|<span data-ttu-id="c6c97-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c6c97-117">More information</span></span>|
|---|---|
|<span data-ttu-id="c6c97-118">**Azure의 SharePoint Server 2013 인터넷 사이트**</span><span class="sxs-lookup"><span data-stu-id="c6c97-118">**SharePoint Server 2013 Internet sites in Azure**</span></span> <br/> <span data-ttu-id="c6c97-119">[![SharePoint를 사용한 Azure의 인터넷 사이트 이미지](../media/MS-AZ-SPInternetSites.jpg)](https://go.microsoft.com/fwlink/p/?LinkId=392552)</span><span class="sxs-lookup"><span data-stu-id="c6c97-119">[![Image of Internet sites in Azure using SharePoint](../media/MS-AZ-SPInternetSites.jpg)](https://go.microsoft.com/fwlink/p/?LinkId=392552)</span></span> <br/> <span data-ttu-id="c6c97-120">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)</span><span class="sxs-lookup"><span data-stu-id="c6c97-120">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)</span></span>|<span data-ttu-id="c6c97-121">이 아키텍처 모델은 Azure의 인터넷 사이트에 대한 주요 디자인 활동과 권장되는 아키텍처 선택에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-121">This architecture model outlines key design activities and recommended architecture choices for Internet sites in Azure.</span></span>|
|<span data-ttu-id="c6c97-122">**디자인 샘플: SharePoint Server 2013용 Azure의 인터넷 사이트**</span><span class="sxs-lookup"><span data-stu-id="c6c97-122">**Design sample: Internet Sites in Azure for SharePoint Server 2013**</span></span> <br/> <span data-ttu-id="c6c97-123">[ ![ 디자인 예제 이미지: SharePoint 2013용 Microsoft Azure의 인터넷 ](../media/MS-AZ-InternetSitesDesignSample.jpg) 사이트]</span><span class="sxs-lookup"><span data-stu-id="c6c97-123">[![Image of the Design sample: Internet sites in Microsoft Azure for SharePoint 2013](../media/MS-AZ-InternetSitesDesignSample.jpg)]</span></span> <br/> <span data-ttu-id="c6c97-124">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)</span><span class="sxs-lookup"><span data-stu-id="c6c97-124">[PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)</span></span>|<span data-ttu-id="c6c97-125">이 디자인 예제를 자체 아키텍처의 시작점으로 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-125">Use this design sample as a starting point for your own architecture.</span></span>|
|<span data-ttu-id="c6c97-126">**[SharePoint 2013용 Microsoft Azure 아키텍처](microsoft-azure-architectures-for-sharepoint-2013.md)**</span><span class="sxs-lookup"><span data-stu-id="c6c97-126">**[Microsoft Azure Architectures for SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)**</span></span> <br/> |<span data-ttu-id="c6c97-127">이 문서에서는 SharePoint 솔루션을 호스트할 Azure 아키텍처를 디자인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c97-127">This article describes how to design Azure architectures to host SharePoint solutions.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="c6c97-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6c97-128">See Also</span></span>

[<span data-ttu-id="c6c97-129">Microsoft 365 솔루션 및 아키텍처 센터</span><span class="sxs-lookup"><span data-stu-id="c6c97-129">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)
