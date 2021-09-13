---
title: 위조 동의 권한 부여 감지 및 수정
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
localization_priority: Normal
search.appverid:
- MET150
description: 개인 정보에서 위조 동의 권한 부여 공격을 인식하고 수정하는 Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb3ccfbb921c106b671c4409bb95bd200f0efb55
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214452"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>위조 동의 권한 부여 감지 및 수정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**요약**  개인 정보에서 위조 동의 권한 부여 공격을 인식하고 수정하는 Microsoft 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>2016년 8월 1일부로 공개된 공격은 Microsoft 365?

불법 동의 권한 부여 공격에는 공격자가 연락처 정보, 전자 메일 또는 문서 등의 데이터에 대한 액세스를 요청하는 Azure 등록 응용 프로그램을 만듭니다. 그런 다음 공격자는 최종 사용자가 피싱 공격을 통해 또는 신뢰할 수있는 웹 사이트에 불법 코드를 주입하여 해당 응용 프로그램에 데이터 액세스 권한을 부여하도록 속임수를 씁니다. 불법 응용 프로그램에 대한 동의가 부여되면 조직 계정이 없어도 데이터에 대한 계정 수준의 액세스 권한을 갖습니다. 침해된 계정에 대한 암호를 재설정하거나 계정에 MFA(다단계 인증)을 요구하는 등의 일반적인 조치 단계는 이러한 응용 프로그램이 타사 응용 프로그램이므로 조직 외부에 있기 때문에 이 유형의 공격에 효과적이지 않습니다.

이러한 공격은 정보를 호출하는 엔터티가 사용자가 아니라 자동화임을 가정하는 상호 작용 모델을 활용합니다.

> [!IMPORTANT]
> 현재 앱에서의 부적격 동의 권한 부여에 문제가 발생하고 있는 것으로 의심하나요? Microsoft Cloud App Security(MCAS)에는 OAuth 앱을 검색, 조사 및 수정하는 도구가 있습니다. 이 MCAS 문서에는 위험한 OAuth 앱 조사 방법을 간략하게 [설명하는 자습서가 있습니다.](/cloud-app-security/investigate-risky-oauth) [OAuth](/cloud-app-security/app-permission-policy) 앱 정책을 설정하여 앱 요청 권한을 조사하고, 사용자가 이러한 앱을 승인하고, 이러한 사용 권한 요청을 광범위하게 승인하거나 금지할 수도 있습니다.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>이 경우의 부적격 동의 권한 부여 공격은 어떤 Microsoft 365?

감사 로그를 **검색하여** 이 공격의 IOC(손상 표시기)라고도 하는 기호를 찾아야 합니다. 여러 Azure 등록 응용 프로그램 및 대규모 사용자를 포함하는 조직의 경우 가장 좋은 방법은 주 단위로 조직 동의 권한 부여를 검토하는 것입니다.

### <a name="steps-for-finding-signs-of-this-attack"></a>이 공격의 신호를 찾는 단계

1. 에서 **Microsoft 365 Defender 포털을** <https://security.microsoft.com> 열고 감사 를 **선택합니다.** 또는 <https://security.microsoft.com/auditlogsearch>에서 **감사** 로 직접 이동하세요.

2. 감사 **페이지에서** 검색 탭이  선택되어 있는지 확인한 후 다음 설정을 구성합니다.
   - **날짜 및 시간 범위**
   - **활동:** 모든 활동에 대한 **결과 표시가 선택되어 있는지** 확인

   마쳤으면 **검색** 을 클릭합니다.

3. 작업 **열을** 클릭하여 결과를 정렬하고 응용 프로그램에 대한 **동의를 검색합니다.**

4. 활동 세부 정보를 확인하려면 목록에서 항목을 선택합니다. IsAdminContent가 True로 설정되어 있는지 검사합니다.

> [!NOTE]
>
> 이벤트가 발생한 후 해당 감사 로그 항목이 검색 결과에 표시될 때 30분에서 24시간까지 걸릴 수 있습니다.
>
> 감사 기록을 보존하고 감사 로그에서 검색할 수 있는 기간은 Microsoft 365 구독, 특히 특정 사용자에게 할당된 라이선스 유형에 따라 다릅니다. 자세한 내용은 [감사 로그](../../compliance/search-the-audit-log-in-security-and-compliance.md)를 참조하세요.
>
> 이 값이 true이면 전역 관리자 액세스 권한이 있는 사용자가 데이터에 대한 광범위한 액세스 권한을 부여할 수 있음을 나타냅니다. 예기치 않은 상황이라면 [공격을 확인](#how-to-confirm-an-attack)하는 단계를 수행하세요.

## <a name="how-to-confirm-an-attack"></a>공격을 확인하는 방법

위에 나와 있는 IOCs의 인스턴스가 하나 이상 있는 경우 공격이 발생했음을 확실하게 확인하도록 추가 조사를 수행해야 합니다. 다음 세 가지 방법 중 한 가지를 사용하여 공격을 확인할 수 있습니다.

- Azure Active Directory 포털을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한 이 방법은 철저하지만 한번에 한 명의 사용자만 검사할 수 있어 검사할 사용자가 많은 경우에는 막대한 시간이 소요됩니다.
- PowerShell을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한 이 방법은 최소한의 오버 헤드를 사용하는 가장 빠르고 철저한 방법입니다.
- 사용자가 앱과 권한을 개별적으로 확인하고 조치를 위해 그 결과를 관리자에게 다시 보고합니다.

## <a name="inventory-apps-with-access-in-your-organization"></a>조직에서 액세스 권한이 있는 인벤터리 앱

Azure Active Directory 포털이나 PowerShell을 사용하여 사용자를 위해 이 작업을 수행하거나 사용자가 응용 프로그램 액세스를 개별적으로 열거하도록 할 수 있습니다.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Azure Active Directory 포털 사용 단계

개별 사용자가 사용 권한을 부여한 응용 프로그램은 의 Azure Active Directory <https://portal.azure.com> 있습니다.

1. 관리자 권한으로 Azure Portal에 로그인합니다.
2. Azure Active Directory 블레이드를 선택합니다.
3. **사용자** 를 선택합니다.
4. 검토할 사용자를 선택합니다.
5. **응용 프로그램** 을 선택합니다.

그러면 사용자에게 할당된 앱과 응용 프로그램에 대한 사용 권한이 표시됩니다.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>사용자가 응용 프로그램에 액세스를 열거하도록 하는 단계

사용자가 <https://myapps.microsoft.com>(으)로 이동하여 해당 응용 프로그램에 대한 액세스를 검토할 수 있도록 합니다. 액세스 권한이 있는 모든 앱을 확인하고, 세부 정보를 볼 수 있습니다(액세스 범위 포함). 또는 의심스러운 앱이나 불법 앱에 대한 사용 권한을 해지할 수 있습니다.

### <a name="steps-for-doing-this-with-powershell"></a>PowerShell로 이 작업을 수행하기 위한 단계

불법 동의 권한 부여를 확인하는 가장 간단한 방법은 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)을 실행하는 것입니다. 이는 테넌시의 모든 사용자에 대한 모든 OAuth 동의 권한 부여 및 OAuth 앱을 하나의 .csv 파일로 덤프합니다.

#### <a name="pre-requisites"></a>필수 구성 요소

- Azure AD PowerShell 라이브러리가 설치됨
- 스크립트를 실행할 테넌트에 대한 전역 관리자 권한
- 스크립트를 실행할 컴퓨터의 로컬 관리자

> [!IMPORTANT]
> 관리 ***계정에*** 다단계 인증을 요구하는 것이 좋습니다. 이 스크립트는 MFA 인증을 지원합니다.

1. 로컬 관리자 권한으로 스크립트를 실행할 컴퓨터에 로그인합니다.

2. 스크립트를Get-AzureADPSPermissions.ps1[폴더로](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) GitHub 스크립트를 다운로드하거나 복사합니다. 이 폴더는 "permissions.csv" 출력 파일이 작성되는 폴더와 동일합니다.

3. 관리자 권한으로 PowerShell 세션을 열고 스크립트를 저장한 폴더를 열어 습니다.

4. [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet을 사용하여 디렉터리에 연결합니다.

5. 이 PowerShell 명령을 실행합니다.

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

스크립트가 Permissions.csv라는 파일 하나를 생성합니다. 다음 단계를 수행하여 불법 응용 프로그램 권한 부여를 찾습니다.

1. ConsentType 열(G열)에서 값 "AllPrinciples"을 검색합니다. AllPrincipals 권한을 사용하면 클라이언트 응용 프로그램에서 테넌시의 모든 콘텐츠에 액세스할 수 있습니다. 네이티브 Microsoft 365 제대로 작동하려면 이 권한이 필요합니다. 이 권한을 가진 Microsoft가 아닌 모든 응용 프로그램은 신중하게 검토해야 합니다.

2. 사용 권한 열(F열)에서 각 위임된 응용 프로그램에 대한 콘텐츠 사용 권한을 확인합니다. "읽기" 및 "쓰기" 권한 또는 "*.All" 권한을 찾아 적절하지 않을 수 있으므로 신중하게 검토합니다.

3. 동의가 부여된 특정 사용자를 검토합니다. 주목 받거나 영향력이 큰 사용자에게 부적절한 동의가 부여된 경우 추가 조사를 수행해야 합니다.

4. ClientDisplayName 열(C열)에서 의심스러운 앱을 찾습니다. 맞춤법이 잘못된 이름, 아주 밋밋한 이름 또는 해커 같은 이름을 사용 하는 앱은 신중하게 검토해야 합니다.

## <a name="determine-the-scope-of-the-attack"></a>공격 범위 확인

응용 프로그램 액세스 인벤토리 작성을  완료한 후 감사 로그를 검토하여 위반의 전체 범위를 파악합니다. 영향을 받는 사용자, 불법 응용 프로그램에서 조직에 액세스한 시간 프레임, 앱에 대한 사용 권한을 검색합니다. 감사 **로그는** 포털 에서 [검색할 Microsoft 365 Defender 있습니다.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> 이 정보를 받으려면 공격 전에 [사서함 감사](../../compliance/enable-mailbox-auditing.md) 및 [관리자 및 사용자 활동에 대한 감사](../../compliance/turn-audit-log-search-on-or-off.md)가 설정되어 있어야 합니다.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>불법 동의 권한 부여를 방지하고 교정하는 방법

불법 사용 권한이 있는 응용 프로그램을 식별한 후 해당 액세스를 제거하는 방법에는 여러 가지가 있습니다.

- 다음과 같은 방법으로 Azure Active Directory 포털에서 응용 프로그램의 사용 권한을 해지할 수 있습니다.
  1. **Azure Active Directory 사용자** 블레이드에서 영향을 받는 사용자로 이동합니다.
  2. **응용 프로그램** 을 선택합니다.
  3. 불법 응용 프로그램을 선택합니다.
  4. 드릴 다운에서 **제거** 를 클릭합니다.

- [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)에 나와 있는 단계를 따라 PowerShell에서 OAuth 승인 부여를 해지할 수 있습니다.

- [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)의 단계에 따라 PowerShell을 사용하여 서비스 앱 역할 할당을 해지할 수 있습니다.

- 영향을 받는 계정에 대한 로그인을 사용하지 않도록 설정할 수도 있습니다. 그러면 해당 계정의 데이터에 대한 앱 액세스를 해제합니다. 이는 최종 사용자의 생산성에 이상적이지는 않지만 영향을 신속하게 제한려 한다면 단기적으로 조치가 될 수 있습니다.

- 테넌시에 통합 응용 프로그램을 해제할 수 있습니다. 이는 최종 사용자가 테넌트 전반에 대한 동의를 부여하는 기능을 해제하는 극단적인 단계입니다. 따라서 사용자가 실수로 악성 응용 프로그램에 액세스를 부여하는 것을 방지할 수 있습니다. 타사 응용 프로그램을 사용하여 생산성을 높일 수 있는 사용자 능력을 크게 손상시킬 수 있으므로 권장하지 않습니다. [통합 앱을 설정하거나 해제](../../admin/misc/user-consent.md)하는 단계를 수행하여 이 작업을 수행할 수 있습니다.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>사이버 보안 프로그램과 같은 Microsoft 365 보안

Microsoft 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수 있는 강력한 보안 기능이 함께 제공됩니다. [Microsoft 365 보안 로드맵 - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Microsoft 365 테넌트 보안을 구현합니다.

- 처음 30일 이내에 수행 할 작업 이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.
- 90일 이내에 수행할 작업입니다. 이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.
- 90일을 초과합니다. 이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.

## <a name="see-also"></a>참고 항목

- [내 응용 프로그램 목록에 예기치 않은 응용 프로그램](/azure/active-directory/application-access-unexpected-application)은 데이터에 대한 액세스 권한이 있는 예기치 않은 응용 프로그램이 있다는 사실을 인식한 후 관리자가 수행할 수 있는 다양한 작업을 안내합니다.
- [Azure Active Directory와 응용 프로그램 통합](/azure/active-directory/active-directory-apps-permissions-consent)은 동의 및 사용 권한에 대한 개요입니다.
- [내 응용 프로그램 개발 문제](/azure/active-directory/active-directory-application-dev-development-content-map)는 다양한 동의 관련 문서의 링크를 제공합니다.
- [Azure AD(Active Directory)의 응용 프로그램 및 서비스 주체 개체](/azure/active-directory/develop/active-directory-application-objects)는 응용 프로그램 모델의 핵심인 응용 프로그램 및 서비스 주체 개체에 대한 개요를 제공합니다.
- [앱 액세스 관리](/azure/active-directory/active-directory-managing-access-to-apps)는 관리자가 앱에 대한 사용자 액세스를 관리해야 하는 기능에 대한 개요입니다.
