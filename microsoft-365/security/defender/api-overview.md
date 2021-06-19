---
title: API Microsoft 365 Defender 개요
description: 2013에서 사용 가능한 API에 대해 Microsoft 365 Defender
keywords: api, api, 개요, 인시던트, 인시던트, 위협 헌팅, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1ddb6da49e5e9f23aacf73caaeb91302ac9c19c9
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028970"
---
# <a name="overview-of-microsoft-365-defender-apis"></a><span data-ttu-id="ceca9-104">API Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="ceca9-104">Overview of Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ceca9-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ceca9-105">**Applies to:**</span></span>

- <span data-ttu-id="ceca9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceca9-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ceca9-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ceca9-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ceca9-109">Microsoft 365 Defender 준비된 플랫폼을 토대하여 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="ceca9-110">이 Microsoft 365 Defender API를 사용하여 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="ceca9-111">**[결합된](api-incident.md)** 인시던트 큐 - 인시던트 API에서 전체 공격 범위 및 영향을 미치는 모든 자산을 그룹화하여 중요한 일에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="ceca9-112">**[제품](api-advanced-hunting.md)** 간 위협 헌팅 - 여러 보호 제품에서 수집된 원시 데이터를 분산하기 위해 사용자 지정 쿼리를 만들어 보안 팀의 조직 지식을 활용하여 손상 징후를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="ceca9-113">Streaming [API를](../defender-endpoint/raw-data-export.md) 사용하여 단일 데이터 스트림 내에서 발생하는 실시간 이벤트 및 인스턴스의 경고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="ceca9-114">이러한 Microsoft 365 Defender 특정 API와 함께 다른 각 보안 제품은 고유한 [](api-articles.md) 기능을 활용하는 데 도움이 되는 추가 API를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="ceca9-115">통합 포털로 전환하면 끝점 API용 Microsoft Defender를 기반으로 하는 PowerBi 대시보드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="ceca9-116">대화형 포털 전환에 관계없이 기존 API를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceca9-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="ceca9-117">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ceca9-117">Learn more</span></span>

| <span data-ttu-id="ceca9-118">**API 액세스 방법 이해**</span><span class="sxs-lookup"><span data-stu-id="ceca9-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="ceca9-119">API 할당량 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="ceca9-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="ceca9-120">MICROSOFT 365 DEFENDER API에 액세스</span><span class="sxs-lookup"><span data-stu-id="ceca9-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="ceca9-121">**앱 빌드**</span><span class="sxs-lookup"><span data-stu-id="ceca9-121">**Build apps**</span></span> |
| [<span data-ttu-id="ceca9-122">'Hello world' 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ceca9-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="ceca9-123">사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ceca9-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="ceca9-124">사용자가 없는 앱에 액세스하는 Microsoft 365 Defender 만들기</span><span class="sxs-lookup"><span data-stu-id="ceca9-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="ceca9-125">다중 테넌트 파트너가 액세스하여 테넌트 API에 Microsoft 365 Defender 만들기</span><span class="sxs-lookup"><span data-stu-id="ceca9-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="ceca9-126">**앱 문제 해결 및 유지 관리**</span><span class="sxs-lookup"><span data-stu-id="ceca9-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="ceca9-127">API 오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="ceca9-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="ceca9-128">Azure Key Vault를 사용하여 앱에서 비밀 관리</span><span class="sxs-lookup"><span data-stu-id="ceca9-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="ceca9-129">사용자 로그인에 대한 OAuth 2.0 권한 부여 구현</span><span class="sxs-lookup"><span data-stu-id="ceca9-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |