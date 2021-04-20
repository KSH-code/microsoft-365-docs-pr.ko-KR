---
title: 공격 표면 감소 개요
ms.reviewer: ''
description: 끝점용 Microsoft Defender의 공격 표면 축소 기능에 대해 자세히 알아보십시오.
keywords: asr, 공격 표면 감소, Microsoft Defender atp, 끝점용 Microsoft Defender, Microsoft Defender, 바이러스 백신, av, windows defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 60efae91e4b65c5977bd2aebf111d9174d7c1042
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893556"
---
# <a name="overview-of-attack-surface-reduction"></a><span data-ttu-id="f106f-104">공격 표면 감소 개요</span><span class="sxs-lookup"><span data-stu-id="f106f-104">Overview of attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f106f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f106f-105">**Applies to:**</span></span>
- [<span data-ttu-id="f106f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f106f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f106f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f106f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f106f-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="f106f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f106f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f106f-110">조직이 사이버 위협 및 공격에 취약한 장소를 최소화하여 공격 표면을 줄이는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-110">Help reduce your attack surfaces, by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="f106f-111">다음 리소스를 사용하여 조직의 장치 및 응용 프로그램에 대한 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-111">Use the following resources to configure protection for the devices and applications in your organization.</span></span>


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]


<span data-ttu-id="f106f-112">문서</span><span class="sxs-lookup"><span data-stu-id="f106f-112">Article</span></span> | <span data-ttu-id="f106f-113">설명</span><span class="sxs-lookup"><span data-stu-id="f106f-113">Description</span></span>
-|-
[<span data-ttu-id="f106f-114">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="f106f-114">Attack surface reduction</span></span>](./attack-surface-reduction.md) | <span data-ttu-id="f106f-115">맬웨어를 중지하는 데 도움이 되는 지능형 규칙을 사용하여 응용 프로그램에서 취약성(공격 표면)을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-115">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="f106f-116">(Microsoft Defender 바이러스 백신이 필요합니다.)</span><span class="sxs-lookup"><span data-stu-id="f106f-116">(Requires Microsoft Defender Antivirus).</span></span>
[<span data-ttu-id="f106f-117">하드웨어 기반 격리</span><span class="sxs-lookup"><span data-stu-id="f106f-117">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="f106f-118">시스템의 시작 및 실행 중일 때 시스템의 무결성을 보호하고 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-118">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="f106f-119">로컬 및 원격 인증을 통해 시스템 무결성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-119">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="f106f-120">또한 Microsoft Edge에 대한 컨테이너를 사용하여 악성 웹 사이트를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-120">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span>
[<span data-ttu-id="f106f-121">응용 프로그램 제어</span><span class="sxs-lookup"><span data-stu-id="f106f-121">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="f106f-122">응용 프로그램을 실행하려면 응용 프로그램이 신뢰를 획득해야 하게 응용 프로그램 제어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-122">Use application control so that your applications must earn trust in order to run.</span></span>
[<span data-ttu-id="f106f-123">악용 방지</span><span class="sxs-lookup"><span data-stu-id="f106f-123">Exploit protection</span></span>](./exploit-protection.md) | <span data-ttu-id="f106f-124">조직에서 사용하는 운영 체제 및 앱이 악용되지 못하게 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-124">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="f106f-125">Exploit Protection은 타사 바이러스 백신 솔루션에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-125">Exploit protection also works with third-party antivirus solutions.</span></span>
[<span data-ttu-id="f106f-126">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="f106f-126">Network protection</span></span>](./network-protection.md) | <span data-ttu-id="f106f-127">조직의 장치에서 네트워크 트래픽 및 연결로 보호를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="f106f-128">(Microsoft Defender 바이러스 백신 필요)</span><span class="sxs-lookup"><span data-stu-id="f106f-128">(Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="f106f-129">웹 보호</span><span class="sxs-lookup"><span data-stu-id="f106f-129">Web protection</span></span>](./web-protection-overview.md) | <span data-ttu-id="f106f-130">웹 위협에 대해 장치를 보호하고 원치 않는 콘텐츠를 규제하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-130">Secure your devices against web threats and help you regulate unwanted content.</span></span>
[<span data-ttu-id="f106f-131">제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="f106f-131">Controlled folder access</span></span>](./controlled-folders.md) | <span data-ttu-id="f106f-132">악의적 또는 의심스러운 앱(파일 암호화 랜섬웨어 맬웨어 포함)이 주요 시스템 폴더의 파일을 변경하지 못하게 방지하는 데 도움이 됩니다(Microsoft Defender 바이러스 백신 필요).</span><span class="sxs-lookup"><span data-stu-id="f106f-132">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="f106f-133">네트워크 방화벽</span><span class="sxs-lookup"><span data-stu-id="f106f-133">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | <span data-ttu-id="f106f-134">양측 네트워크 트래픽 필터링을 사용하여 권한이 없는 트래픽이 조직의 장치에서 유입되는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="f106f-134">Prevent unauthorized traffic from flowing to or from your organization's devices with two-way network traffic filtering.</span></span>
[<span data-ttu-id="f106f-135">공격 표면 감소 FAQ</span><span class="sxs-lookup"><span data-stu-id="f106f-135">Attack surface reduction FAQ</span></span>](./attack-surface-reduction-faq.md) | <span data-ttu-id="f106f-136">공격 표면 감소 규칙, 라이선싱에 대한 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="f106f-136">Frequently asked questions about Attack surface reduction rules, licensing, and more.</span></span>
