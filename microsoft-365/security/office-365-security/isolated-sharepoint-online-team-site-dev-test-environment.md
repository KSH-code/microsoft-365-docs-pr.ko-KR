---
title: 격리된 SharePoint Online 팀 사이트 개발/테스트 환경
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: '요약: Microsoft 365 개발/테스트 환경의 나머지 조직과 격리된 SharePoint Online 팀 사이트를 구성합니다.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286612"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>격리된 SharePoint Online 팀 사이트 개발/테스트 환경

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 요금제 1](office-365-atp.md)
- SharePoint Online 


 **요약:** Microsoft 365 개발/테스트 환경의 나머지 조직과 격리된 SharePoint Online 팀 사이트를 구성합니다.

Microsoft 365의 SharePoint Online 팀 사이트는 공통 문서 라이브러리, OneNote 전자 필기장 및 기타 서비스를 사용하여 공동 작업을 위한 위치입니다. 대부분의 경우 부서나 조직 전체에서 광범위한 액세스 및 공동 작업을 원합니다. 그러나 일부 경우에는 소규모 사용자 그룹이 공동 작업하기 위한 액세스 및 사용 권한을 긴밀하게 제어하려는 경우도 있습니다.

SharePoint Online 팀 사이트에 대한 액세스와 사용자가 할 수 있는 작업을 SharePoint 그룹 및 권한 수준에 따라 제어합니다. 기본적으로 SharePoint Online 사이트에는 세 가지 액세스 수준이 있습니다.

- **사이트에서** 리소스를 보고 만들고 수정할 수 있는 구성원
- **소유자**- 사용 권한을 변경하는 기능을 포함하여 사이트를 완전하게 제어할 수 있습니다.
- **방문자**- 사이트에서 리소스만 볼 수 있습니다.

이 문서에서는 ProjectX라는 비밀 연구 프로젝트에 대해 격리된 SharePoint Online 팀 사이트의 구성을 단계화합니다. 액세스 요구 사항은 다음입니다.

- 프로젝트의 구성원만 사이트 및 해당 콘텐츠(문서, OneNote 전자 필기장, 페이지)에 액세스할 수 있으며 그룹 구성원을 통해 제어되는 SharePoint 권한 수준을 편집하고 볼 수 있습니다.

- 사이트에 대한 Admins 그룹의 사이트 작성자 및 구성원만 사이트 관리(사이트 수준 권한 수정 포함)를 수행할 수 있습니다.

Microsoft 365 개발/테스트 환경에서 격리된 SharePoint Online 팀 사이트를 설정하는 세 가지 단계가 있습니다.

1. Microsoft 365 개발/테스트 환경을 만들 수 있습니다.

2. ProjectX에 대한 사용자 및 그룹을 만들 수 있습니다.

3. 새 ProjectX SharePoint Online 팀 사이트를 만들고 격리합니다.

> [!TIP]
> [여기](https://aka.ms/catlgstack)를 클릭하여 One Microsoft 클라우드 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>1단계: 경량 또는 시뮬레이트된 엔터프라이즈 Microsoft 365 개발/테스트 환경 구축

최소 요구 사항을 사용하여 격리된 SharePoint Online 팀 사이트를 경량 방식으로 만들하려는 경우 간단한 기본 구성의 2, 3단계의 지침을 [따릅니다.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

시뮬레이트된 엔터프라이즈 구성에서 격리된 SharePoint Online 팀 사이트를 만들하려면 [Microsoft 365](../../enterprise/password-hash-sync-m365-ent-test-environment.md)테스트 환경에 대한 암호 해시 동기화의 지침을 따릅니다.

> [!NOTE]
> 격리된 SharePoint Online 사이트를 만들 필요는 없습니다. 여기에는 시뮬레이트된 엔터프라이즈 개발/테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. 여기서는 격리된 SharePoint Online 사이트를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 옵션으로 제공됩니다.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>2단계: 사용자 계정 및 액세스 그룹 만들기

[Office 365 PowerShell에 연결의](../../enterprise/connect-to-microsoft-365-powershell.md) 지침을 사용하여 전역 관리자 계정으로 평가판 구독에 연결합니다.

- 컴퓨터(경량 Microsoft 365 개발/테스트 환경용)

- CLIENT1 가상 컴퓨터(시뮬레이트된 엔터프라이즈 Microsoft 365 개발/테스트 환경용)

ProjectX SharePoint Online 팀 사이트에 대한 새 액세스 그룹을 만들 수 있도록 Windows Azure Active Directory 모듈에서 다음 명령을 Windows PowerShell 실행합니다.

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

조직 이름(예: contosotoycompany), 위치에 대한 2자리 국가 코드를 입력한 후 Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

**New-MsolUser** 명령이 표시될 때 잠재 고객 디자이너 계정의 생성된 암호를 기록하여 안전한 위치에 기록합니다.

Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

**New-MsolUser** 명령이 표시될 때 수석 연구원 계정의 생성된 암호를 기록해두고 안전한 위치에 기록합니다.

Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

**New-MsolUser** 명령이 표시될 때 개발 VP 계정의 생성된 암호를 기록하여 안전한 위치에 기록합니다.

다음으로, 새 액세스 그룹에 새 계정을 추가하기 위해 Windows Azure Active Directory 모듈에서 다음 PowerShell 명령을 Windows PowerShell 실행합니다.

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

결과:

- ProjectX-Members 액세스 그룹에는 수장 디자이너 및 수리 연구원 사용자 계정이 포함되어 있습니다.

- ProjectX-Admins 액세스 그룹에 평가판 구독에 대한 전역 관리자 계정이 포함되어 있습니다.

- ProjectX-Viewers 액세스 그룹에 개발 VP 사용자 계정이 포함되어 있습니다.

그림 1에서는 액세스 그룹 및 해당 구성원 자격을 보여줍니다.

**그림 1:**

![격리된 SharePoint Online 그룹 사이트의 Microsoft 365 그룹 및 구성원 자격](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>3단계: 새 ProjectX SharePoint Online 팀 사이트를 만들고 격리

ProjectX에 대한 SharePoint Online 팀 사이트를 만들 경우 다음을 합니다.

1. 로컬 컴퓨터(경량 구성) 또는 CLIENT1(시뮬레이트된 엔터프라이즈 구성)에서 브라우저를 사용하여 전역 관리자 계정을 사용하여 Microsoft 365 관리 <https://admin.microsoft.com> 센터()에 로그인합니다.

2. 타일 목록에서 **SharePoint** 를 클릭합니다.

3. 브라우저의 새 SharePoint 탭에서 **+ 사이트 만들기** 를 클릭합니다.

4. 팀 **사이트 이름에** **ProjectX를 입력합니다.** 개인 **정보 설정에서** 비공개를 **선택합니다. 구성원만** 이 사이트에 액세스할 수 있습니다.

5. 팀 **사이트 설명에서** **ProjectX에 대한 SharePoint** 사이트를 입력하고 다음을 **클릭합니다.**

6. On the **Who do you want to add?** 창에서 마친 **다음을 클릭합니다.**

7. 브라우저의 **새 ProjectX-Home** 탭에 있는 도구 모음에서 설정 아이콘을 클릭한 다음 사이트 **권한을 클릭합니다.**

8. **사이트 권한** 창에서 **고급 권한 설정** 을 클릭합니다.

9. 새 사용 **권한:** 브라우저의 프로젝트 X 탭에서 액세스 요청 **설정을 클릭합니다.**

10. 액세스  요청 설정 대화 상자에서  구성원이 사이트 및 개별 파일 및  폴더를 공유할 수 있도록 허용을 선택 취소하고 세 개의 확인란을 모두 선택 취소하도록 액세스 요청을 허용하고 확인을 **클릭합니다.**

11. 목록에서 **ProjectX 구성원을** 클릭합니다.

12. **사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.

13. 공유 **대화** 상자에서 **ProjectX-Members를** 입력하고 선택한 다음 공유를 **클릭합니다.**

14. 브라우저에서 뒤로 단추를 클릭합니다.

15. 목록에서 **ProjectX 소유자를** 클릭합니다.

16. **사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.

17. 공유 **대화** 상자에서 **ProjectX-Admins를 입력하고** 선택한 다음 공유를 **클릭합니다.**

18. 브라우저에서 뒤로 단추를 클릭합니다.

19. 목록에서 **ProjectX 방문자를** 클릭합니다.

20. **사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.

21. 공유 **대화** 상자에서 **ProjectX-Viewers를** 입력하고 선택한 다음 공유를 **클릭합니다.**

22. 브라우저에서 사용자 **및 그룹** 탭을 닫고 브라우저에서 **ProjectX-Home** 탭을 클릭한 다음 사이트 권한 창을 **닫습니다.**

권한 구성의 결과는 다음과 같습니다.

- ProjectX 구성원 SharePoint 그룹에는 ProjectX-Members 액세스 그룹(선임 디자이너 및 책임 연구원 사용자 계정만 포함) 및 ProjectX 그룹(전역 관리자 사용자 계정만 포함)만 포함되어 있습니다.

- ProjectX Owners SharePoint 그룹에는 ProjectX-Admins 액세스 그룹(전역 관리자 사용자 계정만 포함)만 포함되어 있습니다.

- ProjectX Visitors SharePoint 그룹에는 개발 ProjectX-Viewers 계정만 포함된 ProjectX-Viewers 액세스 그룹만 포함되어 있습니다.

- 구성원은 사이트 수준 권한을 수정할 수 없습니다(이 권한은 그룹 구성원만 ProjectX-Admins 수 있습니다.

- 다른 사용자 계정은 사이트 또는 해당 리소스에 액세스하거나 사이트에 대한 액세스를 요청할 수 없습니다.

그림 2에서는 SharePoint 그룹 및 구성원 자격을 보여줍니다.

**그림 2**

![격리된 SharePoint Online 그룹 사이트의 SharePoint Online 그룹 및 구성원 자격](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

이제 리드 디자이너 사용자 계정을 사용하여 액세스에 대한 설명을 하자.

1. 브라우저에서 **ProjectX-Home** 탭을 닫은 다음 브라우저에서 **Microsoft Office 홈** 탭을 클릭합니다.

2. 전역 관리자의 이름을 클릭한 다음 **로그인을 클릭합니다.**

3. 리드 디자이너 계정 이름과 암호를 사용하여 Microsoft 365 관리 센터()에 <https://admin.microsoft.com> 로그인합니다.

4. 타일 목록에서 **SharePoint** 를 클릭합니다.

5. 브라우저의 새 **SharePoint** 탭에서 검색 상자에 **ProjectX를** 입력하고 검색을 활성화한 다음 **ProjectX** 팀 사이트를 클릭합니다. ProjectX 팀 사이트의 브라우저에 새 탭이 표시됩니다.

6. 설정 아이콘을 클릭합니다. 사이트 사용 권한에 대한 **옵션은 없습니다.** 이 설정은 ProjectX-Admins 그룹의 구성원만 사이트에 대한 사용 권한을 수정할 수 있기 때문에 올바를 수 있습니다.

7. 메모장 또는 선택한 텍스트 편집기를 여십시오.

8. ProjectX 팀 사이트의 URL을 복사하여 메모장이나 텍스트 편집기에서 새 줄에 붙여 넣습니다.

9. 브라우저의 **새 ProjectX-Home** 탭에서 **문서를 클릭합니다.**

10. ProjectX 문서 폴더의 URL을 복사하여 메모장이나 텍스트 편집기에서 새 줄에 붙여 넣습니다.

11. 브라우저의 **새 ProjectX-Documents** 탭에서 Word 문서의 **> 클릭합니다.**

12. 페이지에 일부 텍스트를 입력하고 상태가 저장될 때까지 기다렸다가 **브라우저에서** 뒤로 단추를 클릭한 다음 페이지를 새로 고치십시오. Documents **폴더에** 새Document.docx **표시됩니다.**

13. 문서의Document.docx클릭한  다음 링크 **다운로드를 클릭합니다.**

14. **'Document.docx'** 공유 대화 상자의 URL을 복사하여 메모장이나 텍스트 편집기에서 새 줄에 붙여 넣은 다음 **공유 'Document.docx' 대화** 상자를 닫습니다.

15. 브라우저에서 **ProjectX-Documents** 및 **SharePoint** 탭을 닫은 다음 Microsoft Office **탭을** 클릭합니다.

16. 잠재 고객 디자이너 이름을 **클릭한** 다음 **로그인을 클릭합니다.**

이제 개발 VP 사용자 계정을 사용하여 액세스에 대한 설명을 하자.

1. 개발 VP 계정 이름과 암호를 사용하여 Microsoft 365 관리 센터()에 <https://admin.microsoft.com> 로그인합니다.

2. 타일 목록에서 **SharePoint** 를 클릭합니다.

3. 브라우저의 새 **SharePoint** 탭에서 검색 상자에 **ProjectX를** 입력하고 검색을 활성화한 다음 **ProjectX** 팀 사이트를 클릭합니다. ProjectX 팀 사이트의 브라우저에 새 탭이 표시됩니다.

4. 문서를 **클릭한** 다음 파일Document.docx **클릭합니다.**

5. In the **Document.docx** tab in your browser, try to modify the text. 이 문서는 읽기 **전용입니다.** 이는 개발 VP 사용자 계정에 사이트에 대한 보기 권한만 있기 때문에 예상됩니다.

6. 브라우저에서 **** **Document.docx, ProjectX-Documents** 및 **SharePoint 탭을** 닫습니다.

7. 홈 **Microsoft Office** 클릭하고 개발 **VP** 이름을 클릭한 다음 **로그인을 클릭합니다.**

이제 사용 권한이 없는 사용자 계정으로의 액세스를 보여보자.

1. 사용자 3 계정 이름과 암호를 사용하여 Microsoft 365 관리 <https://admin.microsoft.com> 센터()에 로그인합니다.

2. 타일 목록에서 **SharePoint** 를 클릭합니다.

3. 브라우저의 새 **SharePoint** 탭에서 검색 상자에 **ProjectX를** 입력한 다음 검색을 활성화합니다. You should see the message **Nothing here matches your search.**

4. 메모장이나 텍스트 편집기에서 ProjectX 사이트의 URL을 브라우저의 주소 표시줄에 복사하고 **Enter를 누르십시오.** 액세스 거부 **페이지가 표시됩니다.**

5. 메모장이나 텍스트 편집기에서 ProjectX Documents 폴더의 URL을 브라우저의 주소 표시줄에 복사하고 **Enter를 누르십시오.** 액세스 거부 **페이지가 표시됩니다.**

6. 메모장이나 텍스트 편집기에서 Documents.docx 파일의 URL을 브라우저의 주소 표시줄에 복사하고 Enter 를 **누르십시오.** 액세스 거부 **페이지가 표시됩니다.**

7. 브라우저에서 **SharePoint** 탭을 닫고  Microsoft Office 탭을 클릭하고 사용자 **3** 이름을 클릭한 다음 **로그인을 클릭합니다.**

이제 격리된 SharePoint Online 사이트를 추가 실험할 준비가 완료되었습니다.

## <a name="next-step"></a>다음 단계

프로덕션 환경에 격리된 SharePoint Online 팀 사이트를 배포할 준비가 되면 [격리된 SharePoint Online 팀 사이트 디자인](design-an-isolated-sharepoint-online-team-site.md)에서 단계별 디자인 고려 사항을 참조하세요.

## <a name="see-also"></a>참고 항목

[격리된 SharePoint Online 팀 사이트](isolated-sharepoint-online-team-sites.md)

[클라우드 도입 TLG(테스트 랩 가이드)](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[시뮬레이트된 엔터프라이즈 기본 구성](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[간단한 기본 구성](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[Microsoft 365 솔루션 및 아키텍처 센터](../../solutions/index.yml)