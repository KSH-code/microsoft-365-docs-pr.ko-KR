---
title: Endpoint용 Microsoft Defender 파일럿, 파일럿 설정, 평가 시 기능 테스트
description: 파일럿 그룹 확인 및 기능 시도를 포함하여 MDE(Microsoft Defender for Endpoint)에 대한 파일럿을 실행하는 방법을 배워야 합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458005"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a><span data-ttu-id="ecea1-103">Endpoint용 파일럿 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ecea1-103">Pilot Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="ecea1-104">이 문서에서는 끝점용 Microsoft Defender에 대한 파일럿을 실행하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-104">This article will guide you in the process of running a pilot for Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="ecea1-105">다음 단계에 따라 끝점용 Microsoft Defender의 파일럿을 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-105">Use the following steps to setup and configure the pilot for Microsoft Defender for Endpoint.</span></span> 

![Defender 평가 환경에 Id용 Microsoft Defender를 추가하는 단계](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- <span data-ttu-id="ecea1-107">1단계.</span><span class="sxs-lookup"><span data-stu-id="ecea1-107">Step 1.</span></span> <span data-ttu-id="ecea1-108">파일럿 그룹 확인</span><span class="sxs-lookup"><span data-stu-id="ecea1-108">Verify pilot group</span></span>
- <span data-ttu-id="ecea1-109">2단계.</span><span class="sxs-lookup"><span data-stu-id="ecea1-109">Step 2.</span></span> <span data-ttu-id="ecea1-110">기능 사용</span><span class="sxs-lookup"><span data-stu-id="ecea1-110">Try out capabilities</span></span>

<span data-ttu-id="ecea1-111">끝점용 Microsoft Defender를 파일럿할 때 전체 조직을 온보딩하기 전에 몇 대의 장치를 서비스에 온보딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-111">When you pilot Microsoft Defender for Endpoint, you may choose to onboard a few devices to the service before onboarding your entire organization.</span></span>  

<span data-ttu-id="ecea1-112">그런 다음 공격 시뮬레이션을 실행하고 Endpoint용 Defender가 악의적인 활동을 표시하고 효율적인 대응을 하는 방법을 보는 등 사용 가능한 기능을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-112">You can then try out capabilities that are available such as running attack simulations and seeing how Defender for Endpoint surfaces malicious activities and enables you to conduct an efficient response.</span></span> 

## <a name="step-1-verify-pilot-group"></a><span data-ttu-id="ecea1-113">1단계.</span><span class="sxs-lookup"><span data-stu-id="ecea1-113">Step 1.</span></span> <span data-ttu-id="ecea1-114">파일럿 그룹 확인</span><span class="sxs-lookup"><span data-stu-id="ecea1-114">Verify pilot group</span></span>
<span data-ttu-id="ecea1-115">평가 사용 섹션에 설명된 온보더링 단계를 완료한 후 약 1시간 후에 장치 인벤토리 목록에 장치가 표시됩니다. [](eval-defender-endpoint-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="ecea1-115">After completing the onboarding steps outlined in the [Enable evaluation](eval-defender-endpoint-enable-eval.md) section, you should see the devices in the Device inventory list approximately after an hour.</span></span> 

<span data-ttu-id="ecea1-116">온보드 디바이스가 표시될 때 기능 시도를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-116">When you see your onboarded devices you can then proceed with trying out capabilities.</span></span> 

## <a name="step-2-try-out-capabilities"></a><span data-ttu-id="ecea1-117">2단계.</span><span class="sxs-lookup"><span data-stu-id="ecea1-117">Step 2.</span></span> <span data-ttu-id="ecea1-118">기능 사용</span><span class="sxs-lookup"><span data-stu-id="ecea1-118">Try out capabilities</span></span>
<span data-ttu-id="ecea1-119">이제 일부 디바이스의 온보드를 완료하고 서비스에 보고하고 있는 것을 확인한 후 바로 사용할 수 있는 강력한 기능을 사용해 보아 제품에 대해 잘 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-119">Now that you've completed onboarding some devices and verified that they are reporting to the service, familiarize yourself with the product by trying out the powerful capabilities that are available right out of the box.</span></span>

<span data-ttu-id="ecea1-120">파일럿 중에 복잡한 구성 단계를 거치지 않고도 일부 기능을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-120">During the pilot, you can easily get started with trying out some of the features to see the product in action without going through complex configuration steps.</span></span>

<span data-ttu-id="ecea1-121">먼저 대시보드를 체크 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-121">Let's start by checking out the dashboards.</span></span>

### <a name="view-the-device-inventory"></a><span data-ttu-id="ecea1-122">장치 인벤토리 보기</span><span class="sxs-lookup"><span data-stu-id="ecea1-122">View the device inventory</span></span>
<span data-ttu-id="ecea1-123">디바이스 인벤토리는 네트워크에서 끝점, 네트워크 장치 및 IoT 장치 목록을 볼 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-123">The device inventory is where you'll see the list of endpoints, network devices, and IoT devices in your network.</span></span> <span data-ttu-id="ecea1-124">네트워크의 디바이스 보기를 제공할 뿐만 아니라 도메인, 위험 수준, OS 플랫폼 및 기타 세부 정보와 같이 가장 위험에 노출된 장치를 쉽게 식별할 수 있는 자세한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-124">Not only does it provide you with a view of the devices in your network, but it also gives your in-depth information about them such as  domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="ecea1-125">위협 및 취약성 관리 보기</span><span class="sxs-lookup"><span data-stu-id="ecea1-125">View the Threat and vulnerability management dashboard</span></span> 
<span data-ttu-id="ecea1-126">위협 및 취약성 관리 조직에 가장 긴급하고 가장 높은 위험을 내포하는 약점에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-126">Threat and vulnerability management helps you focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="ecea1-127">대시보드에서 조직 노출 점수, 장치에 대한 Microsoft 보안 점수, 장치 노출 분포, 최상위 보안 권장 사항, 주요 취약한 소프트웨어, 최상위 수정 활동 및 노출된 상위 장치 데이터에 대한 높은 수준의 보기를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-127">From the dashboard, get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span> 

### <a name="run-a-simulation"></a><span data-ttu-id="ecea1-128">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="ecea1-128">Run a simulation</span></span>
<span data-ttu-id="ecea1-129">끝점용 Microsoft Defender는 파일럿 장치에서 실행할 수 있는 ["직접 실행"](https://securitycenter.windows.com/tutorials) 공격 시나리오와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-129">Microsoft Defender for Endpoint comes with ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials) that you can run on your pilot devices.</span></span>  <span data-ttu-id="ecea1-130">각 문서에는 OS 및 응용 프로그램 요구 사항과 공격 시나리오와 관련한 자세한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-130">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span> <span data-ttu-id="ecea1-131">이러한 스크립트는 안전하고 문서화되어 있으며 사용하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-131">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="ecea1-132">이러한 시나리오는 끝점 기능에 대한 Defender를 반영하고 조사 환경을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-132">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

<span data-ttu-id="ecea1-133">제공된 시뮬레이션을 실행하려면 하나 이상의 온보드 [디바이스가 필요합니다.](../defender-endpoint/onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="ecea1-133">To run any of the provided simulations, you need at least [one onboarded device](../defender-endpoint/onboard-configure.md).</span></span>

1. <span data-ttu-id="ecea1-134">도움말 **시뮬레이션**& 자습서 에서 시뮬레이션할 사용 가능한 공격 시나리오를  >  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-134">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="ecea1-135">**시나리오 1: 문서 드롭 백도어** - 사회적으로 엔지니어링된 Lure 문서의 배달을 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-135">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="ecea1-136">이 문서는 공격자가 제어할 수 있는 특수하게 만들어진 백도어를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-136">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="ecea1-137">**시나리오 2: 파일** 없는 공격의 PowerShell 스크립트 - PowerShell을 사용하여 공격 표면 감소 및 악의적인 메모리 활동의 장치 학습 감지를 표시하는 파일 없는 공격을 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-137">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="ecea1-138">**시나리오 3: 자동화된** 인시던트 대응 - 인시던트 대응 용량을 확장하기 위해 위반 아티팩트를 자동으로 헌팅하고 수정하는 자동화된 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-138">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="ecea1-139">선택한 시나리오와 함께 제공된 해당 Walkthrough 문서를 다운로드하고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-139">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="ecea1-140">시뮬레이션 파일을 다운로드하거나 자습서 에서 도움말   >  **시뮬레이션으로 & 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="ecea1-140">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="ecea1-141">테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-141">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="ecea1-142">테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다. 이 문서의 지시에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-142">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="ecea1-143">시뮬레이션 파일 또는 스크립트는 공격 활동을 모방하지만 실제로는 양호하며 테스트 장치를 손상하거나 손상하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecea1-143">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ecea1-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ecea1-144">Next steps</span></span>
[<span data-ttu-id="ecea1-145">평가 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ecea1-145">Evaluate Microsoft Cloud App Security</span></span>](eval-defender-mcas-overview.md)

<span data-ttu-id="ecea1-146">[끝점용 Microsoft Defender 평가 개요로 돌아가기](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ecea1-146">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="ecea1-147">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ecea1-147">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>