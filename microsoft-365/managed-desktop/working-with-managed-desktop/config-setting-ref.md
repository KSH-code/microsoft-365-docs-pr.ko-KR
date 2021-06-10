---
title: 사용자에 대한 구성 가능한 설정 Microsoft Managed Desktop
description: 구성 가능한 설정에 대한 범주 Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917707"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="ce716-104">구성 가능한 설정 참조 - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ce716-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="ce716-105">이 항목에서는 고객이 이러한 설정을 사용하여 구성할 수 있는 설정 범주를 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ce716-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="ce716-106">각 설정 범주에는 요구 사항, 모범 사례 및 설정 범주를 사용자 지정하는 방법에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="ce716-107">바탕 화면 배경 그림</span><span class="sxs-lookup"><span data-stu-id="ce716-107">Desktop background picture</span></span>
<span data-ttu-id="ce716-108">조직의 디바이스에 대한 데스크톱 배경 Microsoft Managed Desktop 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="ce716-109">이를 사용하여 회사 브랜드 또는 마케팅 자료를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="ce716-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce716-110">Requirements</span></span>

<span data-ttu-id="ce716-111">데스크톱 배경 그림에 대해 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="ce716-112">그림 파일 형식 - .jpg, jpeg 또는 .png</span><span class="sxs-lookup"><span data-stu-id="ce716-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="ce716-113">파일 위치 - 신뢰할 수 있는 보안 http(https) 위치에 호스트</span><span class="sxs-lookup"><span data-stu-id="ce716-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="ce716-114">허용되지 않습니다. Http 및 파일 공유(unc) 위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="ce716-115">데스크톱 배경 사진 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="ce716-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="ce716-116">**사용자 지정 데스크톱 배경 그림을 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="ce716-117">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-117">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="ce716-118">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="ce716-118">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="ce716-119">작업 **설정** 바탕 화면 배경 **그림 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-119">In **Settings** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="ce716-120">사용할 그림의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="ce716-121">단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="ce716-122">브라우저 시작 페이지</span><span class="sxs-lookup"><span data-stu-id="ce716-122">Browser start pages</span></span>
<span data-ttu-id="ce716-123">사용자가 브라우저 시작 페이지를 시작할 때 개별 탭에서 브라우저 Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="ce716-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="ce716-124">사용자가 자주 사용하는 사이트 집합을 쉽게 열 수 있도록 하려는 경우 각 사이트에 대해 브라우저 시작 페이지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="ce716-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce716-125">Requirements</span></span>

<span data-ttu-id="ce716-126">브라우저 시작 페이지에 대한 인트라넷 또는 인터넷 사이트의 FQDN(정식 도메인 이름)을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="ce716-127">내부 사이트가 구성된 경우 사용자가 사무실에 있을 때 또는 VPN 연결로 연결된 경우 내부 네트워크에 연결되어 있을 때만 이러한 사이트에 대한 액세스가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="ce716-128">브라우저 시작 페이지 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="ce716-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="ce716-129">**브라우저 시작 페이지를 추가하는 경우**</span><span class="sxs-lookup"><span data-stu-id="ce716-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="ce716-130">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-130">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="ce716-131">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="ce716-131">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="ce716-132">작업 **설정** 시작 페이지에서 **브라우저 시작 페이지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-132">In **Settings** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="ce716-133">시작 **페이지 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="ce716-134">브라우저 **시작 페이지 추가에서** 사용할 사이트의 URL을 입력한 다음 시작 페이지 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="ce716-135">추가 브라우저 시작 페이지에 대해 1-5단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="ce716-136">단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="ce716-137">Enterprise 모드 사이트 목록 위치</span><span class="sxs-lookup"><span data-stu-id="ce716-137">Enterprise mode site list location</span></span>

<span data-ttu-id="ce716-138">Microsoft Edge 호환성 문제가 있는 것으로 알고 있는 특정 웹 사이트 및 앱이 있는 경우 Enterprise 모드 사이트 목록을 사용하여 Internet Explorer 11을 사용하여 웹 사이트가 자동으로 열리게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="ce716-139">또한 인트라넷 사이트가 Microsoft Edge 제대로 작동하지 않는 경우 모든 인트라넷 사이트가 Internet Explorer 11을 사용하여 열리게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="ce716-140">Enterprise 모드를 사용하면 Microsoft Edge 브라우저로 계속 사용할 수 있는 동시에 앱이 Internet Explorer 11에서 계속 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="ce716-141">엔터프라이즈 모드 사이트 목록에 대한 자세한 내용은 Enterprise 모드 및 Enterprise 사이트 목록을 [참조하세요.](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)</span><span class="sxs-lookup"><span data-stu-id="ce716-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="ce716-142">엔터프라이즈 모드 https:// 호스팅한 내부 공유의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="ce716-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce716-143">Requirements</span></span>

<span data-ttu-id="ce716-144">엔터프라이즈 모드 사이트 목록 파일에 대해 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="ce716-145">파일 형식 - 파일 요구 사항을 충족하는 [XML 파일](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="ce716-145">File format - XML file that meets [file requirements](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="ce716-146">파일 위치 - 내부 https 위치에 파일을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="ce716-147">허용되지 않습니다. *//sharename과* 같은 내부 파일 공유에서 호스팅이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="ce716-148">모범 사례</span><span class="sxs-lookup"><span data-stu-id="ce716-148">Best practices</span></span>

<span data-ttu-id="ce716-149">이러한 모범 사례는 고객이 IT 인프라를 현대화하기 위한 의사 결정을 내리는 데 도움을 줄 수 있도록 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="ce716-150">**제한된 수의** 사이트를 선택 - Microsoft Managed Desktop Microsoft Edge 브라우저를 사용하여 조직의 전반적인 보안과 사용자의 사용성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="ce716-151">이 목록의 대부분의 사이트는 많은 보안 기능을 포함하지 않는 이전 버전의 브라우저가 필요한 레거시 웹앱용입니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="ce716-152">**대체 고려** - 이전 브라우저가 필요하지 않은 다른 사이트 또는 웹앱을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ce716-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="ce716-153">또는 새 브라우저를 사용할 수 있도록 사이트를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="ce716-154">최신 브라우저는 최신 기술을 사용하며 보안을 향상시키는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="ce716-155">사이트 모드 목록 Enterprise 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="ce716-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="ce716-156">**엔터프라이즈 사이트 모드 목록 위치를 추가하는 경우**</span><span class="sxs-lookup"><span data-stu-id="ce716-156">**To add an enterprise site mode list location**</span></span>

1. <span data-ttu-id="ce716-157">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-157">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="ce716-158">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="ce716-158">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="ce716-159">설정  작업 영역에서 Enterprise **사이트 목록 위치 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-159">In **Settings** workspace, select **Enterprise mode site list location**.</span></span> 
4. <span data-ttu-id="ce716-160">사이트 목록의 https 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-160">Enter the https location for your site list.</span></span> 
5. <span data-ttu-id="ce716-161">단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="ce716-162">신뢰할 수 있는 사이트</span><span class="sxs-lookup"><span data-stu-id="ce716-162">Trusted sites</span></span>

<span data-ttu-id="ce716-163">신뢰할 수 있는 사이트를 사용하면 서로 다른 사이트에 대해 보안 영역 또는 사이트를 사용할 수 있는 위치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="ce716-164">보안 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-164">Security zones include:</span></span> 
- <span data-ttu-id="ce716-165">영역 1 - 로컬 인트라넷 영역</span><span class="sxs-lookup"><span data-stu-id="ce716-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="ce716-166">영역 2 - 신뢰할 수 있는 사이트 영역</span><span class="sxs-lookup"><span data-stu-id="ce716-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="ce716-167">영역 3 - 인터넷 영역</span><span class="sxs-lookup"><span data-stu-id="ce716-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="ce716-168">영역 4 - 제한된 사이트 영역</span><span class="sxs-lookup"><span data-stu-id="ce716-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="ce716-169">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce716-169">Requirements</span></span>

<span data-ttu-id="ce716-170">신뢰할 수 있는 각 사이트에 대해 인트라넷 또는 인터넷 사이트에 대한 FQDN(FQDN)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="ce716-171">신뢰할 수 있는 사이트 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="ce716-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="ce716-172">**신뢰할 수 있는 사이트를 추가하는 경우**</span><span class="sxs-lookup"><span data-stu-id="ce716-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="ce716-173">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-173">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="ce716-174">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="ce716-174">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="ce716-175">작업 **설정** 에서 신뢰할 **수** 있는 사이트 를 선택한 다음 신뢰할 수 있는 사이트 추가 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-175">In **Settings** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="ce716-176">신뢰할 **수 있는 사이트 추가에서** URL을 입력하고 보안 영역, 신뢰할 수 있는 사이트 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="ce716-177">추가할 신뢰할 수 있는 각 사이트에 대해 1-4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="ce716-178">단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="ce716-179">**신뢰할 수 있는 사이트를 제거하려면**</span><span class="sxs-lookup"><span data-stu-id="ce716-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="ce716-180">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-180">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="ce716-181">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="ce716-181">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="ce716-182">작업 **설정** 신뢰할 수 있는 **사이트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-182">In **Settings** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="ce716-183">삭제할 사이트를 선택하고 삭제 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="ce716-184">삭제할 신뢰할 수 있는 각 사이트에 대해 1-4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="ce716-185">단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="ce716-186">프록시</span><span class="sxs-lookup"><span data-stu-id="ce716-186">Proxy</span></span>
<span data-ttu-id="ce716-187">조직의 네트워크 프록시 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="ce716-188">프록시 서버 및 포트 번호를 추가한 다음 프록시 사이트 예외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="ce716-189">Microsoft Managed Desktop 서비스에 필요한 기본 프록시 예외 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="ce716-190">기본 제외 목록은 서비스에서만 수정할 Microsoft Managed Desktop 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="ce716-191">자세한 내용은 에 [대한 네트워크 구성을 Microsoft Managed Desktop.](../get-ready/network.md)</span><span class="sxs-lookup"><span data-stu-id="ce716-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="ce716-192">Microsoft Managed Desktop 포털에 추가하는 프록시 사이트 예외는 Microsoft Managed Desktop 서비스에 포함된 기본 프록시 예외에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="ce716-193">기본 프록시 예외 목록 업데이트는 항상 고객 배포보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="ce716-194">즉, 기본 프록시 예외 목록에 대한 배포가 있는 경우 단계적 배포가 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="ce716-195">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce716-195">Requirements</span></span>

<span data-ttu-id="ce716-196">프록시 서버 및 프록시 사이트 예외에 대해 이러한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="ce716-197">유효한 서버 주소 및 포트 번호</span><span class="sxs-lookup"><span data-stu-id="ce716-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="ce716-198">URL은 유효한 http 사이트가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="ce716-199">사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="ce716-199">Customize and deploy proxies</span></span>

<span data-ttu-id="ce716-200">**개별 프록시 사이트 예외를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="ce716-201">로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-201">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="ce716-202">Microsoft Managed Desktop 를 찾아 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="ce716-202">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="ce716-203">작업 **설정** 에서 프록시 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-203">In **Settings** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="ce716-204">프록시 서버에 **대한 주소** 및 **포트** 번호를 입력한 다음 프록시 예외 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="ce716-205">유효한 http 사이트의 URL을 입력한 다음 프록시 예외 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ce716-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="ce716-206">추가할 신뢰할 수 있는 각 사이트에 대해 1-5단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="ce716-207">단계 **배포를** 선택하여 변경 내용을 저장하고 테스트 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ce716-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce716-208">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="ce716-208">Additional resources</span></span>
- [<span data-ttu-id="ce716-209">구성 가능한 설정 개요</span><span class="sxs-lookup"><span data-stu-id="ce716-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="ce716-210">구성 가능한 설정 배포</span><span class="sxs-lookup"><span data-stu-id="ce716-210">Deploy configurable settings</span></span>](config-setting-deploy.md)