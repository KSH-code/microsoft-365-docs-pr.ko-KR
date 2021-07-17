---
title: 시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender(MDE) 경험
description: 테스트 Microsoft 365 Defender 테스트 또는 파일럿 환경을 파일럿합니다.
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender Microsoft 365 Defender 평가 랩, Microsoft 365 Defender 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458145"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="c91a9-104">시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender(MDE) 경험</span><span class="sxs-lookup"><span data-stu-id="c91a9-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="c91a9-105">끝점용 Microsoft Defender의 최신 향상된 기능: [엔드포인트용 Defender의](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)새로운 기능.</span><span class="sxs-lookup"><span data-stu-id="c91a9-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="c91a9-106">Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="c91a9-107">읽기: [Insights MITRE ATT&평가에서 읽어 들이기](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="c91a9-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="c91a9-108">서비스에 여러 장치를 온보딩하기 전에 Endpoint용 Defender를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="c91a9-109">이를 위해 몇 가지 테스트 장치에서 제어된 공격 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="c91a9-110">시뮬레이션된 공격을 실행한 후 Endpoint용 Defender가 악의적인 활동을 어떻게 표면화하는지 검토하고 이를 통해 효율적인 대응을 가능하게 하는 방법을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c91a9-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="c91a9-111">Before you begin</span></span>

<span data-ttu-id="c91a9-112">제공된 시뮬레이션을 실행하려면 하나 이상의 온보드 [디바이스가 필요합니다.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="c91a9-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="c91a9-113">각 공격 시나리오와 함께 제공되는 walkthrough 문서를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="c91a9-114">각 문서에는 OS 및 응용 프로그램 요구 사항과 공격 시나리오와 관련한 자세한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="c91a9-115">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="c91a9-115">Run a simulation</span></span>

1. <span data-ttu-id="c91a9-116">도움말 **시뮬레이션**& 자습서 에서 시뮬레이션할 사용 가능한 공격 시나리오를  >  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="c91a9-117">**시나리오 1: 문서 드롭 백도어** - 사회적으로 엔지니어링된 Lure 문서의 배달을 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="c91a9-118">이 문서는 공격자가 제어할 수 있는 특수하게 만들어진 백도어를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="c91a9-119">**시나리오 2: 파일** 없는 공격의 PowerShell 스크립트 - PowerShell을 사용하여 공격 표면 감소 및 악의적인 메모리 활동의 장치 학습 감지를 표시하는 파일 없는 공격을 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="c91a9-120">**시나리오 3: 자동화된** 인시던트 대응 - 인시던트 대응 용량을 확장하기 위해 위반 아티팩트를 자동으로 헌팅하고 수정하는 자동화된 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="c91a9-121">선택한 시나리오와 함께 제공된 해당 Walkthrough 문서를 다운로드하고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="c91a9-122">시뮬레이션 파일을 다운로드하거나 자습서 에서 도움말   >  **시뮬레이션으로 & 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="c91a9-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="c91a9-123">테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="c91a9-124">테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다. 이 문서의 지시에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="c91a9-125">시뮬레이션 파일 또는 스크립트는 공격 활동을 모방하지만 실제로는 양호하며 테스트 장치를 손상하거나 손상하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="c91a9-126">대체 항목 텍스트</span><span class="sxs-lookup"><span data-stu-id="c91a9-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="c91a9-127">공격 시나리오 시뮬레이트</span><span class="sxs-lookup"><span data-stu-id="c91a9-127">Simulate attack scenarios</span></span>

<span data-ttu-id="c91a9-128">테스트 장치를 사용하여 연결하여 자체 공격 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="c91a9-129">다음을 사용하여 공격 시나리오를 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="c91a9-130">["직접" 공격 시나리오](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="c91a9-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="c91a9-131">위협 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="c91a9-131">Threat simulators</span></span>

<span data-ttu-id="c91a9-132">고급 [헌팅을](advanced-hunting-overview.md) 사용하여 데이터 및 [위협](threat-analytics.md) 분석을 쿼리하여 새로운 위협에 대한 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="c91a9-133">직접 공격 시나리오</span><span class="sxs-lookup"><span data-stu-id="c91a9-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="c91a9-134">미리 만든 시뮬레이션을 찾고 있는 경우 ["직접 실행"](https://securitycenter.windows.com/tutorials)공격 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="c91a9-135">이러한 스크립트는 안전하고 문서화되어 있으며 사용하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="c91a9-136">이러한 시나리오는 끝점 기능에 대한 Defender를 반영하고 조사 환경을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="c91a9-137">테스트 장치에 대한 연결은 RDP를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="c91a9-138">방화벽 설정에서 RDP 연결을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="c91a9-139">커넥트 를 선택하여 장치에 연결하고 를 선택하여 **공격 시뮬레이션을 커넥트.**</span><span class="sxs-lookup"><span data-stu-id="c91a9-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![테스트 장치에 대한 연결 단추의 이미지](images/test-machine-table.png)

2. <span data-ttu-id="c91a9-141">RDP 파일을 저장하고 를 선택하여 **커넥트.**</span><span class="sxs-lookup"><span data-stu-id="c91a9-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![원격 데스크톱 연결의 이미지](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="c91a9-143">초기 설정 중에 암호 복사본을 저장하지 않은 경우 메뉴에서 암호 다시  설정을 선택하여 암호를 다시 설정할 수 있습니다. 암호 재설정 ![ 이미지](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="c91a9-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="c91a9-144">디바이스의 상태가 "암호 재설정 실행"으로 변경되면 몇 분 후에 새 암호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="c91a9-145">디바이스를 만들 때 표시된 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-145">Enter the password that was displayed during the device creation step.</span></span>

   ![자격 증명을 입력할 창의 이미지](images/enter-password.png)

4. <span data-ttu-id="c91a9-147">장치에서 Do-it-yourself 공격 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="c91a9-148">위협 시뮬레이터 시나리오</span><span class="sxs-lookup"><span data-stu-id="c91a9-148">Threat simulator scenarios</span></span>

<span data-ttu-id="c91a9-149">랩 설정 중에 지원되는 위협 시뮬레이터를 설치하도록 선택한 경우 평가 랩 디바이스에서 기본 제공 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="c91a9-150">타사 플랫폼을 사용하여 위협 시뮬레이션을 실행하는 것은 테스트 환경의 범위 내에서 끝점 기능에 대한 Microsoft Defender를 평가하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="c91a9-151">시뮬레이션을 실행하기 전에 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="c91a9-152">디바이스를 평가 랩에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="c91a9-153">위협 시뮬레이터를 평가 랩에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="c91a9-154">포털에서 시뮬레이션 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c91a9-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="c91a9-155">위협 시뮬레이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-155">Select a threat simulator.</span></span>

    ![위협 시뮬레이터 선택 이미지](images/select-simulator.png)

3. <span data-ttu-id="c91a9-157">시뮬레이션을 선택하거나 시뮬레이션 갤러리를 살펴보고 사용 가능한 시뮬레이션을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="c91a9-158">시뮬레이션 갤러리는 다음에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="c91a9-159">시뮬레이션 개요 타일의 주 평가 **대시보드 또는**</span><span class="sxs-lookup"><span data-stu-id="c91a9-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="c91a9-160">탐색 창 평가 및 자습서 시뮬레이션을 탐색하여  >  **자습서를 &** 시뮬레이션 **카탈로그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c91a9-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="c91a9-161">시뮬레이션을 실행할 디바이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="c91a9-162">시뮬레이션 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c91a9-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="c91a9-163">시뮬레이션 탭을 선택하여 시뮬레이션 **진행률을 니다.** 시뮬레이션 상태, 활성 경고 및 기타 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="c91a9-164">![시뮬레이션 탭의 이미지](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="c91a9-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="c91a9-165">시뮬레이션을 실행한 후 랩 진행률 표시줄을 살펴보고 자동화된 조사 및 수정을 트리거한 **Endpoint용 Microsoft Defender를** 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="c91a9-166">기능에서 수집 및 분석한 증거를 확인해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91a9-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="c91a9-167">풍부한 쿼리 언어 및 원시 원격 분석을 사용하여 고급 헌팅을 통해 공격 증거를 헌팅하고 위협 분석에 문서화되어 있는 전 세계 위협을 확인해보십시오.</span><span class="sxs-lookup"><span data-stu-id="c91a9-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
