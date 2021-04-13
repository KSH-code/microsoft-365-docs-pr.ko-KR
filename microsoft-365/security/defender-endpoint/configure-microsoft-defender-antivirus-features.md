---
title: Microsoft Defender 바이러스 백신 기능 구성
description: Intune, Microsoft Endpoint Configuration Manager, 그룹 정책 및 PowerShell을 사용하여 Microsoft Defender 바이러스 백신 기능을 구성할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 구성, 구성, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, 모바일 장치 관리, GP, 그룹 정책, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690820"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="3f036-104">Microsoft Defender 바이러스 백신 기능 구성</span><span class="sxs-lookup"><span data-stu-id="3f036-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3f036-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3f036-105">**Applies to:**</span></span>

- <span data-ttu-id="3f036-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="3f036-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="3f036-107">다음을 비롯한 다양한 도구를 사용하여 Microsoft Defender 바이러스 백신을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f036-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="3f036-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3f036-108">Microsoft Intune</span></span>
- <span data-ttu-id="3f036-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3f036-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="3f036-110">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="3f036-110">Group Policy</span></span>
- <span data-ttu-id="3f036-111">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3f036-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="3f036-112">WMI(Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="3f036-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="3f036-113">다음과 같은 광범위한 기능 범주를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f036-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="3f036-114">클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="3f036-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="3f036-115">동작, 학습 및 기계 학습 기반 보호를 비롯한 항상 실시간 보호</span><span class="sxs-lookup"><span data-stu-id="3f036-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="3f036-116">최종 사용자가 개별 끝점에서 클라이언트와 상호 작용하는 방법</span><span class="sxs-lookup"><span data-stu-id="3f036-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="3f036-117">다음 문서에서는 Microsoft Defender 바이러스 백신을 구성할 때 주요 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f036-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3f036-118">각 문서에는 해당 구성 도구(또는 도구)에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f036-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="3f036-119">문서</span><span class="sxs-lookup"><span data-stu-id="3f036-119">Article</span></span>  |<span data-ttu-id="3f036-120">설명</span><span class="sxs-lookup"><span data-stu-id="3f036-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="3f036-121">Microsoft 클라우드 제공 Microsoft Defender 바이러스 백신 보호 활용</span><span class="sxs-lookup"><span data-stu-id="3f036-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="3f036-122">빠르고 강력한 바이러스 백신 탐지를 위해 클라우드 제공 보호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f036-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="3f036-123">동작,추론적 및 실시간 보호 구성</span><span class="sxs-lookup"><span data-stu-id="3f036-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="3f036-124">동작 기반,추론적 및 실시간 바이러스 백신 보호를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="3f036-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="3f036-125">Microsoft Defender 바이러스 백신과 최종 사용자 상호 작용 구성</span><span class="sxs-lookup"><span data-stu-id="3f036-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="3f036-126">조직의 최종 사용자가 Microsoft Defender 바이러스 백신과 상호 작용하는 방법, 사용자에게 어떤 알림이 표시될지, 설정을 오버라이드할 수 있는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f036-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="3f036-127">또한 관리 및 구성 도구에 대한 [참조](configuration-management-reference-microsoft-defender-antivirus.md) 항목을 검토하여 각 도구에 대한 개요와 추가 도움말에 대한 링크를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f036-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>