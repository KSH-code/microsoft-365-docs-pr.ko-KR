---
title: Microsoft 365 Defender Api 개요
description: Microsoft 365 Defender의 사용 가능한 Api에 대해 자세히 알아보기
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
ms.openlocfilehash: 75a5853e7128667420819c84fbc3c50b07d669b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845016"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="3d9bf-104">Microsoft 365 Defender Api 개요</span><span class="sxs-lookup"><span data-stu-id="3d9bf-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3d9bf-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3d9bf-105">**Applies to:**</span></span>
- <span data-ttu-id="3d9bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d9bf-106">Microsoft 365 Defender</span></span>


>[!IMPORTANT] 
><span data-ttu-id="3d9bf-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3d9bf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3d9bf-109">Microsoft 365 Defender solution은 통합 준비 플랫폼을 기반으로 구축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-109">Microsoft 365 Defender solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="3d9bf-110">Lop 수준 Microsoft 365 Defender Api를 사용 하면 공유 인시던트 및 고급 구하기 테이블을 기반으로 워크플로를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-110">The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="3d9bf-111">**전체 인시던트 큐** -보안 전문가가 중요 한 사항에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-111">**Combined incidents queue** - Helps security professionals focus on what's critical.</span></span> <span data-ttu-id="3d9bf-112">전체 공격 범위 및 영향을 받는 자산이 함께 그룹화 되 고 인시던트 API 아래에 적절 한 시기에 표시 되도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-112">Helps to ensure that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="3d9bf-113">**제품 간 위협 사냥** -보안 팀은 다양 한 보호 제품에서 수집한 원시 데이터에 대 한 api를 통해 고유한 사용자 지정 쿼리를 만들어 손상의 징후를 사냥 하기 위해 고유한 조직의 지식을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-113">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="3d9bf-114">이러한 Api 집합 외에도 각각의 각 보호 제품은 각 제품 기능을 기반으로 하는 추가 Api를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d9bf-114">In addition to these set of APIs, each of the various protection products expose additional APIs to help you innovate based on each product capability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d9bf-115">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3d9bf-115">Related topics</span></span>
- [<span data-ttu-id="3d9bf-116">Microsoft Threat Protection Api 액세스</span><span class="sxs-lookup"><span data-stu-id="3d9bf-116">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="3d9bf-117">기타 API 리소스</span><span class="sxs-lookup"><span data-stu-id="3d9bf-117">Other API resources</span></span>](api-articles.md)
