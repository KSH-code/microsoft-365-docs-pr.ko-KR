---
title: MSSP(관리되는 보안 서비스 공급자) 액세스 제공
description: Microsoft Defender 보안 센터에서 Microsoft 365 보안 센터로의 변경 내용에 대해 자세히 알아보기
keywords: Microsoft 365 보안 센터, Office 365용 Microsoft Defender, 끝점용 Microsoft Defender, MDO, MDE, 단일 창, 수렴 포털, 보안 포털, Defender 보안 포털 시작
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 4b34d3ea20716fb2424d9317b8a51c088a5714a6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935356"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="353a1-104">MSSP(관리되는 보안 서비스 공급자) 액세스 제공</span><span class="sxs-lookup"><span data-stu-id="353a1-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="353a1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="353a1-105">**Applies to:**</span></span>

- [<span data-ttu-id="353a1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="353a1-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="353a1-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="353a1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="353a1-108">다중 테넌트 위임 액세스 솔루션을 구현하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="353a1-109">Microsoft [](/windows/security/threat-protection/microsoft-defender-atp/rbac) 365 보안 센터의 Endpoint용 Defender에서 역할 기반 액세스 제어를 사용하도록 설정하고 Azure AD(Azure Active Directory) 그룹에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="353a1-110">액세스 [요청 및 프로비저닝을 위해](/azure/active-directory/governance/identity-governance-overview) 거버넌스 액세스 패키지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="353a1-111">Microsoft Myaccess에서 액세스 요청 및 [감사를 관리합니다.](/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="353a1-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="353a1-112">Microsoft 365 보안 센터의 끝점에 대한 Microsoft Defender에서 역할 기반 액세스 제어 사용</span><span class="sxs-lookup"><span data-stu-id="353a1-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="353a1-113">**고객 AAD에서 MSSP 리소스에 대한 액세스 그룹 만들기: 그룹**</span><span class="sxs-lookup"><span data-stu-id="353a1-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="353a1-114">이러한 그룹은 Microsoft 365 보안 센터의 Endpoint용 Defender에서 만든 역할에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="353a1-115">이렇게 하여 고객 AD 테넌트에서 세 개의 그룹을 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="353a1-116">이 예제에서는 다음 그룹을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="353a1-117">계층 1 분석가</span><span class="sxs-lookup"><span data-stu-id="353a1-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="353a1-118">계층 2 분석가</span><span class="sxs-lookup"><span data-stu-id="353a1-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="353a1-119">MSSP 분석가 승인자</span><span class="sxs-lookup"><span data-stu-id="353a1-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="353a1-120">Microsoft 365 보안 센터 역할 및 그룹의 Endpoint용 Customer Defender에서 적절한 액세스 수준에 대한 끝점 역할에 대한 Defender를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="353a1-121">고객 Microsoft 365 보안 센터에서 RBAC를 사용하도록 설정하려면 사용 권한 > **끝점** 역할 & 그룹 > 전역 관리자 또는 보안 관리자 권한이 있는 사용자 계정으로 역할에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP 액세스 이미지](../../media/mssp-access.png)

    <span data-ttu-id="353a1-123">그런 다음 MSSP SOC 계층 요구 사항을 충족하는 RBAC 역할을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="353a1-124">"할당된 사용자 그룹"을 통해 이러한 역할을 만든 사용자 그룹에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="353a1-125">가능한 두 가지 역할:</span><span class="sxs-lookup"><span data-stu-id="353a1-125">Two possible roles:</span></span>

    - <span data-ttu-id="353a1-126">**계층 1 분석가**</span><span class="sxs-lookup"><span data-stu-id="353a1-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="353a1-127">라이브 응답을 제외한 모든 작업을 수행하고 보안 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="353a1-128">**계층 2 분석가**</span><span class="sxs-lookup"><span data-stu-id="353a1-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="353a1-129">실시간 응답이 추가된 계층 1 [기능](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="353a1-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="353a1-130">자세한 내용은 역할 기반 액세스 [제어 사용을 참조하세요.](/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="353a1-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="353a1-131">거버넌스 액세스 패키지 구성</span><span class="sxs-lookup"><span data-stu-id="353a1-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="353a1-132">**고객 AAD에서 MSSP를 연결된 조직으로 추가: ID 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="353a1-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="353a1-133">MSSP를 연결된 조직으로 추가하면 MSSP가 프로비전된 액세스를 요청하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="353a1-134">이렇게 하려면 고객 AD 테넌트에서 ID 거버넌스: 연결된 조직에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="353a1-135">새 조직을 추가하고 테넌트 ID 또는 도메인을 통해 MSSP 분석가 테넌트 검색</span><span class="sxs-lookup"><span data-stu-id="353a1-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="353a1-136">MSSP 분석가를 위한 별도의 AD 테넌트 만들기를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="353a1-137">**고객 AAD에서 리소스 카탈로그 만들기: ID 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="353a1-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="353a1-138">리소스 카탈로그는 고객 AD 테넌트에서 만든 액세스 패키지의 논리적 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="353a1-139">이를 위해 고객 AD 테넌트에서 ID 거버넌스: 카탈로그에 액세스하고 새 **카탈로그를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="353a1-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="353a1-140">이 예제에서는 **MSSP Accesses 를 호출합니다.**</span><span class="sxs-lookup"><span data-stu-id="353a1-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![새 카탈로그의 이미지](../../media/goverance-catalog.png)

    <span data-ttu-id="353a1-142">자세한 내용은 리소스 카탈로그 [만들기를 참조하세요.](/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="353a1-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="353a1-143">**MSSP 리소스 고객 AAD: ID 거버넌스에 대한 액세스 패키지 만들기**</span><span class="sxs-lookup"><span data-stu-id="353a1-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="353a1-144">액세스 패키지는 승인 시 요청자에 부여되는 권한 및 액세스의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="353a1-145">이렇게 하여 고객 AD 테넌트에서 ID 거버넌스: 액세스 패키지에 액세스하고 새 **액세스 패키지를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="353a1-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="353a1-146">MSSP 승인자 및 각 분석가 계층에 대한 액세스 패키지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="353a1-147">예를 들어 다음 계층 1 분석가 구성은 다음과 같은 액세스 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="353a1-148">AD 그룹 **MSSP** 분석가 승인자의 구성원이 새 요청을 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="353a1-149">SOC 분석가가 액세스 확장을 요청할 수 있는 연간 액세스 검토가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="353a1-150">MSSP SOC 테넌트의 사용자만 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="353a1-151">365일 후에 액세스 자동 만료</span><span class="sxs-lookup"><span data-stu-id="353a1-151">Access auto expires after 365 days</span></span>

    ![새 액세스 패키지의 이미지](../../media/new-access-package.png)

    <span data-ttu-id="353a1-153">자세한 내용은 새 액세스 패키지 [만들기를 참조하세요.](/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="353a1-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="353a1-154">**고객 AAD에서 MSSP 리소스에 대한 액세스 요청 링크 제공: ID 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="353a1-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="353a1-155">내 액세스 포털 링크는 MSSP SOC 분석가가 만든 액세스 패키지를 통해 액세스를 요청하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="353a1-156">링크는 지속형으로, 시간이 지날 때 새 분석가에게 동일한 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="353a1-157">분석가 요청은 MSSP 분석가 승인자 의 승인을 **위해 큐로 들어갑니다.**</span><span class="sxs-lookup"><span data-stu-id="353a1-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![액세스 속성의 이미지](../../media/access-properties.png)

    <span data-ttu-id="353a1-159">링크는 각 액세스 패키지의 개요 페이지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="353a1-160">액세스 관리</span><span class="sxs-lookup"><span data-stu-id="353a1-160">Manage access</span></span> 

1. <span data-ttu-id="353a1-161">고객 및/또는 MSSP 내 액세스 요청을 검토하고 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="353a1-162">액세스 요청은 MSSP 분석가 승인자 그룹의 구성원에 의해 고객 내 액세스에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="353a1-163">이렇게 하는 경우 를 사용하여 고객의 myaccess에  `https://myaccess.microsoft.com/@<Customer Domain >` 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="353a1-164">예:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="353a1-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="353a1-165">UI의 승인 섹션에서  요청을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="353a1-166">이때 분석가 액세스가 프로비전되고 각 분석가가 고객의 Microsoft 365 보안 센터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="353a1-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` 할당된 사용 권한 및 역할과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="353a1-168">Microsoft 365 보안 센터에서 끝점용 Microsoft Defender에 대한 위임된 액세스를 통해 현재 브라우저 창당 하나의 테넌트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353a1-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>