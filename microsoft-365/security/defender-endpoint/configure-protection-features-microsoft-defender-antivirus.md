---
title: 보안 보호 Microsoft Defender 바이러스 백신 사용 및 구성
description: Microsoft Defender AV에서 동작 기반, 방어적 및 실시간 보호를 사용하도록 설정할 수 있습니다.
keywords: 맬웨어 방지, 기계 학습, 동작 모니터, 실시간 보호, 무중단, Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925566"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="bd847-104">동작, 추론 및 실시간 보호 구성</span><span class="sxs-lookup"><span data-stu-id="bd847-104">Configure behavioral, heuristic, and real-time protection</span></span>


<span data-ttu-id="bd847-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bd847-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd847-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bd847-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bd847-107">Microsoft Defender 바이러스 백신 여러 가지 방법을 사용하여 위협 방지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd847-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="bd847-108">새로운 위협의 거의 즉각적인 탐지 및 차단을 위한 클라우드 제공 보호</span><span class="sxs-lookup"><span data-stu-id="bd847-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="bd847-109">파일 및 프로세스 동작 모니터링 및 기타추론("실시간 보호"라고도 알려지기)을 사용하는 항상 검사</span><span class="sxs-lookup"><span data-stu-id="bd847-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="bd847-110">기계 학습, 인간 및 자동화된 대규모 데이터 분석 그리고 심층 위협 저항 연구를 기반으로 하는 전용 보호 업데이트</span><span class="sxs-lookup"><span data-stu-id="bd847-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="bd847-111">그룹 정책, Microsoft Defender 바이러스 백신, PowerShell cmdlet 및 WMI(System Center Management Instrumentation)를 사용하여 이러한 Windows 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd847-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="bd847-112">이 섹션에서는 안전하지 않은 것으로 보이지만 맬웨어로 검색되지 않을 수 있는 앱을 검색하고 차단하는 방법을 포함하여 항상 실행되는 검사에 대한 구성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd847-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="bd847-113">클라우드 [제공 보호를 사용하도록 Microsoft Defender 바이러스 백신](cloud-protection-microsoft-defender-antivirus.md) 클라우드 제공 보호를 사용하도록 설정하고 구성하는 방법에 대한 자세한 내용은 클라우드 제공 보호를 통해 차세대 Microsoft Defender 바이러스 백신 기술을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="bd847-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bd847-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bd847-114">In this section</span></span>

 <span data-ttu-id="bd847-115">항목</span><span class="sxs-lookup"><span data-stu-id="bd847-115">Topic</span></span> | <span data-ttu-id="bd847-116">설명</span><span class="sxs-lookup"><span data-stu-id="bd847-116">Description</span></span>
---|---
[<span data-ttu-id="bd847-117">잠재적으로 원하지 않는 응용 프로그램 검색 및 차단</span><span class="sxs-lookup"><span data-stu-id="bd847-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="bd847-118">애드웨어, 브라우저 수정자 및 도구 모음, 악성 또는 가짜 바이러스 백신 앱 등 네트워크에서 원치 않는 앱을 검색하고 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="bd847-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="bd847-119">보안 보호 기능 Microsoft Defender 바이러스 백신 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="bd847-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="bd847-120">실시간 보호,추론 및 기타 상시 모니터링 기능 사용 Microsoft Defender 바이러스 백신 구성</span><span class="sxs-lookup"><span data-stu-id="bd847-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>
