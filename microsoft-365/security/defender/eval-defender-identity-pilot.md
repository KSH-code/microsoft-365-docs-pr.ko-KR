---
title: Id에 대한 Microsoft Defender 파일럿, 구성 벤치마크, 표준, 지침을 설정하고, 정찰, 손상된 자격 증명, 측면 이동, 도메인 지위 및 유출 경고와 같은 다양한 ID 위협을 감지하고 수정하는 방법에 대한 자습서를 수행하고, 사용자, 컴퓨터, 엔터티 및 측면 이동 경로 조사를 실시합니다.
description: Microsoft Defender for Identity 파일럿, 벤치마크 설정, 정비, 손상된 자격 증명, 측면 이동, 도메인 위주 및 유출 경고에 대한 자습서를 수행하십시오.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458053"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="2eac0-103">Id에 대한 Microsoft Defender 파일럿</span><span class="sxs-lookup"><span data-stu-id="2eac0-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="2eac0-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2eac0-104">**Applies to:**</span></span>
- <span data-ttu-id="2eac0-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2eac0-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="2eac0-106">이 문서는 Id에 대한 Microsoft Defender의 평가 환경을 설정하는 프로세스의 [3단계](eval-defender-identity-overview.md) 중 3단계입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="2eac0-107">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2eac0-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="2eac0-108">다음 단계에 따라 ID에 맞게 Microsoft Defender에 대한 파일럿을 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="2eac0-109">권장 사항에는 파일럿 그룹 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="2eac0-110">모범 사례는 AD DS(Active Directory 도메인 서비스) 및 AD FS(Active Directory Federated Services)를 실행하는 모든 서버에 센서를 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![Defender 평가 환경에 Id용 Microsoft Defender를 추가하는 단계](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="2eac0-112">다음 표에서는 그림의 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="2eac0-113">1단계: ID 환경에 대한 벤치마크 권장 사항 구성</span><span class="sxs-lookup"><span data-stu-id="2eac0-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="2eac0-114">2단계: 기능 시도 - 다양한 공격 유형을 식별하고 수정하기 위한 자습서를 진행합니다. </span><span class="sxs-lookup"><span data-stu-id="2eac0-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="2eac0-115">1단계.</span><span class="sxs-lookup"><span data-stu-id="2eac0-115">Step 1.</span></span> <span data-ttu-id="2eac0-116">ID 환경에 대한 벤치마크 권장 사항 구성</span><span class="sxs-lookup"><span data-stu-id="2eac0-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="2eac0-117">Microsoft는 Microsoft 클라우드 서비스를 사용하는 고객을 위한 보안 벤치마크 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="2eac0-118">Azure 보안 벤치마크(ASB)는 Azure에서 워크로드, 데이터 및 서비스의 보안을 개선하는 데 도움이 되는 징계적인 모범 사례 및 권장 사항을 제공합니다. [](/security/benchmark/azure/overview)</span><span class="sxs-lookup"><span data-stu-id="2eac0-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="2eac0-119">이러한 벤치마크 권장 사항에는 [Microsoft Defender for Identity에 대한 Azure 보안 기준이 포함됩니다.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)</span><span class="sxs-lookup"><span data-stu-id="2eac0-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="2eac0-120">이러한 권장 사항을 구현하는 데는 계획 및 구현에 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="2eac0-121">이렇게 하면 ID 환경의 보안이 크게 강화되는 반면, ID에 대한 Microsoft Defender를 계속 평가하고 구현하는 것을 방지하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="2eac0-122">이러한 정보는 인식을 위해 여기에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="2eac0-123">2단계.</span><span class="sxs-lookup"><span data-stu-id="2eac0-123">Step 2.</span></span> <span data-ttu-id="2eac0-124">기능 사용 - 다양한 공격 유형을 식별하고 수정하기 위한 자습서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="2eac0-125">Microsoft Defender for Identity 설명서에는 다양한 공격 유형을 식별하고 수정하는 프로세스를 진행하는 일련의 자습서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="2eac0-126">Id용 Defender 자습서를 사용해 냅니다.</span><span class="sxs-lookup"><span data-stu-id="2eac0-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="2eac0-127">정비 경고</span><span class="sxs-lookup"><span data-stu-id="2eac0-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="2eac0-128">손상된 자격 증명 경고</span><span class="sxs-lookup"><span data-stu-id="2eac0-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="2eac0-129">측면 이동 경고</span><span class="sxs-lookup"><span data-stu-id="2eac0-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="2eac0-130">도메인 지수 경고</span><span class="sxs-lookup"><span data-stu-id="2eac0-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="2eac0-131">유출 경고</span><span class="sxs-lookup"><span data-stu-id="2eac0-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="2eac0-132">사용자 조사</span><span class="sxs-lookup"><span data-stu-id="2eac0-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="2eac0-133">컴퓨터 조사</span><span class="sxs-lookup"><span data-stu-id="2eac0-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="2eac0-134">측면 이동 경로 조사</span><span class="sxs-lookup"><span data-stu-id="2eac0-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="2eac0-135">엔터티 조사</span><span class="sxs-lookup"><span data-stu-id="2eac0-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="2eac0-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2eac0-136">Next steps</span></span>

[<span data-ttu-id="2eac0-137">Microsoft Defender에서 Office 365</span><span class="sxs-lookup"><span data-stu-id="2eac0-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="2eac0-138">Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365</span><span class="sxs-lookup"><span data-stu-id="2eac0-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="2eac0-139">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2eac0-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>