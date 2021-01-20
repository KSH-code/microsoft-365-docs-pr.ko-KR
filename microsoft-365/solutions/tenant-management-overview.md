---
title: 엔터프라이즈용 Microsoft 365 테넌트 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 테넌트의 계획, 배포 및 지속적인 작업에 대한 개요입니다.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908765"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a><span data-ttu-id="c3f1c-103">엔터프라이즈용 Microsoft 365 테넌트 관리</span><span class="sxs-lookup"><span data-stu-id="c3f1c-103">Tenant management for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="c3f1c-104">클라우드 컴퓨팅을 사용하여 조직의 디지털 혁신 경로를 만들려면 작업자가 생산성, 공동 작업, 성능, 개인 정보 보호, 규정 준수 및 보안을 사용할 수 있는 확고한 기반을 마련해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-104">Creating a path to your organization's digital transformation with cloud computing requires a firm foundation upon which your workers can rely for productivity, collaboration, performance, privacy, compliance, and security.</span></span>

<span data-ttu-id="c3f1c-105">Microsoft 365 테넌트의 올바른 구성은 이러한 기반을 제공하며, 직원들은 업무를 완료하는 데 집중하고 IT 부서는 추가 비즈니스 가치를 제공하는 종단식 솔루션에 집중할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-105">Correct configuration of your Microsoft 365 tenants provides that foundation, leaving your workers to focus on getting their work done and your IT department to focus on end-to-end solutions that provide additional business value.</span></span> 

<span data-ttu-id="c3f1c-106">이 솔루션은 다음 단계에서 해당 기초의 구성을 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-106">This solution takes you through the configuration of that foundation in these steps:</span></span>

1. <span data-ttu-id="c3f1c-107">테넌트 결정</span><span class="sxs-lookup"><span data-stu-id="c3f1c-107">Determine your tenants</span></span>
2. <span data-ttu-id="c3f1c-108">네트워킹 최적화</span><span class="sxs-lookup"><span data-stu-id="c3f1c-108">Optimize your networking</span></span>
3. <span data-ttu-id="c3f1c-109">ID 동기화 및 보안 로그인 적용</span><span class="sxs-lookup"><span data-stu-id="c3f1c-109">Synchronize your identities and enforce secure sign-ins</span></span>
4. <span data-ttu-id="c3f1c-110">Windows 장치, Office 클라이언트 및온-프레미스 Office 서버 및 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c3f1c-110">Migrate your Windows devices, Office clients, and on-premises Office servers and data</span></span>
5. <span data-ttu-id="c3f1c-111">장치 및 앱 관리 배포</span><span class="sxs-lookup"><span data-stu-id="c3f1c-111">Deploy device and app management</span></span>

<span data-ttu-id="c3f1c-112">그러나 먼저 테넌트가 무엇일지, 그리고 확고한 기반을 제공하는 테넌트의 모양을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-112">But first, let's take a moment to understand what a tenant is and what a tenant that provides a firm foundation looks like.</span></span>

## <a name="a-microsoft-365-tenant-defined"></a><span data-ttu-id="c3f1c-113">정의된 Microsoft 365 테넌트</span><span class="sxs-lookup"><span data-stu-id="c3f1c-113">A Microsoft 365 tenant defined</span></span>

<span data-ttu-id="c3f1c-114">Microsoft 365 테넌트는 Microsoft 365 서비스 및 유럽 또는 북미와 같은 특정 기본 위치에 저장된 조직 데이터의 전용 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-114">A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America.</span></span> <span data-ttu-id="c3f1c-115">이 위치는 조직에 대한 테넌트를 만들 때 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-115">This location is specified when you create the tenant for your organization.</span></span> <span data-ttu-id="c3f1c-116">각 Microsoft 365 테넌트는 다른 모든 Microsoft 365 테넌트와는 고유하며 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-116">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="c3f1c-117">Microsoft 365 E3 또는 E5와 같은 Microsoft에서 하나 이상의 제품(예: Microsoft 365 E3 및 각 제품에 대한 라이선스 집합)을 구매할 때 Microsoft 365 테넌트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-117">You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.</span></span>

<span data-ttu-id="c3f1c-118">Microsoft 365 테넌트에는 사용자 계정, 그룹 및 기타 개체에 대한 Azure AD 전용 인스턴스인 Azure AD(Azure Active Directory) 테넌트도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-118">Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects.</span></span> <span data-ttu-id="c3f1c-119">각 Azure AD 테넌트는 다른 모든 Azure AD 테넌트와는 고유하며 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-119">Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.</span></span> <span data-ttu-id="c3f1c-120">조직에 Azure 구독으로 설정할 수 있는 여러 Azure AD 테넌트가 있을 수 있는 반면, Microsoft 365 테넌트는 테넌트 생성 시 만들어진 하나의 Azure AD 테넌트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-120">While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.</span></span> 

<span data-ttu-id="c3f1c-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-121">Here is an example:</span></span>

![Azure AD 테넌트가 있는 Microsoft 365 테넌트의 예](../media/tenant-management-overview/tenant-management-example-tenant.png)

<span data-ttu-id="c3f1c-123">*테넌트 관리는* Microsoft 365 테넌트의 계획, 배포 및 지속적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-123">*Tenant management* is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.</span></span> 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a><span data-ttu-id="c3f1c-124">잘 디자인 및 운영하는 테넌트의 특성</span><span class="sxs-lookup"><span data-stu-id="c3f1c-124">Attributes of a well-designed and operating tenant</span></span>

<span data-ttu-id="c3f1c-125">테넌트의 올바른 이름과 위치 이외에 Microsoft Teams 및 Exchange Online과 같은 클라우드 생산성 앱에 대한 사용자 환경이 효과적이고 안전하며, 효율적인지 보장하기 위해 계획, 배포 및 관리할 수 있는 추가 요소가 &mdash; &mdash; 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-125">Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps&mdash;such as Microsoft Teams and Exchange Online&mdash;are effective, secure, and performant.</span></span>

<span data-ttu-id="c3f1c-126">요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-126">Here are the elements:</span></span>

- <span data-ttu-id="c3f1c-127">올바른 제품(구독) 및 라이선스 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-127">You have the correct set of products (subscriptions) and licenses.</span></span>
  - <span data-ttu-id="c3f1c-128">제품 집합은 비즈니스, IT 및 보안 요구와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-128">The set of products match your business, IT, and security needs.</span></span>
  - <span data-ttu-id="c3f1c-129">직원에게 적절한 수의 라이선스가 있으며 직원의 예상 인원 변경이 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-129">There is an adequate number of licenses for your workers and anticipated changes in staffing.</span></span>
- <span data-ttu-id="c3f1c-130">네트워킹의 경우:</span><span class="sxs-lookup"><span data-stu-id="c3f1c-130">For networking:</span></span>
  - <span data-ttu-id="c3f1c-131">올바른 DNS 도메인 이름을 구성한 경우</span><span class="sxs-lookup"><span data-stu-id="c3f1c-131">You have configured the correct DNS domain names.</span></span>
  - <span data-ttu-id="c3f1c-132">엔터프라이즈 네트워크의 경우, Microsoft 네트워크에 대한 네트워크 트래픽을 인사이트 작업자를 위해 최적화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-132">For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.</span></span>
  - <span data-ttu-id="c3f1c-133">VPN 클라이언트를 사용하는 원격 작업자를 위해 네트워크 트래픽을 최적화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-133">You have optimized network traffic for remote workers who are using a VPN client.</span></span>
- <span data-ttu-id="c3f1c-134">AD DS(Active Directory 도메인 서비스) 계정, 그룹 및 기타 개체를 동기화했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-134">You have synchronized your Active Directory Domain Services (AD DS) accounts, groups, and other objects.</span></span>
  - <span data-ttu-id="c3f1c-135">Azure AD 테넌트 계정은 전자 메일 주소에 대한 올바른 DNS 도메인을 사용하여 Exchange Online 사서함에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-135">Your Azure AD tenant accounts are mapped to Exchange Online mailboxes with the correct DNS domains for email addresses.</span></span>
  - <span data-ttu-id="c3f1c-136">사용자 계정에 올바른 구매 제품(예: Microsoft 365 E3 또는 E5)에서 올바른 라이선스가 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-136">Your user accounts have been assigned the correct licenses from the correct purchased products (such as Microsoft 365 E3 or E5).</span></span>
- <span data-ttu-id="c3f1c-137">강력한 ID 및 액세스 관리를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-137">You have configured strong identity and access management.</span></span>
  - <span data-ttu-id="c3f1c-138">암호 없는 또는 MFA(다단계 인증)를 사용하여 보안 사용자 로그인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-138">You are requiring secure user sign-in with passwordless or multi-factor authentication (MFA).</span></span>
  - <span data-ttu-id="c3f1c-139">더 높은 수준의 보안을 위해 로그인 요구 사항 및 제한을 적용하는 조건부 액세스 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-139">You have Conditional Access policies that enforce sign-in requirements and restrictions for higher levels of security.</span></span>
- <span data-ttu-id="c3f1c-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span></span>
- <span data-ttu-id="c3f1c-141">Microsoft 365에서 기본 제공되는 Intune 또는 기본 이동성 및 보안으로 장치 관리를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-141">You are doing device management with Intune or Basic Mobility and Security built into Microsoft 365.</span></span>
  - <span data-ttu-id="c3f1c-142">조직 소유 장치가 등록되고 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-142">Your organization-owned devices are enrolled and managed.</span></span>
  - <span data-ttu-id="c3f1c-143">개인 디바이스용 앱은 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-143">The apps for personal devices are managed.</span></span>

<span data-ttu-id="c3f1c-144">다음은 이러한 요소가 모두 있는 Microsoft 365 테넌트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-144">Here is an example of a Microsoft 365 tenant with all these elements in place.</span></span>

![Microsoft 365 테넌트의 예](../media/tenant-management-overview/tenant-management-tenant-config.png)

<span data-ttu-id="c3f1c-146">이 그림에서 Microsoft 365 테넌트에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-146">In this illustration, the Microsoft 365 tenant includes:</span></span>

- <span data-ttu-id="c3f1c-147">Microsoft 365 E3 및 E5의 제품 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="c3f1c-147">Products and licenses for Microsoft 365 E3 and E5.</span></span>
- <span data-ttu-id="c3f1c-148">Microsoft 365 생산성 앱.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-148">Microsoft 365 productivity apps.</span></span>
- <span data-ttu-id="c3f1c-149">등록된 장치 및 장치 및 응용 프로그램 정책이 있는 Intune</span><span class="sxs-lookup"><span data-stu-id="c3f1c-149">Intune with enrolled devices and device and application policies.</span></span>
- <span data-ttu-id="c3f1c-150">동기화된 사용자 계정(그룹 및 기타 디렉터리 개체), 도메인 및 조건부 액세스 정책이 있는 Azure AD 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-150">An Azure AD tenant that has synchronized user account (groups and other directory objects are not shown), domains, and Conditional Access policies.</span></span>

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a><span data-ttu-id="c3f1c-151">엔터프라이즈용 Microsoft 365 테넌트 기능</span><span class="sxs-lookup"><span data-stu-id="c3f1c-151">Tenant capabilities for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="c3f1c-152">다음 섹션 및 표에는 이 솔루션의 단계에 대한 주요 기능 및 라이선스가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-152">The following sections and table list the key capabilities and licensing for the steps in this solution.</span></span>

### <a name="tenant"></a><span data-ttu-id="c3f1c-153">테넌트</span><span class="sxs-lookup"><span data-stu-id="c3f1c-153">Tenant</span></span>

| <span data-ttu-id="c3f1c-154">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="c3f1c-154">Capability or feature</span></span> | <span data-ttu-id="c3f1c-155">설명</span><span class="sxs-lookup"><span data-stu-id="c3f1c-155">Description</span></span> | <span data-ttu-id="c3f1c-156">라이선싱</span><span class="sxs-lookup"><span data-stu-id="c3f1c-156">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c3f1c-157">여러 테넌트</span><span class="sxs-lookup"><span data-stu-id="c3f1c-157">Multiple tenants</span></span> | <span data-ttu-id="c3f1c-158">각 Microsoft 365 테넌트는 다른 모든 Microsoft 365 테넌트와는 고유하며 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-158">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="c3f1c-159">테넌트가 여러 개인 경우 테넌트 관리 및 사용자에게 서비스를 제공하는 경우 제한 사항 및 추가 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-159">With multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span> | <span data-ttu-id="c3f1c-160">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-161">교차 테넌트 사서함 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c3f1c-161">Cross-tenant mailbox migration</span></span> | <span data-ttu-id="c3f1c-162">테넌트 관리자는 테넌트 간에 사서함을 이동할 수 있습니다( 인프라 종속성은 최소한의 수준으로, 해당 테넌트의 경우).</span><span class="sxs-lookup"><span data-stu-id="c3f1c-162">Tenant administrators can move mailboxes between tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="c3f1c-163">이렇게 하여 사서함을 오프보드하고 온보드할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-163">This removes the need to off-board and onboard mailboxes.</span></span> | <span data-ttu-id="c3f1c-164">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-164">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-165">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="c3f1c-165">Multi-Geo</span></span> | <span data-ttu-id="c3f1c-166">테넌트는 데이터 보관 요구 사항을 충족하기 위해 선택한 다른 데이터 센터 지리적 위치에 보관된 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-166">Your tenant can store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements.</span></span> | <span data-ttu-id="c3f1c-167">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-168">핵심 데이터를 새 데이터 센터 지역으로 이동</span><span class="sxs-lookup"><span data-stu-id="c3f1c-168">Move core data to a new datacenter geo</span></span> | <span data-ttu-id="c3f1c-169">Microsoft가 추가 용량 및 계산 리소스를 위해 새 데이터 센터 지역을 추가하면 핵심 고객 데이터에 대한 지역 내 데이터 원본에 대한 데이터 센터 지리적 이동을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-169">As Microsoft adds new datacenter geos for additional capacity and compute resources, you can request a datacenter geo move for in-geo data residency for your core customer data.</span></span> | <span data-ttu-id="c3f1c-170">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-170">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="networking"></a><span data-ttu-id="c3f1c-171">네트워킹</span><span class="sxs-lookup"><span data-stu-id="c3f1c-171">Networking</span></span>

| <span data-ttu-id="c3f1c-172">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="c3f1c-172">Capability or feature</span></span> | <span data-ttu-id="c3f1c-173">설명</span><span class="sxs-lookup"><span data-stu-id="c3f1c-173">Description</span></span> | <span data-ttu-id="c3f1c-174">라이선싱</span><span class="sxs-lookup"><span data-stu-id="c3f1c-174">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c3f1c-175">네트워크 인사이트</span><span class="sxs-lookup"><span data-stu-id="c3f1c-175">Network Insights</span></span> | <span data-ttu-id="c3f1c-176">Microsoft 365 테넌트에서 수집한 네트워크 성능 메트릭을 사용하여 사무실 위치의 네트워크 경계를 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-176">Network performance metrics collected from your Microsoft 365 tenant to help you design network perimeters for your office locations.</span></span> | <span data-ttu-id="c3f1c-177">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-177">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-178">끝점 업데이트 자동화</span><span class="sxs-lookup"><span data-stu-id="c3f1c-178">Automate endpoint updates</span></span> | <span data-ttu-id="c3f1c-179">클라이언트 PAC 파일 및 네트워크 장치 및 서비스에서 Microsoft 365 끝점에 대한 구성 및 지속적인 업데이트를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-179">Automate the configuration and ongoing updates for Microsoft 365 endpoints in your client PAC files and network devices and services.</span></span> | <span data-ttu-id="c3f1c-180">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-180">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="identity"></a><span data-ttu-id="c3f1c-181">ID</span><span class="sxs-lookup"><span data-stu-id="c3f1c-181">Identity</span></span>

| <span data-ttu-id="c3f1c-182">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="c3f1c-182">Capability or feature</span></span> | <span data-ttu-id="c3f1c-183">설명</span><span class="sxs-lookup"><span data-stu-id="c3f1c-183">Description</span></span> | <span data-ttu-id="c3f1c-184">라이선싱</span><span class="sxs-lookup"><span data-stu-id="c3f1c-184">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c3f1c-185">Azure AD 테넌트와 AD DS(Active Directory 도메인 서비스)를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-185">Synchronize on-premises Active Directory Domain Services (AD DS) with your Azure AD tenant</span></span>    | <span data-ttu-id="c3f1c-186">사용자 계정, 그룹 및 기타 개체에 대해 프레미스 ID 공급자를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-186">Leverage your on-premises identity provider for user accounts, groups, and other objects.</span></span> | <span data-ttu-id="c3f1c-187">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-187">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c3f1c-188">보안 기본값을 사용하여 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="c3f1c-188">MFA enforced with security defaults</span></span>   | <span data-ttu-id="c3f1c-189">로그인에 대한 보조 인증을 요구함으로써 손상된 ID와 장치로부터 보호합니다. 보안 기본값은 모든 사용자 계정에 대해 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-189">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="c3f1c-190">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-190">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="c3f1c-191">조건부 액세스로 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="c3f1c-191">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="c3f1c-192">조건부 액세스 정책을 통해 로그인하는 특성을 기반으로 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-192">Require MFA based on the attributes of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="c3f1c-193">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-193">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-194">위험 기반 조건부 액세스로 MFA 실행</span><span class="sxs-lookup"><span data-stu-id="c3f1c-194">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="c3f1c-195">ID용 Microsoft Defender와 함께 사용자 로그인의 위험을 기반으로 하는 MFA가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-195">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="c3f1c-196">Azure AD Premium P2 라이선스를 포함한 Microsoft 365 E5 또는 E3</span><span class="sxs-lookup"><span data-stu-id="c3f1c-196">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="c3f1c-197">셀프 서비스 암호 재설정(SSPR)</span><span class="sxs-lookup"><span data-stu-id="c3f1c-197">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="c3f1c-198">사용자가 암호 또는 계정을 다시 설정하거나 잠금 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-198">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="c3f1c-199">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-199">Microsoft 365 E3 or E5</span></span> |
||||

### <a name="migration"></a><span data-ttu-id="c3f1c-200">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c3f1c-200">Migration</span></span>

| <span data-ttu-id="c3f1c-201">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="c3f1c-201">Capability or feature</span></span> | <span data-ttu-id="c3f1c-202">설명</span><span class="sxs-lookup"><span data-stu-id="c3f1c-202">Description</span></span> | <span data-ttu-id="c3f1c-203">라이선싱</span><span class="sxs-lookup"><span data-stu-id="c3f1c-203">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c3f1c-204">Windows 10으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c3f1c-204">Migrate to Windows 10</span></span> | <span data-ttu-id="c3f1c-205">Windows 7 또는 Windows 8.1을 실행한 디바이스를 Windows 10 Enterprise로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-205">Migrate your devices that run Windows 7 or Windows 8.1 to Windows 10 Enterprise.</span></span> | <span data-ttu-id="c3f1c-206">Microsoft 365 E3 또는 E5에 포함된 Windows 10 Enterprise 라이선스</span><span class="sxs-lookup"><span data-stu-id="c3f1c-206">Windows 10 Enterprise licenses included with Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-207">엔터프라이즈용 Microsoft 365 앱으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c3f1c-207">Migrate to Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="c3f1c-208">Word 및 PowerPoint와 같은 Office 클라이언트 앱을 새 기능으로 업데이트된 클라우드에서 설치된 버전으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-208">Migrate your Office client apps such as Word and PowerPoint to the versions installed from the cloud that are updated with new features.</span></span> | <span data-ttu-id="c3f1c-209">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-209">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-210">Microsoft 365로의온-프레미스 서버 및 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c3f1c-210">Migrate on-premises servers and data to Microsoft 365</span></span> | <span data-ttu-id="c3f1c-211">Exchange 사서함, SharePoint 사이트 및 비즈니스용 Skype Online을 Microsoft 365 클라우드 서비스로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-211">Migrate your Exchange mailboxes, SharePoint sites, and Skype for Business Online to Microsoft 365 cloud services.</span></span> | <span data-ttu-id="c3f1c-212">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-212">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="device-and-app-management"></a><span data-ttu-id="c3f1c-213">장치 및 앱 관리</span><span class="sxs-lookup"><span data-stu-id="c3f1c-213">Device and app management</span></span>

| <span data-ttu-id="c3f1c-214">기능 또는 특징</span><span class="sxs-lookup"><span data-stu-id="c3f1c-214">Capability or feature</span></span> | <span data-ttu-id="c3f1c-215">설명</span><span class="sxs-lookup"><span data-stu-id="c3f1c-215">Description</span></span> | <span data-ttu-id="c3f1c-216">라이선싱</span><span class="sxs-lookup"><span data-stu-id="c3f1c-216">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c3f1c-217">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c3f1c-217">Microsoft Intune</span></span> | <span data-ttu-id="c3f1c-218">MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 관리)을 제공하는 클라우드 기반 서비스로, 휴대폰, 태블릿 및 노트북을 포함하여 조직의 응용 프로그램 및 장치를 사용하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-218">A cloud-based service that provides mobile device management (MDM) and mobile application management (MAM) to control how your organization’s application and the devices are used, including mobile phones, tablets, and laptops.</span></span> | <span data-ttu-id="c3f1c-219">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-219">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="c3f1c-220">기본 모바일 및 보안</span><span class="sxs-lookup"><span data-stu-id="c3f1c-220">Basic Mobility and Security</span></span> | <span data-ttu-id="c3f1c-221">이 기본 제공 서비스를 사용하여 iPhone, iPad, Androids 및 Windows 휴대폰과 같은 사용자의 모바일 장치를 보호하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-221">Secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones with this built-in service.</span></span>  | <span data-ttu-id="c3f1c-222">Microsoft 365 E3 혹은 E5</span><span class="sxs-lookup"><span data-stu-id="c3f1c-222">Microsoft 365 E3 or E5</span></span> | 
||||

## <a name="next-steps"></a><span data-ttu-id="c3f1c-223">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c3f1c-223">Next steps</span></span>

<span data-ttu-id="c3f1c-224">다음 단계에 따라 Microsoft 365 테넌트 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="c3f1c-224">Use these steps to set up and manage your Microsoft 365 tenants.</span></span>

1. [<span data-ttu-id="c3f1c-225">테넌트 결정</span><span class="sxs-lookup"><span data-stu-id="c3f1c-225">Determine your tenants</span></span>](tenant-management-tenants.md)
2. [<span data-ttu-id="c3f1c-226">네트워킹 최적화</span><span class="sxs-lookup"><span data-stu-id="c3f1c-226">Optimize your networking</span></span>](tenant-management-networking.md)
3. [<span data-ttu-id="c3f1c-227">ID 동기화 및 보안 로그인 적용</span><span class="sxs-lookup"><span data-stu-id="c3f1c-227">Synchronize your identities and enforce secure sign-ins</span></span>](tenant-management-identity.md)
4. [<span data-ttu-id="c3f1c-228">온-프레미스 Office 서버 및 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="c3f1c-228">Migrate your on-premises Office servers and data</span></span>](tenant-management-migration.md)
5. [<span data-ttu-id="c3f1c-229">장치 및 앱 관리 배포</span><span class="sxs-lookup"><span data-stu-id="c3f1c-229">Deploy device and app management</span></span>](tenant-management-device-management.md)

<span data-ttu-id="c3f1c-230">[![Microsoft 365 테넌트 배포 및 관리 단계](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="c3f1c-230">[![The steps to deploy and manage a Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span></span>

<span data-ttu-id="c3f1c-231">각 단계에서는 배포 옵션, 결과 요약 및 지속적인 유지 관리 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-231">Each step describes deployment options, summarizes the results, and ongoing maintenance tasks.</span></span>

<span data-ttu-id="c3f1c-232">대표적인 다국적 조직이 Microsoft 365 테넌트의 요소를 배포한 방법을 이해하기 위해 [Contoso 사례](../enterprise/contoso-case-study.md)연구를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-232">To understand how a fictional but representative multi-national organization deployed the elements of their Microsoft 365 tenant, see the [Contoso case study](../enterprise/contoso-case-study.md).</span></span>
