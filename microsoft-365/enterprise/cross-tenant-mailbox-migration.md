---
title: 교차 테넌트 사서함 마이그레이션
description: Microsoft 365 또는 Office 365 테넌트 간에 사서함을 이동하는 방법
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: d81e272cfe50aa8379135406cbe538fbc8a18cb5
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454232"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>테넌트 간 사서함 마이그레이션(미리 보기)

이전에는 Exchange Online 테넌트가 동일한 Exchange Online 서비스의 다른 테넌트로 사서함을 이동해야 했던 경우 온-프레미스로 사서함을 완전히 오프보드한 다음 새 테넌트에 온보드해야 합니다. 새로운 테넌트 간 사서함 마이그레이션 기능을 사용하면 원본 및 대상 테넌트의 테넌트 관리자가 모든 테넌트 간에 사서함을 이동할 수 있으며, 해당 테넌트의 인프라 종속성은 최소한의 수준으로 유지될 수 있습니다. 이렇게 하여 사서함을 오프보드하고 온보드할 필요가 없습니다.

일반적으로 인수 또는 매입 중에 사용자와 콘텐츠를 새 테넌트로 이동하는 능력이 필요합니다. 대상 테넌트 관리자가 이동을 실행하면 온-프레미스에서 클라우드 온보더링 마이그레이션과 유사하게 끌어오기 이동이라고 합니다.

테넌트 간 Exchange 사서함 이동은 테넌트 관리자가 완전히 셀프 서비스하여 사용자를 새 조직으로 전환하는 데 필요한 더 큰 워크플로로 스크립팅할 수 있는 잘 알려진 인터페이스를 사용합니다. 관리자는 사서함 이동 관리 역할을 통해 사용할 수 있는 cmdlet을 사용하여 테넌트 간 이동을 실행할 `New-MigrationBatch` 수 있습니다. 이동 프로세스에는 사서함 동기화 및 완료 중에 테넌트 권한 부여 검사가 포함됩니다. 
 
테넌트 간 이동을 사용하도록 설정하려면 대상 테넌트 Exchange Online 시스템에 특정 특성이 표시된 MailUsers로 마이그레이션하는 사용자가 있어야 합니다. 대상 테넌트에서 제대로 설정되지 않은 사용자에 대해 시스템이 이동되지 않습니다.  

이동이 완료되면 원본 시스템 사서함이 MailUser로 변환하고 targetAddress(Exchange의 ExternalEmailAddress로 표시)는 대상 테넌트에 대한 라우팅 주소로 스탬프가 지정됩니다. 이 프로세스는 원본 테넌트에 레거시 MailUser를 그대로 남겨두고 공조 및 메일 라우팅을 허용합니다. 비즈니스 프로세스에서 허용하는 경우 원본 테넌트가 원본 MailUser를 제거하거나 메일 연락처로 변환할 수 있습니다. 

테넌트 간 Exchange 사서함 마이그레이션은 하이브리드 또는 클라우드의 테넌트 또는 둘의 임의 조합에 대해 지원됩니다.

이 문서에서는 테넌트 간 사서함 이동 프로세스에 대해 설명하고 콘텐츠 이동을 위해 원본 및 대상 테넌트를 준비하는 방법에 대한 지침을 제공합니다.  

## <a name="preparing-source-and-target-tenants"></a>원본 및 대상 테넌트 준비

테넌트 간 Exchange 사서함 마이그레이션 기능을 사용하려면 테넌트 간 마이그레이션을 위한 권한 부여 및 검색이 필요합니다. Azure Enterprise 응용 프로그램 및 Key Vault 저장소 솔루션을 사용하여 테넌트 관리자는 이제 한 테넌트에서 다른 테넌트로 Exchange Online 사서함 마이그레이션의 권한 부여 및 확장을 관리할 수 있습니다. 테넌트 간 사서함 이동은 초대 및 동의 모델을 지원하여 테넌트 쌍 간의 인증에 사용되는 Azure AD(Azure Active Directory) 응용 프로그램을 설정할 수 있습니다. 조직 관계 및 마이그레이션 끝점과 같은 추가 구성 요소도 필요합니다.

이 섹션에는 대상 디렉터리에서 MailUser 사용자 개체를 준비하는 데 필요한 특정 단계가 포함되어 있지 않으며 마이그레이션 일괄 처리를 제출하기 위한 예제 명령도 포함되어 있지 않습니다. 이 정보는 마이그레이션을 위해 대상 [사용자 개체 준비를](#prepare-target-user-objects-for-migration) 참조하세요.

## <a name="prerequisites"></a>필수 구성 요소

테넌트 간 사서함 이동 기능을 사용하려면 [Azure Key Vault가](https://docs.microsoft.com/azure/key-vault/basic-concepts) 테넌트 쌍별 Azure 응용 프로그램을 설정하여 한 테넌트에서 다른 테넌트로의 사서함 마이그레이션을 인증하고 권한을 부여하는 데 사용되는 인증서/비밀을 안전하게 저장하고 액세스하고 테넌트 간에 인증서/비밀을 공유하기 위한 요구 사항을 제거해야 합니다. 

시작하기 전에 Azure Key Vault, 사서함 응용 프로그램 이동, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성하기 위해 배포 스크립트를 실행하기 위해 필요한 사용 권한이 있는지 확인해야 합니다. 일반적으로 전역 관리자에게는 모든 구성 단계를 수행할 수 있는 권한이 있습니다.

또한 설치를 실행하기 전에 원본 테넌트의 메일 사용이 가능한 보안 그룹이 필요합니다. 이러한 그룹은 원본(또는 리소스라고도 하는) 테넌트에서 대상 테넌트로 이동할 수 있는 사서함 목록의 범위를 지정하는 데 사용됩니다. 이렇게 하면 원본 테넌트 관리자가 이동해야 하는 특정 사서함 집합을 제한하거나 범위를 지정하여 의도하지 않은 사용자가 마이그레이션되지 않도록 할 수 있습니다. 중첩된 그룹은 지원되지 않습니다.

또한 Microsoft 365 테넌트 ID를 얻기 위해 신뢰할 수 있는 파트너 회사(사서함을 이동하는 파트너)와 통신해야 합니다. 이 테넌트 ID는 조직 관계 필드에 `DomainName` 사용됩니다.

구독의 테넌트 ID를 얻습니다. Microsoft 365 관리 센터에 로그인하여 로 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 이동하세요. 테넌트 ID 속성의 복사 아이콘을 클릭하여 클립보드에 복사합니다.

다음은 프로세스의 작동 방식입니다.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="사서함 마이그레이션을 위한 테넌트 준비":::

[이 이미지의 더 큰 버전을 참조합니다.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>테넌트 준비

높은 수준에서는 설치 스크립트를 실행할 때 다음 구성 작업이 수행됩니다.

대상 테넌트 준비:

1. 기존 Azure 리소스 그룹을 제공하지 않은 경우 새 Azure 리소스 그룹(SCRIPT)이 만들어집니다.
2. 기존 Key Vault가 제공되지 않은 경우 새 키 자격 증명 모음(SCRIPT)이 만들어집니다.
3. Office 365 Exchange Online 사서함 마이그레이션 응용 프로그램(SCRIPT)에 대한 새 액세스 정책이 만들어집니다.
4. SCRIPT(마이그레이션 응용 프로그램)에 대한 비밀을 보유하기 위해 새 인증서(또는 지정된 경우 기존 인증서)가 만들어집니다.
5. 새 Azure AD 응용 프로그램(SCRIPT)이 만들어집니다.
6. 인증서/비밀이 마이그레이션 응용 프로그램(SCRIPT)에 업로드됩니다.
7. 사서함 마이그레이션 권한이 응용 프로그램(SCRIPT)에 할당됩니다.
8. 배포 스크립트는 대상 관리자가 자신의 응용 프로그램(SCRIPT)에 동의할 때까지 일시 중지됩니다.
9. 대상 테넌트 관리자는 응용 프로그램(MANUAL)에 부여된 사용 권한에 동의합니다.
10. 조직 관계가 대상 테넌트(SCRIPT)에 만들어집니다.
11. 마이그레이션 끝점은 대상 테넌트(SCRIPT)로 사서함을 끌어오기 위해 만들어집니다.

원본 테넌트 준비:

1. 원본 테넌트 관리자는 대상 테넌트(MANUAL)에서 사서함 마이그레이션 응용 프로그램 초대에 동의합니다.
2. 원본 테넌트 관리자는 마이그레이션 응용 프로그램(MANUAL)에서 이동할 수 있는 사서함 목록을 포함하도록 테넌트에 메일 사용이 가능한 보안 그룹을 만듭니다.
3. 사서함 마이그레이션 응용 프로그램을 지정하는 대상 테넌트에 조직 관계가 만들어지며, OAuth 확인을 통해 SCRIPT(이동 요청)를 수락해야 합니다.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>대상 테넌트 관리자에 대한 단계별 지침

1. GitHub 리포지토리에서 SetupCrossTenantRelationshipForTargetTenant.ps1 테넌트 설정에 대한 앱 [스크립트를 다운로드합니다.](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. 스크립트를 실행할 컴퓨터에 SetupCrossTenantRelationshipForTargetTenant.ps1(스크립트)를 저장합니다.
3. Exchange Online 대상 테넌트에 대한 원격 PowerShell 연결을 생성합니다. Azure Key Vault 저장소 및 인증서, 사서함 응용 프로그램 이동, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성하기 위해 배포 스크립트를 실행하기 위해 필요한 사용 권한이 있는지도 확인하십시오.
4. 파일 폴더 디렉터리를 스크립트 위치로 변경하거나 스크립트가 현재 원격 PowerShell 세션의 위치에 저장되어 있는지 확인합니다.
5. 다음 매개 변수와 값으로 스크립트를 실행합니다.

    | 매개 변수 | 값 | 필수 또는 선택 사항
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | 대상 테넌트 도메인(예: fabrikam \. onmicrosoft.com. | 필수 |
    | -ResourceTenantDomain                       | 원본 테넌트 도메인(예: contoso \. onmicrosoft.com. | 필수 |
    | -ResourceTenantAdminEmail                   | 원본 테넌트 관리자의 전자 메일 주소입니다. 대상 관리자가 보낸 사서함 마이그레이션 응용 프로그램 사용에 동의하는 원본 테넌트 관리자입니다. 이 관리자는 응용 프로그램에 대한 전자 메일 초대를 받게 됩니다. | 필수 |
    | -ResourceTenantId                           | 원본 테넌트 조직 ID(GUID)입니다. | 필수 |
    | -SubscriptionId                             | 리소스를 만드는 데 사용할 Azure 구독입니다. | 필수 |
    | -ResourceGroup                              | 키 자격 증명 모음을 포함하거나 포함할 Azure 리소스 그룹 이름입니다. | 필수 |
    | -KeyVaultName                               | 사서함 마이그레이션 응용 프로그램 인증서/비밀을 저장할 Azure Key Vault 인스턴스입니다. | 필수 |
    | -CertificateName                            | 키 자격 증명 모음에서 인증서를 생성하거나 검색할 때의 인증서 이름입니다. | 필수 |
    | -CertificateSubject                         | Azure Key Vault 인증서 주체 이름(예: CN=contoso_fabrikam. | 필수 |
    | -ExistingApplicationId                      | 이미 만들어진 경우 사용할 메일 마이그레이션 응용 프로그램입니다. | 선택 |
    | -AzureAppPermissions                        | Exchange 또는 MSGraph와 같은 사서함 마이그레이션 응용 프로그램에 부여되는 데 필요한 사용 권한(사서함 이동을 위한 Exchange, 리소스 테넌트에 동의 링크 초대를 보내는 데 이 응용 프로그램을 사용하는 경우 MSGraph) | 필수 |
    | -UseAppAndCertGeneratedForSendingInvitation | 원본 테넌트 관리자에게 동의 링크 초대를 보내는 데 사용할 마이그레이션을 위해 만든 응용 프로그램을 사용하는 매개 변수입니다. 이 메시지가 없는 경우 대상 관리자의 자격 증명을 사용하여 Azure 초대 관리자에 연결하고 초대를 대상 관리자로 보낼지 묻는 메시지가 표시됩니다. | 선택 |
    | -KeyVaultAuditStorageAccountName            | Key Vault의 감사 로그가 저장될 저장소 계정입니다. | 선택 |
    | -KeyVaultAuditStorageResourceGroup          | 키 자격 증명 모음 감사 로그를 저장하기 위한 저장소 계정이 포함된 리소스 그룹입니다. | 선택 |
    ||||

    >[!Note]
    > 스크립트를 실행하기 전에 Azure AD PowerShell 모듈을 설치해야 합니다. 설치 단계는 ![ 여기를 ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) 참조하세요.

6. 이 스크립트는 일시 중지 하 고이 프로세스 중에 만든 Exchange 사서함 마이그레이션 응용 프로그램에 동의 또는 동의를 요청 합니다. 예를 들면 다음과 같습니다.

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. URL이 원격 PowerShell 세션에 표시됩니다. 테넌트 동의에 대해 제공된 링크를 복사하여 웹 브라우저에 붙여넣습니다.

8. 전역 관리자 자격 증명으로 로그인합니다. 다음 화면이 표시된 경우 수락을 **선택합니다.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="사용 권한 수락 대화 상자":::

9. 원격 PowerShell 세션으로 다시 전환하고 Enter를 입력하여 계속 진행합니다.

10. 스크립트는 나머지 설치 개체를 구성합니다. 예를 들면 다음과 같습니다.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

이제 대상 관리자 설정이 완료되었습니다!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>원본 테넌트 관리자에 대한 단계별 지침

1.  설치하는 동안 대상 관리자가 지정한 -ResourceTenantAdminEmail로 사서함에 로그인합니다. 대상 테넌트에서 전자 메일 초대를 찾은 다음 시작 **단추를** 선택합니다.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="초대를 들은 대화 상자":::

2. **수락을** 선택하여 초대를 수락합니다.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="사용 권한을 수락할 대화 상자":::

   > [!NOTE]
   > 이 전자 메일을 수신하지 못하거나 찾을 수 없는 경우 대상 테넌트 관리자가 초대를 수락할 수 있는 직접 URL을 제공했습니다. URL은 대상 테넌트 관리자의 원격 PowerShell 세션의 스크립트에 입력해야 합니다.

3. Microsoft 365 관리 센터 또는 원격 PowerShell 세션에서 하나 이상의 메일 사용이 가능한 보안 그룹을 만들어 대상 테넌트가 원본 테넌트에서 대상 테넌트로 끌어오기(이동)할 수 있는 사서함 목록을 제어합니다. 이 그룹을 미리 채우지 않고도 설정 단계(스크립트)를 실행하려면 하나 이상의 그룹을 제공해야 합니다. 중첩 그룹은 지원되지 않습니다. 

4. GitHub 리포지토리에서 SetupCrossTenantRelationshipForResourceTenant.ps1 테넌트 설정에 대한 앱 스크립트를 [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 다운로드합니다. . 

5. Exchange 관리자 권한을 사용하여 원본 테넌트에 대한 원격 PowerShell 연결을 만들 수 있습니다. 전역 관리자 권한은 원본 테넌트 구성에 필요하지 않습니다. Azure 응용 프로그램 만들기 프로세스 때문에 대상 테넌트만 구성할 수 있습니다.

6. 디렉터리를 스크립트 위치로 변경하거나 스크립트가 현재 원격 PowerShell 세션의 위치에 저장되어 있는지 확인합니다.

7. 다음 필수 매개 변수와 값을 사용하여 스크립트를 실행합니다.

    | 매개 변수 | 값 |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | 마이그레이션 범위에 있는 ID/사서함에 대해 원본 테넌트에서 만든 메일 사용이 가능한 보안 그룹입니다. |
    | -ResourceTenantDomain | 원본 테넌트 도메인 이름(예: contoso \. onmicrosoft.com. |
    | -ApplicationId | 마이그레이션에 사용되는 응용 프로그램의 Azure 응용 프로그램 ID(GUID)입니다. Azure Portal(Azure AD, 엔터프라이즈 응용 프로그램, 앱 이름, 응용 프로그램 ID)을 통해 제공되거나 초대 전자 메일에 포함된 응용 프로그램 ID입니다.  |
    | -TargetTenantDomain | 대상 테넌트 도메인 이름(예: fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | 대상 테넌트의 테넌트 ID입니다. 예를 들어 contoso 테넌트의 Azure AD 테넌트 ID는 onmicrosoft.com \. 있습니다. |
    |||

    예를 들면 다음과 같습니다.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

이제 원본 관리자 설정이 완료되었습니다!

### <a name="verify-setup"></a>설치 확인

원본 테넌트와 대상 테넌트 둘 다의 조직 관계와 대상의 마이그레이션 끝점이 성공적으로 만들어졌습니다.

#### <a name="target-tenant"></a>대상 테넌트

**조직 관계**

이 명령을 사용하여 조직 관계 개체가 만들어지며 구성되어 있는지 확인

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
예를 들면 다음과 같습니다.

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**마이그레이션 끝점**

이 명령을 사용하여 마이그레이션 끝점 개체가 만들어지고 구성되어 있는지 확인

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

예를 들면 다음과 같습니다.

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>원본 테넌트

**조직 관계**

이 명령을 사용하여 조직 관계 개체가 만들어지며 구성되어 있는지 확인

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

예를 들면 다음과 같습니다.

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>설치 스크립트 확인

원본 또는 대상 테넌트 구성 중에 오류가 발생하는 경우 [GitHub에](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 있는 VerifySetup.ps1 스크립트를 실행하고 출력을 검토할 수 있습니다.

다음은 대상 테넌트에서 VerifySetup.ps1 예제입니다.

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

다음은 원본 테넌트의 VerifySetup.ps1 예입니다.

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>사서함을 원래 원본으로 다시 이동

사서함을 원래 원본 테넌트로 다시 이동해야 하는 경우 새 원본 테넌트와 새 대상 테넌트에서 동일한 단계 및 스크립트 집합을 실행해야 합니다. 기존 Organization Relationship 개체는 다시 생성되지 않는 업데이트 또는 추가됩니다.

## <a name="prepare-target-user-objects-for-migration"></a>마이그레이션을 위한 대상 사용자 개체 준비

테넌트 간 이동을 사용하려면 대상 테넌트 및 Exchange Online 시스템(MailUsers로)에 특정 특성이 표시되어 있어야 합니다. 대상 테넌트에서 제대로 설정되지 않은 사용자에 대해 시스템이 이동되지 않습니다. 다음 섹션에서는 대상 테넌트에 대한 MailUser 개체 요구 사항에 대해 자세히 설명합니다.

### <a name="prerequisites"></a>필수 구성 요소
  
대상 조직에서 다음과 같은 개체와 특성을 설정해야 합니다.  

1. 원본 조직에서 이동하는 사서함의 경우 대상 조직에서 MailUser 개체를 프로비전해야 합니다. 

   - Target MailUser에는 원본 사서함에서 이러한 특성이 있어야 합니다. 또는 새 User 개체와 함께 할당되어야 합니다.
      - ExchangeGUID(원본에서 대상으로 직접 흐름) - 사서함 GUID가 일치해야 합니다. 이 개체가 대상 개체에 없는 경우 이동 프로세스가 진행되지 않습니다. 
      - ArchiveGUID(원본에서 대상으로 직접 흐름) - 보관 GUID가 일치해야 합니다. 이 개체가 대상 개체에 없는 경우 이동 프로세스가 진행되지 않습니다. 이 설정은 원본 사서함이 보관을 사용하도록 설정된 경우만 필요합니다. 
      - LegacyExchangeDN(proxyAddress, "x500: <LegacyExchangeDN> ") – LegacyExchangeDN은 대상 MailUser에 x500: proxyAddress로 있어야 합니다. 이 개체가 대상 개체에 없는 경우 이동 프로세스가 진행되지 않습니다. 
      - UserPrincipalName – UPN이 사용자의 새 ID 또는 대상 회사(예: user@northwindtraders.onmicrosoft.com)에 맞춰집니다. 
      - 기본 SMTPAddress – 기본 SMTP 주소가 사용자의 새 회사(예: user@northwind.com)에 맞춰집니다. 
      - TargetAddress/ExternalEmailAddress – MailUser는 원본 테넌트에 호스트된 사용자의 현재 사서함을 참조합니다(예: user@contoso.onmicrosoft.com). 이 값을 할당할 때 PrimarySMTPAddress도 할당하고 있는지 또는 이 값이 이동 실패의 원인이 될 PrimarySMTPAddress를 설정하는지 확인해야 합니다. 
      - 원본 사서함의 레거시 smtp 프록시 주소를 대상 MailUser에 추가할 수 없습니다. 예를 들어 테넌트 개체의 MEU에 contoso.com 유지 fabrikam.onmicrosoft.com 없습니다. 도메인은 하나의 Azure AD 또는 Exchange Online 테넌트에만 연결됩니다.
 
     대상  MailUser 개체의 예:
 
     | 특성             | 값                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | 별칭                 | 라라N                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     원본 **사서함 개체의** 예:

     | 특성             | 값                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | 별칭                 | 라라N                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Exchange 하이브리드 쓰기 쓰기에 추가 특성이 이미 포함되어 있을 수 있습니다. 그렇지 않은 경우 포함해야 합니다. 
   - msExchBlockedSendersHash – 클라이언트에서 온라인에서 안전한 수신 및 차단된 보낸 사람 데이터를 다시 프레미스 Active Directory에 기록합니다.
   - msExchSafeRecipientsHash – 온라인에서 클라이언트에서온-프레미스 Active Directory로 안전한 수신 및 차단된 보낸 사람 데이터를 기록합니다.
   - msExchSafeSendersHash – 클라이언트에서온-프레미스 Active Directory로 온라인에서 안전하고 차단된 보낸 사람 데이터를 다시 기록합니다.

2. 원본 사서함이 LitigationHold에 있으며 원본 사서함 복구 가능한 항목 크기가 데이터베이스 기본값(30GB)보다 크면 대상 할당량이 원본 사서함 크기보다 작기 때문에 이동이 진행되지 않습니다. 대상 MailUser 개체를 업데이트하여 원본 환경에서 대상으로 ELC 사서함 플래그를 전환할 수 있습니다. 그러면 대상 시스템에서 MailUser의 할당량 확장을 100GB로 트리거하여 대상으로 이동할 수 있습니다. 이러한 지침은 ELC 플래그 스탬프를 지정하는 명령이 테넌트 관리자에게 노출되지 않는 Azure AD Connect를 실행하는 하이브리드 ID에만 작동됩니다.

    >[!Note]
    > 샘플 – 있는 경우 무상 수리<br/>이 스크립트는 원본 사서함(원본 값을 얻기 위해) 및 대상에 대한 연결(ADUser 개체 스탬프 지정)을 가정합니다. 원본에 소송 또는 단일 항목 복구를 사용하도록 설정한 경우 대상 계정에서 이를 설정합니다.  이렇게 하면 대상 계정의 반지 크기가 100GB로 증가합니다.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. 비하이블 대상 테넌트는 다음 명령을 실행하여 MailUser 개체에 대한 소송 보류를 사용하도록 설정하고 할당량 을 100GB로 늘려 마이그레이션 전에 MailUsers의 복구 가능한 항목 폴더에 대한 할당량 을 수정할 수 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 있습니다. 이 방식은 하이브리드의 테넌트에는 작동하지 않습니다.

4. 대상 조직의 사용자는 조직에 적용할 수 있는 적절한 Exchange Online 구독을 사용이 허가되어야 합니다. 사서함 이동에 앞서 라이선스를 적용할 수 있지만 대상 MailUser가 ExchangeGUID 및 프록시 주소로 올바르게 설정된 후만 적용할 수 있습니다. ExchangeGUID가 적용되기 전에 라이선스를 적용하면 대상 조직에 새 사서함이 프로비전됩니다. 

    > [!Note]
    > Mailbox 또는 MailUser 개체에 라이선스를 적용하면 확인된 도메인만 Exchange EmailAddresses 배열에 포함되도록 모든 SMTP 형식 proxyAddresses가 스크러빙됩니다. 

5. 대상 MailUser에 Source ExchangeGuid와 일치하지 않는 이전 ExchangeGuid가 없는지 확인해야 합니다. 대상 MEU가 이전에 Exchange Online에 대해 라이선스를 부여하고 사서함을 프로비전한 경우 이 문제가 발생할 수 있습니다. 대상 MailUser가 이전에 사용이 허가되거나 Source ExchangeGuid와 일치하지 않는 ExchangeGuid가 있는 경우 클라우드 MEU를 정리해야 합니다. 이러한 클라우드 MEUS의 경우 를 실행할 수 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 있습니다.  

    > [!Caution]
    > 이 프로세스는 다시 할 수 없습니다. 개체에 softDeleted 사서함이 있는 경우 이 시점 이후에는 복원할 수 없습니다. 그러나 선택을 취소한 후 올바른 ExchangeGuid를 대상 개체에 동기화할 수 있으며 MRS는 원본 사서함을 새로 만든 대상 사서함에 연결합니다. (새 매개 변수에 대한 EHLO 참조 블로그)  

    이 명령을 사용하여 이전에 사서함이던 개체를 찾을 수 있습니다.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    예를 들면 다음과 같습니다. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    이 명령을 사용하여 소프트 삭제된 사서함의 선택을 취소합니다.

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    예를 들면 다음과 같습니다.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>사서함 마이그레이션 수행

테넌트 간 Exchange 사서함 마이그레이션은 대상 테넌트에서 시작된 마이그레이션 일괄 처리로 전송됩니다. 이는 Exchange온-프레미스에서 Microsoft 365로 마이그레이션할 때의 보류 마이그레이션 일괄 처리 작동 방식과 비슷합니다. 

### <a name="create-migration-batches"></a>마이그레이션 일괄 처리 만들기

다음은 이동 시작을 위한 마이그레이션 일괄 처리 cmdlet의 예입니다.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> CSV 파일의 전자 메일 주소는 원본 테넌트가 아니라 대상 테넌트에 지정된 주소입니다.

테넌트 간 옵션을 선택할 때 마이그레이션 일괄 처리 제출도 새 Exchange 관리 센터에서 지원됩니다.

#### <a name="update-on-premises-mailusers"></a>On-premises MailUsers 업데이트

사서함이 원본에서 대상으로 이동한 후 원본 및 대상 모두에 대한 새 targetAddress로 업데이트되는 On-premises 메일 사용자를 확인해야 합니다. 예제에서 이동에 사용되는 targetDeliveryDomain은 에 **contoso.onmicrosoft.com.** 이 targetAddress로 메일 사용자를 업데이트합니다.

## <a name="frequently-asked-questions"></a>자주하는 질문

**이동 후 원본에서 원격Mailboxes를 업데이트해야 하나요?**

예, 원본 테넌트 사서함이 대상 테넌트로 이동할 때 원본의 targetAddress(RemoteRoutingAddress/ExternalEmailAddress)를 업데이트해야 합니다.  메일 라우팅은 다른 targetAddresses를 사용하는 여러 메일 사용자에 대한 추천을 따를 수 있는 반면, 메일 사용자에 대한 사용 중/사용 중은 사서함 사용자의 위치를 대상으로 지정해야 합니다. 무료/사용 중 검색은 여러 리디렉션을 추격하지 않습니다. 

**Teams 채팅 폴더 콘텐츠가 테넌트 간 마이그레이션하나요?**  

아니요. Teams 채팅 폴더 콘텐츠는 테넌트 간 마이그레이션을 하지 않습니다.  

**온보드 및 오프보드 이동이 아니라 테넌트 간 이동인 이동만 볼 수 있는 방법**

매개 `-flags` 변수를 사용합니다. 예를 들면 다음과 같습니다.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**테스트에 사용되는 특성을 복사하는 예제 스크립트를 제공할 수 있나요?**

> [!Note]
> 샘플 – 있는 경우 무상 수리<br/>이 스크립트는 원본 사서함(원본 값을 얻기 위해) 및 대상에 대한 연결(ADUser 개체 스탬프 지정)을 가정합니다. 원본에 소송 또는 단일 항목 복구를 사용하도록 설정한 경우 대상 계정에서 이를 설정합니다.  이렇게 하면 대상 계정의 반지 크기가 100GB로 증가합니다.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**사용 사서함이 이동된 후 1일차에 Outlook에 액세스하는 방법**

한 테넌트만 도메인을 소유할 수 있는 것이기 때문에 사서함 이동이 완료되면 이전 기본 SMTPAddress가 대상 테넌트의 사용자에게 연결되지 않습니다. 새 테넌트와 연결된 도메인만 해당합니다. Outlook에서는 새 UPN을 사용하여 서비스에 인증하며 Outlook 프로필은 대상 시스템의 사서함과 일치할 레거시 기본 SMTPAddress를 찾을 것으로 예상합니다. 레거시 주소가 대상 시스템에 있지 않은 경우 Outlook 프로필은 새로 이동된 사서함을 찾기 위해 연결되지 않습니다. 

이 초기 배포의 경우 사용자는 새 UPN, 기본 SMTP 주소로 프로필을 다시 작성하고 OST 콘텐츠를 다시 동기화해야 합니다. 

> [!Note]
> 완료를 위해 사용자를 배치할 때 그에 따라 계획합니다. Outlook 클라이언트 프로필이 만들어지며 이후 OST 및 OAB 파일이 클라이언트로 다운로드될 때 네트워크 사용률 및 용량을 고려해야 합니다. 
 
**테넌트 간 이동을 설정하거나 완료하려면 구성원으로 해야 하는 Exchange RBAC 역할은 무엇입니까?**
 
사서함 이동을 실행할 때 위임된 업무를 가정한 역할 매트릭스가 있습니다. 현재 다음 두 가지 역할이 필요합니다.  

- 첫 번째 역할은 테넌트/조직 경계로 또는 외부로 콘텐츠를 이동하는 권한 부여를 설정하는 일회성 설치 작업에 대한 것입니다. 조직 제어에서 데이터를 이동하는 것은 모든 회사에서 중요한 문제로, 조직 관리자(OrgAdmin)의 가장 높은 할당 역할로 선택했습니다. 이 역할은 원격 조직과의 -MailboxMoveCapability를 정의하는 새 OrganizationRelationship을 변경하거나 설정해야 합니다. OrgAdmin만 MailboxMoveCapability 설정을 변경할 수 있는 반면, OrganizationRelationhip의 다른 특성은 페더링 공유 관리자가 관리할 수 있습니다. 
 
- 실제 이동 명령을 실행하는 역할을 하위 수준 함수로 위임할 수 있습니다. 사서함 이동 역할에는 매개 변수를 사용하여 조직 안이나 밖으로 사서함을 이동하는 기능이 `-RemoteTenant` 할당됩니다.  

**변환된 사서함에서 targetAddress(TargetDeliveryDomain)에 대해 선택한 SMTP 주소를 지정하는 방법(MailUser 변환)?**
 
MRS를 사용하여 Exchange 사서함을 이동하면 대상 개체의 전자 메일 주소(proxyAddress)와 일치하여 MailUser로 변환할 때 원본 원본 사서함에 targetAddress가 생성됩니다. 이 프로세스는 이동 명령에 전달된 -TargetDeliveryDomain 값을 사용하여 대상 쪽에서 해당 도메인에 대한 일치하는 프록시를 검사합니다. 일치하는 항목은 일치하는 proxyAddress를 사용하여 변환된 사서함(현재 MailUser) 개체에 ExternalEmailAddress(targetAddress)를 설정하는 데 사용됩니다.
 
**사서함 사용 권한을 전환하는 방법**

사서함 사용 권한에는 다음을 대신하여 보내기 및 사서함 액세스가 포함됩니다. 

- 대신 보내기(AD:publicDelegates)는 사용자 사서함에 대한 액세스 권한이 있는 받는 사람의 DN을 대리인으로 저장합니다. 이 값은 Active Directory에 저장되고 현재 사서함 전환의 일부로 이동하지 않습니다. 원본 사서함에 publicDelegates가 설정된 경우 를 실행하여 MEU에서 사서함으로의 변환이 대상 환경에서 완료되면 대상 사서함의 publicDelegates를 다시스탬프해야 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 합니다. 
 
- 사서함에 저장된 사용 권한은 보안 주체와 대리인이 모두 대상 시스템으로 이동될 때 사서함과 함께 이동됩니다. 예를 들어 사용자 TestUser_7 테넌트 서버의 사서함 TestUser_8 FullAccess가 SourceCompany.onmicrosoft.com. 사서함 이동이 완료된 TargetCompany.onmicrosoft.com 동일한 사용 권한이 대상 디렉터리에 설정됩니다. 원본 테넌트와 대상 테넌트의 TestUser_7 *Get-MailboxPermission을* 사용하는 예는 다음과 같습니다. Exchange cmdlet에는 그에 따라 원본 및 대상이 미리 지정됩니다. 
 
이동하기 전에 사서함 사용 권한 출력의 예는 다음과 같습니다. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
이동 후 사서함 사용 권한 출력의 예는 다음과 같습니다. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> 테넌트 간 사서함 및 일정 권한은 지원되지 않습니다. 이러한 연결된 사서함이 원본 테넌트에서 동시에 전환될 수 있도록 보안 주체와 대리인을 통합 이동 일괄 처리로 구성해야 합니다. 

**마이그레이션을 사용하도록 설정하려면 대상 MailUser 프록시 주소에 어떤 X500 프록시를 추가해야 하나요?**  

테넌트 간 사서함 마이그레이션을 수행하려면 원본 사서함 개체의 LegacyExchangeDN 값을 대상 MailUser 개체의 x500 전자 메일 주소로 스탬프 처리해야 합니다.  

예제:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> 이 X500 프록시 외에도 원본 사서함의 모든 X500 프록시를 대상의 사서함에 복사해야 합니다.  

**이동이 작동하지 않는 경우 어디에서 문제 해결을 시작해야 하나요?**  

[먼저 GitHub에](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 있는 VerifySetup.ps1 스크립트를 실행하고 출력을 검토합니다.

다음은 대상 테넌트에서 VerifySetup.ps1 예제입니다.

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

다음은 원본 테넌트에서 VerifySetup.ps1 eExample입니다.

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**원본 테넌트와 대상 테넌트가 동일한 도메인 이름을 사용할 수 있나요?**  

아니요. 원본 및 대상 테넌트 도메인 이름은 고유해야 합니다. 예를 들어 contoso.com 도메인의 원본 도메인과 대상 도메인은 fourthcoffee.com.

**공유 사서함이 이동하고 계속 작동하나요?**

예. 그러나 다음 문서에 설명된 바와 같이 스토어 사용 권한만 보관합니다.

- [Microsoft Docs | Exchange Online에서 받는 사람에 대한 사용 권한 관리](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft 지원 | Office 365 전용 Exchange 및 Outlook 사서함 권한을 부여하는 방법](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Azure Key Vault가 필요하며 언제 거래가 이행되는가?**  

예. 마이그레이션을 승인하기 위해 키 자격 증명 모음을 사용하여 인증서를 저장하려면 Azure 구독이 필요합니다. 사용자 이름 및 & 사용하여 원본에 인증하는 온보더링 마이그레이션과 달리 테넌트 간 사서함 마이그레이션에서는 OAuth 및 이 인증서를 비밀/자격 증명으로 사용하게 됩니다. 키 자격 증명 모음에 대한 액세스는 모든 사서함 마이그레이션 전체에서 유지 관리되어야 합니다. 이 액세스는 마이그레이션이 시작될 때와 한 번씩, 그리고 증분 동기화 시간 동안 24시간마다 한 번씩 유지 관리되어야 합니다. 여기에서 AKV 비용 세부 정보를 검토할 [수 있습니다.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)  

**일괄 처리에 대한 권장 사항이 있나요?**  

일괄 처리당 사서함 수가 2,000개를 초과하지 않습니다. 동기화하는 동안 최종 사용자에게 영향이 없는 일괄 처리는 2주 전에 제출하는 것이 좋습니다. 50,000개가 넘는 사서함 수량에 대한 지침이 필요한 경우 2016년 8월에 엔지니어링 피드백 메일 crosstenantmigrationpreview@service.microsoft.com.

**고객 키와 함께 서비스 암호화를 사용하는 경우 어떻게 하나요?**

이동하기 전에 사서함의 암호가 해독됩니다. 고객 키가 필요한 경우 대상 테넌트에 구성되어 있는지 확인 자세한 [내용은 여기를](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) 참조하세요.  

**예상 마이그레이션 시간은 무엇입니까?**

마이그레이션을 계획하는 데 도움이 [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) 될 수 있도록 여기에 있는 표에는 대량 사서함 마이그레이션 또는 개별 마이그레이션이 완료될 것으로 예상되는 경우에 대한 지침이 표시됩니다. 이러한 예상 비용은 이전 고객 마이그레이션에 대한 데이터 분석을 기반으로 합니다. 모든 환경은 고유하기 때문에 정확한 마이그레이션 속도는 다를 수 있습니다.  

이 기능은 현재 미리 보기에 있으며 SLA 및 해당 서비스 수준은 이 기능의 미리 보기 상태 중 성능 또는 가용성 문제에 적용되지 않습니다.

## <a name="known-issues"></a>알려진 문제  

-  **문제: 자동 확장된 보관 파일을 마이그레이션할 수 없습니다.** 테넌트 간 마이그레이션 기능은 특정 사용자에 대한 기본 사서함 및 보관 사서함의 마이그레이션을 지원합니다. 그러나 원본의 사용자에게 자동 확장 보관함이 있는 경우(즉, 두 개 이상의 보관 사서함을 의미) 이 기능은 추가 보관 파일을 마이그레이션할 수 없습니다.

- **문제: 소유하지 않은 smtp proxyAddress를 사용하는 클라우드 메일사용자가 MRS 이동을 차단합니다.** 대상 테넌트 MailUser 개체를 만들 때 모든 SMTP 프록시 주소가 대상 테넌트 조직에 속하는지 확인해야 합니다. SMTP proxyAddress가 로컬 테넌트에 속하지 않은 대상 메일 사용자에 있는 경우 MailUser를 Mailbox로 변환할 수 없습니다. 이는 사서함 개체가 테넌트가 권한이 있는 도메인(테넌트가 클레임한 도메인)에서만 메일을 보낼 수 있습니다. 

   - Azure AD Connect를 사용하여 사내에서 사용자를 동기화하는 경우 사서함이 있는 원본 테넌트(laran@contoso.onmicrosoft.com)를 대상으로 하는 ExternalEmailAddress를 사용하여 사내 메일User 개체를 프로비전하고 PrimarySMTPAddress를 대상 테넌트(Lara.Newton@northwind.com)에 있는 도메인으로 스탬프 지정합니다. 이러한 값은 테넌트와 동기화되어 적절한 메일 사용자가 프로비전되어 마이그레이션할 준비가 됩니다. 예제 개체는 다음과 같습니다.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > 전자 *contoso.onmicrosoft.com* 주소가  EmailAddresses/proxyAddresses 배열에 없습니다.

- **문제: "외부" 기본 SMTP 주소가 있는 MailUser 개체가 수정/"내부" 회사 클레임 도메인으로 다시 설정**

   MailUser 개체는 로컬이 아닌 사서함에 대한 포인터입니다. 테넌트 간 사서함 마이그레이션의 경우 MailUser 개체를 사용하여 원본 사서함(대상 조직의 관점에서) 또는 대상 사서함(원본 조직의 관점에서)을 표현합니다. MailUsers에는 디렉터리에 있는 사서함 사용자의 표시된 SMTP 주소를 나타내는 실제 사서함(ProxyTest@fabrikam.onmicrosoft.com) 및 primarySMTP 주소의 smtp 주소를 나타내는 ExternalEmailAddress(targetAddress)가 있습니다. 일부 조직에서는 기본 SMTP 주소를 로컬 테넌트가 소유/확인한 주소가 아닌 외부 SMTP 주소로 표시하기로 fabrikam.com(예: contoso.com.  그러나 라이선스 작업을 통해 Exchange 서비스 계획 개체를 MailUser에 적용하면 기본 SMTP 주소가 수정되어 로컬 조직(contoso.com)에서 확인된 도메인으로 표시됩니다. 두 가지 이유로 인해 발생할 수 있습니다.
   
   - Exchange 서비스 계획이 MailUser에 적용되면 Azure AD 프로세스에서 프록시 스크러빙을 적용하여 로컬 조직이 다른 테넌트에서 메일을 보낼 수 없는지 확인하기 시작합니다. 로컬 조직에서 주소를 확인하지 않은 경우 이러한 서비스 계획이 있는 받는 사람 개체의 SMTP 주소가 제거됩니다. 예에서와 같습니다. Fabikam.com 도메인은 contoso.onmicrosoft.com 확인되지 않았기 때문에 스크러빙을 통해 fabrikam.com 제거됩니다. MailUser에서 이러한 외부 도메인을 유지하려면 마이그레이션 전이나 마이그레이션 후에 마이그레이션 프로세스를 변경하여 이동이 완료된 후 또는 이동 전에 라이선스를 제거하여 사용자가 예상되는 외부 브랜더를 적용하도록 해야 합니다. 메일 서비스에 영향을 주지 않도록 사서함 개체에 적절한 사용이 허가되었는지 확인해야 합니다.<br/><br/>테넌트의 MailUser에서 서비스 계획을 제거하는 Contoso.onmicrosoft.com 스크립트가 여기에 나와 있습니다.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       할당된 ServicePlans 집합의 결과는 다음과 같습니다.

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       사용자의 PrimarySMTPAddress는 더 이상 스크러빙하지 않습니다. fabrikam.com 도메인은 contoso.onmicrosoft.com 소유하지 않고 디렉터리에 표시된 기본 SMTP 주소로 유지됩니다.

       예를 들면 다음과 같습니다.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - msExchRemoteRecipientType이 8(DeprovisionMailbox)로 설정되어 있는 경우 대상 테넌트로 마이그레이션된 사내 메일 사용자에 대해 Azure의 프록시 스크러빙 논리는 비공식 도메인을 제거하고 primarySMTP를 소유 도메인으로 다시 설정합니다. 프록시 스크럽 논리는 더 이상 적용되지 않습니다. <br/><br>다음은 Exchange Online을 포함 하는 가능한 서비스 계획의 전체 집합입니다.

   | 이름                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery Storage(500GB)               |
   | 고객 Lockbox                                  |
   | 데이터 손실 방지                              |
   | EOP, DLP(Exchange Enterprise CAL Services)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online(P1)                              |
   | Exchange Online(계획 1)                          |
   | Exchange Online(계획 2)                          |
   | Exchange Online용 Exchange Online Archiving     |
   | Exchange Server용 Exchange Online Archiving     |
   | Exchange Online 비활성 사용자 추가 기능              |
   | Exchange Online Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online 요금제 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | 정보 장벽                              |
   | Office 365에 대한 정보 보호 - Premium   |
   | Office 365에 대한 정보 보호 - 표준  |
   | MyAnalytics의 인사이트                           |
   | Microsoft 365 고급 감사                   |
   | Microsoft Bookings                                |
   | Microsoft 비즈니스 센터                         |
   | Microsoft MyAnalytics(전체)                      |
   | Office 365 고급 eDiscovery                    |
   | Microsoft Defender for Office 365(계획 1)    |
   | Microsoft Defender for Office 365(계획 2)    |
   | Office 365 권한 있는 액세스 관리           |
   | Office 365의 고급 암호화                  |
    
