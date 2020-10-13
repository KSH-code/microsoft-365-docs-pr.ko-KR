---
title: Microsoft 365에 대 한 테 넌 트 로드맵
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Microsoft 365에 대 한 테 넌 트를 설정 하기 위한 로드맵
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446010"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="f7241-103">Microsoft 365에 대 한 테 넌 트 로드맵</span><span class="sxs-lookup"><span data-stu-id="f7241-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="f7241-104">Microsoft 365 테 넌 트가 조직에 할당 된 서비스 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="f7241-105">일반적으로이 테 넌 트는 하나 이상의 DNS 도메인 이름과 연결 되어 있으며 사용자 계정에 할당 하는 다른 구독 및 라이선스 내의 중앙 컨테이너 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="f7241-106">Microsoft 365 테 넌 트를 만들 때이를 특정 지리적 위치에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="f7241-107">여러 지리적 위치를 사용 하 여 테 넌 트를 만들고 테 넌 트를 한 위치에서 다른 위치로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="f7241-108">네트워킹 및 id의 기본 서비스에 대 한 테 넌 트를 준비 하려면 테 넌 트 구성을 신중 하 게 계획 하 고 실행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="f7241-109">계획</span><span class="sxs-lookup"><span data-stu-id="f7241-109">Plan</span></span>

<span data-ttu-id="f7241-110">다음을 수행 하 여 테 넌 트 구현을 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="f7241-111">구독, 라이선스 및 Azure AD (Active Directory) 테 넌 트 이해</span><span class="sxs-lookup"><span data-stu-id="f7241-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="f7241-112">타사 SSL 인증서 사용 방법 이해</span><span class="sxs-lookup"><span data-stu-id="f7241-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="f7241-113">Microsoft 365 테 넌 트가 Azure AD services와 통합 되는 방식 이해</span><span class="sxs-lookup"><span data-stu-id="f7241-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="f7241-114">클라이언트 앱 지원 계획</span><span class="sxs-lookup"><span data-stu-id="f7241-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="f7241-115">하이브리드 최신 인증을 사용 하는 방법 결정</span><span class="sxs-lookup"><span data-stu-id="f7241-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="f7241-116">Office 2007 및 Office 2010 업그레이드 계획</span><span class="sxs-lookup"><span data-stu-id="f7241-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="f7241-117">테 넌 트 격리 이해</span><span class="sxs-lookup"><span data-stu-id="f7241-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="f7241-118">Microsoft 365 서비스 보증에 대 한 세부 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="f7241-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="f7241-119">배포</span><span class="sxs-lookup"><span data-stu-id="f7241-119">Deploy</span></span>

<span data-ttu-id="f7241-120">테 넌 트를 배포 하려면 조직의 [DNS 도메인을 추가](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 하 고 [Microsoft 365 관리 센터에서 설치 가이드](setup-guides-for-microsoft-365.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="f7241-121">여러 지리적 위치가 있는 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="f7241-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="f7241-122">Microsoft 365 Multi-Geo를 사용하면 Microsoft 365 범위를 기존 테넌트 내 여러 지리적 지역 및 / 또는 국가로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="f7241-123">이를 계획, 구성 및 관리 하는 방법을 포함 하 여 Microsoft 365 다중 위치에 대 한 자세한 내용은 [여기에서 시작](microsoft-365-multi-geo.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="f7241-124">테 넌 트의 지리적 위치 이동</span><span class="sxs-lookup"><span data-stu-id="f7241-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="f7241-125">Microsoft는 Microsoft 365 서비스에 대 한 새로운 데이터 센터 지리적 위치 (geos)를 계속 해 서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="f7241-126">이러한 새 데이터 센터 지역는 고객 요구 및 사용 증가를 지원 하기 위해 용량을 추가 하 고 리소스를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="f7241-127">또한 새 데이터 센터 지역는 핵심 고객 데이터에 대 한 상주 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="f7241-128">지리적 데이터 이동을 요청 하는 방법을 포함 하 여 Microsoft 365 데이터 센터 geo에 대 한 자세한 내용은 [여기에서 시작](moving-data-to-new-datacenter-geos.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="f7241-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f7241-129">Next step</span></span>

<span data-ttu-id="f7241-130">[구독, 라이선스, 계정, 테](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)넌 트를 사용 하 여 테 넌 트 계획을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7241-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

