---
title: Microsoft 365 정보 네트워크 라우팅
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 정보 네트워크 라우팅
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717589"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="14fac-103">Microsoft 365 정보 네트워크 라우팅(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="14fac-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="14fac-104">정보 네트워크 라우팅은 Microsoft 서비스 끝점에 대한 네트워크 연결을 최적화하고 개선하기 위해 다양한 Microsoft 365 응용 프로그램을 타사 SD-WAN(소프트웨어 정의 네트워크) 솔루션과 통합하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="14fac-105">최적화된 SD-WAN 연결로 인해 사용자 환경 및 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="14fac-106">Microsoft 365 정보 네트워크 라우팅은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="14fac-107">지원을 받는 지침을 포함하여 이 미리 보기에 대한 자세한 내용은 [Microsoft 365의](https://go.microsoft.com/fwlink/?linkid=2151565)정보 제공 네트워크 라우팅 공개 미리 보기 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14fac-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="14fac-108">개요</span><span class="sxs-lookup"><span data-stu-id="14fac-108">Overview</span></span>

<span data-ttu-id="14fac-109">정보 네트워크 라우팅은 Microsoft와 SD-WAN 솔루션 간에 양방향 데이터 공유 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="14fac-110">구성하는 모든 사무실 위치 및 인터넷 회로에 대해 Microsoft는 각 특정 인터넷 회로와 연결된 네트워크 트래픽에 대해 선택한 Microsoft 365 응용 프로그램 환경의 품질에 대한 피드백을 SD-WAN 솔루션과 주기적으로 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="14fac-111">이 피드백을 사용하여 SD-WAN 솔루션은 사용 가능한 대체 링크를 통해 Microsoft 365 응용 프로그램 트래픽을 라우팅하여 스마트 복구 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="14fac-112">대기 시간 증가 또는 높은 패킷 손실과 같은 특정 인터넷 회로 경로의 서비스 품질 저하는 지속적으로 감지하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="14fac-113">이러한 저하는 Exchange Online, SharePoint, OneDrive 및 Microsoft Teams와 같은 응용 프로그램에 대한 사용자 환경의 저하로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="14fac-114">일반적인 증상으로는 Exchange 콘텐츠 검색 속도가 느려지거나, SharePoint 또는 OneDrive 문서 라이브러리와 상호 작용할 때 전송 속도가 늦거나, Microsoft Teams에서 통화 또는 모임 품질이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="14fac-115">네트워크 정보 라우팅 내의 피드백 및 복구 메커니즘은 거의 실시간으로 이러한 문제를 동적으로 감지하고 배포된 SD-WAN 솔루션에 자동 복구 작업을 수행하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="14fac-116">또한 데이터 공유 채널은 장치 및 연결된 회로와 관련된 구성 정보 및 사용 통계를 포함하여 SD-WAN 솔루션에서 네트워크 수준 광학 데이터를 주기적으로 수신하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="14fac-117">개인 정보는 수집되거나 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-117">No personal information is collected or stored.</span></span> <span data-ttu-id="14fac-118">수집된 모든 정보는 사무실 위치 및 연결된 인터넷 회로로 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="14fac-119">이 정보는 Microsoft가 Microsoft 365 서비스 및 응용 프로그램을 사용할 때 보고된 문제를 보다 효율적이고 효과적으로 해결하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="14fac-120">Microsoft 365의 정보 제공 네트워크 라우팅은 WW Commercial 클라우드의 테넌트는 지원하지만 GCC Moderate, GCC High, DoD, Germany 또는 중국 클라우드는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="14fac-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14fac-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="14fac-122">통합 SD-WAN 솔루션</span><span class="sxs-lookup"><span data-stu-id="14fac-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="14fac-123">Microsoft는 다양한 파트너와 협력하여 Microsoft 365 정보 네트워크 라우팅과의 통합을 활성화하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="14fac-124">현재 사용하도록 설정된 솔루션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="14fac-125">장치 제작자</span><span class="sxs-lookup"><span data-stu-id="14fac-125">Device Maker</span></span> | <span data-ttu-id="14fac-126">솔루션 이름</span><span class="sxs-lookup"><span data-stu-id="14fac-126">Solution Name</span></span> | <span data-ttu-id="14fac-127">최소 버전</span><span class="sxs-lookup"><span data-stu-id="14fac-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="14fac-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="14fac-128">Cisco</span></span> | [<span data-ttu-id="14fac-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="14fac-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="14fac-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="14fac-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="14fac-131">네트워크 토폴로지</span><span class="sxs-lookup"><span data-stu-id="14fac-131">Network topology</span></span>

<span data-ttu-id="14fac-132">정보 네트워크 라우팅은 현재 Microsoft로 네트워크 트래픽을 보내는 데 사용되는 공용 IP 주소를 기반으로 특정 사무실 위치 및 인터넷 회로와 연결된 트래픽을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="14fac-133">분기 위치에 직접 인터넷 액세스를 제공하는 네트워크 회로가 하나 이상 없는 경우 네트워크 정보 라우팅에서 중요한 가치를 제공하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="14fac-134">응용 프로그램 사용 현황</span><span class="sxs-lookup"><span data-stu-id="14fac-134">Application usage</span></span>

<span data-ttu-id="14fac-135">응용 프로그램 환경 데이터(네트워크 품질 메트릭을 통해 반영)는 특정 Microsoft 클라이언트 응용 프로그램의 사용을 통해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-135">Application experience data (reflected through network quality metrics) is collected through usage of specific Microsoft client applications.</span></span> <span data-ttu-id="14fac-136">Exchange 메트릭은 Outlook 클라이언트의 사용과 일부 Outlook Web App 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-136">Exchange metrics reflect usage of the Outlook client as well as some Outlook Web App usage.</span></span> <span data-ttu-id="14fac-137">SharePoint 및 OneDrive 메트릭은 클라이언트 응용 프로그램에 관계없이 테넌트별 SharePoint 끝점의 사용을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-137">SharePoint and OneDrive metrics reflect usage of the tenant-specific SharePoint endpoints, regardless of client application.</span></span> <span data-ttu-id="14fac-138">Teams 메트릭은 Teams 데스크톱 클라이언트의 사용을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-138">Teams metrics reflect usage of the Teams desktop client.</span></span> <span data-ttu-id="14fac-139">네트워크 회로의 상태 평가 시 다른 응용 프로그램 트래픽은 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-139">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="14fac-140">정보 제공 네트워크 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="14fac-140">Enabling informed network routing</span></span>

<span data-ttu-id="14fac-141">정보를 제공된 네트워크 라우팅을 사용하려면 여러 단계가 필요하고, 그 중 일부는 SD-WAN 솔루션의 구성 인터페이스 내에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-141">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="14fac-142">Microsoft 365 관리 센터에서 구성을 진행하기 전에 SD-WAN 솔루션 내에서 네트워크 정보 라우팅을 사용하도록 설정하는 프로세스를 시작하는 방법에 대한 지침은 SD-WAN 솔루션 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="14fac-142">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="14fac-143">Microsoft 365 관리 센터에서 정보 네트워크 라우팅을 사용하도록 설정할 준비가 되면 필요한 전역 관리자 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-143">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="14fac-144">선택한 SD-WAN 솔루션에서 정보 제공된 네트워크 라우팅 데이터 공유 채널에 액세스하는 데 필요한 테넌트 수준 응용 프로그램 사용 권한을 제공하려면 전역 관리자로서 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-144">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="14fac-145">1단계: SD-WAN 솔루션 구성 옵션 열기</span><span class="sxs-lookup"><span data-stu-id="14fac-145">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="14fac-146">Microsoft [365](https://admin.microsoft.com/)관리 센터의 왼쪽 **탐색 창에서** 상태 > 네트워크 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-146">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="14fac-147">관리 센터의 이 섹션에서는 조직에 대한 집계된 네트워크 연결 메트릭과 연결을 개선하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-147">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="14fac-148">관리 센터 내에서 사용할 수 있는 이러한 기능에 대한 자세한 내용은 [Microsoft 365](office-365-network-mac-perf-overview.md) 관리 센터의 네트워크 연결(미리 보기)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14fac-148">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="14fac-149">**SD-WAN >** 설정을 선택하여 정보 제공된 네트워크 라우팅 구성 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-149">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="14fac-150">설정 아래에 나타나는  다른 옵션은 관리 센터의 일반 네트워크 연결 지침에 적용될 수 있으며, 정보 제공된 네트워크 라우팅을 사용하도록 설정하는 데 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-150">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="14fac-151">구성 창에서 **SD-WAN 솔루션 추가(미리 보기)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="14fac-151">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="14fac-152">2단계: SD-WAN 솔루션 및 데이터 저장소 위치 선택</span><span class="sxs-lookup"><span data-stu-id="14fac-152">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="14fac-153">드롭다운 상자에서 배포한 SD-WAN 솔루션과 네트워크 정보 라우팅과 연결된 데이터를 저장할 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-153">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="14fac-154">자세한 [내용은 데이터 저장소](#data-storage) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14fac-154">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="14fac-155">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-155">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="14fac-156">3단계: 데이터 공유 조건 수락</span><span class="sxs-lookup"><span data-stu-id="14fac-156">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="14fac-157">Microsoft와 선택한 SD-WAN 솔루션 간의 데이터 공유와 관련된 제공된 용어를 신중하게 읽고 확인한 다음 표시된 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-157">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="14fac-158">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-158">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="14fac-159">4단계: SD-WAN 솔루션에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="14fac-159">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="14fac-160">이 단계에서는 Azure AD(Azure Active Directory)에 대한 권한 부여 요청을 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-160">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="14fac-161">선택한 SD-WAN 솔루션이 테넌트와 연결된 정보 네트워크 라우팅 데이터 저장소 및 서비스 상태 정보에 액세스할 수 있도록 허용하는 테넌트 수준 권한을 부여하도록 요청됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-161">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="14fac-162">이 작업을 수행하려면 전역 관리자 역할 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-162">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="14fac-163">이 응용 프로그램에 대한 사용 권한 **부여 링크를 선택하고** Azure AD 요청을 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="14fac-163">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="14fac-164">사용 권한 부여를 완료한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="14fac-164">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="14fac-165">5단계: 구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="14fac-165">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="14fac-166">테넌트에 대해 네트워크 정보 라우팅을 사용하도록 설정하는 마지막 단계는 제공한 설정을 표시하는 확인 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-166">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="14fac-167">이제 테넌트에 대해 정보 네트워크 라우팅이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-167">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="14fac-168">**완료를** 선택한 다음 SD-WAN 솔루션 구성 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-168">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="14fac-169">네트워크 정보 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="14fac-169">Configuring network informed routing</span></span>

<span data-ttu-id="14fac-170">SD-WAN 솔루션 내에서 정보 네트워크 라우팅에 대한 많은 구성을 수행하게 됩니다. 예를 들어 정상적인 상황에서 트래픽을 라우팅하는 방법 및 문제가 감지된 경우 사용할 대체 경로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-170">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="14fac-171">이러한 구성 단계에 대한 자세한 내용은 SD-WAN 솔루션 공급자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="14fac-171">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="14fac-172">정보 제공된 네트워크 라우팅이 이러한 위치에 대한 연결을 제공하는 네트워크 회로와 연결된 트래픽을 제대로 식별할 수 있도록 Microsoft 365 관리 센터에서 각 사무실 위치를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-172">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="14fac-173">Office 위치는 Microsoft의 지속적인 네트워크 원격 분석 컬렉션의 일부로 자동 검색될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-173">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="14fac-174">따라서 일부 위치는 테넌트의 관리 센터에 미리 채워지는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-174">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="14fac-175">이러한 위치가 정확하면 원하는 각 위치에 대해 정보 제공 네트워크 라우팅 기능을 사용하도록 설정하고 인터넷 회로 및 공용 IP 주소를 구성하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-175">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="14fac-176">자동 검색 위치가 정확하지 않은 경우 또는 테넌트에 미리 채워진 위치가 없는 경우 조직의 정확한 토폴로지가 반영될 수 있도록 위치를 수동으로 추가하거나 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-176">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="14fac-177">위치 업데이트</span><span class="sxs-lookup"><span data-stu-id="14fac-177">Updating locations</span></span>

<span data-ttu-id="14fac-178">테넌트의 위치는 위치 **탭에서** 찾을 수 있습니다. 위치는 목록에서 직접 편집하거나 CSV 파일을 사용하여 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-178">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="14fac-179">정보 네트워크 라우팅을 사용하도록 설정할 각 사무실 위치가 이 목록에 표시되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-179">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="14fac-180">수집된 샘플  및 기타 평가 관련 정보에 대한 위치 목록의 열은 정보 제공된 네트워크 라우팅 기능과 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-180">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="14fac-181">정보 네트워크 라우팅 위치 사용</span><span class="sxs-lookup"><span data-stu-id="14fac-181">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="14fac-182">위치 **목록에서** 빠른 **작업** 메뉴에서 편집을 선택하여 위치 구성 창을 니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-182">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="14fac-183">이 **위치에서 Microsoft 365 정보 네트워크 라우팅 사용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="14fac-183">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="14fac-184">이 사무실 위치 섹션의 **Egress IP 주소** 범위에서 이 사무실 위치에 대한 인터넷 연결을 제공하는 모든 네트워크 회로를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-184">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="14fac-185">각 회로가 네트워크 트래픽을 나타내는 고유한 공용 IP 주소 서브넷과 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-185">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="14fac-186">변경 내용을 저장하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-186">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="14fac-187">네트워크 정보 라우팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-187">Disabling network informed routing</span></span>

<span data-ttu-id="14fac-188">SD-WAN 솔루션 설정을 다시 설정하여 전체 테넌트에 대해 정보 제공 네트워크 라우팅 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-188">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="14fac-189">이렇게 하면 Microsoft 365 내의 모든 데이터 처리가 중지되는 반면 관리 센터 내에서 네트워크 정보 라우팅을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-189">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="14fac-190">1단계: SD-WAN 솔루션 구성 옵션 열기</span><span class="sxs-lookup"><span data-stu-id="14fac-190">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="14fac-191">Microsoft [365](https://admin.microsoft.com/) 관리 센터의 왼쪽 탐색 **창에서** 상태 > 네트워크 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-191">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="14fac-192">**SD-WAN >** 설정을 선택하여 정보 제공된 네트워크 라우팅 구성 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-192">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="14fac-193">구성 창에는 현재 구성된 SD-WAN 솔루션의 요약이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-193">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="14fac-194">2단계: 구성 다시 설정</span><span class="sxs-lookup"><span data-stu-id="14fac-194">Step 2: Reset your configuration</span></span>

<span data-ttu-id="14fac-195">구성 창에서 **SD-WAN** 솔루션 설정 다시 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-195">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="14fac-196">이제 설정이 다시 설정되고 정보 네트워크 라우팅이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-196">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="14fac-197">정보 네트워크 라우팅 사용의 단계에 따라 원하는 경우 다시 사용하도록 설정할 [수 있습니다.](#enabling-informed-network-routing)</span><span class="sxs-lookup"><span data-stu-id="14fac-197">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="14fac-198">데이터 저장소</span><span class="sxs-lookup"><span data-stu-id="14fac-198">Data storage</span></span>

<span data-ttu-id="14fac-199">Microsoft와 SD-WAN 솔루션 공급자 간에 교환되는 데이터는 네트워크 정보 라우팅을 처음 사용하도록 설정하는 동안 선택한 데이터 저장소 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-199">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="14fac-200">데이터 저장소 위치 옵션은 데이터가 저장되는 Microsoft Azure 지역이 포함된 지리적 영역을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-200">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="14fac-201">미리 보기 단계에서 사용할 수 있는 유일한 데이터 저장소 위치는 **북미입니다.**</span><span class="sxs-lookup"><span data-stu-id="14fac-201">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="14fac-202">정보 네트워크 라우팅이 일반적이기 전에 추가 데이터 저장소 위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-202">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="14fac-203">데이터는 최대 30일 동안 이 위치에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-203">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="14fac-204">사용하지 않도록 설정하면 남은 모든 데이터가 이 30일 보존 기간 내에 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="14fac-204">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="14fac-205">관련 항목</span><span class="sxs-lookup"><span data-stu-id="14fac-205">Related topics</span></span>

[<span data-ttu-id="14fac-206">Microsoft 365 관리 센터의 네트워크 연결(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="14fac-206">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="14fac-207">Microsoft 365 Network Connectivity Location Services(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="14fac-207">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
