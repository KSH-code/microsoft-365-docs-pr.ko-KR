---
title: 21Vianet에서 Office 365 Azure Information Protection 지원
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: 21Vianet에서 운영하는 Office 365 AIP(Azure Information Protection)와 중국에서 고객을 위해 AIP를 구성하는 방법에 대해 자세히 설명합니다.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535845"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="986c3-103">21Vianet에서 Office 365 Azure Information Protection 지원</span><span class="sxs-lookup"><span data-stu-id="986c3-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="986c3-104">이 문서에서는 21Vianet에서 운영하는 Office 365 및 상업용 제품용 Azure Information Protection(AIP) 지원의 차이점과, AIP-프레미스 스캐너를 설치하고 콘텐츠 검색 작업을 관리하는 방법을 포함하여 중국 고객의 AIP를 구성하기 위한 구체적인 지침을 &mdash; 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="986c3-105">21Vianet에서 운영하는 Office 365 제품용 AIP의 차이점</span><span class="sxs-lookup"><span data-stu-id="986c3-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="986c3-106">21Vianet에서 운영하는 21Vianet 제품용 A Office 365 IP를 통해 중국 고객에게 모든 상용 기능과 기능을 제공하는 것이 목표지만, 강조 표시하고자 하는 몇 가지 누락된 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="986c3-107">다음 목록에는 21Vianet에서 운영하는 Office 365 AIP와 2021년 1월 현재 상업용 제품 간의 기존 간격이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="986c3-108">IRM(정보 권한 관리)은 엔터프라이즈용 Microsoft 365 앱(빌드 11731.10000 이상)에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="986c3-109">Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="986c3-110">AD RMS(Active Directory Rights Management Services)에서 AIP로의 마이그레이션은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="986c3-111">상용 클라우드의 사용자와 보호된 전자 메일 공유가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="986c3-112">현재 상업용 클라우드의 사용자와 문서 및 전자 메일 첨부 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="986c3-113">여기에는 Office 365 클라우드에서 21Vianet 사용자가 운영하는 Office 365, 상업용 클라우드의 21Vianet 사용자가 운영하지 않는 사용자 및 개인용 RMS 라이선스가 있는 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="986c3-114">IRM을 SharePoint(IRM으로 보호된 사이트 및 라이브러리)는 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="986c3-115">AD RMS용 모바일 장치 확장을 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="986c3-116">모바일 [뷰어는](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="986c3-117">중국 고객은 Azure Portal의 AIP 영역을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="986c3-118">포털에서 콘텐츠 검색 작업 관리 및 실행과 같은 작업을 수행하는 대신 [PowerShell](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="986c3-119">중국 고객의 AIP 구성</span><span class="sxs-lookup"><span data-stu-id="986c3-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="986c3-120">중국 고객의 AIP를 구성하는 경우:</span><span class="sxs-lookup"><span data-stu-id="986c3-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="986c3-121">[테넌트에 대한 권한 관리를 사용하도록 설정](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="986c3-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="986c3-122">[Microsoft Information Protection 동기화 서비스 서비스 사용자 를 추가합니다.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)</span><span class="sxs-lookup"><span data-stu-id="986c3-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="986c3-123">[DNS 암호화를 구성합니다.](#step-3-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="986c3-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="986c3-124">AIP 통합 레이블 클라이언트를 [설치하고 구성합니다.](#step-4-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="986c3-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="986c3-125">[에서 AIP 앱을 Windows.](#step-5-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="986c3-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="986c3-126">[AIP 사내 스캐너를 설치하고 콘텐츠 검사 작업을 관리합니다.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="986c3-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="986c3-127">1단계: 테넌트에 대한 권한 관리 사용</span><span class="sxs-lookup"><span data-stu-id="986c3-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="986c3-128">암호화가 제대로 작동하려면 테넌트에 대해 RMS를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="986c3-129">RMS를 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="986c3-130">관리자 권한으로 PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="986c3-131">AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="986c3-132">를 사용하여 모듈을 가져올 수 `Import-Module AipService` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="986c3-133">커넥트 를 사용하여 서비스에 대한 데이터 열기 `Connect-AipService -environmentname azurechinacloud`</span><span class="sxs-lookup"><span data-stu-id="986c3-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="986c3-134">를 `(Get-AipServiceConfiguration).FunctionalState` 실행하고 상태가 입니다. `Enabled`</span><span class="sxs-lookup"><span data-stu-id="986c3-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="986c3-135">기능 상태가 인 경우 `Disabled` 를 `Enable-AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="986c3-136">2단계: Microsoft Information Protection 동기화 서비스 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="986c3-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="986c3-137">**Microsoft Information Protection Sync Service 서비스** 계정은 Azure China 테넌트에서 기본적으로 사용할 수 없습니다. Azure Information Protection에는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="986c3-138">[New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet 및 Microsoft Information Protection Sync Service의 응용 프로그램 ID를 사용하여 이 서비스 계정을 수동으로 `870c4f2e-85b6-4d43-bdda-6ed9a579b725` 만드하십시오.</span><span class="sxs-lookup"><span data-stu-id="986c3-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="986c3-139">서비스 사용자 추가 후 서비스에 필요한 관련 권한을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="986c3-140">3단계: DNS 암호화 구성</span><span class="sxs-lookup"><span data-stu-id="986c3-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="986c3-141">암호화가 제대로 작동하려면 Office 클라이언트 응용 프로그램이 서비스 중국 인스턴스에 연결하고 해당 인스턴스에서 부트스트스트프를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="986c3-142">클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테넌트 관리자가 Azure RMS URL에 대한 정보를 사용하여 DNS SRV 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="986c3-143">DNS SRV 레코드가 없는 경우 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 연결하려고 시도하며 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="986c3-144">또한 사용자가 테넌트 소유 도메인을 기반으로 사용자 이름(예: )을 사용하여 로그인하고 사용자 이름(예: )을 사용하여 로그인할 것으로 `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="986c3-145">사용자 이름의 도메인 이름은 올바른 서비스 인스턴스로의 DNS 리디렉션에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="986c3-146">DNS 암호화 구성 - Windows</span><span class="sxs-lookup"><span data-stu-id="986c3-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="986c3-147">RMS ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="986c3-148">관리자 권한으로 PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="986c3-149">AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="986c3-150">커넥트 를 사용하여 서비스에 대한 데이터 열기 `Connect-AipService -environmentname azurechinacloud`</span><span class="sxs-lookup"><span data-stu-id="986c3-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="986c3-151">`(Get-AipServiceConfiguration).RightsManagementServiceId`RMS ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="986c3-152">DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="986c3-153">서비스 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="986c3-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="986c3-154">프로토콜 = `_http`</span><span class="sxs-lookup"><span data-stu-id="986c3-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="986c3-155">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="986c3-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="986c3-156">대상 = `[GUID].rms.aadrm.cn` (여기서 GUID는 RMS ID)</span><span class="sxs-lookup"><span data-stu-id="986c3-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="986c3-157">Priority, Weight, Seconds, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="986c3-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="986c3-158">Azure Portal의 테넌트와 사용자 지정 [도메인을 연결합니다.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="986c3-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="986c3-159">이렇게 하면 DNS에 항목이 추가됩니다. DNS 설정에 값을 추가한 후 확인되는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="986c3-160">해당 전역 Microsoft 365 자격 증명으로 Microsoft 365 관리 센터에 로그인하고 사용자 만들기를 위해 도메인(예: `contoso.cn` )을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="986c3-161">확인 프로세스에서는 DNS를 추가로 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="986c3-162">확인이 완료되면 사용자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="986c3-163">DNS 암호화 구성 - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="986c3-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="986c3-164">DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="986c3-165">서비스 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="986c3-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="986c3-166">프로토콜 = `_http`</span><span class="sxs-lookup"><span data-stu-id="986c3-166">Protocol = `_http`</span></span>
- <span data-ttu-id="986c3-167">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="986c3-167">Name = `_tcp`</span></span>
- <span data-ttu-id="986c3-168">대상 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="986c3-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="986c3-169">포트 = `80`</span><span class="sxs-lookup"><span data-stu-id="986c3-169">Port = `80`</span></span>
- <span data-ttu-id="986c3-170">Priority, Weight, Seconds, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="986c3-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="986c3-171">4단계: AIP 통합 레이블 클라이언트 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="986c3-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="986c3-172">Microsoft 다운로드 센터에서 AIP 통합 레이블 클라이언트를 다운로드하여 [설치합니다.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="986c3-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="986c3-173">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="986c3-173">For more information, see:</span></span>

- [<span data-ttu-id="986c3-174">AIP 설명서</span><span class="sxs-lookup"><span data-stu-id="986c3-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="986c3-175">AIP 버전 기록 및 지원 정책</span><span class="sxs-lookup"><span data-stu-id="986c3-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="986c3-176">AIP 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="986c3-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="986c3-177">AIP 빠른 시작: AIP 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="986c3-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="986c3-178">AIP 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="986c3-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="986c3-179">AIP 사용자 가이드</span><span class="sxs-lookup"><span data-stu-id="986c3-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="986c3-180">민감도 Microsoft 365 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="986c3-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="986c3-181">5단계: 설치 시 AIP Windows</span><span class="sxs-lookup"><span data-stu-id="986c3-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="986c3-182">Azure의 AIP Windows Azure China에 대한 올바른 주권 클라우드를 설정하려면 다음 레지스트리 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="986c3-183">레지스트리 노드 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="986c3-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="986c3-184">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="986c3-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="986c3-185">값 = `6` (기본값 = 0)</span><span class="sxs-lookup"><span data-stu-id="986c3-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="986c3-186">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="986c3-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="986c3-187">제거 후 레지스트리 키를 삭제하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="986c3-188">키가 비어 있거나, 잘못되거나, 존재하지 않는 경우에는 기능이 기본값(상업용 클라우드의 경우 기본값 = 0)으로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="986c3-189">키가 비어 있거나 올바르지 않은 경우 로그에 인쇄 오류도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="986c3-190">6단계: AIP 사내 스캐너 설치 및 콘텐츠 검사 작업 관리</span><span class="sxs-lookup"><span data-stu-id="986c3-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="986c3-191">AIP-프레미스 스캐너를 설치하여 네트워크 및 콘텐츠 공유에서 중요한 데이터를 검색하고 조직의 정책에 구성된 분류 및 보호 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="986c3-192">콘텐츠 검색 작업을 구성하고 관리할 때 상업용 제품에서 사용하는 [Azure Portal](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) 인터페이스 대신 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="986c3-193">자세한 내용은 [Azure Information Protection](/azure/information-protection/deploy-aip-scanner) 통합 레이블 지정 스캐너란? 및 [PowerShell만](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)사용하여 콘텐츠 검사 작업 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="986c3-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="986c3-194">**스캐너를 설치 및 구성하려면:**</span><span class="sxs-lookup"><span data-stu-id="986c3-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="986c3-195">스캐너를 실행할 Windows Server 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="986c3-196">로컬 관리자 권한이 있으며 마스터 데이터베이스에 쓸 수 있는 권한이 있는 SQL Server 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="986c3-197">PowerShell을 닫은 후 시작</span><span class="sxs-lookup"><span data-stu-id="986c3-197">Start with PowerShell closed.</span></span> <span data-ttu-id="986c3-198">이전에 AIP 클라이언트 및 스캐너를 설치한 경우 **AIPScanner 서비스가** 중지된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="986c3-199">관리자 권한으로 Windows PowerShell 옵션을 사용하여 **세션을 런타합니다.**</span><span class="sxs-lookup"><span data-stu-id="986c3-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="986c3-200">[Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet을 실행하여 Azure Information Protection 스캐너에 대한 데이터베이스를 만들 SQL Server 인스턴스와 스캐너 클러스터에 대해 의미 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="986c3-201">[Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 명령에서 동일한 클러스터 이름을 사용하여 여러 스캐너 노드를 동일한 클러스터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="986c3-202">여러 스캐너 노드에 동일한 클러스터를 사용하면 여러 스캐너가 함께 작동하여 스캔을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="986c3-203">이제 관리 도구 서비스를 사용하여 **서비스가 설치되어 있는지**  >  **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="986c3-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="986c3-204">설치된 서비스의 이름은 **Azure Information Protection Scanner로,** 만든 스캐너 서비스 계정을 사용하여 실행하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="986c3-205">스캐너에 사용할 Azure 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="986c3-206">Azure AD 토큰을 사용하면 스캐너가 Azure Information Protection 서비스에 인증하여 대화형이 아닌 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="986c3-207">Azure Portal을 열고 Azure AD 응용 프로그램을 만들어 인증에 대한 액세스 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="986c3-208">자세한 내용은 Azure Information Protection에 대해 대화형이 아닌 파일에 레이블을 [지정하는 방법을 참조하세요.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="986c3-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="986c3-209">[Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 명령에 대해 Azure AD 응용 프로그램을  만들고 구성할 때  API 요청 창에는 **조직에서 Microsoft API** 탭 대신 탭을 사용하는 API가 표시됩니다. 조직에서 **사용하는 API를** 선택한 다음 **Azure 권한 관리 서비스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="986c3-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="986c3-210">Windows 서버 컴퓨터에서 스캐너 서비스 계정에 설치에 대한 로컬로  로그온 권한이 부여된 경우 이 계정으로 로그인하고 PowerShell 세션을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="986c3-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="986c3-211">스캐너 서비스 계정에 설치에 대한  로컬로 로그온 권한을 부여할 수 없는 경우 [Azure Information Protection에서](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)비대화형으로 파일에 레이블을 지정하는 방법에 설명된 바와 같이 *OnBehalfOf* 매개 변수를 [Set-AIPAuthentication과](/powershell/module/azureinformationprotection/set-aipauthentication)함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="986c3-212">[Set-AIPAuthentication을](/powershell/module/azureinformationprotection/set-aipauthentication)실행하여 Azure AD 응용 프로그램에서 복사된 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="986c3-213">예:</span><span class="sxs-lookup"><span data-stu-id="986c3-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="986c3-214">이제 스캐너에 Azure AD에 인증할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="986c3-215">이 토큰은 Azure AD의 웹 앱 **/API** 클라이언트 비밀 구성에 따라 1년, 2년 또는 절대 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="986c3-216">토큰이 만료되면 이 절차를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="986c3-217">[Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet을 실행하여 스캐너가 오프라인 모드에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="986c3-218">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="986c3-219">[Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet을 실행하여 기본 콘텐츠 검사 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="986c3-220">**Set-AIPScannerContentScanJob** cmdlet의 유일한 필수 매개 변수는 **Enforce입니다.**</span><span class="sxs-lookup"><span data-stu-id="986c3-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="986c3-221">그러나 현재 콘텐츠 검색 작업의 다른 설정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="986c3-222">예:</span><span class="sxs-lookup"><span data-stu-id="986c3-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="986c3-223">위의 구문은 구성을 계속하는 동안 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="986c3-224">스캐너 실행을 수동으로 *유지*</span><span class="sxs-lookup"><span data-stu-id="986c3-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="986c3-225">민감도 레이블 정책에 따라 검색할 정보 유형 설정</span><span class="sxs-lookup"><span data-stu-id="986c3-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="986c3-226">*민감도* 레이블 지정 정책을 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="986c3-227">민감도 레이블 정책에 정의된 기본 레이블을 사용하여 콘텐츠에 따라 파일에 자동으로 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="986c3-228">*파일레이블을* 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="986c3-229">검사 및 자동 레이블 지정 시 파일 세부 정보 보존(수정된 날짜, 마지막으로 수정한 날짜 및 값으로 *수정한* 날짜 포함) </span><span class="sxs-lookup"><span data-stu-id="986c3-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="986c3-230">실행 시 .msg 및 .tmp 파일을 제외할 스캐너 설정</span><span class="sxs-lookup"><span data-stu-id="986c3-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="986c3-231">스캐너를 실행하는 데 사용할 계정으로 기본 소유자 설정</span><span class="sxs-lookup"><span data-stu-id="986c3-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="986c3-232">[Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet을 사용하여 콘텐츠 검색 작업에서 검색할 리포지토리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="986c3-233">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="986c3-234">추가하는 리포지토리의 유형에 따라 다음 구문 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="986c3-235">네트워크 공유의 경우 를 사용 `\\Server\Folder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="986c3-236">SharePoint 라이브러리의 경우 를 사용 `http://sharepoint.contoso.com/Shared%20Documents/Folder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="986c3-237">로컬 경로의 경우: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="986c3-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="986c3-238">UNC 경로의 경우: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="986c3-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="986c3-239">와일드카드는 지원되지 않습니다. WebDav 위치는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="986c3-240">나중에 리포지토리를 수정하려면 [대신 Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="986c3-241">필요한 경우 다음 단계를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="986c3-242">검색 주기 실행 및 스캐너용 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="986c3-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="986c3-243">PowerShell을 사용하여 분류 및 보호를 적용하도록 스캐너 구성</span><span class="sxs-lookup"><span data-stu-id="986c3-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="986c3-244">PowerShell을 사용하여 스캐너를 사용하여 DLP 정책 구성</span><span class="sxs-lookup"><span data-stu-id="986c3-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="986c3-245">다음 표에는 스캐너 설치 및 콘텐츠 검사 작업 관리와 관련된 PowerShell cmdlet이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="986c3-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="986c3-246">Cmdlet</span></span> | <span data-ttu-id="986c3-247">설명</span><span class="sxs-lookup"><span data-stu-id="986c3-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="986c3-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="986c3-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="986c3-249">콘텐츠 검색 작업에서 새 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="986c3-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="986c3-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="986c3-251">클러스터에 대한 세부 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="986c3-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="986c3-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="986c3-253">콘텐츠 검색 작업의 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="986c3-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="986c3-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="986c3-255">콘텐츠 검색 작업에서 정의된 리포지토리에 대한 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="986c3-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="986c3-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="986c3-257">콘텐츠 검색 작업을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="986c3-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="986c3-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="986c3-259">콘텐츠 검색 작업에서 리포지토리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="986c3-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="986c3-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="986c3-261">콘텐츠 검색 작업의 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="986c3-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="986c3-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="986c3-263">콘텐츠 검색 작업의 기존 리포지토리에 대한 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="986c3-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="986c3-264">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="986c3-264">For more information, see:</span></span>

- [<span data-ttu-id="986c3-265">Azure Information Protection 통합 레이블 지정 스캐너란?</span><span class="sxs-lookup"><span data-stu-id="986c3-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="986c3-266">AIP(Azure Information Protection) 통합 레이블 지정 스캐너 구성 및 설치</span><span class="sxs-lookup"><span data-stu-id="986c3-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="986c3-267">[PowerShell만 사용하여 콘텐츠 검색 작업을 관리합니다.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="986c3-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
