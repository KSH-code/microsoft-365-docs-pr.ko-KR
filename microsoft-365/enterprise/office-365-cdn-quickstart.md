---
title: Office 365 Content Delivery Network(CDN) 빠른 시작
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network(CDN) 빠른 시작
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921597"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="f4660-103">Office 365 Content Delivery Network(CDN) 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="f4660-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="f4660-104">기본 제공 Office 365 Content Delivery Network(CDN)를 사용하여 정적 자산(이미지, **JavaScript,** 스타일시트, WOFF 파일)을 호스트하여 SharePoint 온라인 페이지에 더 나은 성능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="f4660-105">Office 365 CDN은 정적 자산을 요청하는 브라우저에 더 가깝게 캐싱하여 성능을 향상시켜 다운로드 속도를 높이고 대기 시간을 줄이는 데 기여합니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="f4660-106">또한 이 Office 365 CDN 향상된 압축 및 HTTP 파이프라이너를 위해 HTTP/2 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="f4660-107">Office 365 CDN 서비스는 SharePoint Online 구독의 일부로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="f4660-108">자세한 내용은 [온라인에서 Office 365 Content Delivery Network(CDN)를 SharePoint 참조하세요.](use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="f4660-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="f4660-109">이 Office 365 CDN 프로덕션(전 세계) 클라우드의 테넌트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="f4660-110">미국 정부, 중국 및 독일 클라우드의 테넌트는 현재 이 서비스를 지원하지 Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="f4660-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="f4660-111">페이지 진단을 사용하여 SharePoint 없는 항목을 식별할 CDN</span><span class="sxs-lookup"><span data-stu-id="f4660-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="f4660-112">SharePoint 도구  브라우저 확장에 대한 페이지 진단을 사용하여 SharePoint 온라인 페이지에 추가될 수 있는 자산을 CDN 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="f4660-113">SharePoint  페이지 진단 도구는 새로운 Microsoft Edge(및 SharePoint Online 최신 포털 및 클래식 게시 사이트 페이지를 모두 분석하는 Chrome 브라우저의 브라우저 https://www.microsoft.com/edge) 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="f4660-114">이 도구는 정의된 성능 기준의 집합 대비 페이지 수행 방식을 보여주는 분석된 각 페이지에 대한 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="f4660-115">Sharepoint용 페이지 진단 도구에 대해 배우고 설치하려면[Sharepoint Online에 페이지 진단 도구 사용](./page-diagnostics-for-spo.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4660-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="f4660-116">SharePoint Online 페이지에서 SharePoint 진단 도구를 실행하면 진단 테스트 탭을 클릭하여 웹  페이지에서 호스팅되지 않는 자산 목록을 볼 CDN.</span><span class="sxs-lookup"><span data-stu-id="f4660-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="f4660-117">이러한 자산은 아래 스크린샷에 표시된 Content Delivery Network **(CDN) 확인** 제목 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![페이지 진단](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="f4660-119">페이지 진단 도구는 SharePoint Online에서만 사용할 수 있으며 SharePoint 시스템 페이지에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="f4660-120">CDN 개요</span><span class="sxs-lookup"><span data-stu-id="f4660-120">CDN Overview</span></span>

<span data-ttu-id="f4660-121">이 Office 365 CDN 고속 전역 네트워크를 통해 이미지 및 javascript 파일과 같은 자주 액세스하는 개체를 배포하여 페이지 로드 시간을 줄이고 호스트된 개체에 최대한 가까운 액세스 권한을 제공하여 사용자의 성능을 최적화하도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="f4660-122">이 CDN 원본 이라는 위치에서 자산을 _페치합니다._</span><span class="sxs-lookup"><span data-stu-id="f4660-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="f4660-123">원본은 URL에서 액세스할 SharePoint 사이트, 문서 라이브러리 또는 폴더일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="f4660-124">이 Office 365 CDN 두 가지 기본 유형으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="f4660-125">**공용** CDN JS(JavaScript), CSS(스타일시트), 웹 글꼴 파일(WOFF, WOFF2) 및 회사 로고와 같은 비소유 이미지에 사용할 수 있도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="f4660-126">**전용 CDN** 이미지(PNG, JPG, JPEG 등)에 사용할 수 있도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="f4660-127">조직에 대한 공개 출처 또는 비공개 출처를 둘 다 찾게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="f4660-128">대부분의 조직에서는 둘의 조합을 구현하기로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="f4660-129">공개 옵션과 개인 옵션 모두 비슷한 성능 이점을 제공하지만 각각 고유한 특성과 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="f4660-130">공개 및 개인 CDN 대한 자세한 내용은 각 출처가 공개인지 비공개인지를 [선택을 참조하세요.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="f4660-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="f4660-131">기본 구성을 사용하여 공용 및 CDN 개인 설정을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="f4660-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="f4660-132">테넌트 CDN 변경하기 전에 테넌트가 조직의 규정 준수, 보안 및 개인 정보 보호 정책을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="f4660-133">자세한 구성 설정 또는 CDN 이미 사용하도록 설정하고 추가 위치(원본)를 추가하려는 경우 Office 365 CDN Online 관리 셸을 사용하여 Office 365 CDN 설정 및 구성 섹션을 SharePoint [참조하세요.](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="f4660-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="f4660-134">커넥트 온라인 관리 셸을 사용하여 테넌트에 SharePoint 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="f4660-135">조직에서 기본 구성에서 공용 원본과 개인 출처를 모두 사용할 수 있도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="f4660-136">이러한 cmdlet의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4660-136">Output of these cmdlets should look like the following:</span></span>

![출력 Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="f4660-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4660-138">See also</span></span>

[<span data-ttu-id="f4660-139">온라인용 페이지 진단 SharePoint 사용</span><span class="sxs-lookup"><span data-stu-id="f4660-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="f4660-140">sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기</span><span class="sxs-lookup"><span data-stu-id="f4660-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="f4660-141">콘텐츠 배달 네트워크</span><span class="sxs-lookup"><span data-stu-id="f4660-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="f4660-142">Office 365의 네트워크 계획 및 성능 조정</span><span class="sxs-lookup"><span data-stu-id="f4660-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="f4660-143">SharePoint Performance Series - Office 365 CDN 비디오 시리즈</span><span class="sxs-lookup"><span data-stu-id="f4660-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)