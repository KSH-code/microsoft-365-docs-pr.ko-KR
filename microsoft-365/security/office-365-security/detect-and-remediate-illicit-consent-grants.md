---
title: 불법 동의 권한 부여 검색 및 재구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Office 365에서 불법 동의 권한 부여 공격을 인식하고 교정하는 방법에 대해 알아보세요.
ms.openlocfilehash: 43ce8de2826006069b815a37208fe2a3834bf313
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637607"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>불법 동의 권한 부여 검색 및 재구성

**요약** Office 365에서 불법 동의 권한 부여 공격을 인식하고 교정하는 방법에 대해 알아보세요.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Office 365에서 불법 동의 권한 부여 공격은 무엇인가요?

불법 동의 권한 부여 공격에는 공격자가 연락처 정보, 전자 메일 또는 문서 등의 데이터에 대한 액세스를 요청하는 Azure 등록 응용 프로그램을 만듭니다. 그런 다음 공격자는 최종 사용자가 피싱 공격을 통해 또는 신뢰할 수있는 웹 사이트에 불법 코드를 주입하여 해당 응용 프로그램에 데이터 액세스 권한을 부여하도록 속임수를 씁니다. 불법 응용 프로그램에 대한 동의가 부여되면 조직 계정이 없어도 데이터에 대한 계정 수준의 액세스 권한을 갖습니다. 침해된 계정에 대한 암호를 재설정하거나 계정에 MFA(다단계 인증)을 요구하는 등의 일반적인 조치 단계는 이러한 응용 프로그램이 타사 응용 프로그램이므로 조직 외부에 있기 때문에 이 유형의 공격에 효과적이지 않습니다. 

이러한 공격은 정보를 호출하는 엔터티가 사용자가 아니라 자동화임을 가정하는 상호 작용 모델을 활용합니다.

> [!IMPORTANT]
> 지금은 앱에서 불법 동의 허용으로 인해 문제가 발생 하는 것으로 생각 하십니까? Microsoft Cloud App Security (MCAS)에는 OAuth 앱을 검색, 조사 및 수정 하기 위한 도구가 포함 되어 있습니다. 이 MCAS 문서에는 [위험한 OAuth 앱 조사](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)에 대 한 방법을 설명 하는 자습서가 포함 되어 있습니다. 또한 [OAuth 앱 정책을](https://docs.microsoft.com/cloud-app-security/app-permission-policy) 설정 하 여 앱 요청 권한, 사용자가 이러한 앱에 권한을 부여 하 고 있으며 이러한 사용 권한 요청을 광범위 하 게 승인 하거나 금지 하도록 설정할 수 있습니다.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>불법 동의 권한 부여는 Office 365에서 어떻게 보이나요?

**감사 로그** 를 검색 하 여이 공격의 손상 표시기 (IOC) 라고도 하는 서명을 찾습니다. 여러 Azure 등록 응용 프로그램 및 대규모 사용자를 포함하는 조직의 경우 가장 좋은 방법은 주 단위로 조직 동의 권한 부여를 검토하는 것입니다.

### <a name="steps-for-finding-signs-of-this-attack"></a>이 공격의 신호를 찾는 단계

1. 테 넌 트에서 **보안 & 준수 센터** 를 엽니다.

2. **검색** 으로 이동한 후 **감사 로그 검색**을 선택 합니다.

3. 검색 (모든 작업 및 모든 사용자)을 선택 하 고 필요한 경우 시작 날짜와 끝 날짜를 입력 한 다음 **검색**을 클릭 합니다. 

4. 응용 프로그램에 대 한 동의에 대 한 결과를 필터링 하 고 OAuth2PermissionGrant를 추가 합니다.

5. 결과를 클릭 하 여 활동의 세부 정보를 확인 합니다. **자세한 정보** 를 클릭 하면 활동에 대 한 세부 정보를 볼 수 있습니다. IsAdminContent가 True로 설정 되어 있는지 확인 하세요.

> [!NOTE]
> * 이벤트가 발생 한 후에는 해당 감사 로그 항목이 검색 결과에 표시 될 때까지 30 분에서 24 시간까지 소요 될 수 있습니다. <br/><br/> 감사 레코드가 보존 되 고 감사 로그에서 검색 가능한 기간은 Microsoft 365 구독에 따라 다르며, 특히 특정 사용자에 게 할당 된 라이선스의 유형입니다. 자세한 내용은 [감사 로그](../../compliance/search-the-audit-log-in-security-and-compliance.md)를 참조하세요.
이 값이 true이면 전역 관리자 액세스 권한이 있는 사용자가 데이터에 대한 광범위한 액세스 권한을 부여할 수 있음을 나타냅니다. 예기치 않은 상황이라면 [공격을 확인](#how-to-confirm-an-attack)하는 단계를 수행하세요.

## <a name="how-to-confirm-an-attack"></a>공격을 확인하는 방법

위에 나와 있는 IOCs의 인스턴스가 하나 이상 있는 경우 공격이 발생했음을 확실하게 확인하도록 추가 조사를 수행해야 합니다. 다음의 세 가지 방법 중 하나를 사용하여 공격을 확인할 수 있습니다.

- Azure Active Directory 포털을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한 이 방법은 철저하지만 한번에 한 명의 사용자만 검사할 수 있어 검사할 사용자가 많은 경우에는 막대한 시간이 소요됩니다.

- PowerShell을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한 이 방법은 최소한의 오버 헤드를 사용하는 가장 빠르고 철저한 방법입니다.

- 사용자가 앱과 권한을 개별적으로 확인하고 조치를 위해 그 결과를 관리자에게 다시 보고합니다.

## <a name="inventory-apps-with-access-in-your-organization"></a>조직에서 액세스 권한이 있는 인벤터리 앱

Azure Active Directory 포털이나 PowerShell을 사용하여 사용자를 위해 이 작업을 수행하거나 사용자가 응용 프로그램 액세스를 개별적으로 열거하도록 할 수 있습니다.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Azure Active Directory 포털 사용 단계

[Azure Active Directory 포털](https://portal.azure.com/)를 사용하여 개별 사용자에게 사용 권한을 부여한 응용 프로그램을 찾을 수 있습니다.

1. 관리 권한으로 Azure Portal에 로그인합니다.

2. Azure Active Directory 블레이드를 선택합니다.

3. **사용자**를 선택합니다.

4. 검토할 사용자를 선택합니다.

5. **응용 프로그램**을 선택합니다.

이렇게 하면 사용자에 게 할당 된 앱과 응용 프로그램에 포함 된 사용 권한이 표시 됩니다.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>사용자가 응용 프로그램에 액세스를 열거하도록 하는 단계

사용자가 https://myapps.microsoft.com(으)로 이동하여 해당 응용 프로그램에 대한 액세스를 검토할 수 있도록 합니다. 액세스 권한이 있는 모든 앱을 확인하고, 세부 정보를 볼 수 있습니다(액세스 범위 포함). 또는 의심스러운 앱이나 불법 앱에 대한 사용 권한을 해지할 수 있습니다.

### <a name="steps-for-doing-this-with-powershell"></a>PowerShell로 이 작업을 수행하기 위한 단계

불법 동의 권한 부여를 확인하는 가장 간단한 방법은 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)을 실행하는 것입니다. 이는 테넌시의 모든 사용자에 대한 모든 OAuth 동의 권한 부여 및 OAuth 앱을 하나의 .csv 파일로 덤프합니다.

#### <a name="pre-requisites"></a>필수 구성 요소

- Azure AD PowerShell 라이브러리가 설치됨

- 스크립트를 실행할 테넌트에 대한 전역 관리자 권한

- 스크립트를 실행할 컴퓨터의 로컬 관리자

> [!IMPORTANT]
> 관리 계정에 대해 multi-factor authentication을 사용 하는 것 ***이 좋습니다*** . 이 스크립트는 MFA 인증을 지원합니다.

1. 로컬 관리자 권한으로 스크립트를 실행할 컴퓨터에 로그인합니다.

2. GitHub에서 스크립트를 실행 하는 폴더에 [Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) 스크립트를 다운로드 하거나 복사 합니다. 이 폴더는 "permissions.csv" 출력 파일이 작성되는 폴더와 동일합니다.

3. PowerShell 인스턴스를 관리자로 열고 스크립트를 저장한 폴더를 엽니다.

4. [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet을 사용하여 디렉터리에 연결합니다.

5. 이 PowerShell 명령을 실행합니다.

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

스크립트가 Permissions.csv라는 파일 하나를 생성합니다. 다음 단계를 수행하여 불법 응용 프로그램 권한 부여를 찾습니다.

1. ConsentType 열(G열)에서 값 "AllPrinciples"을 검색합니다. AllPrincipals 사용 권한을 사용 하면 클라이언트 응용 프로그램에서 테 넌 시의 모든 사용자 콘텐츠에 액세스할 수 있습니다. 네이티브 Microsoft 365 응용 프로그램은 올바르게 작동 하려면이 권한이 필요 합니다. 이 권한을 가진 Microsoft가 아닌 모든 응용 프로그램은 신중하게 검토해야 합니다.

2. 사용 권한 열(F열)에서 각 위임된 응용 프로그램에 대한 콘텐츠 사용 권한을 확인합니다. "읽기" 및 "쓰기" 권한 또는 "*.All" 권한을 찾아 적절하지 않을 수 있으므로 신중하게 검토합니다.

3. 동의가 부여된 특정 사용자를 검토합니다. 주목 받거나 영향력이 큰 사용자에게 부적절한 동의가 부여된 경우 추가 조사를 수행해야 합니다.

4. ClientDisplayName 열(C열)에서 의심스러운 앱을 찾습니다. 맞춤법이 잘못된 이름, 아주 밋밋한 이름 또는 해커 같은 이름을 사용 하는 앱은 신중하게 검토해야 합니다.

## <a name="determine-the-scope-of-the-attack"></a>공격 범위 확인

응용 프로그램 액세스 인벤토리를 완료 한 후 **감사 로그** 를 검토 하 여 위반의 전체 범위를 확인 합니다. 영향을 받는 사용자, 불법 응용 프로그램에서 조직에 액세스한 시간 프레임, 앱에 대한 사용 권한을 검색합니다. [Microsoft 365 보안 및 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)에서 **감사 로그**를 검색할 수 있습니다.

> [!IMPORTANT]
> 이 정보를 받으려면 공격 전에 [사서함 감사](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) 및 [관리자 및 사용자 활동에 대한 감사](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)가 설정되어 있어야 합니다.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>불법 동의 권한 부여를 방지하고 교정하는 방법

불법 사용 권한이 있는 응용 프로그램을 식별한 후 해당 액세스를 제거하는 방법에는 여러 가지가 있습니다.

- 다음과 같은 방법으로 Azure Active Directory 포털에서 응용 프로그램의 사용 권한을 해지할 수 있습니다.

  - **Azure Active Directory 사용자** 블레이드에서 영향을 받는 사용자로 이동합니다.

  - **응용 프로그램**을 선택합니다.

  - 불법 응용 프로그램을 선택합니다.

  - 드릴 다운에서 **제거**를 클릭합니다.

- [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)에 나와 있는 단계를 따라 PowerShell에서 OAuth 승인 부여를 해지할 수 있습니다.

- [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)의 단계에 따라 PowerShell을 사용하여 서비스 앱 역할 할당을 해지할 수 있습니다.

- 영향을 받는 계정에 대한 로그인을 사용하지 않도록 설정할 수도 있습니다. 그러면 해당 계정의 데이터에 대한 앱 액세스를 해제합니다. 이는 최종 사용자의 생산성에 이상적이지는 않지만 영향을 신속하게 제한려 한다면 단기적으로 조치가 될 수 있습니다.

- 테넌시에 통합 응용 프로그램을 해제할 수 있습니다. 이는 최종 사용자가 테넌트 전반에 대한 동의를 부여하는 기능을 해제하는 극단적인 단계입니다. 따라서 사용자가 실수로 악성 응용 프로그램에 액세스를 부여하는 것을 방지할 수 있습니다. 타사 응용 프로그램을 사용하여 생산성을 높일 수 있는 사용자 능력을 크게 손상시킬 수 있으므로 권장하지 않습니다. [통합 앱을 설정하거나 해제](https://docs.microsoft.com/office365/admin/misc/integrated-apps)하는 단계를 수행하여 이 작업을 수행할 수 있습니다.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Cybersecurity pro와 같은 Microsoft 365 보안

Microsoft 365 구독에는 데이터와 사용자를 보호 하는 데 사용할 수 있는 강력한 보안 기능 집합이 포함 되어 있습니다. Microsoft 365 테 넌 트를 보호 하기 위한 Microsoft 권장 모범 사례를 구현 하려면 [microsoft 365 보안 로드맵-처음 30 일, 90 일 및 그 이상에 해당 하는 주요 우선 순위](security-roadmap.md) 를 사용 합니다.

- 처음 30일 이내에 수행 할 작업 이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.

- 90일 이내에 수행해야 할 작업 이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.

- 90일 초과 이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.

## <a name="see-also"></a>참고 항목:

- [내 응용 프로그램 목록에 예기치 않은 응용 프로그램](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)은 데이터에 대한 액세스 권한이 있는 예기치 않은 응용 프로그램이 있다는 사실을 인식한 후 관리자가 수행할 수 있는 다양한 작업을 안내합니다.

- [Azure Active Directory와 응용 프로그램 통합](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)은 동의 및 사용 권한에 대한 개요입니다.

- [내 응용 프로그램 개발 문제](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)는 다양한 동의 관련 문서의 링크를 제공합니다.

- [Azure AD(Active Directory)의 응용 프로그램 및 서비스 주체 개체](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)는 응용 프로그램 모델의 핵심인 응용 프로그램 및 서비스 주체 개체에 대한 개요를 제공합니다.

- [앱 액세스 관리](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)는 관리자가 앱에 대한 사용자 액세스를 관리해야 하는 기능에 대한 개요입니다.
