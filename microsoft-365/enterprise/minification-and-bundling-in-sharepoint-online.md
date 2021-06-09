---
title: SharePoint Online의 축소 및 묶음
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
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
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Web Essentials와 함께 축소 및 번들링 기술을 사용하여 HTTP 요청과 온라인에서 페이지를 로드하는 데 걸리는 시간을 SharePoint 방법을 알아보습니다.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692327"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="18f35-103">SharePoint Online의 축소 및 묶음</span><span class="sxs-lookup"><span data-stu-id="18f35-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="18f35-104">이 문서에서는 Web Essentials와 함께 축소 및 번들링 기술을 사용하여 HTTP 요청 수를 줄이고 SharePoint Online에서 페이지를 로드하는 데 걸리는 시간을 줄이는 방법을 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="18f35-105">웹 사이트를 사용자 지정할 때 사용자 지정을 지원하기 위해 서버에 많은 수의 추가 파일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="18f35-106">JavaScript, CSS 및 이미지를 더 추가하면 서버에 대한 HTTP 요청 수가 증가하여 웹 페이지를 표시하는 데 걸리는 시간이 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="18f35-107">동일한 형식의 파일이 여러 개 있는 경우 이러한 파일을 번들로 묶어 파일을 더 빠르게 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="18f35-108">JavaScript 및 CSS 파일의 경우 축소라는 접근 방식을 사용하여 공백 및 필요하지 않은 기타 문자를 제거하여 파일의 전체 크기를 줄일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="18f35-109">Web Essentials를 사용하여 JavaScript 및 CSS 파일 다국어화 및 번들화</span><span class="sxs-lookup"><span data-stu-id="18f35-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="18f35-110">Web Essentials와 같은 타사 소프트웨어를 사용하여 CSS 및 JavaScript 파일을 번들로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="18f35-111">Web Essentials는 타사 오픈 소스 커뮤니티 기반 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="18f35-112">소프트웨어는 2012 및 Visual Studio 확장 Visual Studio 2013 Microsoft에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="18f35-113">Web Essentials를 다운로드하려면 의 웹 사이트를 [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="18f35-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="18f35-114">Web Essentials는 두 가지 형태의 번들링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="18f35-115">.bundle: CSS 및 JavaScript 파일용</span><span class="sxs-lookup"><span data-stu-id="18f35-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="18f35-116">.sprite: 이미지의 경우(Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="18f35-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="18f35-117">사용자 지정 마스터 페이지 내에서 참조되는 일부 브랜징 요소가 있는 기존 기능이 있는 경우 Web Essentials를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![사용자 지정 마스터 페이지의 브랜드 요소 스크린샷](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="18f35-119">**Web Essentials에서 TE000127218 및 CSS 번들을 만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="18f35-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="18f35-120">이 Visual Studio 솔루션 탐색기에서 번들에 포함할 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="18f35-121">선택한 파일을 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **Web Essentials** \> **JavaScript 번들** 파일 만들기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="18f35-122">예:</span><span class="sxs-lookup"><span data-stu-id="18f35-122">For example:</span></span> 
    
    ![Web Essentials 메뉴 옵션을 보여 주는 스크린샷](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="18f35-124">JavaScript 및 CSS 파일 번들링 결과 보기</span><span class="sxs-lookup"><span data-stu-id="18f35-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="18f35-125">JavaScript 및 CSS 번들을 만들 때 Web Essentials는 JavaScript 및 CSS 파일 및 기타 구성 정보를 식별하는 조리법 파일이라는 XML 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![JavaScript 및 CSS 조리법 파일의 스크린샷](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="18f35-127">또한 번들화법에서 minify 플래그를 true로 설정하면 파일 크기가 줄어들고 함께 번들화됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="18f35-128">즉, 마스터 페이지에서 참조할 수 있는 새로운 JavaScript 파일 버전이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![true로 설정된 minify 플래그의 스크린샷](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="18f35-130">웹 사이트에서 페이지를 로드할 때 웹 브라우저(예: Internet Explorer 11)에서 개발자 도구를 사용하여 서버로 전송된 요청 수와 각 파일을 로드하는 데 걸려오는 기간을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="18f35-131">다음 그림은 자르기 전에 JavaScript 및 CSS 파일을 로드한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![다운로드되는 80가지 항목을 보여 주는 스크린샷](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="18f35-133">CSS 및 JavaScript 파일을 함께 번들링한 후 요청 수가 74개로 삭제된 후 각 파일이 원래 파일보다 약간 더 오래 걸려 개별적으로 다운로드했습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![다운로드되는 74가지 항목을 보여 주는 스크린샷](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="18f35-135">번들링 후 JavaScript 번들 파일은 815KB에서 365KB로 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![감소된 다운로드 크기를 보여 주는 스크린샷](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="18f35-137">이미지 스프라이트를 만들어 이미지 번들링</span><span class="sxs-lookup"><span data-stu-id="18f35-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="18f35-138">JavaScript 및 CSS 파일을 번들로 묶는 방법과 마찬가지로 많은 작은 아이콘과 기타 일반적인 이미지를 더 큰 스프라이트 시트에 결합한 다음 CSS를 사용하여 개별 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="18f35-139">사용자의 웹 브라우저는 각 개별 이미지를 다운로드하는 대신 스프라이트 시트를 한 번 다운로드한 다음 로컬 컴퓨터에 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="18f35-140">이렇게하면 웹 서버로의 왕복 및 다운로드 수를 컷다운하여 페이지 로드 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="18f35-141">**Web Essentials에서 이미지 스프라이트를 만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="18f35-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="18f35-142">이 Visual Studio 솔루션 탐색기에서 번들에 포함할 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="18f35-143">선택한 파일을 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **Web Essentials** 이미지 \> **스프라이트** 만들기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="18f35-144">예:</span><span class="sxs-lookup"><span data-stu-id="18f35-144">For example:</span></span> 
    
    ![이미지 스프라이트를 만드는 방법을 보여 주는 스크린샷](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="18f35-146">스프라이트 파일을 저장할 위치를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="18f35-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="18f35-147">.sprite 파일은 스프라이트의 설정 및 파일을 설명하는 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="18f35-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="18f35-148">다음 그림에서는 스프라이트 PNG 파일과 해당 .sprite XML 파일의 예를 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="18f35-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![스프라이트 파일의 스크린샷](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![스프라이트 XML 파일의 스크린샷](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

