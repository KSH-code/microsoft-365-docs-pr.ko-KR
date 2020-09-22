---
title: Microsoft Threat Protection Api 개요
description: Microsoft Threat Protection에서 사용할 수 있는 Api에 대해 알아보기
keywords: api, api, 개요, 인시던트, 인시던트, 위협 요소 구하기
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e80d8143898a31f7ae08b2cb1cf9b0eb2fc8bb8e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198670"
---
# <a name="overview-of--microsoft-threat-protection-apis"></a><span data-ttu-id="b47e6-104">Microsoft Threat Protection Api 개요</span><span class="sxs-lookup"><span data-stu-id="b47e6-104">Overview of  Microsoft Threat Protection APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b47e6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b47e6-105">**Applies to:**</span></span>
- <span data-ttu-id="b47e6-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="b47e6-106">Microsoft Threat Protection</span></span>


>[!IMPORTANT] 
><span data-ttu-id="b47e6-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b47e6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b47e6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b47e6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b47e6-109">Microsoft Threat Protection 솔루션은 통합 준비 플랫폼을 기반으로 구축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b47e6-109">Microsoft Threat Protection solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="b47e6-110">Lop 수준 Microsoft Threat Protection Api를 사용 하면 공유 인시던트 및 고급 구하기 테이블을 기반으로 워크플로를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b47e6-110">The lop-level Microsoft Threat Protection APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="b47e6-111">**결합 된 인시던트 큐** -보안 전문가는 전체 공격 범위 및 영향을 받는 자산이 함께 그룹화 되 고 인시던트 API 아래에 적절 하 게 표시 되도록 하 여 중요 한 사항에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="b47e6-111">**Combined incidents queue** - Helps security professionals focus on what's critical by ensuring that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="b47e6-112">**제품 간 위협 사냥** -보안 팀은 다양 한 보호 제품에서 수집한 원시 데이터에 대 한 api를 통해 고유한 사용자 지정 쿼리를 만들어 손상의 징후를 사냥 하기 위해 고유한 조직의 지식을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b47e6-112">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="b47e6-113">각각의 각 보호 제품에는 이러한 Api 집합 외에도 각 제품 기능을 기반으로 하는 추가 Api가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b47e6-113">In addition to these set of APIs each of the various protection products expose additional APIs to help you innovate based on each product capabilities.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b47e6-114">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b47e6-114">Related topics</span></span>
- [<span data-ttu-id="b47e6-115">Microsoft Threat Protectin Api 액세스</span><span class="sxs-lookup"><span data-stu-id="b47e6-115">Access the Microsoft Threat Protectin APIs</span></span>](api-access.md)
- [<span data-ttu-id="b47e6-116">기타 API 리소스</span><span class="sxs-lookup"><span data-stu-id="b47e6-116">Other API resources</span></span>](api-articles.md)
