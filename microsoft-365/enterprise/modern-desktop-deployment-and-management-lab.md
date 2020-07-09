---
title: Windows 및 Office 배포 랩 키트
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows 및 Office 배포 랩 키트에 액세스하는 방법 및 위치에 대해 알아보세요.
ms.openlocfilehash: a52d2ef1570509150aa1b44c7d7d767287e308f1
ms.sourcegitcommit: 020b89b0d558a866ea68d35b5170db76f6d8d74d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45052728"
---
# <a name="windows-and-office-deployment-lab-kit"></a><span data-ttu-id="793b3-103">Windows 및 Office 배포 랩 키트</span><span class="sxs-lookup"><span data-stu-id="793b3-103">Windows and Office Deployment Lab Kit</span></span>

<span data-ttu-id="793b3-104">이 랩은 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱을 실행하는 데스크톱의 배포 및 관리를 계획, 테스트 및 검증하는 데 도움을 주기 위해 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-104">These labs are designed to help you plan, test and validate your deployment and management of desktops running Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="793b3-105">이 랩에서는 Microsoft Endpoint Configuration Manager, Desktop Analytics, Office 사용자 지정 도구, OneDrive, Windows Autopilot 등의 데스크톱 배포 도구에 설명된 단계와 도구를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-105">The labs cover the steps and tools outlined in the Desktop Deployment wheel, spanning Microsoft Endpoint Configuration Manager, Desktop Analytics, Office Customization Tool, OneDrive, Windows Autopilot and more.</span></span>

<span data-ttu-id="793b3-106">이 교육은 Windows 7 사용 종료를 준비하는 조직에 권장되며 현재 Windows 10 및 엔터프라이즈용 Microsoft 365 앱(이전 Office 365 ProPlus) 또는 Office 2019를 사용 중인 경우에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-106">This training is highly recommended for organizations preparing for Windows 7 end of life, and also applies if you're currently using Windows 10 and Microsoft 365 Apps for enterprise (formerly Office 365 ProPlus) or Office 2019.</span></span> <span data-ttu-id="793b3-107">또한 격리된 환경으로서 랩은 배포 도구 업데이트를 탐색하고 배포 관련 자동화를 테스트하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-107">Additionally, as an isolated environment, the lab is ideal for exploring deployment tool updates and testing your deployment-related automation.</span></span>

<span data-ttu-id="793b3-108">[Windows 및 Office 배포 랩 키트 다운로드](https://www.microsoft.com/evalcenter/evaluate-lab-kit)</span><span class="sxs-lookup"><span data-stu-id="793b3-108">[Download the Windows and Office Deployment Lab Kit](https://www.microsoft.com/evalcenter/evaluate-lab-kit).</span></span>

## <a name="a-complete-lab-environment"></a><span data-ttu-id="793b3-109">전체 랩 환경</span><span class="sxs-lookup"><span data-stu-id="793b3-109">A complete lab environment</span></span>

<span data-ttu-id="793b3-110">랩은 도메인 가입 데스크톱 클라이언트, 도메인 컨트롤러, 인터넷 게이트웨이 및 완전히 구성된 구성 매니저 인스턴스를 포함하여 자동으로 프로비저닝된 가상 랩 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-110">The lab provides you with an automatically provisioned virtual lab environment, including domain-joined desktop clients, domain controller, Internet gateway and a fully configured Configuration Manager instance.</span></span> <span data-ttu-id="793b3-111">랩에는 다음 제품의 최신 평가판 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-111">The lab contains the latest Evaluation Versions of the following products:</span></span>

  - <span data-ttu-id="793b3-112">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-112">NEW!</span></span> <span data-ttu-id="793b3-113">Windows 10 Enterprise, 버전 2004</span><span class="sxs-lookup"><span data-stu-id="793b3-113">Windows 10 Enterprise, Version 2004</span></span>
  - <span data-ttu-id="793b3-114">Windows 7 Enterprise</span><span class="sxs-lookup"><span data-stu-id="793b3-114">Windows 7 Enterprise</span></span>
  - <span data-ttu-id="793b3-115">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-115">NEW!</span></span> <span data-ttu-id="793b3-116">Microsoft Endpoint Configuration Manager, 버전 2002</span><span class="sxs-lookup"><span data-stu-id="793b3-116">Microsoft Endpoint Configuration Manager, Version 2002</span></span>
  - <span data-ttu-id="793b3-117">Windows 10용 Windows 평가 및 배포 키트</span><span class="sxs-lookup"><span data-stu-id="793b3-117">Windows Assessment and Deployment Kit for Windows 10</span></span>
  - <span data-ttu-id="793b3-118">Microsoft Deployment Toolkit</span><span class="sxs-lookup"><span data-stu-id="793b3-118">Microsoft Deployment Toolkit</span></span>
  - <span data-ttu-id="793b3-119">Microsoft Application Virtualization(App-V)</span><span class="sxs-lookup"><span data-stu-id="793b3-119">Microsoft Application Virtualization (App-V)</span></span>
  - <span data-ttu-id="793b3-120">Microsoft BitLocker 관리 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="793b3-120">Microsoft BitLocker Administration and Monitoring</span></span> 
  - <span data-ttu-id="793b3-121">Windows Server</span><span class="sxs-lookup"><span data-stu-id="793b3-121">Windows Server</span></span> 
  - <span data-ttu-id="793b3-122">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="793b3-122">Microsoft SQL Server</span></span> 

<span data-ttu-id="793b3-123">또한, 랩은 다음에 대한 평가판에 연결되도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-123">PLUS, the lab is designed to be connected to trials for:</span></span> 

  - <span data-ttu-id="793b3-124">Microsoft 365 E5 또는</span><span class="sxs-lookup"><span data-stu-id="793b3-124">Microsoft 365 E5, or</span></span>
  - <span data-ttu-id="793b3-125">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="793b3-125">Office 365 Enterprise E5</span></span>
  - <span data-ttu-id="793b3-126">Enterprise Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="793b3-126">Enterprise Mobility + Security</span></span>

## <a name="step-by-step-labs"></a><span data-ttu-id="793b3-127">단계별 랩</span><span class="sxs-lookup"><span data-stu-id="793b3-127">Step-by-step labs</span></span>

<span data-ttu-id="793b3-128">자세한 랩 가이드는 여러 배포 및 관리 시나리오를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-128">Detailed lab guides take you through multiple deployment and management scenarios.</span></span> <span data-ttu-id="793b3-129">최신 버전의 Intune 및 Configuration Manager에 대한 랩이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="793b3-129">The labs have been updated for the latest versions of Intune and Configuration Manager.</span></span> 

### <a name="device-and-app-readiness"></a><span data-ttu-id="793b3-130">장치 및 앱 준비</span><span class="sxs-lookup"><span data-stu-id="793b3-130">Device and App Readiness</span></span>

  - <span data-ttu-id="793b3-131">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="793b3-131">Desktop Analytics</span></span>
  - <span data-ttu-id="793b3-132">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-132">NEW!</span></span> <span data-ttu-id="793b3-133">새 Microsoft Edge 배포 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="793b3-133">Deploy and update the new Microsoft Edge</span></span> 
  - <span data-ttu-id="793b3-134">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-134">NEW!</span></span> <span data-ttu-id="793b3-135">CMG(클라우드 관리 게이트웨이) 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="793b3-135">Install and configure the Cloud Management Gateway (CMG)</span></span> 
  - <span data-ttu-id="793b3-136">Internet Explorer 모드</span><span class="sxs-lookup"><span data-stu-id="793b3-136">Internet Explorer Mode</span></span> 
  - <span data-ttu-id="793b3-137">Application Guard</span><span class="sxs-lookup"><span data-stu-id="793b3-137">Application Guard</span></span> 

### <a name="directory-and-network-readiness"></a><span data-ttu-id="793b3-138">디렉터리 및 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="793b3-138">Directory and Network Readiness</span></span>

  - <span data-ttu-id="793b3-139">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-139">NEW!</span></span> <span data-ttu-id="793b3-140">Windows 10 업데이트 제공 최적화</span><span class="sxs-lookup"><span data-stu-id="793b3-140">Optimize Windows 10 Update Delivery</span></span> 
  - <span data-ttu-id="793b3-141">구성 관리자 및 Microsoft Intune 공동 관리</span><span class="sxs-lookup"><span data-stu-id="793b3-141">Configuration Manager and Microsoft Intune Co-Management</span></span>
  - <span data-ttu-id="793b3-142">원격 액세스(VPN)</span><span class="sxs-lookup"><span data-stu-id="793b3-142">Remote Access (VPN)</span></span>

### <a name="office-and-lob-app-delivery"></a><span data-ttu-id="793b3-143">Office 및 LOB 앱 제공</span><span class="sxs-lookup"><span data-stu-id="793b3-143">Office and LOB App Delivery</span></span>

  - <span data-ttu-id="793b3-144">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="793b3-144">Microsoft 365 Apps for enterprise</span></span>
  - <span data-ttu-id="793b3-145">구성 관리자 및 Microsoft Intune을 사용한 엔터프라이즈 관리 배포</span><span class="sxs-lookup"><span data-stu-id="793b3-145">Enterprise Managed Deployment using Configuration Manager and Microsoft Intune</span></span>
  - <span data-ttu-id="793b3-146">Microsoft Intune을 사용하여 응용 프로그램 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="793b3-146">Application deployment and management using Microsoft Intune</span></span>
  - <span data-ttu-id="793b3-147">비즈니스용 Microsoft Store를 사용하여 앱 배포 및 셀프 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="793b3-147">App deployment and self-service installation using Microsoft Store for Business</span></span>
  - <span data-ttu-id="793b3-148">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-148">NEW!</span></span> <span data-ttu-id="793b3-149">Microsoft Teams 설치</span><span class="sxs-lookup"><span data-stu-id="793b3-149">Install Microsoft Teams</span></span> 

### <a name="user-file-and-settings-migration"></a><span data-ttu-id="793b3-150">사용자 파일 및 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="793b3-150">User File and Settings Migration</span></span>

  - <span data-ttu-id="793b3-151">알려진 폴더 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="793b3-151">Known Folder File Migration</span></span> 
  - <span data-ttu-id="793b3-152">사용자 상태 마이그레이션 도구</span><span class="sxs-lookup"><span data-stu-id="793b3-152">User State Migration Tool</span></span> 
  - <span data-ttu-id="793b3-153">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="793b3-153">Enterprise State Roaming</span></span>
  - <span data-ttu-id="793b3-154">시작 메뉴 사용자 정의 및 UWP 앱 제거</span><span class="sxs-lookup"><span data-stu-id="793b3-154">Start Menu Customization and UWP App Removal</span></span> 
  - <span data-ttu-id="793b3-155">사용자 경험 가상화 (UE-V)</span><span class="sxs-lookup"><span data-stu-id="793b3-155">User Experience Virtualization (UE-V)</span></span> 

### <a name="security-and-compliance"></a><span data-ttu-id="793b3-156">보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="793b3-156">Security and Compliance</span></span>

  - <span data-ttu-id="793b3-157">BitLocker 장치 암호화</span><span class="sxs-lookup"><span data-stu-id="793b3-157">BitLocker device encryption</span></span>
  - <span data-ttu-id="793b3-158">Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="793b3-158">Windows Defender Antivirus</span></span>
  - <span data-ttu-id="793b3-159">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="793b3-159">Windows Hello for Business</span></span>
  - <span data-ttu-id="793b3-160">BIOS에서 UEFI로 변환</span><span class="sxs-lookup"><span data-stu-id="793b3-160">BIOS to UEFI Conversion</span></span>
  - <span data-ttu-id="793b3-161">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="793b3-161">Windows Defender Application Guard</span></span>
  - <span data-ttu-id="793b3-162">Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="793b3-162">Windows Defender Exploit Guard</span></span>
  - <span data-ttu-id="793b3-163">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="793b3-163">Windows Defender Application Control</span></span>
  - <span data-ttu-id="793b3-164">Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="793b3-164">Windows Defender Advanced Threat Protection</span></span>
  - <span data-ttu-id="793b3-165">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-165">NEW!</span></span> <span data-ttu-id="793b3-166">끝점 보안</span><span class="sxs-lookup"><span data-stu-id="793b3-166">Endpoint Security</span></span> 

### <a name="os-deployment-and-feature-updates"></a><span data-ttu-id="793b3-167">운영 체제 배포 및 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="793b3-167">OS Deployment and Feature Updates</span></span>

  - <span data-ttu-id="793b3-168">OS 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="793b3-168">OS Image Creation</span></span>
  - <span data-ttu-id="793b3-169">구성 관리자의 OS 배포 작업 순서</span><span class="sxs-lookup"><span data-stu-id="793b3-169">OS Deployment Task Sequences in Configuration Manager</span></span> 
  - <span data-ttu-id="793b3-170">MDT의 OS 배포 작업 순서</span><span class="sxs-lookup"><span data-stu-id="793b3-170">OS Deployment Task Sequences in MDT</span></span>
  - <span data-ttu-id="793b3-171">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="793b3-171">Windows Autopilot</span></span>
  - <span data-ttu-id="793b3-172">패키지 프로비저닝</span><span class="sxs-lookup"><span data-stu-id="793b3-172">Provisioning Packages</span></span> 

### <a name="windows-and-office-as-a-service"></a><span data-ttu-id="793b3-173">Windows 및 Office as a Service</span><span class="sxs-lookup"><span data-stu-id="793b3-173">Windows and Office as a Service</span></span>
  - <span data-ttu-id="793b3-174">그룹 정책을 사용하여 Windows 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="793b3-174">Manage Windows Updates using Group Policy</span></span>
  - <span data-ttu-id="793b3-175">구성 관리자 및 Intune으로 Windows 10 서비스</span><span class="sxs-lookup"><span data-stu-id="793b3-175">Servicing Windows 10 with Configuration Manager and Intune</span></span>
  - <span data-ttu-id="793b3-176">Configuration Manager를 사용하여 엔터프라이즈용 Microsoft 365 앱 제공</span><span class="sxs-lookup"><span data-stu-id="793b3-176">Servicing Microsoft 365 Apps for enterprise with Configuration Manager</span></span>
  - <span data-ttu-id="793b3-177">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-177">NEW!</span></span> <span data-ttu-id="793b3-178">Configuration Manager 및 Intune을 사용하여 Office 업데이트</span><span class="sxs-lookup"><span data-stu-id="793b3-178">Office updates with Configuration Manager and Intune</span></span>
  
### <a name="new-windows-virtual-desktop"></a><span data-ttu-id="793b3-179">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="793b3-179">NEW!</span></span> <span data-ttu-id="793b3-180">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="793b3-180">Windows Virtual Desktop</span></span>
  - <span data-ttu-id="793b3-181">Windows 가상 데스크톱: 준비, 배포, 최적화</span><span class="sxs-lookup"><span data-stu-id="793b3-181">Windows Virtual Desktop: Prepare, Deploy, Optimize</span></span> 

### <a name="download-the-windows-and-office-deployment-lab-kit"></a><span data-ttu-id="793b3-182">Windows 및 Office 배포 랩 키트 다운로드</span><span class="sxs-lookup"><span data-stu-id="793b3-182">Download the Windows and Office Deployment Lab Kit</span></span>

<span data-ttu-id="793b3-183">[Windows 및 Office 배포 랩 키트 다운로드](https://www.microsoft.com/evalcenter/evaluate-lab-kit)</span><span class="sxs-lookup"><span data-stu-id="793b3-183">[Download the Windows and Office Deployment Lab Kit](https://www.microsoft.com/evalcenter/evaluate-lab-kit).</span></span>

<span data-ttu-id="793b3-184">*광대역폭을 통해 이 콘텐츠를 다운로드하여 다운로드 환경을 개선하고 자동 프로비전을 위해 30-45분을 허용하세요. 이 랩 환경에는 최소 16GB의 사용 가능한 메모리와 150GB의 사용 가능한 디스크 공간이 필요합니다. 최적의 성능을 위해 32GB의 사용 가능한 메모리가 있는 것이 좋습니다. 이 랩은 2020년 9월 12일에 만료됩니다. 만료 전에 새 버전이 게시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="793b3-184">*Please use a broad bandwidth to download this content to enhance your downloading experience and allow 30-45 minutes for automatic provisioning. The lab environment requires a minimum of 16 GB of available memory and 150 GB of free disk space. For optimal performance, 32 GB of available memory is recommended. The lab expires September 12, 2020. A new version will be published prior to expiration.*</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="793b3-185">추가 안내</span><span class="sxs-lookup"><span data-stu-id="793b3-185">Additional guidance</span></span>

  - [<span data-ttu-id="793b3-186">데스크톱 배포 센터</span><span class="sxs-lookup"><span data-stu-id="793b3-186">Desktop Deployment Center</span></span>](https://www.aka.ms/howtoshift)

  - [<span data-ttu-id="793b3-187">Microsoft Mechanics의 데스크톱 배포 시리즈 비디오</span><span class="sxs-lookup"><span data-stu-id="793b3-187">Desktop Deployment series videos from Microsoft Mechanics</span></span>](https://www.aka.ms/watchhowtoshift)

  - [<span data-ttu-id="793b3-188">Microsoft Endpoint Configuration Manager OS 배포</span><span class="sxs-lookup"><span data-stu-id="793b3-188">Microsoft Endpoint Configuration Manager OS Deployment</span></span>](https://docs.microsoft.com/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)

  - [<span data-ttu-id="793b3-189"><span class="underline">Windows 10 배포 계획</span></span><span class="sxs-lookup"><span data-stu-id="793b3-189"><span class="underline">Plan for Windows 10 deployment</span></span></span>](https://docs.microsoft.com/windows/deployment/planning/index)

  - [<span data-ttu-id="793b3-190"><span class="underline">Microsoft 365 앱 배포 가이드</span></span><span class="sxs-lookup"><span data-stu-id="793b3-190"><span class="underline">Deployment guide for Microsoft 365 Apps</span></span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

  - [<span data-ttu-id="793b3-191"><span class="underline">Intune 시작</span></span><span class="sxs-lookup"><span data-stu-id="793b3-191"><span class="underline">Getting Started with Intune</span></span></span>](https://docs.microsoft.com/intune/get-started-evaluation)

## <a name="related-resources"></a><span data-ttu-id="793b3-192">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="793b3-192">Related resources</span></span>

  - [<span data-ttu-id="793b3-193"><span class="underline">Microsoft 365 소개</span></span><span class="sxs-lookup"><span data-stu-id="793b3-193"><span class="underline">Introducing Microsoft 365</span></span></span>](https://www.microsoft.com/microsoft-365/default.aspx)

  - [<span data-ttu-id="793b3-194"><span class="underline">Office 365 비즈니스 에디션</span></span><span class="sxs-lookup"><span data-stu-id="793b3-194"><span class="underline">Office 365 for business</span></span></span>](https://products.office.com/business/office)

  - [<span data-ttu-id="793b3-195"><span class="underline">Introducing Enterprise Mobility + Security</span></span><span class="sxs-lookup"><span data-stu-id="793b3-195"><span class="underline">Introducing Enterprise Mobility + Security</span></span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

  - [<span data-ttu-id="793b3-196"><span class="underline">Windows 10 엔터프라이즈 에디션</span></span><span class="sxs-lookup"><span data-stu-id="793b3-196"><span class="underline">Windows 10 for enterprise</span></span></span>](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)

  - [<span data-ttu-id="793b3-197"><span class="underline">Windows 10 중소기업용 에디션</span></span><span class="sxs-lookup"><span data-stu-id="793b3-197"><span class="underline">Windows 10 for small and medium business</span></span></span>](https://www.microsoft.com/WindowsForBusiness/windows-for-small-business)
