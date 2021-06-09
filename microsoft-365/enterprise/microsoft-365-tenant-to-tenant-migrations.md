---
title: Microsoft 365 테넌트 마이그레이션
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
description: 테넌트에서 마이그레이션하는 Microsoft 365 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819717"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="13a28-103">Microsoft 365 테넌트 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="13a28-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="13a28-104">합병, 인수, 매입 및 기타 시나리오에 대한 아키텍처 접근 방식이 여러 가지 있으며, 이 경우 기존 Microsoft 365 테넌트를 새 테넌트로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a28-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="13a28-105">대부분의 고객은 타사 도구를 사용하여 콘텐츠를 마이그레이션하는 등 Microsoft 컨설팅 서비스 또는 Microsoft 파트너와 협력하여 테넌트 마이그레이션을 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="13a28-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="13a28-106">테넌트 대 [테넌트](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 마이그레이션 아키텍처 모델을 사용하여 테넌트 Microsoft 365 마이그레이션을 계획하는 방법과 마이그레이션 단계를 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a28-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="13a28-107">[![테넌트와 테넌트 마이그레이션 모델](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="13a28-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="13a28-108">이 모델을 PDF 형식으로 [다운로드하여](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 편지형, 법률형 또는 타블로이드(11 x 17) 크기 용지에 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="13a28-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="13a28-109">이 모델은 다음에 대한 섹션을 사용하여 계획하기 위한 지침과 시작 지점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13a28-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="13a28-110">비즈니스 시나리오를 아키텍처 접근 방식에 매핑</span><span class="sxs-lookup"><span data-stu-id="13a28-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="13a28-111">디자인 고려 사항</span><span class="sxs-lookup"><span data-stu-id="13a28-111">Design considerations</span></span>

<span data-ttu-id="13a28-112">이 모델에는 다음에 대한 자세한 예제도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a28-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="13a28-113">단일 이벤트 마이그레이션 흐름</span><span class="sxs-lookup"><span data-stu-id="13a28-113">A single event migration flow</span></span>
- <span data-ttu-id="13a28-114">단계적 마이그레이션 흐름</span><span class="sxs-lookup"><span data-stu-id="13a28-114">A phased migration flow</span></span>
- <span data-ttu-id="13a28-115">테넌트 이동 또는 분할 흐름</span><span class="sxs-lookup"><span data-stu-id="13a28-115">A tenant move or split flow</span></span>
