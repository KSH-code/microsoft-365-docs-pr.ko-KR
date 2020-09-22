---
title: 테 넌 트 사서함 마이그레이션
description: Microsoft 365 또는 Office 365 테 넌 트 간에 사서함을 이동 하는 방법입니다.
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
ms.openlocfilehash: f649a72dc5569e8aec46347df295aa3ff9d93613
ms.sourcegitcommit: 327163f70eac0de568ebe3c9a97a744c3ed408cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177174"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>테 넌 트 사서함 마이그레이션 (미리 보기)

이전에는 Exchange Online 테 넌 트에서 사서함을 같은 Exchange Online 서비스의 다른 테 넌 트로 이동 해야 하는 경우 온-프레미스에 보드를 완전히 해제 한 다음 새 테 넌 트로 다시 마이그레이션해야 합니다. 새 테 넌 트 사서함 마이그레이션 기능을 사용 하는 경우 원본 및 대상 테 넌 트에 포함 된 거주자 관리자는 온-프레미스 시스템에서 인프라 종속성이 최소화 된 테 넌 트 간에 사서함을 이동할 수 있습니다. 이렇게 하면 보드 및 온보드 사서함을 오프 로드 됩니다.

일반적으로 합병 또는 divestitures 중에 사용자와 콘텐츠를 새 테 넌 트로 이동 하는 기능이 필요 합니다. 대상 테 넌 트 관리자가 이동을 실행 하면 온-프레미스에서 클라우드 온 보 딩 마이그레이션과 비슷한 끌어오기 이동 이라고 합니다.

테 넌 트 Exchange 사서함 이동은 테 넌 트 관리자가 완전히 셀프 서비스를 제공 하며, 사용자를 새 조직으로 전환 하는 데 필요한 더 큰 워크플로에 스크립팅할 수 있는 잘 알려진 인터페이스를 사용 합니다. 관리자 `New-MigrationBatch` 는 사서함 이동 관리 역할을 통해 사용 가능한 cmdlet을 사용 하 여 테 넌 트 이동을 실행할 수 있습니다. 이동 프로세스에는 사서함 동기화 및 종료 중에 테 넌 트 권한 부여 검사가 포함 됩니다. 
 
마이그레이션 사용자가 테 넌 트 이동을 사용 하도록 설정 하려면 대상 테 넌 트 Exchange Online 시스템에서 MailUsers로 표시 되어 있어야 합니다. 대상 테 넌 트에서 제대로 설정 되지 않은 사용자에 대 한 시스템 이동이 실패 합니다. 

이동이 완료 되 면 원본 시스템 사서함은 MailUser로 변환 되 고 Exchange에서 ExternalEmailAddress로 표시 된 targetAddress는 대상 테 넌 트에 대 한 라우팅 주소로 스탬프 처리 됩니다. 이 프로세스를 진행 하면 레거시 MailUser가 원본 테 넌 트에 남게 되 고 일정 기간 동안 및 메일 라우팅을 허용 합니다. 비즈니스 프로세스에서 허용 하는 경우 원본 테 넌 트에서 원본 메일 사용자를 제거 하거나이를 메일로 변환할 수 있습니다. 

테 넌 트에 대 한 Exchange 사서함 마이그레이션은 하이브리드 또는 클라우드에서만 또는이 둘의 조합에 대해 지원 됩니다.

이 문서에서는 상호 테 넌 트 사서함 이동에 대 한 프로세스를 설명 하 고 콘텐츠 이동을 위해 원본 및 대상 테 넌 트를 준비 하는 방법에 대 한 지침을 제공 합니다. 

## <a name="preparing-source-and-target-tenants"></a>원본 및 대상 테 넌 트 준비

테 넌 트 Exchange 사서함 마이그레이션 기능을 사용 하려면 테 넌 트 마이그레이션에 대 한 권한 부여 및 범위 지정이 필요 합니다. 이제 테 넌 트 관리자는 Azure Enterprise 응용 프로그램 및 키 자격 증명 모음 저장소 솔루션을 사용 하 여 테 넌 트 간에 Exchange Online 사서함 마이그레이션에 대 한 권한 부여 및 범위 지정을 관리할 수 있습니다. 테 넌 트 사서함 이동은 초대 및 승인 모델을 지원 하 여 테 넌 트 쌍 간의 인증에 사용 되는 azure AD (azure Active Directory) 응용 프로그램을 설정 합니다. 조직 관계 및 마이그레이션 끝점과 같은 추가 구성 요소도 필요 합니다.

이 섹션에는 대상 디렉터리에서 MailUser 사용자 개체를 준비 하는 데 필요한 특정 단계는 포함 되지 않으며, 마이그레이션 일괄 처리를 전송 하는 예제 명령도 포함 되지 않습니다. 이 정보는 [마이그레이션을 위한 대상 사용자 개체 준비를](#prepare-target-user-objects-for-migration) 참조 하세요.

## <a name="prerequisites"></a>필수 구성 요소

테 넌 트 사서함 이동 기능을 사용 하려면 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) 가 테 넌 트 쌍 별 azure 응용 프로그램을 설정 하 여 해당 테 넌 트에서 사서함 마이그레이션을 인증 하 고 권한을 부여 하는 데 사용할 인증서/비밀을 안전 하 게 저장 하 고 액세스 해야 합니다. 

시작 하기 전에 배포 스크립트를 실행 하 여 Azure 키 자격 증명, 이동 사서함 응용 프로그램, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성 하기 위해 필요한 권한이 있는지를 알려야 합니다. 일반적으로 전역 관리자에 게는 모든 구성 단계를 수행할 수 있는 권한이 있습니다.

또한 설치 프로그램을 실행 하기 전에 원본 테 넌 트에서 메일 사용이 가능한 보안 그룹이 필요 합니다. 이러한 그룹은 원본 (또는 리소스 라고도 함) 테 넌 트에서 대상 테 넌 트로 이동할 수 있는 사서함 목록의 범위를 지정 하는 데 사용 됩니다. 따라서 원본 테 넌 트 관리자는 이동 해야 하는 특정 사서함 집합을 제한 하거나 범위를 지정할 수 있으므로 의도 하지 않은 사용자를 마이그레이션하지 못하게 됩니다. 중첩 그룹은 지원 되지 않습니다.

또한 사서함을 이동할 수 있는 신뢰할 수 있는 파트너 회사와 통신 하 여 해당 Microsoft 365 테 넌 트 ID를 얻도록 해야 합니다. 이 테 넌 트 ID는 조직 관계 필드에서 사용 됩니다 `DomainName` .

구독의 테 넌 트 ID를 가져오려면 Microsoft 365 관리 센터에 로그인 하 고로 이동 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 합니다. 테 넌 트 ID 속성에 대 한 복사 아이콘을 클릭 하 여 클립보드에 복사 합니다.

프로세스의 작동 방식은 다음과 같습니다.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg" alt-text="사서함 마이그레이션에 대 한 테 넌 트 준비":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg).
--> 

### <a name="prepare-tenants"></a>테 넌 트 준비

높은 수준에서는 설치 스크립트를 실행할 때 다음과 같은 구성 작업이 수행 됩니다.

대상 테 넌 트 준비:

1. 기존 Azure 리소스 그룹을 제공 하지 않으면 새 항목을 만듭니다 (SCRIPT).
2. 기존 키 보관소를 제공 하지 않으면 새로 생성 됩니다 (스크립트).
3. Office 365 Exchange Online 사서함 마이그레이션 응용 프로그램 (스크립트)에 대 한 새 액세스 정책이 만들어집니다.
4. 새 인증서를 만들거나 (지정 된 경우) 마이그레이션 응용 프로그램 (스크립트)에 대 한 비밀을 보존 합니다.
5. 새 Azure AD 응용 프로그램을 만듭니다 (스크립트).
6. 인증서/암호가 마이그레이션 응용 프로그램 (스크립트)에 업로드 됩니다.
7. 사서함 마이그레이션 사용 권한은 응용 프로그램 (스크립트)에 할당 됩니다.
8. 배포 스크립트는 대상 관리자가 자체 응용 프로그램 (스크립트)을 consents 때까지 일시 중지 됩니다.
9. 대상 테 넌 트 관리자가 응용 프로그램에 부여 된 사용 권한 (수동)을 consents 합니다.
10. 대상 테 넌 트 (스크립트)에 대 한 조직 관계를 만듭니다.
11. 대상 테 넌 트 (스크립트)로 사서함을 가져오기 위한 마이그레이션 끝점을 만듭니다.

원본 테 넌 트 준비:

1. 원본 테 넌 트 관리자는 대상 테 넌 트 (수동)에서 사서함 마이그레이션 응용 프로그램 초대에 대 한 동의를 수락 합니다.
2. 원본 테 넌 트 관리자는 마이그레이션 응용 프로그램 (수동)에 의해 이동 될 수 있는 사서함 목록을 포함 하기 위해 테 넌 트에 메일 사용이 가능한 보안 그룹을 만듭니다.
3. 조직 관계는 OAuth 확인에 사서함 마이그레이션 응용 프로그램을 사용 하 여 이동 요청 (스크립트)을 수락 하도록 지정 하는 대상 테 넌 트에 대해 만들어집니다.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>대상 테 넌 트 관리에 대 한 단계별 지침

1. [GitHub 리포지토리에서](https://github.com/microsoft/cross-tenant/releases/tag/Preview)대상 테 넌 트 설정에 대 한 SetupCrossTenantRelationshipForTargetTenant.ps1 스크립트를 다운로드 합니다. 
2. 스크립트를 실행할 컴퓨터에 스크립트 (SetupCrossTenantRelationshipForTargetTenant.ps1)를 저장 합니다.
3. Exchange Online 대상 테 넌 트에 대 한 원격 PowerShell 연결을 만듭니다. Azure 키 자격 증명 저장소 및 인증서, 이동 사서함 응용 프로그램, EXO 마이그레이션 끝점 및 EXO 조직 관계를 구성 하기 위해 배포 스크립트를 실행 하는 데 필요한 권한이 있는지 확인 합니다.
4. 파일 폴더 디렉터리를 스크립트 위치로 변경 하거나 스크립트가 현재 원격 PowerShell 세션의 현재 위치에 저장 되어 있는지 확인 합니다.
5. 다음 매개 변수와 값을 사용 하 여 스크립트를 실행 합니다.

    | 매개 변수 | 값 | 필수 또는 선택 사항
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | 원본 테 넌 트 도메인 (예: fabrikam \. onmicrosoft.com) | 필수 |
    | -Resourceten앤틸리스 전자 메일                   | 원본 테 넌 트 관리자의 전자 메일 주소입니다. 대상 관리자가 보낸 사서함 마이그레이션 응용 프로그램을 사용 하기 위해 consenting 되는 원본 테 넌 트 관리자입니다. 응용 프로그램에 대 한 전자 메일 초대를 받을 관리자입니다. | 필수 |
    | -TargetTenantDomain                         | 대상 테 넌 트 도메인 (예: contoso \. onmicrosoft.com) | 필수 |
    | -ResourceTenantId                           | 원본 테 넌 트 조직 ID (GUID)입니다. | 필수 |
    | -SubscriptionId                             | 리소스를 만드는 데 사용할 Azure 구독입니다. | 필수 |
    | -ResourceGroup                              | 키 자격 증명 모음을 포함 하거나 포함 하는 Azure 리소스 그룹 이름입니다. | 필수 |
    | -KeyVaultName                               | 사서함 마이그레이션 응용 프로그램 인증서/비밀을 저장할 Azure 키 자격 증명 모음 인스턴스입니다. | 필수 |
    | -CertificateName                            | 키 자격 증명 모음에서 인증서를 생성 하거나 검색할 때의 인증서 이름입니다. | 필수 |
    | -CertificateSubject 사용 합니다.                         | Azure 키 자격 증명 모음 인증서 주체 이름 (예: CN = contoso_fabrikam)입니다. | 필수 |
    | -ExistingApplicationId                      | 메일 마이그레이션 응용 프로그램이 이미 만들어진 경우 사용할 수 있습니다. | 선택 |
    | -AzureAppPermissions                        | 사서함 마이그레이션 응용 프로그램에 부여 해야 하는 사용 권한 (예: Exchange 또는 MSGraph) (이 응용 프로그램을 사용 하 여 리소스 테 넌 트에 대 한 승인 연결 초대를 전송 하는 데 필요한 MSGraph, 사서함 이동에 대 한 Exchange) | 필수 |
    | -UseAppAndCertGeneratedForSendingInvitation | 마이그레이션에 대해 만든 응용 프로그램을 사용 하 여 승인 링크 초대를 원본 테 넌 트 관리자에 게 보내는 데 사용 하는 매개 변수입니다. 이 매개 변수가 없으면 대상 관리자의 자격 증명을 입력 하 라는 메시지가 Azure 초대 관리자에 연결 하 고 대상 관리자로 초대를 보내야 합니다. | 선택 |
    | -KeyVaultAuditStorageAccountName            | 키 자격 증명 모음의 감사 로그가 저장 되는 저장소 계정입니다. | 선택 |
    | -KeyVaultAuditStorageResourceGroup          | 키 자격 증명 모음 감사 로그를 저장 하기 위한 저장소 계정이 포함 된 리소스 그룹입니다. | 선택 |
    ||||

6. 스크립트를 일시 중지 하 고이 프로세스 중에 만들어진 Exchange 사서함 마이그레이션 응용 프로그램에 대 한 수락 또는 동의를 요청 합니다. 예를 들면 다음과 같습니다.

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. 원격 PowerShell 세션에 URL이 표시 됩니다. 테 넌 트 동의를 위해 제공 된 링크를 복사한 다음 웹 브라우저에 붙여넣습니다.

8. 전역 관리자 자격 증명으로 로그인 합니다. 다음 화면이 표시 되 면 **수락**을 선택 합니다.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="사용 권한 수락 대화 상자":::
    
9. 원격 PowerShell 세션으로 다시 전환한 다음 Enter 키를 눌러 계속 합니다.

10. 이 스크립트는 나머지 설치 개체를 구성 합니다. 예를 들면 다음과 같습니다.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

이제 대상 관리자 설치가 완료 되었습니다.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>원본 테 넌 트 관리자를 위한 단계별 지침

1.  설정 하는 동안 대상 관리자가 지정한-Resourceten앤틸리스 전자 메일로 사서함에 로그인 합니다. 대상 테 넌 트에서 전자 메일 초대를 찾은 다음 **시작** 단추를 선택 합니다.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Invided 된 대화 상자":::

2. **수락** 을 선택 하 여 초대를 수락 합니다.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Permissons를 허용 하는 대화 상자":::

   > [!NOTE]
   > 이 전자 메일을 받지 않거나 찾을 수 없는 경우 대상 테 넌 트 관리자에 게는 초대를 수락 하도록 사용자에 게 제공할 수 있는 직접 URL이 제공 됩니다. URL은 대상 테 넌 트 관리자의 원격 PowerShell 세션에 대 한 성적의 기록에 있어야 합니다.

3. Microsoft 365 관리 센터 또는 원격 PowerShell 세션에서 하나 이상의 메일 사용이 가능한 보안 그룹을 만들어 대상 테 넌 트에서 대상 테 넌 트로 끌어오기 (이동) 할 사서함 목록을 제어할 수 있습니다. 이 그룹을 미리 채우지 않아도 되지만 설치 단계 (스크립트)를 실행 하려면 하나 이상의 그룹을 제공 해야 합니다. 그룹 중첩은 지원 되지 않습니다. 

4. [여기](https://github.com/microsoft/cross-tenant/releases/tag/Preview)에서 GitHub 리포지토리에서 원본 테 넌 트 설정에 대 한 SetupCrossTenantRelationshipForTargetResource.ps1 스크립트를 다운로드 합니다. 

5. Exchange 관리자 권한을 사용 하 여 원본 테 넌 트에 대 한 원격 PowerShell 연결을 만듭니다. 전역 관리자 권한은 원본 테 넌 트를 구성 하는 데 필요 하지 않으며, Azure 응용 프로그램 만들기 프로세스 때문에 대상 테 넌 트에만 적용 됩니다.

6. 스크립트 위치로 디렉터리를 변경 하거나 스크립트가 현재 원격 PowerShell 세션의 현재 위치에 저장 되어 있는지 확인 합니다.

7. 다음 필수 매개 변수 및 값을 사용 하 여 스크립트를 실행 합니다.

    | 매개 변수 | 값 |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | 마이그레이션 범위에 있는 id/사서함에 대해 원본 테 넌 트에서 만든 메일 사용이 가능한 보안 그룹입니다. |
    | -ResourceTenantDomain | 원본 테 넌 트 도메인 이름 (예: fabrikam \. onmicrosoft.com)입니다. |
    | -TargetTenantDomain | 대상 테 넌 트 도메인 이름 (예: contoso \. onmicrosoft.com)입니다. |
    | -ApplicationId | 마이그레이션에 사용 되는 응용 프로그램의 Azure 응용 프로그램 ID (GUID)입니다. Azure portal (Azure AD, Enterprise 응용 프로그램, 앱 이름, 응용 프로그램 ID)을 통해 사용할 수 있는 응용 프로그램 ID 또는 초대 전자 메일에 포함 됩니다.  |
    | -TargetTenantId | 대상 테 넌 트의 테 넌 트 ID입니다. 예를 들어 contoso \. onmicrosoft.com 테 넌 트의 AZURE AD 테 넌 트 ID입니다. |
    |||
    
    예를 들면 다음과 같습니다.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

이제 원본 관리자 설치가 완료 되었습니다.

### <a name="verify-setup"></a>설치 확인

원본 및 대상 테 넌 트 및 대상에 있는 마이그레이션 끝점 모두의 조직 관계가 성공적으로 만들어졌는지 확인 합니다.

#### <a name="target-tenant"></a>대상 테 넌 트

**조직 관계**

이 명령을 사용 하 여 조직 관계 개체를 만들고 구성 했는지 확인 합니다.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
예를 들면 다음과 같습니다.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**마이그레이션 끝점**

이 명령을 사용 하 여 마이그레이션 끝점 개체를 만들고 구성 했는지 확인 합니다.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

예를 들면 다음과 같습니다.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>원본 테 넌 트

**조직 관계**

이 명령을 사용 하 여 조직 관계 개체를 만들고 구성 했는지 확인 합니다.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
예를 들면 다음과 같습니다.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>원본으로 사서함 다시 이동

사서함이 원래 원본 테 넌 트로 다시 이동 해야 하는 경우 동일한 단계 및 스크립트 집합을 새 원본과 새 대상 테 넌 트 둘 다에서 실행 하면 됩니다. 기존 조직 관계 개체가 다시 만들어지지 않고 업데이트 되거나 추가 됩니다.

## <a name="prepare-target-user-objects-for-migration"></a>마이그레이션을 위한 대상 사용자 개체 준비

사용자를 마이그레이션하는 작업은 대상 테 넌 트 및 Exchange Online 시스템 (MailUsers)에 특정 특성을 표시 하 여 테 넌 트 이동이 가능 하도록 설정 되어 있어야 합니다. 대상 테 넌 트에서 제대로 설정 되지 않은 사용자에 대 한 시스템 이동이 실패 합니다. 다음 섹션에서는 대상 테 넌 트에 대 한 MailUser 개체 요구 사항을 자세히 설명 합니다.

### <a name="prerequisites"></a>필수 구성 요소
  
다음 개체 및 특성이 대상 조직에 설정 되어 있는지 확인 해야 합니다.  

1. 원본 조직에서 이동 하는 사서함의 경우 대상 조직에서 MailUser 개체를 프로 비전 해야 합니다. 
   - 대상 MailUser는 원본 사서함에서 다음 특성을 갖고 있거나 새 사용자 개체를 사용 하 여 할당 해야 합니다.
      - ExchangeGUID (원본에서 대상으로 직접 흐름)-사서함 GUID가 일치 해야 합니다. 대상 개체에 없는 경우에는 이동 프로세스가 진행 되지 않습니다. 
      - ArchiveGUID (원본에서 대상으로 직접 흐름)-보관 GUID가 일치 해야 합니다. 대상 개체에 없는 경우에는 이동 프로세스가 진행 되지 않습니다. (원본 사서함이 사용 하도록 설정 된 경우에만 필요). 
      - LegacyExchangeDN (proxyAddress, "x500: <LegacyExchangeDN> ")-legacyexchangedn은 대상 MailUser에 x500: proxyAddress로 제공 되어야 합니다. 대상 개체에 없는 경우에는 이동 프로세스가 진행 되지 않습니다. 
      - UserPrincipalName – UPN은 사용자의 새 id 또는 대상 회사 (예: user@northwindtraders.onmicrosoft.com)에 맞춰집니다. 
      - Primary SMTPAddress-기본 SMTP 주소가 사용자의 새 회사 (예: user@northwind.com)에 맞춰집니다. 
      - TargetAddress/ExternalEmailAddress – MailUser는 원본 테 넌 트에 호스트 된 사용자의 현재 사서함을 참조 합니다 (예: user@contoso.onmicrosoft.com). 이 값을 할당할 때 PrimarySMTPAddress도 할당 하거나이 값에 의해 이동 오류가 발생할 PrimarySMTPAddress이 설정 되었는지 확인 합니다. 
      - 원본 사서함의 레거시 smtp 프록시 주소를 대상 MailUser에 추가할 수 없습니다. 예를 들어 fabrikam.onmicrosoft.com 테 넌 트 개체에서 MEU의 contoso.com를 유지 관리할 수는 없습니다. 도메인은 하나의 Azure AD 또는 Exchange Online 테 넌 트에만 연결 됩니다.
 
    예제 **대상** mailuser 개체:
 
    | 특성             | 값                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | 별칭                 | LaraN                                                                                                                    |
    | RecipientType         | Enable-mailuser                                                                                                                 |
    | RecipientTypeDetails  | Enable-mailuser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = 첫 번째 조직/ou = Exchange 관리 그룹                                                                   |
    |                       | (FYDIBOHF23SPDLT)/recn = Recipients/cn = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500:/o = 첫 번째 조직/ou = Exchange 관리 그룹 (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | smtp: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Lara \. Newton@northwind.com                                                                                           |
    |||

   예제 **원본** 사서함 개체:

   | 특성             | 값                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | 별칭                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = 첫 번째 조직/ou = Exchange 관리 그룹                   |
   |                       | (FYDIBOHF23SPDLT)/recn = Recipients/cn = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | smtp: LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP: Lara \. Newton@contoso.com          |
   |||

   - 추가 특성은 Exchange 하이브리드 쓰기에 이미 포함 되어 있을 수 있습니다. 그렇지 않으면 포함 해야 합니다. 
   - msExchBlockedSendersHash – 클라이언트의 온라인 수신 허용 및 수신 거부 데이터를 온-프레미스 Active Directory에 다시 씁니다.
   - msExchSafeRecipientsHash – 클라이언트의 온라인 수신 허용 및 수신 거부 데이터를 온-프레미스 Active Directory에 다시 씁니다.
   - msExchSafeSendersHash – 클라이언트의 온라인 수신 허용 및 수신 거부 데이터를 온-프레미스 Active Directory에 다시 씁니다.

2. 원본 사서함이 LitigationHold에 있고 원본 사서함 복구 가능한 항목 크기가 데이터베이스 기본값 (30gb) 보다 크면 대상 할당량이 원본 사서함 크기 보다 작기 때문에 이동을 진행 하지 않습니다. 대상 MailUser 개체를 업데이트 하 여 ELC 사서함 플래그를 원본 환경에서 대상으로 전환 하 여 대상 시스템이 MailUser의 할당량을 100 g b로 확장 하 여 대상으로 이동할 수 있도록 합니다. 이 지침은 ELC 플래그 스탬프 명령을 사용 하 여 테 넌 트 관리자에 게 노출 되지 않으므로 Azure AD Connect를 실행 하는 하이브리드 id에 대해서만 작동 합니다.

    >[!Note]
    > 샘플-보증 없음<br/>이 스크립트는 원본 사서함 (원본 값 가져오기)과 대상 온-프레미스 Active Directory (ADUser 개체 스탬프 지정)에 대 한 연결을 가정 합니다. 원본에 소송 또는 단일 항목 복구가 사용 하도록 설정 되어 있는 경우 대상 계정에서이를 설정 합니다.  이렇게 하면 대상 계정의 휴지통 크기가 100 GB로 증가 합니다.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. 비 하이브리드 대상 테 넌 트는 Mailusers 개체에 대 한 소송 보존을 사용 하도록 설정 하 고 할당량을 100 GB로 늘리기 위해 다음 명령을 실행 하 여, 마이그레이션 전에 MailUsers에 대 한 복구 가능한 항목 폴더의 할당량을 수정할 수 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 있습니다. 참고 하이브리드의 테 넌 트에 대해서는이 작업을 수행할 수 없습니다.

4. 대상 조직의 사용자에 게는 조직에 적합 한 Exchange Online 구독을 사용할 수 있는 권한이 있어야 합니다. 사서함 이동이 진행 되는 동안에는 라이선스를 적용할 수 있지만 대상 MailUser가 ExchangeGUID 및 프록시 주소로 제대로 설정 된 경우에만 가능 합니다. ExchangeGUID을 적용 하기 전에 라이선스를 적용 하면 대상 조직에 새 사서함이 프로 비전 됩니다. 

    > [!Note]
    > 사서함 또는 MailUser 개체에 라이선스를 적용 하는 경우 모든 SMTP 유형 proxyAddresses가 scrubbed 되어 확인 된 도메인만 Exchange EmailAddresses 배열에 포함 됩니다. 

5. 대상 MailUser에 원본 ExchangeGuid와 일치 하지 않는 이전 ExchangeGuid가 없는지 확인 해야 합니다. 이 문제는 대상 MEU가 이전에 Exchange Online에 대해 사용이 허가 되었으며 사서함이 프로 비전 된 경우에 발생할 수 있습니다. 대상 MailUser가 이전에 사용이 허가 되었거나 원본 ExchangeGuid와 일치 하지 않는 ExchangeGuid 있는 경우 클라우드 MEU 정리를 수행 해야 합니다. 이러한 클라우드 MEUs의 경우 명령을 실행할 수 있습니다 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` . 

    > [!Caution]
    > 이 프로세스는 되돌릴 수 없습니다. 개체에 소프트 삭제 된 사서함이 있는 경우이 지점 이후에는 복원할 수 없습니다. 하지만 올바른 ExchangeGuid를 대상 개체에 동기화 할 수는 있지만 MRS에서는 원본 사서함을 새로 만든 대상 사서함에 연결 합니다. 새 매개 변수에서 EHLO 블로그를 참조 합니다. 
 
    이 명령을 사용 하 여 이전에 사서함 이었던 개체를 찾습니다.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    예를 들면 다음과 같습니다. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    이 명령을 사용 하 여 일시 삭제 된 사서함의 선택을 취소 합니다.

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    예를 들면 다음과 같습니다.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>사서함 마이그레이션 수행

테 넌 트 Exchange 사서함 마이그레이션은 대상 테 넌 트에서 시작 되는 마이그레이션 일괄 처리로 전송 됩니다. 이는 Exchange 온-프레미스에서 Microsoft 365으로 마이그레이션할 때 탑재 된 마이그레이션 일괄 처리가 작동 하는 방식과 비슷합니다. 

### <a name="create-migration-batches"></a>마이그레이션 일괄 처리 만들기

다음은 kicking 끄기 이동에 대 한 예제 마이그레이션 일괄 처리 cmdlet입니다.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> CSV 파일의 전자 메일 주소는 원본 테 넌 트가 아닌 대상 테 넌 트에 지정 된 것 이어야 합니다.

또한 마이그레이션 일괄 처리는 테 넌 트 옵션을 선택할 때 새 Exchange 관리 센터에서 지원 됩니다.
 
#### <a name="update-on-premises-mailusers"></a>온-프레미스 MailUsers 업데이트

사서함이 원본에서 대상으로 이동한 후에는 원본 및 대상 모두의 온-프레미스 메일 사용자가 새 targetAddress 업데이트 되도록 해야 합니다. 예제에서 이동에 사용 되는 targetDeliveryDomain는 **contoso \. onmicrosoft.com**입니다. 이 targetAddress를 사용 하 여 메일 사용자를 업데이트 합니다.
 
## <a name="frequently-asked-questions"></a>자주하는 질문
 
**이동 후 원본 온-프레미스에서 RemoteMailboxes을 업데이트 해야 하나요?**
 
예, 원본 테 넌 트 사서함이 대상 테 넌 트로 이동 하는 경우 원본 온-프레미스 사용자의 targetAddress (RemoteRoutingAddress/ExternalEmailAddress)를 업데이트 해야 합니다.  메일 라우팅은 서로 다른 targetAddresses를 사용 하는 여러 메일 사용자 간의 참조를 따를 수 있지만 메일 사용자에 대 한 약속 있음/없음 조회는 사서함 사용자의 위치를 지정 해야 합니다. 약속 있음/없음 조회에서는 여러 리디렉션이 추적 되지 않습니다. 
 
**팀 채팅 폴더 콘텐츠가 교차 테 넌 트를 마이그레이션 하나요?** 

아니요, 팀 채팅 폴더 콘텐츠가 교차 테 넌 트를 마이그레이션하지 않습니다. 
 
**내 온 보 딩 및 오프 보 딩 이동이 아니라 테 넌 트 이동의 이동만 표시 하려면 어떻게 해야 합니까?**

`-flags`매개 변수를 사용 합니다. 예를 들면 다음과 같습니다.

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**테스트에 사용 되는 특성을 복사 하는 예제 스크립트를 제공할 수 있나요?**

> [!Note]
> 샘플-보증 없음<br/>이 스크립트는 원본 사서함 (원본 값 가져오기)과 대상 온-프레미스 Active Directory 도메인 서비스 (ADUser 개체 스탬프 지정)에 대 한 연결을 가정 합니다. 원본에 소송 또는 단일 항목 복구가 사용 하도록 설정 되어 있는 경우 대상 계정에서이를 설정 합니다.  이렇게 하면 대상 계정의 휴지통 크기가 100 GB로 증가 합니다.

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
**사서함을 이동한 후 제 1 일에 Outlook에 액세스 하려면 어떻게 해야 합니까?**

한 테 넌 트가 도메인을 소유할 수 있으므로 사서함 이동이 완료 되 면 이전 주 SMTPAddress 대상 테 넌 트의 사용자에 게 연결 되지 않습니다. 새 테 넌 트와 연결 된 도메인만 Outlook에서는 사용자 새 UPN을 사용 하 여 서비스를 인증 하며, Outlook 프로필에서는 대상 시스템의 사서함과 일치 하도록 레거시 기본 SMTPAddress를 찾습니다. 레거시 주소가 대상 시스템에 없으므로 outlook 프로필이 연결 되지 않아 새로 이동한 사서함을 찾을 수 없습니다. 

이 초기 배포의 경우 사용자는 새 UPN, 기본 SMTP 주소 및 다시 동기화 OST 콘텐츠를 사용 하 여 프로필을 다시 작성 해야 합니다. 

> [!Note]
> 사용자가 완료를 위해 일괄 처리 하도록 계획 합니다. Outlook 클라이언트 프로필을 만들고 이후 OST 및 OAB 파일을 클라이언트에 다운로드 하는 경우 네트워크 사용률과 용량을 고려해 야 합니다. 
 
**테 넌 트 이동을 설정 하거나 완료 하려면 어떤 Exchange RBAC 역할이 필요 합니까?**
 
사서함 이동을 실행할 때 위임 된 의무의 가정을 기반으로 하는 역할 매트릭스가 있습니다. 현재 다음과 같은 두 가지 역할이 필요 합니다.  

- 첫 번째 역할은 테 넌 트/조직 경계에서 들어오고 외부로 콘텐츠를 이동할 수 있는 권한을 설정 하는 일회성 설치 작업에 대 한 것입니다. 조직 제어에서 데이터를 이동 하는 것이 모든 회사에서 중요 한 관심사 이기 때문에, 조직 관리자 (OrgAdmin)에 게 할당 된 가장 높은 역할이 적용 됩니다. 이 역할은 원격 조직과의-MailboxMoveCapability을 정의 하는 새 New-organizationrelationship를 변경 하거나 설정 해야 합니다. MailboxMoveCapability 설정을 변경할 수 있는 OrgAdmin 있고, OrganizationRelationhip의 기타 특성을 페더레이션 공유 관리자가 관리할 수 있습니다. 
 
- 실제 move 명령을 실행 하는 역할은 하위 수준 기능으로 위임 될 수 있습니다. 사서함 이동 역할에는 매개 변수를 사용 하 여 조직 외부로 또는 외부에서 사서함을 이동 하는 기능이 할당 됩니다 `-RemoteTenant` .  

**어떤 방법으로 변환 된 사서함에서 targetAddress (TargetDeliveryDomain)에 대해 선택한 SMTP 주소를 어떻게 지정 하나요?**
 
MRS를 사용 하 여 Exchange 사서함 이동 대상 개체에 proxyAddress (전자 메일 주소)를 일치 시켜 MailUser로 변환할 때 원본 사서함에서 targetAddress를 만듭니다. 이 프로세스에서는 이동 명령에 전달 된-TargetDeliveryDomain 값을 사용 하 여 대상 쪽에서 해당 도메인에 대해 일치 하는 프록시를 확인 합니다. 일치 하는 항목을 찾은 경우 일치 하는 proxyAddress는 변환 된 사서함 (now MailUser) 개체에서 ExternalEmailAddress (targetAddress)를 설정 하는 데 사용 됩니다.
 
**사서함 사용 권한을 전환 하는 방법**

사서함 사용 권한에는 대신 보내기 및 사서함 액세스가 포함 됩니다. 

- 대신 보내기 (AD: publicDelegates)는 사용자의 사서함에 대 한 액세스 권한이 있는 받는 사람의 DN을 대리인으로 저장 합니다. 이 값은 Active Directory에 저장 되며 사서함 전환의 일부로 현재 이동 하지 않습니다. 원본 사서함에 publicDelegates 설정 된 경우에는 명령을 사용 하 여 대상 환경에서 MEU to Mailbox 변환이 완료 되 면 대상 사서함에 publicDelegates을 다시 스탬프 해야 합니다 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` . 
 
- 사서함에 저장 된 사서함 사용 권한은 주 서버와 대리인이 모두 대상 시스템으로 이동 될 때 사서함과 함께 이동 됩니다. 예를 들어 사용자 TestUser_7에는 테 넌 트 SourceCompany.onmicrosoft.com의 사서함 TestUser_8에 대 한 FullAccess 권한이 부여 됩니다. 사서함 이동이 TargetCompany.onmicrosoft.com으로 완료 된 후에는 대상 디렉터리에 동일한 사용 권한이 설정 됩니다. 원본 및 대상 테 넌 트에서 TestUser_7에 대 한 *add-mailboxpermission* 를 사용 하는 예는 다음과 같습니다. Exchange cmdlet에는 원본 및 대상에 따라 접두사가 지정 됩니다. 
 
다음은 이동 하기 전의 사서함 사용 권한 출력의 예입니다. 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
다음은 이동 후의 사서함 사용 권한 출력에 대 한 예입니다. 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> 테 넌 트 사서함 및 일정 사용 권한은 지원 되지 않습니다. 이러한 연결 된 사서함이 원본 테 넌 트에서 동시에 전환 되도록 주체와 대리인을 통합 일괄 처리로 구성 해야 합니다. 
 
## <a name="known-issues"></a>알려진 문제 

-  **문제: 자동으로 확장 된 보관 함을 마이그레이션할 수 없습니다.** 테 넌 트 마이그레이션 기능은 특정 사용자에 대 한 기본 사서함 및 보관 사서함의 마이그레이션을 지원 합니다. 원본 사용자가 보관 사서함을 두 개 이상 자동으로 확장 한 경우에는 해당 기능을 통해 추가 보관 함을 마이그레이션할 수 없습니다.

- **문제: 소유 하지 않은 smtp proxyAddress block을 사용 하는 클라우드 MailUsers MRS가 background를 이동 합니다.** 대상 테 넌 트 MailUser 개체를 만들 때 모든 SMTP 프록시 주소가 대상 테 넌 트 조직에 속하는지 확인 해야 합니다. 로컬 테 넌 트에 속하지 않은 대상 메일 사용자에 게 SMTP proxyAddress가 있으면 MailUser를 Mailbox로 변환 하는 것이 차단 됩니다. 이는 사서함 개체가 테 넌 트가 신뢰할 수 있는 도메인 (테 넌 트에 의해 요구 되는 도메인)에서 메일을 보내기만 하기 때문입니다. 
- 
   - Azure AD Connect를 사용 하 여 온-프레미스에서 사용자를 동기화 하는 경우 온-프레미스 MailUser 개체에 사서함이 있는 원본 테 넌 트를 가리키는 ExternalEmailAddress (laran@contoso onmicrosoft.com)를 제공 하 \. 고 PrimarySMTPAddress를 대상 테 넌 트 (Lara. Newton@northwind com)에 있는 도메인으로 스탬프 처리 합니다. \. 이러한 값은 테 넌 트에서 동기화 되 고 적절 한 메일 사용자가 프로 비전 되어 마이그레이션 준비가 완료 된 것입니다. 예제 개체는 다음과 같습니다.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > EmailAddresses/proxyAddresses 배열에 *contoso. onmicrosoft \. com* 주소가 *없습니다* .

- **문제: "external" 기본 SMTP 주소가 있는 MailUser 개체를 수정/다시 설정 하 여 "내부" 회사에 요청한 도메인**

   MailUser 개체는 비로컬 사서함에 대 한 포인터입니다. 테 넌 트 사서함 마이그레이션의 경우에는 MailUser 개체를 사용 하 여 원본 사서함 (대상 조직의 관점) 또는 대상 사서함 (원본 조직의 관점)을 나타냅니다. MailUsers에는 \@ \. 디렉터리에 있는 사서함 사용자의 표시 된 smtp 주소를 나타내는 실제 사서함 (proxytest fabrikam onmicrosoft.com) 및 primarysmtp 주소의 smtp 주소를 가리키는 ExternalEmailAddress (targetAddress)이 있습니다. 일부 조직에서는 기본 SMTP 주소를 로컬 테 넌 트 (예: contoso.com가 아닌 fabrikam.com)가 소유 하는 주소가 아닌 외부 SMTP 주소로 표시 하도록 선택 합니다.  그러나 Exchange 서비스 계획 개체가 라이선스 작업을 통해 MailUser에 적용 되 면 기본 SMTP 주소가 로컬 조직에서 확인 된 도메인 (contoso.com)으로 표시 되도록 수정 됩니다. 다음과 같은 두 가지 이유가 있습니다.
   
   - Exchange 서비스 계획이 MailUser에 적용 되 면 Azure AD 프로세스는 로컬 조직이 다른 테 넌 트에서 메일을 보내거나 스푸핑 또는 메일을 보낼 수 없도록 하기 위해 프록시 스크러빙을 강제로 적용 하기 시작 합니다. 로컬 조직에서 주소를 확인 하지 않으면 이러한 서비스 계획이 포함 된 받는 사람 개체의 모든 SMTP 주소가 제거 됩니다. 예제의 경우와 마찬가지로, Fabikam \. com 도메인은 contoso onmicrosoft.com 테 넌 트에 의해 확인 되지 않으므로 \. 스크러빙은 해당 fabrikam com 도메인을 제거 합니다 \. . 이 외부 도메인을 MailUser에 유지 하려면 마이그레이션 이전 또는 마이그레이션 후에 해당 사용자에 게 예상 되는 외부 브랜딩을 적용 되도록 이동이 완료 된 후 또는 이동 하기 전에 라이선스를 제거 하도록 마이그레이션 프로세스를 변경 해야 합니다. 메일 서비스에 영향을 주지 않도록 사서함 개체의 사용권이 적절 한지 확인 해야 합니다.<br/><br/>Contoso onmicrosoft.com 테 넌 트의 MailUser에서 서비스 요금제를 제거 하는 예제 스크립트는 \. 여기에 표시 됩니다.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       지정 된 ServicePlans 집합의 결과가 여기에 표시 됩니다.

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
 
       사용자의 PrimarySMTPAddress 더 이상 scrubbed 않습니다. Fabrikam.com 도메인은 contoso.onmicrosoft.com 테 넌 트에서 소유 되지 않으며 디렉터리에 표시 된 기본 SMTP 주소로 유지 됩니다.

       예를 들면 다음과 같습니다.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - MsExchRemoteRecipientType가 8 (DeprovisionMailbox)로 설정 되 면 대상 테 넌 트로 마이그레이션되는 온-프레미스 MailUsers의 경우 Azure의 프록시 스크러빙 논리는 소유 하지 않는 도메인을 제거 하 고 primarySMTP를 소유한 도메인으로 다시 설정 합니다. 온-프레미스 MailUser에서 msExchRemoteRecipientType를 지우면 프록시 삭제 논리가 더 이상 적용 되지 않습니다. <br/><br>다음은 Exchange Online을 포함 하는 가능한 서비스 계획의 전체 집합입니다.

   | 이름                                              |
   |---------------------------------------------------|
   | 고급 eDiscovery 저장소 (500GB)               |
   | 고객 Lockbox                                  |
   | 데이터 손실 방지                              |
   | Exchange Enterprise CAL Services (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (계획 1)                          |
   | Exchange Online (계획 2)                          |
   | Exchange Online용 Exchange Online Archiving     |
   | Exchange Server용 Exchange Online Archiving     |
   | Exchange Online 비활성 사용자 추가 기능              |
   | Exchange Online Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online 요금제 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | 정보 장벽                              |
   | Office 365에 대 한 정보 보호-Premium   |
   | Office 365에 대 한 정보 보호-표준  |
   | MyAnalytics에서의 정보                           |
   | Microsoft 365 고급 감사                   |
   | Microsoft Bookings                                |
   | Microsoft 비즈니스 센터                         |
   | Microsoft MyAnalytics (Full)                      |
   | Office 365 고급 eDiscovery                    |
   | Office 365 Advanced Threat Protection (요금제 1)    |
   | Office 365 Advanced Threat Protection (계획 2)    |
   | Office 365 권한 있는 액세스 관리           |
   | Outlook Customer Manager                          |
   | Office 365의 Premium 암호화                  |
   || 
 
