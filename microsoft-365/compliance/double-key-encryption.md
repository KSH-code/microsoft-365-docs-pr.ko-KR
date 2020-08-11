---
title: DKE (이중 암호화)
description: DKE를 사용 하면 중요 한 데이터를 보호 하 고 키에 대 한 모든 권한을 유지할 수 있습니다.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 0c66afa22c8712455a875bc8ca4ddcad1678e2e7
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602001"
---
# <a name="double-key-encryption-dke"></a>DKE (이중 암호화)

> *적용 대상: Microsoft 365 공개 미리 보기, [microsoft 365 준수](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection) 에 대 한 이중 암호화*
>
> *지침: [Azure Information Protection 통합 레이블 클라이언트 Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *서비스 설명: [Microsoft 365 준수](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

DKE (이중 암호화)에서는 보호 된 콘텐츠에 액세스 하기 위해 두 개의 키를 함께 사용 합니다. Microsoft Azure에 하나의 키를 저장 하 고 다른 키를 보유 하 고 있습니다. Azure Information Protection 통합 레이블 클라이언트는 중요 한 콘텐츠를 보호 하지만 키 중 하나에 대 한 모든 권한을 유지 합니다.

이중 키 암호화는 클라우드 및 온-프레미스 배포를 모두 지원 합니다. 이러한 배포를 통해 보호 된 데이터를 저장할 때마다 암호화 된 데이터를 불투명 하 게 유지할 수 있습니다.

클라우드 기반 테 넌 트 루트 키의 기본에 대 한 자세한 내용은 [Azure Information Protection 테 넌 트 키 계획 및 구현](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)를 참조 하세요.

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

조직에 다음과 같은 요구 사항이 있는 경우 DKE를 사용 하 여 콘텐츠를 안전 하 게 보호할 수 있습니다.

- 모든 상황에서 보호 된 콘텐츠의 암호를 *해독할 수 있도록* 해야 합니다.
- Microsoft가 보호 된 데이터에 자체 액세스 하지 못하도록 하려는 경우
- 지리적 경계 내에 키를 포함 하기 위한 규정 요구 사항이 있습니다. 데이터 암호화 및 암호 해독을 위해 보유 하는 모든 키가 데이터 센터에 유지 됩니다.

## <a name="system-and-licensing-requirements-for-dke"></a>DKE에 대 한 시스템 및 라이선스 요구 사항

Microsoft 365에 대 한 이중 키 암호화는 Microsoft 365 E5와 Office 365 E5와 함께 제공 됩니다. Microsoft 365 E5 라이선스가 없는 경우 [평가판](https://aka.ms/M365E5ComplianceTrial)에 등록할 수 있습니다. 이러한 라이선스에 대 한 자세한 내용은 [보안 & 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조 하세요.

**Office 참가자** 공개 미리 보기를 사용 하려면 Office 참가자 프로그램의 구성원 이어야 합니다. Office 참가자에 게 연결 하려면로 이동 [https://insider.office.com](https://insider.office.com) 합니다. 구성원 인 경우 조직에 적합 한 배포 방법을 선택 하 여 Office 참가자 빌드를 배포할 수 있도록 환경을 준비 합니다. 자세한 내용은 [Office 참가자 빌드 배포 시작](https://insider.office.com/business/deploy)을 참조 하세요.

**Azure Information Protection** DKE는 민감도 레이블에서 작동 하며 Azure Information Protection을 필요로 합니다.

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>DKE로 보호 된 콘텐츠를 저장 하 고 보기 위한 지원 되는 환경

**지원 되는 응용 프로그램** Word, Excel 및 PowerPoint를 포함 하는 Windows의 [엔터프라이즈 클라이언트용 Microsoft 365 앱](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)

**온라인 콘텐츠 지원** Microsoft SharePoint 및 비즈니스용 OneDrive에 모두 온라인으로 저장 된 문서 및 파일을 지원 합니다. 전자 메일로 암호화 된 콘텐츠를 공유할 수 있지만 암호화 된 문서 및 파일은 볼 수 없습니다. 대신 로컬 컴퓨터의 데스크톱 앱을 사용 하 여 보호 된 콘텐츠를 확인 해야 합니다.

## <a name="about-this-public-preview-article"></a>이 공개 미리 보기 문서 정보

몇 가지 단계를 완료 하 여 이중 암호화를 배포할 수도 있습니다. 이 문서에서는 숙련 된 관리자가 서비스를 성공적으로 배포 하는 데 필요한 자세한 지침을 제공 합니다. 이렇게 하는 것이 어려우면 사용자가 직접 메서드를 사용 하도록 선택할 수 있습니다.

이 문서에서는 Azure에 이중 키 암호화 서비스를 배포 하는 방법에 대 한 단계별 지침을 제공 합니다. 이 시나리오는 프로덕션 환경에서 발생할 수 있는 것이 아닙니다. 공개 미리 보기의 경우 Azure를 사용 하는 것이 DKE를 빠르게 배포 하는 방법입니다. Azure에 배포 하면 이중 키 암호화를 바로 사용할 수 있습니다.

서비스를 네트워크에 로컬로 배포 하거나 다른 공급자와 함께 배포할 수 있습니다. 해당 위치에 적합 한 방법을 사용 하 여 키 저장소를 게시 해야 합니다.

## <a name="deploy-double-key-encryption"></a>이중 암호화 배포

이 문서와 배포 동영상은 Azure를 DKE 서비스의 배포 대상으로 사용 합니다. 다른 위치에 배포 하는 경우에는 고유한 값을 제공 해야 합니다.

[이중 키 암호화 배포 비디오](https://youtu.be/vDWfHN_kygg) 를 시청 문서의 개념에 대 한 단계별 개요를 확인 하세요. 완료 하는 데 약 18 분 정도 걸립니다.

이러한 일반적인 단계를 수행 하 여 조직에 대 한 이중 암호화를 설정 합니다.

1. [소프트웨어 필수 구성 요소 설치](#install-software-prerequisites)
1. [이중 키 암호화 GitHub 리포지토리 복제](#clone-the-dke-github-repository)
1. [응용 프로그램 설정 수정](#modify-application-settings)
1. [테스트 키 생성](#generate-test-keys)
1. [프로젝트 빌드](#build-the-project)
1. [키 저장소 게시](#publish-the-key-store)
1. [배포 유효성 검사](#validate-your-deployment)
1. [키 저장소 등록](#register-your-key-store)
1. [민감도 레이블 만들기](#create-labels-using-dke)

작업이 완료 되 면 DKE을 사용 하 여 문서와 파일을 암호화할 수 있습니다. 자세한 내용은 [Office에서 파일 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)을 참조 하세요.

### <a name="install-software-prerequisites"></a>소프트웨어 필수 구성 요소 설치

이중 키 암호화에는 두 가지 유형의 소프트웨어 필수 구성 요소가 있습니다.

- [이중 키 암호화 서비스 필수 구성 요소](#double-key-encryption-service-prerequisites)
- [클라이언트 컴퓨터에 대 한 이중 키 암호화 필수 구성 요소](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a>이중 키 암호화 서비스 필수 구성 요소

DKE 서비스를 설치 하려는 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.

**.Net Core 3.1 SDK** [.Net Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)에서 SDK를 다운로드 하 여 설치 합니다.

**Visual Studio Code** Visual Studio Code from을 다운로드 [https://code.visualstudio.com/](https://code.visualstudio.com) 하세요. 설치가 완료 되 면 Visual Studio Code를 실행 하 고 Extensions **보기** 를 선택 \> **Extensions**합니다. 이러한 확장을 설치 합니다.

- Visual Studio 코드용 c # 코드

- NuGet 패키지 관리자

**Microsoft Office 참가자**입니다. [배포 방법을](https://insider.office.com/business/deploy)하나 이상 설정 합니다.

**Git 리소스** 다음 중 하나를 다운로드 하 여 설치 합니다.

- [Git](https://git-scm.com/downloads)

- [GitHub 데스크톱](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** DKE를 배포한 후 [테스트 키를 생성](#generate-test-keys) 하려면 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) 이 설치 되어 있어야 합니다. 환경 변수 경로에서 올바르게 호출 하 고 있는지 확인 합니다. 예를 들어 자세한 내용은 "설치 디렉터리를 PATH에 추가 합니다."를 참조 하십시오 https://www.osradar.com/install-openssl-windows/ .

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a>클라이언트 컴퓨터에 대 한 이중 키 암호화 필수 구성 요소

보호 된 문서를 보호 하 고 사용 하려는 각 클라이언트 컴퓨터에 이러한 필수 구성 요소를 설치 합니다.

**Microsoft Office** 버전 *. 12711 이상

**Azure Information Protection 통합 레이블 클라이언트** 버전 2.7.93.0 이상입니다. [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)에서 통합 레이블 클라이언트를 다운로드 하 여 설치 합니다.

### <a name="clone-the-dke-github-repository"></a>DKE GitHub 리포지토리 복제

Microsoft는 GitHub 리포지토리에 DKE 원본 파일을 제공 합니다. 조직의 사용을 위해 로컬로 프로젝트를 빌드하기 위해 리포지토리를 복제 합니다. DKE GitHub 리포지토리는에 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 있습니다.

다음 지침은 inexperienced git 또는 Visual Studio Code 사용자에 게 적합 합니다.

1. 브라우저에서 다음 위치로 이동 합니다.[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)

1. 화면 오른쪽 방향으로 **코드**를 선택 합니다. 사용자의 UI 버전에 **복제 또는 다운로드** 단추가 표시 될 수 있습니다. 그런 다음 표시 되는 드롭다운 목록에서 복사 아이콘을 선택 하 여 클립보드에 URL을 복사 합니다.

    예제:

   ![GitHub에서 이중 키 암호화 서비스 리포지토리 복제](../media/dke-clone.png)

3. Visual Studio Code에서 **View** \> **명령 색상표** 보기를 선택 하 고 **Git: 클론**을 선택 합니다. 목록에서 옵션으로 이동 하려면 입력을 시작 하 여 `git: clone` 항목을 필터링 한 다음 드롭다운에서 선택 합니다. 예제:

   ![Visual Studio Code GIT: Clone 옵션](../media/dke-vscode-clone.png)

4. Git에서 복사한 URL을 텍스트 상자에 붙여넣고 **GitHub에서 복제**를 선택 합니다.

5. **폴더 선택** 대화 상자가 나타나면 저장소를 저장할 위치를 찾아 선택 합니다. 프롬프트에서 **열기**를 선택 합니다.

    Visual Studio Code에서 리포지토리를 열고 왼쪽 아래에 현재 Git 분기를 표시 합니다. 분기는 **마스터**여야 합니다.

    예제:

   ![Visual Studio 코드 마스터 분기](../media/dke-vscode-master.png)

6. Word **마스터를** 선택한 다음 분기 목록에서 **public_preview** 를 선택 합니다.

   > [!IMPORTANT]
   > Public_preview 분기를 선택 하면 프로젝트를 빌드하는 데 올바른 파일이 있는지 확인할 수 있습니다. 올바른 분기를 선택 하지 않으면 배포가 실패 합니다.

이제 DKE 원본 리포지토리가 로컬로 설정 되었습니다. 다음으로, 조직의 [응용 프로그램 설정을 수정](#modify-application-settings) 합니다.

### <a name="modify-application-settings"></a>응용 프로그램 설정 수정

DKE 서비스를 배포 하려면 다음 유형의 응용 프로그램 설정을 수정 해야 합니다.

- [키 액세스 설정](#key-access-settings)
- [테 넌 트 및 키 설정](#tenant-and-key-settings)

파일의 appsettings.js에서 응용 프로그램 설정을 수정 합니다. 이 파일은 DoubleKeyEncryptionService\src\customer-key-store.에서 로컬로 복제 한 DoubleKeyEncryptionService 저장소에 있습니다. 예를 들어 Visual Studio Code에서는 다음 그림과 같이 파일을 탐색할 수 있습니다.

![DKE 용 파일에서 appsettings.js찾기](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>키 액세스 설정

전자 메일 또는 역할 인증을 사용할지를 선택 합니다. DKE에서는 이러한 인증 방법 중 하나를 한 번에 하나만 지원 합니다.

- **전자 메일 권한 부여** 조직에서 전자 메일 주소만 기반으로 하는 키에 대 한 액세스 권한을 부여할 수 있습니다.

- **역할 권한 부여** 조직에서 Active Directory 그룹을 기반으로 하는 키에 대 한 액세스 권한을 부여 하 고, 웹 서비스가 LDAP를 쿼리할 수 있도록 해야 합니다.

**전자 메일 인증을 사용 하 여 DKE에 대 한 키 액세스 설정을 설정 하려면**

1. 파일 **에서appsettings.js** 열고 `AuthorizedEmailAddress` 설정을 찾습니다.

2. 권한을 부여 하려는 전자 메일 주소를 추가 합니다. 여러 전자 메일 주소는 큰따옴표와 쉼표로 구분 합니다. 예제:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. 설정을 찾고 `LDAPPath` 큰따옴표 사이에 있는 텍스트를 제거 `If role authorization is used then this is the LDAP path` 합니다. 큰따옴표를 자리에 둡니다. 작업이 완료 되 면 설정은 다음과 같습니다.

   ```json
   "LDAPPath": ""
   ```

4. 설정을 찾아서 `AuthorizedRoles` 전체 줄을 삭제 합니다.

이 이미지는 전자 메일 권한 부여를 위해 올바르게 형식이 지정 된 파일 **의appsettings.js** 를 보여 줍니다.

   ![전자 메일 인증 방법을 보여 주는 appsettings.js파일](../media/dke-email-accesssetting.png)

**역할 인증을 사용 하 여 DKE에 대 한 키 액세스 설정을 설정 하려면**

1. 파일 **에서appsettings.js** 열고 `AuthorizedRoles` 설정을 찾습니다.

2. 권한을 부여 하려는 Active Directory 그룹 이름을 추가 합니다. 여러 그룹 이름은 큰따옴표와 쉼표로 구분 합니다. 예제:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. 설정을 찾고 `LDAPPath` Active Directory 도메인을 추가 합니다. 예제:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. 설정을 찾아서 `AuthorizedEmailAddress` 전체 줄을 삭제 합니다.

이 이미지는 역할 권한 부여를 위해 올바르게 형식이 지정 된 파일 **의appsettings.js** 를 보여 줍니다.

   ![역할 인증 방법을 보여 주는 파일의 appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>테 넌 트 및 키 설정

DKE 테 넌 트 및 키 설정은 파일 **의appsettings.js** 에 있습니다.

**DKE에 대 한 테 넌 트 및 키 설정을 구성 하려면**

1. 파일 **에서appsettings.js** 엽니다.

2. 설정을 찾은 `ValidIssuers` 후 `<tenantid>` 테 넌 트 ID로 바꿉니다. Azure 포털로 이동 하 여 [테 넌 트 속성](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)을 확인 하 여 테 넌 트 ID를 찾을 수 있습니다. 예제:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

를 찾습니다 `JwtAudience` . `<yourhostname>`DKE 서비스가 실행 될 컴퓨터의 호스트 이름으로 대체 합니다. 예제:



  > [!IMPORTANT]
  > 값은 `JwtAudience` 호스트 이름과 *정확히*일치 해야 합니다. 디버깅 하는 동안 **localhost: 5001** 을 사용할 수 있습니다. 그러나 디버깅이 완료 되 면이 값을 서버의 호스트 이름으로 업데이트 해야 합니다.

- `TestKeys:Name`. 키의 이름을 입력 합니다. 예: `TestKey1`
- `TestKeys:Id`. GUID를 만들어 값으로 입력 `TestKeys:ID` 합니다. 예를 들면 `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`와 같습니다. [온라인 Guid 생성기](https://guidgenerator.com/) 와 같은 사이트를 사용 하 여 GUID를 임의로 생성할 수 있습니다.

**appsettings.js**의 테 넌 트 및 키 설정에 대 한 올바른 형식을 표시 하는 이미지입니다. `LDAPPath`역할 인증에 대해 구성 됩니다.

![파일의 appsettings.js에 있는 DKE에 대 한 올바른 테 넌 트 및 키 설정을 표시 합니다.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>테스트 키 생성

응용 프로그램 설정을 정의한 후에는 공용 및 개인 테스트 키를 생성할 수 있습니다.

키를 생성 하려면

1. Windows 시작 메뉴에서 OpenSSL 명령 프롬프트를 실행 합니다.

1. 테스트 키를 저장할 폴더로 변경 합니다. 이 작업의 단계를 완료 하 여 만든 파일은 동일한 폴더에 저장 됩니다.

1. 새 테스트 키를 생성 합니다.

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. 개인 키를 생성 합니다.

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. 공개 키를 생성 합니다.

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. 텍스트 편집기에서 **pubkeyonly**를 엽니다. 파일의appsettings.js섹션에 있는 첫 번째 행과 마지막 줄을 제외한 **pubkeyonly pem** 파일의 모든 콘텐츠를 복사 합니다. `PublicPem` **appsettings.json**

1. 텍스트 편집기에서 **privkeynopass**를 엽니다. **Privkeynopass** 파일에서 첫 번째 줄을 제외한 모든 콘텐츠를 `PrivatePem` 파일 **의appsettings.js** 섹션에 복사 합니다.

1. 및 섹션 모두에서 공백 및 newlines를 모두 `PublicPem` 제거 `PrivatePem` 합니다.

    > [!IMPORTANT]
    > 이 콘텐츠를 복사할 때는 PEM 데이터를 삭제 하지 마십시오.

1. Visual Studio Code에서 **Startup.cs** 파일을 찾습니다. 이 파일은 DoubleKeyEncryptionService\src\customer-key-store\.에서 로컬로 복제 한 DoubleKeyEncryptionService 저장소에 있습니다.

2. 다음 줄을 찾습니다.

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. 다음 텍스트를이 줄로 바꿉니다.

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   최종 결과는 다음과 같습니다.

   ![공용 미리 보기용 startup.cs 파일](../media/dke-startupcs-usetestkeys.png)

이제 [DKE 프로젝트를 빌드할](#build-the-project)준비가 되었습니다.

### <a name="build-the-project"></a>프로젝트 빌드

다음 지침을 사용 하 여 DKE 프로젝트를 로컬로 빌드합니다.

1. Visual Studio Code의 dke 서비스 저장소에서 **View** \> **명령 색상표** 보기를 선택 하 고 프롬프트에서 **빌드** 를 입력 합니다.

1. 목록에서 **작업: 빌드 작업 실행**을 선택 합니다.

   빌드 작업을 찾을 수 없는 경우에는 **빌드 작업 구성을** 선택 하 고 다음과 같이 .net core에 대해 create build tasks를 만듭니다.

   ![.NET에 대 한 누락 된 빌드 작업 구성](../media/dke-configurebuildtask.png)

   1. **서식 파일에서 tasks.js만들기**를 선택 합니다.

   ![DKE 템플릿의 파일에서 tasks.js만들기](../media/dke-createtasksjsonfromtemplate.png)

   2. 템플릿 유형 목록에서 **.Net Core**를 선택 합니다.

   ![DKE 템플릿의 파일에서 tasks.js만들기](../media/dke-tasksjsontemplate.png)

   3. 빌드 섹션에서 **customerkeystore** 파일의 경로를 찾습니다. 여기에 해당 하지 않으면 다음 줄을 추가 합니다.

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. 빌드를 다시 실행 합니다.

1. 출력 창에 빨간색 오류가 없는지 확인 합니다.

   빨간색 오류가 있으면 콘솔 출력을 확인 합니다. 이전 단계를 모두 올바르게 완료 했으며 올바른 빌드 버전이 있는지 확인 합니다.

2. **Run** \> **디버깅 시작** 을 선택 하 여 프로세스를 디버깅 합니다. 환경을 선택 하 라는 메시지가 표시 되 면 **.net core**를 선택 합니다.

일반적으로 .net 핵심 디버거는 ' ' '를 시작 하 https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 고 슬래시 (/)와 키 이름을 추가 합니다. 예제:

```https
https://localhost:5001/TestKey1
```

키가 JSON 형식으로 표시 되어야 합니다.

이제 설치가 완료 되었습니다. Keystore를 게시 하기 전에 JwtAudience 설정에 대 한 appsettings.json에서 호스트 값이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다. 빌드 문제를 해결 하기 위해 localhost로 변경 했을 수 있습니다.

### <a name="publish-the-key-store"></a>키 저장소 게시

키 저장소를 게시 하려면 DKE 배포를 호스트 하는 Azure App Service 인스턴스를 만듭니다. 다음에는 생성 된 키를 Azure에 게시 합니다.

**DKE 배포를 호스트 하는 Azure Web App 인스턴스를 만들려면**

1. 브라우저에서 [Microsoft Azure 포털](https://ms.portal.azure.com)에 로그인 하 고 **앱 서비스**  >  **추가**로 이동 합니다.

1. 구독 및 리소스 그룹을 선택 하 고 인스턴스 세부 정보를 정의 합니다.

    - DKE 서비스를 설치 하려는 컴퓨터의 호스트 이름을 입력 합니다. 파일 [**의appsettings.js**](#tenant-and-key-settings) 에서 JwtAudience 설정에 대해 정의 된 이름과 이름이 같은지 확인 합니다. 이름에 입력 하는 값은 WebAppInstanceName입니다.

    - **게시**에서 **코드**를 선택 하 고 **런타임 스택을**보려면 **.net Core 3.1**를 선택 합니다.

    예제:

   ![앱 서비스 추가](../media/dke-azure-add-app-service.png)

1. 페이지 맨 아래에서 **검토 + 만들기**를 선택한 다음 **추가**를 선택 합니다.

1. 다음 중 하나를 수행 하 여 생성 된 키를 Azure에 게시 합니다.

    - [ZipDeployUI를 통해 게시](#publish-via-zipdeployui)
    - [FTP를 통해 게시](#publish-via-ftp)
    - [Visual Studio 2019 이상 버전을 통해 게시](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [온-프레미스 시스템에 게시](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > 다른 방법으로 키를 배포할 수도 있습니다. 조직에 가장 적합 한 방법을 선택 합니다.

    > [!TIP]
    > [Visual Studio를 통해](https://docs.microsoft.com/aspnet/core/tutorials/) [온-프레미스 시스템](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) 에 게시 하는 방법에 대 한 자세한 내용은 [ASP .net 설명서](https://docs.microsoft.com/aspnet/core/)를 참조 하십시오. 이러한 방법 중 하나를 사용 하는 경우에는 작업을 마친 후 쉽게 반환할 수 있도록 별도의 탭에서 명령을 엽니다.

#### <a name="publish-via-zipdeployui"></a>ZipDeployUI를 통해 게시

1. `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`(으)로 이동합니다.

    예: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

1. 키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store** 폴더로 이동 하 여이 폴더에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.

1. 실행: **dotnet 게시**

     출력 창에는 게시가 배포 된 디렉터리가 표시 됩니다.

    예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. 게시 디렉터리의 모든 파일을 .zip 파일로 보냅니다. .Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.

1. 위에서 연 ZipDeployUI 사이트에 만든 .zip 파일을 끌어서 놓습니다. 예: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다. 아래에서 [배포에 대 한 유효성 검사](#validate-your-deployment) 를 계속 합니다.

#### <a name="publish-via-ftp"></a>FTP를 통해 게시

1. [위에서](#publish-the-key-store)만든 앱 서비스에 연결 합니다.

    브라우저에서 **Azure portal**  >  **App Service**  >  **배포 센터**  >  **수동 배포**  >  **FTP**  >  **대시보드로**이동 합니다.

1. 로컬 파일에 표시 되는 연결 문자열을 복사 합니다. 이러한 문자열을 사용 하 여 웹 앱 서비스에 연결 하 고 FTP를 통해 파일을 업로드 합니다.

    예제:

   ![FTP 대시보드에서 연결 문자열 복사](../media/dke-ftp-dashboard.png)

1. 키 저장소의 코드 베이스에서 **customer-key-store\src\customer-key-store 디렉터리로**이동 합니다.

1. 이 디렉터리에 **customerkeystore** 파일이 포함 되어 있는지 확인 합니다.

1. 실행: **dotnet 게시**

    출력에는 게시가 배포 된 디렉터리가 포함 됩니다.

    예: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. 게시 디렉터리의 모든 파일을 zip 파일로 보냅니다. .Zip 파일을 만들 때 디렉터리의 모든 파일이 .zip 파일의 루트 수준에 있는지 확인 합니다.

1. FTP 클라이언트에서 복사한 연결 정보를 사용 하 여 앱 서비스에 연결 합니다. 이전 단계에서 만든 .zip 파일을 웹 응용 프로그램의 루트 디렉터리에 업로드 합니다.

DKE가 배포 되었으며 만든 테스트 키로 이동할 수 있습니다. 다음으로, [배포 유효성을 검사](#validate-your-deployment)합니다.

### <a name="validate-your-deployment"></a>배포 유효성 검사

위에 설명 된 방법 중 하나를 사용 하 여 DKE를 배포한 후에는 배포 및 키 저장소 설정의 유효성을 검사 합니다.

을 실행합니다.

src\customer-key-store\scripts\key_store_tester.ps1 mykeymykey url/

예제:

key_store_tester.ps1https://mycustomerkeystore.com/mykey

출력에 오류가 표시 되지 않는지 확인 합니다. 준비 되 면 [키 저장소를 등록](#register-your-key-store)합니다.

## <a name="register-your-key-store"></a>키 저장소 등록

다음 단계를 수행 하면 키 저장소를 등록할 수 있습니다. 레이블 만들기를 시작 하기 전에 키 저장소를 등록 하는 것은 DKE를 배포 하는 마지막 단계입니다.

키 저장소를 등록 하려면:

1. 브라우저에서 [Microsoft Azure portal](https://ms.portal.azure.com/)을 열고 **모든 서비스** \> **id** \> **앱 등록**으로 이동 합니다.

2. **새 등록**을 선택 하 고 의미 있는 이름을 입력 합니다.

3. 표시 된 옵션에서 계정 유형을 선택 합니다.

    사용자 지정 하지 않은 도메인 (예: **onmicrosoft.com**)에서 Microsoft Azure를 사용 하는 경우 **에는이 조직 디렉터리의 계정만 선택 합니다 (Microsoft only 단일 테 넌 트).**

    예제:

   ![새 앱 등록](../media/dke-app-registration.png)

4. 페이지 맨 아래에서 **등록** 을 선택 하 여 새 앱 등록을 만듭니다.

5. 새 앱 등록의 왼쪽 창에 있는 **관리**에서 **인증**을 선택 합니다.

6. **플랫폼 추가를**선택 합니다.
 
7. **플랫폼 구성** 팝업에서 **웹**을 선택 합니다.
 
8. **리디렉션 uri**에서 이중 키 암호화 서비스의 URI를 입력 합니다. 호스트 이름 및 도메인을 포함 하 여 앱 서비스 URL을 입력 합니다.

    예: https://mycustomerkeystoretest.com

    - 입력 하는 URL은 키 저장소가 배포 된 호스트 이름과 일치 해야 합니다.
    - Visual Studio를 사용 하 여 로컬로 테스트 하는 경우를 사용 **https://localhost:5001** 합니다.
    - 모든 경우에 스키마는 **https**여야 합니다.

    호스트 이름이 앱 서비스 호스트 이름과 정확히 일치 하는지 확인 합니다. 빌드 문제를 해결 하기 위해 변경 했을 수 있습니다 `localhost` . **appsettings.js**설정에서이 값은 설정한 호스트 이름입니다 `JwtAudience` .

6. **암시적 권한 부여**에서 **ID 토큰** 확인란을 선택 합니다.

1. 변경 내용을 저장하려면 **저장**을 선택합니다.

7. 왼쪽 창에서 **API 노출**을 선택한 다음 응용 프로그램 ID URI 옆에 있는 **설정**을 선택 합니다.

9. 여전히 **Api 노출** 페이지의 **이 API** 영역에 정의 된 범위에서 **범위 추가**를 선택 합니다. 새 범위에서 다음을 수행 합니다.

    1. 범위 이름을 **user_impersonation**로 정의 합니다.

    2. 동의할 수 있는 관리자 및 사용자를 선택 합니다.

    3. 필요한 나머지 값을 정의 합니다.

    4. **범위 추가를 선택 합니다.**

    맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.

10. 여전히 **API 노출** 페이지의 **권한 있는 클라이언트 응용 프로그램** 영역에서 **클라이언트 응용 프로그램 추가**를 선택 합니다.

    새 클라이언트 응용 프로그램에서 다음을 수행 합니다.

    1. 클라이언트 ID를 **d3590ed6-52b3-4102-aeff-aad2292ab01c**으로 정의 합니다. 이 값은 Microsoft Office 클라이언트 ID 이며 Office에서 키 저장소에 대 한 액세스 토큰을 가져올 수 있도록 합니다.

    2. **권한 있는 범위**에서 **user_impersonation** 범위를 선택 합니다.

    3. **응용 프로그램 추가**를 선택 합니다.

    4. 맨 위에 있는 **저장** 을 선택 하 여 변경 내용을 저장 합니다.

이제 DKE 키 저장소가 등록 되었습니다. 계속 [하 여 DKE를 사용 하 여 레이블을 만듭니다](#create-labels-using-dke).

## <a name="create-labels-using-dke"></a>DKE을 사용 하 여 레이블 만들기

Microsoft 365 준수 센터에서 새 민감도 레이블을 만들고 암호화를 다른 방법으로 적용 합니다. **이중 키 암호화 사용** 을 선택 하 고 키에 대 한 끝점 URL을 입력 합니다.

예제:

![Microsoft 365 준수 센터에서 이중 키 암호화 사용을 선택 합니다.](../media/dke-use-dke.png)

추가 하는 모든 DKE 레이블은 최신 버전의 Microsoft 365 Apps for enterprise의 사용자에 게 표시 되기 시작 합니다.

> [!NOTE]
> 클라이언트가 새 레이블로 새로 고치는 데 최대 24 시간이 걸릴 수 있습니다.

### <a name="enable-dke-in-your-client"></a>클라이언트에서 DKE 사용

다음 레지스트리 키를 추가 하 여 클라이언트에 대해 DKE를 사용 하도록 설정 합니다.

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
