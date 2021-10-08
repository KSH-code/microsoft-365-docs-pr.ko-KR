---
title: 개발/테스트 환경에서 보안 격리를 사용하여 팀 구성
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: 직원이 언제 어디서나 원격으로 작업할 수 있는 보안 및 인프라를 구성하세요.
ms.openlocfilehash: 29b97c570972527ef30f3333797a213bf2722932
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176322"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a>개발/테스트 환경에서 보안 격리를 사용하여 팀 구성

이 문서에서는 개발/테스트 환경에서 [보안 격리](secure-teams-security-isolation.md)를 사용하여 팀을 만들기 위한 단계별 지침을 제공합니다.

![회사 전략 격리 팀 구성.](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

이 개발/테스트 환경을 사용하여 생산에 이러한 유형의 팀을 배포하기 전에 특정 요구 사항에 맞게 설정을 시험해 보고 세부 조정하도록 합니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항을 사용하여 중요하고 매우 중요한 팀을 간단한 방식으로 테스트하려는 경우에는 [간단한 기반 구성](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.

시뮬레이션 된 엔터프라이즈에서 중요하고 매우 중요한 팀을 테스트하려면 [암호 해시 동기화](../enterprise/password-hash-sync-m365-ent-test-environment.md)의 지침을 따릅니다.

> [!NOTE]
> 보안 격리를 사용하여 팀을 테스트할 때는 인터넷에 연결된 시뮬레이트된 인트라넷 및 AD DS(Active Directory 도메인 서비스) 포리스트의 디렉터리 동기화를 포함하여 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 보안 격리를 사용하여 팀을 테스트하고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 여기에 옵션으로 제공됩니다.

## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a>2단계: Azure AD(Azure Active Directory) 그룹 및 사용자 만들기 및 구성

이 단계에서는 가상의 조직에 대한 Azure AD 그룹 및 사용자를 만들고 구성합니다.

먼저 Azure 포털을 사용하여 보안 그룹을 만듭니다.

1. 브라우저에서 별도의 탭을 만든 다음 [https://portal.azure.com](https://portal.azure.com)에서 Azure Portal로 이동합니다. 필요한 경우 Microsoft 365 E5 평가판 또는 유료 구독에 대한 전역 관리자 계정의 자격 증명으로 로그인합니다.

2. Azure Portal에서 **Azure Active Directory > 그룹** 을 차례로 클릭합니다.

3. **그룹 - 모든 그룹** 블레이드에서 **+ 새 그룹** 을 클릭합니다.

4. **그룹** 블레이드에서:

  - **그룹 유형** 에서 **보안** 을 선택합니다.

  - **이름** 에 **C-Suite** 를 입력합니다.

  - **멤버 유형** 에서 **할당됨** 을 선택합니다.

5. **만들기** 를 클릭한 다음 **그룹** 블레이드를 닫습니다.

그런 다음 새 **C-제품군** 그룹의 구성원에게 Microsoft 365 E5 라이선스가 자동으로 할당되도록 자동 라이선스를 구성하세요.

1. Azure Portal에서 **Azure Active Directory > 라이선스 > 모든 제품** 을 차례로 클릭합니다.

2. 목록에서 **Microsoft 365 Enterprise E5** 를 선택한 다음 **할당** 을 클릭합니다.

3. **라이선스 할당** 블레이드에서 **사용자 및 그룹** 을 클릭합니다.

4. 그룹 목록에서 **C-제품군** 그룹을 선택합니다.

5. **선택** 을 클릭하고 **할당** 을 클릭합니다.

6. 브라우저에서 Azure Portal 탭을 닫습니다.

그런 다음, [Azure Active Directory PowerShell for Graph 모듈에 연결](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.

조직 이름, 사용자 위치 및 공통 암호를 입력한 다음 PowerShell 명령 프롬프트 또는 ISE(Integrated Script Environment)에서 다음 명령을 실행하여 새로운 사용자 계정을 만들고 C-제품군 그룹에 추가합니다.

```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> 여기서 공통 암호를 사용하는 것은 자동화 및 개발/테스트 환경에 대한 구성 용이성을 위한 것입니다. 프로덕션 구독에는 권장되지 않습니다.

이러한 단계에 따라 그룹 기반 라이선스가 제대로 작동하는지 확인합니다.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.

2. 브라우저의 새 **Microsoft 365 관리 센터** 탭에서 **사용자** 를 클릭합니다.

3. 사용자 목록에서 **CEO** 를 클릭합니다.

4. **CEO** 사용자 계정의 속성을 나열하는 창에서(**제품 라이선스** 에서) **Microsoft 365 Enterprise E5** 라이선스가 할당되었는지 확인합니다.

## <a name="phase-3-create-your-team"></a>3단계: 팀 만들기

이 단계에서는 시니어 리더십 팀의 구성원이 회사 전략에 대해 협업할 수 있도록 보안 격리 기능이 있는 팀을 작성하고 구성합니다.

먼저 [이 문서](../compliance/sensitivity-labels-teams-groups-sites.md)의 단계를 진행하기 전에 민감도 레이블을 사용하여 Microsoft Teams, Office 365 그룹 ​​및 SharePoint 사이트의 콘텐츠를 보호하세요.

그런 다음, 팀을 만듭니다.

1. Teams에서 앱 왼쪽에 있는 **Teams** 를 클릭한 다음, 팀 목록 아래에서 **팀 참가 또는 만들기** 를 클릭합니다.
2. **팀 만들기** 를 클릭합니다(첫 번째 카드, 왼쪽 위 모서리).
3. **처음부터 팀 만들기** 를 선택합니다.
4. **민감도** 목록에서 기본값을 유지합니다.
5. **개인 정보 보호** 에서 **비공개** 를 클릭합니다.
6. **회사 전략** 을 입력한 다음 **만들기** > **닫기** 를 클릭합니다.

다음으로, 회사 전략 그룹의 소유자에게 개인 채널 만들기를 제한합니다.

1. 팀에서 **추가 옵션** 을 클릭한 다음 **팀 관리** 를 클릭합니다.
2. **설정** 탭에서 **구성원 사용 권한** 을 확장합니다.
3. **구성원이 비공개 채널을 만들 수 있도록 허용** 확인란을 선택 취소합니다.

다음으로, 다음 설정으로 민감도 레이블을 구성해야 합니다.

- 이름을 회사 전략이라고 합니다.
- 암호화가 사용하도록 설정됩니다.
- 회사 전략 그룹은 공동 작성자 권한이 있습니다.

다음 단계를 따릅니다.

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.
2. **솔루션** 에서 **정보 보호** 를 클릭합니다.
3. **레이블 만들기** 를 클릭합니다.
4. 레이블 이름에 대한 **회사 전략** 을 입력합니다.
5. 툴팁으로 **선임 리더십 회사 전략 문서** 를 입력한 다음 **다음** 을 클릭하세요.
6. **암호화** 페이지의 **암호화** 드롭다운에서 **적용** 을 선택합니다.
7. 팀 사용 권한을 추가하려면:<br>a. **사용 권한 할당** 을 클릭합니다.<br>NS. **사용자 또는 그룹 추가** 를 클릭하고 **회사 전략** 을 선택한 다음 **추가** 를 클릭합니다.<br> c. **사용 권한 선택** 을 클릭합니다.<br> d. 드롭다운 목록에서 **공동 작성** 을 선택한 다음 **저장** 을 클릭합니다.<br>
8. **다음** 을 클릭합니다.
9. **콘텐츠 표시** 페이지에서 **다음** 을 클릭합니다.
10. **사이트 및 그룹 설정** 페이지에서 **사이트 및 그룹 설정** 을 **켜짐** 으로 설정합니다.
11. **Office 365 그룹에 연결된 팀 사이트의 개인 정보 보호** 드롭다운에서 **비공개 - 구성원만 사이트에 액세스할 수 있음** 을 선택합니다.
12. **관리되지 않는 장치** 에서 **액세스 차단** 을 선택합니다.
13. **다음** 을 클릭합니다.
14. **Office 앱에 대한 자동 레이블 지정** 페이지에서 **다음** 을 클릭합니다.
15. **제출** 을 클릭한 다음 **완료** 를 클릭합니다.

다음 단계에 따라 새 레이블을 게시합니다.

1. Microsoft 365 규정 준수 센터의 **정보 보호** 페이지에서 **레이블 정책** 탭을 선택합니다.
2. **레이블 게시** 를 클릭합니다.
3. **민감도 레이블을 게시하도록 선택** 페이지에서 **민감도 레이블을 게시하도록 선택** 을 클릭합니다.
4. **회사 전략** 을 선택한 다음 **추가** 를 클릭하세요.
5. **다음** 을 클릭합니다.
6. **사용자 및 그룹에 게시** 페이지에서 **사용자 및 그룹 선택** 을 클릭하세요.
7. **추가** 를 클릭한 다음 **회사 전략** 을 선택하세요.
8. **추가** 를 클릭한 다음 **완료** 를 클릭합니다.
9. **다음** 을 클릭합니다.
10. 정책 설정 페이지에서 **사용자가 레이블이나 하위 분류 레이블을 제거하려면 정당성을 제공해야 함** 확인란을 선택한 후 **다음** 을 클릭합니다.
11. 정책 이름에 대 한 **회사 전략** 를 입력하고 **다음** 을 클릭합니다.
12. **제출** 을 클릭한 다음 **완료** 를 클릭합니다.

**회사 전략** 레이블이 게시 된 후 사용할 수 있기까지 시간이 걸릴 수 있습니다.

그런 다음 새 라벨을 **회사 전략** 팀에 적용하고 기본 공유 링크 유형을 업데이트하여 의도하지 않은 것보다 더 많은 사용자가 파일 및 폴더를 실수로 공유할 위험을 줄입니다.

1. [SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.
2. **사이트** 에서 **활성 사이트** 를 클릭합니다.
3. **회사 전략** 사이트를 클릭합니다.
4. **정책** 탭의 **민감도** 에서 **편집** 을 클릭합니다.
5. **회사 전략** 레이블을 선택한 다음 **저장** 을 클릭합니다.
6. **정책** 탭의 **외부 공유** 에서 **편집** 을 클릭합니다.
5. **조직 내부 사용자만** 을 선택합니다.
6. **기본 공유** 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소하고 **기존 액세스가 있는 사용자** 를 선택합니다.
7. **저장** 을 클릭합니다.

그런 다음 **회사 전략** 팀에 대한 소유자 전용 사이트 공유를 구성합니다.

1. Teams에서 **회사 전략** 팀의 **일반** 탭으로 이동하세요.
2. 팀의 도구 막대에서 **파일** 을 클릭합니다.
3. 줄임표를 클릭한 다음 **SharePoint에서 열기** 를 클릭합니다.
4. 기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한** 을 클릭합니다.
5. 사이트 권한 창의 **사이트 공유** 에서 **멤버 공유 방법 변경** 을 클릭하세요.
6. **사용 권한 공유** 에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다** 를 선택하고 **저장** 을 클릭합니다.
7. **사용 권한** 과 **설정 창** 을 닫습니다.

회사 전략 그룹의 구성원으로 로그인하면 Word, Excel 및 PowerPoint의 홈 도구 모음에있는 **민감도** 옵션에 **회사 전략** 이 표시됩니다. **중요** 옵션에서 **회사 전략 레이블** 을 선택하여 레이블을 파일에 할당합니다.

다음은 회사 전략 팀에 대한 구성의 결과입니다.

![회사 전략 격리 팀 구성.](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a>다음 단계

프로덕션 배포 준비가 되면 [구성 지침](secure-teams-security-isolation.md)을 참조하세요.
