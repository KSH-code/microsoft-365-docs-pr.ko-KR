---
title: 개발/테스트 환경의 SharePoint Online 사이트 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/26/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: '요약: 개발/테스트 환경에서 중요하고 기밀인 SharePoint Online 팀 사이트를 만듭니다.'
ms.openlocfilehash: 016fd99423305e0d11272f3d25115dcffe29ecae
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631992"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>개발/테스트 환경의 SharePoint Online 사이트 보호

이 문서에서는 [SharePoint Online 사이트 및 파일 보호 솔루션](secure-sharepoint-online-sites-and-files.md)에 대한 중요하고 기밀인 SharePoint 사이트를 포함하는 개발/테스트 환경을 만드는 단계별 지침을 제공합니다.

![파일에 대한 중요하고 기밀인 SharePoint Online 사이트](../../media/sensitive-highly-confidential-sp-sites-dev-test.png)

이 개발/테스트 환경을 사용하여 생산에 이러한 유형의 팀 사이트를 배포하기 전에 특정 요구 사항에 맞게 설정을 시험해보고 세부 조정하도록 합니다.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항을 사용하여 중요하고 기밀인 팀 사이트를 간단한 방식으로 테스트하려는 경우에는 [간단한 기반 구성](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)의 지침을 따릅니다.

시뮬레이션된 엔터프라이즈에서 중요하고 기밀인 팀 사이트를 테스트하려면 [암호 해시 동기화](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)의 지침을 따릅니다.

> [!NOTE]
> 중요하고 기밀인 팀 사이트를 테스트하는 데는 Active Directory 도메인 서비스(AD DS) 포리스트를 위한 디렉터리 동기화와 인터넷에 연결된 시뮬레이션 된 인트라넷을 포함하는 시뮬레이션 된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 이는 사용자가 중요한 극비의 팀 사이트를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 여기에 옵션으로 제공됩니다.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>2단계: Azure AD(Active Directory) 그룹 및 사용자 만들기 및 구성

이 단계에서는 가상의 조직에 대한 Azure AD 그룹 및 사용자를 만들고 구성합니다.

먼저 Azure Portal을 사용하여 일반적인 조직의 두 개의 집합을 만듭니다.

1. 브라우저에 별도의 탭을 만든 다음 [https://portal.azure.com](https://portal.azure.com)에서 Azure Portal로 이동합니다. 필요한 경우 Office 365 E5 평가판 혹은 유료 구독의 전역 관리자 계정의 자격 증명으로 로그인합니다.

2. Azure Portal에서 **Azure Active Directory > 그룹**을 차례로 클릭합니다.

3. **그룹 - 모든 그룹** 블레이드에서 **+ 새 그룹**을 클릭합니다.

4. **그룹** 블레이드에서:

   - **그룹 유형**에서 **보안**을 선택합니다.

   - **이름**에 **C-Suite**를 입력합니다.

   - **멤버 유형**에서 **할당됨**을 선택합니다.

5. **만들기**를 클릭한 다음 **그룹** 블레이드를 닫습니다.

6. **마케팅 직원**이라는 새로운 그룹에 대해 3-5 단계를 반복합니다.

그런 다음 그룹 구성원에게 Microsoft 365 및 EMS 구독에 대한 라이선스를 자동으로 할당하도록 자동 라이선스를 구성합니다.

1. Azure Portal에서 **Azure Active Directory > 라이선스 > 모든 제품**을 차례로 클릭합니다.

2. 목록에서 **Microsoft 365 Enterprise E5**를 선택한 다음 **할당**을 클릭합니다.

3. **라이선스 할당** 블레이드에서 **사용자 및 그룹**을 클릭합니다.

4. 그룹 목록에서 다음을 선택합니다.

   - C-Suite

   - 마케팅 직원

5. **선택**을 클릭하고 **할당**을 클릭합니다.

6. 브라우저에서 Azure Portal 탭을 닫습니다.

그런 다음, [Azure Active Directory PowerShell for Graph 모듈에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.

조직 이름, 사용자 위치 및 공통 암호를 입력한 다음 PowerShell 명령 프롬프트 또는 ISE(Integrated Script Environment)에서 다음 명령을 실행하여 사용자 계정을 만들고 해당 그룹에 추가합니다.

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
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
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> 여기서 공통 암호를 사용하는 것은 자동화 및 개발/테스트 환경에 대한 구성 용이성을 위한 것입니다. 물론 프로덕션 구독에서는 공통 암호를 사용하지 않는 것이 좋습니다.

이러한 단계에 따라 그룹 기반 라이선스가 제대로 작동하는지 확인합니다.

1. 브라우저의 **Microsoft Office 홈** 탭에서 **관리** 타일을 클릭합니다.

2. 브라우저의 새 **Microsoft 365 관리 센터** 탭에서 **사용자**를 클릭합니다.

3. 사용자 목록에서 **CEO**를 클릭합니다.

4. **CEO** 사용자 계정의 속성을 나열하는 창에서(**제품 라이선스**에서) **Microsoft 365 Enterprise E5** 라이선스가 할당되었는지 확인합니다.

## <a name="phase-3-create-retention-labels"></a>3단계: 보존 레이블 만들기

이 단계에서는 SharePoint 팀 사이트에서 문서에 대한 보존 레이블을 만듭니다.

1. 전역 관리자 계정을 사용하여 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com)에 로그인합니다.

2. 브라우저의 **홈 - Microsoft 365 규정 준수** 탭에서 **분류 > 레이블**을 차례로 클릭합니다.

3. **보존 레이블 > 레이블 만들기**를 클릭합니다.

4. **레이블 이름 지정** 창에서 **레이블 이름 지정**에 **중요한**을 입력하고 **다음**을 클릭합니다.

5. **파일 플랜 설명자** 창에서 **다음**을 클릭합니다.

6. 필요에 따라 **레이블 설정** 창에서 **보존**을 **켜기**로 설정하고 **다음**을 클릭합니다.

7. **설정 검토** 창에서 **레이블 만들기**를 클릭합니다.

8. **극비**라고 명칭되는 추가 보존 레이블에 대해 3-7단계를 반복합니다.

9. **홈 > 레이블 ** 창에서 **레이블 게시**를 클릭합니다.

10. **게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.

11. **레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택합니다.

12. **완료**를 클릭합니다.

13. **게시할 레이블 선택** 창에서 **다음**을 클릭합니다.

14. **위치 선택** 창에서 **다음**을 클릭합니다.

15. **정책 이름 지정** 창에서 **이름**에 **예제 조직**을 입력하고 **다음**을 클릭합니다.

16. **설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.

## <a name="phase-4-create-your-team-sites"></a>4단계: 팀 사이트 만들기

이 단계에서는 예제 조직에 대한 중요하고 극비인 팀 사이트를 만들고 구성합니다.

### <a name="sensitive-team-site-for-marketing-campaigns"></a>마케팅 캠페인을 위한 중요한 팀 사이트

먼저 마케팅 그룹의 구성원이 지속적인 마케팅 캠페인을 공동으로 작업하기 위해 중요한 수준의 팀 사이트를 만듭니다.

1. **마케팅 캠페인** 이름을 사용하여 [새로운 비공개 팀 사이트를 만듭니다](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d).

2. SharePoint 팀 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.

3. **사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.

4. **사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택하고 **저장**을 클릭합니다.

그런 다음 마케팅 캠페인 SharePoint 팀 사이트의 문서 폴더를 중요 보존 레이블로 구성합니다.

1. 브라우저의 **마케팅 캠페인 - 홈** 탭에서 **문서**를 클릭합니다.

2. 설정 아이콘을 클릭한 다음, **라이브러리 설정**을 클릭합니다.

3. **권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용**을 클릭합니다.

4. **설정 - 레이블 적용**에서 **중요**를 선택하고 **저장**을 클릭합니다.

그런 다음 사용자가 마케팅 캠페인 사이트의 문서를 포함하는 중요 레이블이 있는 문서를 조직 외부와 공유할 때 사용자에게 통보를 하는 데이터 손실 방지(DLP) 정책을 구성합니다.

1. 전역 관리자 계정을 사용하여 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com/)에 로그인합니다.

2. 브라우저의 새 **Microsoft 365 규정 준수** 탭에서 **정책 > 데이터 손실 방지**를 차례로 클릭합니다.

3. **홈 > 데이터 손실 방지** 창에서 **정책 만들기**를 클릭합니다.

4. **서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.

5. **정책 이름 지정** 창의 **이름**에서 **중요 레이블 SharePoint Online 사이트**를 입력하고 **다음**을 클릭합니다.

6. **위치 선택** 창에서 **특정 위치 선택 허용**을 선택하고 **다음**을 클릭합니다.

7. 위치 목록에서 **Exchange 전자 메일**, **OneDrive 계정** 및 **팀 채팅 및 채널 메시지** 를 사용하지 않도록 설정하고 **다음**을 클릭합니다.

8. **보호할 콘텐츠 유형 사용자 지정** 창에서 **편집**을 클릭합니다.

9. **보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **보존 레이블**을 차례로 클릭합니다.

10. **보존 레이블** 창에서 **+추가**를 클릭하고, **중요** 레이블을 선택하고, **추가**를 클릭한 다음, **완료**를 클릭합니다.

11. **보호할 콘텐츠 유형 선택** 창에서 **저장**을 클릭합니다.

12. **보호할 콘텐츠 유형 사용자 지정** 창에서 **다음**을 클릭합니다.

13. **중요한 정보를 발견하면 ** 창에서 **팁 및 전자 메일 사용자 지정**을 클릭합니다.

14. **Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.

15. 텍스트 상자에 다음을 입력하거나 붙여넣습니다.

    조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.

16. **확인**을 클릭합니다.

17. **중요한 정보를 발견 시 어떠한 작업을 수행하시겠습니까?** 창에서 **다음**을 클릭합니다.

18. **정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음**을 클릭합니다.

19. **설정 검토 창**에서 **만들기**, **닫기**를 차례로 클릭합니다.

### <a name="company-strategy-team-site"></a>회사 전략 팀 사이트

먼저 수석 리더십 팀이 회사 전략을 공동으로 작업하기 위한 극비의 팀 사이트를 만듭니다.

1. **회사 전략** 이름을 사용하여 [새로운 비공개 팀 사이트를 만듭니다](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d).
2. SharePoint 팀 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.

3. **사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.

4. **사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택합니다.

5. **액세스 요청 허용**을 해제한 다음, **저장**을 클릭합니다.

그런 다음 회사 전략 SharePoint 팀 사이트의 문서 폴더를 극비 레이블로 구성합니다.

1. 브라우저의 **회사 전략 - 홈** 탭에서 **문서**를 클릭합니다.

2. 설정 아이콘을 클릭한 다음, **라이브러리 설정**을 클릭합니다.

3. **권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용**을 클릭합니다.

4. **설정 - 레이블 적용**에서 **극비**를 선택하고 **저장**을 클릭합니다.

그런 다음 회사 전략 사이트의 문서가 포함된 극비 레이블을 사용하여 조직 외부와 문서를 공유할 때 사용자를 차단하는 DLP 정책을 구성합니다.

1. 전역 관리자로 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com/)에 로그인합니다.

2. 브라우저의 새 **Microsoft 365 규정 준수** 탭에서 **정책 > 데이터 손실 방지**를 차례로 클릭합니다.

3. **홈 > 데이터 손실 방지** 창에서 **정책 만들기**를 클릭합니다.

4. **서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.

5. **정책 이름 지정** 창의 **이름**에서 **극비 레이블 SharePoint 사이트**를 입력하고 **다음**을 클릭합니다.

6. **위치 선택** 창에서 **특정 위치 선택 허용**을 선택하고 **다음**을 클릭합니다.

7. 위치 목록에서 **Exchange 전자 메일**, **OneDrive 계정** 및 **팀 채팅 및 채널 메시지** 를 사용하지 않도록 설정하고 **다음**을 클릭합니다.

8. **보호할 콘텐츠 유형 사용자 지정** 창에서 **편집**을 클릭합니다.

9. **보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **보존 레이블**을 차례로 클릭합니다.

10. **레이블** 창에서 **추가**를 클릭하고, **극비** 레이블을 선택하고, **추가**를 클릭한 다음, **완료**를 클릭합니다.

11. **보호할 콘텐츠 유형 선택** 창에서 **저장**을 클릭합니다.

12. **보호할 콘텐츠 유형 사용자 지정** 창에서 **다음**을 클릭합니다.

13. **중요한 정보를 발견하면 ** 창에서 **팁 및 전자 메일 사용자 지정**을 클릭합니다.

14. **Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.

15. 텍스트 상자에 다음을 입력하거나 붙여넣습니다.

    조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.

16. **확인**을 클릭합니다.

17. **정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음**을 클릭합니다.

18. **정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음**을 클릭합니다.

19. **설정 검토 창**에서 **만들기**, **닫기**를 차례로 클릭합니다.

[이 지침](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)을 사용하여 다음의 설정으로 중요한 레이블을 구성합니다.

- 레이블의 이름은 회사 전략입니다

- 암호화를 사용하도록 설정되어 있습니다.

- 회사 전략 그룹은 공동 작성자 권한이 있습니다.

만든 다음에 새 레이블을 게시합니다. 회사 전략 그룹의 구성원으로 로그인하는 경우 Word, Excel 및 PowerPoint의 홈 도구 모음에 있는 중요 옵션에 새 레이블이 표시됩니다. 중요 옵션에서 회사 전략 레이블을 선택하여 레이블을 파일에 할당합니다.

회사 전략 SharePoint 팀 사이트의 문서 섹션에 있는 파일에는 극비 보존 레이블이 할당되고 구성된 DLP 정책이 적용됩니다. 파일에는 또한 회사 전략 중요 레이블이 할당될 수도 있습니다.

다음은 마케팅 캠페인과 회사 전략 팀 사이트에 대한 구성의 결과입니다.

![파일에 대한 중요하고 기밀인 SharePoint Online 사이트](../../media/sensitive-highly-confidential-sp-sites-dev-test.png)

## <a name="next-step"></a>다음 단계

보호된 SharePoint Online 사이트를 프로덕션에 배포할 준비가 되면 [SharePoint Online 사이트 및 파일 보호](secure-sharepoint-online-sites-and-files.md)에서 자세한 정보와 단계별 배포 문서에 대한 링크를 참조하세요.

## <a name="see-also"></a>참고 항목

[클라우드 도입 및 하이브리드 솔루션](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)

[정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
