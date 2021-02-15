---
title: Contoso의 Windows 10 Enterprise 배포
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 어떻게 Contoso에서 Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 Enterprise의 현재 위치에서 업그레이드를 배포했는지를 이해합니다.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754254"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="bf940-103">Contoso의 Windows 10 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="bf940-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="bf940-p101">엔터프라이즈용 Microsoft 365를 광범위하게 출시하기 전에 Contoso는 Windows 7(10%), Windows 8.1(65%) 및 Windows 10(25%)이 혼합된 Windows 호환 PC 및 장치를 실행했습니다. Contoso는 Windows 10 Enterprise용 PC를 업그레이드하여 고급 보안을 활용하고 자동화된 업데이트 배포에서 IT 오버헤드를 낮추고자 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-p101">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="bf940-106">Contoso는 해당 인프라 및 비즈니스 요구를 파악한 후 다음과 같은 핵심 배포 요구 사항을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="bf940-107">가능한 한 많은 PC 및 장치에서 Windows 10 Enterprise를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="bf940-108">현재 위치 업그레이드의 롤아웃은 기존 Configuration Manager 인프라를 활용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="bf940-109">배포할 Windows 10 Enterprise 버전 및 업데이트에 대한 제어는 링을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="bf940-110">PC 및 장치는 최소한의 IT 관리 비용을 들이고 최종 사용자에게 최소한의 영향을 미치면서 최신 상태로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="bf940-111">최신 버전은 지원되는 Contoso의 비즈니스 요구를 충족하는 지원되는 Windows 10 Enterprise 버전으로 정의되며, 이것은 모든 Windows 호환 PC에서 최신 버전의 Windows 10 Enterprise를 실행하도록 하는 것과는 다른 차원일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="bf940-112">배포 도구</span><span class="sxs-lookup"><span data-stu-id="bf940-112">Deployment tools</span></span>

<span data-ttu-id="bf940-113">Windows 10 Enterprise의 현재 위치 업그레이드 이전 및 도중에 Contoso는 다음 Windows Analytics 솔루션을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="bf940-114">업그레이드 준비</span><span class="sxs-lookup"><span data-stu-id="bf940-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="bf940-115">분석을 위해 시스템, 응용 프로그램 및 드라이버 데이터를 수집한 후 업그레이드를 차단할 수 있는 호환성 문제와 Microsoft에 알려져 있는 문제에 대한 제안된 수정 프로그램을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="bf940-116">준수 업데이트</span><span class="sxs-lookup"><span data-stu-id="bf940-116">Update Compliance</span></span>  

  <span data-ttu-id="bf940-117">Windows 업데이트와 관련된 장치의 상태를 표시 하여 최신 업데이트를 적절하게 유지할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="bf940-118">장치 상태</span><span class="sxs-lookup"><span data-stu-id="bf940-118">Device Health</span></span>  

  <span data-ttu-id="bf940-119">자주 충돌이 발생하여 다시 제조하거나 대체할 필요가 있는 장치 및 장치의 충돌을 발생시키는 장치 드라이버와 충돌 횟수를 줄일 수 있는 이들 드라이버의 대체 버전에 대한 제안과 함께 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="bf940-120">최종 사용자에게 프롬프트를 보내는 Windows Information Protection의 잘못된 구성에 대해 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="bf940-p103">Contoso는 기존의 Configuration Manager(현재 분기) 인프라가 있습니다. Configuration Manager는 대규모 환경에 맞게 확장되며, 설치, 업데이트 및 설정을 포괄적으로 제어할 수 있도록 합니다. 그뿐 아니라 Windows 10 Enterprise를 보다 쉽고 효율적으로 배포 및 관리할 수 있도록 하는 기본 제공 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="bf940-124">계획 프로세스</span><span class="sxs-lookup"><span data-stu-id="bf940-124">Planning process</span></span>

<span data-ttu-id="bf940-125">Contoso는 Windows Analytics의 업그레이드 준비를 사용하여 설치된 앱 집합과 Windows 10 Enterprise와의 호환성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="bf940-126">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="bf940-126">Deployment process</span></span>

<span data-ttu-id="bf940-127">Windows 10 Enterprise의 현재 위치 업그레이드 배포를 완료하기 위해 Contoso는 Microsoft의 모범 사례 권장 사항을 포함하는 다음 프로세스를 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="bf940-128">Configuration Manager에 대한 피어 캐시를 사용하도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="bf940-129">볼륨 라이선스 서비스 센터의 이미지를 기준으로 사용자 지정된 Windows 패키지를 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="bf940-130">Configuration Manager를 사용하여 네트워크의 배포 지점에 Windows 패키지를 배포하고 세 가지 유효성 검사 및 배포 준비 그룹에 빌드를 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="bf940-131">Windows Analytics의 장치 상태 및 업데이트 준수 솔루션을 사용하여 3개의 유효성 검사 및 배포 준비 링의 PC 및 장치에 대한 배포 성공 여부를 평가했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="bf940-132">Windows Analytics 정보에 따라 Contoso는 광범위한 배포 그룹에 배포할 Windows 10 Enterprise 버전을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="bf940-133">Configuration Manager 배포 작업 순서를 실행하여 선택된 Windows 패키지를 광범위한 배포 그룹에 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="bf940-134">장치 상태 및 업데이트 준수 솔루션을 사용하여 광범위한 배포 그룹의 PC 및 장치를 모니터링하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="bf940-135">Contoso의 현재 위치 업그레이드 및 지속적인 업데이트 배포 아키텍처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contoso의 Windows 10 Enterprise 배포 인프라](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="bf940-137">이 인프라는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="bf940-138">다음과 같은 Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="bf940-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="bf940-139">Microsoft Network의 Microsoft 볼륨 라이선스 센터에서 Windows 10 Enterprise 패키지에 대한 이미지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="bf940-140">배포 패키지에 대한 중앙 관리 지점</span><span class="sxs-lookup"><span data-stu-id="bf940-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="bf940-141">일반적으로 Contoso의 지역 허브 사무실에 있는 지역별 배포 지점</span><span class="sxs-lookup"><span data-stu-id="bf940-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="bf940-142">그룹 구성원 자격에 따라 현재 위치 업그레이드 또는 지속적인 업데이트에 대한 배포 패키지를 받아 설치하는 다양한 위치의 Windows PC 및 장치</span><span class="sxs-lookup"><span data-stu-id="bf940-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="bf940-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf940-143">Next step</span></span>

<span data-ttu-id="bf940-144">Contoso가 Configuration Manager 인프라를 활용하여 조직 전체에 최신 [엔터프라이즈용 Microsoft 365](contoso-o365pp.md) 앱을 배포하고 유지하는 방법을 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="bf940-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="bf940-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf940-145">See also</span></span>

[<span data-ttu-id="bf940-146">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bf940-146">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="bf940-147">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="bf940-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="bf940-148">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="bf940-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
