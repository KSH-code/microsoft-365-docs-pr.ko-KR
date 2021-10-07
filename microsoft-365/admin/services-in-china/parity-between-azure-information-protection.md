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
ms.localizationpriority: medium
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
ms.openlocfilehash: 3235bf77ec8cd7be96910614bdde41fb60f9f556
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199240"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>21Vianet에서 Office 365 Azure Information Protection 지원

이 문서에서는 21Vianet에서 운영하는 Office 365 및 상업용 제품용 Azure Information Protection(AIP) 지원의 차이점과, AIP-프레미스 스캐너를 설치하고 콘텐츠 검색 작업을 관리하는 방법을 포함하여 중국 고객의 AIP를 구성하기 위한 구체적인 지침을 &mdash; 설명합니다.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>21Vianet에서 운영하는 Office 365 제품용 AIP의 차이점

21Vianet에서 운영하는 21Vianet 제품용 A Office 365 IP를 통해 중국 고객에게 모든 상용 기능과 기능을 제공하는 것이 목표지만, 강조 표시하고자 하는 몇 가지 누락된 기능이 있습니다.

다음 목록에는 21Vianet에서 운영하는 Office 365 AIP와 2021년 1월 현재 상업용 제품 간의 기존 간격이 포함되어 있습니다.

- IRM(정보 권한 관리)은 엔터프라이즈용 Microsoft 365 앱(빌드 11731.10000 이상)에만 지원됩니다. Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다.

- AD RMS(Active Directory Rights Management Services)에서 AIP로의 마이그레이션은 현재 사용할 수 없습니다.
  
- 상용 클라우드의 사용자와 보호된 전자 메일 공유가 지원됩니다.
  
- 현재 상업용 클라우드의 사용자와 문서 및 전자 메일 첨부 파일을 공유할 수 없습니다. 여기에는 Office 365 클라우드에서 21Vianet 사용자가 운영하는 Office 365, 상업용 클라우드의 21Vianet 사용자가 운영하지 않는 사용자 및 개인용 RMS 라이선스가 있는 사용자가 포함됩니다.
  
- IRM을 SharePoint(IRM으로 보호된 사이트 및 라이브러리)는 현재 사용할 수 없습니다.
  
- AD RMS용 모바일 장치 확장을 현재 사용할 수 없습니다.

- 모바일 [뷰어는](/azure/information-protection/rms-client/mobile-app-faq) Azure China 21Vianet에서 지원되지 않습니다.

- 중국 고객은 Azure Portal의 AIP 영역을 사용할 수 없습니다. 포털에서 콘텐츠 검색 작업 관리 및 실행과 같은 작업을 수행하는 대신 [PowerShell](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 명령을 사용합니다.

## <a name="configure-aip-for-customers-in-china"></a>중국 고객의 AIP 구성

중국 고객의 AIP를 구성하는 경우:
1. [테넌트에 대한 권한 관리를 사용하도록 설정](#step-1-enable-rights-management-for-the-tenant)

1. [동기화 Microsoft Information Protection 서비스 사용자 를 추가합니다.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)

1. [DNS 암호화를 구성합니다.](#step-3-configure-dns-encryption)

1. AIP 통합 레이블 클라이언트를 [설치하고 구성합니다.](#step-4-install-and-configure-the-aip-unified-labeling-client)

1. [에서 AIP 앱을 Windows.](#step-5-configure-aip-apps-on-windows)

1. [AIP 사내 스캐너를 설치하고 콘텐츠 검사 작업을 관리합니다.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>1단계: 테넌트에 대한 권한 관리 사용

암호화가 제대로 작동하려면 테넌트에 대해 RMS를 사용하도록 설정해야 합니다.

1. RMS를 사용할 수 있는지 확인합니다.

    1. 관리자 권한으로 PowerShell을 실행합니다.
    2. AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.
    3. 를 사용하여 모듈을 가져올 수 `Import-Module AipService` 있습니다.
    4. 커넥트 를 사용하여 서비스에 대한 데이터 열기 `Connect-AipService -environmentname azurechinacloud`
    5. 를 `(Get-AipServiceConfiguration).FunctionalState` 실행하고 상태가 입니다. `Enabled`

2. 기능 상태가 인 경우 `Disabled` 를 `Enable-AipService` 실행합니다.

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>2단계: Microsoft Information Protection 동기화 서비스 사용자 추가

Azure **Microsoft Information Protection 동기화** 서비스 계정은 기본적으로 Azure China 테넌트에서 사용할 수 없습니다. Azure Information Protection에 필요합니다.

1. [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet 및 Microsoft Information Protection 동기화 서비스의 응용 프로그램 ID를 사용하여 이 서비스 계정을 Microsoft Information Protection `870c4f2e-85b6-4d43-bdda-6ed9a579b725` 생성합니다. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. 서비스 사용자 추가 후 서비스에 필요한 관련 권한을 추가합니다.

### <a name="step-3-configure-dns-encryption"></a>3단계: DNS 암호화 구성

암호화가 제대로 작동하려면 Office 클라이언트 응용 프로그램이 서비스 중국 인스턴스에 연결하고 해당 인스턴스에서 부트스트스트프를 연결해야 합니다. 클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테넌트 관리자가 Azure RMS URL에 대한 정보를 사용하여 DNS SRV 레코드를 구성해야 합니다. DNS SRV 레코드가 없는 경우 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 연결하려고 시도하며 실패합니다.

또한 사용자가 테넌트 소유 도메인을 기반으로 사용자 이름(예: )을 사용하여 로그인하고 사용자 이름(예: )을 사용하여 로그인할 것으로 `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` 가정합니다. 사용자 이름의 도메인 이름은 올바른 서비스 인스턴스로의 DNS 리디렉션에 사용됩니다.

#### <a name="configure-dns-encryption---windows"></a>DNS 암호화 구성 - Windows

1. RMS ID를 얻습니다.

    1. 관리자 권한으로 PowerShell을 실행합니다.
    2. AIPService 모듈이 설치되어 있지 않은 경우 를 `Install-Module AipService` 실행합니다.
    3. 커넥트 를 사용하여 서비스에 대한 데이터 열기 `Connect-AipService -environmentname azurechinacloud`
    4. `(Get-AipServiceConfiguration).RightsManagementServiceId`RMS ID를 얻습니다.

2. DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.

    - 서비스 = `_rmsredir`
    - 프로토콜 = `_http`
    - Name = `_tcp`
    - 대상 = `[GUID].rms.aadrm.cn` (여기서 GUID는 RMS ID)
    - Priority, Weight, Seconds, TTL = 기본값

3. Azure Portal의 테넌트와 사용자 지정 [도메인을 연결합니다.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) 이렇게 하면 DNS에 항목이 추가됩니다. DNS 설정에 값을 추가한 후 확인되는 데 몇 분 정도 걸릴 수 있습니다.

4. 해당 전역 Microsoft 365 관리 센터 자격 증명으로 로그인하고 사용자 만들기를 위해 도메인(예: `contoso.cn` )을 추가합니다. 확인 프로세스에서는 DNS를 추가로 변경해야 할 수 있습니다. 확인이 완료되면 사용자를 만들 수 있습니다.

#### <a name="configure-dns-encryption---mac-ios-android"></a>DNS 암호화 구성 - Mac, iOS, Android

DNS 공급자에 로그인하고 도메인의 DNS 설정으로 이동한 다음 새 SRV 레코드를 추가합니다.

- 서비스 = `_rmsdisco`
- 프로토콜 = `_http`
- Name = `_tcp`
- 대상 = `api.aadrm.cn`
- 포트 = `80`
- Priority, Weight, Seconds, TTL = 기본값


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>4단계: AIP 통합 레이블 클라이언트 설치 및 구성

Microsoft 다운로드 센터에서 AIP 통합 레이블 클라이언트를 다운로드하여 [설치합니다.](https://www.microsoft.com/download/details.aspx?id=53018)

자세한 내용은 다음을 참조하세요.

- [AIP 설명서](/azure/information-protection/)
- [AIP 버전 기록 및 지원 정책](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 시스템 요구 사항](/azure/information-protection/requirements)
- [AIP 빠른 시작: AIP 클라이언트 배포](/azure/information-protection/quickstart-deploy-client)
- [AIP 관리자 가이드](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 사용자 가이드](/azure/information-protection/rms-client/clientv2-user-guide)
- [민감도 Microsoft 365 대해 자세히 알아보시고](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>5단계: 설치 시 AIP Windows

Azure의 AIP Windows Azure China에 대한 올바른 주권 클라우드를 설정하려면 다음 레지스트리 키가 필요합니다.

- 레지스트리 노드 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 값 = `6` (기본값 = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> 제거 후 레지스트리 키를 삭제하지 않는지 확인 합니다. 키가 비어 있거나, 잘못되거나, 존재하지 않는 경우에는 기능이 기본값(상업용 클라우드의 경우 기본값 = 0)으로 동작합니다. 키가 비어 있거나 올바르지 않은 경우 로그에 인쇄 오류도 추가됩니다.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>6단계: AIP 사내 스캐너 설치 및 콘텐츠 검사 작업 관리

AIP-프레미스 스캐너를 설치하여 네트워크 및 콘텐츠 공유에서 중요한 데이터를 검색하고 조직의 정책에 구성된 분류 및 보호 레이블을 적용합니다.

콘텐츠 검색 작업을 구성하고 관리할 때 상업용 제품에서 사용하는 [Azure Portal](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) 인터페이스 대신 다음 절차를 사용합니다.

자세한 내용은 [Azure Information Protection](/azure/information-protection/deploy-aip-scanner) 통합 레이블 지정 스캐너란? 및 [PowerShell만](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)사용하여 콘텐츠 검사 작업 관리를 참조하세요.

**스캐너를 설치 및 구성하려면:**

1. 스캐너를 실행할 Windows Server 컴퓨터에 로그인합니다. 로컬 관리자 권한이 있으며 마스터 데이터베이스에 쓸 수 있는 권한이 있는 SQL Server 사용합니다.

1. PowerShell을 닫은 후 시작 이전에 AIP 클라이언트 및 스캐너를 설치한 경우 **AIPScanner 서비스가** 중지된지 확인합니다.

1. 관리자 권한으로 Windows PowerShell 옵션을 사용하여 **세션을 런타합니다.**

1. [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet을 실행하여 Azure Information Protection 스캐너에 대한 데이터베이스를 만들 SQL Server 인스턴스와 스캐너 클러스터에 대해 의미 있는 이름을 지정합니다.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 명령에서 동일한 클러스터 이름을 사용하여 여러 스캐너 노드를 동일한 클러스터에 연결합니다. 여러 스캐너 노드에 동일한 클러스터를 사용하면 여러 스캐너가 함께 작동하여 스캔을 수행할 수 있습니다.
    > 

1. 이제 관리 도구 서비스를 사용하여 **서비스가 설치되어 있는지**  >  **확인합니다.**

    설치된 서비스의 이름은 **Azure Information Protection Scanner로,** 만든 스캐너 서비스 계정을 사용하여 실행하도록 구성됩니다.

1. 스캐너에 사용할 Azure 토큰을 얻습니다. Azure AD 토큰을 사용하면 스캐너가 Azure Information Protection 서비스에 인증하여 대화형이 아닌 프로그램을 실행할 수 있습니다. 

    1. Azure Portal을 열고 Azure AD 응용 프로그램을 만들어 인증에 대한 액세스 토큰을 지정합니다. 자세한 내용은 Azure Information Protection에 대해 대화형이 아닌 파일에 레이블을 [지정하는 방법을 참조하세요.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)
    
        > [!TIP]
        > [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 명령에 대해 Azure AD 응용 프로그램을  만들고 구성할 때  API 요청 창에는 **조직에서 Microsoft API** 탭 대신 탭을 사용하는 API가 표시됩니다. 조직에서 **사용하는 API를** 선택한 다음 **Azure 권한 관리 서비스를 선택합니다.** 
        >

    1. Windows 서버 컴퓨터에서 스캐너 서비스 계정에 설치에 대한 로컬로  로그온 권한이 부여된 경우 이 계정으로 로그인하고 PowerShell 세션을 시작하십시오. 
    
        스캐너 서비스 계정에 설치에 대한  로컬로 로그온 권한을 부여할 수 없는 경우 [Azure Information Protection에서](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)비대화형으로 파일에 레이블을 지정하는 방법에 설명된 바와 같이 *OnBehalfOf* 매개 변수를 [Set-AIPAuthentication과](/powershell/module/azureinformationprotection/set-aipauthentication)함께 사용합니다.

    1. [Set-AIPAuthentication을](/powershell/module/azureinformationprotection/set-aipauthentication)실행하여 Azure AD 응용 프로그램에서 복사된 값을 지정합니다.

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      예제:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    이제 스캐너에 Azure AD에 인증할 토큰이 있습니다. 이 토큰은 Azure AD의 웹 앱 **/API** 클라이언트 비밀 구성에 따라 1년, 2년 또는 절대 유효하지 않습니다. 토큰이 만료되면 이 절차를 반복해야 합니다.

1. [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet을 실행하여 스캐너가 오프라인 모드에서 작동할 수 있습니다. 을 실행합니다.

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet을 실행하여 기본 콘텐츠 검사 작업을 만들 수 있습니다.

    **Set-AIPScannerContentScanJob** cmdlet의 유일한 필수 매개 변수는 **Enforce입니다.** 그러나 현재 콘텐츠 검색 작업의 다른 설정을 정의할 수 있습니다. 예제:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    위의 구문은 구성을 계속하는 동안 다음 설정을 구성합니다.

    - 스캐너 실행을 수동으로 *유지*
    - 민감도 레이블 정책에 따라 검색할 정보 유형 설정
    - *민감도* 레이블 지정 정책을 적용하지 않습니다.
    - 민감도 레이블 정책에 정의된 기본 레이블을 사용하여 콘텐츠에 따라 파일에 자동으로 레이블을 지정합니다.
    - *파일레이블을* 허용하지 않습니다.
    - 검사 및 자동 레이블 지정 시 파일 세부 정보 보존(수정된 날짜, 마지막으로 수정한 날짜 및 값으로 *수정한* 날짜 포함) 
    - 실행 시 .msg 및 .tmp 파일을 제외할 스캐너 설정
    - 스캐너를 실행하는 데 사용할 계정으로 기본 소유자 설정

1. [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet을 사용하여 콘텐츠 검색 작업에서 검색할 리포지토리를 정의할 수 있습니다. 예를 들어 다음을 실행합니다.

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    추가하는 리포지토리의 유형에 따라 다음 구문 중 하나를 사용 합니다.

    - 네트워크 공유의 경우 를 사용 `\\Server\Folder` 합니다.
    - SharePoint 라이브러리의 경우 를 사용 `http://sharepoint.contoso.com/Shared%20Documents/Folder` 합니다.
    - 로컬 경로의 경우: `C:\Folder`
    - UNC 경로의 경우: `\\Server\Folder`

    > [!NOTE]
    > 와일드카드는 지원되지 않습니다. WebDav 위치는 지원되지 않습니다.
    >
    > 나중에 리포지토리를 수정하려면 [대신 Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet을 사용합니다. 


필요한 경우 다음 단계를 계속 진행합니다.

- [검색 주기 실행 및 스캐너용 보고서 보기](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [PowerShell을 사용하여 분류 및 보호를 적용하도록 스캐너 구성](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [PowerShell을 사용하여 스캐너를 사용하여 DLP 정책 구성](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

다음 표에는 스캐너 설치 및 콘텐츠 검사 작업 관리와 관련된 PowerShell cmdlet이 나열됩니다.

| Cmdlet | 설명 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 콘텐츠 검색 작업에서 새 리포지토리를 추가합니다. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|클러스터에 대한 세부 정보를 반환합니다. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 콘텐츠 검색 작업의 세부 정보를 얻습니다. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 콘텐츠 검색 작업에서 정의된 리포지토리에 대한 세부 정보를 얻습니다. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 콘텐츠 검색 작업을 삭제합니다. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 콘텐츠 검색 작업에서 리포지토리를 제거합니다. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 콘텐츠 검색 작업의 설정을 정의합니다. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 콘텐츠 검색 작업의 기존 리포지토리에 대한 설정을 정의합니다. |
| | |

자세한 내용은 다음을 참조하세요.

- [Azure Information Protection 통합 레이블 지정 스캐너란?](/azure/information-protection/deploy-aip-scanner)
- [AIP(Azure Information Protection) 통합 레이블 지정 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [PowerShell만 사용하여 콘텐츠 검색 작업을 관리합니다.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
