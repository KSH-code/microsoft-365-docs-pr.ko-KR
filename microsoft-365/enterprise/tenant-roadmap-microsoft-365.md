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
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656010"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="dc335-103">Microsoft 365에 대 한 테 넌 트 로드맵</span><span class="sxs-lookup"><span data-stu-id="dc335-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="dc335-104">Microsoft 365 테 넌 트가 조직에 할당 된 서비스 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="dc335-105">일반적으로이 테 넌 트는 하나 이상의 DNS 도메인 이름과 연결 되어 있으며 사용자 계정에 할당 하는 다른 구독 및 라이선스 내의 중앙 컨테이너 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="dc335-106">자세한 내용은 [구독, 라이선스, 계정 및 Microsoft 클라우드 서비스에 대 한 테 넌 트](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc335-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="dc335-107">Microsoft 365 테 넌 트를 만들 때이를 특정 지리적 위치에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="dc335-108">여러 지리적 위치를 사용 하 여 테 넌 트를 만들고 테 넌 트를 한 위치에서 다른 위치로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="dc335-109">테 넌 트를 id로 준비 하려면 테 넌 트 구성을 신중 하 게 계획 하 고 실행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="dc335-110">Microsoft 365 테 넌 트 설정</span><span class="sxs-lookup"><span data-stu-id="dc335-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="dc335-111">사용자가 온-프레미스 및 원격 작업자 모두에 대해 Microsoft 365에 액세스할 수 있도록 네트워킹을 최적화 한 후에는 다음 대규모 작업에서 DNS 도메인 이름, 일반 서비스 및 보안 사용자 로그인을 지 원하는 해당 id 인프라에 대 한 Microsoft 365 테 넌 트를 계획 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="dc335-112">계획</span><span class="sxs-lookup"><span data-stu-id="dc335-112">Plan</span></span>

<span data-ttu-id="dc335-113">다음을 수행 하 여 테 넌 트 구현을 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="dc335-114">구독, 라이선스 및 Azure AD (Active Directory) 테 넌 트 이해</span><span class="sxs-lookup"><span data-stu-id="dc335-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="dc335-115">타사 SSL 인증서 사용 방법 이해</span><span class="sxs-lookup"><span data-stu-id="dc335-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="dc335-116">Microsoft 365 테 넌 트가 Azure AD services와 통합 되는 방식 이해</span><span class="sxs-lookup"><span data-stu-id="dc335-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="dc335-117">클라이언트 앱 지원 계획</span><span class="sxs-lookup"><span data-stu-id="dc335-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="dc335-118">하이브리드 최신 인증을 사용 하는 방법 결정</span><span class="sxs-lookup"><span data-stu-id="dc335-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="dc335-119">Office 2007 및 Office 2010 업그레이드 계획</span><span class="sxs-lookup"><span data-stu-id="dc335-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="dc335-120">테 넌 트 격리 이해</span><span class="sxs-lookup"><span data-stu-id="dc335-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="dc335-121">Microsoft 365 서비스 보증에 대 한 세부 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="dc335-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="dc335-122">배포</span><span class="sxs-lookup"><span data-stu-id="dc335-122">Deploy</span></span>

<span data-ttu-id="dc335-123">테 넌 트를 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="dc335-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="dc335-124">조직의 [DNS 도메인](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="dc335-125">[Microsoft 365 관리 센터의 설치 가이드](setup-guides-for-microsoft-365.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="dc335-126">[Id 인프라](identity-roadmap-microsoft-365.md) 를 구축 하 고 [사용자 로그인을 보호](microsoft-365-secure-sign-in.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="dc335-127">테 넌 트의 지리적 위치 이동</span><span class="sxs-lookup"><span data-stu-id="dc335-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="dc335-128">Microsoft는 Microsoft 365 서비스에 대 한 새로운 데이터 센터 지리적 위치 (geos)를 계속 해 서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="dc335-129">이러한 새 데이터 센터 지역는 고객 요구 및 사용 증가를 지원 하기 위해 용량을 추가 하 고 리소스를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="dc335-130">또한 새 데이터 센터 지역는 핵심 고객 데이터에 대 한 상주 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="dc335-131">자세한 내용은 [핵심 데이터를 새로운 Microsoft 365 datacenter 지역로 이동을](moving-data-to-new-datacenter-geos.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc335-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="dc335-132">Microsoft 365 다중 지역 배포</span><span class="sxs-lookup"><span data-stu-id="dc335-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="dc335-133">Microsoft 365 Multi-Geo를 사용하면 Microsoft 365 범위를 기존 테넌트 내 여러 지리적 지역 및 / 또는 국가로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="dc335-134">자세한 내용은 [Microsoft 365 다중 Geo](microsoft-365-multi-geo.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc335-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="dc335-135">여러 Microsoft 365 테 넌 트 관리</span><span class="sxs-lookup"><span data-stu-id="dc335-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="dc335-136">Oganization에 대해 테 넌 트를 하나만 유지 하는 것이 이상적인 경우에도 여러 개의 테 넌 트가 있는 여러 조직 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="dc335-137">여러 테 넌 트에 대 한 합병 및 합병, 관리 격리가 필요한 경우 또는이를 분산 시킨 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="dc335-138">Microsoft 365 테 넌 트 여러 개 있는 경우 다음 문서에서 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc335-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="dc335-139">테넌트 간 공동 작업</span><span class="sxs-lookup"><span data-stu-id="dc335-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="dc335-140">교차 테넌트 사서함 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dc335-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="dc335-141">테넌트 간 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dc335-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="dc335-142">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dc335-142">Next step</span></span>

<span data-ttu-id="dc335-143">[구독, 라이선스, 계정, 테](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)넌 트를 사용 하 여 테 넌 트 계획을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc335-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
