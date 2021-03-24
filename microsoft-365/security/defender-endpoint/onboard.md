---
title: Microsoft Defender ATP 기능 구성 및 관리
ms.reviewer: ''
description: 공격 표면 감소 및 차세대 보호와 같은 Microsoft Defender ATP 기능 구성 및 관리
keywords: 구성, 관리, 기능, 공격 표면 감소, 차세대 보호, 보안 제어, 끝점 감지 및 대응, 자동 조사 및 수정, 보안 제어, 컨트롤
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
ms.openlocfilehash: e2082929cf1fb7f4b55331cf62adcd9b936168d0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061080"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="4653f-104">끝점용 Microsoft Defender 기능 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="4653f-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4653f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4653f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4653f-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4653f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4653f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4653f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4653f-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4653f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4653f-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="4653f-110">조직에 가장 적합한 보안 보호를 얻을 수 있도록 끝점에 대한 모든 Defender 기능을 구성하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="4653f-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="4653f-111">In this section</span></span> 
<span data-ttu-id="4653f-112">항목</span><span class="sxs-lookup"><span data-stu-id="4653f-112">Topic</span></span> | <span data-ttu-id="4653f-113">설명</span><span class="sxs-lookup"><span data-stu-id="4653f-113">Description</span></span> 
:---|:---
[<span data-ttu-id="4653f-114">공격 표면 감소 기능 구성</span><span class="sxs-lookup"><span data-stu-id="4653f-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="4653f-115">구성 설정이 올바르게 설정되고 악용 완화 기술이 적용되었는지 확인하여 이러한 기능 집합은 공격 및 악용을 저항합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="4653f-116">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="4653f-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="4653f-117">모든 유형의 새로운 위협을 catch하도록 차세대 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="4653f-118">Microsoft 위협 전문가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="4653f-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="4653f-119">Microsoft 위협 전문가로부터 사이버 보안 위협 인텔리전스를 받을 방법을 구성하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="4653f-120">Microsoft Threat Protection 통합 구성</span><span class="sxs-lookup"><span data-stu-id="4653f-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="4653f-121">끝점용 Defender와 통합되는 다른 솔루션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="4653f-122">관리 및 API 지원</span><span class="sxs-lookup"><span data-stu-id="4653f-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="4653f-123">SIEM으로 경고를 끌어오거나 API를 사용하여 사용자 지정 경고를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="4653f-124">Power BI 보고서를 만들고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="4653f-125">Microsoft Defender 보안 센터 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4653f-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="4653f-126">일반 설정, 고급 기능과 같은 포털 관련 설정을 구성하고 미리 보기 환경을 사용하도록 설정하는 등의 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4653f-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



