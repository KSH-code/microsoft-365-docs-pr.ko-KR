---
title: 21Vianet에서 운영하는 Office 365에 대한 Azure Information Protection 지원
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
description: 21Vianet에서 운영하는 Office 365용 AIP(Azure Information Protection)와 중국 고객의 AIP(Azure Information Protection)를 구성하는 방법을 자세히 설명합니다.
monikerRange: o365-21vianet
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418035"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="46db2-103">21Vianet에서 운영하는 Office 365에 대한 Azure Information Protection 지원</span><span class="sxs-lookup"><span data-stu-id="46db2-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="46db2-104">이 문서에서는 21Vianet에서 운영하는 Office 365에 대한 AIP(Azure Information Protection) 지원과 상업용 제품 간의 차이점과 AIP-프레미스 스캐너를 설치하고 콘텐츠 검색 작업을 관리하는 방법을 포함하여 중국의 고객을 위해 AIP를 구성하기 위한 특정 지침을 &mdash; 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="46db2-105">21Vianet에서 운영하는 Office 365용 AIP와 상업용 제품 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="46db2-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="46db2-106">21Vianet에서 운영하는 Office 365용 AIP를 통해 중국 고객에게 모든 상용 기능과 기능을 제공하는 것이 목표지만, 강조 표시하고자 하는 몇 가지 누락된 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="46db2-107">다음 목록에는 21Vianet에서 운영하는 Office 365용 AIP와 2021년 1월 현재 상업용 제품 간의 기존 간격이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="46db2-108">IRM(정보 권한 관리)은 엔터프라이즈용 Microsoft 365 앱(빌드 11731.10000 이상)에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="46db2-109">Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="46db2-110">AD RMS(Active Directory Rights Management Services)에서 AIP로의 마이그레이션은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="46db2-111">상용 클라우드의 사용자와 보호된 전자 메일 공유가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="46db2-112">현재 상업용 클라우드의 사용자와 문서 및 전자 메일 첨부 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="46db2-113">여기에는 상용 클라우드의 21Vianet 사용자가 운영하는 Office 365, 상업용 클라우드의 21Vianet 사용자가 운영하는 비 Office 365 사용자 및 개인용 RMS 라이선스가 있는 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="46db2-114">SharePoint(IRM으로 보호된 사이트 및 라이브러리)를 사용하는 IRM은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="46db2-115">AD RMS용 모바일 장치 확장을 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="46db2-116">모바일 [뷰어는](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="46db2-117">중국 고객은 Azure Portal의 AIP 영역을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="46db2-118">포털에서 작업(예: 사내 스캐너 설치 및 콘텐츠 검색 작업 관리)을 수행하는 대신 [PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="46db2-119">중국 고객의 AIP 구성</span><span class="sxs-lookup"><span data-stu-id="46db2-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="46db2-120">중국 고객의 AIP를 구성하는 경우:</span><span class="sxs-lookup"><span data-stu-id="46db2-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="46db2-121">[테넌트에 대한 권한 관리를 사용하도록 설정](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="46db2-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="46db2-122">[DNS 암호화를 구성합니다.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="46db2-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="46db2-123">AIP 통합 레이블 클라이언트를 [설치하고 구성합니다.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="46db2-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="46db2-124">[Windows에서 AIP 앱을 구성합니다.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="46db2-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="46db2-125">[AIP 사내 스캐너를 설치하고 콘텐츠 검사 작업을 관리합니다.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="46db2-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="46db2-126">1단계: 테넌트에 대한 권한 관리 사용</span><span class="sxs-lookup"><span data-stu-id="46db2-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="46db2-127">암호화가 제대로 작동하려면 테넌트에 대해 RMS를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="46db2-128">RMS를 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="46db2-129">관리자 권한으로 PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="46db2-130">AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="46db2-131">를 사용하여 모듈을 가져올 수 `Import-Module AipService` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="46db2-132">를 사용하여 서비스에 `Connect-AipService -environmentname azurechinacloud` 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="46db2-133">를 `(Get-AipServiceConfiguration).FunctionalState` 실행하고 상태가 입니다. `Enabled`</span><span class="sxs-lookup"><span data-stu-id="46db2-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="46db2-134">기능 상태가 인 경우 `Disabled` 를 `Enable-AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="46db2-135">2단계: DNS 암호화 구성</span><span class="sxs-lookup"><span data-stu-id="46db2-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="46db2-136">암호화가 제대로 작동하려면 Office 클라이언트 응용 프로그램이 서비스의 중국 인스턴스에 연결하고 해당 서비스에서 부트스트스트프를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="46db2-137">클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테넌트 관리자가 Azure RMS URL에 대한 정보를 사용하여 DNS SRV 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="46db2-138">DNS SRV 레코드가 없는 경우 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 연결하려고 시도하며 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="46db2-139">또한 사용자가 테넌트 소유 도메인을 기반으로 사용자 이름(예: )을 사용하여 로그인하고 사용자 이름(예: )을 사용하여 로그인할 것으로 `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="46db2-140">사용자 이름의 도메인 이름은 올바른 서비스 인스턴스로의 DNS 리디렉션에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="46db2-141">DNS 암호화 구성 - Windows</span><span class="sxs-lookup"><span data-stu-id="46db2-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="46db2-142">RMS ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="46db2-143">관리자 권한으로 PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="46db2-144">AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="46db2-145">를 사용하여 서비스에 `Connect-AipService -environmentname azurechinacloud` 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="46db2-146">`(Get-AipServiceConfiguration).RightsManagementServiceId`RMS ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="46db2-147">DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="46db2-148">서비스 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="46db2-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="46db2-149">프로토콜 = `_http`</span><span class="sxs-lookup"><span data-stu-id="46db2-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="46db2-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="46db2-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="46db2-151">대상 = `[GUID].rms.aadrm.cn` (여기서 GUID는 RMS ID)</span><span class="sxs-lookup"><span data-stu-id="46db2-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="46db2-152">Priority, Weight, Seconds, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="46db2-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="46db2-153">Azure Portal의 테넌트와 사용자 지정 [도메인을 연결합니다.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="46db2-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="46db2-154">이렇게 하면 DNS에 항목이 추가됩니다. DNS 설정에 값을 추가한 후 확인되는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="46db2-155">해당하는 전역 관리자 자격 증명으로 Microsoft 365 관리 센터에 로그인하고 사용자 만들기를 위한 도메인(예: `contoso.cn` )을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="46db2-156">확인 프로세스에서는 DNS를 추가로 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="46db2-157">확인이 완료되면 사용자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="46db2-158">DNS 암호화 구성 - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="46db2-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="46db2-159">DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="46db2-160">서비스 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="46db2-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="46db2-161">프로토콜 = `_http`</span><span class="sxs-lookup"><span data-stu-id="46db2-161">Protocol = `_http`</span></span>
- <span data-ttu-id="46db2-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="46db2-162">Name = `_tcp`</span></span>
- <span data-ttu-id="46db2-163">대상 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="46db2-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="46db2-164">포트 = `80`</span><span class="sxs-lookup"><span data-stu-id="46db2-164">Port = `80`</span></span>
- <span data-ttu-id="46db2-165">Priority, Weight, Seconds, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="46db2-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="46db2-166">3단계: AIP 통합 레이블 클라이언트 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="46db2-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="46db2-167">Microsoft 다운로드 센터에서 AIP 통합 레이블 [클라이언트를 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="46db2-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="46db2-168">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46db2-168">For more information, see:</span></span>

- [<span data-ttu-id="46db2-169">AIP 설명서</span><span class="sxs-lookup"><span data-stu-id="46db2-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="46db2-170">AIP 버전 기록 및 지원 정책</span><span class="sxs-lookup"><span data-stu-id="46db2-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="46db2-171">AIP 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="46db2-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="46db2-172">AIP 빠른 시작: AIP 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="46db2-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="46db2-173">AIP 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="46db2-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="46db2-174">AIP 사용자 가이드</span><span class="sxs-lookup"><span data-stu-id="46db2-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="46db2-175">Microsoft 365 민감도 레이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="46db2-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="46db2-176">4단계: Windows에서 AIP 앱 구성</span><span class="sxs-lookup"><span data-stu-id="46db2-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="46db2-177">Windows의 AIP 앱은 Azure China에 대한 올바른 주권 클라우드를 표시하기 위해 다음 레지스트리 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="46db2-178">레지스트리 노드 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="46db2-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="46db2-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="46db2-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="46db2-180">값 = `6` (기본값 = 0)</span><span class="sxs-lookup"><span data-stu-id="46db2-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="46db2-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="46db2-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46db2-182">제거 후 레지스트리 키를 삭제하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="46db2-183">키가 비어 있거나, 잘못되거나, 존재하지 않는 경우에는 기능이 기본값(상업용 클라우드의 경우 기본값 = 0)으로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="46db2-184">키가 비어 있거나 올바르지 않은 경우 로그에 인쇄 오류도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="46db2-185">5단계: AIP 사내 스캐너 설치 및 콘텐츠 검사 작업 관리</span><span class="sxs-lookup"><span data-stu-id="46db2-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="46db2-186">AIP-프레미스 스캐너를 설치하여 네트워크 및 콘텐츠 공유에서 중요한 데이터를 검색하고 조직의 정책에 구성된 분류 및 보호 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="46db2-187">[Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 명령에 대해 Azure AD 응용 프로그램을  만들고 구성할 때  API 요청 창에는 **조직에서 Microsoft API** 탭 대신 탭을 사용하는 API가 표시됩니다. 조직에서 **사용하는 API를** 선택한 다음 **Azure 권한 관리 서비스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46db2-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="46db2-188">스캐너를 설치하고 콘텐츠 검색 작업을 관리할 때 상업용 제품에서 사용하는 Azure Portal 인터페이스 대신 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="46db2-189">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="46db2-189">Cmdlet</span></span> | <span data-ttu-id="46db2-190">설명</span><span class="sxs-lookup"><span data-stu-id="46db2-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="46db2-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="46db2-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="46db2-192">콘텐츠 검색 작업에서 새 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="46db2-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="46db2-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="46db2-194">콘텐츠 검색 작업의 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="46db2-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="46db2-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="46db2-196">콘텐츠 검색 작업에서 정의된 리포지토리에 대한 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="46db2-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="46db2-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="46db2-198">콘텐츠 검색 작업을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="46db2-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="46db2-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="46db2-200">콘텐츠 검색 작업에서 리포지토리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="46db2-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="46db2-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="46db2-202">콘텐츠 검색 작업의 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="46db2-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="46db2-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="46db2-204">콘텐츠 검색 작업의 기존 리포지토리에 대한 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="46db2-205">스캐너를 [설치할 때](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner) [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 명령에서 동일한 클러스터 이름을 사용하여 여러 스캐너 노드를 동일한 클러스터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="46db2-206">여러 스캐너 노드에 동일한 클러스터를 사용하면 여러 스캐너가 함께 작동하여 스캔을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="46db2-207">[Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet을 사용하여 클러스터에 대한 세부 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="46db2-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="46db2-208">자세한 내용은 [Azure Information Protection](/azure/information-protection/deploy-aip-scanner) 통합 레이블 지정 스캐너란? 및 [PowerShell만](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)사용하여 콘텐츠 검사 작업 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46db2-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>