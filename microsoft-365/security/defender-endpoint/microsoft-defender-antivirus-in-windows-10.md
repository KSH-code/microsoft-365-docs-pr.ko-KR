---
title: 차세대 보호
description: Microsoft Defender 바이러스 백신, 기본 제공 맬웨어 방지 및 바이러스 백신 보호를 관리, 구성 및 사용하는 방법을 학습합니다.
keywords: Microsoft Defender 바이러스 백신, windows defender, 맬웨어 방지, scep, system center endpoint protection, system center configuration manager, 바이러스, 맬웨어, 위협, 탐지, 보호, 보안
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: eb7e0253b3761d05d112500c0410fffa58548221
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765422"
---
# <a name="next-generation-protection"></a><span data-ttu-id="d16c8-104">차세대 보호</span><span class="sxs-lookup"><span data-stu-id="d16c8-104">Next-generation protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d16c8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d16c8-105">**Applies to:**</span></span>

- <span data-ttu-id="d16c8-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="d16c8-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a><span data-ttu-id="d16c8-107">Microsoft Defender 바이러스 백신: 차세대 보호</span><span class="sxs-lookup"><span data-stu-id="d16c8-107">Microsoft Defender Antivirus: Your next-generation protection</span></span>

<span data-ttu-id="d16c8-108">Microsoft Defender 바이러스 백신은 끝점용 Microsoft Defender의 차세대 보호 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-108">Microsoft Defender Antivirus is the next-generation protection component of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d16c8-109">이 보호는 기계 학습, 빅 데이터 분석, 심층 위협 저항 연구 및 Microsoft 클라우드 인프라를 함께 사용하여 엔터프라이즈 조직의 장치를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-109">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices in your enterprise organization.</span></span> <span data-ttu-id="d16c8-110">차세대 보호 서비스에는 다음 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-110">Your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="d16c8-111">[동작 기반,](configure-protection-features-microsoft-defender-antivirus.md)지론 및 실시간 바이러스 백신 보호 - 파일 및 프로세스 동작 모니터링 및 기타추론(실시간 보호라고도 알려지기)을 사용하는 항상 검사가 *포함됩니다.*</span><span class="sxs-lookup"><span data-stu-id="d16c8-111">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="d16c8-112">또한 안전하지 않은 것으로 보이지만 맬웨어로 검색되지 않을 수 있는 앱을 검색하고 차단하는 방법도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-112">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="d16c8-113">[클라우드 제공 보호](cloud-protection-microsoft-defender-antivirus.md)- 새로운 위협을 거의 즉각적으로 감지하고 차단하는 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-113">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="d16c8-114">[전용 보호 및 제품 업데이트](manage-updates-baselines-microsoft-defender-antivirus.md)에는 Microsoft Defender 바이러스 백신을 최신 상태로 유지하는 데 관련된 업데이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-114">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="d16c8-115">데모를 사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="d16c8-115">Try a demo!</span></span>

<span data-ttu-id="d16c8-116">[Endpoint용 Microsoft Defender 데모](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 웹 사이트를 방문하여 다음 보호 기능이 작동하고 있으며 데모 시나리오를 사용하여 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-116">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>
- <span data-ttu-id="d16c8-117">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="d16c8-117">Cloud-delivered protection</span></span>
- <span data-ttu-id="d16c8-118">BAFS(최초 차단) 보호</span><span class="sxs-lookup"><span data-stu-id="d16c8-118">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="d16c8-119">잠재적으로 원치 않는 응용 프로그램(PUA) 보호</span><span class="sxs-lookup"><span data-stu-id="d16c8-119">Potentially unwanted applications (PUA) protection</span></span>

## <a name="minimum-system-requirements"></a><span data-ttu-id="d16c8-120">최소 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d16c8-120">Minimum system requirements</span></span>

<span data-ttu-id="d16c8-121">Microsoft Defender 바이러스 백신의 하드웨어 요구 사항은 Windows 10과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-121">Microsoft Defender Antivirus has the same hardware requirements as of Windows 10.</span></span> <span data-ttu-id="d16c8-122">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d16c8-122">For more information, see the following resources:</span></span>

- [<span data-ttu-id="d16c8-123">최소 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d16c8-123">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [<span data-ttu-id="d16c8-124">하드웨어 구성 요소 지침</span><span class="sxs-lookup"><span data-stu-id="d16c8-124">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="d16c8-125">차세대 보호 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="d16c8-125">Configure next-generation protection services</span></span>

<span data-ttu-id="d16c8-126">차세대 보호 서비스를 구성하는 방법에 대한 자세한 내용은 Microsoft Defender 바이러스 백신 기능 [구성을 참조하세요.](configure-microsoft-defender-antivirus-features.md)</span><span class="sxs-lookup"><span data-stu-id="d16c8-126">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="d16c8-127">구성 및 관리는 Microsoft Defender 바이러스 백신을 실행하는 동안 Windows Server 2016 및 Windows Server 2019에서 크게 동일합니다. 그러나 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d16c8-127">Configuration and management is largely the same in Windows Server 2016 and Windows Server 2019, while running Microsoft Defender Antivirus; however, there are some differences.</span></span> <span data-ttu-id="d16c8-128">자세한 내용은 [Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신을 참조합니다.](microsoft-defender-antivirus-on-windows-server.md)</span><span class="sxs-lookup"><span data-stu-id="d16c8-128">To learn more, see [Microsoft Defender Antivirus on Windows Server 2016 and 2019](microsoft-defender-antivirus-on-windows-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d16c8-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d16c8-129">See also</span></span>

- [<span data-ttu-id="d16c8-130">Windows Server 2016 및 2019의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="d16c8-130">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="d16c8-131">Microsoft Defender 바이러스 백신 관리 및 구성</span><span class="sxs-lookup"><span data-stu-id="d16c8-131">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d16c8-132">Microsoft Defender 바이러스 백신 보호 평가</span><span class="sxs-lookup"><span data-stu-id="d16c8-132">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)