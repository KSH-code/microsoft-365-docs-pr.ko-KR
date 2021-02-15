---
title: Microsoft 365 테넌트와 테넌트 마이그레이션
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
description: Microsoft 365 테넌트 마이그레이션 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17aabbd945c6dec699384eb9f203029255ae62f6
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447153"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="5855d-103">Microsoft 365 테넌트와 테넌트 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="5855d-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="5855d-104">합병, 인수, 매입 및 기존 Microsoft 365 테넌트를 새 테넌트로 마이그레이션할 수 있는 기타 시나리오에 대한 몇 가지 아키텍처 접근 방식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5855d-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="5855d-105">대부분의 고객은 타사 도구를 사용하여 콘텐츠를 마이그레이션하는 등 Microsoft Consulting Services 또는 Microsoft 파트너와 함께 테넌트 마이그레이션을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5855d-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="5855d-106">테넌트 [대 테넌트](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) 마이그레이션 아키텍처 모델을 사용하여 Microsoft 365 테넌트-테넌트 마이그레이션을 계획하는 방법과 마이그레이션 단계를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="5855d-106">Use the [Tenant-to-tenant migration architecture model](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="5855d-107">[![테넌트와 테넌트 마이그레이션 모델](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="5855d-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="5855d-108">이 모델을 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) 또는 [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) 형식으로 다운로드하여 편지, 법률 또는 타블로이드(11 x 17) 크기 용지에 인쇄할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5855d-108">You can also download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) or [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="5855d-109">이 모델은 다음에 대한 섹션을 사용하여 계획하기 위한 지침과 시작점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5855d-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="5855d-110">아키텍처 접근 방식에 대한 비즈니스 시나리오 매핑</span><span class="sxs-lookup"><span data-stu-id="5855d-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="5855d-111">디자인 고려 사항</span><span class="sxs-lookup"><span data-stu-id="5855d-111">Design considerations</span></span>

<span data-ttu-id="5855d-112">이 모델에는 다음에 대한 자세한 예제도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5855d-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="5855d-113">단일 이벤트 마이그레이션 흐름</span><span class="sxs-lookup"><span data-stu-id="5855d-113">A single event migration flow</span></span>
- <span data-ttu-id="5855d-114">단계적 마이그레이션 흐름</span><span class="sxs-lookup"><span data-stu-id="5855d-114">A phased migration flow</span></span>
- <span data-ttu-id="5855d-115">테넌트 이동 또는 분할 흐름</span><span class="sxs-lookup"><span data-stu-id="5855d-115">A tenant move or split flow</span></span>
