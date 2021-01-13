---
title: 21Vianet에서 운영하는 Office 365용 Azure Information Protection과 상업용 제품 간의 패리티
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 21Vianet에서 운영하는 Office 365용 AIP(Azure Information Protection)와 중국 고객을 위해 AIP를 구성하는 방법에 대해 자세히 알아보고
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840304"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="6d437-103">21Vianet에서 운영하는 Office 365용 Azure Information Protection과 상업용 제품 간의 패리티</span><span class="sxs-lookup"><span data-stu-id="6d437-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="6d437-104">21Vianet에서 운영하는 Office 365용 AIP(Azure Information Protection)를 사용하여 중국 고객에게 모든 상업적 기능을 제공하는 것이 목표지만, 강조하고자 하는 몇 가지 누락된 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="6d437-105">다음 목록에는 21Vianet에서 운영하는 Office 365용 Azure Information Protection과 2021년 1월 현재 상업용 제품 간의 기존 간격이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="6d437-106">IRM(정보 권한 관리)은 엔터프라이즈용 Microsoft 365 앱(빌드 11731.10000 이상)에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="6d437-107">Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="6d437-108">AD RMS(Active Directory Rights Management Services)에서 Azure Information Protection으로 마이그레이션하는 것은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="6d437-109">상용 클라우드의 사용자에게 보호된 전자 메일 공유가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="6d437-110">현재 상업용 클라우드의 사용자에게 문서 및 전자 메일 첨부 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="6d437-111">여기에는 상용 클라우드의 21Vianet 사용자가 운영하는 Office 365, 상업용 클라우드의 21Vianet 사용자가 운영하는 비 Office 365 사용자 및 개인용 RMS 라이선스가 있는 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="6d437-112">SharePoint(IRM으로 보호된 사이트 및 라이브러리)를 사용하는 IRM은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="6d437-113">AD RMS용 모바일 장치 확장은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="6d437-114">모바일 [뷰어는](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="6d437-115">중국 고객의 Azure Information Protection 구성</span><span class="sxs-lookup"><span data-stu-id="6d437-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="6d437-116">테넌트에 대한 권한 관리 사용</span><span class="sxs-lookup"><span data-stu-id="6d437-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="6d437-117">암호화가 제대로 작동하려면 테넌트에 대해 RMS를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="6d437-118">RMS가 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="6d437-119">관리자 권한으로 PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="6d437-120">AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="6d437-121">.를 사용하여 모듈을 가져올 `Import-Module AipService` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="6d437-122">.를 사용하여 서비스에 `Connect-AipService -environmentname azurechinacloud` 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="6d437-123">실행 `(Get-AipServiceConfiguration).FunctionalState` 및 상태 확인 `Enabled`</span><span class="sxs-lookup"><span data-stu-id="6d437-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="6d437-124">기능 상태가면 `Disabled` 다음을 `Enable-AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="6d437-125">암호화에 대한 DNS 구성(Windows)</span><span class="sxs-lookup"><span data-stu-id="6d437-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="6d437-126">암호화가 제대로 작동하려면 Office 클라이언트 응용 프로그램이 서비스의 중국 인스턴스에 연결하고 이 인스턴스에서 부트스트라프를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="6d437-127">클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테넌트 관리자가 Azure RMS URL에 대한 정보를 사용하여 DNS SRV 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="6d437-128">DNS SRV 레코드가 없는 경우 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 연결하려고 시도하며 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="6d437-129">또한 사용자가 테넌트 소유 도메인(예: 사용자 이름)을 기반으로 사용자 이름(예: )을 사용하여 로그인할 것으로 `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="6d437-130">사용자 이름의 도메인 이름은 올바른 서비스 인스턴스로 DNS 리디렉션에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="6d437-131">RMS ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="6d437-132">관리자 권한으로 PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="6d437-133">AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="6d437-134">.를 사용하여 서비스에 `Connect-AipService -environmentname azurechinacloud` 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="6d437-135">실행하여 `(Get-AipServiceConfiguration).RightsManagementServiceId` RMS ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="6d437-136">DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="6d437-137">서비스 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="6d437-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="6d437-138">프로토콜 = `_http`</span><span class="sxs-lookup"><span data-stu-id="6d437-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="6d437-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="6d437-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="6d437-140">Target = `[GUID].rms.aadrm.cn` (여기서 GUID는 RMS ID)</span><span class="sxs-lookup"><span data-stu-id="6d437-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="6d437-141">우선 순위, 가중치, 초, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="6d437-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="6d437-142">Azure Portal의 테넌트와 사용자 지정 [도메인을 연결합니다.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="6d437-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="6d437-143">이렇게 하면 DNS에 항목이 추가됩니다. DNS 설정에 값을 추가한 후 확인되는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="6d437-144">해당하는 전역 관리자 자격 증명으로 Microsoft 365 관리 센터에 로그인하고 사용자 만들기를 위한 도메인(예: `contoso.cn` )을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="6d437-145">확인 프로세스에서 추가 DNS 변경이 요구될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="6d437-146">확인이 완료되면 사용자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="6d437-147">암호화에 대한 DNS 구성(Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="6d437-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="6d437-148">DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="6d437-149">서비스 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="6d437-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="6d437-150">프로토콜 = `_http`</span><span class="sxs-lookup"><span data-stu-id="6d437-150">Protocol = `_http`</span></span>
- <span data-ttu-id="6d437-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="6d437-151">Name = `_tcp`</span></span>
- <span data-ttu-id="6d437-152">대상 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="6d437-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="6d437-153">포트 = `80`</span><span class="sxs-lookup"><span data-stu-id="6d437-153">Port = `80`</span></span>
- <span data-ttu-id="6d437-154">우선 순위, 가중치, 초, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="6d437-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="6d437-155">AIP 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6d437-155">AIP client configuration</span></span>

<span data-ttu-id="6d437-156">통합 AIP 클라이언트는 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="6d437-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="6d437-157">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d437-157">For more information, see:</span></span>

- [<span data-ttu-id="6d437-158">Azure Information Protection 설명서</span><span class="sxs-lookup"><span data-stu-id="6d437-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="6d437-159">AIP 버전 기록 및 지원 정책</span><span class="sxs-lookup"><span data-stu-id="6d437-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="6d437-160">AIP 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d437-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="6d437-161">AIP 빠른 시작: AIP 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="6d437-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="6d437-162">AIP 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="6d437-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="6d437-163">AIP 사용자 가이드</span><span class="sxs-lookup"><span data-stu-id="6d437-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="6d437-164">Microsoft 365 민감도 레이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6d437-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="6d437-165">AIP 앱 구성(통합 레이블 클라이언트만 해당)</span><span class="sxs-lookup"><span data-stu-id="6d437-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="6d437-166">통합 레이블 솔루션의 경우 Windows의 AIP 앱에 Azure China의 올바른 주권 클라우드를 지정하기 위해 다음 레지스트리 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="6d437-167">레지스트리 노드 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="6d437-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="6d437-168">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="6d437-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="6d437-169">값 = `6` (기본값 = 0)</span><span class="sxs-lookup"><span data-stu-id="6d437-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="6d437-170">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="6d437-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d437-171">제거 후 레지스트리 키를 삭제하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="6d437-172">키가 비어 있거나, 잘못되거나, 존재하지 않는 경우 기능이 기본값(상업용 클라우드의 경우 기본값 = 0)으로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="6d437-173">키가 비어 있거나 올바르지 않은 경우 로그에 인쇄 오류가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="6d437-174">Azure Information Protection 콘텐츠 검사 작업 관리</span><span class="sxs-lookup"><span data-stu-id="6d437-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="6d437-175">Azure China 스캐너 서버에서 Azure Information Protection 콘텐츠 검색 작업을 관리하기 위해 Azure Portal 대신 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="6d437-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6d437-176">Cmdlet</span></span> | <span data-ttu-id="6d437-177">설명</span><span class="sxs-lookup"><span data-stu-id="6d437-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="6d437-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="6d437-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="6d437-179">콘텐츠 검색 작업에서 새 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="6d437-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="6d437-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="6d437-181">콘텐츠 검색 작업의 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="6d437-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="6d437-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="6d437-183">콘텐츠 검색 작업을 위해 정의된 리포지토리에 대한 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="6d437-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="6d437-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="6d437-185">콘텐츠 검색 작업을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="6d437-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="6d437-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="6d437-187">콘텐츠 검색 작업에서 리포지토리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="6d437-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="6d437-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="6d437-189">콘텐츠 검색 작업의 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="6d437-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="6d437-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="6d437-191">콘텐츠 검색 작업의 기존 리포지토리에 대한 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6d437-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="6d437-192">자세한 내용은 PowerShell만 사용하여 콘텐츠 검사 작업 [관리를 참조하세요.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="6d437-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>