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
description: 21Vianet에서 운영하는 Office 365용 AIP(Azure Information Protection)와 중국 고객을 위해 AIP를 구성하는 방법에 대해 자세히 알아보고
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099681"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>21Vianet에서 운영하는 Office 365에 대한 Azure Information Protection 지원

이 문서에서는 21Vianet에서 운영하는 Office 365에 대한 AIP(Azure Information Protection) 지원과 상업용 제품 간의 차이점과 AIP-프레미스 스캐너를 설치하고 콘텐츠 검색 작업을 관리하는 방법을 포함하여 중국 고객의 AIP를 구성하기 위한 특정 지침을 &mdash; 설명합니다.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet에서 운영하는 Office 365용 AIP와 상업용 제품 간의 차이점

21Vianet에서 운영하는 Office 365용 AIP를 통해 중국 고객에게 모든 상업적 기능을 제공하는 것이 목표지만, 강조하고자 하는 몇 가지 누락된 기능이 있습니다.

다음 목록에는 21Vianet에서 운영하는 Office 365용 AIP와 2021년 1월 현재 상업용 제품 간의 기존 간격이 포함되어 있습니다.

- IRM(정보 권한 관리)은 엔터프라이즈용 Microsoft 365 앱(빌드 11731.10000 이상)에만 지원됩니다. Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다.

- AD RMS(Active Directory Rights Management Services)에서 AIP로 마이그레이션할 수 없습니다.
  
- 상용 클라우드의 사용자와 보호된 전자 메일 공유가 지원됩니다.
  
- 현재 상용 클라우드의 사용자와 문서 및 전자 메일 첨부 파일을 공유할 수 없습니다. 여기에는 상용 클라우드의 21Vianet 사용자가 운영하는 Office 365, 상업용 클라우드의 21Vianet 사용자가 운영하는 비 Office 365 사용자 및 개인용 RMS 라이선스가 있는 사용자가 포함됩니다.
  
- SharePoint(IRM으로 보호된 사이트 및 라이브러리)를 사용하는 IRM은 현재 사용할 수 없습니다.
  
- AD RMS용 모바일 장치 확장은 현재 사용할 수 없습니다.

- 모바일 [뷰어는](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet에서 지원되지 않습니다.

- 중국의 고객은 Azure Portal의 AIP 영역을 사용할 수 없습니다. 포털에서 작업을 수행하는 대신 [PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 명령을 사용합니다(예: On-premises scanner 설치 및 콘텐츠 검색 작업 관리).

## <a name="configure-aip-for-customers-in-china"></a>중국 고객의 AIP 구성

중국 고객의 AIP를 구성하는 경우:
1. [테넌트에 대해 권한 관리를 사용하도록 설정](#step-1-enable-rights-management-for-the-tenant)

2. [DNS 암호화를 구성합니다.](#step-2-configure-dns-encryption)

3. [AIP 통합 레이블 지정 클라이언트를 설치하고 구성합니다.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Windows에서 AIP 앱을 구성합니다.](#step-4-configure-aip-apps-on-windows)

5. [AIP-프레미스](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)스캐너를 설치하고 콘텐츠 검색 작업을 관리합니다. 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>1단계: 테넌트에 대한 권한 관리 사용

암호화가 제대로 작동하려면 테넌트에 대해 RMS를 사용하도록 설정해야 합니다.

1. RMS가 사용하도록 설정되어 있는지 확인합니다.

    1. 관리자 권한으로 PowerShell을 실행합니다.
    2. AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.
    3. .를 사용하여 모듈을 가져올 `Import-Module AipService` 수 있습니다.
    4. .를 사용하여 서비스에 `Connect-AipService -environmentname azurechinacloud` 연결합니다.
    5. 실행 `(Get-AipServiceConfiguration).FunctionalState` 및 상태 확인 `Enabled`

2. 기능 상태가면 `Disabled` 다음을 `Enable-AipService` 실행합니다.

### <a name="step-2-configure-dns-encryption"></a>2단계: DNS 암호화 구성

암호화가 제대로 작동하려면 Office 클라이언트 응용 프로그램이 서비스의 중국 인스턴스에 연결하고 이 인스턴스에서 부트스트라프를 연결해야 합니다. 클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테넌트 관리자가 Azure RMS URL에 대한 정보를 사용하여 DNS SRV 레코드를 구성해야 합니다. DNS SRV 레코드가 없는 경우 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 연결하려고 시도하며 실패합니다.

또한 사용자가 테넌트 소유 도메인(예: 사용자 이름)을 기반으로 사용자 이름(예: )을 사용하여 로그인할 것으로 `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` 가정합니다. 사용자 이름의 도메인 이름은 올바른 서비스 인스턴스로 DNS 리디렉션에 사용됩니다.

#### <a name="configure-dns-encryption---windows"></a>DNS 암호화 구성 - Windows

1. RMS ID를 얻습니다.

    1. 관리자 권한으로 PowerShell을 실행합니다.
    2. AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.
    3. .를 사용하여 서비스에 `Connect-AipService -environmentname azurechinacloud` 연결합니다.
    4. 실행하여 `(Get-AipServiceConfiguration).RightsManagementServiceId` RMS ID를 얻습니다.

2. DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.

    - 서비스 = `_rmsredir`
    - 프로토콜 = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (여기서 GUID는 RMS ID)
    - 우선 순위, 가중치, 초, TTL = 기본값

3. 사용자 지정 도메인을 [Azure Portal의 테넌트와 연결합니다.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) 이렇게 하면 DNS에 항목이 추가됩니다. DNS 설정에 값을 추가한 후 확인되는 데 몇 분 정도 걸릴 수 있습니다.

4. 해당하는 전역 관리자 자격 증명으로 Microsoft 365 관리 센터에 로그인하고 사용자 만들기를 위한 도메인(예: `contoso.cn` )을 추가합니다. 확인 프로세스에서 추가 DNS 변경이 요구될 수 있습니다. 확인이 완료되면 사용자를 만들 수 있습니다.

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS 암호화 구성 - Mac, iOS, Android

DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.

- 서비스 = `_rmsdisco`
- 프로토콜 = `_http`
- Name = `_tcp`
- 대상 = `api.aadrm.cn`
- 포트 = `80`
- 우선 순위, 가중치, 초, TTL = 기본값

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>3단계: AIP 통합 레이블 클라이언트 설치 및 구성

Microsoft 다운로드 센터에서 AIP 통합 레이블 [클라이언트를 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=53018)

자세한 내용은 다음을 참조하세요.

- [AIP 설명서](/azure/information-protection/)
- [AIP 버전 기록 및 지원 정책](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 시스템 요구 사항](/azure/information-protection/requirements)
- [AIP 빠른 시작: AIP 클라이언트 배포](/azure/information-protection/quickstart-deploy-client)
- [AIP 관리자 가이드](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 사용자 가이드](/azure/information-protection/rms-client/clientv2-user-guide)
- [Microsoft 365 민감도 레이블에 대해 자세히](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>4단계: Windows에서 AIP 앱 구성

Windows의 AIP 앱에는 Azure China의 올바른 주권 클라우드를 설정하기 위해 다음 레지스트리 키가 필요합니다.

- 레지스트리 노드 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 값 = `6` (기본값 = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> 제거 후 레지스트리 키를 삭제하지 않습니다. 키가 비어 있거나, 잘못되거나, 존재하지 않는 경우 기능이 기본값(상업용 클라우드의 경우 기본값 = 0)으로 동작합니다. 키가 비어 있거나 올바르지 않은 경우 인쇄 오류도 로그에 추가됩니다.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>5단계: AIP-프레미스 스캐너 설치 및 콘텐츠 검색 작업 관리

AIP-프레미스 스캐너를 설치하여 네트워크 및 콘텐츠 공유에서 중요한 데이터를 검색하고 조직의 정책에 구성된 분류 및 보호 레이블을 적용합니다.

스캐너를 설치하고 콘텐츠 검색 작업을 관리할 때 상업용 제품에서 사용하는 Azure Portal 인터페이스 대신 다음 cmdlet을 사용합니다.<br><br>

| Cmdlet | 설명 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 콘텐츠 검색 작업에서 새 리포지토리를 추가합니다. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 콘텐츠 검색 작업의 세부 정보를 얻습니다. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 콘텐츠 검색 작업에서 정의된 리포지토리에 대한 세부 정보를 얻습니다. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 콘텐츠 검색 작업을 삭제합니다. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 콘텐츠 검색 작업에서 리포지토리를 제거합니다. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 콘텐츠 검색 작업의 설정을 정의합니다. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 콘텐츠 검색 작업의 기존 리포지토리에 대한 설정을 정의합니다. |

자세한 내용은 [Azure Information Protection](/azure/information-protection/deploy-aip-scanner) 통합 레이블 지정 스캐너란? [PowerShell만](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)사용하여 콘텐츠 검색 작업을 관리하세요.
