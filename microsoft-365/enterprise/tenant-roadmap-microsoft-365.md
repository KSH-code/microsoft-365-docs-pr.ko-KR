---
title: 테넌트에 대한 Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 테넌트에 대한 테넌트 설정 로드맵을 Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909457"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="0f7b9-103">테넌트에 대한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f7b9-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="0f7b9-104">사용자 Microsoft 365 테넌트는 조직에 할당된 서비스 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="0f7b9-105">일반적으로 이 테넌트는 공용 DNS 도메인 이름 중 하나 이상과 연결되고, 사용자 계정에 할당한 여러 구독 및 해당 구독 내의 라이선스에 대한 중앙 및 격리된 컨테이너 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="0f7b9-106">자세한 내용은 Microsoft 클라우드 서비스 구독, 라이선스, 계정 및 [테넌트 를 참조하세요.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="0f7b9-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="0f7b9-107">테넌트 Microsoft 365 특정 지리적 위치에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="0f7b9-108">여러 지리적 위치가 있는 테넌트가 있을 수도 있으며 테넌트는 한 위치에서 다른 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="0f7b9-109">테넌트가 사용자, 그룹, 라이선스 및 클라우드 앱을 사용할 수 있도록 준비하려면 테넌트 구성을 신중하게 계획하고 실행하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="0f7b9-110">테넌트 Microsoft 365 설정</span><span class="sxs-lookup"><span data-stu-id="0f7b9-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="0f7b9-111">네트워킹이 Microsoft 365 및 원격 작업자 모두에 대한 액세스에 최적화된 경우 다음 큰 작업은 DNS 도메인 이름, 일반 서비스 및 보안 사용자 로그인을 지원하는 해당 ID 인프라에 대한 Microsoft 365 테넌트에 대한 계획 및 구성을 계획하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="0f7b9-112">계획</span><span class="sxs-lookup"><span data-stu-id="0f7b9-112">Plan</span></span>

<span data-ttu-id="0f7b9-113">테넌트 구현을 계획하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="0f7b9-114">구독, 라이선스 및 Azure AD(Azure Active Directory) 테넌트 이해</span><span class="sxs-lookup"><span data-stu-id="0f7b9-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="0f7b9-115">타사 SSL 인증서 사용 방법 이해</span><span class="sxs-lookup"><span data-stu-id="0f7b9-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="0f7b9-116">테넌트가 Azure AD Microsoft 365 통합되는 방식 이해</span><span class="sxs-lookup"><span data-stu-id="0f7b9-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="0f7b9-117">클라이언트 앱 지원 계획</span><span class="sxs-lookup"><span data-stu-id="0f7b9-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="0f7b9-118">하이브리드 최신 인증 사용 방법 결정</span><span class="sxs-lookup"><span data-stu-id="0f7b9-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="0f7b9-119">Office 2007 및 Office 업그레이드 계획</span><span class="sxs-lookup"><span data-stu-id="0f7b9-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="0f7b9-120">테넌트 고리 이해</span><span class="sxs-lookup"><span data-stu-id="0f7b9-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="0f7b9-121">배포</span><span class="sxs-lookup"><span data-stu-id="0f7b9-121">Deploy</span></span>

<span data-ttu-id="0f7b9-122">테넌트 배포:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="0f7b9-123">조직의 [DNS](../admin/setup/add-domain.md) 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="0f7b9-124">Microsoft 365 관리 [센터의 설정 가이드를 사용하세요.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="0f7b9-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="0f7b9-125">ID 인프라를 [구축하고](identity-roadmap-microsoft-365.md) [사용자 로그인을 보호합니다.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="0f7b9-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="0f7b9-126">테넌트의 지리적 위치 이동</span><span class="sxs-lookup"><span data-stu-id="0f7b9-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="0f7b9-127">Microsoft는 계속해서 서비스용 새 데이터 센터 지리적 위치(지리적 위치)를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="0f7b9-128">이러한 새로운 데이터 센터 지역은 고객 요구 및 사용 증가를 지원하기 위해 용량 및 계산 리소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="0f7b9-129">또한 새 데이터 센터 지역은 핵심 고객 데이터에 대한 지역 내 데이터 레지스터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="0f7b9-130">자세한 내용은 핵심 데이터를 새 데이터 센터 지역으로 [Microsoft 365 이동을 참조하세요.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="0f7b9-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="0f7b9-131">Multi-Microsoft 365 배포</span><span class="sxs-lookup"><span data-stu-id="0f7b9-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="0f7b9-132">Microsoft 365 Multi-Geo를 사용하면 Microsoft 365 범위를 기존 테넌트 내 여러 지리적 지역 및 / 또는 국가로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="0f7b9-133">자세한 내용은 [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="0f7b9-134">여러 Microsoft 365 테넌트 관리</span><span class="sxs-lookup"><span data-stu-id="0f7b9-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="0f7b9-135">조직에 단일 테넌트가 있는 것이 이상적이기는 하지만 여러 테넌트가 있는 많은 조직 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="0f7b9-136">인수 합병, 관리적 고리 사용, 분산된 IT 등 다양한 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="0f7b9-137">테넌트가 여러 개인 Microsoft 365 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="0f7b9-138">테넌트 간 공동 작업</span><span class="sxs-lookup"><span data-stu-id="0f7b9-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="0f7b9-139">교차 테넌트 사서함 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0f7b9-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="0f7b9-140">테넌트 간 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0f7b9-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="0f7b9-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0f7b9-141">Next step</span></span>

<span data-ttu-id="0f7b9-142">[구독, 라이선스,](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)계정 및 테넌트로 테넌트 계획을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>