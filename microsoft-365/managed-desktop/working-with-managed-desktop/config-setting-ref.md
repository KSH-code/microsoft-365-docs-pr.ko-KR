---
title: Microsoft Managed Desktop에 대 한 구성 가능한 설정 참조
description: Microsoft Managed Desktop에서 구성 가능한 설정에 대 한 범주 설정
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c3f8aec244b1b0685b8293fda0b048d662c7cef2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529364"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="9bd50-104">구성 가능한 설정 참조-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="9bd50-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="9bd50-105">이 항목에서는 고객이 Microsoft Managed Desktop을 사용 하 여 구성할 수 있는 설정 범주를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="9bd50-106">각 설정 범주에는 요구 사항, 모범 사례 및 설정 범주를 사용자 지정 하는 방법에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="9bd50-107">바탕 화면 배경 그림</span><span class="sxs-lookup"><span data-stu-id="9bd50-107">Desktop background picture</span></span>
<span data-ttu-id="9bd50-108">조직의 Microsoft Managed Desktop 장치에 대 한 바탕 화면 배경 그림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="9bd50-109">회사 브랜드 또는 마케팅 자료를 적용 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="9bd50-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bd50-110">Requirements</span></span>

<span data-ttu-id="9bd50-111">데스크톱 배경 사진에 대해 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="9bd50-112">그림 파일 형식-.jpg, jpeg 또는 .png</span><span class="sxs-lookup"><span data-stu-id="9bd50-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="9bd50-113">파일 위치-신뢰할 수 있는 보안 http (https) 위치의 호스트입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="9bd50-114">허용 되지 않음-Http 및 파일 공유 (unc) 위치는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="9bd50-115">데스크톱 배경 그림 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="9bd50-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="9bd50-116">**사용자 지정 바탕 화면 배경 그림을 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="9bd50-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="9bd50-117">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="9bd50-117">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9bd50-118">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9bd50-119">**구성 가능한** 작업 영역에서 **바탕 화면 배경 그림**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="9bd50-120">사용 하려는 사진의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="9bd50-121">**단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="9bd50-122">브라우저 시작 페이지</span><span class="sxs-lookup"><span data-stu-id="9bd50-122">Browser start pages</span></span>
<span data-ttu-id="9bd50-123">사용자가 Microsoft Edge를 시작 하면 브라우저 시작 페이지가 개별 탭에 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="9bd50-124">사용자가 자주 사용 하는 사이트 집합을 쉽게 열 수 있도록 하려면 각 사이트에 대해 브라우저 시작 페이지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="9bd50-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bd50-125">Requirements</span></span>

<span data-ttu-id="9bd50-126">브라우저 시작 페이지에 대 한 인트라넷 또는 인터넷 사이트의 FQDN (정규화 된 도메인 이름)을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="9bd50-127">내부 사이트가 구성 된 경우 사용자에 게는 이러한 사이트에 대 한 액세스가 사무실에서 또는 VPN 연결로 연결 된 경우 내부 네트워크에 연결 된 경우에만 허용 된다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="9bd50-128">브라우저 시작 페이지 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="9bd50-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="9bd50-129">**브라우저 시작 페이지를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="9bd50-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="9bd50-130">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="9bd50-130">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9bd50-131">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9bd50-132">**구성 가능한** 작업 영역에서 **브라우저 시작 페이지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="9bd50-133">**시작 페이지 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="9bd50-134">**브라우저 시작 추가 페이지**에서 사용 하려는 사이트의 URL을 입력 하 고 **시작 페이지 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="9bd50-135">추가 브라우저 시작 페이지에 대해 1-5 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="9bd50-136">**단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="9bd50-137">엔터프라이즈 모드 사이트 목록 위치</span><span class="sxs-lookup"><span data-stu-id="9bd50-137">Enterprise mode site list location</span></span>

<span data-ttu-id="9bd50-138">Microsoft Edge와의 호환성 문제가 있다는 것을 알고 있는 특정 웹 사이트 및 앱이 있는 경우 엔터프라이즈 모드 사이트 목록을 사용 하 여 Internet Explorer 11을 사용 하 여 웹 사이트를 자동으로 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="9bd50-139">또한 인트라넷 사이트가 Microsoft Edge에서 제대로 작동 하지 않을 것을 알고 있는 경우 Internet Explorer 11을 사용 하 여 모든 인트라넷 사이트를 자동으로 열도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="9bd50-140">엔터프라이즈 모드를 사용 하는 경우에도 Microsoft Edge를 기본 브라우저로 계속 사용할 수 있고, 앱이 Internet Explorer 11에서 계속 작동 하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="9bd50-141">엔터프라이즈 모드 사이트 목록에 대 한 자세한 내용은 [엔터프라이즈 모드 및 엔터프라이즈 모드 사이트 목록을](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bd50-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="9bd50-142">Https://위치를 지정 하거나 엔터프라이즈 모드 사이트 목록을 호스팅한 내부 공유 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="9bd50-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bd50-143">Requirements</span></span>

<span data-ttu-id="9bd50-144">엔터프라이즈 모드 사이트 목록 파일에 대해 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="9bd50-145">파일 형식- [파일 요구 사항을](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file) 충족 하는 XML 파일</span><span class="sxs-lookup"><span data-stu-id="9bd50-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="9bd50-146">파일 위치-내부 https 위치에 호스트 파일을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="9bd50-147">허용 안 됨-/ *sharename*과 같은 내부 파일 공유에서 호스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="9bd50-148">모범 사례</span><span class="sxs-lookup"><span data-stu-id="9bd50-148">Best practices</span></span>

<span data-ttu-id="9bd50-149">고객이 IT 인프라를 modernize 위해 결정을 내리는 데 도움이 되는 모범 사례가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="9bd50-150">**제한 된 수의 사이트 선택** -Microsoft Managed Desktop은 microsoft Edge를 기본 브라우저로 사용 하 여 사용자의 조직 및 유용성에 대 한 전반적인 보안을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="9bd50-151">이 목록에 있는 대부분의 사이트는 보안 기능을 많이 포함 하지 않는 이전 버전의 브라우저가 필요한 레거시 웹 앱에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="9bd50-152">다른 사이트 또는 이전 브라우저가 필요 하지 않은 웹 앱 **을 고려 하세요** .</span><span class="sxs-lookup"><span data-stu-id="9bd50-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="9bd50-153">또는 최신 브라우저를 사용할 수 있도록 사이트를 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="9bd50-154">최신 버전의 브라우저에서는 최근 기술을 사용 하 여 보안을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="9bd50-155">엔터프라이즈 사이트 모드 목록 위치 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="9bd50-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="9bd50-156">**엔터프라이즈 사이트 모드 목록 위치를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="9bd50-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="9bd50-157">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="9bd50-157">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="9bd50-158">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="9bd50-159">**구성 가능한** 작업 영역에서 **엔터프라이즈 모드 사이트 목록 위치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="9bd50-160">사이트 목록에 대 한 https 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="9bd50-161">**단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="9bd50-162">신뢰할 수 있는 사이트</span><span class="sxs-lookup"><span data-stu-id="9bd50-162">Trusted sites</span></span>

<span data-ttu-id="9bd50-163">신뢰할 수 있는 사이트에서는 각 사이트에 대해 보안 영역 또는 사이트를 사용할 수 있는 위치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="9bd50-164">보안 영역에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-164">Security zones include:</span></span> 
- <span data-ttu-id="9bd50-165">영역 1-로컬 인트라넷 영역</span><span class="sxs-lookup"><span data-stu-id="9bd50-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="9bd50-166">영역 2-신뢰할 수 있는 사이트 영역</span><span class="sxs-lookup"><span data-stu-id="9bd50-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="9bd50-167">영역 3-인터넷 영역</span><span class="sxs-lookup"><span data-stu-id="9bd50-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="9bd50-168">영역 4-제한 된 사이트 영역</span><span class="sxs-lookup"><span data-stu-id="9bd50-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="9bd50-169">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bd50-169">Requirements</span></span>

<span data-ttu-id="9bd50-170">신뢰할 수 있는 각 사이트에 대 한 인트라넷 또는 인터넷 사이트의 FQDN (정규화 된 도메인 이름)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="9bd50-171">신뢰할 수 있는 사이트 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="9bd50-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="9bd50-172">**신뢰할 수 있는 사이트를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="9bd50-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="9bd50-173">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="9bd50-173">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9bd50-174">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9bd50-175">**구성 가능한** 작업 영역에서 **신뢰할 수**있는 사이트를 선택 하 고 **신뢰할 수 있는 사이트로 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="9bd50-176">**신뢰할 수 있는 사이트 추가**에서 URL을 입력 하 고 보안 영역을 선택한 다음 **신뢰할 수 있는 사이트 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="9bd50-177">추가 하려는 각 신뢰할 수 있는 사이트에 대해 1-4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="9bd50-178">**단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="9bd50-179">**신뢰할 수 있는 사이트를 제거 하려면**</span><span class="sxs-lookup"><span data-stu-id="9bd50-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="9bd50-180">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="9bd50-180">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9bd50-181">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9bd50-182">**구성 가능한** 작업 영역에서 **신뢰할 수 있는 사이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="9bd50-183">삭제할 사이트를 선택 하 고 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="9bd50-184">삭제 하려는 각 신뢰할 수 있는 사이트에 대해 1-4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="9bd50-185">**단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="9bd50-186">프록시와</span><span class="sxs-lookup"><span data-stu-id="9bd50-186">Proxy</span></span>
<span data-ttu-id="9bd50-187">조직에 대 한 네트워크 프록시 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="9bd50-188">프록시 서버 및 포트 번호를 추가한 다음 프록시 사이트 예외를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="9bd50-189">Microsoft Managed Desktop에는 서비스가 작동 하는 데 필요한 기본 프록시 예외 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="9bd50-190">기본 제외 목록은 Microsoft Managed Desktop service를 통해서만 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="9bd50-191">자세한 내용은 [Microsoft Managed Desktop의 네트워크 구성을](../get-ready/network.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bd50-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="9bd50-192">Microsoft Managed Desktop portal에서 추가 하는 프록시 사이트 예외는 Microsoft Managed Desktop service에 포함 된 기본 프록시 예외에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="9bd50-193">기본 프록시 예외 목록의 업데이트는 항상 고객 배포에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="9bd50-194">즉, 기본 프록시 예외 목록에 대 한 배포가 있으면 미리 구성 된 배포가 일시 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="9bd50-195">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bd50-195">Requirements</span></span>

<span data-ttu-id="9bd50-196">프록시 서버 및 프록시 사이트 예외에 대해 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="9bd50-197">유효한 서버 주소 및 포트 번호 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="9bd50-198">Url은 유효한 http 사이트 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="9bd50-199">프록시 사용자 지정 및 배포</span><span class="sxs-lookup"><span data-stu-id="9bd50-199">Customize and deploy proxies</span></span>

<span data-ttu-id="9bd50-200">**개별 프록시 사이트 예외를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="9bd50-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="9bd50-201">[Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인</span><span class="sxs-lookup"><span data-stu-id="9bd50-201">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9bd50-202">**설정**아래에서 **보안 계정 구성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9bd50-203">**구성 가능한** 작업 영역에서 **프록시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="9bd50-204">프록시 서버의 **주소** 와 **포트 번호** 를 입력 하 고 **프록시 예외 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="9bd50-205">유효한 http 사이트의 URL을 입력 하 고 **프록시 예외 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="9bd50-206">추가 하려는 각 신뢰할 수 있는 사이트에 대해 1-5 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="9bd50-207">**단계 배포** 를 선택 하 여 변경 내용을 저장 하 고 테스트 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd50-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bd50-208">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9bd50-208">Additional resources</span></span>
- [<span data-ttu-id="9bd50-209">구성 가능한 설정 개요</span><span class="sxs-lookup"><span data-stu-id="9bd50-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="9bd50-210">구성 가능한 설정 배포</span><span class="sxs-lookup"><span data-stu-id="9bd50-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
