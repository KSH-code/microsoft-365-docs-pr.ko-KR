---
title: Microsoft Defender 바이러스 백신 기능 구성
description: Intune, Microsoft Defender 바이러스 백신, 그룹 정책 및 PowerShell을 사용하여 Microsoft Endpoint Configuration Manager 기능을 구성할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 구성, 구성, 구성 관리자, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, 모바일 장치 관리, GP, 그룹 정책, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789030"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="ab773-104">Microsoft Defender 바이러스 백신 기능 구성</span><span class="sxs-lookup"><span data-stu-id="ab773-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab773-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ab773-105">**Applies to:**</span></span>

- [<span data-ttu-id="ab773-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab773-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ab773-107">다음을 Microsoft Defender 바이러스 백신 도구를 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab773-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="ab773-108">Microsoft Endpoint Manager(Microsoft Intune 및 Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="ab773-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="ab773-109">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="ab773-109">Group Policy</span></span>
- <span data-ttu-id="ab773-110">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="ab773-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="ab773-111">WMI(Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="ab773-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="ab773-112">다음과 같은 광범위한 기능 범주를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab773-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="ab773-113">클라우드 제공 보호.</span><span class="sxs-lookup"><span data-stu-id="ab773-113">Cloud-delivered protection.</span></span> <span data-ttu-id="ab773-114">클라우드 [제공 보호 및 보호 Microsoft Defender 바이러스 백신](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ab773-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="ab773-115">동작, 학습 및 기계 학습 기반 보호를 비롯한 항상 실시간 보호 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ab773-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="ab773-116">동작,추론적 및 실시간 보호 [구성을 참조합니다.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ab773-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="ab773-117">최종 사용자가 개별 끝점에서 클라이언트와 상호 작용하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab773-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="ab773-118">다음 리소스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab773-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="ab773-119">사용자가 사용자 인터페이스를 보거나 상호 작용하지 Microsoft Defender 바이러스 백신 방지</span><span class="sxs-lookup"><span data-stu-id="ab773-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="ab773-120">사용자가 로컬에서 정책 설정을 수정하지 Microsoft Defender 바이러스 백신 허용</span><span class="sxs-lookup"><span data-stu-id="ab773-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="ab773-121">관리 [및 구성 도구에 대한 참조 항목을 검토합니다.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ab773-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>