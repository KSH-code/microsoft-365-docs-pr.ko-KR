---
title: 시뮬레이션된 공격을 통해 Microsoft Defender ATP 경험
description: 제공된 공격 시나리오 시뮬레이션을 실행하여 Microsoft Defender ATP가 위반을 감지, 조사 및 대응하는 방법을 경험합니다.
keywords: wdatp, 테스트, 시나리오, 공격, 시뮬레이션, 시뮬레이션, diy, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 25538e1866db8f4a7bff24ac336005bf2e1ce78b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073052"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="e1147-104">시뮬레이트된 공격을 통해 끝점에 대한 Microsoft Defender 경험</span><span class="sxs-lookup"><span data-stu-id="e1147-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e1147-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e1147-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1147-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e1147-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e1147-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1147-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e1147-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e1147-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e1147-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="e1147-110">Microsoft Defender ATP의 최신 향상된 기능: [끝점용 Defender의 새로운 기능에 대해 자세히 알아보세요.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="e1147-110">Learn about the latest enhancements in Microsoft Defender ATP: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="e1147-111">Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="e1147-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="e1147-112">읽기: [MITRE ATT의 인사이트&CK 기반 평가.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="e1147-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="e1147-113">서비스에 여러 장치를 온보딩하기 전에 Endpoint용 Defender를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="e1147-114">이를 위해 몇 가지 테스트 장치에서 제어된 공격 시뮬레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="e1147-115">시뮬레이션된 공격을 실행한 후 Endpoint용 Defender가 악의적인 활동을 어떻게 표면화하는지 검토하고 이를 통해 효율적인 대응을 가능하게 하는 방법을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e1147-116">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="e1147-116">Before you begin</span></span>

<span data-ttu-id="e1147-117">제공된 시뮬레이션을 실행하려면 하나 이상의 온보드 [디바이스가 필요합니다.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e1147-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="e1147-118">각 공격 시나리오와 함께 제공되는 walkthrough 문서를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="e1147-119">각 문서에는 OS 및 응용 프로그램 요구 사항과 공격 시나리오와 관련한 자세한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="e1147-120">시뮬레이션 실행</span><span class="sxs-lookup"><span data-stu-id="e1147-120">Run a simulation</span></span>

1. <span data-ttu-id="e1147-121">도움말 **시뮬레이션**& 자습서 에서 시뮬레이션할 사용 가능한 공격 시나리오를  >  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-121">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="e1147-122">**시나리오 1: 문서 드롭 백도어** - 사회적으로 엔지니어링된 Lure 문서의 배달을 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="e1147-123">이 문서는 공격자가 제어할 수 있는 특수하게 만들어진 백도어를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="e1147-124">**시나리오 2: 파일** 없는 공격의 PowerShell 스크립트 - PowerShell을 사용하여 공격 표면 감소 및 악의적인 메모리 활동의 장치 학습 감지를 표시하는 파일 없는 공격을 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="e1147-125">**시나리오 3: 자동화된** 인시던트 대응 - 인시던트 대응 용량을 확장하기 위해 위반 아티팩트를 자동으로 헌팅하고 수정하는 자동화된 조사를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="e1147-126">선택한 시나리오와 함께 제공된 해당 Walkthrough 문서를 다운로드하고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="e1147-127">시뮬레이션 파일을 다운로드하거나 자습서 에서 도움말   >  **시뮬레이션으로 & 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="e1147-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="e1147-128">테스트 장치에서 파일 또는 스크립트를 다운로드할 수 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="e1147-129">테스트 장치에서 시뮬레이션 파일 또는 스크립트를 실행합니다. 이 문서의 지시에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="e1147-130">시뮬레이션 파일 또는 스크립트는 공격 활동을 모방하지만 실제로는 양호하며 테스트 장치를 손상하거나 손상하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="e1147-131">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e1147-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e1147-132">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e1147-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="e1147-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e1147-133">Related topics</span></span>

- [<span data-ttu-id="e1147-134">장치 온보드</span><span class="sxs-lookup"><span data-stu-id="e1147-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="e1147-135">Windows 10 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="e1147-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
