---
title: SharePoint Online의 성능 문제 진단
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: 이 문서에서는 개발자 도구를 사용하여 SharePoint Online 사이트의 일반적인 문제를 진단하는 Internet Explorer 보여줍니다.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692518"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="ce866-103">SharePoint Online의 성능 문제 진단</span><span class="sxs-lookup"><span data-stu-id="ce866-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="ce866-104">이 문서에서는 개발자 도구를 사용하여 SharePoint Online 사이트의 일반적인 문제를 진단하는 Internet Explorer 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="ce866-105">SharePoint Online 사이트의 페이지에 사용자 지정에 성능 문제가 있는 경우를 식별할 수 있는 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="ce866-106">F12 도구 모음 네트워크 모니터</span><span class="sxs-lookup"><span data-stu-id="ce866-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="ce866-107">사용자 지정되지 않은 기준선 비교</span><span class="sxs-lookup"><span data-stu-id="ce866-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="ce866-108">SharePoint Online 응답 헤더 메트릭</span><span class="sxs-lookup"><span data-stu-id="ce866-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="ce866-109">이 항목에서는 이러한 각 방법을 사용하여 성능 문제를 진단하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="ce866-110">문제의 원인을 찾은 후 찾을 수 있는 SharePoint 성능 개선 관련 문서를 사용하여 해결 방법을 찾을 수 https://aka.ms/tune 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="ce866-111">F12 도구 모음을 사용하여 SharePoint Online의 성능 진단</span><span class="sxs-lookup"><span data-stu-id="ce866-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="ce866-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ce866-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ce866-113">이 문서에서는 Internet Explorer 11을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="ce866-114">다른 브라우저의 F12 개발자 도구 버전은 비슷한 기능을 가지지만 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="ce866-115">F12 개발자 도구에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce866-115">For information on the F12 developer tools, see:</span></span>
  
- [<span data-ttu-id="ce866-116">F12 도구의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="ce866-116">What's new in F12 Tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [<span data-ttu-id="ce866-117">F12 개발자 도구 사용</span><span class="sxs-lookup"><span data-stu-id="ce866-117">Using the F12 developer tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522546)

<span data-ttu-id="ce866-118">개발자 도구를 표시하려면 **F12를** 누를 때 다음 Wi-Fi 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![F12 개발자 도구 Wi-Fi 아이콘 스크린샷](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="ce866-120">네트워크 **탭에서** 녹색 재생 단추를 눌러 페이지를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="ce866-121">이 도구는 요청한 페이지를 다운로드하기 위해 브라우저에서 요청하는 모든 파일을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="ce866-122">다음 스크린샷에는 이러한 목록이 하나씩 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-122">The following screen shot shows one such list.</span></span>
  
![페이지 요청을 통해 반환되는 파일 목록의 스크린샷](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="ce866-124">이 스크린샷과 같이 오른쪽에 있는 파일의 다운로드 시간을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![SharePoint에서 요청된 페이지를 로드하는 데 걸리는 시간을 보여 주는 다이어그램](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="ce866-126">이렇게 하면 파일을 로드하는 데 걸려진 기간을 시각적으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="ce866-127">녹색 선은 페이지를 브라우저에서 렌더링할 준비가 된 때를 나타내는 선입니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="ce866-128">이렇게하면 사이트에 페이지 로드 속도가 느려질 수 있는 여러 파일을 빠르게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="ce866-129">SharePoint Online에 대해 사용자 지정되지 않은 기준 설정</span><span class="sxs-lookup"><span data-stu-id="ce866-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="ce866-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ce866-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ce866-131">사이트의 성능 약점을 확인하는 가장 좋은 방법은 SharePoint Online에서 완전히 새로운 사이트 모음을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="ce866-132">이렇게 하면 사이트의 모든 다양한 측면을 페이지에서 사용자 지정하지 않고도 얻을 수 있는 측면과 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="ce866-133">비즈니스용 OneDrive 홈 페이지는 사용자 지정이 없는 별도의 사이트 모음의 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="ce866-134">SharePoint 응답 헤더 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ce866-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="ce866-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ce866-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ce866-136">SharePoint Online에서는 각 파일의 응답 헤더에서 브라우저로 다시 전송된 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="ce866-137">성능 문제를 평가하는 데 가장 유용한 값은 요청이 처리되는 서버에 걸려오는 시간을 표시하는 **SPRequestDuration입니다.**</span><span class="sxs-lookup"><span data-stu-id="ce866-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="ce866-138">이렇게 하여 요청이 매우 과도하고 리소스를 많이 사용하는지 여부를 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="ce866-139">이는 서버가 페이지를 제공하기 위해 얼마나 많은 작업을 수행하고 있는지 파악하는 데 가장 적합한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="ce866-140">SharePoint 응답 헤더 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="ce866-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="ce866-141">F12 도구가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="ce866-142">이러한 도구를 다운로드하고 설치하는 데 대한 자세한 내용은 F12 도구의 새로운 기능 [을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=522545)</span><span class="sxs-lookup"><span data-stu-id="ce866-142">For more information on downloading and installing these tools, see [What's new in F12 tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span></span>

2. <span data-ttu-id="ce866-143">F12 도구의 네트워크  탭에서 녹색 재생 단추를 눌러 페이지를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="ce866-144">도구에서 반환된 .aspx 파일 중 하나를 클릭한 다음 **세부 정보를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce866-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![응답 헤더의 세부 정보 표시](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="ce866-146">응답 **헤더를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce866-146">Click **Response headers**.</span></span>

    ![응답 헤더의 URL을 보여 주는 다이어그램](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="ce866-148">SharePoint Online에서 성능 문제를 일으키는 원인은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ce866-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="ce866-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ce866-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ce866-150">[SharePoint Online의](navigation-options-for-sharepoint-online.md) 탐색 옵션 문서에서는 SPRequestDuration 값을 사용하여 복잡한 구조 탐색으로 인해 페이지에서 처리 시간이 오래 걸릴 수 있는 예를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="ce866-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="ce866-151">사용자 지정하지 않고 기준 사이트에 대한 값을 지정하면 특정 파일을 로드하는 데 시간이 오래 필요한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="ce866-152">[SharePoint Online의 탐색](navigation-options-for-sharepoint-online.md) 옵션에 사용되는 예제는 기본 .aspx 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="ce866-153">이 파일에는 페이지 로드에 ASP.NET 실행되는 대부분의 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="ce866-154">사용하는 사이트 서식 파일에 따라 홈 페이지를 사용자 지정하는 경우 start.aspx, home.aspx, default.aspx 또는 다른 이름이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="ce866-155">이 수치가 기준 사이트보다 훨씬 높은 경우 페이지에 성능 문제를 일으키는 복잡한 문제가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="ce866-156">사이트와 관련한 문제가 확인되면 성능 향상을 위한 권장 방법은 페이지 사용자 지정과 같은 가능한 모든 원인을 제거한 다음 사이트에 하나씩 다시 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="ce866-157">페이지가 잘 수행되는 충분한 사용자 지정을 제거한 후 특정 사용자 지정을 하나씩 다시 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="ce866-158">예를 들어 매우 복잡한 탐색이 있는 경우 탐색을 변경하여 하위 사이트를 표시하지 않습니다. 그런 다음 개발자 도구를 확인하여 이로 인해 차이가 나는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="ce866-159">또는 많은 양의 콘텐츠 롤업이 있는 경우 페이지에서 이를 제거하여 개선하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="ce866-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="ce866-160">가능한 원인을 모두 제거하고 동시에 하나씩 추가하는 경우 가장 큰 문제인 기능을 쉽게 식별한 다음 해결을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce866-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>
