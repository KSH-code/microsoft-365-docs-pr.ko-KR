---
title: 공격 표면 감소 구성
description: Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell cmdlet 및 그룹 정책을 사용하여 공격 표면 감소를 구성합니다.
keywords: asr, 공격 표면 감소, windows defender, microsoft defender, 바이러스 백신, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166169"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="ab07a-104">공격 표면 감소 구성</span><span class="sxs-lookup"><span data-stu-id="ab07a-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab07a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ab07a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab07a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab07a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab07a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab07a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ab07a-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ab07a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab07a-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ab07a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="ab07a-110">다음을 비롯한 여러 도구를 사용하여 공격 표면 감소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab07a-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="ab07a-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab07a-111">Microsoft Intune</span></span>
* <span data-ttu-id="ab07a-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ab07a-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="ab07a-113">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="ab07a-113">Group Policy</span></span>
* <span data-ttu-id="ab07a-114">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="ab07a-114">PowerShell cmdlets</span></span>

<span data-ttu-id="ab07a-115">문서</span><span class="sxs-lookup"><span data-stu-id="ab07a-115">Article</span></span> | <span data-ttu-id="ab07a-116">설명</span><span class="sxs-lookup"><span data-stu-id="ab07a-116">Description</span></span>
-|-
[<span data-ttu-id="ab07a-117">Microsoft Edge에 대해 하드웨어 기반의 고리 사용</span><span class="sxs-lookup"><span data-stu-id="ab07a-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="ab07a-118">하드웨어 및 소프트웨어 요구 사항을 포함하여 Application Guard를 준비하고 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab07a-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="ab07a-119">응용 프로그램 제어 사용</span><span class="sxs-lookup"><span data-stu-id="ab07a-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="ab07a-120">사용자가 실행한 응용 프로그램을 제어하고 커널 모드 프로세스를 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab07a-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="ab07a-121">Exploit Protection</span><span class="sxs-lookup"><span data-stu-id="ab07a-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="ab07a-122">운영 체제 프로세스와 개별 앱 모두에 악용 완화 기술을 자동으로 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab07a-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="ab07a-123">네트워크 보호</span><span class="sxs-lookup"><span data-stu-id="ab07a-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="ab07a-124">사용자가 앱을 사용하여 위험한 도메인에 액세스하지 못하게 하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab07a-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="ab07a-125">제어된 폴더 액세스</span><span class="sxs-lookup"><span data-stu-id="ab07a-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="ab07a-126">악성 앱으로부터 중요한 데이터를 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab07a-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="ab07a-127">공격 표면 감소</span><span class="sxs-lookup"><span data-stu-id="ab07a-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="ab07a-128">악용 검색 맬웨어에 의해 일반적으로 사용되는 작업 및 앱을 방지하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab07a-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="ab07a-129">네트워크 방화벽</span><span class="sxs-lookup"><span data-stu-id="ab07a-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="ab07a-130">네트워크에서 장치 및 데이터를 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab07a-130">How to protect devices and data across a network</span></span>

