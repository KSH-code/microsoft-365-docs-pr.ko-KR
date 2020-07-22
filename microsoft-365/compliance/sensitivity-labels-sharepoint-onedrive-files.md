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
ms.openlocfilehash: a6826be5cccf89d3b2e48e0e37df9a9263e4a8a7
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201512"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용 하도록 설정 하기 전에 Office의 웹에 [민감도 레이블을](sensitivity-labels.md) 적용할 수 없습니다. 리본 메뉴에 **민감도** 단추가 표시 되지 않거나 상태 표시줄에 레이블 이름이 적용 됩니다. 또한 데스크톱 앱을 사용 하 여 파일에 레이블을 지정 하 고 SharePoint 또는 OneDrive에 저장 하는 경우에는 레이블에서 암호화를 적용 한 경우 이러한 파일의 내용을 처리할 수 없습니다. 이러한 상황에서는 공동 작성, eDiscovery, 데이터 손실 방지, 검색 및 기타 공동 작업 기능이 작동 하지 않습니다.

SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용 하도록 설정 하면 이러한 모든 기능이 사용 되도록 설정 됩니다. 민감도 레이블을 사용자에 게 표시 하는 것 외에, 클라우드 기반 키를 사용 하 여 암호화를 포함 하는 우편물 종류 레이블이 적용 된 새 파일과 변경 되는 파일에 대해 [이중 키 암호화](double-key-encryption.md)를 사용 하지 않습니다.

- Word, Excel 및 PowerPoint 파일의 경우 SharePoint에서 레이블을 인식 하며, 이제 암호화 된 파일의 내용을 처리할 수 있습니다.

- SharePoint 또는 OneDrive에서 이러한 파일을 다운로드 하거나 액세스할 때 레이블에서 민감도 레이블 및 모든 암호화 설정이 적용 되며 저장 되 면 어디에서 든 파일에 남아 있게 됩니다. 문서를 보호 하는 데 레이블만 사용할 수 있도록 사용자 지침을 제공 해야 합니다. 자세한 내용은 [IRM (정보 권한 관리) 옵션 및 민감도 레이블을](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)참조 하세요.

- 사용자가 레이블이 지정 되 고 암호화 된 파일을 SharePoint에 업로드 하는 경우 해당 파일에 대 한 최소한의 보기 권한이 있어야 합니다. 예를 들어 SharePoint 외부에서 파일을 열 수 있습니다. 이 최소 사용 권한이 없는 경우 업로드가 성공 하지만 SharePoint에서 레이블을 인식 하지 않으며 파일 내용을 처리할 수 없습니다.

- 웹에서 Office (Word, Excel, PowerPoint)를 사용 하 여 암호화를 적용 하는 레이블이 민감도 인 Office 파일을 열고 편집 합니다. 암호화를 통해 할당 된 사용 권한이 적용 됩니다. 웹에서 Word를 사용 하는 경우 이러한 문서를 편집할 때도 자동 레이블 기능을 사용할 수 있습니다.

- 외부 사용자는 게스트 계정을 사용 하 여 암호화로 레이블이 지정 된 문서에 액세스할 수 있습니다. 자세한 내용은 [외부 사용자에 대 한 지원 및 레이블이 지정 된 콘텐츠](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)를 참조 하세요. 

- Office 365 eDiscovery는 이러한 파일에 대 한 전체 텍스트 검색을 지원 합니다. DLP (데이터 손실 방지) 정책은 이러한 파일의 콘텐츠를 지원 합니다.

> [!NOTE]
> 온-프레미스 키를 사용 하 여 암호화를 적용 한 경우 키 관리 토폴로지에서 흔히 "사용자의 키를 사용 하 고 있습니다." (HYOK) 또는 [이중 키 암호화](double-key-encryption.md)를 사용한 경우 파일 콘텐츠 처리에 대 한 SharePoint 동작이 변경 되지 않습니다.
>
> 또한 sharepoint의 기존 레이블이 지정 되 고 암호화 된 파일에 대해서도 변경 되지 않습니다. 이러한 파일을 새 기능의 혜택을 얻으려면 다운로드 및 업로드 하거나 SharePoint 및 OneDrive에 대해 민감도 레이블을 사용 하도록 설정 하는 명령을 실행 한 후에 편집 해야 합니다. 그러면 SharePoint에서 이러한 파일을 처리할 수 있습니다. 예를 들어 검색 및 eDiscovery 결과에서 반환 됩니다.

SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용 하도록 설정한 후 SharePoint 및 OneDrive의 문서에 적용 되는 세 가지 새 [감사 이벤트](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 를 모니터링 민감도 레이블로 사용할 수 있습니다.
- **파일에 적용된 민감도 레이블**
- **파일에 변경된 민감도 레이블을 적용**
- **파일에서 제거된 민감도 레이블**

다음 비디오 (오디오 없음)를 시청 하 여 새로운 기능이 작동 하는지 확인 합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

언제 든 지 SharePoint 및 OneDrive에서 Office 파일에 대 한 민감도 레이블을 사용 하지 않도록[opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) 설정할 수 있습니다.

Sharepoint에서 IRM (정보 권한 관리)을 사용 하 여 현재 문서를 보호 하는 경우이 페이지에서 [SHAREPOINT irm (정보 권한 관리) 및 민감도 레이블](#sharepoint-information-rights-management-irm-and-sensitivity-labels) 섹션을 확인 해야 합니다. 

## <a name="requirements"></a>요구 사항

이러한 새 기능은 [민감도 레이블](sensitivity-labels.md) 에서만 작동 합니다. 현재 Azure Information Protection 레이블이 있는 경우에는 업로드 하는 새 파일에 대해 이러한 기능을 사용할 수 있도록 먼저 해당 레이블을 민감도 레이블로 마이그레이션하십시오. 자세한 내용은 [통합 민감도 레이블로 Azure Information Protection 레이블을 마이그레이션하는 방법](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 를 참조 하십시오.

Windows 및 버전 19.002.0107.0008 이상에서 OneDrive 동기화 앱 버전 19.002.0121.0008 이상을 사용 합니다. 두 버전 모두 2019 년 1 월 28 일에 출시 되었으며 현재 모든 링으로 출시 되었습니다. 자세한 내용은 [OneDrive 릴리스 노트](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)를 참조 하세요. SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용 하도록 설정 하 고 나면 이전 버전의 동기화 앱을 실행 하는 사용자에 게 업데이트 하 라는 메시지가 표시 됩니다.

## <a name="limitations"></a>제한 사항

- SharePoint에서는 이미 Azure Information Protection 레이블을 사용 하 여 암호화 한 기존 파일에 민감도 레이블을 자동으로 적용 하지 않습니다. 대신 SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용 하도록 설정 하 고 나면 기능이 작동 하도록 하려면 다음 작업을 완료 하세요.
    
    1. [Azure Information Protection 레이블을](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 민감도 레이블로 마이그레이션하고 Microsoft 365 준수 센터 또는 레이블 관리 센터에서 [게시](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 했는지 확인 합니다.
    
    2. 파일을 다운로드 한 다음 SharePoint에 업로드 합니다.

- 암호화를 적용 한 레이블에 암호화 [에 대 한 다음 구성](encryption-sensitivity-labels.md#configure-encryption-settings)중 하나가 있는 경우에는 암호화 된 파일을 처리할 수 없습니다.
    - 사용자가 **Word, PowerPoint 및 Excel에서 사용 권한을 지정할** **때 사용 권한을 할당할 수** 있습니다. 이 설정을 "사용자 정의 권한"이 라고도 합니다.
    - **콘텐츠에 대 한 사용자 액세스 만료** 는 **Never**이외의 값으로 설정 됩니다.
    - **이중 키 암호화** 가 선택 됩니다.
    
    이러한 암호화 구성이 적용 된 레이블의 경우에는 웹에서 Office 사용자에 게 레이블이 표시 되지 않습니다. 또한 이러한 암호화 설정이 이미 있는 레이블이 지정 된 문서에는 새 기능을 사용할 수 없습니다. 예를 들어 이러한 문서는 업데이트 되더라도 검색 결과에 반환 되지 않습니다.

- 사용자에 게 편집 권한을 부여 하는 암호화 된 문서에서는 Office 앱의 웹 버전에서 복사를 차단할 수 없습니다.

- Azure Information Protection 문서 추적 사이트는 지원 되지 않습니다.

- Office 데스크톱 앱 및 모바일 앱은 암호화로 레이블이 지정 된 파일에 대 한 공동 작성을 지원 하지 않습니다. 이러한 앱은 계속 해 서 레이블이 지정 되 고 암호화 된 파일을 단독 편집 모드로 엽니다.

- 사용자의 동기화 클라이언트에 다운로드 한 파일에 이미 적용 되어 있는 게시 된 레이블의 설정이 관리자가 변경 하는 경우 사용자는 해당 파일에 대 한 변경 내용을 OneDrive 동기화 폴더에 저장 하지 못할 수 있습니다. 이 시나리오는 암호화가 지정 된 파일에 적용 되며, 레이블이 암호화를 적용 하는 레이블에 암호화를 적용 하지 않은 레이블에서 변경 되는 경우에도 마찬가지입니다. 사용자에 게 [흰색 횡단면 오류가 있는 빨간색 원이](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)표시 되 고 새 변경 내용을 별도의 복사본으로 저장할지 묻는 메시지가 나타납니다. 대신 파일을 닫았다가 다시 열거나, 웹에서 Office를 사용할 수 있습니다.

- 레이블이 지정 된 문서가 SharePoint에 업로드 되 고 레이블이 서비스 사용자 이름의 계정을 사용 하 여 암호화를 적용 한 경우에는 웹의 Office에서 해당 문서를 열 수 없습니다. 예제 시나리오에는 Microsoft Cloud App Security 및 팀별로 전자 메일로 전송 되는 파일이 포함 됩니다.

- 사용자는 오프 라인으로 전환 하거나 절전 모드로 전환한 후에 저장 문제를 경험 하거나, 웹에서 Office를 사용 하는 대신 Word, Excel 또는 PowerPoint 용 데스크톱 및 모바일 앱을 사용할 수 있습니다. 이러한 사용자의 경우 Office 앱 세션을 다시 시작 하 고 변경 내용을 저장 하려고 하면 원본 파일을 저장 하는 대신 복사본을 저장 하는 옵션이 포함 된 업로드 실패 메시지가 표시 됩니다. 

- 다음과 같은 방법으로 암호화 된 문서는 웹에서 Office에서 열 수 없습니다.
    - 온-프레미스 키를 사용 하는 암호화 ("자체 키를 포함" 또는 HYOK)
    - [이중 키 암호화](double-key-encryption.md) 를 사용 하 여 적용 한 암호화 
    - 예를 들어 권한 관리 보호 서식 파일을 직접 적용 하는 경우와 같이 레이블과 독립적으로 적용 되는 암호화

- 해당 레이블 정책에서 레이블을 제거 하지 않고 SharePoint의 문서에 적용 된 레이블을 삭제 하는 경우에는 다운로드 시 문서를 레이블이 지정 되거나 암호화 되지 않습니다. 비교에서 레이블이 지정 된 문서가 SharePoint 외부에 저장 된 경우 레이블이 삭제 되 면 문서는 암호화 된 상태로 유지 됩니다. 테스트 단계에서 레이블을 삭제할 수는 있지만 프로덕션 환경에서는 레이블을 삭제 하는 것이 거의 발생 하지 않습니다.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>SharePoint 및 OneDrive (옵트인)에 대해 민감도 레이블을 사용 하도록 설정 하는 방법

Microsoft 365 준수 센터를 사용 하거나 PowerShell을 사용 하 여 새 기능을 사용 하도록 설정할 수 있습니다.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>준수 센터를 사용 하 여 민감도 레이블 지원 설정

이 옵션은 SharePoint 및 OneDrive에 민감도 레이블을 사용 하도록 설정 하는 가장 쉬운 방법입니다.

조직의 전역 관리자는 민감도 레이블의 모든 측면을 작성하고 관리할 수있는 모든 권한을 가지고 있습니다. 전역 관리자로 로그인하지 않은 경우 [민감도 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)을 참조하십시오.

1. [Microsoft 365 준수 센터](https://compliance.microsoft.com/)에 로그인 하 고 **솔루션**  >  **정보 보호** 로 이동 합니다.
    
    이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다. 

2. Office online 파일에서 콘텐츠를 처리할 수 있는 기능을 설정 하는 메시지가 표시 되 면 **지금 켜기**를 선택 합니다.
    
    ![지금 설정 단추를 클릭 하 여 Office Online에 민감도 레이블을 사용 하도록 설정](../media/sensitivity-labels-turn-on-banner.png)
    
    이 명령은 즉시 실행 되며, 다음에 페이지를 새로 고치면 메시지 또는 단추가 더 이상 표시 되지 않습니다. 

> [!NOTE]
> Microsoft 365 다중 Geo가 있는 경우 PowerShell을 사용 하 여 모든 지리적 위치에서 이러한 기능을 사용 하도록 설정 해야 합니다. 자세한 내용은 다음 섹션을 참조하세요.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell을 사용 하 여 민감도 레이블 지원 설정

준수 센터를 사용 하는 대신 SharePoint Online PowerShell에서 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet을 사용 하 여 민감도 레이블에 대 한 지원을 사용 하도록 설정할 수 있습니다. 

Microsoft 365 다중 Geo가 있는 경우 PowerShell을 사용 하 여 모든 지리적 위치에 대해이 지원을 사용 하도록 설정 해야 합니다.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>SharePoint Online 관리 셸 준비

SharePoint 및 OneDrive에서 Office 파일의 민감도 레이블을 사용 하도록 설정 하기 위해 PowerShell 명령을 실행 하기 전에 SharePoint Online 관리 셸 버전 16.0.19418.12000 이상을 실행 하 고 있는지 확인 하세요. 최신 버전이 이미 있는 경우에는 [다음 절차](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) 로 건너뛰고 PowerShell 명령을 실행할 수 있습니다.

1. PowerShell 갤러리에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 다음 cmdlet을 실행하여 모듈을 업데이트할 수 있습니다.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 또는 Microsoft 다운로드 센터에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거** 로 이동 하 여 Sharepoint Online 관리 셸을 제거할 수도 있습니다.

3. 웹 브라우저에서 다운로드 센터 페이지로 이동한 다음 [최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.

4. 언어를 선택한 다음 **다운로드**를 클릭합니다.

5. X64 및 x86 .msi 파일 중에서 선택합니다. 64 비트 버전의 Windows 또는 x86 파일 (32 비트 버전을 실행 하는 경우)을 실행 하는 경우 x64 파일을 다운로드 합니다. 알 수 없는 경우 [실행 중인 Windows 운영 체제 버전](https://support.microsoft.com/help/13443/windows-which-operating-system) 을 확인 하세요.

6. 파일을 다운로드 한 후에는 파일을 실행 하 고 설치 마법사의 단계를 따릅니다.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell 명령을 실행 하 여 민감도 레이블 지원을 사용 하도록 설정

새 기능을 사용 하도록 설정 하려면 *EnableAIPIntegration* 매개 변수와 함께 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet을 사용 합니다.

1. Microsoft 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.
    
    참고: Microsoft 365 다중 위치를 사용 하는 경우에는 [connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)에-Url 매개 변수를 사용한 다음 지리적 위치 중 하나에 대 한 SharePoint Online 관리 센터 사이트 Url을 지정 합니다.

2. 다음 명령을 실행 하 고 **Y** 를 눌러 확인 합니다.

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. Microsoft 365 다중 사용자의 경우 남은 각 지리적 위치에 대해 1 ~ 2 단계를 반복 합니다.

## <a name="publishing-and-changing-sensitivity-labels"></a>민감도 레이블 게시 및 변경

SharePoint 및 OneDrive에서 민감도 레이블을 사용 하는 경우 새 민감도 레이블을 게시 하거나 기존 민감도 레이블을 업데이트할 때 복제 시간을 허용 해야 합니다. 이는 암호화를 적용 하는 새 레이블에서 특히 중요 합니다.

예를 들어, 암호화를 적용 하 고 사용자의 데스크톱 앱에 매우 빠르게 표시 되는 새 민감도 레이블을 만들고 게시 합니다. 사용자가 문서에이 레이블을 적용 한 다음 SharePoint 또는 OneDrive에 업로드 합니다. 서비스에 대해 레이블 복제가 완료 되지 않은 경우 업로드 시 해당 문서에 새 기능이 적용 되지 않습니다. 따라서 문서가 검색 또는 eDiscovery에 반환 되지 않으며, 웹의 Office에서 문서를 열 수 없습니다.

- 다음 변경 내용은 1 시간 내에 복제 되며, 새 민감도 레이블 및 민감도 레이블 정책 설정에 따라 정책에 포함 됩니다.

- 24 시간 이내에 다음과 같은 변경 사항이 복제 됩니다.

이제 새 민감도 레이블에 대 한 복제 지연은 1 시간 이므로이 예제의 시나리오에서는 실행 되지 않을 수 있습니다. 하지만 보호 수단으로는 소수의 테스트 사용자 에게만 새 레이블을 게시 하 고 한 시간 정도 기다린 다음 SharePoint 및 OneDrive에서 레이블 동작을 확인 하는 것이 좋습니다. 마지막 단계로 기존 레이블 정책에 더 많은 사용자를 추가 하 여 더 많은 사용자가 레이블을 사용할 수 있도록 하거나 표준 사용자의 기존 레이블 정책에 레이블을 추가 합니다. 표준 사용자가 레이블을 볼 때 이미 SharePoint 및 OneDrive와 동기화 되었습니다.


## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint IRM (정보 권한 관리) 및 민감도 레이블

[SHAREPOINT IRM (정보 권한 관리)](set-up-irm-in-sp-admin-center.md) 은 파일을 다운로드할 때 암호화 및 제한을 적용 하 여 목록 및 라이브러리 수준에서 파일을 보호 하는 데 사용할 수 있는 이전 기술입니다. 이 이전 보호 기술은 SharePoint 외부에서 권한이 없는 사용자가 파일을 열지 못하도록 하기 위한 것입니다.

비교에서 민감도 레이블은 암호화와 함께 시각적 표시 (머리글, 바닥글, 워터 마크)의 보호 설정을 제공 합니다. 암호화 설정은 전체 [사용 권한](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) 범위를 지원 하 여 사용자가 콘텐츠를 사용 하 여 수행할 수 있는 작업을 제한 하 고, [여러 시나리오](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)에서 동일한 민감도 레이블을 지원 합니다. 여러 작업 및 앱 간에 일관 된 설정과 동일한 보호 방법을 사용 하면 일관성 있는 보호 전략이 적용 됩니다.

그러나 두 보호 솔루션을 함께 사용할 수 있으며 동작은 다음과 같습니다. 

- 암호화를 적용 하는 민감도 레이블을 사용 하 여 파일을 업로드 하는 경우 SharePoint에서이 파일에 대해 공동 작업, eDiscovery, DLP 및 검색이 작동 하지 않도록이 파일을 처리할 수 없습니다.

- 웹에서 Office를 사용 하 여 파일에 레이블을 지정 하면 레이블에서 암호화 설정이 적용 됩니다. 이러한 파일에 대해 공동 작성, eDiscovery, DLP 및 검색이 지원 됩니다.

- 웹에서 Office를 사용 하 여 레이블이 지정 된 파일을 다운로드 하는 경우 레이블이 보존 되 고 해당 레이블의 모든 암호화 설정이 IRM 제한 설정이 아닌 적용 됩니다.

- 민감도 레이블로 암호화 되지 않은 Office 또는 PDF 파일을 다운로드 하는 경우 IRM 설정이 적용 됩니다.

- 사용자가 IRM을 지원 하지 않는 문서를 업로드 하지 못하게 하는 추가 IRM library 설정이 사용 하도록 설정 된 경우에는 이러한 설정이 적용 됩니다.

이 동작을 사용 하면 레이블이 없는 경우에도 모든 Office 및 PDF 파일을 다운로드 한 경우 무단으로 액세스 하지 못하도록 보호할 수 있습니다. 그러나 레이블이 지정 된 파일은 새로운 기능을 통해 얻을 수 없습니다.

## <a name="search-for-documents-by-sensitivity-label"></a>민감도 레이블을 기준으로 문서 검색

관리 속성 **InformationProtectionLabelId** 를 사용 하 여 특정 민감도 레이블이 있는 SharePoint 또는 OneDrive의 모든 문서를 찾을 수 있습니다. 다음 구문을 사용 합니다.`InformationProtectionLabelId:<GUID>`

예를 들어 "기밀" 이라는 레이블이 지정 된 모든 문서를 검색 하 고 해당 레이블에 GUID가 "8faca7b8-8d20-48a3-8ea2-0f96310a848e" 인 경우 검색 상자에 다음을 입력 합니다.

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

민감도 레이블의 Guid를 가져오려면 [get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet을 사용 합니다.
    
1. 우선 [Office 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다. 
    
    예를 들어 관리자로 실행하는 PowerShell 세션에서 전역 관리자 계정으로 로그인합니다.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. 그리고 나 서 다음 명령을 실행 합니다.
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

관리 속성을 사용 하는 방법에 대 한 자세한 내용은 [SharePoint에서 검색 스키마 관리](https://docs.microsoft.com/sharepoint/manage-search-schema)를 참조 하세요.

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>SharePoint 및 OneDrive에 대해 민감도 레이블을 사용 하지 않도록 설정 하는 방법 (옵트아웃)

이러한 새 기능을 사용 하지 않도록 설정 하는 경우 레이블 설정이 계속 적용 되므로 SharePoint 및 OneDrive의 민감도 레이블을 사용 하도록 설정한 후 업로드 한 파일은 레이블로 계속 보호 됩니다. 이러한 새 기능을 사용 하지 않도록 설정 하 고 나면 새 파일에 민감도 레이블을 적용할 때 전체 텍스트 검색, eDiscovery 및 공동 작업은 더 이상 작동 하지 않습니다.

이러한 새 기능을 사용 하지 않도록 설정 하려면 PowerShell을 사용 해야 합니다. SharePoint Online 관리 셸 및 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet을 사용 하 여 [민감도 레이블 지원 사용](#use-powershell-to-enable-support-for-sensitivity-labels) 섹션에 설명 된 것과 동일한 *EnableAIPIntegration* 매개 변수를 지정 합니다. 하지만 이번에는 매개 변수 값을 false로 설정 하 고 **Y** 를 눌러 확인 합니다.

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Microsoft 365 다중 지역에 있는 경우 각 지리적 위치에 대해이 명령을 실행 해야 합니다.

## <a name="next-steps"></a>다음 단계

SharePoint 및 OneDrive에서 Office 파일에 대 한 민감도 레이블을 사용 하도록 설정한 후 자동 레이블 지정 정책을 사용 하 여 이러한 파일에 자동으로 레이블을 지정 하는 것이 좋습니다. 자세한 내용은 [콘텐츠에 민감도 레이블 자동 적용](apply-sensitivity-label-automatically.md)을 참조 하십시오.