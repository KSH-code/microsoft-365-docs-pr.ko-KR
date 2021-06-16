---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 마이그레이션 후 활동
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동한 후의 마이그레이션 후 활동'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930418"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="33ce1-103">도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 마이그레이션 후 활동</span><span class="sxs-lookup"><span data-stu-id="33ce1-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="33ce1-104">다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스를 이동한 후 여러 서비스에 대한 마이그레이션 후 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="33ce1-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="33ce1-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="33ce1-106">AD FS를 사용하는 Azure AD 페더전 인증</span><span class="sxs-lookup"><span data-stu-id="33ce1-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="33ce1-107">**다음에 적용됩니다.** AD FS와의 페더러드 인증을 사용하는 모든 고객</span><span class="sxs-lookup"><span data-stu-id="33ce1-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="33ce1-108">Step(s)</span><span class="sxs-lookup"><span data-stu-id="33ce1-108">Step(s)</span></span> | <span data-ttu-id="33ce1-109">설명</span><span class="sxs-lookup"><span data-stu-id="33ce1-109">Description</span></span> | <span data-ttu-id="33ce1-110">영향</span><span class="sxs-lookup"><span data-stu-id="33ce1-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="33ce1-111">도이치클라드 MICROSOFT 클라우드 AD FS에서 신뢰 파티 트러스트 제거</span><span class="sxs-lookup"><span data-stu-id="33ce1-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="33ce1-112">Azure AD에 대한 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이클란드 Microsoft 클라우드에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="33ce1-113">이 시점에서 고객은 도이치클라드 Microsoft 클라우드 끝점에 대한 신뢰 파티 트러스트는 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="33ce1-114">Azure AD가 IdP(ID 공급자)로 활용될 때 고객의 응용 프로그램이 도이치클라드 Microsoft 클라우드 끝점을 지점하지만 이행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="33ce1-115">페더리드 인증 조직</span><span class="sxs-lookup"><span data-stu-id="33ce1-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="33ce1-116">그룹 승인</span><span class="sxs-lookup"><span data-stu-id="33ce1-116">Group approvals</span></span>
<span data-ttu-id="33ce1-117">**다음에 적용됩니다.** 마이그레이션 전 지난 30일 동안 Azure AD 그룹 승인 요청이 승인되지 않은 최종 사용자</span><span class="sxs-lookup"><span data-stu-id="33ce1-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="33ce1-118">Step(s)</span><span class="sxs-lookup"><span data-stu-id="33ce1-118">Step(s)</span></span> | <span data-ttu-id="33ce1-119">설명</span><span class="sxs-lookup"><span data-stu-id="33ce1-119">Description</span></span> | <span data-ttu-id="33ce1-120">영향</span><span class="sxs-lookup"><span data-stu-id="33ce1-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="33ce1-121">원래 요청이 승인되지 않은 경우 마이그레이션 전에 지난 30일 동안 Azure AD 그룹에 가입하기 위한 요청을 다시 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="33ce1-122">최종 사용자 고객은 마이그레이션 전 지난 30일 동안 해당 요청이 승인되지 않은 경우 액세스 패널을 사용하여 Azure AD 그룹에 가입하기 위한 요청을 다시 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="33ce1-123">최종 사용자:</span><span class="sxs-lookup"><span data-stu-id="33ce1-123">As an end-user:</span></span> <ol><li><span data-ttu-id="33ce1-124">액세스 [패널로 이동합니다.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</span><span class="sxs-lookup"><span data-stu-id="33ce1-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="33ce1-125">마이그레이션 30일 전에 구성원 승인이 보류된 Azure AD 그룹을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="33ce1-126">Azure AD 그룹에 다시 참가를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="33ce1-127">마이그레이션 후 다시 요청되지 않는 한 마이그레이션을 승인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="33ce1-128">사용자 지정 DNS 업데이트</span><span class="sxs-lookup"><span data-stu-id="33ce1-128">Custom DNS updates</span></span>
<span data-ttu-id="33ce1-129">**다음에 적용됩니다.**  자체 DNS 영역 관리</span><span class="sxs-lookup"><span data-stu-id="33ce1-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="33ce1-130">Step(s)</span><span class="sxs-lookup"><span data-stu-id="33ce1-130">Step(s)</span></span> | <span data-ttu-id="33ce1-131">설명</span><span class="sxs-lookup"><span data-stu-id="33ce1-131">Description</span></span> | <span data-ttu-id="33ce1-132">영향</span><span class="sxs-lookup"><span data-stu-id="33ce1-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="33ce1-133">서비스 끝점에 대한 Office 365 DNS 서비스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="33ce1-134">도이치클라드 Microsoft 클라우드를 지점으로 하는 고객 관리 DNS 항목을 업데이트하여 글로벌 서비스 끝점을 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="33ce1-135">Microsoft 365 관리 센터에서 도메인을 [참조하고](https://admin.microsoft.com/Adminportal/Home#/Domains) DNS 구성의 변경 내용을 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="33ce1-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="33ce1-136">이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="33ce1-137">타사 서비스</span><span class="sxs-lookup"><span data-stu-id="33ce1-137">Third-party services</span></span>
<span data-ttu-id="33ce1-138">**다음에 적용됩니다.** Office 365 서비스 끝점에 타사 서비스를 사용하는 고객</span><span class="sxs-lookup"><span data-stu-id="33ce1-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="33ce1-139">Step(s)</span><span class="sxs-lookup"><span data-stu-id="33ce1-139">Step(s)</span></span> | <span data-ttu-id="33ce1-140">설명</span><span class="sxs-lookup"><span data-stu-id="33ce1-140">Description</span></span> | <span data-ttu-id="33ce1-141">영향</span><span class="sxs-lookup"><span data-stu-id="33ce1-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="33ce1-142">Office 365 끝점에 대한 파트너 및 타사 서비스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="33ce1-143">독일을 지점으로 하는 타사 서비스 및 Office 365 서비스 끝점을 Office 365 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="33ce1-144">예: 공급업체 및 파트너에 따라 응용 프로그램의 갤러리 앱 버전(사용 가능한 경우)을 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="33ce1-145">에서 으로 Graph 사용자 지정 응용 프로그램을 `graph.microsoft.de` `graph.microsoft.com` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="33ce1-146">변경된 끝점이 있는 다른 API도 활용하는 경우 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="33ce1-147">모든 비제한 엔터프라이즈 응용 프로그램을 변경하여 전 세계 끝점으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="33ce1-148">필수 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-148">Required action.</span></span> <span data-ttu-id="33ce1-149">이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ce1-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||