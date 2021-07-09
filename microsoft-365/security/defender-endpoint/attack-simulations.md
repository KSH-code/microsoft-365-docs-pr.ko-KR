---
title: 시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender 경험
description: 제공된 공격 시나리오 시뮬레이션을 실행하여 Microsoft Defender for Endpoint가 위반을 감지, 조사 및 대응하는 방법을 경험합니다.
keywords: test, scenario, attack, simulation, simulationd, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339541"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="f83b8-104">시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender 경험</span><span class="sxs-lookup"><span data-stu-id="f83b8-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f83b8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f83b8-105">**Applies to:**</span></span>
- [<span data-ttu-id="f83b8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f83b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f83b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f83b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="f83b8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f83b8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f83b8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="f83b8-110">끝점용 Microsoft Defender의 최신 향상된 기능: [엔드포인트용 Defender의](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)새로운 기능.</span><span class="sxs-lookup"><span data-stu-id="f83b8-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="f83b8-111">Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="f83b8-112">읽기: [Insights MITRE ATT&평가에서 읽어 들이기](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="f83b8-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="f83b8-113">서비스에 여러 장치를 온보딩하기 전에 Endpoint용 Defender를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="f83b8-114">이를 위해 몇 가지 테스트 장치에서 제어된 공격 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="f83b8-115">시뮬레이션된 공격을 실행한 후 Endpoint용 Defender가 악의적인 활동을 어떻게 표면화하는지 검토하고 이를 통해 효율적인 대응을 가능하게 하는 방법을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f83b8-116">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="f83b8-116">Before you begin</span></span>

<span data-ttu-id="f83b8-117">제공된 시뮬레이션을 실행하려면 하나 이상의 온보드 [디바이스가 필요합니다.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="f83b8-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="f83b8-118">각 공격 시나리오와 함께 제공되는 walkthrough 문서를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="f83b8-119">각 문서에는 OS 및 응용 프로그램 요구 사항과 공격 시나리오와 관련한 자세한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="f83b8-120">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="f83b8-120">Run a simulation</span></span>

1. <span data-ttu-id="f83b8-121">**Endpoints** Evaluation & 자습서 자습서 & 시뮬레이션 에서 시뮬레이션할 사용 가능한 공격 시나리오를  >    >  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-121">In **Endpoints** > **Evaluation & tutorials** > **Tutorials & simulations**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="f83b8-122">**시나리오 1: 문서 드롭 백도어** - 사회적으로 엔지니어링된 Lure 문서의 배달을 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="f83b8-123">이 문서는 공격자가 제어할 수 있는 특수하게 만들어진 백도어를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="f83b8-124">**시나리오 2: 파일** 없는 공격의 PowerShell 스크립트 - PowerShell을 사용하여 공격 표면 감소 및 악의적인 메모리 활동의 장치 학습 감지를 표시하는 파일 없는 공격을 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="f83b8-125">**시나리오 3: 자동화된** 인시던트 대응 - 인시던트 대응 용량을 확장하기 위해 위반 아티팩트를 자동으로 헌팅하고 수정하는 자동화된 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="f83b8-126">선택한 시나리오와 함께 제공된 해당 Walkthrough 문서를 다운로드하고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="f83b8-127">시뮬레이션 파일을 다운로드하거나 자습서 에서 도움말   >  **시뮬레이션으로 & 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="f83b8-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="f83b8-128">테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="f83b8-129">테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다. 이 문서의 지시에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="f83b8-130">시뮬레이션 파일 또는 스크립트는 공격 활동을 모방하지만 실제로는 양호하며 테스트 장치를 손상하거나 손상하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="f83b8-131">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f83b8-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f83b8-132">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f83b8-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="f83b8-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f83b8-133">Related topics</span></span>

- [<span data-ttu-id="f83b8-134">온보딩 장치</span><span class="sxs-lookup"><span data-stu-id="f83b8-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="f83b8-135">그룹 정책을 통한 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="f83b8-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
