---
title: 하드웨어 기반의 고리(Windows 10)
ms.reviewer: ''
description: Windows 10에서 하드웨어 기반의 고가용성으로 맬웨어를 방지하는 방법에 대해 자세히 알아보습니다.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060951"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="7ef29-103">Windows 10의 하드웨어 기반 고리</span><span class="sxs-lookup"><span data-stu-id="7ef29-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ef29-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7ef29-104">**Applies to:**</span></span>
- [<span data-ttu-id="7ef29-105">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7ef29-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7ef29-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ef29-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7ef29-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="7ef29-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7ef29-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef29-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="7ef29-109">하드웨어 기반을 통해 Windows 10의 시스템 무결성을 보호하고 끝점용 Microsoft Defender와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ef29-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="7ef29-110">기능</span><span class="sxs-lookup"><span data-stu-id="7ef29-110">Feature</span></span> | <span data-ttu-id="7ef29-111">설명</span><span class="sxs-lookup"><span data-stu-id="7ef29-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="7ef29-112">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="7ef29-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="7ef29-113">Application Guard는 생산성을 유지하면서 고급 공격으로부터 장치를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef29-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="7ef29-114">고유한 하드웨어 기반 격리 방법을 사용하여 기본 Windows 하이퍼바이저를 통해 운영 체제와 분리된 경량 컨테이너 내에서 트러스트되지 않은 웹 사이트와 PDF 문서를 격리하는 것이 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="7ef29-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="7ef29-115">트러스터가 악의적인 것으로 확인된 사이트 또는 PDF 문서는 여전히 Application Guard의 보안 컨테이너 내에 포함되어 데스크톱 PC를 보호하고 공격자가 엔터프라이즈 데이터에서 멀어지게 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef29-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="7ef29-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="7ef29-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="7ef29-117">System Guard는 시스템 시작 및 실행 후 시스템의 무결성을 보호하고 유지 관리하며, 의거를 사용하여 시스템 무결성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef29-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

