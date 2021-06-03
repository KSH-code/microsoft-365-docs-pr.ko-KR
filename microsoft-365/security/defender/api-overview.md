---
title: Defender Microsoft 365 개요
description: Defender에서 사용 가능한 API에 Microsoft 365
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
ms.openlocfilehash: b19a6072be5f97b90c117f053ccae4593587c43d
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730899"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="4dea6-104">Defender Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="4dea6-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4dea6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4dea6-105">**Applies to:**</span></span>

- <span data-ttu-id="4dea6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4dea6-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4dea6-107">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4dea6-108">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4dea6-109">Microsoft 365 Defender는 통합 준비가 된 플랫폼을 토로합니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="4dea6-110">Microsoft 365 Defender API를 사용하여 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="4dea6-111">**[결합된](api-incident.md)** 인시던트 큐 - 인시던트 API에서 전체 공격 범위 및 영향을 미치는 모든 자산을 그룹화하여 중요한 일에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="4dea6-112">**[제품](api-advanced-hunting.md)** 간 위협 헌팅 - 여러 보호 제품에서 수집된 원시 데이터를 분산하기 위해 사용자 지정 쿼리를 만들어 보안 팀의 조직 지식을 활용하여 손상 징후를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="4dea6-113">Streaming [API를](../defender-endpoint/raw-data-export.md) 사용하여 단일 데이터 스트림 내에서 발생하는 실시간 이벤트 및 인스턴스의 경고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="4dea6-114">이러한 Microsoft 365 Defender 관련 API와 함께, 다른 각 보안 제품은 [](api-articles.md) 고유한 기능을 활용하는 데 도움이 되는 추가 API를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="4dea6-115">통합 포털로 전환하면 끝점 API용 Microsoft Defender를 기반으로 하는 PowerBi 대시보드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="4dea6-116">대화형 포털 전환에 관계없이 기존 API를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dea6-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="4dea6-117">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4dea6-117">Learn more</span></span>

| <span data-ttu-id="4dea6-118">**API 액세스 방법 이해**</span><span class="sxs-lookup"><span data-stu-id="4dea6-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="4dea6-119">API 할당량 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="4dea6-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="4dea6-120">Microsoft 365 Defender API에 액세스</span><span class="sxs-lookup"><span data-stu-id="4dea6-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="4dea6-121">**앱 빌드**</span><span class="sxs-lookup"><span data-stu-id="4dea6-121">**Build apps**</span></span> |
| [<span data-ttu-id="4dea6-122">'Hello world' 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="4dea6-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="4dea6-123">사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="4dea6-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="4dea6-124">사용자 없이 Microsoft 365 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="4dea6-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="4dea6-125">다중 테넌트 파트너 액세스 권한이 있는 앱 만들기Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="4dea6-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="4dea6-126">**앱 문제 해결 및 유지 관리**</span><span class="sxs-lookup"><span data-stu-id="4dea6-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="4dea6-127">API 오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="4dea6-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="4dea6-128">Azure Key Vault를 사용하여 앱에서 비밀 관리</span><span class="sxs-lookup"><span data-stu-id="4dea6-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="4dea6-129">사용자 로그인에 대한 OAuth 2.0 권한 부여 구현</span><span class="sxs-lookup"><span data-stu-id="4dea6-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |