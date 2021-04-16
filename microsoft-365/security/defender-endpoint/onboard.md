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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861338"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="ad05e-104">끝점용 Microsoft Defender 기능 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="ad05e-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ad05e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ad05e-105">**Applies to:**</span></span>

- [<span data-ttu-id="ad05e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ad05e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ad05e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad05e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ad05e-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="ad05e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad05e-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ad05e-110">조직에 최상의 보안 보호를 제공하도록 끝점 기능용 Defender를 구성하고 관리하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="ad05e-111">조직에서 새 장치를 연결하는 데 대한 실용적인 조언은 끝점용 Microsoft Defender 서비스에 장치 온보딩을 [참조합니다.](./onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="ad05e-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ad05e-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ad05e-112">In this section</span></span>

<span data-ttu-id="ad05e-113">항목</span><span class="sxs-lookup"><span data-stu-id="ad05e-113">Topic</span></span> | <span data-ttu-id="ad05e-114">설명</span><span class="sxs-lookup"><span data-stu-id="ad05e-114">Description</span></span>
:---|:---
[<span data-ttu-id="ad05e-115">Microsoft Defender 보안 센터 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ad05e-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="ad05e-116">일반 설정, 고급 기능 등의 포털 관련 설정을 구성하거나 미리 보기 환경을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad05e-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="ad05e-117">공격 표면 감소 기능 구성</span><span class="sxs-lookup"><span data-stu-id="ad05e-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="ad05e-118">공격 표면 감소 기능을 구성하여 설정이 올바르게 적용되고 악용 완화 기술이 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="ad05e-119">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="ad05e-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="ad05e-120">모든 유형의 새로운 위협을 catch하도록 차세대 보호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="ad05e-121">Microsoft 위협 전문가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="ad05e-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="ad05e-122">Microsoft 위협 전문가의 사이버 보안 위협 인텔리전스를 구성하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="ad05e-123">Microsoft Threat Protection 통합 구성</span><span class="sxs-lookup"><span data-stu-id="ad05e-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="ad05e-124">끝점용 Defender와 통합되는 다른 솔루션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="ad05e-125">관리 및 API 지원</span><span class="sxs-lookup"><span data-stu-id="ad05e-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="ad05e-126">SIEM(보안 정보 및 이벤트 관리)으로 경고를 끌어오거나 API를 사용하여 사용자 지정 경고를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="ad05e-127">Power BI 보고서를 만들고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ad05e-127">Create and build Power BI reports.</span></span>
