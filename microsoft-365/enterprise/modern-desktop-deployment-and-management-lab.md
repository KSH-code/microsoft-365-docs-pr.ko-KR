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
ms.openlocfilehash: 48d8cf5bc618f4f1e840872c4369bc5cdda19727
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262560"
---
# <a name="windows-and-office-deployment-lab-kit"></a><span data-ttu-id="9db79-103">Windows 및 Office 배포 랩 키트</span><span class="sxs-lookup"><span data-stu-id="9db79-103">Windows and Office Deployment Lab Kit</span></span>

<span data-ttu-id="9db79-104">이 랩은 Windows 10 Enterprise 및 엔터프라이즈용 Microsoft 365 앱을 실행하는 데스크톱의 배포 및 관리를 계획, 테스트 및 검증하는 데 도움을 주기 위해 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-104">These labs are designed to help you plan, test and validate your deployment and management of desktops running Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="9db79-105">이 랩에서는 Microsoft Endpoint Configuration Manager, Desktop Analytics, Office 사용자 지정 도구, OneDrive, Windows Autopilot 등의 데스크톱 배포 도구에 설명된 단계와 도구를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-105">The labs cover the steps and tools outlined in the Desktop Deployment wheel, spanning Microsoft Endpoint Configuration Manager, Desktop Analytics, Office Customization Tool, OneDrive, Windows Autopilot and more.</span></span>

<span data-ttu-id="9db79-106">이 교육은 Windows 7 사용 종료를 준비하는 조직에 권장되며 현재 Windows 10 및 Office 365 Plus 또는 Office 2019를 사용 중인 경우에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-106">This training is highly recommended for organizations preparing for Windows 7 end of life, and also applies if you're currently using Windows 10 and Office 365 Plus or Office 2019.</span></span> <span data-ttu-id="9db79-107">또한 격리된 환경으로서 랩은 배포 도구 업데이트를 탐색하고 배포 관련 자동화를 테스트하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-107">Additionally, as an isolated environment, the lab is ideal for exploring deployment tool updates and testing your deployment-related automation.</span></span>

<span data-ttu-id="9db79-108">[Windows 및 Office 배포 랩 키트 다운로드](https://www.microsoft.com/evalcenter/evaluate-lab-kit)</span><span class="sxs-lookup"><span data-stu-id="9db79-108">[Download the Windows and Office Deployment Lab Kit](https://www.microsoft.com/evalcenter/evaluate-lab-kit).</span></span>

## <a name="a-complete-lab-environment"></a><span data-ttu-id="9db79-109">전체 랩 환경</span><span class="sxs-lookup"><span data-stu-id="9db79-109">A complete lab environment</span></span>

<span data-ttu-id="9db79-110">랩은 도메인 가입 데스크톱 클라이언트, 도메인 컨트롤러, 인터넷 게이트웨이 및 완전히 구성된 구성 매니저 인스턴스를 포함하여 자동으로 프로비저닝된 가상 랩 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-110">The lab provides you with an automatically provisioned virtual lab environment, including domain-joined desktop clients, domain controller, Internet gateway and a fully configured Configuration Manager instance.</span></span> <span data-ttu-id="9db79-111">랩에는 다음 제품의 최신 평가판 버전이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-111">The lab contains the latest Evaluation Versions of the following products:</span></span>

  - <span data-ttu-id="9db79-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9db79-112">Windows 10 Enterprise</span></span>
  - <span data-ttu-id="9db79-113">Windows 7 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9db79-113">Windows 7 Enterprise</span></span>
  - <span data-ttu-id="9db79-114">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9db79-114">Microsoft Endpoint Configuration Manager</span></span>
  - <span data-ttu-id="9db79-115">Windows 10용 Windows 평가 및 배포 키트</span><span class="sxs-lookup"><span data-stu-id="9db79-115">Windows Assessment and Deployment Kit for Windows 10</span></span>
  - <span data-ttu-id="9db79-116">Microsoft Deployment Toolkit</span><span class="sxs-lookup"><span data-stu-id="9db79-116">Microsoft Deployment Toolkit</span></span>
  - <span data-ttu-id="9db79-117">Microsoft Application Virtualization(App-V)</span><span class="sxs-lookup"><span data-stu-id="9db79-117">Microsoft Application Virtualization (App-V)</span></span>
  - <span data-ttu-id="9db79-118">Microsoft BitLocker 관리 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="9db79-118">Microsoft BitLocker Administration and Monitoring</span></span> 
  - <span data-ttu-id="9db79-119">Windows Server</span><span class="sxs-lookup"><span data-stu-id="9db79-119">Windows Server</span></span> 
  - <span data-ttu-id="9db79-120">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9db79-120">Microsoft SQL Server</span></span> 

<span data-ttu-id="9db79-121">또한, 랩은 다음에 대한 평가판에 연결되도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-121">PLUS, the lab is designed to be connected to trials for:</span></span> 

  - <span data-ttu-id="9db79-122">Microsoft 365 E5 또는</span><span class="sxs-lookup"><span data-stu-id="9db79-122">Microsoft 365 E5, or</span></span>
  - <span data-ttu-id="9db79-123">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="9db79-123">Office 365 Enterprise E5</span></span>
  - <span data-ttu-id="9db79-124">Enterprise Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="9db79-124">Enterprise Mobility + Security</span></span>

## <a name="step-by-step-labs"></a><span data-ttu-id="9db79-125">단계별 랩</span><span class="sxs-lookup"><span data-stu-id="9db79-125">Step-by-step labs</span></span>

<span data-ttu-id="9db79-126">자세한 랩 가이드는 여러 배포 및 관리 시나리오를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-126">Detailed lab guides take you through multiple deployment and management scenarios.</span></span> <span data-ttu-id="9db79-127">최신 버전의 Intune 및 Configuration Manager(버전 1910)에 대한 labs가 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9db79-127">The labs have been updated for the latest versions of Intune and Configuration Manager (Version 1910).</span></span> 

### <a name="device-and-app-readiness"></a><span data-ttu-id="9db79-128">장치 및 앱 준비</span><span class="sxs-lookup"><span data-stu-id="9db79-128">Device and App Readiness</span></span>

  - <span data-ttu-id="9db79-129">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="9db79-129">Desktop Analytics</span></span>
  - <span data-ttu-id="9db79-130">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="9db79-130">NEW!</span></span> <span data-ttu-id="9db79-131">새 Microsoft Edge 배포 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="9db79-131">Deploy and update the new Microsoft Edge</span></span> 
  - <span data-ttu-id="9db79-132">Internet Explorer 모드</span><span class="sxs-lookup"><span data-stu-id="9db79-132">Internet Explorer Mode</span></span> 
  - <span data-ttu-id="9db79-133">Application Guard</span><span class="sxs-lookup"><span data-stu-id="9db79-133">Application Guard</span></span> 

### <a name="directory-and-network-readiness"></a><span data-ttu-id="9db79-134">디렉터리 및 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="9db79-134">Directory and Network Readiness</span></span>

  - <span data-ttu-id="9db79-135">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="9db79-135">NEW!</span></span> <span data-ttu-id="9db79-136">Windows 10 업데이트 제공 최적화</span><span class="sxs-lookup"><span data-stu-id="9db79-136">Optimize Windows 10 Update Delivery</span></span> 
  - <span data-ttu-id="9db79-137">구성 관리자 및 Microsoft Intune 공동 관리</span><span class="sxs-lookup"><span data-stu-id="9db79-137">Configuration Manager and Microsoft Intune Co-Management</span></span>
  - <span data-ttu-id="9db79-138">원격 액세스(VPN)</span><span class="sxs-lookup"><span data-stu-id="9db79-138">Remote Access (VPN)</span></span>

### <a name="office-and-lob-app-delivery"></a><span data-ttu-id="9db79-139">Office 및 LOB 앱 제공</span><span class="sxs-lookup"><span data-stu-id="9db79-139">Office and LOB App Delivery</span></span>

  - <span data-ttu-id="9db79-140">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="9db79-140">Microsoft 365 Apps for enterprise</span></span>
  - <span data-ttu-id="9db79-141">구성 관리자 및 Microsoft Intune을 사용한 엔터프라이즈 관리 배포</span><span class="sxs-lookup"><span data-stu-id="9db79-141">Enterprise Managed Deployment using Configuration Manager and Microsoft Intune</span></span>
  - <span data-ttu-id="9db79-142">Microsoft Intune을 사용하여 응용 프로그램 배포 및 관리</span><span class="sxs-lookup"><span data-stu-id="9db79-142">Application deployment and management using Microsoft Intune</span></span>
  - <span data-ttu-id="9db79-143">비즈니스용 Microsoft Store를 사용하여 앱 배포 및 셀프 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="9db79-143">App deployment and self-service installation using Microsoft Store for Business</span></span>

### <a name="user-file-and-settings-migration"></a><span data-ttu-id="9db79-144">사용자 파일 및 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9db79-144">User File and Settings Migration</span></span>

  - <span data-ttu-id="9db79-145">알려진 폴더 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9db79-145">Known Folder File Migration</span></span> 
  - <span data-ttu-id="9db79-146">사용자 상태 마이그레이션 도구</span><span class="sxs-lookup"><span data-stu-id="9db79-146">User State Migration Tool</span></span> 
  - <span data-ttu-id="9db79-147">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="9db79-147">Enterprise State Roaming</span></span>
  - <span data-ttu-id="9db79-148">시작 메뉴 사용자 정의 및 UWP 앱 제거</span><span class="sxs-lookup"><span data-stu-id="9db79-148">Start Menu Customization and UWP App Removal</span></span> 
  - <span data-ttu-id="9db79-149">사용자 경험 가상화 (UE-V)</span><span class="sxs-lookup"><span data-stu-id="9db79-149">User Experience Virtualization (UE-V)</span></span> 

### <a name="security-and-compliance"></a><span data-ttu-id="9db79-150">보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="9db79-150">Security and Compliance</span></span>

  - <span data-ttu-id="9db79-151">BitLocker 장치 암호화</span><span class="sxs-lookup"><span data-stu-id="9db79-151">BitLocker device encryption</span></span>
  - <span data-ttu-id="9db79-152">Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9db79-152">Windows Defender Antivirus</span></span>
  - <span data-ttu-id="9db79-153">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="9db79-153">Windows Hello for Business</span></span>
  - <span data-ttu-id="9db79-154">BIOS에서 UEFI로 변환</span><span class="sxs-lookup"><span data-stu-id="9db79-154">BIOS to UEFI Conversion</span></span>
  - <span data-ttu-id="9db79-155">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="9db79-155">Windows Defender Application Guard</span></span>
  - <span data-ttu-id="9db79-156">Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="9db79-156">Windows Defender Exploit Guard</span></span>
  - <span data-ttu-id="9db79-157">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="9db79-157">Windows Defender Application Control</span></span>
  - <span data-ttu-id="9db79-158">Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9db79-158">Windows Defender Advanced Threat Protection</span></span>

### <a name="os-deployment-and-feature-updates"></a><span data-ttu-id="9db79-159">운영 체제 배포 및 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="9db79-159">OS Deployment and Feature Updates</span></span>

  - <span data-ttu-id="9db79-160">OS 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="9db79-160">OS Image Creation</span></span>
  - <span data-ttu-id="9db79-161">구성 관리자의 OS 배포 작업 순서</span><span class="sxs-lookup"><span data-stu-id="9db79-161">OS Deployment Task Sequences in Configuration Manager</span></span> 
  - <span data-ttu-id="9db79-162">MDT의 OS 배포 작업 순서</span><span class="sxs-lookup"><span data-stu-id="9db79-162">OS Deployment Task Sequences in MDT</span></span>
  - <span data-ttu-id="9db79-163">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="9db79-163">Windows Autopilot</span></span>
  - <span data-ttu-id="9db79-164">패키지 프로비저닝</span><span class="sxs-lookup"><span data-stu-id="9db79-164">Provisioning Packages</span></span> 

### <a name="windows-and-office-as-a-service"></a><span data-ttu-id="9db79-165">Windows 및 Office as a Service</span><span class="sxs-lookup"><span data-stu-id="9db79-165">Windows and Office as a Service</span></span>
  - <span data-ttu-id="9db79-166">그룹 정책을 사용하여 Windows 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="9db79-166">Manage Windows Updates using Group Policy</span></span>
  - <span data-ttu-id="9db79-167">구성 관리자 및 Intune으로 Windows 10 서비스</span><span class="sxs-lookup"><span data-stu-id="9db79-167">Servicing Windows 10 with Configuration Manager and Intune</span></span>
  - <span data-ttu-id="9db79-168">Configuration Manager를 사용하여 엔터프라이즈용 Microsoft 365 앱 제공</span><span class="sxs-lookup"><span data-stu-id="9db79-168">Servicing Microsoft 365 Apps for enterprise with Configuration Manager</span></span>

### <a name="new-windows-virtual-desktop"></a><span data-ttu-id="9db79-169">새로운 기능!</span><span class="sxs-lookup"><span data-stu-id="9db79-169">NEW!</span></span> <span data-ttu-id="9db79-170">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="9db79-170">Windows Virtual Desktop</span></span>
  - <span data-ttu-id="9db79-171">Windows 가상 데스크톱: 준비, 배포, 최적화</span><span class="sxs-lookup"><span data-stu-id="9db79-171">Windows Virtual Desktop: Prepare, Deploy, Optimize</span></span> 

### <a name="download-the-windows-and-office-deployment-lab-kit"></a><span data-ttu-id="9db79-172">Windows 및 Office 배포 랩 키트 다운로드</span><span class="sxs-lookup"><span data-stu-id="9db79-172">Download the Windows and Office Deployment Lab Kit</span></span>

<span data-ttu-id="9db79-173">[Windows 및 Office 배포 랩 키트 다운로드](https://www.microsoft.com/evalcenter/evaluate-lab-kit)</span><span class="sxs-lookup"><span data-stu-id="9db79-173">[Download the Windows and Office Deployment Lab Kit](https://www.microsoft.com/evalcenter/evaluate-lab-kit).</span></span>

<span data-ttu-id="9db79-174">*광대역폭을 통해 이 콘텐츠를 다운로드하여 다운로드 환경을 개선하고 자동 프로비전을 위해 30-45분을 허용하세요. 이 랩 환경에는 최소 16GB의 사용 가능한 메모리와 150GB의 사용 가능한 디스크 공간이 필요합니다. 최적의 성능을 위해 32GB의 사용 가능한 공간이 있는 것이 좋습니다. 이 랩은 2020년 7월 5일에 만료됩니다. 만료 전에 새 버전이 게시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="9db79-174">*Please use a broad bandwidth to download this content to enhance your downloading experience and allow 30-45 minutes for automatic provisioning. The lab environment requires a minimum of 16 GB of available memory and 150 GB of free disk space. For optimal performance, 32 GB of available memory is recommended. The lab expires July 5, 2020. A new version will be published prior to expiration.*</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="9db79-175">추가 안내</span><span class="sxs-lookup"><span data-stu-id="9db79-175">Additional guidance</span></span>

  - [<span data-ttu-id="9db79-176">데스크톱 배포 센터</span><span class="sxs-lookup"><span data-stu-id="9db79-176">Desktop Deployment Center</span></span>](https://www.aka.ms/howtoshift)

  - [<span data-ttu-id="9db79-177">Microsoft Mechanics의 데스크톱 배포 시리즈 비디오</span><span class="sxs-lookup"><span data-stu-id="9db79-177">Desktop Deployment series videos from Microsoft Mechanics</span></span>](https://www.aka.ms/watchhowtoshift)

  - [<span data-ttu-id="9db79-178">Microsoft Endpoint Configuration Manager OS 배포</span><span class="sxs-lookup"><span data-stu-id="9db79-178">Microsoft Endpoint Configuration Manager OS Deployment</span></span>](https://docs.microsoft.com/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)

  - [<span data-ttu-id="9db79-179"><span class="underline">Windows 10 배포 계획</span></span><span class="sxs-lookup"><span data-stu-id="9db79-179"><span class="underline">Plan for Windows 10 deployment</span></span></span>](https://docs.microsoft.com/windows/deployment/planning/index)

  - [<span data-ttu-id="9db79-180"><span class="underline">Microsoft 365 앱 배포 가이드</span></span><span class="sxs-lookup"><span data-stu-id="9db79-180"><span class="underline">Deployment guide for Microsoft 365 Apps</span></span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

  - [<span data-ttu-id="9db79-181"><span class="underline">Intune 시작</span></span><span class="sxs-lookup"><span data-stu-id="9db79-181"><span class="underline">Getting Started with Intune</span></span></span>](https://docs.microsoft.com/intune/get-started-evaluation)

## <a name="related-resources"></a><span data-ttu-id="9db79-182">관련 리소스</span><span class="sxs-lookup"><span data-stu-id="9db79-182">Related resources</span></span>

  - [<span data-ttu-id="9db79-183"><span class="underline">Microsoft 365 소개</span></span><span class="sxs-lookup"><span data-stu-id="9db79-183"><span class="underline">Introducing Microsoft 365</span></span></span>](https://www.microsoft.com/microsoft-365/default.aspx)

  - [<span data-ttu-id="9db79-184"><span class="underline">Office 365 비즈니스 에디션</span></span><span class="sxs-lookup"><span data-stu-id="9db79-184"><span class="underline">Office 365 for business</span></span></span>](https://products.office.com/business/office)

  - [<span data-ttu-id="9db79-185"><span class="underline">Introducing Enterprise Mobility + Security</span></span><span class="sxs-lookup"><span data-stu-id="9db79-185"><span class="underline">Introducing Enterprise Mobility + Security</span></span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

  - [<span data-ttu-id="9db79-186"><span class="underline">Windows 10 엔터프라이즈 에디션</span></span><span class="sxs-lookup"><span data-stu-id="9db79-186"><span class="underline">Windows 10 for enterprise</span></span></span>](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)

  - [<span data-ttu-id="9db79-187"><span class="underline">Windows 10 중소기업용 에디션</span></span><span class="sxs-lookup"><span data-stu-id="9db79-187"><span class="underline">Windows 10 for small and medium business</span></span></span>](https://www.microsoft.com/WindowsForBusiness/windows-for-small-business)
