---
title: SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 관리자는 SharePoint 및 OneDrive에서 Word, Excel 및 PowerPoint 파일에 대해 민감도 레이블 지원을 사용 하도록 설정할 수 있습니다.
ms.openlocfilehash: 5946fc193b0f96501a2f8168eef0d3e694d9cfcb
ms.sourcegitcommit: 21be88a1b38b6554ffa1bc5b743c129fe8547704
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41830982"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)

이 미리 보기를 수행 하기 전에 SharePoint 및 OneDrive에 저장 된 Office 파일에 암호화를 포함 한 민감도 레이블을 적용할 때 서비스가 이러한 파일의 콘텐츠를 처리할 수 없습니다. 이러한 상황에서는 공동 작성, eDiscovery, 데이터 손실 방지, 검색, Delve 및 기타 공동 작업 기능이 작동 하지 않습니다. 이 미리 보기에서는 클라우드 기반 키를 사용 하 여 암호화가 적용 된 경우 이러한 기능을 사용할 수 있습니다.

- Sharepoint 및 OneDrive의 Word, Excel 및 PowerPoint 파일에 적용 되는 민감도 레이블을 인식할 수 없습니다. 또한 SharePoint에서는 각 레이블에 해당 하는 설정을 적용 합니다.

- SharePoint 또는 OneDrive에서 파일을 다운로드 하면 민감도 레이블이 파일과 함께 이동 하 고 설정이 적용 됩니다.

- Word, Excel 및 PowerPoint의 웹 버전을 사용 하 여 Office 파일에 민감도 레이블을 적용 하 고 적용 된 우편물 종류를 포함 하는 파일을 열고 편집 합니다 (레이블의 사용 권한을 허용 하는 경우). 웹에서 Word를 사용 하 여 문서를 편집할 때도 자동 레이블 지정을 사용할 수 있습니다.

- Office 365 eDiscovery는 민감도 레이블이 적용 된 파일에서 전체 텍스트 검색을 지원 합니다. DLP (데이터 손실 방지) 정책은 이러한 파일의 콘텐츠를 포함 합니다.

- 세 개의 새로운 감사 이벤트를 모니터링 민감도 레이블로 사용할 수 있습니다.
  - FileSensitivityApplied 됨
  - FileSensitivityLabelChanged 됨
  - FileSensitivityLabelRemoved 됨

> [!NOTE]
> 암호화가 클라우드 기반 키와 함께 온-프레미스 키가 적용 되지 않은 경우 키 관리 토폴로지에서 흔히 "자체 키를 사용" (HYOK)으로 지칭 되는 경우에는이 미리 보기를 통해 SharePoint 동작이 변경 되지 않습니다. 

이제 Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블을 적용할 수도 있습니다. 이 별도의 미리 보기에 대 한 자세한 내용은 [사용 민감도 레이블 (Microsoft 팀, Office 365 그룹 및 SharePoint 사이트 (공용 미리 보기))](sensitivity-labels-teams-groups-sites.md)을 참조 하십시오.

언제 든 지이 미리 보기를 선택할 수 있습니다.

다음 비디오 (오디오 없음)를 시청 하 여 이러한 새로운 기능이 작동 하는지 확인 합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a>요구 사항

이러한 기능은 [민감도 레이블](sensitivity-labels.md) 에서만 작동 합니다. 현재 Azure Information Protection 레이블이 있는 경우에는 업로드 하는 새 파일에 대해 이러한 기능을 사용할 수 있도록 먼저 해당 레이블을 민감도 레이블로 마이그레이션하십시오. 자세한 내용은 [통합 민감도 레이블로 Azure Information Protection 레이블을 마이그레이션하는 방법](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 를 참조 하십시오.

이 미리 보기의 경우 Windows 및 버전 19.002.0107.0008 이상에서 OneDrive 동기화 앱 버전 19.002.0121.0008 이상을 사용 하십시오. 두 버전 모두 2019 년 1 월 28 일에 출시 되었으며 현재 모든 링으로 출시 되었습니다. 자세한 내용은 [OneDrive 릴리스 노트](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)를 참조 하세요. 이 미리 보기를 사용 하도록 설정한 후에는 이전 버전의 동기화 앱을 실행 하는 사용자에 게 업데이트 하 라는 메시지가 표시 됩니다.

## <a name="limitations"></a>제한

- 이 미리 보기를 사용 하도록 설정 하면 OneDrive 동기화 폴더에 있는 파일의 레이블을 변경 하는 사용자가 파일에 변경한 다른 내용을 저장 하지 못할 수 있습니다.  사용자에 게 [흰색 횡단면 오류가 있는 빨간색 원이](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)표시 되 고 새 변경 내용을 별도의 복사본으로 저장할지 묻는 메시지가 나타납니다.  사용자가 시작한 레이블 변경 사항 외에도, 관리자가 사용자의 동기화 클라이언트에 다운로드 된 파일에 이미 적용 되어 있는 게시 한 레이블의 설정을 변경 하는 경우에도 같은 동작이 발생할 수 있습니다.
    
    이러한 시나리오에서 작업이 손실 되지 않도록 하려면 다음 작업 중 하나를 수행 합니다.
    - 레이블을 적용 하려면 Office 앱의 웹 버전을 사용 합니다.
    - 레이블을 적용 한 후 파일을 닫고 다른 내용을 변경 하기 위해 파일을 다시 엽니다.

- SharePoint에서는 Azure Information Protection 레이블을 사용 하 여 이미 암호화 한 기존 파일에 새 레이블을 자동으로 적용 하지 않습니다. 대신이 미리 보기를 사용 하도록 설정한 후에 기능을 작동 시키려면 다음 작업을 완료 합니다.
    
    1. Azure Information Protection 레이블을 민감도 레이블로 마이그레이션하고 Microsoft 365 준수 센터 또는 레이블 관리 센터에서 게시 했는지 확인 합니다.
    
    2. 파일을 다운로드 하 여 SharePoint에 업로드 합니다.

- 암호화를 적용 한 레이블에서 암호화에 대 한 다음 구성 중 하나를 수행 하면 SharePoint에서 암호화 된 파일을 처리할 수 없습니다.
    - **사용자가 레이블을 적용할 때 사용 권한을 할당할 수 있도록** 하 고 **Word, PowerPoint 및 Excel에서 사용자에 게 사용 권한을 지정 하 라는 메시지를 표시** 합니다.
    - **콘텐츠에 대 한 사용자 액세스 만료** 는 **Never**이외의 값으로 설정 됩니다.

- 사용자에 게 편집 권한을 부여 하는 암호화 된 문서에서는 Office 앱의 웹 버전에서 복사를 차단할 수 없습니다.

- Azure Information Protection 문서 추적 사이트는 지원 되지 않습니다.

- Office 데스크톱 앱 및 모바일 앱은 공동 작성을 지원 하지 않습니다. 대신 이러한 앱은 계속 해 서 단독 편집 모드로 파일을 엽니다.

- 레이블에 암호화가 포함 되어 있으면 Microsoft Cloud App Security에서 SharePoint의 파일에 대 한 레이블 정보를 읽을 수 없습니다.

- 레이블이 지정 된 문서가 SharePoint에 업로드 되 고 레이블이 서비스 사용자 이름의 계정을 사용 하 여 암호화를 적용 한 경우에는 웹의 Office에서 해당 문서를 열 수 없습니다. 예제 시나리오에는 Microsoft Cloud App Security 및 팀별로 전자 메일로 전송 되는 파일이 포함 됩니다.

- 다음과 같은 방법으로 암호화 된 문서는 웹에서 Office에서 열 수 없습니다.
    - 온-프레미스 키를 사용 하는 암호화 ("자체 키를 포함" 또는 HYOK)
    - 예를 들어 권한 관리 보호 서식 파일을 직접 적용 하는 경우와 같이 레이블과 독립적으로 적용 되는 암호화

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>미리 보기에 대 한 SharePoint Online 관리 셸 준비

미리 보기를 사용 하도록 설정 하기 전에 SharePoint Online 관리 셸 버전 16.0.19418.12000 이상이 실행 되 고 있는지 확인 합니다. 최신 버전을 이미 사용 하 고 있는 경우 미리 보기를 사용할 수 있습니다.

1. PowerShell 갤러리에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 다음 cmdlet을 실행 하 여 모듈을 업데이트할 수 있습니다.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 또는 Microsoft 다운로드 센터에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거** 로 이동 하 여 Sharepoint Online 관리 셸을 제거할 수도 있습니다.

3. 웹 브라우저에서 다운로드 센터 페이지로 이동한 다음 [최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.

4. 언어를 선택한 다음 **다운로드**를 클릭합니다.

5. X64 및 x86 .msi 파일 중에서 선택합니다. 64 비트 버전의 Windows 또는 x86 파일 (32 비트 버전을 실행 하는 경우)을 실행 하는 경우 x64 파일을 다운로드 합니다. 알 수 없는 경우 [실행 중인 Windows 운영 체제 버전](https://support.microsoft.com/help/13443/windows-which-operating-system) 을 확인 하세요.


6. 파일을 다운로드 한 후에는 파일을 실행 하 고 설치 마법사의 단계를 따릅니다.

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Microsoft PowerShell을 사용 하 여 미리 보기 사용 (옵트인)

미리 보기를 사용 하도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.

1. Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.

2. 다음 명령을 실행합니다.

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>민감도 레이블을 만들거나 변경한 후 일정 롤업

Microsoft 365 준수 센터에서 민감도 레이블을 만들거나 변경한 후에는 스테이지에 게시 합니다. 완전히 동기화 되지 않은 레이블을 게시 하면 사용자가 파일에 레이블을 적용 하 여 SharePoint에 업로드 하는 경우 Office 앱의 웹 버전에서는 파일을 열 수 없습니다. 검색 및 eDiscovery도 파일에 대해 작동 하지 않습니다.

다음 단계를 따르는 것이 좋습니다.

1. 새 민감도 레이블을 한 명 또는 두 사람에 게 게시 합니다.

2. 초기 발행물 이후 24 시간 이상 기다립니다. 레이블이 완전히 동기화 되었는지 확인 합니다.

3. 레이블을 보다 광범위 하 게 게시 합니다.

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>Microsoft PowerShell을 사용 하 여 미리 보기 사용 안 함 (옵트아웃)

이 미리 보기를 사용 하지 않도록 설정 하는 경우 미리 보기 중에 업로드 한 파일은 계속 해 서 레이블로 보호 됩니다. 해당 설정이 계속 적용 됩니다. 미리 보기를 사용 하지 않도록 설정한 후 새 파일에 레이블을 적용 하면 전체 텍스트 검색, eDiscovery 및 공동 작성이 더 이상 작동 하지 않습니다.

미리 보기를 사용 하지 않도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.

1. Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.

2. 다음 명령을 실행합니다.

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
