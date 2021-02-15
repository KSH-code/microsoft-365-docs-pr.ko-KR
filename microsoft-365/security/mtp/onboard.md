---
title: 끝점용 Microsoft Defender 기능 구성 및 관리
ms.reviewer: ''
description: 공격 표면 감소 및 차세대 보호와 같은 끝점 기능에 대한 Microsoft Defender 구성 및 관리
keywords: 구성, 관리, 기능, 공격 표면 감소, 차세대 보호, 보안 제어, 끝점 감지 및 대응, 자동 조사 및 수정, 보안 제어, 컨트롤
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d04177ef38c1bd04b0b73e29de9d8ab6fc0893ce
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930129"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="b704a-104">끝점용 Microsoft Defender 기능 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="b704a-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b704a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b704a-105">**Applies to:**</span></span>

- [<span data-ttu-id="b704a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b704a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="b704a-107">조직에 가장 적합한 보안 보호를 얻을 수 있도록 모든 끝점용 Microsoft Defender 기능을 구성하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="b704a-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b704a-108">In this section</span></span> 
<span data-ttu-id="b704a-109">항목</span><span class="sxs-lookup"><span data-stu-id="b704a-109">Topic</span></span> | <span data-ttu-id="b704a-110">설명</span><span class="sxs-lookup"><span data-stu-id="b704a-110">Description</span></span> 
:---|:---
[<span data-ttu-id="b704a-111">공격 표면 축소 기능 구성</span><span class="sxs-lookup"><span data-stu-id="b704a-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="b704a-112">구성 설정이 올바르게 설정되고 악용 완화 기술이 적용되었는지 확인하여 이러한 기능 집합은 공격 및 악용을 저항합니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="b704a-113">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="b704a-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="b704a-114">모든 유형의 새로운 위협을 catch하도록 차세대 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="b704a-115">Microsoft 위협 전문가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="b704a-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="b704a-116">Microsoft 위협 전문가로부터 사이버 보안 위협 인텔리전스를 얻을 방법을 구성하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="b704a-117">Microsoft 365 Defender 통합 구성</span><span class="sxs-lookup"><span data-stu-id="b704a-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="b704a-118">끝점용 Microsoft Defender와 통합되는 다른 솔루션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="b704a-119">관리 및 API 지원</span><span class="sxs-lookup"><span data-stu-id="b704a-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="b704a-120">SIEM으로 경고를 끌어오거나 API를 사용하여 사용자 지정 경고를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="b704a-121">Power BI 보고서를 만들고 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="b704a-122">Microsoft Defender 보안 센터 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b704a-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="b704a-123">일반 설정, 고급 기능과 같은 포털 관련 설정을 구성하고 미리 보기 환경을 사용하도록 설정하는 등의 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b704a-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



