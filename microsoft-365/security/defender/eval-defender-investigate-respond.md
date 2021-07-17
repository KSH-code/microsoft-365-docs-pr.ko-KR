---
title: 파일럿 환경에서 Microsoft 365 Defender 조사 및 대응하고 공격 시뮬레이터를 사용하여 사용자에게 공격 표면을 감지하고 조사하고 보안 환경을 강화하도록 교육합니다.
description: Microsoft 365 Defender 테스트 랩 또는 파일럿 환경에서 공격 시뮬레이션을 설정하여 사용자에게 장치, ID, 데이터 및 응용 프로그램을 보호하도록 설계된 보안 솔루션을 시도합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 590b9445b08e3a786b32e7086f27b140934d22d0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458815"
---
# <a name="investigate-and-respond-using-microsoft-365-defender-in-a-pilot-environment"></a><span data-ttu-id="a7939-103">파일럿 환경에서 파일럿 Microsoft 365 Defender 사용하여 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="a7939-103">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>

<span data-ttu-id="a7939-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a7939-104">**Applies to:**</span></span>
- <span data-ttu-id="a7939-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7939-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="a7939-106">이 문서에서는 공격 시뮬레이션 및 자습서를 사용하여 인시던트 만들기 프로세스를 간략하게 설명하고 Microsoft 365 Defender 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7939-106">This article outlines the process to create incidents with attack simulations and tutorials and use Microsoft 365 Defender to investigate and respond.</span></span> <span data-ttu-id="a7939-107">이 프로세스를 시작하기 전에 전체 프로세스를 검토하여 Microsoft 365 Defender [](eval-overview.md) 평가 환경을 Microsoft 365 Defender [합니다.](eval-create-eval-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a7939-107">Before starting this process, be sure you've reviewed the overall process for [evaluating Microsoft 365 Defender](eval-overview.md) and you have [created the Microsoft 365 Defender evaluation environment](eval-create-eval-environment.md).</span></span>

<span data-ttu-id="a7939-108">다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7939-108">Use the following steps.</span></span>

![Microsoft 365 Defender 평가 환경에서 시뮬레이트된 인시던트 대응을 수행하기 위한 단계](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-steps.png)

<span data-ttu-id="a7939-110">다음 표에서는 그림의 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7939-110">The following table describes the steps in the illustration.</span></span>

| |<span data-ttu-id="a7939-111">단계</span><span class="sxs-lookup"><span data-stu-id="a7939-111">Step</span></span>  |<span data-ttu-id="a7939-112">설명</span><span class="sxs-lookup"><span data-stu-id="a7939-112">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a7939-113">1</span><span class="sxs-lookup"><span data-stu-id="a7939-113">1</span></span>|[<span data-ttu-id="a7939-114">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="a7939-114">Simulate attacks</span></span>](eval-defender-investigate-respond-simulate-attack.md)     |   <span data-ttu-id="a7939-115">평가 환경에 대한 공격을 시뮬레이트하고 Microsoft 365 Defender 포털을 사용하여 인시던트 대응을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7939-115">Simulate attacks on your evaluation environment and use the Microsoft 365 Defender portal to perform incident response.</span></span>      |
|<span data-ttu-id="a7939-116">2 </span><span class="sxs-lookup"><span data-stu-id="a7939-116">2</span></span>|[<span data-ttu-id="a7939-117">인시던트 대응 기능 시도 </span><span class="sxs-lookup"><span data-stu-id="a7939-117">Try incident response capabilities </span></span>](eval-defender-investigate-respond-additional.md)    |    <span data-ttu-id="a7939-118">Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a7939-118">Try features and capabilities in Microsoft 365 Defender.</span></span>     |
||||

### <a name="navigation-you-may-need"></a><span data-ttu-id="a7939-119">필요한 탐색</span><span class="sxs-lookup"><span data-stu-id="a7939-119">Navigation you may need</span></span>

[<span data-ttu-id="a7939-120">Microsoft 365 Defender 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="a7939-120">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
