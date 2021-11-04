---
title: 이중 키 암호화(DKE)
description: DKE를 사용하면 키에 대한 모든 제어를 유지하면서 매우 중요한 데이터를 보호할 수 있습니다.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 1e3629c1d5dfdf32da25a7b89452df0009ad6df7
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747401"
---
# <a name="double-key-encryption-for-microsoft-365"></a>이중 키 암호화 Microsoft 365

> *적용 사항: [Microsoft 365,](https://www.microsoft.com/microsoft-365/business/compliance-management)Microsoft 365 준수, [Azure Information Protection에](https://azure.microsoft.com/pricing/details/information-protection) 대한 이중 키 암호화*
>
> *지침: Azure Information Protection 통합 레이블 [클라이언트를 Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *서비스 설명: Microsoft 365 [규정 준수](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

DKE(이중 키 암호화)는 두 개의 키를 함께 사용하여 보호된 콘텐츠에 액세스합니다. Microsoft는 키 하나를 Microsoft Azure 다른 키를 저장합니다. 이중 키 암호화 서비스를 사용하여 키 중 하나에 대한 모든 제어를 유지 관리합니다. Azure Information Protection 통합 레이블 지정 클라이언트를 사용하여 매우 중요한 콘텐츠에 보호를 적용합니다.

이중 키 암호화는 클라우드 및 사내 배포를 모두 지원합니다. 이러한 배포를 통해 보호된 데이터를 저장할 때마다 암호화된 데이터가 불투명하게 유지되도록 할 수 있습니다.

기본 클라우드 기반 테넌트 루트 키에 대한 자세한 내용은 Azure Information Protection 테넌트 키 계획 및 [구현을 참조하세요.](/azure/information-protection/plan-implement-tenant-key)

## <a name="when-your-organization-should-adopt-dke"></a>조직에서 DKE를 채택해야 하는 경우

이중 키 암호화는 가장 엄격한 보호 요구 사항을 준수하는 가장 중요한 데이터를 위한 것입니다. DKE는 모든 데이터를 위한 것이 아니며, 일반적으로 이중 키 암호화를 사용하여 전체 데이터의 일부만 보호합니다. 배포하기 전에 이 솔루션에 사용할 올바른 데이터를 식별할 때 신심해야 합니다. 경우에 따라 범위를 좁히고 Microsoft 관리 키 또는 BYOK를 사용하는 경우와 같은 대부분의 데이터에 Microsoft Information Protection 다른 솔루션을 활용해야 할 수 있습니다. 이러한 솔루션은 향상된 보호 및 규정 요구 사항을 준수하지 않는 문서에 충분합니다. 또한 이러한 솔루션을 사용하면 가장 강력한 Office 365 사용할 수 있습니다. DKE로 암호화된 콘텐츠와 함께 사용할 수 없는 서비스 예제:

- 첨부 파일을 표시해야 하는 맬웨어 방지 및 스팸 방지를 포함한 전송 규칙
- Microsoft Delve
- eDiscovery
- 콘텐츠 검색 및 인덱싱
- Office 공동자치 기능을 포함한 웹앱

MIP SDK를 통해 DKE와 통합되지 않은 외부 응용 프로그램 또는 서비스는 암호화된 데이터에 대해 작업을 수행할 수 없습니다.

이 Microsoft Information Protection SDK 1.7+는 이중 키 암호화를 지원합니다. SDK와 통합되는 응용 프로그램은 충분한 사용 권한 및 통합을 통해 이 데이터를 추론할 수 있습니다.

조직은 Microsoft 정보 보호 기능(분류 및 레이블 지정)을 사용하여 대부분의 중요한 데이터를 보호하고 중요 중요 데이터에만 DKE를 사용하는 것이 좋습니다. 이중 키 암호화는 금융 서비스 및 의료와 같은 높은 규제 대상 산업의 중요한 데이터와 관련이 있습니다.

조직에 다음 요구 사항이 있는 경우 DKE를 사용하여 콘텐츠 보안을 지원할 수 있습니다.

- 모든 상황에서 보호된 콘텐츠의 암호 해독만 할 수 있도록 하려는 경우 
- Microsoft가 자체로 보호된 데이터에 액세스하는 것을 원하지 않습니다.
- 지리적 경계 내에 키를 보유하기 위한 규정 요구 사항이 있습니다. 데이터 암호화 및 암호 해독을 위해 보유하는 모든 키는 데이터 센터에서 유지 관리됩니다.

## <a name="system-and-licensing-requirements-for-dke"></a>DKE에 대한 시스템 및 라이선스 요구 사항

**이중 키 암호화는** Microsoft 365 함께 Microsoft 365 E5. 라이선스가 없는 Microsoft 365 E5 평가판에 등록할 수 [있습니다.](https://aka.ms/M365E5ComplianceTrial) 이러한 라이선스에 대한 자세한 내용은 보안 Microsoft 365 규정 준수에 대한 [& 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

**Azure Information Protection**. DKE는 민감도 레이블과 함께 작동하며 Azure Information Protection이 필요합니다.

DKE 민감도 레이블은 데스크톱 앱의 민감도 리본을 통해 최종 Office 있습니다. 보호된 문서를 보호하고 사용하려는 각 클라이언트 컴퓨터에 이러한 선행 요구를 설치합니다.

**Microsoft Office 엔터프라이즈용 앱** 버전 2009 이상(데스크톱 버전의 Word, PowerPoint 및 Excel)Windows.

**Azure Information Protection 통합 레이블 지정 클라이언트** 버전 2.7.93.0 이상. Microsoft 다운로드 센터에서 통합 레이블 지정 클라이언트를 [다운로드하여 설치합니다.](https://www.microsoft.com/download/details.aspx?id=53018)

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>DKE로 보호된 콘텐츠를 저장하고 보기 위한 지원되는 환경

**지원되는 응용 프로그램**. [엔터프라이즈용 Microsoft 365 앱,](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) Windows 및 Excel 클라이언트를 PowerPoint.

**온라인 콘텐츠 지원**. 이중 키 암호화로 보호된 문서와 파일은 Microsoft 365 및 Microsoft SharePoint 모두에서 비즈니스용 OneDrive. 이러한 위치에 업로드하기 전에 지원되는 응용 프로그램에서 DKE로 문서 및 파일에 레이블을 지정하고 보호해야 합니다. 암호화된 콘텐츠를 전자 메일로 공유할 수 있지만 암호화된 문서와 파일은 온라인으로 볼 수 없습니다. 대신 로컬 컴퓨터에서 지원되는 데스크톱 응용 프로그램 및 클라이언트를 사용하여 보호된 콘텐츠를 보아야 합니다.

## <a name="overview-of-deploying-dke"></a>DKE 배포 개요

DKE를 설정하기 위해 다음과 같은 일반적인 단계를 수행합니다. 이러한 단계를 완료하면 최종 사용자가 이중 키 암호화를 사용하여 매우 중요한 데이터를 보호할 수 있습니다.

1. 이 문서에 설명된 바와 같이 DKE 서비스를 배포합니다.

2. 이중 키 암호화를 사용하여 레이블을 만들 수 있습니다. 앱의 정보 보호로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a> 이중 키 암호화를 사용하여 새 레이블을 만들 수 있습니다. 민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠에 대한 [액세스 제한을 참조하세요.](./encryption-sensitivity-labels.md)

3. 이중 키 암호화 레이블을 사용합니다. 사용자 지정의 민감도 리본에서 이중 키 암호화 레이블을 선택하여 데이터를 Microsoft Office.

몇 가지 방법으로 이중 키 암호화를 배포하는 단계를 완료할 수 있습니다. 이 문서에서는 경험이 적은 관리자가 서비스를 성공적으로 배포할 수 있도록 자세한 지침을 제공합니다. 원하는 경우 자체 방법을 사용할 수 있습니다.

## <a name="deploy-dke"></a>DKE 배포

이 문서 및 배포 비디오에서는 Azure를 DKE 서비스의 배포 대상으로 사용하세요. 다른 위치에 배포하는 경우 자체 값을 제공해야 합니다.

이중 키 암호화 [배포](https://youtu.be/vDWfHN_kygg) 비디오를 시청하여 이 문서의 개념에 대한 단계별 개요를 확인할 수 있습니다. 비디오를 완료하는 데 18분 정도 걸립니다.

조직에 대해 이중 키 암호화를 설정하기 위해 다음과 같은 일반적인 단계를 수행합니다.

1. [DKE 서비스에 대한 소프트웨어 선행 구성](#install-software-prerequisites-for-the-dke-service)
1. [리포지토리에서 이중 GitHub 암호화 복제](#clone-the-dke-github-repository)
1. [응용 프로그램 설정 수정](#modify-application-settings)
1. [테스트 키 생성](#generate-test-keys)
1. [프로젝트 빌드](#build-the-project)
1. [DKE 서비스 배포 및 키 저장소 게시](#deploy-the-dke-service-and-publish-the-key-store)
1. [배포 유효성 검사](#validate-your-deployment)
1. [키 저장소 등록](#register-your-key-store)
1. [DKE를 사용하여 민감도 레이블 만들기](#create-sensitivity-labels-using-dke)
1. [클라이언트에서 DKE 사용](#enable-dke-in-your-client)
1. [HYOK 레이블에서 DKE 레이블로 보호된 파일 마이그레이션](#migrate-protected-files-from-hyok-labels-to-dke-labels)

완료되면 DKE를 사용하여 문서 및 파일을 암호화할 수 있습니다. 자세한 내용은 [에서 파일](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)및 전자 메일에 민감도 레이블 적용을 Office.

### <a name="install-software-prerequisites-for-the-dke-service"></a>DKE 서비스에 대한 소프트웨어 선행 구성

DKE 서비스를 설치하려는 컴퓨터에 이러한 선행 구성을 설치합니다.

**.NET Core 3.1 SDK**. [.NET Core 3.1 다운로드에서 SDK를 다운로드하여 설치합니다.](https://dotnet.microsoft.com/download/dotnet-core/3.1)

**Visual Studio Code**. 에서 Visual Studio Code [https://code.visualstudio.com/](https://code.visualstudio.com) 다운로드합니다. 설치한 후 Visual Studio Code 확장  \> **보기를 선택합니다.** 이러한 확장을 설치합니다.

- C# 대한 Visual Studio Code

- NuGet 패키지 관리자

**Git 리소스**. 다음 중 하나를 다운로드하여 설치합니다.

- [Git](https://git-scm.com/downloads)

- [GitHub 데스크톱](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** DKE를 배포한 후 [](#generate-test-keys) 테스트 키를 생성하려면 [OpenSSL이](https://slproweb.com/products/Win32OpenSSL.html) 설치되어 있어야 합니다. 환경 변수 경로에서 올바르게 호출하고 있는지 확인합니다. 예를 들어 자세한 내용은 "PATH에 설치 디렉터리 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) 추가"를 참조하십시오.

### <a name="clone-the-dke-github-repository"></a>DKE 데이터베이스 GitHub 복제

Microsoft는 DKE 원본 파일을 로컬 저장소에 GitHub 제공합니다. 리포지토리를 복제하여 조직에서 사용할 수 있도록 프로젝트를 로컬로 빌드합니다. DKE GitHub 리포지토리는 에 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 있습니다.

다음 지침은 비경제적 git 또는 Visual Studio Code 위한 것입니다.

1. 브라우저에서 로 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 이동하세요. .

2. 화면 오른쪽에서 코드를 **선택합니다.** UI 버전에 복제 또는 다운로드 **단추가 표시될 수** 있습니다. 그런 다음 나타나는 드롭다운에서 복사 아이콘을 선택하여 URL을 클립보드에 복사합니다.

    예제:

   > [!div class="mx-imgBorder"]
   > ![이중 키 암호화 서비스 리포지토리를 GitHub.](../media/dke-clone.png)

3. 다음 Visual Studio Code 보기 명령  팔레트 보기를 \> **선택하고** **Git: 복제를 선택합니다.** 목록의 옵션으로 이동하려면 입력을 시작하여 항목을 필터링한 다음 `git: clone` 드롭다운에서 선택합니다. 예제:

   > [!div class="mx-imgBorder"]
   > ![Visual Studio Code GIT:Clone 옵션.](../media/dke-vscode-clone.png)

4. 텍스트 상자에 Git에서 복사한 URL을 붙여넣고 에서 **복제를 GitHub.**

5. 나타나는 **폴더 선택** 대화 상자에서 리포지토리를 저장할 위치를 찾아 선택합니다. 프롬프트에서 열기 **를 선택합니다.**

    리포지토리가 Visual Studio Code 왼쪽 아래에 현재 Git 분기가 표시됩니다. 예를 들어 분기는 **main** 입니다. 예제:

   ![주 분기를 표시하는 Visual Studio Code DKE 리포지터의 스크린샷입니다.](../media/dke-vscode-main-branch.jpg)

6. 주 분기에 없는 경우 해당 분기를 선택해야 합니다. 다음 Visual Studio Code 분기를 선택하고 표시하는  분기 목록에서 main을 선택합니다.

   > [!IMPORTANT]
   > 주 분기를 선택하면 프로젝트를 빌드할 올바른 파일이 있습니다. 올바른 분기를 선택하지 않은 경우 배포가 실패합니다.

이제 DKE 원본 리포지토리가 로컬로 설정됩니다. 그런 다음 [조직의 응용 프로그램](#modify-application-settings) 설정을 수정합니다.

### <a name="modify-application-settings"></a>응용 프로그램 설정 수정

DKE 서비스를 배포하려면 다음과 같은 유형의 응용 프로그램 설정을 수정해야 합니다.

- [키 액세스 설정](#key-access-settings)
- [테넌트 및 키 설정](#tenant-and-key-settings)

appsettings.json 파일에서 응용 프로그램 설정을 수정합니다. 이 파일은 로컬로 복제한 DoubleKeyEncryptionService 리포지션의 DoubleKeyEncryptionService\src\customer-key-store에 있습니다. 예를 들어 Visual Studio Code 그림과 같이 파일을 찾아볼 수 있습니다.

![DKE용 appsettings.json 파일 찾기](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>키 액세스 설정

전자 메일 또는 역할 권한 부여를 사용할지 여부를 선택하십시오. DKE는 한 번의 인증 방법 중 하나만 지원됩니다.

- **전자 메일 권한 부여**. 조직에서 전자 메일 주소만 기준으로 키에 대한 액세스 권한을 부여할 수 있습니다.

- **역할 권한 부여**. 조직에서 Active Directory 그룹을 기반으로 키에 대한 액세스 권한을 부여할 수 있도록 허용하며 웹 서비스가 LDAP를 쿼리할 수 있도록 요구합니다.

##### <a name="to-set-key-access-settings-for-dke-using-email-authorization"></a>전자 메일 권한 부여를 사용하여 DKE에 대한 키 액세스 설정을 설정하려면

1. **appsettings.json** 파일을 열고 설정을 `AuthorizedEmailAddress` 찾습니다.

2. 승인할 전자 메일 주소 또는 주소를 추가합니다. 여러 전자 메일 주소를 따옴표와 각자 구분합니다. 예제:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. 설정을 찾아서 따옴표 `LDAPPath` 사이에 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 있는 텍스트를 제거합니다. 따옴표를 그대로 다. 완료되면 설정이 다음과 같이 설정됩니다.

   ```json
   "LDAPPath": ""
   ```

4. 설정을 `AuthorizedRoles` 찾아 전체 줄을 삭제합니다.

이 이미지는 전자 메일 권한 부여를 위해 올바르게 형식이 지정된 **appsettings.json** 파일을 보여줍니다.

   ![전자 메일 권한 부여 방법을 보여주는 appsettings.json 파일입니다.](../media/dke-email-accesssetting.png)

##### <a name="to-set-key-access-settings-for-dke-using-role-authorization"></a>역할 권한 부여를 사용하여 DKE에 대한 키 액세스 설정을 설정하려면

1. **appsettings.json** 파일을 열고 설정을 `AuthorizedRoles` 찾습니다.

2. 승인할 Active Directory 그룹 이름을 추가합니다. 여러 그룹 이름을 따옴표와 각자 구분합니다. 예제:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. 설정을 `LDAPPath` 찾아 Active Directory 도메인을 추가합니다. 예제:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. 설정을 `AuthorizedEmailAddress` 찾아 전체 줄을 삭제합니다.

이 이미지는 역할 권한 부여를 위해 올바르게 형식이 지정된 **appsettings.json** 파일을 보여줍니다.

   ![역할 권한 부여 방법을 보여준 appsettings.json 파일입니다.](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>테넌트 및 키 설정

DKE 테넌트 및 키 설정은 **appsettings.json 파일에** 있습니다.

##### <a name="to-configure-tenant-and-key-settings-for-dke"></a>DKE에 대한 테넌트 및 키 설정을 구성하려면

1. **appsettings.json 파일을 열** 수 있습니다.

2. 설정을 `ValidIssuers` 찾아 `<tenantid>` 테넌트 ID로 대체합니다. Azure Portal로 이동하고 테넌트 속성을 확인하여 테넌트 [ID를 찾을 수 있습니다.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 예제:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

> [!NOTE]
> 키 저장소에 대한 외부 B2B 액세스를 사용하도록 설정하려면 이러한 외부 테넌트도 유효한 발급자 목록의 일부로 포함해야 합니다.

`JwtAudience`를 찾습니다. DKE 서비스가 실행될 컴퓨터의 호스트 `<yourhostname>` 이름으로 바 대체합니다. 예제:

  > [!IMPORTANT]
  > 의 값은 정확히 호스트의 `JwtAudience` 이름과 *일치해야 합니다.* 디버깅하는 동안 **localhost:5001을** 사용할 수 있습니다. 그러나 디버깅이 완료되면 이 값을 서버의 호스트 이름으로 업데이트해야 합니다.

- `TestKeys:Name`. 키 이름을 입력합니다. 예: `TestKey1`
- `TestKeys:Id`. GUID를 만들고 값으로 `TestKeys:ID` 입력합니다. 예를 들면 `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`와 같습니다. 온라인 GUID 생성기와 같은 사이트를 사용하여 [GUID를](https://guidgenerator.com/) 임의로 생성할 수 있습니다.

이 이미지는 **appsettings.json의** 테넌트 및 키 설정에 대한 올바른 형식을 보여줍니다. `LDAPPath` 는 역할 권한 부여를 위해 구성됩니다.

![appsettings.json 파일에서 DKE에 대한 올바른 테넌트 및 키 설정을 보여줍니다.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>테스트 키 생성

응용 프로그램 설정이 정의되면 공개 및 개인 테스트 키를 생성할 수 있습니다.

키를 생성하는 경우:

1. 시작 Windows 시작 메뉴 OpenSSL 명령 프롬프트를 실행합니다.

2. 테스트 키를 저장할 폴더로 변경합니다. 이 작업의 단계를 완료하여 만든 파일은 같은 폴더에 저장됩니다.

3. 새 테스트 키를 생성합니다.

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. 개인 키를 생성합니다.

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. 공개 키를 생성합니다.

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. 텍스트 편집기에서 **pubkeyonly.pem을 열 수 있습니다.** 첫 줄과 마지막 줄을 제외한 **pubkeyonly.pem** 파일의 모든 콘텐츠를 `PublicPem` **appsettings.json** 파일의 섹션에 복사합니다.

7. 텍스트 편집기에서 **privkeynopass.pem을 열 수 있습니다.** 첫 줄과 마지막 줄을 제외한 **privkeynopass.pem** 파일의 모든 콘텐츠를 `PrivatePem` **appsettings.json** 파일의 섹션에 복사합니다.

8. 및 섹션에서 공백과 줄임 표시를 `PublicPem` `PrivatePem` 모두 제거합니다.

    > [!IMPORTANT]
    > 이 콘텐츠를 복사할 때 PEM 데이터를 삭제하지 않습니다.

9. In Visual Studio Code, browse to the **Startup.cs** file. 이 파일은 로컬로 복제한 DoubleKeyEncryptionService 리포지션의 DoubleKeyEncryptionService\src\customer-key-store\에 있습니다.

10. 다음 줄을 찾습니다.

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. 이러한 줄을 다음 텍스트로 바 대체합니다.

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    최종 결과는 다음과 유사해야 합니다.

    ![공개 미리 보기용 startup.cs 파일입니다.](../media/dke-startupcs-usetestkeys.png)

이제 [DKE 프로젝트를 빌드할 준비가 완료되었습니다.](#build-the-project)

### <a name="build-the-project"></a>프로젝트 빌드

다음 지침을 사용하여 DKE 프로젝트를 로컬로 빌드합니다.

1. Visual Studio Code DKE 서비스 리포지토리에서 명령  팔레트 보기를 선택한 다음 프롬프트에 \>  **빌드를** 입력합니다.

2. 목록에서 작업: 빌드 작업 **실행 을 선택합니다.**

   빌드 작업을 찾을 수 없는  경우 다음과 같이 빌드 작업 구성을 선택하고 .NET core에 대해 빌드를 하나씩 만드면 됩니다.

   ![.NET에 대한 누락된 빌드 작업을 구성합니다.](../media/dke-configurebuildtask.png)

   1. 서식 **파일에서 tasks.json 만들기를 선택하십시오.**

      ![DKE용 템플릿에서 tasks.json 파일을 만듭니다.](../media/dke-createtasksjsonfromtemplate.png)

   2. 템플릿 유형 목록에서 **.NET Core 를 선택합니다.**

      ![DKE에 대한 올바른 템플릿을 선택합니다.](../media/dke-tasksjsontemplate.png)

   3. 빌드 섹션에서 **customerkeystore.csproj** 파일의 경로를 찾습니다. 이 목록에 없는 경우 다음 줄을 추가합니다.

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. 빌드를 다시 실행합니다.

3. 출력 창에 빨간색 오류가 없는지 확인해야 합니다.

   빨간색 오류가 있는 경우 콘솔 출력을 확인합니다. 이전 단계를 모두 올바르게 완료하고 올바른 빌드 버전이 있는지 확인합니다.

4. **디버깅** 시작 \> **실행을 선택하여** 프로세스를 디버그합니다. 환경을 선택하라는 메시지가 표시될 경우 **.NET core 를 선택합니다.**

   .NET 코어 디버거는 일반적으로 에 `https://localhost:5001` 실행됩니다. 테스트 키를 확인하기 위해 으로 이동하여 슬래시(/) 및 키 이름을 `https://localhost:5001` 추가합니다. 예제:

   ```https
   https://localhost:5001/TestKey1
   ```

   키는 JSON 형식으로 표시해야 합니다.

이제 설치가 완료되었습니다. 키스토어를 게시하기 전에 appsettings.json에서 JwtAudience 설정에 대해 호스트 이름의 값이 앱 서비스 호스트 이름과 정확히 일치해야 합니다. 빌드 문제를 해결하기 위해 localhost로 변경한 것일 수 있습니다.

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>DKE 서비스 배포 및 키 저장소 게시

프로덕션 배포의 경우 타사 클라우드에 서비스를 배포하거나, 사내 시스템에 [게시합니다.](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)

키를 배포하는 다른 방법을 사용하는 것이 좋습니다. 조직에 가장 적합한 방법을 선택합니다.

파일럿 배포의 경우 Azure에 배포하고 바로 시작할 수 있습니다.

#### <a name="to-create-an-azure-web-app-instance-to-host-your-dke-deployment"></a>DKE 배포를 호스트할 Azure Web App 인스턴스를 만들면

키 저장소를 게시하기 위해 Azure 앱 서비스 인스턴스를 만들어 DKE 배포를 호스트합니다. 다음으로 생성된 키를 Azure에 게시합니다.

1. 브라우저에서 Microsoft Azure [포털에](https://ms.portal.azure.com)로그인하고 앱 서비스 추가 로  >  **이동하세요.**

2. 구독 및 리소스 그룹을 선택하고 인스턴스 세부 정보를 정의합니다.

   - DKE 서비스를 설치할 컴퓨터의 호스트 이름을 입력합니다. [**appsettings.json**](#tenant-and-key-settings) 파일의 JwtAudience 설정에 정의된 이름과 같은지 확인 이름에 대해 제공하는 값은 WebAppInstanceName도 됩니다.

   - **게시에서** 코드를 **선택하고** 런타임 스택에 대해 **.NET Core 3.1을 선택합니다.** 

   예제:

   > [!div class="mx-imgBorder"]
   > ![앱 서비스를 추가합니다.](../media/dke-azure-add-app-service.png)

3. At the bottom of the page, select **Review + create**, and then select **Add**.

4. 다음 중 하나를 사용하여 생성된 키를 게시합니다.

   - [ZipDeployUI를 통해 게시](#publish-via-zipdeployui)
   - [FTP를 통해 게시](#publish-via-ftp)
   - [Visual Studio 2019 이상을 통해 게시](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>ZipDeployUI를 통해 게시

1. `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`로 이동합니다.

   예: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. 키 저장소의 코드베이스에서 **customer-key-store\src\customer-key-store** 폴더로 이동한 다음 이 폴더에 **customerkeystore.csproj** 파일이 포함되어 있는지 확인합니다.

3. 실행: **dotnet publish**

   출력 창에는 게시가 배포된 디렉터리가 표시됩니다.

   예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. 게시 디렉터리의 모든 파일을 파일로 .zip 전송합니다. .zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 수준에 있는지 확인합니다.

5. 만든 .zip 파일을 끌어서 위에서 연 ZipDeployUI 사이트로 놓습니다. 예: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE가 배포된 후 만든 테스트 키를 찾아볼 수 있습니다. 아래의 배포 [유효성 검사를 계속](#validate-your-deployment) 진행합니다.

#### <a name="publish-via-ftp"></a>FTP를 통해 게시

1. 커넥트 만든 앱 서비스에 [대한 설명입니다.](#deploy-the-dke-service-and-publish-the-key-store)

   브라우저에서 **Azure Portal** 앱 서비스 배포 센터 수동 배포  >    >    >  FTP **대시보드로**  >    >  **이동하세요.**

2. 표시되는 연결 문자열을 로컬 파일에 복사합니다. 이러한 문자열을 사용하여 Web App 서비스에 연결하고 FTP를 통해 파일을 업로드합니다.

   예제:

   ![FTP 대시보드에서 연결 문자열을 복사합니다.](../media/dke-ftp-dashboard.png)

3. 키 저장소에 대한 코드베이스에서 고객 키 **저장소\src\customer-key-store 디렉터리로 이동하십시오.**

4. 이 디렉터리에 **customerkeystore.csproj** 파일이 포함되어 있는지 확인합니다.

5. 실행: **dotnet publish**

   출력에는 게시가 배포된 디렉터리가 포함됩니다.

   예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. 게시 디렉터리의 모든 파일을 zip 파일로 전송합니다. .zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 수준에 있는지 확인합니다.

7. FTP 클라이언트에서 복사한 연결 정보를 사용하여 앱 서비스에 연결합니다. 업로드 만든 .zip Web App의 루트 디렉터리로 연결합니다.

DKE가 배포된 후 만든 테스트 키를 찾아볼 수 있습니다. 그런 다음 [배포의 유효성을 검사합니다.](#validate-your-deployment)

### <a name="validate-your-deployment"></a>배포 유효성 검사

위에서 설명한 방법 중 하나를 사용하여 DKE를 배포한 후 배포 및 키 저장소 설정의 유효성을 검사합니다.

을(를) 실행합니다.

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

예를 들면 다음과 같습니다.

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

출력에 오류가 나타나지 않도록 합니다. 준비가 되면 키 [저장소를 등록합니다.](#register-your-key-store)

키 이름은 대소문자 구분됩니다. appsettings.json 파일에 나타나는 키 이름을 입력합니다.

## <a name="register-your-key-store"></a>키 저장소 등록

다음 단계를 통해 DKE 서비스를 등록할 수 있습니다. 레이블 만들기를 시작하기 전에 DKE 서비스를 등록하는 것이 DKE 배포의 마지막 단계입니다.

DKE 서비스를 등록하는 경우:

1. 브라우저에서 Microsoft Azure [포털을 열고](https://ms.portal.azure.com/)모든 서비스  ID 앱 \>  \> **등록으로 이동하세요.**

2. 새 **등록 을** 선택하고 의미 있는 이름을 입력합니다.

3. 표시되는 옵션에서 계정 유형을 선택합니다.

   사용자 지정이 아닌 도메인(예: Microsoft Azure )에서 onmicrosoft.com 를 사용하는 경우 이 조직 디렉터리의 계정만(Microsoft 전용 - 단일 **테넌트)을** **선택합니다.**

   예제:

   > [!div class="mx-imgBorder"]
   > ![새 앱 등록.](../media/dke-app-registration.png)

4. 페이지 아래쪽에서 등록을  선택하여 새 앱 등록을 만드십시오.

5. 새 앱 등록의 왼쪽 창에 있는 관리에서 **인증을** **선택합니다.**

6. 플랫폼 **추가를 선택합니다.**

7. 플랫폼 **구성** 팝업에서 웹 을 **선택합니다.**

8. URI **리디렉션에서** 이중 키 암호화 서비스의 URI를 입력합니다. 호스트 이름과 도메인을 모두 포함하여 앱 서비스 URL을 입력합니다.

   예: https://mydkeservicetest.com

   - 입력하는 URL은 DKE 서비스가 배포된 호스트 이름과 일치해야 합니다.
   - 로컬로 테스트하는 경우 를 **https://localhost:5001** Visual Studio.
   - 모든 경우에 스키마는 **https 되어야 합니다.**

   호스트 이름을 앱 서비스 호스트 이름과 정확히 일치하도록 합니다. 빌드 문제를 해결하기 위해 `localhost` 변경한 것일 수 있습니다. **appsettings.json에서** 이 값은 에 대해 설정한 호스트 `JwtAudience` 이름입니다.

9. **암시적 부여에서** **ID 토큰** 확인란을 선택합니다.

10. 변경 내용을 저장하려면 **저장** 을 선택합니다.

11. 왼쪽 창에서 **API** 노출을 선택한 다음 응용 프로그램 ID URI 옆에 있는 설정 을 **선택합니다.**

12. API 표시 **페이지의** 이 **API에** 정의된 범위에서 범위 **추가를 선택합니다.** 새 범위에서 다음을 합니다.

    1. 범위 이름을 에 로 **user_impersonation.**

    2. 동의할 수 있는 관리자 및 사용자를 선택합니다.

    3. 필요한 나머지 값을 정의합니다.

    4. **범위 추가** 를 선택합니다.

    5. 맨 **위에** 저장을 선택하여 변경 내용을 저장합니다.

13. API 표시 **페이지의** 권한이 부여된 클라이언트 응용 프로그램 **영역에서** 클라이언트 응용 프로그램 **추가를 선택합니다.**

    새 클라이언트 응용 프로그램에서 다음을 실행합니다.

    1. 클라이언트 ID를 로 `d3590ed6-52b3-4102-aeff-aad2292ab01c` 정의합니다. 이 값은 Microsoft Office 클라이언트 ID로, Office 저장소에 대한 액세스 토큰을 얻을 수 있도록 합니다.

    2. 권한이 **부여된 범위에서** user_impersonation **선택합니다.**

    3. 응용 **프로그램 추가를 선택합니다.**

    4. 맨 **위에** 저장을 선택하여 변경 내용을 저장합니다.

    5. 이러한 단계를 반복하지만 이번에는 클라이언트 ID를 로 `c00e9d32-3c8d-4a7d-832b-029040e7db99` 정의합니다. 이 값은 Azure Information Protection 통합 레이블 지정 클라이언트 ID입니다.

이제 DKE 서비스가 등록됩니다. [DKE를 사용하여 레이블을 만들어 계속합니다.](#create-sensitivity-labels-using-dke)

## <a name="create-sensitivity-labels-using-dke"></a>DKE를 사용하여 민감도 레이블 만들기

이 Microsoft 365 규정 준수 센터 새 민감도 레이블을 만들고 다른 경우처럼 암호화를 적용합니다. 이중 **키 암호화 사용을 선택하고** 키의 끝점 URL을 입력합니다.

예제:

> [!div class="mx-imgBorder"]
> ![다음 목록에서 이중 키 암호화 사용을 Microsoft 365 규정 준수 센터.](../media/dke-use-dke.png)

추가한 모든 DKE 레이블은 최신 버전의 엔터프라이즈용 Microsoft 365 앱.

> [!NOTE]
> 클라이언트가 새 레이블로 새로 고쳐지기까지 최대 24시간이 걸릴 수 있습니다.

### <a name="enable-dke-in-your-client"></a>클라이언트에서 DKE 사용

If you're an Office Insider, DKE is enabled for you. 그렇지 않은 경우 다음 레지스트리 키를 추가하여 클라이언트에 대해 DKE를 사용하도록 설정하십시오.

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>HYOK 레이블에서 DKE 레이블로 보호된 파일 마이그레이션

원하는 경우 DKE 설정이 완료되면 HYOK 레이블을 사용하여 보호한 콘텐츠를 DKE 레이블로 마이그레이션할 수 있습니다. 마이그레이션하려면 AIP 스캐너를 사용하게 됩니다. 스캐너 사용을 시작하기 위해 Azure Information Protection 통합 레이블 지정 [스캐너란?을 참조하세요.](/azure/information-protection/deploy-aip-scanner)

콘텐츠를 마이그레이션하지 않는 경우 HYOK로 보호된 콘텐츠는 영향을 받지 않습니다.
