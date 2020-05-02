---
title: Microsoft Defender ATP 기능 구성 및 관리
ms.reviewer: ''
description: Attack surface reduction, 차세대 보호 및 보안 제어와 같은 Microsoft Defender ATP 기능 구성 및 관리
keywords: configure, manage, capabilities, attack surface reduction, 다음 세대 보호, 보안 제어, 끝점 검색 및 응답, 자동 조사 및 업데이트, 보안 제어, 컨트롤
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 2435a934065a06c8105f8ac4e0f80dcfbaed8f7f
ms.sourcegitcommit: b57d597edbff5ab6cff8c2b04d27c15b0024776f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/01/2020
ms.locfileid: "43998052"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="0c075-104">Microsoft Defender ATP 기능 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="0c075-104">Configure and manage Microsoft Defender ATP capabilities</span></span>
<span data-ttu-id="0c075-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0c075-105">**Applies to:**</span></span>

- [<span data-ttu-id="0c075-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="0c075-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="0c075-107">모든 Microsoft Defender ATP 기능을 구성 하 고 관리 하 여 조직에 가장 적합 한 보안 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="0c075-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0c075-108">In this section</span></span> 
<span data-ttu-id="0c075-109">항목</span><span class="sxs-lookup"><span data-stu-id="0c075-109">Topic</span></span> | <span data-ttu-id="0c075-110">설명</span><span class="sxs-lookup"><span data-stu-id="0c075-110">Description</span></span> 
:---|:---
[<span data-ttu-id="0c075-111">공격 영역 감소 기능 구성</span><span class="sxs-lookup"><span data-stu-id="0c075-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="0c075-112">구성 설정이 제대로 설정 되 고 익스플로잇 완화 기술이 적용 되며, 이러한 기능 집합은 공격 및 exploitations을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="0c075-113">차세대 보호 구성</span><span class="sxs-lookup"><span data-stu-id="0c075-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="0c075-114">다음 세대 보호를 구성 하 여 모든 유형의 최신 위협을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="0c075-115">Microsoft Threat 전문가가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="0c075-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="0c075-116">Microsoft Threat 전문가가 cybersecurity 위협 인텔리전스를 가져올 방법을 구성 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="0c075-117">Microsoft Threat Protection 통합 구성</span><span class="sxs-lookup"><span data-stu-id="0c075-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="0c075-118">Microsoft Defender ATP와 통합 되는 다른 솔루션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="0c075-119">관리 및 API 지원</span><span class="sxs-lookup"><span data-stu-id="0c075-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="0c075-120">SIEM에 알림을 끌어오거나 Api를 사용 하 여 사용자 지정 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="0c075-121">Power BI 보고서를 만들고 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="0c075-122">Microsoft Defender 보안 센터 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0c075-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="0c075-123">일반 설정, 고급 기능, 미리 보기 환경 사용 및 기타와 같은 포털 관련 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c075-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



