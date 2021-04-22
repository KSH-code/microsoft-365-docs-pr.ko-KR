---
title: MSSP(관리되는 보안 서비스 공급자)에 대한 액세스 권한 부여
description: 끝점용 Microsoft Defender와 MSSP 통합을 구성하는 데 필요한 단계 수행
keywords: 관리되는 보안 서비스 공급자, mssp, 구성, 통합
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 320355f838db5dbb1540350e95e4cc0645acd805
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932754"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="93cd6-104">MSSP(관리되는 보안 서비스 공급자) 액세스 권한 부여(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="93cd6-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93cd6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="93cd6-105">**Applies to:**</span></span>
- [<span data-ttu-id="93cd6-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="93cd6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="93cd6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93cd6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="93cd6-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="93cd6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="93cd6-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="93cd6-110">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="93cd6-111">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="93cd6-112">다중 테넌트 위임 액세스 솔루션을 구현하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="93cd6-113">[끝점용](rbac.md) Defender에서 역할 기반 액세스 제어를 사용하도록 설정하고 AD(Active Directory) 그룹과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="93cd6-114">액세스 [요청 및 프로비저닝을 위해](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) 거버넌스 액세스 패키지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="93cd6-115">Microsoft Myaccess에서 액세스 요청 및 [감사를 관리합니다.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="93cd6-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="93cd6-116">끝점용 Microsoft Defender에서 역할 기반 액세스 제어 사용</span><span class="sxs-lookup"><span data-stu-id="93cd6-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="93cd6-117">**고객 AAD에서 MSSP 리소스에 대한 액세스 그룹 만들기: 그룹**</span><span class="sxs-lookup"><span data-stu-id="93cd6-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="93cd6-118">이러한 그룹은 Endpoint용 Defender에서 만든 역할에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="93cd6-119">이렇게 하여 고객 AD 테넌트에서 세 개의 그룹을 만드면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="93cd6-120">이 예제에서는 다음 그룹을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="93cd6-121">계층 1 분석가</span><span class="sxs-lookup"><span data-stu-id="93cd6-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="93cd6-122">계층 2 분석가</span><span class="sxs-lookup"><span data-stu-id="93cd6-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="93cd6-123">MSSP 분석가 승인자</span><span class="sxs-lookup"><span data-stu-id="93cd6-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="93cd6-124">Endpoint용 Customer Defender에서 적절한 액세스 수준에 대한 끝점 역할에 대한 Defender를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="93cd6-125">고객 Microsoft Defender 보안 센터에서 RBAC를 사용하도록 설정하려면 전역 관리자 또는 보안 관리자 권한이 **>** 사용자 계정에서 > 권한 > 역할 및 "역할 켜기"에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP 액세스 이미지](images/mssp-access.png)

    <span data-ttu-id="93cd6-127">그런 다음 MSSP SOC 계층 요구 사항을 충족하는 RBAC 역할을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="93cd6-128">"할당된 사용자 그룹"을 통해 이러한 역할을 만든 사용자 그룹에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="93cd6-129">가능한 두 가지 역할:</span><span class="sxs-lookup"><span data-stu-id="93cd6-129">Two possible roles:</span></span>

    - <span data-ttu-id="93cd6-130">**계층 1 분석가**</span><span class="sxs-lookup"><span data-stu-id="93cd6-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="93cd6-131">라이브 응답을 제외한 모든 작업을 수행하고 보안 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="93cd6-132">**계층 2 분석가**</span><span class="sxs-lookup"><span data-stu-id="93cd6-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="93cd6-133">실시간 응답이 추가된 계층 1 [기능](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="93cd6-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="93cd6-134">자세한 내용은 역할 기반 액세스 [제어 사용을 참조하세요.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="93cd6-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="93cd6-135">거버넌스 액세스 패키지 구성</span><span class="sxs-lookup"><span data-stu-id="93cd6-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="93cd6-136">**고객 AAD에서 MSSP를 연결된 조직으로 추가: ID 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="93cd6-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="93cd6-137">MSSP를 연결된 조직으로 추가하면 MSSP가 프로비전된 액세스를 요청하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="93cd6-138">이렇게 하려면 고객 AD 테넌트에서 ID 거버넌스: 연결된 조직에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="93cd6-139">새 조직을 추가하고 테넌트 ID 또는 도메인을 통해 MSSP 분석가 테넌트 검색</span><span class="sxs-lookup"><span data-stu-id="93cd6-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="93cd6-140">MSSP 분석가를 위한 별도의 AD 테넌트 만들기를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="93cd6-141">**고객 AAD에서 리소스 카탈로그 만들기: ID 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="93cd6-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="93cd6-142">리소스 카탈로그는 고객 AD 테넌트에서 만든 액세스 패키지의 논리적 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="93cd6-143">이를 위해 고객 AD 테넌트에서 ID 거버넌스: 카탈로그에 액세스하고 새 **카탈로그를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="93cd6-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="93cd6-144">이 예제에서는 **MSSP Accesses 를 호출합니다.**</span><span class="sxs-lookup"><span data-stu-id="93cd6-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![새 카탈로그의 이미지](images/goverance-catalog.png)

    <span data-ttu-id="93cd6-146">자세한 내용은 리소스 카탈로그 [만들기를 참조하세요.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="93cd6-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="93cd6-147">**MSSP 리소스 고객 AAD: ID 거버넌스에 대한 액세스 패키지 만들기**</span><span class="sxs-lookup"><span data-stu-id="93cd6-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="93cd6-148">액세스 패키지는 승인 시 요청자에 부여되는 권한 및 액세스의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="93cd6-149">이렇게 하여 고객 AD 테넌트에서 ID 거버넌스: 액세스 패키지에 액세스하고 새 **액세스 패키지를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="93cd6-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="93cd6-150">MSSP 승인자 및 각 분석가 계층에 대한 액세스 패키지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="93cd6-151">예를 들어 다음 계층 1 분석가 구성은 다음과 같은 액세스 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="93cd6-152">AD 그룹 **MSSP** 분석가 승인자의 구성원이 새 요청을 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="93cd6-153">SOC 분석가가 액세스 확장을 요청할 수 있는 연간 액세스 검토가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="93cd6-154">MSSP SOC 테넌트의 사용자만 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="93cd6-155">365일 후에 액세스 자동 만료</span><span class="sxs-lookup"><span data-stu-id="93cd6-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="93cd6-156">![새 액세스 패키지의 이미지](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="93cd6-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="93cd6-157">자세한 내용은 새 액세스 패키지 [만들기를 참조하세요.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="93cd6-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="93cd6-158">**고객 AAD에서 MSSP 리소스에 대한 액세스 요청 링크 제공: ID 거버넌스**</span><span class="sxs-lookup"><span data-stu-id="93cd6-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="93cd6-159">내 액세스 포털 링크는 MSSP SOC 분석가가 만든 액세스 패키지를 통해 액세스를 요청하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="93cd6-160">링크는 지속형으로, 시간이 지날 때 새 분석가에게 동일한 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="93cd6-161">분석가 요청은 MSSP 분석가 승인자 의 승인을 **위해 큐로 들어갑니다.**</span><span class="sxs-lookup"><span data-stu-id="93cd6-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="93cd6-162">![액세스 속성의 이미지](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="93cd6-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="93cd6-163">링크는 각 액세스 패키지의 개요 페이지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="93cd6-164">액세스 관리</span><span class="sxs-lookup"><span data-stu-id="93cd6-164">Manage access</span></span> 

1. <span data-ttu-id="93cd6-165">고객 및/또는 MSSP 내 액세스 요청을 검토하고 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="93cd6-166">액세스 요청은 MSSP 분석가 승인자 그룹의 구성원에 의해 고객 내 액세스에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="93cd6-167">이렇게 하는 경우 를 사용하여 고객의 myaccess에  `https://myaccess.microsoft.com/@<Customer Domain >` 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="93cd6-168">예:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="93cd6-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="93cd6-169">UI의 승인 섹션에서  요청을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="93cd6-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="93cd6-170">이때 분석가 액세스가 프로비전되고 각 분석가가 고객의 Microsoft Defender 보안 센터에 액세스할 수 있습니다. `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="93cd6-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="93cd6-171">관련 항목</span><span class="sxs-lookup"><span data-stu-id="93cd6-171">Related topics</span></span>
- [<span data-ttu-id="93cd6-172">MSSP 고객 포털에 액세스</span><span class="sxs-lookup"><span data-stu-id="93cd6-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="93cd6-173">경고 알림 구성</span><span class="sxs-lookup"><span data-stu-id="93cd6-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="93cd6-174">고객 테넌트에서 경고 페치</span><span class="sxs-lookup"><span data-stu-id="93cd6-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

