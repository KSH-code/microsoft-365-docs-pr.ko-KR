---
title: 온라인 Office 365 Content Delivery Network(CDN)를 SharePoint 사용
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Office 365 Content Delivery Network(CDN)를 사용하여 온라인 자산의 배달 속도를 SharePoint 방법을 알아보습니다.
ms.openlocfilehash: e6cce93be0e8d893d68ae8bcdb15fde325a2cb59
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169559"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="b028e-103">sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기</span><span class="sxs-lookup"><span data-stu-id="b028e-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="b028e-104">기본 제공 Office 365 Content Delivery Network(CDN)을 사용하여 정적 자산을 호스팅하여 SharePoint Online 페이지의 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="b028e-105">Office 365 CDN은 정적 자산을 요청하는 브라우저에 더 가깝게 캐싱하여 성능을 향상시켜 다운로드 속도를 높이고 대기 시간을 줄이는 데 기여합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="b028e-106">또한 이 Office 365 CDN 향상된 압축 및 HTTP 파이프라이너를 위해 [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="b028e-107">Office 365 CDN 서비스는 SharePoint Online 구독의 일부로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-108">이 Office 365 CDN 프로덕션(전 세계) 클라우드의  테넌트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="b028e-109">미국 정부, 중국 및 독일 클라우드의 테넌트는 현재 이 서비스를 지원하지 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="b028e-110">Office 365 CDN은 여러 위치, 즉 _출발지_ 에 정적 자산을 호스트하고 글로벌 고속 네트워크에서 제공할 수 있는 여러 CDN으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="b028e-111">Office 365 CDN에서 호스팅하려는 콘텐츠의 종류에 따라 **공개** 출처, **비공개** 출처 또는 둘 다를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="b028e-112">공개 [원본과](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) 개인 출처 간의 차이점에 대한 자세한 내용은 각 출처가 공개 또는 비공개인지 선택을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="b028e-113">![Office 365 CDN 다이어그램](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="b028e-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="b028e-114">CDNS 작동 방식에 이미 익숙한 경우 테넌트에 대해 CDNS를 사용하도록 설정하기 위해 몇 Office 365 CDN만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="b028e-115">이 항목에서는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-115">This topic describes how.</span></span> <span data-ttu-id="b028e-116">정적 자산 호스팅을 시작하는 방법에 대한 자세한 내용을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="b028e-117">특수 사용 시나리오에 대해 Office 365 사용할 수 있는 다른 Microsoft 호스팅 CDNS가 있지만 이 항목에서는 이러한 CDNS가 특정 시나리오의 범위를 벗어날 수 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="b028e-118">자세한 내용은 기타 [Microsoft CDNs를 참조하세요.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="b028e-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="b028e-119">**에 대한 네트워크 계획 및 성능 [조정으로 Office 365.](./network-planning-and-performance.md)**</span><span class="sxs-lookup"><span data-stu-id="b028e-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="b028e-120">Office 365 CDN Online의 SharePoint 개요</span><span class="sxs-lookup"><span data-stu-id="b028e-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="b028e-121">조직에 대한 Office 365 CDN 설정하기 위해 다음 기본 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="b028e-122">배포 계획 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="b028e-123">에서 호스트할 정적 [자산을 CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="b028e-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="b028e-124">[자산을 저장할 위치를 결정하십시오.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="b028e-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="b028e-125">이 위치는 SharePoint, 라이브러리 또는 폴더일 수 있으며 원점이라고 _합니다._</span><span class="sxs-lookup"><span data-stu-id="b028e-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="b028e-126">[각 원본이 공용인지 비공개인지를 선택 합니다.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="b028e-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="b028e-127">공용 형식과 개인 형식의 원본을 여러 개 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="b028e-128">PowerShell 또는 CDN Online CLI를 사용하여 SharePoint 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="b028e-129">온라인 관리 셸을 CDN 설정 및 SharePoint 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="b028e-130">PnP PowerShell을 CDN 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="b028e-131">CLI를 사용하여 CDN 설정 및 Office 365 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="b028e-132">이 단계를 완료하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="b028e-133">조직에 CDN 사용하도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="b028e-134">출처가 추가되었습니다. 각 원점은 공개 또는 비공개로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="b028e-135">설치가 완료되면 다음을 수행하여 Office 365 CDN [수](use-microsoft-365-cdn-with-spo.md#CDNManage) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="b028e-136">자산 추가, 업데이트 및 제거</span><span class="sxs-lookup"><span data-stu-id="b028e-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="b028e-137">원본 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="b028e-137">Adding and removing origins</span></span>
+ <span data-ttu-id="b028e-138">정책 CDN 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="b028e-139">필요한 경우 이 응용 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="b028e-140">마지막으로, [CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) 자산을 사용하여 공개 및 개인 출처에서 CDN 자산에 액세스하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="b028e-141">일반적인 [문제를 Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) 지침은 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="b028e-142">배포 계획 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="b028e-143">Office 365 CDN 테넌트에 Office 365 배포하기 전에 계획 프로세스의 일부로 다음 요소를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="b028e-144">설정에서 호스트할 정적 자산을 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="b028e-145">자산을 저장할 위치 결정</span><span class="sxs-lookup"><span data-stu-id="b028e-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="b028e-146">각 출처를 공개 또는 비공개로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="b028e-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="b028e-148">설정에서 호스트할 정적 자산을 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="b028e-149">일반적으로 CDNS는 정적 자산 또는 자주 변경되지 않는 자산을 호스팅하는 데 가장 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="b028e-150">이러한 조건의 일부 또는 전체를 충족하는 파일을 식별하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="b028e-151">페이지에 포함된 정적 파일(예: 스크립트 및 이미지)이 페이지 로드 시간의 증분에 큰 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="b028e-152">실행 파일 및 설치 파일과 같은 큰 파일</span><span class="sxs-lookup"><span data-stu-id="b028e-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="b028e-153">클라이언트 쪽 코드를 지원하는 리소스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b028e-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="b028e-154">예를 들어 사이트 이미지 및 스크립트와 같이 반복적으로 요청되는 작은 파일은 사이트 렌더링 성능을 크게 개선하고 SharePoint Online 사이트에 대한 로드를 CDN 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="b028e-155">설치 실행 파일과 같은 더 큰 파일은 CDN 다운로드할 수 있으며, 이러한 파일을 자주 액세스하지 않는 경우에도 SharePoint Online 사이트의 부하가 감소하고 성능에 긍정적인 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="b028e-156">파일 기준의 성능 향상은 클라이언트가 가장 가까운 CDN, 로컬 네트워크의 일시적 조건 등을 비롯한 여러 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="b028e-157">많은 정적 파일은 매우 작고 1초 Office 365 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="b028e-158">그러나 웹 페이지에는 몇 초의 누적 다운로드 시간이 포함된 여러 파일이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="b028e-159">파일에서 이러한 파일을 CDN 전체 페이지 로드 시간을 크게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="b028e-160">성능 [향상에 대한](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) CDN 예시를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="b028e-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="b028e-162">자산을 저장할 위치 결정</span><span class="sxs-lookup"><span data-stu-id="b028e-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="b028e-163">이 CDN 원본 이라는 위치에서 자산을 _페치합니다._</span><span class="sxs-lookup"><span data-stu-id="b028e-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="b028e-164">원본은 URL에서 액세스할 SharePoint 사이트, 문서 라이브러리 또는 폴더일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="b028e-165">조직의 출처를 지정할 때 유연성이 뛰어나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="b028e-166">예를 들어 여러 원점 또는 모든 원본 자산을 넣을 단일 원본을 지정할 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="b028e-167">조직에 대한 공개 출처 또는 비공개 출처를 둘 다 찾게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="b028e-168">대부분의 조직에서는 둘의 조합을 구현하기로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="b028e-169">폴더 또는 문서 라이브러리와 같은 원본에 대한 새 컨테이너를 만들고 원본에서 사용할 수 있도록 할 파일을 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="b028e-170">이 방법은 CDN 사용할 특정 자산 집합이 있으며 컨테이너의 파일로만 CDN 자산 집합을 제한하려는 경우 좋은 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="b028e-171">기존 사이트 모음, 사이트, 라이브러리 또는 폴더를 원본으로 구성하여 컨테이너의 모든 적합한 자산을 원본으로 구성할 수도 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="b028e-172">기존 컨테이너를 원본으로 추가하기 전에 익명 액세스나 권한이 없는 사용자에게 자산을 부수적으로 노출하지 못하게 콘텐츠 및 사용 권한을 알고 있는지를 반드시 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="b028e-173">원본의 _콘텐츠를_ CDN 정책을 정의하여 원본에서 콘텐츠를 제외할 수 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="b028e-174">CDN 정책은 파일 형식 및 사이트 분류와 같은  특성에 따라 공개 또는 개인 출처의 자산을 제외하며 정책에서 지정한 CdnType(개인 또는 공용)의 모든 원본에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="b028e-175">예를 들어 여러 하위 사이트가 포함된 사이트로 구성된 비공개 출처를 추가하는 경우 기밀로 표시된  사이트를 제외하는 정책을 정의하여 분류가 적용된 사이트의 콘텐츠가 해당 사이트에서 제공되지 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="b028e-176">정책은 해당 정책에  추가한 모든 비공개 출처의 콘텐츠에 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="b028e-177">원점 수가 클수록 서비스에서 요청을 처리하기 위해 CDN 영향을 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="b028e-178">가능한 한 원점 수를 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="b028e-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="b028e-180">각 출처를 공개 또는 비공개로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="b028e-181">출처를 식별할 때 출처를 공개 또는 비공개로 _지정할지_ 여부를 _지정합니다._</span><span class="sxs-lookup"><span data-stu-id="b028e-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="b028e-182">공개 CDN 자산에 대한 액세스는 익명이며, CDN 원본의 콘텐츠는 동적으로 생성된 토큰을 통해 보호되어 보안을 강화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="b028e-183">선택한 옵션에 관계없이 Microsoft는 사용자 자체의 관리와 관련하여 모든 CDN 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="b028e-184">또한 나중에 정보를 설정하고 출처를 식별한 CDN 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="b028e-185">공개 옵션과 개인 옵션 모두 비슷한 성능 이점을 제공하지만 각각 고유한 특성과 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="b028e-186">**웹** 사이트 내의 공개 Office 365 CDN 익명으로 액세스할 수 있으며, 자산 URL이 있는 모든 사용자가 호스팅된 자산에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="b028e-187">공개 출처의 콘텐츠에 대한 액세스는 익명이기 때문에 JavaScript 파일, 스크립트, 아이콘, 이미지와 같은 민감하지 않은 일반 콘텐츠를 캐시하기 위해서만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="b028e-188">**사이트** 내의 비공개 출처는 Office 365 CDN 온라인 문서 라이브러리, 사이트 및 소유 이미지와 SharePoint 콘텐츠에 대한 개인 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="b028e-189">비공개 원본의 콘텐츠에 대한 액세스는 동적으로 생성된 토큰을 통해 보호되어 원본 문서 라이브러리 또는 저장 위치에 대한 사용 권한이 있는 사용자만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="b028e-190">Office 365 CDN 원본은 SharePoint Online 콘텐츠에만 사용할 수 있으며, SharePoint Online 테넌트에서 리디렉션을 통해 개인 출처의 자산에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="b028e-191">개인 출처의 자산에 대한 액세스 권한을 CDN 방법에 대한 자세한 내용은 [Using assets in private origins에서 을(를)](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)읽어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="b028e-192">공개 출처에서 자산을 호스팅하는 특성 및 이점</span><span class="sxs-lookup"><span data-stu-id="b028e-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="b028e-193">공개 출처에 노출된 자산은 모든 사람이 익명으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="b028e-194">사용자 정보를 포함하거나 조직에 중요한 것으로 간주되는 리소스를 공개 출처에 두면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="b028e-195">공개 출처에서 자산을 제거하는 경우 자산은 캐시에서 최대 30일 동안 계속 사용할 수 있습니다. 그러나 15분 이내에 자산에 대한 CDN 무효화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="b028e-196">공개 원본에서 스타일시트(CSS 파일)를 호스팅하는 경우 코드 내에서 상대 경로 및 URIS를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="b028e-197">즉, 배경 이미지 및 기타 개체의 위치를 호출하는 자산의 위치를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="b028e-198">공개 출처의 URL을 구성할 수 있는 동안에는 신중하게 진행하고 페이지 컨텍스트 속성을 활용하고 이에 대한 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="b028e-199">이 때문에 CDN 액세스할 수 없게 되는 경우 URL이 SharePoint Online의 조직으로 자동으로 확인되지 않고 링크 및 기타 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="b028e-200">또한 URL은 변경될 수 있습니다. 이 때문에 현재 값으로 하드 코딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="b028e-201">공개 원본에 포함된 기본 파일 형식은 .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff 및 .woff2입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="b028e-202">추가 파일 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="b028e-203">지정한 사이트 분류로 식별된 자산을 제외하도록 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="b028e-204">예를 들어 허용된 파일 형식이고 공개 출처에 있는 경우에도 "기밀" 또는 "제한"으로 표시된 모든 자산을 제외하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="b028e-205">개인 출처에서 자산을 호스팅하는 특성 및 이점</span><span class="sxs-lookup"><span data-stu-id="b028e-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="b028e-206">개인 출처는 온라인 자산에 SharePoint 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="b028e-207">사용자는 컨테이너에 액세스할 수 있는 권한이 있는 경우 개인 출처의 자산에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="b028e-208">이러한 자산에 대한 익명 액세스는 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="b028e-209">비공개 출처의 자산은 온라인 테넌트에서 SharePoint 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="b028e-210">개인 CDN 직접 액세스가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="b028e-211">개인 출처에서 자산을 제거하는 경우 캐시에서 최대 1시간 동안 자산을 계속 사용할 수 있습니다. 그러나 자산이 제거된 후 CDN 자산에 대한 링크가 무효화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="b028e-212">비공개 .gif 원본에 포함된 기본 파일 형식은 .ico, .jpeg, .jpg, .js 및 .png.</span><span class="sxs-lookup"><span data-stu-id="b028e-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="b028e-213">추가 파일 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="b028e-214">공개 출처와 마찬가지로, 와일드카드를 사용하여 폴더 또는 문서 라이브러리 내의 모든 자산을 포함하기 위해 지정한 사이트 분류로 식별된 자산을 제외하도록 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="b028e-215">Office 365 CDN, 일반 CDN 개념 및 Office 365 사용할 수 있는 기타 Microsoft CDNS를 사용하는 이유에 대한 자세한 내용은 [Content Delivery Networks를 참조하세요.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="b028e-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="b028e-216">기본 CDN 원본</span><span class="sxs-lookup"><span data-stu-id="b028e-216">Default CDN origins</span></span>

<span data-ttu-id="b028e-217">달리 지정하지 않는 한, Office 365 사용하도록 설정할 때 기본 출처를 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b028e-218">처음에 프로비전하지 않을 경우 설치를 완료한 후 이러한 원본을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="b028e-219">기본 원본 설정을 건너뛰는 경우의 결과를 이해하고 특정 이유가 없는 한 기본 원본을 사용하도록 설정할 때 만들 수 있도록 허용해야 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="b028e-220">기본 개인 CDN 원본:</span><span class="sxs-lookup"><span data-stu-id="b028e-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="b028e-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="b028e-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="b028e-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="b028e-222">\*/siteassets</span></span>

<span data-ttu-id="b028e-223">기본 공용 CDN 원본:</span><span class="sxs-lookup"><span data-stu-id="b028e-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="b028e-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="b028e-224">\*/masterpage</span></span>
+ <span data-ttu-id="b028e-225">\*/style library</span><span class="sxs-lookup"><span data-stu-id="b028e-225">\*/style library</span></span>
+ <span data-ttu-id="b028e-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="b028e-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-227">_clientsideassets는_ 2017년 12월에 Office 365 CDN 서비스에 추가된 기본 공개 출처입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="b028e-228">이 원본은 원본 원본이 SharePoint 프레임워크 솔루션이 작동하려면 CDN 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="b028e-229">2017년 12월 이전에 Office 365 CDN 또는 기본 원본 설정을 건너뛴 경우 CDN 원본을 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="b028e-230">자세한 내용은 클라이언트 쪽 웹 파트 또는 SharePoint 프레임워크 [작동하지 않습니다.를 참조하세요.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="b028e-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="b028e-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="b028e-232">온라인 관리 셸을 Office 365 CDN 설정 및 SharePoint 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="b028e-233">이 섹션의 절차를 수행하려면 SharePoint Online에 연결하기 위해 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="b028e-234">자세한 내용은 커넥트 [PowerShell을 SharePoint 참조하세요.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="b028e-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="b028e-235">다음 단계를 완료하여 CDN Online 관리 셸을 사용하여 SharePoint 자산을 호스트하도록 SharePoint 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="b028e-236">클릭하여 확장</span><span class="sxs-lookup"><span data-stu-id="b028e-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b028e-237">조직에서 조직에서 다음을 사용하도록 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b028e-238">테넌트 CDN 변경하기 전에 CDN 테넌트에서 private CDN 구성의 현재 상태를 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b028e-239">커넥트 온라인 관리 셸을 사용하여 테넌트에 SharePoint 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="b028e-240">이제 **Get-SPOTenantCdnEnabled** cmdlet을 사용하여 테넌트에서 CDN 상태 설정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b028e-241">지정한 CDN CdnType의 상태는 화면에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b028e-242">**Set-SPOTenantCdnEnabled** cmdlet을 사용하여 조직에서 이 응용 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b028e-243">조직에서 공개 출처, 비공개 출처 또는 둘 다를 한에 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="b028e-244">기본 원본 설정을 CDN 건너뛰도록 기본 원본 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b028e-245">이 항목에 설명된 바와 같이 언제든지 이러한 출처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="b028e-246">온라인 Windows PowerShell 대한 SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b028e-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b028e-247">예를 들어 조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b028e-248">조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 하지만 기본 원본 설정을 건너뛰기 위해 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b028e-249">기본 [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) 사용하도록 설정할 때 기본적으로 프로비전되는 원본에 대한 자세한 Office 365 CDN 기본 원본 설정을 건너뛰는 경우의 잠재적인 영향에 대한 자세한 내용은 Default CDN origins를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b028e-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b028e-250">조직에서 공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b028e-251">조직에서 비공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b028e-252">이 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="b028e-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="b028e-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b028e-254">파일 형식 목록에 포함할 파일 형식 목록 Office 365 CDN(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b028e-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b028e-255">**Set-SPOTenantCdnPolicy** cmdlet을 사용하여 파일 형식을 정의하는 경우 현재 정의된 목록을 덮어 덮어 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b028e-256">목록에 추가 파일 형식을 추가하려는 경우 먼저 cmdlet을 사용하여 이미 허용된 파일 형식을 찾아 새 파일 형식과 함께 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="b028e-257">**Set-SPOTenantCdnPolicy** cmdlet을 사용하여 공용 및 개인 원본에서 호스팅할 수 있는 정적 파일 형식을 정의할 수 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b028e-258">기본적으로 일반적인 자산 유형(예: .css, .gif, .jpg 및 .js.</span><span class="sxs-lookup"><span data-stu-id="b028e-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b028e-259">온라인 Windows PowerShell 대한 SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b028e-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b028e-260">예를 들어. CDN .css 및 .png 호스트할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b028e-261">현재 허용되는 파일 형식을 CDN **Get-SPOTenantCdnPolicies** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b028e-262">이러한 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 및 [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b028e-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b028e-264">목록에서 제외할 사이트 분류 목록 Office 365 CDN(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b028e-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b028e-265">**Set-SPOTenantCdnPolicy** cmdlet을 사용하여 사이트 분류를 제외하는 경우 현재 정의된 목록을 덮어 덮어 덮어입습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b028e-266">추가 사이트 분류를 제외하려는 경우 먼저 cmdlet을 사용하여 이미 제외된 분류를 확인한 다음 새 분류와 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b028e-267">**Set-SPOTenantCdnPolicy** cmdlet을 사용하여 사이트 분류에서 사용할 수 있도록 설정하지 않을 사이트 분류를 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b028e-268">기본적으로 사이트 분류는 제외되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b028e-269">온라인 Windows PowerShell 대한 SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b028e-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="b028e-270">현재 제한된 사이트 분류를 표시하기 위해 **Get-SPOTenantCdnPolicies** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b028e-271">반환될 속성은 _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ 및 _ExcludeIfNoScriptDisabled입니다._</span><span class="sxs-lookup"><span data-stu-id="b028e-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b028e-272">_IncludeFileExtensions_ 속성에는 해당 속성에서 제공될 파일 확장명 목록이 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-273">기본 파일 확장명은 public과 private 간에 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b028e-274">_ExcludeRestrictedSiteClassifications_ 속성에는 목록에서 제외하려는 사이트 분류가 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b028e-275">예를 들어 기밀로 표시된  사이트를 제외하여 분류가 적용된 사이트의 콘텐츠가 해당 사이트에서 제공되지 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b028e-276">_ExcludeIfNoScriptDisabled_ 속성은 사이트 수준 _noScript_ 특성 CDN 콘텐츠는 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b028e-277">기본적으로 _NoScript_ 특성은 최신 사이트에 대해 **사용으로** 설정되어 _있으며_ 클래식 사이트에는 **사용** _안 하게_ 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b028e-278">이는 테넌트 설정에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="b028e-279">이러한 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) 및 [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b028e-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b028e-281">자산의 원점 추가</span><span class="sxs-lookup"><span data-stu-id="b028e-281">Add an origin for your assets</span></span>

<span data-ttu-id="b028e-282">**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 원점 정의</span><span class="sxs-lookup"><span data-stu-id="b028e-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b028e-283">여러 원본을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-283">You can define multiple origins.</span></span> <span data-ttu-id="b028e-284">원본은 웹 응용 SharePoint 호스트할 자산이 포함된 SharePoint 폴더를 지정하는 url입니다CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b028e-285">사용자 정보를 포함하거나 조직에 중요한 것으로 간주되는 리소스를 공개 출처에 두면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b028e-286">_path_ 값은 자산이 포함된 라이브러리 또는 폴더의 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b028e-287">상대 경로와 함께 와일드카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b028e-288">원본은 URL에 추가된 와일드카드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b028e-289">이렇게 하면 여러 사이트에 걸쳐 있는 원본을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b028e-290">예를 들어 모든 사이트의 masterpages 폴더에 모든 자산을 CDN 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b028e-291">와일드카드 수정자 \*는 경로의 시작에만 사용할 수 있으며 지정된 URL 아래에 있는 **/** 모든 URL 세그먼트와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b028e-292">경로는 문서 라이브러리, 폴더 또는 사이트를 포인터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b028e-293">예를 들어 _경로 \*/site1은_ 사이트의 모든 문서 라이브러리와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b028e-294">특정 상대 경로를 사용하여 원점을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b028e-295">전체 경로를 사용하여 원점은 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b028e-296">이 예제에서는 특정 사이트에서 siteassets 라이브러리의 개인 출처를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b028e-297">이 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _folder1_ 폴더의 개인 출처를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b028e-298">경로에 공백이 있는 경우 경로를 작은 따옴표로 둘러싸거나 공백을 URL 인코딩 %20으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b028e-299">다음 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _폴더 1_ 폴더의 개인 출처를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b028e-300">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-301">개인 출처에서 공유되는 자산은 원본에서 공유되는 주 버전을 게시해야만 해당 원본에서 액세스할 수 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="b028e-302">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-303">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b028e-305">예제: 마스터 페이지 및 온라인용 스타일 라이브러리에 대한 공개 SharePoint 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b028e-306">일반적으로 이러한 원본은 사용자 지정 원본을 사용하도록 설정할 때 기본적으로 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b028e-307">그러나 수동으로 사용하도록 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="b028e-308">**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 스타일 라이브러리를 공용 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b028e-309">**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 마스터 페이지를 공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b028e-310">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b028e-311">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-312">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b028e-314">예: SharePoint Online에 대한 사이트 자산, 사이트 페이지 및 게시 이미지에 대한 비공개 출처 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b028e-315">**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 사이트 자산 폴더를 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b028e-316">**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 사이트 페이지 폴더를 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b028e-317">**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 게시 이미지 폴더를 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b028e-318">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b028e-319">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-320">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b028e-322">예: SharePoint Online의 사이트 모음에 대한 비공개 출처 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b028e-323">**Add-SPOTenantCdnOrigin** cmdlet을 사용하여 사이트 모음을 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b028e-324">예제:</span><span class="sxs-lookup"><span data-stu-id="b028e-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b028e-325">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="b028e-326">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-327">SharePoint Online  테넌트가 SharePoint 서비스로 연결될 것으로 예상되는 구성 보류 중인 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b028e-328">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b028e-330">관리 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b028e-331">구성을 설정한 CDN 이 섹션에 설명된 바와 같이 콘텐츠를 업데이트하거나 요구 사항이 변경될 때 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="b028e-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b028e-333">사용자 계정에서 자산을 추가, 업데이트 또는 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b028e-334">설치 단계를 완료한 후 원하는 경우 새 자산을 추가하고 기존 자산을 업데이트하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b028e-335">원본으로 식별한 폴더 또는 SharePoint 자산을 변경하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b028e-336">새 자산을 추가하는 경우 자산을 즉시 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b028e-337">그러나 자산을 업데이트하는 경우 새 복사본이 전파되어 해당 자산에서 사용 가능한 데 최대 15분이 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="b028e-338">원점의 위치를 검색해야 하는 경우 **Get-SPOTenantCdnOrigins** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="b028e-339">이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Get-SPOTenantCdnOrigins 를 참조하세요.](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)</span><span class="sxs-lookup"><span data-stu-id="b028e-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="b028e-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b028e-341">원본을 원본에서 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b028e-342">원본으로 식별한 폴더 또는 SharePoint 라이브러리에 대한 액세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b028e-343">이렇게하려면 **Remove-SPOTenantCdnOrigin** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b028e-344">이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Remove-SPOTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b028e-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b028e-346">원본의 원본을 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b028e-347">만든 원본은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b028e-348">대신 원점은 제거한 다음 새 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b028e-349">자세한 내용은 원본에서 원본을 제거하려면 Office 365 CDN 자산의 원점 [추가를 참조하세요.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh) [](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="b028e-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="b028e-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b028e-351">이 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b028e-352">**Set-SPOTenantCdnEnabled** cmdlet을 사용하여 조직에 대한 CDN 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b028e-353">공용 원본과 개인 원본을 모두 사용하도록 CDN 다음 예제와 같이 cmdlet을 두 번 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="b028e-354">원본에서 공용 출처를 사용하지 CDN 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b028e-355">원본에서 개인 출처를 사용하지 CDN 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b028e-356">이 cmdlet에 대한 자세한 내용은 [Set-SPOTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="b028e-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="b028e-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="b028e-358">PnP PowerShell을 Office 365 CDN 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="b028e-359">이 섹션의 절차를 수행하려면 PnP PowerShell을 사용하여 온라인에 SharePoint 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="b028e-360">자세한 내용은 [PnP PowerShell 시작을 참조하세요.](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="b028e-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="b028e-361">PnP PowerShell을 사용하여 CDN 자산을 호스트하도록 SharePoint 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="b028e-362">클릭하여 확장</span><span class="sxs-lookup"><span data-stu-id="b028e-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b028e-363">조직에서 조직에서 다음을 사용하도록 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b028e-364">테넌트 CDN 변경하기 전에 CDN 테넌트에서 private CDN 구성의 현재 상태를 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b028e-365">커넥트 PnP PowerShell을 사용하여 테넌트에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="b028e-366">이제 **Get-PnPTenantCdnEnabled** cmdlet을 사용하여 테넌트에서 CDN 상태 설정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b028e-367">지정한 CDN CdnType의 상태는 화면에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b028e-368">**Set-PnPTenantCdnEnabled cmdlet을 사용하여 조직에서 Set-PnPTenantCdnEnabled** cmdlet을 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b028e-369">조직에서 공개 출처, 비공개 출처 또는 둘 다를 동시에 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="b028e-370">기본 원본 설정을 CDN 건너뛰도록 기본 원본 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b028e-371">이 항목에 설명된 바와 같이 언제든지 이러한 출처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="b028e-372">PnP PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="b028e-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b028e-373">예를 들어 조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b028e-374">조직에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 하지만 기본 원본 설정을 건너뛰기 위해 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b028e-375">기본 [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) 사용하도록 설정할 때 기본적으로 프로비전되는 원본에 대한 자세한 Office 365 CDN 기본 원본 설정을 건너뛰는 경우의 잠재적인 영향에 대한 자세한 내용은 Default CDN origins를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b028e-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b028e-376">조직에서 공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b028e-377">조직에서 비공개 출처를 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b028e-378">이 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="b028e-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="b028e-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b028e-380">파일 형식 목록에 포함할 파일 형식 목록 Office 365 CDN(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b028e-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b028e-381">**Set-PnPTenantCdnPolicy** cmdlet을 사용하여 파일 형식을 정의하는 경우 현재 정의된 목록을 덮어 덮어 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b028e-382">목록에 추가 파일 형식을 추가하려는 경우 먼저 cmdlet을 사용하여 이미 허용된 파일 형식을 찾아 새 파일 형식과 함께 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="b028e-383">**Set-PnPTenantCdnPolicy** cmdlet을 사용하여 공용 및 개인 원본에서 호스팅할 수 있는 정적 파일 형식을 정의할 수 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b028e-384">기본적으로 일반적인 자산 유형(예: .css, .gif, .jpg 및 .js.</span><span class="sxs-lookup"><span data-stu-id="b028e-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b028e-385">PnP PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="b028e-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b028e-386">예를 들어. CDN .css 및 .png 호스트할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b028e-387">현재 허용되는 파일 형식을 CDN **Get-PnPTenantCdnPolicies** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b028e-388">이러한 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 및 [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b028e-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b028e-390">목록에서 제외할 사이트 분류 목록 Office 365 CDN(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b028e-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b028e-391">**Set-PnPTenantCdnPolicy** cmdlet을 사용하여 사이트 분류를 제외하는 경우 현재 정의된 목록을 덮어 덮어 덮어입습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b028e-392">추가 사이트 분류를 제외하려는 경우 먼저 cmdlet을 사용하여 이미 제외된 분류를 확인한 다음 새 분류와 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b028e-393">**Set-PnPTenantCdnPolicy** cmdlet을 사용하여 사이트 분류에서 사용할 수 있도록 설정하지 않을 사이트 분류를 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b028e-394">기본적으로 사이트 분류는 제외되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b028e-395">PnP PowerShell에서:</span><span class="sxs-lookup"><span data-stu-id="b028e-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="b028e-396">현재 제한되는 사이트 분류를 표시하기 위해 **Get-PnPTenantCdnPolicies** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b028e-397">반환될 속성은 _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ 및 _ExcludeIfNoScriptDisabled입니다._</span><span class="sxs-lookup"><span data-stu-id="b028e-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b028e-398">_IncludeFileExtensions_ 속성에는 해당 속성에서 제공될 파일 확장명 목록이 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-399">기본 파일 확장명은 public과 private 간에 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b028e-400">_ExcludeRestrictedSiteClassifications_ 속성에는 목록에서 제외하려는 사이트 분류가 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b028e-401">예를 들어 기밀로 표시된  사이트를 제외하여 분류가 적용된 사이트의 콘텐츠가 해당 사이트에서 제공되지 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b028e-402">_ExcludeIfNoScriptDisabled_ 속성은 사이트 수준 _noScript_ 특성 CDN 콘텐츠는 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b028e-403">기본적으로 _NoScript_ 특성은 최신 사이트에 대해 **사용으로** 설정되어 _있으며_ 클래식 사이트에는 **사용** _안 하게_ 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b028e-404">이는 테넌트 설정에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="b028e-405">이러한 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) 및 [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b028e-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b028e-407">자산의 원점 추가</span><span class="sxs-lookup"><span data-stu-id="b028e-407">Add an origin for your assets</span></span>

<span data-ttu-id="b028e-408">**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 원점 정의</span><span class="sxs-lookup"><span data-stu-id="b028e-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b028e-409">여러 원본을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-409">You can define multiple origins.</span></span> <span data-ttu-id="b028e-410">원본은 웹 응용 SharePoint 호스트할 자산이 포함된 SharePoint 폴더를 지정하는 url입니다CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b028e-411">사용자 정보를 포함하거나 조직에 중요한 것으로 간주되는 리소스를 공개 출처에 두면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b028e-412">_path_ 값은 자산이 포함된 라이브러리 또는 폴더의 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b028e-413">상대 경로와 함께 와일드카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b028e-414">원본은 URL에 추가된 와일드카드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b028e-415">이렇게 하면 여러 사이트에 걸쳐 있는 원본을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b028e-416">예를 들어 모든 사이트의 masterpages 폴더에 모든 자산을 CDN 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b028e-417">와일드카드 수정자 \*는 경로의 시작에만 사용할 수 있으며 지정된 URL 아래에 있는 **/** 모든 URL 세그먼트와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b028e-418">경로는 문서 라이브러리, 폴더 또는 사이트를 포인터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b028e-419">예를 들어 _경로 \*/site1은_ 사이트의 모든 문서 라이브러리와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b028e-420">특정 상대 경로를 사용하여 원점을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b028e-421">전체 경로를 사용하여 원점은 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b028e-422">이 예제에서는 특정 사이트에서 사이트 자산 라이브러리의 개인 출처를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b028e-423">이 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _folder1_ 폴더의 개인 출처를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b028e-424">경로에 공백이 있는 경우 경로를 작은 따옴표로 둘러싸거나 공백을 URL 인코딩 %20으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b028e-425">다음 예제에서는 사이트 모음의 사이트 자산 라이브러리에 있는 _폴더 1_ 폴더의 개인 출처를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b028e-426">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-427">개인 출처에서 공유되는 자산은 원본에서 공유되는 주 버전을 게시해야만 해당 원본에서 액세스할 수 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="b028e-428">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-429">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b028e-431">예제: 마스터 페이지 및 온라인용 스타일 라이브러리에 대한 공개 SharePoint 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b028e-432">일반적으로 이러한 원본은 사용자 지정 원본을 사용하도록 설정할 때 기본적으로 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b028e-433">그러나 수동으로 사용하도록 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b028e-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="b028e-434">**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 스타일 라이브러리를 공용 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b028e-435">**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 마스터 페이지를 공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b028e-436">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b028e-437">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-438">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b028e-440">예: SharePoint Online에 대한 사이트 자산, 사이트 페이지 및 게시 이미지에 대한 비공개 출처 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b028e-441">**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 사이트 자산 폴더를 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b028e-442">**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 사이트 페이지 폴더를 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b028e-443">**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 게시 이미지 폴더를 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b028e-444">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b028e-445">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-446">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b028e-448">예: SharePoint Online의 사이트 모음에 대한 비공개 출처 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b028e-449">**Add-PnPTenantCdnOrigin** cmdlet을 사용하여 사이트 모음을 비공개 원본으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b028e-450">예제:</span><span class="sxs-lookup"><span data-stu-id="b028e-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b028e-451">이 명령 및 해당 구문에 대한 자세한 내용은 [Add-PnPTenantCdnOrigin 을 참조하세요.](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="b028e-452">명령을 실행하면 시스템에서 데이터 센터 전체에서 구성을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b028e-453">SharePoint Online  테넌트가 SharePoint 서비스로 연결될 것으로 예상되는 구성 보류 중인 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b028e-454">최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b028e-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b028e-456">관리 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b028e-457">구성을 설정한 CDN 이 섹션에 설명된 바와 같이 콘텐츠를 업데이트하거나 요구 사항이 변경될 때 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="b028e-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b028e-459">사용자 계정에서 자산을 추가, 업데이트 또는 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b028e-460">설치 단계를 완료한 후 원하는 경우 새 자산을 추가하고 기존 자산을 업데이트하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b028e-461">원본으로 식별한 폴더 또는 SharePoint 자산을 변경하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b028e-462">새 자산을 추가하는 경우 자산을 즉시 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b028e-463">그러나 자산을 업데이트하는 경우 새 복사본이 전파되어 해당 자산에서 사용 가능한 데 최대 15분이 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="b028e-464">원점의 위치를 검색해야 하는 경우 **Get-PnPTenantCdnOrigin** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="b028e-465">이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Get-PnPTenantCdnOrigin을 참조하십시오.](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b028e-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b028e-467">원본을 원본에서 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b028e-468">원본으로 식별한 폴더 또는 SharePoint 라이브러리에 대한 액세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b028e-469">이렇게하려면 **Remove-PnPTenantCdnOrigin** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b028e-470">이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Remove-PnPTenantCdnOrigin을 참조하십시오.](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="b028e-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b028e-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b028e-472">원본의 원본을 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b028e-473">만든 원본은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b028e-474">대신 원점은 제거한 다음 새 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b028e-475">자세한 내용은 원본에서 원본을 제거하려면 Office 365 CDN 자산의 원점 [추가를 참조하세요.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh) [](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="b028e-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="b028e-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b028e-477">이 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b028e-478">**Set-PnPTenantCdnEnabled** cmdlet을 사용하여 조직의 CDN 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b028e-479">공용 원본과 개인 원본을 모두 사용하도록 CDN 다음 예제와 같이 cmdlet을 두 번 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="b028e-480">원본에서 공용 출처를 사용하지 CDN 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b028e-481">원본에서 개인 출처를 사용하지 CDN 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b028e-482">이 cmdlet에 대한 자세한 내용은 [Set-PnPTenantCdnEnabled 를 참조하세요.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="b028e-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="b028e-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="b028e-484">CLI를 사용하여 Office 365 CDN 설정 및 Office 365 구성</span><span class="sxs-lookup"><span data-stu-id="b028e-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="b028e-485">이 섹션의 절차를 수행하려면 CLI 를 [설치해야 Office 365 합니다.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="b028e-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="b028e-486">그런 다음 로그인 명령을 Office 365 테넌트에 [연결합니다.](https://pnp.github.io/office365-cli/cmd/login/)</span><span class="sxs-lookup"><span data-stu-id="b028e-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="b028e-487">CLI를 사용하여 CDN 온라인에서 자산을 호스트하도록 SharePoint 구성하기 위해 다음 Office 365 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="b028e-488">클릭하여 확장</span><span class="sxs-lookup"><span data-stu-id="b028e-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="b028e-489">다음 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="b028e-490">스포 [cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) 집합 명령을 사용하여 테넌트에서 Office 365 CDN 상태를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="b028e-491">테넌트에서 Office 365 Public CDN 실행하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="b028e-492">다음을 Office 365 SharePoint CDN 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="b028e-493">현재 상태 보기 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="b028e-494">특정 유형의 Office 365 CDN 활성화 또는 사용하지 않도록 설정되어 있는지 확인하기 위해 [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="b028e-495">공용 Office 365 사용하도록 CDN 확인을 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="b028e-496">원본 Office 365 CDN 보기</span><span class="sxs-lookup"><span data-stu-id="b028e-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="b028e-497">현재 구성된 공용 Office 365 원본을 CDN 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="b028e-498">기본 [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) 사용하도록 설정할 때 기본적으로 프로비전되는 원본에 대한 자세한 내용은 기본 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="b028e-499">원본 Office 365 CDN 추가</span><span class="sxs-lookup"><span data-stu-id="b028e-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b028e-500">조직에 중요한 것으로 간주되는 리소스를 공용 원본으로 구성된 SharePoint 라이브러리에 두면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="b028e-501">spo [cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) 명령을 사용하여 CDN 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="b028e-502">여러 원본을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-502">You can define multiple origins.</span></span> <span data-ttu-id="b028e-503">원본은 웹 응용 SharePoint 호스트할 자산이 포함된 SharePoint 폴더를 지정하는 url입니다CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="b028e-504">여기서 `path` 은 자산이 포함된 폴더의 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="b028e-505">상대 경로와 함께 와일드카드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="b028e-506">모든 사이트의 마스터 페이지 **갤러리에** 모든 자산을 공개 원본으로 포함하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="b028e-507">특정 사이트 모음에 대해 비공개 원본을 구성하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="b028e-508">원본을 CDN 서비스에서 파일을 검색하는 데 최대 15분이 걸릴 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="b028e-509">spo [cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 출처 목록 명령을 사용하여 특정 원본이 이미 활성화되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="b028e-510">원본 Office 365 CDN 제거</span><span class="sxs-lookup"><span data-stu-id="b028e-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="b028e-511">[spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) 명령을 사용하여 지정된 CDN 원본을 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="b028e-512">공용 원본을 구성에서 제거하려면 CDN 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="b028e-513">원본 CDN 제거해도 해당 원본과 일치하는 문서 라이브러리에 저장된 파일에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="b028e-514">이러한 자산이 해당 SharePoint URL을 사용하여 참조된 SharePoint 자동으로 문서 라이브러리를 SharePoint 원래 URL로 다시 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="b028e-515">그러나 공용 CDN URL을 사용하여 자산을 참조한 경우 원본을 제거하면 링크가 중단되고 수동으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="b028e-516">원본 Office 365 CDN 수정</span><span class="sxs-lookup"><span data-stu-id="b028e-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="b028e-517">기존 원본은 수정할 수 CDN 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="b028e-518">대신 명령을 사용하여 이전에 정의한 CDN 원본을 제거하고 명령을 사용하여 새 원본을 `spo cdn origin remove` 추가해야 `spo cdn origin add` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="b028e-519">파일에 포함할 파일 형식을 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="b028e-520">기본적으로 _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff 및 .woff2_ 파일 형식이 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="b028e-521">파일 형식에 추가 파일 형식을 포함해야 CDN [spo cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 정책 집합 명령을 사용하여 CDN 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-522">파일 형식 목록을 변경할 때 현재 정의된 목록을 덮어 덮어 덮어 니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="b028e-523">추가 파일 형식을 포함하려는 경우 먼저 [spo cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 정책 목록 명령을 사용하여 현재 구성된 파일 형식을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="b028e-524">공용 파일에 포함된 파일 형식의 기본 목록에 _JSON_ 파일 형식을 CDN 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="b028e-525">목록에서 제외할 사이트 분류 목록을 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="b028e-526">[spo cdn 정책 집합](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 명령을 사용하여 사이트 분류에서 사용할 수 있도록 설정하지 않을 사이트 분류를 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b028e-527">기본적으로 사이트 분류는 제외되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-528">제외된 사이트 분류 목록을 변경할 때 현재 정의된 목록을 덮어 덮어 덮어입습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="b028e-529">추가 분류를 제외하려는 경우 먼저 [spo cdn](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) 정책 목록 명령을 사용하여 현재 구성된 분류를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="b028e-530">_HBI로_ 분류된 사이트를 공용 웹 사이트에서 CDN 실행</span><span class="sxs-lookup"><span data-stu-id="b028e-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b028e-531">이 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b028e-532">명령을 사용하지 Office 365 CDN 명령을 사용 합니다. 예를 `spo cdn set` 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="b028e-533">사용자 CDN 사용</span><span class="sxs-lookup"><span data-stu-id="b028e-533">Using your CDN assets</span></span>

<span data-ttu-id="b028e-534">이제 원본 및 정책을 CDN 및 정책을 사용하도록 설정한 후 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="b028e-535">이 섹션에서는 SharePoint 페이지 및 콘텐츠에서 CDN URL을 사용하는 방법을 이해하여 SharePoint 원본과 비공개 원본 모두의 자산에 대한 요청을 해당 url로 리디렉션하는 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="b028e-536">CDN 링크 업데이트</span><span class="sxs-lookup"><span data-stu-id="b028e-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="b028e-537">공개 출처에서 자산 사용</span><span class="sxs-lookup"><span data-stu-id="b028e-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="b028e-538">개인 출처에서 자산 사용</span><span class="sxs-lookup"><span data-stu-id="b028e-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="b028e-539">클라이언트 쪽 웹 파트를 호스팅하는 CDN 방법에 대한 자세한 내용은 [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b028e-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-540">_ClientSideAssets_ 폴더를 개인 CDN  원본 목록에 추가하면 CDN 사용자 지정 웹 파트가 렌더링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="b028e-541">SPFX 웹 파트에서 사용하는 파일은 공용 파일만 사용할 수 CDN ClientSideAssets 폴더는 공용 웹 파트의 기본 원본 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="b028e-542">CDN 링크 업데이트</span><span class="sxs-lookup"><span data-stu-id="b028e-542">Updating links to CDN assets</span></span>

<span data-ttu-id="b028e-543">원본에 추가한 자산을 사용하기 위해 원본 파일의 경로로 원본 파일에 대한 링크를 업데이트하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="b028e-544">원본에 추가한 자산에 대한 링크가 포함된 페이지 또는 콘텐츠를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="b028e-545">또한 링크가 나타나는 모든 곳에서 특정 자산으로 링크를 업데이트하려는 경우 여러 방법 중 하나를 사용하여 입력 사이트 또는 사이트 모음 전체에서 링크를 전역적으로 검색하고 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="b028e-546">원점에 있는 자산에 대한 각 링크에 대해 경로를 원본 파일의 경로로 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="b028e-547">상대 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-547">You can use relative paths.</span></span>
+ <span data-ttu-id="b028e-548">페이지 또는 콘텐츠를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-548">Save the page or content.</span></span>

<span data-ttu-id="b028e-549">예를 들어 이미지 _/site/SiteAssets/images/image.png_ _/site/CDN_origins/public/_ 에 복사했다고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="b028e-550">CDN 원본 경로를 이미지 파일 위치에 대한 원본 경로로 바꾸어 새 URL _/site/site/CDN_origins/public/image.png._</span><span class="sxs-lookup"><span data-stu-id="b028e-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="b028e-551">상대 경로 대신 자산에 대한 전체 URL을 사용하려면 링크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="b028e-552">일반적으로 URL을 해당 URL의 자산으로 직접 하드코딩하면 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="b028e-553">그러나 필요한 경우 공개 출처의 자산에 대한 URL을 수동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="b028e-554">자세한 내용은 [공용 자산에 대한 CDN 하드코드를 참조하세요.](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)</span><span class="sxs-lookup"><span data-stu-id="b028e-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="b028e-555">자산이 에서 제공되고 있는지 확인하는 방법에 대한 자세한 [](use-microsoft-365-cdn-with-spo.md#CDNConfirm) 내용은 CDN 문제 해결에서 CDN 자산이 제공되고 있는지 확인하는 [방법을 Office 365 CDN.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b028e-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="b028e-556">공개 출처에서 자산 사용</span><span class="sxs-lookup"><span data-stu-id="b028e-556">Using assets in public origins</span></span>

<span data-ttu-id="b028e-557">SharePoint  Online의 게시 기능은 공개 원본에 저장된 자산의 URL을 해당 자산의 CDN 해당 url로 자동으로 다시 덮어 CDN 대신 CDN 서비스에서 SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b028e-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="b028e-558">원본이 게시 기능을 사용하도록 설정된 사이트에 있는 경우 CDN로 오프로드할 자산이 다음 범주 중 하나에 있는 경우 SharePoint 정책에 의해 자산이 제외되지 않은 경우 원본에 있는 자산의 URL을 자동으로 다시 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="b028e-559">다음은 게시 기능에서 링크를 자동으로 다시 SharePoint 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="b028e-560">클래식 게시 페이지 HTML 응답의 IMG/LINK/CSS URL</span><span class="sxs-lookup"><span data-stu-id="b028e-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="b028e-561">여기에는 페이지의 HTML 콘텐츠 내에서 작성자가 추가한 이미지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="b028e-562">그림 라이브러리 SlideShow 웹파트 이미지 URL</span><span class="sxs-lookup"><span data-stu-id="b028e-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="b028e-563">SPList REST API(RenderListDataAsStream) 결과의 이미지 필드</span><span class="sxs-lookup"><span data-stu-id="b028e-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="b028e-564">새 속성 _ImageFieldsToTryRewriteToCdnUrls를_ 사용하여 콤보로 구분된 필드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="b028e-565">하이퍼링크 필드 및 PublishingImage 필드 지원</span><span class="sxs-lookup"><span data-stu-id="b028e-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="b028e-566">SharePoint 이미지 Nditions</span><span class="sxs-lookup"><span data-stu-id="b028e-566">SharePoint image renditions</span></span>

<span data-ttu-id="b028e-567">다음 다이어그램은 워크플로를 보여 SharePoint 원본에서 자산이 포함된 페이지에 대한 요청을 받는 경우 워크플로를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="b028e-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="b028e-568">![워크플로 다이어그램: Office 365 CDN 원본에서 자산 검색](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "워크플로: Office 365 CDN 원본에서 자산 검색")</span><span class="sxs-lookup"><span data-stu-id="b028e-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="b028e-569">페이지의 특정 URL에 대해 자동 다시 작성을 사용하지 않도록 설정하려는 경우 페이지를 체크 아웃하고 쿼리 문자열 매개 변수를 추가할 수 **있습니다. NoAutoReWrites=true이면** 사용하지 않도록 설정할 각 링크의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="b028e-570">공용 CDN URL 생성</span><span class="sxs-lookup"><span data-stu-id="b028e-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="b028e-571">게시 _기능이_ 공개 출처에 대해 사용하도록 설정되어 있지 않은 경우 또는 자산이 CDN 서비스의 자동 다시 사용 기능에서 지원되는 링크 유형 중 하나가 아닌 경우 자산의 CDN 위치에 대한 URL을 수동으로 생성하고 콘텐츠에서 이러한 URL을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-572">URL의 마지막 섹션을 구성하는 필수 액세스 토큰은 리소스가 요청될 때 생성되어 CDN 원본에 있는 자산에 대한 URL을 하드코드하거나 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="b028e-573">Public 2013에 대한 URL을 CDN 수 있으며 URL은 변경될 수 있는 하드 코딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="b028e-574">공용 CDN 자산의 경우 URL 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="b028e-575">**TenantHostName을 테넌트** 이름으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="b028e-576">예제:</span><span class="sxs-lookup"><span data-stu-id="b028e-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="b028e-577">페이지 컨텍스트 속성은 하드 코딩 " "대신에 prefix를 구성하는 데 https://publiccdn.sharepointonline.com 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="b028e-578">URL은 변경될 수 있으며 하드 코딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="b028e-579">클래식 SharePoint Online에서 표시 서식 파일을 사용하는 경우 표시 서식 파일에서 URL의 window._spPageContextInfo.publicCdnBaseUrl" 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="b028e-580">최신 SPFx 클래식 웹 파트에 대한 웹 파트를 SharePoint "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="b028e-581">이렇게 하면 변경된 경우 구현이 업데이트될 수 있도록 사전이 제공될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="b028e-582">예를 SPFx URL은 "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item"을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="b028e-583">시리즈 [1](https://youtu.be/IH1RbQlbhIA) CDN 일부인 클라이언트 쪽 코드에서 CDN 코드를 [참조하시기 바랍니다.](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="b028e-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="b028e-584">개인 출처에서 자산 사용</span><span class="sxs-lookup"><span data-stu-id="b028e-584">Using assets in private origins</span></span>

<span data-ttu-id="b028e-585">개인 출처의 자산을 사용하기 위해 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="b028e-586">SharePoint 온라인에서는 개인 출처의 자산에 대한 URL을 자동으로 다시 덮어 찾게 하여 해당 자산에 대한 요청은 항상 원본에서 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="b028e-587">이러한 URL에는 자산이 요청될 때 SharePoint Online에서 자동으로 생성해야 하는 토큰이 포함되어 있기 때문에 개인 출처의 CDN 자산에 대한 URL을 수동으로 빌드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="b028e-588">비공개 출처의 자산에 대한 액세스는 원점에 대한 사용자 권한을 기반으로 동적으로 생성된 토큰으로 보호됩니다. 이 토큰은 다음 섹션에 설명된 주의를 하여 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="b028e-589">콘텐츠를 렌더링하려면  사용자에게 원본에 대한 읽기 CDN 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="b028e-590">다음 다이어그램은 개인 출처의 자산이 SharePoint 페이지를 요청하는 워크플로를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="b028e-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="b028e-591">![워크플로 다이어그램: Office 365 CDN 원본에서 자산 검색](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "워크플로: 개인 Office 365 CDN 자산 검색")</span><span class="sxs-lookup"><span data-stu-id="b028e-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="b028e-592">비공개 원본의 토큰 기반 권한 부여</span><span class="sxs-lookup"><span data-stu-id="b028e-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="b028e-593">온라인에서 개인 출처의 자산에 Office 365 CDN 액세스는 SharePoint 통해 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="b028e-594">원본으로 지정된 폴더 또는 라이브러리에 대한 액세스 권한이 이미 있는 사용자에게는 사용 권한 수준에 따라 파일에 액세스할 수 있는 토큰이 자동으로 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="b028e-595">이러한 액세스 토큰은 생성 후 30~90분 동안 유효하여 토큰 재생 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="b028e-596">액세스 토큰이 생성된 후 SharePoint Online은 두 개의 권한 부여 매개  변수(edge 인증 토큰)와 _oat(원본_ 인증 토큰)이 포함된 클라이언트에 사용자 지정 URI를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="b028e-597">각 토큰의 구조는 _에포치<_ 형식의 >__< 서명의 만료 >.</span><span class="sxs-lookup"><span data-stu-id="b028e-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="b028e-598">예제:</span><span class="sxs-lookup"><span data-stu-id="b028e-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="b028e-599">토큰을 소유하는 모든 사람은 해당 토큰의 리소스에 액세스할 CDN.</span><span class="sxs-lookup"><span data-stu-id="b028e-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="b028e-600">그러나 이러한 액세스 토큰을 포함하는 URL은 HTTPS를 통해만 공유되기 때문에 토큰이 만료되기 전에 최종 사용자가 URL을 명시적으로 공유하지 않는 한 권한이 없는 사용자는 자산에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="b028e-601">개인 출처의 자산에 대해 항목 수준 권한이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="b028e-602">온라인에서는 개인 SharePoint 자산에 대한 항목 수준 권한을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="b028e-603">예를 들어 에 있는 파일의 경우 다음과 같은 조건에 따라 파일에 효과적으로 `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="b028e-604">사용자</span><span class="sxs-lookup"><span data-stu-id="b028e-604">User</span></span>  |<span data-ttu-id="b028e-605">사용 권한</span><span class="sxs-lookup"><span data-stu-id="b028e-605">Permissions</span></span>  |<span data-ttu-id="b028e-606">효과적인 액세스</span><span class="sxs-lookup"><span data-stu-id="b028e-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b028e-607">사용자 1</span><span class="sxs-lookup"><span data-stu-id="b028e-607">User 1</span></span>     |<span data-ttu-id="b028e-608">folder1에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-608">Has access to folder1</span></span>         |<span data-ttu-id="b028e-609">사용자 image1.jpg 액세스할 수 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b028e-610">사용자 2</span><span class="sxs-lookup"><span data-stu-id="b028e-610">User 2</span></span>     |<span data-ttu-id="b028e-611">folder1에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-611">Does not have access to folder1</span></span>         |<span data-ttu-id="b028e-612">에서 image1.jpg 액세스할 수 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b028e-613">사용자 3</span><span class="sxs-lookup"><span data-stu-id="b028e-613">User 3</span></span>     |<span data-ttu-id="b028e-614">folder1에 액세스할 수 없지만 온라인에서 폴더 1에 액세스할 수 있는 명시적 image1.jpg SharePoint</span><span class="sxs-lookup"><span data-stu-id="b028e-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b028e-615">image1.jpg Online에서 직접 자산 SharePoint 액세스할 수 있지만 자산 관리에서 액세스할 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="b028e-616">사용자 4</span><span class="sxs-lookup"><span data-stu-id="b028e-616">User 4</span></span>     |<span data-ttu-id="b028e-617">folder1에 대한 액세스 권한이 있지만 image1.jpg Online에서 SharePoint 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b028e-618">SharePoint Online에서 자산에 액세스할 수 없지만 CDN Online의 파일에 대한 액세스가 거부되어도 자산에 액세스할 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="b028e-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="b028e-620">문제 해결 Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b028e-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="b028e-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="b028e-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="b028e-622">자산이 관리 에지에서 제공되고 CDN?</span><span class="sxs-lookup"><span data-stu-id="b028e-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="b028e-623">페이지에 CDN 자산에 대한 링크를 추가한 후 페이지로 이동한 후 이미지를 마우스 오른쪽 단추로 클릭하고 이미지 URL을 검토하여 CDN 자산이 페이지에서 제공되고 있는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="b028e-624">브라우저의 개발자 도구를 사용하여 페이지의 각 자산에 대한 URL을 보거나 타사 네트워크 추적 도구를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="b028e-625">Fiddler와 같은 네트워크 도구를 사용하여 SharePoint 페이지에서 자산을 렌더링하는 것 외의 자산을 테스트하는 경우 URL이 SharePoint Online 테넌트의 루트 URL인 GET 요청에 참조자 헤더 "Referer: " 를 수동으로 추가해야 `https://yourdomain.sharepoint.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="b028e-626">온라인에서 CDN 참조가 있어야 하기 때문에 웹 브라우저에서 직접 SharePoint 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="b028e-627">그러나 CDN 자산 URL을 SharePoint 페이지에 추가한 다음 브라우저에서 페이지를 열면 페이지에 CDN 자산이 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="b028e-628">앱 브라우저에서 개발자 도구를 사용하는 Microsoft Edge 자세한 내용은 개발자 Microsoft Edge [참조하세요.](/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="b028e-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="b028e-629">CDN 사용 현황 확인 및 최적의 네트워크 연결 확인을 참조하여 SharePoint 개발자 패턴 및 사례 [YouTube](https://aka.ms/sppnp-videos) 채널에서 호스트되는 짧은 비디오를 시청하세요 [CDN.](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)</span><span class="sxs-lookup"><span data-stu-id="b028e-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="b028e-630">새 원본의 자산을 사용할 수 없는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="b028e-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="b028e-631">새 원본의 자산은 등록이 CDN 원본에서 원본 저장소로 업로드되는 데 시간이 걸리기 때문에 즉시 사용할 수 CDN 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="b028e-632">자산 구성에서 자산을 사용할 수 있는 데 CDN 시간은 자산의 수와 파일 크기에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="b028e-633">클라이언트 쪽 웹 파트 또는 SharePoint 프레임워크 솔루션이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="b028e-634">공용 원본에 Office 365 CDN 사용하도록 설정하면 CDN 원본이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="b028e-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="b028e-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="b028e-636">\*/스타일 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b028e-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="b028e-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="b028e-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="b028e-638">\*/clientsideassets 원본이 없는 경우 SharePoint 프레임워크 솔루션이 실패하고 경고 또는 오류 메시지가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="b028e-639">_-NoDefaultOrigins_ 매개 변수를 CDN 사용하도록 설정한 경우 또는 원본이 수동으로 삭제된 $true 원본이 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="b028e-640">다음 PowerShell 명령에 원본이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="b028e-641">또는 CLI를 사용하여 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="b028e-642">PowerShell에서 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="b028e-643">CLI의 원본을 Office 365:</span><span class="sxs-lookup"><span data-stu-id="b028e-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="b028e-644">어떤 PowerShell 모듈 및 CLI 셸을 사용하여 작업해야 Office 365 CDN?</span><span class="sxs-lookup"><span data-stu-id="b028e-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="b028e-645">온라인 관리 셸 PowerShell 모듈 또는  Office 365 CDN **CLI를** 사용하여 SharePoint 선택할 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b028e-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="b028e-646">SharePoint Online 관리 셸 시작</span><span class="sxs-lookup"><span data-stu-id="b028e-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="b028e-647">CLI Office 365 설치</span><span class="sxs-lookup"><span data-stu-id="b028e-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="b028e-648">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b028e-648">See also</span></span>

[<span data-ttu-id="b028e-649">콘텐츠 배달 네트워크</span><span class="sxs-lookup"><span data-stu-id="b028e-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="b028e-650">Office 365의 네트워크 계획 및 성능 조정</span><span class="sxs-lookup"><span data-stu-id="b028e-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="b028e-651">SharePoint Performance Series - Office 365 CDN 비디오 시리즈</span><span class="sxs-lookup"><span data-stu-id="b028e-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
