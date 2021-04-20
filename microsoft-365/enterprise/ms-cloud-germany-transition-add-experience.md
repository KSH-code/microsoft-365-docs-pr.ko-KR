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
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899367"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3aa25-103">도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 마이그레이션 후 활동</span><span class="sxs-lookup"><span data-stu-id="3aa25-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="3aa25-104">다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동한 후 여러 서비스에 대한 마이그레이션 후 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="3aa25-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="3aa25-105">Azure AD</span></span>
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

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="3aa25-106">AD FS를 사용하는 Azure AD 페더전 인증</span><span class="sxs-lookup"><span data-stu-id="3aa25-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="3aa25-107">**다음에 적용됩니다.** AD FS와의 페더러드 인증을 사용하는 모든 고객</span><span class="sxs-lookup"><span data-stu-id="3aa25-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="3aa25-108">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3aa25-108">Step(s)</span></span> | <span data-ttu-id="3aa25-109">설명</span><span class="sxs-lookup"><span data-stu-id="3aa25-109">Description</span></span> | <span data-ttu-id="3aa25-110">영향</span><span class="sxs-lookup"><span data-stu-id="3aa25-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3aa25-111">도이치클라드 MICROSOFT 클라우드 AD FS에서 신뢰 파티 트러스트 제거</span><span class="sxs-lookup"><span data-stu-id="3aa25-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="3aa25-112">Azure AD에 대한 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이치랜드 Microsoft 클라우드에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="3aa25-113">이 시점에서 고객은 도이치클라드 Microsoft 클라우드 끝점에 대한 신뢰 파티 트러스트는 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="3aa25-114">Azure AD가 IdP(ID 공급자)로 활용될 때 고객의 응용 프로그램이 도이치클라드 Microsoft 클라우드 끝점을 지점하지만 이행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="3aa25-115">페더리드 인증 조직</span><span class="sxs-lookup"><span data-stu-id="3aa25-115">Federated Authentication organizations</span></span> | <span data-ttu-id="3aa25-116">없음</span><span class="sxs-lookup"><span data-stu-id="3aa25-116">None.</span></span> |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="3aa25-117">그룹 승인</span><span class="sxs-lookup"><span data-stu-id="3aa25-117">Group approvals</span></span>
<span data-ttu-id="3aa25-118">**다음에 적용됩니다.** 마이그레이션 전 지난 30일 동안 Azure AD 그룹 승인 요청이 승인되지 않은 최종 사용자</span><span class="sxs-lookup"><span data-stu-id="3aa25-118">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="3aa25-119">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3aa25-119">Step(s)</span></span> | <span data-ttu-id="3aa25-120">설명</span><span class="sxs-lookup"><span data-stu-id="3aa25-120">Description</span></span> | <span data-ttu-id="3aa25-121">영향</span><span class="sxs-lookup"><span data-stu-id="3aa25-121">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3aa25-122">원래 요청이 승인되지 않은 경우 마이그레이션 전에 지난 30일 동안 Azure AD 그룹에 가입하기 위한 요청을 다시 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-122">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="3aa25-123">최종 사용자 고객은 마이그레이션 전 지난 30일 동안 해당 요청이 승인되지 않은 경우 액세스 패널을 사용하여 Azure AD 그룹에 가입하기 위한 요청을 다시 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-123">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="3aa25-124">최종 사용자:</span><span class="sxs-lookup"><span data-stu-id="3aa25-124">As an end-user:</span></span> <ol><li><span data-ttu-id="3aa25-125">액세스 [패널로 이동합니다.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</span><span class="sxs-lookup"><span data-stu-id="3aa25-125">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="3aa25-126">마이그레이션 30일 전에 구성원 승인이 보류된 Azure AD 그룹을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-126">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="3aa25-127">Azure AD 그룹에 다시 참가를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-127">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="3aa25-128">마이그레이션 후 다시 요청되지 않는 한 마이그레이션을 승인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-128">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a><span data-ttu-id="3aa25-129">사용자 지정 DNS 업데이트</span><span class="sxs-lookup"><span data-stu-id="3aa25-129">Custom DNS updates</span></span>
<span data-ttu-id="3aa25-130">**다음에 적용됩니다.**  자체 DNS 영역 관리</span><span class="sxs-lookup"><span data-stu-id="3aa25-130">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="3aa25-131">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3aa25-131">Step(s)</span></span> | <span data-ttu-id="3aa25-132">설명</span><span class="sxs-lookup"><span data-stu-id="3aa25-132">Description</span></span> | <span data-ttu-id="3aa25-133">영향</span><span class="sxs-lookup"><span data-stu-id="3aa25-133">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="3aa25-134">Office 365 서비스 끝점에 대한 사내 DNS 서비스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-134">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="3aa25-135">도이치클랜드 Microsoft 클라우드를 지점으로 하는 고객 관리 DNS 항목을 업데이트하여 Office 365 전역 서비스 끝점을 지점으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-135">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> | <span data-ttu-id="3aa25-136">이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="3aa25-137">타사 서비스</span><span class="sxs-lookup"><span data-stu-id="3aa25-137">Third-party services</span></span>
<span data-ttu-id="3aa25-138">**다음에 적용됩니다.** Office 365 서비스 끝점에 대해 타사 서비스를 사용하는 고객</span><span class="sxs-lookup"><span data-stu-id="3aa25-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="3aa25-139">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3aa25-139">Step(s)</span></span> | <span data-ttu-id="3aa25-140">설명</span><span class="sxs-lookup"><span data-stu-id="3aa25-140">Description</span></span> | <span data-ttu-id="3aa25-141">영향</span><span class="sxs-lookup"><span data-stu-id="3aa25-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3aa25-142">Office 365 서비스 끝점에 대한 파트너 및 타사 서비스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="3aa25-143">Office 365 Germany를 지점하는 타사 서비스 및 파트너는 Office 365 서비스 끝점을 지점으로 하여 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="3aa25-144">예: 공급업체 및 파트너에 따라 응용 프로그램의 갤러리 앱 버전(사용 가능한 경우)을 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="3aa25-145">Graph API를 활용하는 모든 사용자 지정 응용 프로그램을 에서 로 `graph.microsoft.de` `graph.microsoft.com` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="3aa25-146">변경된 끝점이 있는 다른 API도 활용하는 경우 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="3aa25-147">모든 비제한 엔터프라이즈 응용 프로그램을 변경하여 전 세계 끝점으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="3aa25-148">필수 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-148">Required action.</span></span> <span data-ttu-id="3aa25-149">이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="sharepoint-online"></a><span data-ttu-id="3aa25-150">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3aa25-150">SharePoint Online</span></span>
<span data-ttu-id="3aa25-151">**적용 사항:** SharePoint 2013 워크플로를 사용하는 고객</span><span class="sxs-lookup"><span data-stu-id="3aa25-151">**Applies to**: Customers using SharePoint 2013 Workflows</span></span>

| <span data-ttu-id="3aa25-152">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3aa25-152">Step(s)</span></span> | <span data-ttu-id="3aa25-153">설명</span><span class="sxs-lookup"><span data-stu-id="3aa25-153">Description</span></span> | <span data-ttu-id="3aa25-154">영향</span><span class="sxs-lookup"><span data-stu-id="3aa25-154">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3aa25-155">SharePoint 2013 워크플로를 다시 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-155">Republish SharePoint 2013 workflows.</span></span> | <span data-ttu-id="3aa25-156">마이그레이션 전 작업에서는 SharePoint 2013 워크플로 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-156">In the pre-migration work, we reduced the number of SharePoint 2013 workflows.</span></span> <span data-ttu-id="3aa25-157">이제 마이그레이션이 완료된 후 고객은 워크플로를 다시 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-157">Now with migration complete, the customer can republish the workflows.</span></span> | <span data-ttu-id="3aa25-158">이 작업은 필수 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-158">This is a required action.</span></span> <span data-ttu-id="3aa25-159">이렇게 하지 못하면 사용자 혼동 및 지원 센터 통화가 발생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-159">Failure to do so may result in user confusion and help desk calls.</span></span> |
| <span data-ttu-id="3aa25-160">Outlook을 통해 항목 공유</span><span class="sxs-lookup"><span data-stu-id="3aa25-160">Share items via Outlook</span></span> | <span data-ttu-id="3aa25-161">Outlook을 통해 SharePoint Online 및 비즈니스용 OneDrive의 항목 공유는 테넌트가 컷오버된 후에 더 이상 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-161">Sharing items in SharePoint Online and OneDrive for Business via Outlook no longer works after tenant cutover.</span></span> |<ul><li><span data-ttu-id="3aa25-162">SharePoint Online 및 비즈니스용 OneDrive에서 Outlook을 통해 항목을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-162">In SharePoint Online and OneDrive for Business, you can share items via Outlook.</span></span> <span data-ttu-id="3aa25-163">Outlook 단추를 누르면 공유 가능한 링크가 만들어지며 새 메시지로 Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="3aa25-163">After pressing the Outlook button, a shareable link is created and pushed into a new message in the Outlook Web App.</span></span></li><li><span data-ttu-id="3aa25-164">테넌트가 잘리면 이 공유 방법이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-164">After tenant cutover, this method of sharing won't work.</span></span> <span data-ttu-id="3aa25-165">이 문제는 알려진 문제로 인식하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-165">We recognize this is a known issue.</span></span> <span data-ttu-id="3aa25-166">그러나 이 Outlook 기능은 사용되지 않는 경로에 있는 것이기 때문에 사용되지 않는 기능이 롤아웃될 때까지 이 문제를 해결할 계획이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-166">However, since this Outlook feature is in the path of deprecation, fixing the issue is not planned until the deprecation is rolled out.</span></span> </li></ul>|
||||

## <a name="exchange-online"></a><span data-ttu-id="3aa25-167">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3aa25-167">Exchange Online</span></span>
<span data-ttu-id="3aa25-168">**적용 사항:** 하이브리드 Exchange 구성을 사용하는 고객</span><span class="sxs-lookup"><span data-stu-id="3aa25-168">**Applies to**: Customers using a hybrid Exchange configuration</span></span>

| <span data-ttu-id="3aa25-169">Step(s)</span><span class="sxs-lookup"><span data-stu-id="3aa25-169">Step(s)</span></span> | <span data-ttu-id="3aa25-170">설명</span><span class="sxs-lookup"><span data-stu-id="3aa25-170">Description</span></span> | <span data-ttu-id="3aa25-171">영향</span><span class="sxs-lookup"><span data-stu-id="3aa25-171">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3aa25-172">Office 365 서비스에 대해 HCW(하이브리드 구성 마법사)를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-172">Rerun Hybrid Configuration wizard (HCW) against Office 365 services.</span></span> | <span data-ttu-id="3aa25-173">기존 HCW 구성은 도이클란드 Microsoft 클라우드를 지원하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-173">The existing HCW configuration is meant to support Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="3aa25-174">Exchange 서비스 마이그레이션이 완료되면 도이치란드 Microsoft 클라우드에서 사내 구성을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-174">With migration of Exchange services complete, we decouple on-premises configuration from Microsoft Cloud Deutschland.</span></span> |<ul><li><span data-ttu-id="3aa25-175">필수 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-175">Required action.</span></span> <span data-ttu-id="3aa25-176">이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-176">Failure to do so may result in failure of the service or of software clients.</span></span> <span data-ttu-id="3aa25-177">Exchange 사서함 마이그레이션이 시작되기 전에(5일 이상의 알림이 제공된 경우) 사서함의 온보드 또는 오프보더 이동을 중지하고 삭제해야 한다고 클라이언트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-177">Before Exchange mailbox migration begins (with 5 or more days of notice), notify clients that they should stop and delete any onboarding or offboarding moves of their mailboxes.</span></span>  <span data-ttu-id="3aa25-178">그렇지 않은 경우 이동 요청에 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-178">If they don't, they'll see errors in their move requests.</span></span> </li><li><span data-ttu-id="3aa25-179">Exchange 사서함 마이그레이션이 완료되면 온보드 및 오프보더 이동을 다시 시작할 수 있도록 클라이언트에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-179">After Exchange mailbox migration is complete, notify clients that they can resume onboarding and offboarding moves.</span></span> <br> <span data-ttu-id="3aa25-180">Microsoft 클라우드에서 Office 365 서비스로 Exchange를 마이그레이션하는 동안 PowerShell cmdlet인 **Test-MigrationServerAvailabiilty를** 실행하면 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-180">Running **Test-MigrationServerAvailabiilty**, a PowerShell cmdlet, during migration of Exchange from Microsoft Cloud Deutschland to Office 365 services might not work.</span></span> <span data-ttu-id="3aa25-181">그러나 마이그레이션이 완료된 후 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-181">However, it will work properly after migration is complete.</span></span> </li><li><span data-ttu-id="3aa25-182">사서함이 마이그레이션된 후 클라이언트에서 자격 증명 또는 권한 부여에 문제가 있는 경우 사용자는 를 실행하거나 ECP(Exchange 제어판)를 사용하여 동일하게 설정하여 마이그레이션 끝점에서 자신의 사내 관리자 자격 증명을 다시 입력할 수 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa25-182">If clients run into issues with credentials or authorization after mailboxes are migrated, users can reenter their on-premises administrator credentials in the migration endpoint by running `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)`, or by setting the same by using Exchange Control Panel (ECP).</span></span> </li></ul>|
