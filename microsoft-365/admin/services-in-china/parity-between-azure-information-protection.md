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
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet 및 상업적 제공품에서 운영 하는 Office 365의 Azure Information Protection 간 패리티

Microsoft의 목표는 21Vianet에서 운영 하는 Office 365의 Azure Information Protection을 사용 하 여 중국의 고객에 게 모든 상업용 기능과 기능을 제공 하는 것 이며 몇 가지 기능을 강조 해야 합니다.

다음은 21Vianet에서 운영 하는 Office 365의 Azure Information Protection과 7 월 2019의 상용 제품 간의 기존 간격입니다.

- IRM (정보 권한 관리)은 enterprise 용 Microsoft 365 Apps (빌드 11731.10000 이상)에만 지원 됩니다. Office 2010, Office 2013 및 기타 Office 2016 버전은 지원 되지 않습니다.

- AD RMS (Active Directory Rights Management Services)에서 Azure Information Protection으로의 마이그레이션을 현재 사용할 수 없습니다.
  
- 보호 된 전자 메일을 상업용 클라우드의 사용자에 게 공유 하는 기능은 지원 됩니다.
  
- 현재 상업용 클라우드의 사용자에 게 문서 및 전자 메일 첨부 파일을 공유할 수 없습니다. 여기에는 상업용 클라우드의 21Vianet 사용자가 운영 하는 Office 365, 상업용 클라우드의 21Vianet 사용자가 운영 하는 Office 365 및 개별 라이선스에 대 한 RMS가 있는 사용자가 포함 됩니다.
  
- SharePoint (IRM으로 보호 된 사이트 및 라이브러리)가 포함 된 IRM을 현재 사용할 수 없습니다.
  
- 권한 관리 커넥터를 현재 사용할 수 없습니다.
  
- AD RMS에 대 한 모바일 장치 확장을 현재 사용할 수 없습니다.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>중국에서 고객에 대 한 Azure Information Protection 구성

### <a name="enable-rights-management-for-the-tenant"></a>테 넌 트에 대 한 권한 관리 사용

암호화가 제대로 작동 하려면 테 넌 트에 대해 RMS를 사용 하도록 설정 해야 합니다.

- RMS가 사용 하도록 설정 되어 있는지 확인 합니다.
  1. 관리자로 PowerShell을 시작 합니다.
  2. AIPService 모듈이 설치 되어 있지 않으면를 실행  `Install-Module AipService` 합니다.
  3. 를 사용 하 여 모듈을 가져옵니다 `Import-Module AipService` .
  4. 을 사용 하 여 서비스에 연결  `Connect-AipService -environmentname azurechinacloud` 합니다.
  5.  `(Get-AipServiceConfiguration).FunctionalState`   를 실행 하 고 상태가 인지 확인  `Enabled` 합니다.

- 기능 상태가 이면  `Disabled` 를 실행  `Enable-AipService` 합니다.

### <a name="dns-configuration-for-encryption-windows"></a>암호화에 대 한 DNS 구성 (Windows)

암호화가 제대로 작동 하려면 Office 클라이언트 응용 프로그램에서 중국 서비스 인스턴스에 연결 하 여 부트스트랩 해야 합니다. 클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테 넌 트 관리자가 Azure RMS URL에 대 한 정보를 사용 하 여 DNS SRV 레코드를 구성 해야 합니다. DNS SRV 레코드가 없으면 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 대 한 연결을 시도 하며 실패 하 게 됩니다.

또한 사용자가 사용자 `joe@contoso.cn` `onmschina` 이름 (예:)이 아니라 테 넌 트 소유 도메인 (예:)을 기반으로 사용자 이름으로 로그인 하는 것으로 가정 합니다 `joe@contoso.onmschina.cn` . 사용자 이름의 도메인 이름은 DNS를 올바른 서비스 인스턴스로 리디렉션하는 데 사용 됩니다.

- RMS ID를 가져옵니다.
  1. 관리자로 PowerShell을 시작 합니다.
  2. AIPService 모듈이 설치 되어 있지 않으면를 실행  `Install-Module AipService` 합니다.
  3. 을 사용 하 여 서비스에 연결  `Connect-AipService -environmentname azurechinacloud` 합니다.
  4.  `(Get-AipServiceConfiguration).RightsManagementServiceId`   를 실행 하 여 RMS ID를 가져옵니다.

- DNS 공급자에 로그인 하 고 도메인에 대 한 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가 합니다.
  - 서비스 = `_rmsredir`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target =  `[GUID].rms.aadrm.cn`   (여기서 GUID는 RMS ID)
  - 우선 순위, 가중치, 초, TTL = 기본값

- 사용자 지정 도메인을 [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)의 테 넌 트에 연결 합니다. 이렇게 하면 dns에 항목이 추가 되 고 DNS 설정에 값을 추가한 후 확인 하는 데 몇 분 정도 걸릴 수 있습니다.

- 해당 하는 전역 관리자 자격 증명을 사용 하 여 Microsoft 365 관리 센터에 로그인 하 고 `contoso.cn` 사용자 만들기에 대 한 도메인 (예:)을 추가 합니다. 확인 프로세스에서 추가 DNS 변경이 필요할 수 있습니다. 확인이 완료 되 면 사용자를 만들 수 있습니다.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>암호화에 대 한 DNS 구성 (Mac, iOS, Android)

- DNS 공급자에 로그인 하 고 도메인에 대 한 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가 합니다.
  - 서비스 = `_rmsdisco`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `api.aadrm.cn`
  - Port = `80`
  - 우선 순위, 가중치, 초, TTL = 기본값
