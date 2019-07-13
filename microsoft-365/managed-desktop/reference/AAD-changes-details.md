---
title: Azure Active Directory 테 넌 트 세부 정보
description: 이 항목에서는 Microsoft Managed Desktop에서 등록할 때 AAD 계정의 변경 사항에 대해 설명 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643949"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="03aff-104">Azure Active Directory 테 넌 트 세부 정보</span><span class="sxs-lookup"><span data-stu-id="03aff-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="03aff-105">{gory 계정, API calls, perms 등)에 대 한 세부 정보}</span><span class="sxs-lookup"><span data-stu-id="03aff-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="03aff-106">AAD 계정에 전송 되는 데이터</span><span class="sxs-lookup"><span data-stu-id="03aff-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="03aff-107">Microsoft의 계정으로 전송 되는 데이터:</span><span class="sxs-lookup"><span data-stu-id="03aff-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="03aff-108">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="03aff-108">Group names</span></span>
- <span data-ttu-id="03aff-109">보안 정책 구성</span><span class="sxs-lookup"><span data-stu-id="03aff-109">Security policy configuration</span></span>
- <span data-ttu-id="03aff-110">장치 주문</span><span class="sxs-lookup"><span data-stu-id="03aff-110">Device orders</span></span>
- <span data-ttu-id="03aff-111">사용자 계정 (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span><span class="sxs-lookup"><span data-stu-id="03aff-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="03aff-112">E5 사용자 계정에 대 한 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="03aff-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="03aff-113">업데이트 링에 대 한 Windows update 정책</span><span class="sxs-lookup"><span data-stu-id="03aff-113">Windows update policies for update rings</span></span>

<span data-ttu-id="03aff-114">계정에서 Microsoft로 전송 되는 데이터:</span><span class="sxs-lookup"><span data-stu-id="03aff-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="03aff-115">장치 업데이트, 사용 현황 및 안정성 데이터</span><span class="sxs-lookup"><span data-stu-id="03aff-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="03aff-116">앱 배포 및 안정성 데이터</span><span class="sxs-lookup"><span data-stu-id="03aff-116">App deployment and reliability data</span></span>
- <span data-ttu-id="03aff-117">업데이트 및 보안 정책 배포 데이터</span><span class="sxs-lookup"><span data-stu-id="03aff-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="03aff-118">장치에 할당 된 사용자</span><span class="sxs-lookup"><span data-stu-id="03aff-118">Users assigned to devices</span></span>  

<span data-ttu-id="03aff-119">계정에서 전송 되는 데이터는 미국 내에서 호스트 되는 Microsoft 테 넌 트의 Azure SQL 데이터베이스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03aff-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="03aff-120">데이터는 {Microsoft Azure security}에 설명 된 정책에 따라 저장 및 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03aff-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="03aff-121">API 사용 권한 및 통화</span><span class="sxs-lookup"><span data-stu-id="03aff-121">API permissions and calls</span></span>

<span data-ttu-id="03aff-122">**등록 중:**</span><span class="sxs-lookup"><span data-stu-id="03aff-122">**During enrollment:**</span></span>

<span data-ttu-id="03aff-123">API 사용 권한:</span><span class="sxs-lookup"><span data-stu-id="03aff-123">API permissions:</span></span>
- <span data-ttu-id="03aff-124">DeviceManagementServiceConfig All</span><span class="sxs-lookup"><span data-stu-id="03aff-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-125">Directory AccessAsUser. 모든</span><span class="sxs-lookup"><span data-stu-id="03aff-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="03aff-126">사용자. ReadWrite. 모두</span><span class="sxs-lookup"><span data-stu-id="03aff-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-127">DeviceManagementConfiguration All</span><span class="sxs-lookup"><span data-stu-id="03aff-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-128">DeviceManagementManagedDevices All</span><span class="sxs-lookup"><span data-stu-id="03aff-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-129">그룹. a i a. 모두</span><span class="sxs-lookup"><span data-stu-id="03aff-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="03aff-130">API 호출:</span><span class="sxs-lookup"><span data-stu-id="03aff-130">API calls:</span></span>
- <span data-ttu-id="03aff-131">게시물/organization/{organizationId}/setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="03aff-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="03aff-132">GET/POST/directory역할/구성원 id</span><span class="sxs-lookup"><span data-stu-id="03aff-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="03aff-133">GET/POST/users</span><span class="sxs-lookup"><span data-stu-id="03aff-133">GET/POST /users</span></span>
- <span data-ttu-id="03aff-134">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="03aff-134">GET/POST /groups</span></span>
- <span data-ttu-id="03aff-135">PATCH/p/p/{id}</span><span class="sxs-lookup"><span data-stu-id="03aff-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="03aff-136">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="03aff-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="03aff-137">/DeviceManagement/detectedApps 가져오기</span><span class="sxs-lookup"><span data-stu-id="03aff-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="03aff-138">**등록 후 일반적인 관리 작업을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="03aff-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="03aff-139">API 사용 권한:</span><span class="sxs-lookup"><span data-stu-id="03aff-139">API permissions:</span></span>
- <span data-ttu-id="03aff-140">DeviceManagementManagedDevices All</span><span class="sxs-lookup"><span data-stu-id="03aff-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-141">DeviceManagementApps All</span><span class="sxs-lookup"><span data-stu-id="03aff-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-142">DeviceManagementConfiguration All</span><span class="sxs-lookup"><span data-stu-id="03aff-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-143">보고서. 모두</span><span class="sxs-lookup"><span data-stu-id="03aff-143">Reports.Read.All</span></span>
- <span data-ttu-id="03aff-144">사용자. ReadWrite. 모두</span><span class="sxs-lookup"><span data-stu-id="03aff-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-145">그룹. a i a. 모두</span><span class="sxs-lookup"><span data-stu-id="03aff-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="03aff-146">Directory AccessAsUser. 모든</span><span class="sxs-lookup"><span data-stu-id="03aff-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="03aff-147">API 호출:</span><span class="sxs-lookup"><span data-stu-id="03aff-147">API calls:</span></span>
- <span data-ttu-id="03aff-148">GET/POST/directory역할/구성원 id</span><span class="sxs-lookup"><span data-stu-id="03aff-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="03aff-149">GET/PATCH/POST/users</span><span class="sxs-lookup"><span data-stu-id="03aff-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="03aff-150">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="03aff-150">GET/POST /groups</span></span>
- <span data-ttu-id="03aff-151">PATCH/p/p/{id}</span><span class="sxs-lookup"><span data-stu-id="03aff-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="03aff-152">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="03aff-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="03aff-153">GET/POST/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="03aff-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="03aff-154">/DeviceManagement/detectedApps 가져오기</span><span class="sxs-lookup"><span data-stu-id="03aff-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="03aff-155">GET/devices</span><span class="sxs-lookup"><span data-stu-id="03aff-155">GET /devices</span></span>
- <span data-ttu-id="03aff-156">게시물/사용자/{id | userPrincipalName}/라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="03aff-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="03aff-157">/SubscribedSkus 가져오기</span><span class="sxs-lookup"><span data-stu-id="03aff-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="03aff-158">Microsoft Managed Desktop에서 사용 되는 계정</span><span class="sxs-lookup"><span data-stu-id="03aff-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="03aff-159">Account</span><span class="sxs-lookup"><span data-stu-id="03aff-159">Account</span></span> | <span data-ttu-id="03aff-160">설명</span><span class="sxs-lookup"><span data-stu-id="03aff-160">Description</span></span>  | <span data-ttu-id="03aff-161">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="03aff-161">Conditional access</span></span>  | <span data-ttu-id="03aff-162">Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="03aff-162">Multi-factor authentication</span></span>  | <span data-ttu-id="03aff-163">정상 인 이유</span><span class="sxs-lookup"><span data-stu-id="03aff-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="03aff-164">msadmin @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="03aff-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="03aff-165">Microsoft Intune 및 사용자 관리자로 사용 되는 제한 된 서비스 계정 (관리자 권한) {what?}</span><span class="sxs-lookup"><span data-stu-id="03aff-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="03aff-166">Microsoft 최신 데스크톱 장치에 대 한 테 넌 트를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="03aff-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="03aff-167">대화형 로그인 권한이 없습니다. 서비스를 통해서만 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03aff-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="03aff-168">네트워크에서 시작 되지 않으므로 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03aff-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="03aff-169">대화형 로그온이 없기 때문에 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03aff-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="03aff-170">Azure 키 자격 증명 모음에 저장 된 암호</span><span class="sxs-lookup"><span data-stu-id="03aff-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="03aff-171">mstest @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="03aff-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="03aff-172">mssupport @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="03aff-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="03aff-173">msadminint @ \* onmmicrosoft .com</span><span class="sxs-lookup"><span data-stu-id="03aff-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
