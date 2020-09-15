---
title: Microsoft 365 네트워크 연결 테스트 (미리 보기)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/14/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 네트워크 연결 테스트 (미리 보기)
ms.openlocfilehash: 92bd850c98261df1808219ee1f28c75da370d443
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650032"
---
# <a name="microsoft-365-network-connectivity-test-preview"></a><span data-ttu-id="d0781-103">Microsoft 365 네트워크 연결 테스트 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d0781-103">Microsoft 365 network connectivity test (preview)</span></span>

<span data-ttu-id="d0781-104">Microsoft 365 네트워크 연결 테스트 도구는에 <https://connectivity.office.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-104">The Microsoft 365 network connectivity test tool is located at <https://connectivity.office.com>.</span></span> <span data-ttu-id="d0781-105">Microsoft 365 관리 센터에서 사용할 수 있는 네트워크 평가 및 네트워크 insights 정보에 대 한 adjunct 도구입니다. **| 연결** 메뉴</span><span class="sxs-lookup"><span data-stu-id="d0781-105">It is an adjunct tool to the network assessment and network insights information available in the Microsoft 365 admin center under the **Health | Connectivity** menu.</span></span>

>[!NOTE]
><span data-ttu-id="d0781-106">네트워크 연결 테스트 도구는 WW 상업용 및 독일의 테 넌 트를 지원 하지만 GCC 보통, GCC High, DoD 또는 중국이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-106">The network connectivity test tool supports tenants in WW Commercial and Germany but not GCC Moderate, GCC High, DoD or China.</span></span>

<span data-ttu-id="d0781-107">Microsoft 365 관리 센터의 네트워크 insights는 매일 집계 되는 Microsoft 365 테 넌 트에 대 한 일반 제품 측정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-107">The network insights in the Microsoft 365 Admin Center are based on regular in-product measurements for your Microsoft 365 tenant which are aggregated each day.</span></span> <span data-ttu-id="d0781-108">비교에서는 Microsoft 365 네트워크 연결 테스트의 네트워크 insights가 로컬로 실행 되 고 도구에서 한 번 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-108">In comparison, the network insights from the Microsoft 365 network connectivity test are run locally and one time in the tool.</span></span> <span data-ttu-id="d0781-109">제품에서 수행할 수 있는 테스트는 제한 되며 사용자에 대 한 로컬 테스트를 실행 하 여 더 많은 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-109">Testing that can be done in-product is limited and by running tests local to the user more data can be gathered resulting in deeper insights.</span></span> <span data-ttu-id="d0781-110">Microsoft 365 관리 센터의 네트워크 insights에서 특정 사무실 위치에 Microsoft 365 사용에 대 한 네트워킹 문제가 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-110">Consider then that the network insights in the Microsoft 365 Admin Center will show that there is a networking problem for use of Microsoft 365 at a specific office location.</span></span> <span data-ttu-id="d0781-111">Microsoft 365 연결 테스트를 통해 권장 되는 네트워크 성능 개선 작업으로 인해 발생 하는 문제의 근본적인 원인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-111">The Microsoft 365 connectivity test can help to identify the root cause of that problem leading to a recommended network performance improvement action.</span></span>

<span data-ttu-id="d0781-112">Microsoft 365 관리 센터의 각 사무실 위치에 대해 네트워킹 품질 상태를 평가할 수 있으며 Microsoft 365 연결 테스트를 기반으로 테스트를 배포한 후 더 자세한 내용을 확인할 수 있는 방법을 함께 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-112">We recommend that these be used together where networking quality status can be assessed for each office location in the Microsoft 365 Admin Center and more specifics can be found after deployment of testing based on the Microsoft 365 connectivity test.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d0781-113">네트워크 insights, Microsoft 365 관리 센터의 성능 권장 사항 및 평가는 현재 미리 보기 상태 이며, 기능 미리 보기 프로그램에 등록 되어 있는 Microsoft 365 테 넌 트에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-113">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="the-advanced-tests-client-application"></a><span data-ttu-id="d0781-114">고급 테스트 클라이언트 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d0781-114">The advanced tests client application</span></span>

<span data-ttu-id="d0781-115">Microsoft 365 네트워크 연결 테스트는 두 부분으로 구성 됩니다. <https://connectivity.office.com> 고급 네트워크 연결 테스트를 실행 하는 다운로드 가능한 Windows 클라이언트 응용 프로그램 및 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="d0781-115">There are two parts to the Microsoft 365 network connectivity test; the web site <https://connectivity.office.com> and a downloadable Windows client application that runs advanced network connectivity tests.</span></span> <span data-ttu-id="d0781-116">대부분의 테스트에서는 응용 프로그램을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-116">Most of the tests require the application to be run.</span></span> <span data-ttu-id="d0781-117">그러면 결과가 웹 페이지에 다시 실행 될 때 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-117">It will populate results back into the web page as it runs.</span></span>

<span data-ttu-id="d0781-118">웹 브라우저 테스트가 완료 되 면 웹 사이트에서 고급 클라이언트 테스트 응용 프로그램을 다운로드 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-118">You will be prompted to download the advanced client test application from the web site after the web browser tests have completed.</span></span> <span data-ttu-id="d0781-119">메시지가 표시 되 면 파일을 열고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-119">Open and run the file when prompted.</span></span>

![고급 테스트 클라이언트 응용 프로그램](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

## <a name="sharing-your-test-report"></a><span data-ttu-id="d0781-121">테스트 보고서 공유</span><span class="sxs-lookup"><span data-stu-id="d0781-121">Sharing your test report</span></span>

<span data-ttu-id="d0781-122">테스트 보고서를 사용 하려면 Office 365 계정에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-122">The test report requires sign-in to your Office 365 account.</span></span> <span data-ttu-id="d0781-123">관리자가 테스트 보고서를 공유할 수 있는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-123">Your administrator selects how you can share your test report.</span></span>

### <a name="sharing-your-report-with-your-administrator"></a><span data-ttu-id="d0781-124">관리자와 보고서 공유</span><span class="sxs-lookup"><span data-stu-id="d0781-124">Sharing your report with your administrator</span></span>

<span data-ttu-id="d0781-125">로그인 한 상태에서 모든 테스트 보고서는 관리자와 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-125">All test reports while you are signed in are shared with your administrator.</span></span>

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a><span data-ttu-id="d0781-126">Microsoft 계정 팀, 지원 또는 기타 직원과 공유</span><span class="sxs-lookup"><span data-stu-id="d0781-126">Sharing with your Microsoft account team, support or other personnel</span></span>

<span data-ttu-id="d0781-127">개인 식별을 제외 하는 테스트 보고서는 Microsoft 직원과 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-127">Test reports excluding any personal identification are shared with Microsoft employees.</span></span> <span data-ttu-id="d0781-128">이 기능은 기본적으로 사용 하도록 설정 되어 있으며 관리자가 상태를 사용 하지 않도록 설정할 수 있습니다. \*\*| \*\* Microsoft 365 관리 센터의 네트워크 연결 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-128">This is enabled by default and can be disabled by your administrator in the **Health | Network Connectivity** page in the Microsoft 365 Admin Center.</span></span>

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a><span data-ttu-id="d0781-129">동일한 Office 365 테 넌 트에 로그인 하는 다른 사용자와 공유</span><span class="sxs-lookup"><span data-stu-id="d0781-129">Sharing with other users who sign in to the same Office 365 tenant</span></span>

<span data-ttu-id="d0781-130">사용자를 선택 하 여 보고서를 공유할 수 있으며, 기본적으로이 옵션은 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-130">You can choose users to share your report with and this is enabled by default.</span></span> <span data-ttu-id="d0781-131">관리자가이 기능을 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-131">It can also be disabled by your administrator.</span></span>

![사용자와 함께 테스트 결과에 대 한 링크 공유](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a><span data-ttu-id="d0781-133">ReportID 링크를 사용 하 여 모든 사용자와 공유</span><span class="sxs-lookup"><span data-stu-id="d0781-133">Sharing with anyone using a ReportID link</span></span>

<span data-ttu-id="d0781-134">ReportID 링크에 대 한 액세스 권한을 제공 하 여 모든 사용자와 테스트 보고서를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-134">You can share your test report with anyone by providing access to a ReportID link.</span></span> <span data-ttu-id="d0781-135">이렇게 하면 로그인 하지 않고도 테스트 보고서를 가져올 수 있도록 다른 사람에 게 보낼 수 있는 URL이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-135">This generates a URL that you can send to someone so that they can bring up the test report without signing in.</span></span> <span data-ttu-id="d0781-136">이 기능은 기본적으로 사용 하지 않도록 설정 되어 있으며 관리자가 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-136">This is disabled by default and must be enabled by your administrator.</span></span>

![테스트 결과에 대 한 링크 공유](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a><span data-ttu-id="d0781-138">네트워크 연결 테스트 결과</span><span class="sxs-lookup"><span data-stu-id="d0781-138">Network Connectivity Test Results</span></span>

<span data-ttu-id="d0781-139">결과가 **요약** 및 **세부 정보** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-139">The results are shown in the **Summary** and **Details** tabs.</span></span> <span data-ttu-id="d0781-140">요약 탭에는 검색 된 네트워크 경계의 맵과 주변의 다른 Office 365 고객에 대 한 네트워크 평가가 비교 되어 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-140">The summary tab shows a map of the detected network perimeter and a comparison of the network assessment to other Office 365 customers nearby.</span></span> <span data-ttu-id="d0781-141">또한 테스트 보고서를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-141">It also allows for sharing of the test report.</span></span> <span data-ttu-id="d0781-142">요약 결과 보기의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-142">Here's what the summary results view looks like.</span></span>

![네트워크 연결 테스트 도구 요약 결과](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

<span data-ttu-id="d0781-144">다음은 도구에 표시 되는 세부 정보 탭 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-144">Here is an example of the details tab output that the tool shows.</span></span> <span data-ttu-id="d0781-145">세부 정보 탭에서 favorably를 임계값과 비교한 결과 녹색 원형 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-145">On the details tab we show a green circle check mark if the result was compared favorably to a threshold.</span></span> <span data-ttu-id="d0781-146">결과가 네트워크 통찰력을 나타내는 임계값을 초과 하면 빨간색 삼각형 느낌표가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-146">We show a red triangle exclamation point if the result exceeded a threshold indicating a network insight.</span></span> <span data-ttu-id="d0781-147">다음 섹션에서는 각 세부 항목 탭 결과 행에 대해 설명 하 고 네트워크 insights에 사용 되는 임계값에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-147">The following sections describe each of the details tab results rows and explains the thresholds used for network insights.</span></span>

![네트워크 연결 테스트 도구 예제 테스트 결과](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a><span data-ttu-id="d0781-149">위치 정보</span><span class="sxs-lookup"><span data-stu-id="d0781-149">Your location information</span></span>

<span data-ttu-id="d0781-150">이 섹션에서는 사용자의 위치와 관련 된 테스트 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-150">This section shows test results related to your location.</span></span>

#### <a name="your-location"></a><span data-ttu-id="d0781-151">사용자 위치</span><span class="sxs-lookup"><span data-stu-id="d0781-151">Your location</span></span>

<span data-ttu-id="d0781-152">사용자 위치는 사용자가 웹 브라우저에서 검색 되거나 사용자가 선택한 시간에 입력 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-152">The user location is detected from the users web browser, or it can be typed in at the users choice.</span></span> <span data-ttu-id="d0781-153">네트워크 거리를 엔터프라이즈 네트워크 경계의 특정 부분으로 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-153">It is used to identify network distances to specific parts of the enterprise network perimeter.</span></span> <span data-ttu-id="d0781-154">이 위치 검색의 도시와 다른 네트워크 지점 까지의 거리가 보고서에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-154">Only the city from this location detection and the distance to other network points are saved in the report.</span></span>

<span data-ttu-id="d0781-155">사용자 사무실 위치는 지도 보기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-155">The user office location is shown on the map view.</span></span>

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a><span data-ttu-id="d0781-156">네트워크 송신 위치 (ISP에 네트워크가 연결 되는 위치)</span><span class="sxs-lookup"><span data-stu-id="d0781-156">Network egress location (the location where your network connects to your ISP)</span></span>

<span data-ttu-id="d0781-157">서버 쪽에서 네트워크 송신 IP 주소를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-157">We identify the network egress IP address on the server side.</span></span> <span data-ttu-id="d0781-158">위치 데이터베이스는 네트워크 송신에 대 한 대략적인 위치를 조회 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-158">Location databases are used to look up the approximate location for the network egress.</span></span> <span data-ttu-id="d0781-159">일반적으로 이러한 데이터베이스는 약 90%의 IP 주소를 정확 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-159">These databases typically have an accuracy of about 90% of IP addresses.</span></span> <span data-ttu-id="d0781-160">네트워크 송신 IP 주소에서 찾은 위치가 정확 하지 않으면이 테스트에서 잘못 된 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-160">If the location looked up from the network egress IP address is not accurate then this would lead to a false result from this test.</span></span> <span data-ttu-id="d0781-161">특정 IP 주소에 대해이 오류가 발생 하는지 확인 하려면 공용으로 액세스 가능한 네트워크 IP 주소 위치 웹 사이트를 사용 하 여 실제 위치와 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-161">To validate if this error is occurring for a specific IP address you can use publicly accessible network IP address location web sites to compare to your actual location.</span></span>

#### <a name="your-distance-from-the-network-egress-location"></a><span data-ttu-id="d0781-162">네트워크 송신 위치 로부터의 거리</span><span class="sxs-lookup"><span data-stu-id="d0781-162">Your distance from the network egress location</span></span>

<span data-ttu-id="d0781-163">해당 위치에서 사무실 위치로의 거리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-163">We determine the distance from that location to the office location.</span></span> <span data-ttu-id="d0781-164">이는 TCP 대기 시간이 25ms 보다 많이 증가 하 여 사용자 환경에 영향을 줄 수 있으므로 거리가 **500 마일** (800 킬로미터) 보다 큰 경우 네트워크를 파악 하는 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-164">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers) since that is likely to increase the TCP latency by more than 25ms and may affect user experience.</span></span>

<span data-ttu-id="d0781-165">네트워크 송신 위치가 지도 보기에 표시 되 고 엔터프라이즈 WAN 내부에 네트워크가 연결 되었음을 나타내는 사용자 사무실 위치에 연결이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-165">The network egress location is shown on the map view and connected to the user office location indicating the network backhaul inside of the enterprise WAN.</span></span>

<span data-ttu-id="d0781-166">Microsoft 365 네트워크 연결에는 사용자 사무실 위치에서 인터넷으로 로컬 및 직접 네트워크 송신을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-166">Implementing local and direct network egress from user office locations to the Internet is recommended for Microsoft 365 network connectivity.</span></span> <span data-ttu-id="d0781-167">이러한 네트워크 통찰력을 해결 하는 가장 좋은 방법은 로컬 및 직접 egress에 대 한 개선 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-167">Improvements to local and direct egress are the best way to address this network insight.</span></span>

#### <a name="proxy-server-information"></a><span data-ttu-id="d0781-168">프록시 서버 정보</span><span class="sxs-lookup"><span data-stu-id="d0781-168">Proxy server information</span></span>

<span data-ttu-id="d0781-169">로컬 컴퓨터에 구성 된 프록시 서버를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-169">We identify proxy server(s) configured on the local machine.</span></span> <span data-ttu-id="d0781-170">최적화 범주에 대 한 네트워크 경로에 구성 되어 있는 항목 (Microsoft 365 네트워크 트래픽)이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-170">We identify if any of these are configured in the network path for optimize category Microsoft 365 network traffic.</span></span> <span data-ttu-id="d0781-171">사용자 사무실 위치에서 프록시 서버 까지의 거리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-171">We identify the distance from the user office location to the proxy servers.</span></span> <span data-ttu-id="d0781-172">이러한 간격은 먼저 ICMP ping을 통해 테스트 하며,이로 인해 TCP ping을 실행 하는 데 실패 한 경우에는 IP 주소 위치 데이터베이스에서 프록시 서버 IP 주소를 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-172">The distance is tested first by ICMP ping and if that fails we test with TCP ping and finally if that fails we look up the proxy server IP Address in an IP Address location database.</span></span> <span data-ttu-id="d0781-173">사용자 사무실 위치에서 프록시 서버가 **500 마일** (800 킬로미터) 보다 멀리 떨어진 경우 네트워크 통찰력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-173">We show a network insight if the proxy server is further than **500 miles** (800 kilometers) away from the user office location.</span></span>

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a><span data-ttu-id="d0781-174">조직에 연결 하는 데 사용 하는 VPN (가상 사설망)</span><span class="sxs-lookup"><span data-stu-id="d0781-174">Virtual private network (VPN) you use to connect to your organization</span></span>

<span data-ttu-id="d0781-175">이는 VPN을 사용 하 여 Office 365에 연결 하는 경우를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-175">This detects if you are using a VPN to connect to Office 365.</span></span> <span data-ttu-id="d0781-176">VPN을 사용 하지 않는 경우 또는 Office 365에 대 한 권장 분할 터널 구성의 VPN이 있는 경우 통과 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-176">A passing result will show if you have no VPN, or if you have a VPN with recommended split tunnel configuration for Office 365.</span></span>

#### <a name="vpn-split-tunnel"></a><span data-ttu-id="d0781-177">VPN 분할 터널</span><span class="sxs-lookup"><span data-stu-id="d0781-177">VPN Split Tunnel</span></span>

<span data-ttu-id="d0781-178">Exchange Online, SharePoint Online 및 Microsoft 팀에 대 한 각 최적화 범주 경로는 VPN에서 tunnelled 인지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-178">Each optimize category route for Exchange Online, SharePoint Online, and Microsoft Teams is tested to see if it is tunnelled on the VPN or not.</span></span> <span data-ttu-id="d0781-179">작업을 분할 하면 VPN 전체가 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-179">A split out workload avoids the VPN entirely.</span></span> <span data-ttu-id="d0781-180">Tunnelled 작업 부하는 모두 VPN을 통해 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-180">A tunnelled workload is all sent over the VPN.</span></span> <span data-ttu-id="d0781-181">선택적 tunnelled 작업에는 VPN을 통해 전송 되는 일부 경로와 몇 개의 분할이 있습니다. 모든 작업을 분할 또는 선택적 tunnelled 경우 통과 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-181">A selective tunnelled workload has some routes sent over the VPN and some split out. A passing result will show if all workloads are split out or selective tunnelled.</span></span>

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a><span data-ttu-id="d0781-182">대도시 영역에 있는 고객의 성능 향상</span><span class="sxs-lookup"><span data-stu-id="d0781-182">Customers in your metropolitan area with better performance</span></span>

<span data-ttu-id="d0781-183">Exchange Online 서비스에 대 한 사용자 사무실 위치의 네트워크 TCP 대기 시간은 같은 메트로 영역의 다른 Microsoft 365 고객과 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-183">The network TCP latency of the user office location to the Exchange Online service front door is compared to other Microsoft 365 customers in the same metro area.</span></span> <span data-ttu-id="d0781-184">네트워크에 대 한 자세한 내용은 같은 지하철 영역에 있는 고객 중 10% 이상이 더 나은 성능을 가진 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-184">A network insight is shown if 10% or more of customers in the same metro area have better performance.</span></span> <span data-ttu-id="d0781-185">즉, 사용자는 Microsoft 365 사용자 인터페이스에서 더 나은 성능을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-185">This means their users will have better performance in the Microsoft 365 user interface.</span></span>

<span data-ttu-id="d0781-186">이 네트워크 통찰력은 도시의 모든 사용자가 동일한 통신 인프라에 대 한 액세스 권한을 가지 며 인터넷 회로 및 Microsoft 네트워크와 같은 근접성을 갖게 된다는 것을 기반으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-186">This network insight is generated on the basis that all users in a city have access to the same telecommunications infrastructure and the same proximity to Internet circuits and Microsoft's network.</span></span>

#### <a name="time-to-make-a-dns-request-on-your-network"></a><span data-ttu-id="d0781-187">네트워크에서 DNS 요청을 만드는 시간</span><span class="sxs-lookup"><span data-stu-id="d0781-187">Time to make a DNS request on your network</span></span>

<span data-ttu-id="d0781-188">테스트를 실행 한 클라이언트 컴퓨터에 구성 된 DNS 서버를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-188">This shows the DNS server configured on the client machine that ran the tests.</span></span> <span data-ttu-id="d0781-189">DNS 재귀 확인 프로그램 서버 일 수 있지만 드문 경우는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-189">It might be a DNS Recursive Resolver server however this is uncommon.</span></span> <span data-ttu-id="d0781-190">DNS 결과를 캐시 하 고 캐시 되지 않은 DNS 요청을 다른 DNS 서버로 전달 하는 DNS 전달자 서버가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-190">It is more likely to be a DNS forwarder server which caches DNS results and forwards any uncached DNS requests to another DNS server.</span></span>

<span data-ttu-id="d0781-191">이는 정보를 제공 하기 위한 것 이며 네트워크 통찰력에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-191">This is provided for information only and does not contribute to any network insight.</span></span>

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a><span data-ttu-id="d0781-192">DNS 재귀 해결 프로그램에 연결할 때 까지의 거리 및/또는 시간</span><span class="sxs-lookup"><span data-stu-id="d0781-192">Your distance from and/or time to connect to a DNS recursive resolver</span></span>

<span data-ttu-id="d0781-193">사용 중인 DNS 재귀 해결 프로그램은 특정 DNS 요청을 수행한 다음 DNS 이름 서버에 동일한 요청을 받은 IP 주소를 물어 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-193">The in-use DNS Recursive Resolver is identified by making a specific DNS request and then asking the DNS Name Server for the IP Address that it received the same request from.</span></span> <span data-ttu-id="d0781-194">이 IP 주소는 DNS 재귀 해결 프로그램 이며 위치를 찾기 위해 IP 주소 위치 데이터베이스에서 조회 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-194">This IP Address is the DNS Recursive Resolver and it will be looked up in IP Address location databases to find the location.</span></span> <span data-ttu-id="d0781-195">그러면 사용자 사무실 위치에서 DNS 재귀 확인자 서버 위치로의 거리가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-195">The distance from the user office location to the DNS Recursive Resolver server location is then calculated.</span></span> <span data-ttu-id="d0781-196">이는 거리가 **500 마일** (800 킬로미터) 보다 크면 네트워크에 대 한 정보를 파악 하는 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-196">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers).</span></span>

<span data-ttu-id="d0781-197">네트워크 송신 IP 주소에서 조회 되는 위치는 정확 하지 않을 수 있으며이 테스트에서 잘못 된 결과가 이어집니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-197">The location looked up from the network egress IP Address may not be accurate and this would lead to a false result from this test.</span></span> <span data-ttu-id="d0781-198">특정 IP 주소에 대해이 오류가 발생 하는지 확인 하려면 공개적으로 액세스 가능한 네트워크 IP 주소 위치 웹 사이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-198">To validate if this error is occurring for a specific IP Address you can use publicly accessible network IP Address location web sites.</span></span>

<span data-ttu-id="d0781-199">이 네트워크 통찰력은 Exchange Online 서비스의 프런트 도어 선택에 특히 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-199">This network insight will specifically impact the selection of the Exchange Online service front door.</span></span> <span data-ttu-id="d0781-200">이 통찰력을 확인 하려면 로컬 및 직접 네트워크 송신이 필수 구성 요소 여야 하 고, DNS 재귀 해결 프로그램을 해당 네트워크 egress에 가까이에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-200">To address this insight local and direct network egress should be a pre-requisite and then DNS Recursive Resolver should be located close to that network egress.</span></span>

### <a name="exchange-online"></a><span data-ttu-id="d0781-201">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d0781-201">Exchange Online</span></span>

<span data-ttu-id="d0781-202">이 섹션에서는 Exchange Online과 관련 된 테스트 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-202">This section shows test results related to Exchange Online.</span></span>

#### <a name="exchange-service-front-door-location"></a><span data-ttu-id="d0781-203">Exchange 서비스 전면 도어 위치</span><span class="sxs-lookup"><span data-stu-id="d0781-203">Exchange service front door location</span></span>

<span data-ttu-id="d0781-204">사용 중인 Exchange service 프런트 도어는 Outlook에서이를 수행 하는 것과 동일한 방식으로 식별 되며, 사용자 위치에서 네트워크 TCP 대기 시간을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-204">The in-use Exchange service front door is identified in the same way that Outlook does this and we measure the network TCP latency from the user location to it.</span></span> <span data-ttu-id="d0781-205">TCP 대기 시간이 표시 되 고 사용 중 Exchange 서비스 전면 도어가 현재 위치에 대 한 모범 사례 서비스 전면 도어 목록과 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-205">The TCP latency is shown and the in-use Exchange service front door is compared to the list of best service front doors for the current location.</span></span> <span data-ttu-id="d0781-206">이는 최상의 Exchange 서비스 전면 도어 중 하나를 사용 하지 않는 경우 네트워크에 대 한 정보로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-206">This is shown as a network insight if one of the best Exchange service front door(s) is not in use.</span></span>

<span data-ttu-id="d0781-207">회사 네트워크를 송신 하기 전에 네트워크 교환이 너무 많이 발생 하는 경우 (예를 들어, 로컬 및 직접 네트워크 송신을 권장 하는 경우)에는 Exchange 서비스 프런트 도어 중 하나를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-207">Not using one of the best Exchange service front door(s) could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="d0781-208">또한 원격 DNS 재귀 해결 프로그램 서버를 사용 하는 경우에도 DNS 재귀 해결 프로그램 서버를 네트워크 egress에 정렬 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-208">It could also be caused by use of a remote DNS recursive resolver server in which case we recommend aligning the DNS recursive resolver server with the network egress.</span></span>

<span data-ttu-id="d0781-209">Exchange 서비스 전면 도어의 TCP 대기 시간 (ms)에 대 한 잠재적 개선이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-209">We calculate a potential improvement in TCP latency (ms) to the Exchange service front door.</span></span> <span data-ttu-id="d0781-210">이 작업은 테스트 된 사용자 사무실 위치 네트워크 대기 시간을 살펴보고 현재 위치에서 closets Exchange 서비스 전면 도어 까지의 네트워크 대기 시간을 빼서 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-210">This is done by looking at the tested user office location network latency and subtracting the network latency from the current location to the closets Exchange service front door.</span></span> <span data-ttu-id="d0781-211">차이점은 개선에 대 한 잠재적인 기회를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-211">The difference represents the potential opportunity for improvement.</span></span>

#### <a name="best-exchange-service-front-doors-for-your-location"></a><span data-ttu-id="d0781-212">사용자의 위치에 대 한 최상의 Exchange 서비스 전면 도어</span><span class="sxs-lookup"><span data-stu-id="d0781-212">Best Exchange service front door(s) for your location</span></span>

<span data-ttu-id="d0781-213">사용자 위치에 대해 도시별로 가장 적합 한 Exchange 서비스 프런트 도어 위치를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-213">This lists the best Exchange service front door locations by city for your location.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="d0781-214">클라이언트 DNS에 기록 된 서비스 전면 도어</span><span class="sxs-lookup"><span data-stu-id="d0781-214">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="d0781-215">여기에는 연결 하려는 Exchange 서비스 전면 도어 서버의 DNS 이름과 IP 주소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-215">This shows the DNS name and IP Address of the Exchange service front door server that you were directed to.</span></span> <span data-ttu-id="d0781-216">정보를 제공 하기 위한 것 이며 연결 된 네트워크 통찰력은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-216">It is provided for information only and there is no associated network insight.</span></span>

### <a name="sharepoint-online"></a><span data-ttu-id="d0781-217">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d0781-217">SharePoint Online</span></span>

<span data-ttu-id="d0781-218">이 섹션에서는 SharePoint Online 및 OneDrive와 관련 된 테스트 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-218">This section shows test results related to SharePoint Online and OneDrive.</span></span>

#### <a name="the-service-front-door-location"></a><span data-ttu-id="d0781-219">서비스 전방 도어 위치</span><span class="sxs-lookup"><span data-stu-id="d0781-219">The service front door location</span></span>

<span data-ttu-id="d0781-220">사용 중인 SharePoint service 프런트 도어는 OneDrive 클라이언트와 동일한 방식으로 식별 되며, 사용자 사무실 위치에서의 네트워크 TCP 대기 시간을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-220">The in-use SharePoint service front door is identified in the same way that the OneDrive client does and we measure the network TCP latency from the user office location to it.</span></span>

#### <a name="download-speed"></a><span data-ttu-id="d0781-221">다운로드 속도</span><span class="sxs-lookup"><span data-stu-id="d0781-221">Download speed</span></span>

<span data-ttu-id="d0781-222">SharePoint 서비스 전면 도어에서 15Mb 파일의 다운로드 속도를 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-222">We measure the download speed for a 15Mb file from the SharePoint service front door.</span></span> <span data-ttu-id="d0781-223">결과는 **1 초**에 SharePoint 또는 OneDrive에서 다운로드할 수 있는 크기 (mb)를 나타내기 위해 초당 mb로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-223">The result is shown in megabytes per second to indicate what size file in megabytes can be downloaded from SharePoint or OneDrive in **one second**.</span></span> <span data-ttu-id="d0781-224">이 숫자는 최소 회로 대역폭과 초당 1-10과 비슷해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-224">The number should be similar to one tenth of the minimum circuit bandwidth in megabits per second.</span></span> <span data-ttu-id="d0781-225">예를 들어 100mbps 인터넷 연결이 있는 경우 초당 10mb가 될 수 있습니다 (10MBps).</span><span class="sxs-lookup"><span data-stu-id="d0781-225">For example if you have a 100mbps internet connection, you may expect 10 megabytes per second (10MBps).</span></span>

#### <a name="buffer-bloat"></a><span data-ttu-id="d0781-226">버퍼 팽창</span><span class="sxs-lookup"><span data-stu-id="d0781-226">Buffer bloat</span></span>

<span data-ttu-id="d0781-227">15Mb 다운로드 중에 SharePoint 서비스 전면 도어의 TCP 대기 시간을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-227">During the 15Mb download we measure the TCP latency to the SharePoint service front door.</span></span> <span data-ttu-id="d0781-228">이 시간은 부하가 발생 하는 대기 시간으로, 부하가 발생 하지 않을 때의 대기 시간과 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-228">This is the latency under load and it is compared to the latency when not under load.</span></span> <span data-ttu-id="d0781-229">로드 하는 동안 대기 시간 증가는 종종 로드 되는 소비자 네트워크 장치 버퍼 (또는 증가가)로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-229">The increase in latency when under load is often attributable to consumer network device buffers being loaded (or bloated).</span></span> <span data-ttu-id="d0781-230">네트워크 통찰력은 1000 이상으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-230">A network insight is shown for any bloat of 1,000 or more.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="d0781-231">클라이언트 DNS에 기록 된 서비스 전면 도어</span><span class="sxs-lookup"><span data-stu-id="d0781-231">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="d0781-232">여기에는 보낸 SharePoint 서비스 프런트 엔드 서버의 DNS 이름과 IP 주소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-232">This shows the DNS name and IP Address of the SharePoint service front door server that you were directed to.</span></span> <span data-ttu-id="d0781-233">정보를 제공 하기 위한 것 이며 연결 된 네트워크 통찰력은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-233">It is provided for information only and there is no associated network insight.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="d0781-234">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0781-234">Microsoft Teams</span></span>

<span data-ttu-id="d0781-235">이 섹션에서는 Microsoft 팀과 관련 된 테스트 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-235">This section shows test results related to Microsoft Teams.</span></span>

#### <a name="media-connectivity-audio-video-and-application-sharing"></a><span data-ttu-id="d0781-236">미디어 연결 (오디오, 비디오 및 응용 프로그램 공유)</span><span class="sxs-lookup"><span data-stu-id="d0781-236">Media connectivity (audio, video, and application sharing)</span></span>

<span data-ttu-id="d0781-237">이를 통해 Microsoft 팀 서비스 전면 도어의 UDP 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-237">This tests for UDP connectivity to the Microsoft Teams service front door.</span></span> <span data-ttu-id="d0781-238">이 문제가 차단 되 면 Microsoft 팀 에서도 여전히 TCP를 사용할 수 있지만 오디오 및 비디오는 손상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-238">If this is blocked then Microsoft Teams may still work using TCP, but audio and video will be impaired.</span></span> <span data-ttu-id="d0781-239">[비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 에서 Microsoft 팀에도 적용 되는 이러한 UDP 네트워크 측정에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-239">Read more about these UDP network measurements which also apply to Microsoft Teams at [Media Quality and Network Connectivity Performance in Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)</span></span>

#### <a name="packet-loss"></a><span data-ttu-id="d0781-240">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="d0781-240">Packet loss</span></span>

<span data-ttu-id="d0781-241">클라이언트에서 Microsoft 팀 서비스 전면 도어로 10 초의 두 번째 테스트 오디오 호출로 측정 된 UDP 패킷 손실을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-241">Shows the UDP packet loss measured in a 10 second test audio call from the client to the Microsoft Teams service front door.</span></span> <span data-ttu-id="d0781-242">이는 패스의 **1.00%** 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-242">This should be lower than **1.00%** for a pass.</span></span>

### <a name="latency"></a><span data-ttu-id="d0781-243">대기 시간</span><span class="sxs-lookup"><span data-stu-id="d0781-243">Latency</span></span>

<span data-ttu-id="d0781-244">측정 된 UDP 대기 시간 ( **적고 100 밀리초**미만 이어야 함)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-244">Shows the measured UDP latency, which should be lower than **100ms**.</span></span>

#### <a name="jitter"></a><span data-ttu-id="d0781-245">지터</span><span class="sxs-lookup"><span data-stu-id="d0781-245">Jitter</span></span>

<span data-ttu-id="d0781-246">계산 된 UDP 지터를 표시 하며이 값은 **30ms**보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-246">Shows the measured UDP jitter, which should be lower than **30ms**.</span></span>

#### <a name="connectivity"></a><span data-ttu-id="d0781-247">연결</span><span class="sxs-lookup"><span data-stu-id="d0781-247">Connectivity</span></span>

<span data-ttu-id="d0781-248">사용자 사무실 위치에서 필요한 모든 Microsoft 365 네트워크 끝점에 대 한 HTTP 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-248">We test for HTTP connectivity from the user office location to all of the required Microsoft 365 network endpoints.</span></span> <span data-ttu-id="d0781-249">이러한 기능은에 게시 됩니다 [https://aka.ms/o365ip](https://aka.ms/o365ip) .</span><span class="sxs-lookup"><span data-stu-id="d0781-249">These are published at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="d0781-250">연결할 수 없는 모든 필수 네트워크 끝점에 대 한 네트워크 통찰력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-250">A network insight is shown for any required network endpoints which cannot be connected to.</span></span>

<span data-ttu-id="d0781-251">연결 ay는 회사 네트워크 경계에 있거나 클라우드 프록시로 사용 중인 프록시 서버, 방화벽 또는 다른 네트워크 보안 장치에 의해 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-251">Connectivity ay be blocked by a proxy server, a firewall, or another network security device on the enterprise network perimeter or in use as a cloud proxy.</span></span>

<span data-ttu-id="d0781-252">에서 정의 된 최적화 또는 허용 범주에 있는 각각의 필수 Microsoft 365 네트워크 끝점에서 SSL 인증서를 테스트 합니다 [https://aka.ms/o365ip](https://aka.ms/o365ip) .</span><span class="sxs-lookup"><span data-stu-id="d0781-252">We test the SSL certificate at each required Microsoft 365 network endpoint that is in the optimize or allow category as defined at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="d0781-253">Microsoft SSL 인증서를 찾지 못하는 테스트는 중간 네트워크 장치에 의해 연결 된 암호화 된 네트워크를 차단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-253">If any tests do not find a Microsoft SSL certificate, then the encrypted network connected must have been intercepted by an intermediary network device.</span></span> <span data-ttu-id="d0781-254">네트워크에 대 한 통찰력은 모든 암호화 된 네트워크 끝점에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-254">A network insight is shown on any intercepted encrypted network endpoints.</span></span>

<span data-ttu-id="d0781-255">Microsoft에서 제공 하지 않는 SSL 인증서가 발견 되 면 테스트에 대 한 FQDN과 사용 중인 SSL 인증서 소유자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-255">Where an SSL certificate is found that isn't provided by Microsoft, we show the FQDN for the test and the in-use SSL certificate owner.</span></span> <span data-ttu-id="d0781-256">SSL 인증서 소유자는 프록시 서버 공급 업체가 될 수도 있고, 엔터프라이즈 자체 서명 된 인증서 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-256">This SSL certificate owner may be a proxy server vendor, or it may be an enterprise self-signed certificate.</span></span>

#### <a name="network-path"></a><span data-ttu-id="d0781-257">네트워크 경로</span><span class="sxs-lookup"><span data-stu-id="d0781-257">Network path</span></span>

<span data-ttu-id="d0781-258">이 섹션에서는 Exchange Online 서비스 전면 도어, SharePoint Online 서비스 전면 도어 및 Microsoft 팀 서비스 전면 도어에 대 한 ICMP traceroute 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-258">This section shows the results of an ICMP traceroute to the Exchange Online service front door, the SharePoint Online service front door, and the Microsoft Teams service front door.</span></span> <span data-ttu-id="d0781-259">정보를 제공 하기 위한 것 이며 연결 된 네트워크 통찰력은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-259">It is provided for information only and there is no associated network insight.</span></span> <span data-ttu-id="d0781-260">3 개의 traceroutes 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-260">There are three traceroutes provided.</span></span> <span data-ttu-id="d0781-261">_Outlook.office365.com_에 대 한 traceroute, 고객 SharePoint 프런트 엔드에 대 한 traceroute 또는 _microsoft.sharepoint.com_ 에 대 한 _traceroute를 제공 합니다._</span><span class="sxs-lookup"><span data-stu-id="d0781-261">A traceroute to _outlook.office365.com_, a traceroute to the customers SharePoint front end or to _microsoft.sharepoint.com_ if one was not provided, and a traceroute to _world.tr.teams.microsoft.com_.</span></span>

## <a name="connectivity-reports"></a><span data-ttu-id="d0781-262">연결 보고서</span><span class="sxs-lookup"><span data-stu-id="d0781-262">Connectivity reports</span></span>

<span data-ttu-id="d0781-263">로그인 한 경우 이전에 실행 한 보고서를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-263">When you are signed in you can review previous reports that you have run.</span></span> <span data-ttu-id="d0781-264">또한 목록에서 공유 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-264">You can also share them or delete them from the list.</span></span>

![보고서](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a><span data-ttu-id="d0781-266">네트워크 상태</span><span class="sxs-lookup"><span data-stu-id="d0781-266">Network health status</span></span>

<span data-ttu-id="d0781-267">여기에는 microsoft 365 고객에 게 영향을 줄 수 있는 Microsoft의 글로벌 네트워크에 대 한 중요 한 상태 문제가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-267">This shows any significant health issues with Microsoft's global network which might impact Microsoft 365 customers.</span></span>

![네트워크 상태](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a><span data-ttu-id="d0781-269">FAQ</span><span class="sxs-lookup"><span data-stu-id="d0781-269">FAQ</span></span>

<span data-ttu-id="d0781-270">다음은 자주 묻는 몇 가지 질문에 대 한 대답입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-270">Here are answers to some of our frequently asked questions.</span></span>

### <a name="is-this-tool-released-and-supported-by-microsoft"></a><span data-ttu-id="d0781-271">이 도구는 Microsoft에서 출시 및 지원 하나요?</span><span class="sxs-lookup"><span data-stu-id="d0781-271">Is this tool released and supported by Microsoft?</span></span>

<span data-ttu-id="d0781-272">현재는 미리 보기 이며 Microsoft의 지원을 통해 일반 가용성 릴리스 상태에 도달할 때까지 정기적으로 업데이트를 제공 하는 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-272">It is currently a preview and we plan to provide updates regularly until we reach general availability release status with support from Microsoft.</span></span> <span data-ttu-id="d0781-273">개선에 도움이 되는 의견을 제공 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0781-273">Please provide feedback to help us improve.</span></span> <span data-ttu-id="d0781-274">테스트 결과를 기준으로 조직에 대해 사용자 지정 된이 도구의 일부로 보다 자세한 Office 365 네트워크 온 보 딩 가이드를 게시할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-274">We are planning to publish a more detailed Office 365 Network Onboarding guide as part of this tool which is customized for the organization by its test results.</span></span>

### <a name="what-is-microsoft-365-service-front-door"></a><span data-ttu-id="d0781-275">Microsoft 365 서비스 전면 도어 란?</span><span class="sxs-lookup"><span data-stu-id="d0781-275">What is Microsoft 365 service front door?</span></span>

<span data-ttu-id="d0781-276">Microsoft 365 서비스 전면 도어는 Microsoft의 글로벌 네트워크에서 Office 클라이언트 및 서비스가 네트워크 연결을 종료 하는 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-276">The Microsoft 365 service front door is an entry point on Microsoft's global network where Office clients and services terminate their network connection.</span></span> <span data-ttu-id="d0781-277">Microsoft 365에 대 한 최적의 네트워크 연결을 위해 네트워크 연결이 도시나 메트로 가장 가까운 Microsoft 365 전면 도어로 종료 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-277">For an optimal network connection to Microsoft 365, it is recommended that your network connection is terminated into the closest Microsoft 365 front door in your city or metro.</span></span>

<span data-ttu-id="d0781-278">참고: Microsoft 365 서비스 전면 도어는 Azure marketplace에서 제공 되는 **azure Direct 도어 서비스** 제품과 직접 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-278">Note: Microsoft 365 service front door has no direct relationship to the **Azure Front Door Service** product available in the Azure marketplace.</span></span>

### <a name="what-is-the-best-microsoft-365-service-front-door"></a><span data-ttu-id="d0781-279">가장 적합 한 Microsoft 365 서비스 전면 도어는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d0781-279">What is the best Microsoft 365 service front door?</span></span>

<span data-ttu-id="d0781-280">가장 적합 한 Microsoft 365 서비스 전면 도어 (이전의 가장 적합 한 서비스 전면 도어)는 네트워크 egress에서 일반적으로 구/군/시 또는 지하철 지역에 가깝습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-280">A best Microsoft 365 service front door (formerly known as an optimal service front door) is one that is closest to your network egress, generally in your city or metro area.</span></span> <span data-ttu-id="d0781-281">Microsoft 365 네트워크 성능 도구를 사용 하 여 사용 중인 Microsoft 365 서비스 전면 도어의 위치 및 모범 서비스 전면 도어를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-281">Use the Microsoft 365 network performance tool to determine location of your in-use Microsoft 365 service front door and the best service front door(s).</span></span> <span data-ttu-id="d0781-282">도구에서 사용자가 사용 하는 프런트 도어 중 하나에 해당 하는 경우 Microsoft의 글로벌 네트워크에 대 한 연결을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-282">If the tool determines your in-use front door is one of the best ones, then you should expect great connectivity into Microsoft's global network.</span></span>

### <a name="what-is-an-internet-egress-location"></a><span data-ttu-id="d0781-283">인터넷 송신 위치 란?</span><span class="sxs-lookup"><span data-stu-id="d0781-283">What is an internet egress location?</span></span>

<span data-ttu-id="d0781-284">인터넷 송신 위치는 네트워크 트래픽이 기업 네트워크를 종료 하 고 인터넷에 연결 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-284">The internet egress Location is the location where your network traffic exits your enterprise network and connects to the Internet.</span></span> <span data-ttu-id="d0781-285">또한 NAT (Network Address Translation) 장치가 있는 위치로도 식별 되며, 대개 ISP (인터넷 서비스 공급자)와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-285">This is also identified as the location where you have a Network Address Translation (NAT) device and usually where you connect with an Internet Service Provider (ISP).</span></span> <span data-ttu-id="d0781-286">위치와 인터넷 송신 위치 사이에 긴 거리가 표시 되 면이로 인해 상당한 WAN 백을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0781-286">If you see a long distance between your location and your internet egress location, then this may identify a significant WAN backhaul.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0781-287">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d0781-287">Related topics</span></span>

[<span data-ttu-id="d0781-288">Microsoft 365 관리 센터의 네트워크 성능 권장 사항 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d0781-288">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="d0781-289">Microsoft 365 network performance insights (preview)</span><span class="sxs-lookup"><span data-stu-id="d0781-289">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="d0781-290">Microsoft 365 네트워크 평가 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d0781-290">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="d0781-291">Microsoft 365 네트워크 연결 위치 서비스 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d0781-291">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
