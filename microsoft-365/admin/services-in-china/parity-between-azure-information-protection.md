---
title: 21Vianet에서 운영하는 Office 365
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
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
description: 21Vianet에서 운영 하는 Office 365의 Azure Information Protection에 대해 자세히 알아보고 중국의 고객을 위해이를 구성 하는 방법을 알아보세요.
monikerRange: o365-21vianet
ms.openlocfilehash: 1f5d73f5c421a545ea0085f018a2c2a703b0b374
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399041"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="81ee5-103">21Vianet 및 상업적 제공품에서 운영 하는 Office 365의 Azure Information Protection 간 패리티</span><span class="sxs-lookup"><span data-stu-id="81ee5-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="81ee5-104">Microsoft의 목표는 21Vianet에서 운영 하는 Office 365의 Azure Information Protection을 사용 하 여 중국의 고객에 게 모든 상업용 기능과 기능을 제공 하는 것 이며 몇 가지 기능을 강조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="81ee5-105">다음은 21Vianet에서 운영 하는 Office 365의 Azure Information Protection과 7 월 2019의 상용 제품 간의 기존 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="81ee5-106">IRM (정보 권한 관리)은 enterprise 용 Microsoft 365 Apps (빌드 11731.10000 이상)에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="81ee5-107">Office 2010, Office 2013 및 기타 Office 2016 버전은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="81ee5-108">AD RMS (Active Directory Rights Management Services)에서 Azure Information Protection으로의 마이그레이션을 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="81ee5-109">보호 된 전자 메일을 상업용 클라우드의 사용자에 게 공유 하는 기능은 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="81ee5-110">현재 상업용 클라우드의 사용자에 게 문서 및 전자 메일 첨부 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="81ee5-111">여기에는 상업용 클라우드의 21Vianet 사용자가 운영 하는 Office 365, 상업용 클라우드의 21Vianet 사용자가 운영 하는 Office 365 및 개별 라이선스에 대 한 RMS가 있는 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="81ee5-112">SharePoint (IRM으로 보호 된 사이트 및 라이브러리)가 포함 된 IRM을 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="81ee5-113">권한 관리 커넥터를 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="81ee5-114">AD RMS에 대 한 모바일 장치 확장을 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="81ee5-115">중국에서 고객에 대 한 Azure Information Protection 구성</span><span class="sxs-lookup"><span data-stu-id="81ee5-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="81ee5-116">테 넌 트에 대 한 권한 관리 사용</span><span class="sxs-lookup"><span data-stu-id="81ee5-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="81ee5-117">암호화가 제대로 작동 하려면 테 넌 트에 대해 RMS를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="81ee5-118">RMS가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="81ee5-119">관리자로 PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="81ee5-120">AIPService 모듈이 설치 되어 있지 않으면를 실행  `Install-Module AipService` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="81ee5-121">를 사용 하 여 모듈을 가져옵니다 `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="81ee5-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="81ee5-122">을 사용 하 여 서비스에 연결  `Connect-AipService -environmentname azurechinacloud` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="81ee5-123"> `(Get-AipServiceConfiguration).FunctionalState`   를 실행 하 고 상태가 인지 확인  `Enabled` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="81ee5-124">기능 상태가 이면  `Disabled` 를 실행  `Enable-AipService` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="81ee5-125">암호화에 대 한 DNS 구성 (Windows)</span><span class="sxs-lookup"><span data-stu-id="81ee5-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="81ee5-126">암호화가 제대로 작동 하려면 Office 클라이언트 응용 프로그램에서 중국 서비스 인스턴스에 연결 하 여 부트스트랩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="81ee5-127">클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테 넌 트 관리자가 Azure RMS URL에 대 한 정보를 사용 하 여 DNS SRV 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="81ee5-128">DNS SRV 레코드가 없으면 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 대 한 연결을 시도 하며 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="81ee5-129">또한 사용자가 사용자 `joe@contoso.cn` `onmschina` 이름 (예:)이 아니라 테 넌 트 소유 도메인 (예:)을 기반으로 사용자 이름으로 로그인 하는 것으로 가정 합니다 `joe@contoso.onmschina.cn` .</span><span class="sxs-lookup"><span data-stu-id="81ee5-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="81ee5-130">사용자 이름의 도메인 이름은 DNS를 올바른 서비스 인스턴스로 리디렉션하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="81ee5-131">RMS ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="81ee5-132">관리자로 PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="81ee5-133">AIPService 모듈이 설치 되어 있지 않으면를 실행  `Install-Module AipService` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="81ee5-134">을 사용 하 여 서비스에 연결  `Connect-AipService -environmentname azurechinacloud` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="81ee5-135"> `(Get-AipServiceConfiguration).RightsManagementServiceId`   를 실행 하 여 RMS ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="81ee5-136">DNS 공급자에 로그인 하 고 도메인에 대 한 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="81ee5-137">서비스 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="81ee5-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="81ee5-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="81ee5-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="81ee5-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="81ee5-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="81ee5-140">Target =  `[GUID].rms.aadrm.cn`   (여기서 GUID는 RMS ID)</span><span class="sxs-lookup"><span data-stu-id="81ee5-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="81ee5-141">우선 순위, 가중치, 초, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="81ee5-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="81ee5-142">사용자 지정 도메인을 [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)의 테 넌 트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="81ee5-143">이렇게 하면 dns에 항목이 추가 되 고 DNS 설정에 값을 추가한 후 확인 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="81ee5-144">해당 하는 전역 관리자 자격 증명을 사용 하 여 Microsoft 365 관리 센터에 로그인 하 고 `contoso.cn` 사용자 만들기에 대 한 도메인 (예:)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="81ee5-145">확인 프로세스에서 추가 DNS 변경이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="81ee5-146">확인이 완료 되 면 사용자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="81ee5-147">암호화에 대 한 DNS 구성 (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="81ee5-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="81ee5-148">DNS 공급자에 로그인 하 고 도메인에 대 한 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ee5-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="81ee5-149">서비스 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="81ee5-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="81ee5-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="81ee5-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="81ee5-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="81ee5-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="81ee5-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="81ee5-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="81ee5-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="81ee5-153">Port = `80`</span></span>
  - <span data-ttu-id="81ee5-154">우선 순위, 가중치, 초, TTL = 기본값</span><span class="sxs-lookup"><span data-stu-id="81ee5-154">Priority, Weight, Seconds, TTL = default values</span></span>
