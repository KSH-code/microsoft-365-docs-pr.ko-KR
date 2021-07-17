---
title: 사용자에 대해 평가 환경을 Microsoft Cloud App Security
description: Microsoft Defender에서 MICROSOFT Defender의 아키텍처를 Office 365 제품 간의 상호 작용을 Microsoft 365 Defender 이해합니다.
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender Microsoft 365 Defender 평가 랩, Microsoft 365 Defender 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458052"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="84e65-104">사용자에 대해 평가 환경을 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="84e65-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="84e65-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="84e65-105">**Applies to:**</span></span>

- <span data-ttu-id="84e65-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84e65-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="84e65-107">이 문서는 사용자 환경의 평가 환경을 설정하는 프로세스의 [2단계](eval-defender-mcas-overview.md) 중 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="84e65-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="84e65-108">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84e65-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="84e65-109">이 문서에서는 Cloud App Security 포털에 액세스하고 클라우드 앱 트래픽 데이터를 수집하는 데 필요한 통합을 구성하는 프로세스를 진행하는 과정을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="84e65-110">환경에서 사용되는 클라우드 앱을 검색하기 위해 다음 중 하나 또는 둘 다를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="84e65-111">끝점용 Microsoft Defender와 통합하여 클라우드 검색을 빠르게 시작하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="84e65-112">이 네이티브 통합을 통해 네트워크의 모든 디바이스에서 클라우드 트래픽에 Windows 10 즉시 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="84e65-113">네트워크에 연결된 모든 장치에서 액세스하는 모든 클라우드 앱을 검색하려면 방화벽 및 기타 Cloud App Security 로그 수집기 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="84e65-114">그러면 끝점에서 데이터를 수집하여 분석하기 위해 Cloud App Security 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="84e65-115">Cloud App Security 기능을 위해 기본적으로 일부 타사 Proxies와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="84e65-116">이 문서에는 두 방법 모두에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="84e65-117">다음 단계에 따라 설치 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="84e65-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![Microsoft Defender 평가 환경에서 Microsoft Microsoft Cloud App Security 사용하도록 설정하는 단계](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="84e65-119">1단계. 커넥트 포털에 Cloud App Security 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="84e65-120">2단계. 끝점용 Microsoft Defender와 통합</span><span class="sxs-lookup"><span data-stu-id="84e65-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="84e65-121">3단계. 방화벽 및 Cloud App Security 로그 수집기 배포</span><span class="sxs-lookup"><span data-stu-id="84e65-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="84e65-122">4단계. 클라우드 검색 대시보드를 확인하여 조직에서 사용되는 앱 확인</span><span class="sxs-lookup"><span data-stu-id="84e65-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="84e65-123">1단계.</span><span class="sxs-lookup"><span data-stu-id="84e65-123">Step 1.</span></span> <span data-ttu-id="84e65-124">커넥트 포털에 Cloud App Security 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="84e65-125">라이선스를 확인하고 Cloud App Security 연결하기 위해 빠른 [시작:](/cloud-app-security/getting-started-with-cloud-app-security)시작을 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="84e65-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="84e65-126">포털에 즉시 연결할 수 없는 경우 방화벽의 허용 목록에 IP 주소를 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="84e65-127">에 [대한 기본 설정을 Cloud App Security.](/cloud-app-security/general-setup)</span><span class="sxs-lookup"><span data-stu-id="84e65-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="84e65-128">그래도 문제가 있는 경우 네트워크 요구 [사항을 검토하세요.](/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="84e65-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="84e65-129">2단계.</span><span class="sxs-lookup"><span data-stu-id="84e65-129">Step 2.</span></span> <span data-ttu-id="84e65-130">끝점용 Microsoft Defender와 통합</span><span class="sxs-lookup"><span data-stu-id="84e65-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="84e65-131">Microsoft Cloud App Security Microsoft Defender for Endpoint와 기본적으로 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="84e65-132">이러한 통합은 클라우드 검색의 롤아웃을 간소화하고, 회사 네트워크를 넘어 클라우드 검색 기능을 확장하며, 장치 기반 조사를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="84e65-133">이러한 통합은 IT 관리 디바이스에서 클라우드 앱 및 서비스에 액세스하는 Windows 10 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="84e65-134">끝점에 대해 Microsoft Defender를 이미 설정한 경우 Cloud App Security 통합을 구성하는 것이 Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="84e65-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="84e65-135">통합이 켜진 후 클라우드 검색 대시보드에서 Cloud App Security 포털로 돌아가서 다양한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="84e65-136">이러한 작업을 수행하기 위해 [Microsoft Defender for Endpoint와](/cloud-app-security/mde-integration)Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="84e65-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="84e65-137">3단계.</span><span class="sxs-lookup"><span data-stu-id="84e65-137">Step 3.</span></span> <span data-ttu-id="84e65-138">방화벽 및 Cloud App Security 로그 수집기 배포</span><span class="sxs-lookup"><span data-stu-id="84e65-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="84e65-139">네트워크에 연결된 모든 디바이스에서 적용 범위를 확인하려면 방화벽 및 기타 Cloud App Security 로그 수집기 를 배포하여 끝점에서 데이터를 수집하고 분석을 위해 Cloud App Security 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="84e65-140">다음 SWG(Secure Web Gateways) 중 하나를 사용하는 경우 Cloud App Security 통합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="84e65-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="84e65-141">Zscaler</span></span>
- <span data-ttu-id="84e65-142">iboss</span><span class="sxs-lookup"><span data-stu-id="84e65-142">iboss</span></span>
- <span data-ttu-id="84e65-143">코라타</span><span class="sxs-lookup"><span data-stu-id="84e65-143">Corrata</span></span>
- <span data-ttu-id="84e65-144">Menlo Security</span><span class="sxs-lookup"><span data-stu-id="84e65-144">Menlo Security</span></span>

<span data-ttu-id="84e65-145">이러한 네트워크 장치와의 통합에 대한 자세한 내용은 클라우드 검색 설정 [을 참조하세요.](/cloud-app-security/set-up-cloud-discovery)</span><span class="sxs-lookup"><span data-stu-id="84e65-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="84e65-146">4단계.</span><span class="sxs-lookup"><span data-stu-id="84e65-146">Step 4.</span></span> <span data-ttu-id="84e65-147">클라우드 검색 대시보드를 확인하여 조직에서 사용되는 앱 확인</span><span class="sxs-lookup"><span data-stu-id="84e65-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="84e65-148">클라우드 검색 대시보드는 조직에서 클라우드 앱이 사용되는 방식에 대한 더 많은 정보를 제공하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="84e65-149">사용되는 앱 종류, 열린 경고 및 조직의 앱 위험 수준에 대한 간략한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84e65-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="84e65-150">클라우드 검색 대시보드 사용을 시작하고 검색된 앱 작업을 [참조하세요.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="84e65-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="84e65-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="84e65-151">Next steps</span></span>

<span data-ttu-id="84e65-152">3단계 중 3단계: [파일럿 Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="84e65-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="84e65-153">평가용 [개요로 Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84e65-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="84e65-154">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84e65-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>