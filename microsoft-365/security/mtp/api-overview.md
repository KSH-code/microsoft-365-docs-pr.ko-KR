---
title: Microsoft 365 Defender API 개요
description: Microsoft 365 Defender에서 사용 가능한 API에 대해 자세히 알아보기
keywords: api, api, 개요, 인시던트, 인시던트, 위협 헌팅, Microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931005"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="a2b9d-104">Microsoft 365 Defender API 개요</span><span class="sxs-lookup"><span data-stu-id="a2b9d-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a2b9d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a2b9d-105">**Applies to:**</span></span>

- <span data-ttu-id="a2b9d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2b9d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2b9d-107">일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 판매된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b9d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a2b9d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a2b9d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a2b9d-109">Microsoft 365 Defender는 통합 준비가 완료된 플랫폼을 토대로 구축되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b9d-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="a2b9d-110">Microsoft 365 Defender API를 사용하여 공유 인시던트 및 고급 헌팅 테이블을 기반으로 워크플로를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b9d-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="a2b9d-111">**[결합된 인시던트 큐](api-incident.md)** - 인시던트 API에서 전체 공격 범위와 영향을 미치는 모든 자산을 함께 그룹화하여 중요한 일에 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b9d-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="a2b9d-112">**[제품](api-advanced-hunting.md)** 간 위협 헌팅 - 보안 팀의 조직 지식을 활용하여 사용자 지정 쿼리를 만들어 여러 보호 제품에서 수집된 원시 데이터를 시차를 두어 손상 징후를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b9d-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="a2b9d-113">이러한 Microsoft 365 Defender 관련 API와 함께 다른 각 보안 제품은 고유한 기능을 활용하는 데 도움이 되는 추가 [API를](api-articles.md) 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b9d-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="a2b9d-114">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a2b9d-114">Learn more</span></span>

| <span data-ttu-id="a2b9d-115">**API 액세스 방법 이해**</span><span class="sxs-lookup"><span data-stu-id="a2b9d-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="a2b9d-116">API 할당량 및 라이선싱에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="a2b9d-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="a2b9d-117">Microsoft 365 Defender API 액세스</span><span class="sxs-lookup"><span data-stu-id="a2b9d-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="a2b9d-118">**앱 빌드**</span><span class="sxs-lookup"><span data-stu-id="a2b9d-118">**Build apps**</span></span> |
| [<span data-ttu-id="a2b9d-119">'Hello world' 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a2b9d-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="a2b9d-120">사용자를 대신하여 Microsoft 365 Defender API에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a2b9d-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="a2b9d-121">사용자 없이 Microsoft 365 Defender에 액세스하는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a2b9d-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="a2b9d-122">Microsoft 365 Defender API에 대한 다중 테넌트 파트너 액세스가 있는 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a2b9d-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="a2b9d-123">**앱 문제 해결 및 유지 관리**</span><span class="sxs-lookup"><span data-stu-id="a2b9d-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="a2b9d-124">API 오류 코드 이해</span><span class="sxs-lookup"><span data-stu-id="a2b9d-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="a2b9d-125">Azure Key Vault를 사용하여 앱에서 비밀 관리</span><span class="sxs-lookup"><span data-stu-id="a2b9d-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="a2b9d-126">사용자 로그인에 대한 OAuth 2.0 권한 부여 구현</span><span class="sxs-lookup"><span data-stu-id="a2b9d-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
