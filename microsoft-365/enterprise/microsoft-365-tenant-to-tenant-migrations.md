---
title: Microsoft 365 테 넌 트 간 마이그레이션
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Microsoft 365 테 넌 트를 마이그레이션하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17aabbd945c6dec699384eb9f203029255ae62f6
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447153"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="3ec58-103">Microsoft 365 테 넌 트 간 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3ec58-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="3ec58-104">기존 Microsoft 365 테 넌 트를 새 테 넌 트로 마이그레이션하는 데 사용할 수 있는 합병, 인수, divestitures 및 기타 시나리오를 위한 몇 가지 아키텍처 방식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec58-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="3ec58-105">대부분의 고객은 Microsoft 컨설팅 서비스 또는 Microsoft 파트너와 협력 하 여 타사 도구를 사용 하 여 콘텐츠를 마이그레이션하는 작업을 비롯 한 테 넌 트를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec58-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="3ec58-106">테 넌 트 [마이그레이션 아키텍처 모델](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) 을 사용 하 여 Microsoft 365 테 넌 트 간 마이그레이션 및 마이그레이션 단계를 계획 하는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec58-106">Use the [Tenant-to-tenant migration architecture model](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="3ec58-107">[![테 넌 트 마이그레이션 모델](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="3ec58-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="3ec58-108">또한이 모델을 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) 또는 [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) 형식으로 다운로드 하 여 letter, legal 또는 tabloid (11 x 17) 크기 용지에 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec58-108">You can also download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) or [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="3ec58-109">이 모델에서는 다음에 대 한 섹션을 사용 하 여 계획 하는 지침 및 시작 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec58-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="3ec58-110">비즈니스 시나리오를 아키텍처 접근 방식으로 매핑</span><span class="sxs-lookup"><span data-stu-id="3ec58-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="3ec58-111">디자인 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3ec58-111">Design considerations</span></span>

<span data-ttu-id="3ec58-112">이 모델에는 다음과 같은 자세한 예제도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec58-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="3ec58-113">단일 이벤트 마이그레이션 흐름</span><span class="sxs-lookup"><span data-stu-id="3ec58-113">A single event migration flow</span></span>
- <span data-ttu-id="3ec58-114">단계별 마이그레이션 흐름</span><span class="sxs-lookup"><span data-stu-id="3ec58-114">A phased migration flow</span></span>
- <span data-ttu-id="3ec58-115">테 넌 트 이동 또는 분할 흐름</span><span class="sxs-lookup"><span data-stu-id="3ec58-115">A tenant move or split flow</span></span>
