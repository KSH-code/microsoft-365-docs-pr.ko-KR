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
description: 관리자는 SharePoint 및 OneDrive에서 Word, Excel 및 PowerPoint 파일에 민감도 레이블 지원을 사용하도록 설정할 수 있습니다.
ms.openlocfilehash: d049cdd61d2155267f4e55c612885929e27adaaa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845724"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용하도록 설정하기 전에 웹에서 Office에 민감도 [레이블을](sensitivity-labels.md) 적용할 수 없습니다. 리본의 **민감도 단추또는** 상태 표시줄에 적용된 레이블 이름이 표시되지 않습니다. 또한 데스크톱 앱을 사용하여 파일에 레이블을 지정하고 SharePoint 또는 OneDrive에 저장하는 경우, 레이블에 암호화를 적용한 경우 서비스에서 이러한 파일의 내용을 처리할 수 없습니다. 이러한 경우에는 공동 작성, eDiscovery, 데이터 손실 방지, 검색 및 기타 공동 작업 기능이 작동하지 않습니다.

SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용하도록 설정하면 이러한 모든 기능이 사용됩니다. 클라우드 기반 키로 암호화를 포함(이중 키 암호화는 사용하지 않습니다)을 포함한 민감도 레이블이 적용된 새 파일과 변경된 파일의 경우에도 민감도 레이블을 사용자에게 [표시할 뿐만 항목](double-key-encryption.md)

- Word, Excel 및 PowerPoint 파일의 경우 SharePoint는 레이블을 인식하여 암호화된 파일의 내용을 처리할 수 있습니다.

- SharePoint 또는 OneDrive에서 이러한 파일을 다운로드하거나 액세스할 때, 레이블의 모든 암호화 설정이 적용되어 파일은 어디에든 파일에 보존됩니다. 문서 보호를 위한 레이블만 사용하기 위한 사용자 지침을 제공해야 합니다. 자세한 내용은 [IRM(정보 권한 관리) 옵션 및 민감도 레이블을 참조하세요.](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)

- 사용자가 레이블이 지정되고 암호화된 파일을 SharePoint에 업로드하는 경우 해당 파일에 대한 보기 권한이 최소한 보존 및 암호화된 파일을 업로드할 수 있습니다. 예를 들어 SharePoint 외부의 파일을 열 수 있습니다. 사용자가 이러한 최소 사용 권한이 없으면 업로드에 성공하지만 SharePoint는 레이블을 인식하지 않아 파일 콘텐츠를 처리할 수 없습니다.

- 웹용 Office(Word, Excel, PowerPoint)를 사용하여 암호화를 적용하는 민감도 레이블이 지정된 Office 파일을 열고 편집합니다. 암호화에 할당된 권한이 적용됩니다. 웹용 Word에서는 이러한 문서를 편집할 때 자동 레이블 지정을 사용할 수도 있습니다.

- 외부 사용자는 게스트 계정을 사용하여 암호화로 레이블이 지정된 문서에 액세스할 수 있습니다. 자세한 내용은 외부 사용자 [에 대한 지원 및 레이블이 지정된 콘텐츠에 대한 지원을 참조하십시오.](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)

- Office 365 eDiscovery는 이러한 파일 및 DLP(데이터 손실 방지) 정책에서 이러한 파일의 콘텐츠를 지원합니다.

> [!NOTE]
> 암호화가 온-프레미스 키(종종 "자체 키 보유" 또는 HYOK라고 도명함)를 사용하여 적용되었거나 [이중 키](double-key-encryption.md)암호화를 사용하여 적용된 경우 파일 콘텐츠 처리를 위한 SharePoint 동작은 변경되지 않습니다.
>
> 또한 SharePoint 동작은 단일 Azure 기반 키를 사용하는 암호화로 레이블이 지정되는 기존 파일에 대한 SharePoint 파일을 변경하지 않습니다. SharePoint 및 OneDrive에서 Office 파일에 민감도 레이블을 사용하도록 설정한 후 이러한 파일이 새로운 기능을 이용하려면 파일이 다시 다운로드하여 업로드되거나 편집해야 합니다. 그러면 검색 결과 와서 eDiscovery 결과가 반환됩니다.

SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용하도록 [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 설정하고 면 SharePoint 및 OneDrive의 문서에 적용되는 민감도 레이블을 모니터링할 수 있는 3가지 새로운 감사 이벤트를 사용할 수 있습니다.

- **파일에 적용된 민감도 레이블**
- **파일에 변경된 민감도 레이블을 적용**
- **파일에서 제거된 민감도 레이블**

다음 비디오(오디오 없음)를 시청하여 실행 중 새 기능을 확인하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

언제든지 옵트아웃을 할 수 있습니다.[opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)

현재 SharePoint IRM(정보 권한 관리)을 사용하여 SharePoint의 문서를 보호 중인 경우 이 페이지에서 [SharePoint IRM(정보 권한 관리) 및 민감도 레이블](#sharepoint-information-rights-management-irm-and-sensitivity-labels) 섹션을 확인하세요.

## <a name="requirements"></a>요구 사항

이러한 새 기능은 [민감도 레이블에만 작동합니다.](sensitivity-labels.md) 현재 Azure Information Protection 레이블이 있는 경우 먼저 업로드한 새 파일에 대해 이러한 기능을 사용하도록 설정할 수 있도록 민감도 레이블로 마이그레이션합니다. 지침은 통합 [민감도 레이블로 Azure Information Protection 레이블을 마이그레이션하는 방법을 참조하세요.](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Windows에서 OneDrive 동기화 앱 버전 19.002.0121.0008 이상을 사용하고, Mac버전 19.002.0107.0008 이상을 Mac에서 사용하세요. 두 버전 모두 2019년 1월 28일에 출시이되어 현재 모든 링에 릴리스됩니다. 자세한 내용은 [OneDrive 릴리스 정보를 참조하세요.](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0) SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용하도록 설정하고 나면 이전 버전의 동기화 앱을 실행하는 사용자에게 이를 업데이트하라는 메시지가 표시됩니다.

## <a name="limitations"></a>제한 사항

- SharePoint에서는 이미 Azure Information Protection 레이블을 사용하여 암호화한 기존 파일에 자동으로 민감도 레이블을 적용하지 않습니다. 대신, SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용하도록 설정한 후 기능을 사용하려면 다음 작업을 완료하세요.

    1. Azure Information [Protection 레이블을 민감도](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 레이블로 마이그레이션하고 Microsoft 365 규정 준수 센터 또는 이와 동일한 레이블 관리 센터에서 게시합니다. [published them](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)

    2. 파일을 다운로드한 다음 SharePoint에 업로드합니다.

- 암호화를 적용한 레이블에 다음과 같은 암호화 구성이 있는 경우 SharePoint는 암호화된 [파일을 처리할 수 없습니다.](encryption-sensitivity-labels.md#configure-encryption-settings)

  - **사용자가 레이블을 적용하는 경우와** Word, PowerPoint 및 Excel의 확인란을 적용하는 경우 권한을 할당하도록 **사용자에게 권한을 지정하라는 메시지가** 표시됩니다. 이 설정을 "사용자 정의 권한"이라고도 합니다.
  - **콘텐츠에 대한 사용자 액세스 는** 거짓이 아닌 다른 **값으로 설정되어 있습니다.**
  - **이중 키 암호화가** 선택되어 있습니다.

  이러한 암호화 구성이 있는 레이블의 경우, 웹에서 Office의 사용자에게는 레이블이 표시되지 않습니다. 또한 이러한 암호화 설정이 이미 있는 레이블이 지정된 문서에는 새로운 기능을 사용할 수 없습니다. 예를 들어 이러한 문서는 업데이트되더라도 검색 결과에서 반환되지 않습니다.

- 사용자에게 편집 권한을 부여하는 암호화된 문서의 경우 Office 앱의 웹 버전에서는 복사가 차단될 수 없습니다.

- Azure Information Protection 문서 추적 사이트는 지원되지 않습니다.

- Office 데스크톱 앱및 모바일 앱은 암호화 레이블이 있는 파일에 대한 공동 작성을 지원하지 않습니다. 이러한 앱은 독점 편집 모드에서 레이블이 지정되고 암호화된 파일을 계속 엽니다.

- 사용자의 동기화 클라이언트에 다운로드된 파일에 이미 적용된 게시된 레이블에 대한 설정을 변경하는 경우 사용자는 해당 파일의 변경 내용을 OneDrive 동기화 폴더에 저장할 수 없습니다. 이 시나리오는 암호화로 레이블이 지정된 파일에 해당되며, 레이블 변경 내용이 암호화를 적용하지 않은 레이블에서 변경된 경우에도 적용됩니다. 사용자에는 [흰색 교차 아이콘 오류가 있는 빨간색 원이 표시되며](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)새 변경 내용을 별도의 복사본으로 저장하라는 메시지가 표시됩니다. 그 대신 파일을 닫은 후 다시 열거나 웹에서 Office를 사용할 수 있습니다.

- 레이블이 지정된 문서가 SharePoint에 업로드되고 서비스 사용자 이름의 계정을 사용하여 레이블 암호화를 적용한 경우, 웹에서 Office에서 문서를 열 수 없습니다. 예제 시나리오에는 Microsoft Cloud App Security 및 전자 메일로 Teams로 전송되는 파일이 포함됩니다.

- 사용자는 웹용 Office를 사용하는 대신, 오프라인 또는 절전 모드로 전환한 후 Word, Excel 또는 PowerPoint용 데스크톱과 모바일 앱을 사용해야 합니다. 이러한 사용자의 경우, Office 앱 세션을 다시 시작한 후 변경 내용을 저장하려고 시도하면 원본 파일을 저장하는 대신 업로드 오류 메시지가 표시됩니다.

- 다음 방법으로 암호화된 문서는 웹의 Office에서 열 수 없습니다.

  - 온-프레미스 키를 사용하는 암호화("자체 키를 보유하기" 또는 HYOK)
  - 이중 키 암호화를 사용하여 [적용된 암호화](double-key-encryption.md)
  - 예를 들어 권한 관리 보호 서식 파일을 직접 적용하여 레이블과 독립적으로 적용된 암호화입니다.

- 적용 가능한 레이블 정책에서 레이블을 제거하는 대신 SharePoint에서 문서에 적용된 레이블을 삭제할 경우 다운로드한 문서에 레이블이 지정되거나 암호화되지 않습니다. 비교하여 레이블이 지정된 문서가 SharePoint 외부에 저장되어 있는 경우 레이블이 삭제되어도 문서는 암호화된 상태로 유지됩니다. 테스트 단계에서는 레이블을 삭제할 수 있지만 프로덕션 환경에서는 레이블을 삭제하는 경우는 매우 드는 문제입니다.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>SharePoint 및 OneDrive에 대해 민감도 레이블을 사용하도록 설정하는 방법(옵트인)

Microsoft 365 준수 센터 또는 PowerShell을 사용하여 새 기능을 활성화할 수 있습니다.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>규정 준수 센터를 사용하여 민감도 레이블에 대한 지원 사용

이 옵션은 SharePoint 및 OneDrive에 대해 민감도 레이블을 사용하도록 하는 가장 쉬쉬는 방법입니다.

조직의 전역 관리자는 민감도 레이블의 모든 측면을 작성하고 관리할 수있는 모든 권한을 가지고 있습니다. 전역 관리자로 로그인하지 않은 경우 [민감도 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)을 참조하십시오.

1. [Microsoft 365 규정 준수 센터에 로그인하고](https://compliance.microsoft.com/)솔루션 정보 **보호로**  >  **이동**

    이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시**를 선택합니다.

2. Office online 파일에서 콘텐츠를 처리할 수 있는 권한을 설정하라는 메시지가 표시되면 지금 **켜기를 선택합니다.**

    ![Office Online에 민감도 레이블을 사용하도록 설정하려면 지금 설정 단추 켜기](../media/sensitivity-labels-turn-on-banner.png)

    명령은 즉시 실행되며 페이지를 다음으로 새로 고치면 메시지나 단추가 더 이상 표시되지 않습니다.

> [!NOTE]
> Microsoft 365 Multi-Geo를 사용하는 경우 PowerShell을 사용하여 모든 지리적 위치에 대해 이러한 기능을 사용하도록 해야 합니다. 자세한 내용은 다음 섹션을 참조하세요.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>PowerShell을 사용하여 민감도 레이블에 대한 지원 사용

준수 센터를 사용하는 대신, SharePoint Online PowerShell에서 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet을 사용하여 민감도 레이블에 대한 지원을 사용하도록 설정할 수 있습니다.

Microsoft 365 Multi-Geo를 사용하는 경우 PowerShell을 사용하여 모든 지리적 위치에 대해 이 지원을 사용하도록 설정해야 합니다.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>SharePoint Online 관리 셸 준비

PowerShell 명령을 실행하여 SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용하도록 설정하기 전에 SharePoint Online 관리 셸 버전 16.0.19418.12000 이상을 실행하고 있는지 확인하세요. 이미 최신 버전을 가지고 있으면 다음 절차를 진행하여 [PowerShell 명령을](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) 실행할 수 있습니다.

1. PowerShell 갤러리에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 다음 cmdlet을 실행하여 모듈을 업데이트할 수 있습니다.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 또는 Microsoft 다운로드 센터에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우에는 프로그램 **추가/제거로** 이동하고 SharePoint Online 관리 셸을 제거할 수 있습니다.

3. 웹 브라우저에서 다운로드 센터 페이지로 이동한 다음 [최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.

4. 언어를 선택한 다음 **다운로드**를 클릭합니다.

5. X64 및 x86 .msi 파일 중에서 선택합니다. 32비트 버전의 Windows는 64비트 버전이거나 32비트 버전을 실행하는 경우 x86 파일을 실행하고 있는 경우 x64 파일을 다운로드합니다. 버전을 모르는 [경우에는 현재 실행 중인 Windows 운영 체제 버전을 어떤 버전을 확인하고,](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. 파일을 다운로드한 후 실행하고 설정 마법사의 단계를 따릅니다.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>PowerShell 명령을 실행하여 민감도 레이블에 대한 지원 사용

새 기능을 사용하도록 설정하려면 *EnableAIPIntegration* [매개 변수와 함께 Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet을 사용합니다.

1. Microsoft 365에서 전역 관리자 또는 SharePoint 관리자 권한을 보유하는 회사 또는 학교 계정을 사용하여 SharePoint에 연결합니다. 자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.

    참고: Microsoft 365 Multi-Geo가 있는 경우 [Connect-SPOService와](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)함께 -Url 매개 변수를 사용하고, 지리적 위치 중 하나에 대해 SharePoint Online 관리 센터 사이트 URL을 지정합니다.

2. 다음 명령을 실행하고 Y 키를 **눌러** 확인합니다.

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```

3. Microsoft 365 Multi-Geo의 경우: 나머지 각 지리적 위치에 대해 1~ 2단계를 반복합니다.

## <a name="publishing-and-changing-sensitivity-labels"></a>민감도 레이블 게시 및 변경

SharePoint 및 OneDrive에서 민감도 레이블을 사용하는 경우 새 민감도 레이블을 게시하거나 기존 민감도 레이블을 업데이트할 때 복제 시간을 허용해야 한다는 사실에 유의하세요. 이 레이블은 암호화를 적용하는 새 레이블에 특히 중요합니다.

예를 들어 암호화를 적용하는 새 민감도 레이블을 만들고 게시하며 사용자의 데스크톱 앱에 매우 신속하게 표시됩니다. 사용자는 문서에 이 레이블을 적용한 다음 SharePoint 또는 OneDrive에 업로드합니다. 서비스에 대한 레이블 복제가 완료되지 않은 경우 업로드 시 해당 문서에 새 기능이 적용되지 않습니다. 따라서 eDiscovery에서 문서가 반환되지 않거나 eDiscovery에서 문서를 열 수 없습니다.

- 다음 변경 내용은 1시간 내에 복제됩니다. 신속하고 삭제된 민감도 레이블과 정책에 있는 레이블을 포함하는 민감도 레이블 정책 설정입니다.

- 다음 변경 내용은 24시간 내에 기존 레이블에 대한 민감도 레이블 설정의 변경 내용을 복제합니다.

복제 지연이 이제 새로운 민감도 레이블에 대해 1시간 정도 이하이므로 예제에서 시나리오를 실행할 가능성이 없습니다. 그러나 보호 장치로서 새로운 레이블을 먼저 몇 명의 테스트 사용자에게만 게시하고 한 시간 정도 기다린 다음 SharePoint 및 OneDrive에서 레이블 동작을 확인하는 것이 좋습니다. 마지막 단계로, 기존 레이블 정책에 더 많은 사용자를 추가하여 레이블을 더 많은 사용자에게 제공하거나, 기존 레이블 정책에 레이블을 추가합니다. 표준 사용자에게 는 레이블이 표시될 때 이 레이블이 이미 SharePoint 및 OneDrive에 동기화되어 있습니다.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>IRM(정보 권한 관리) 및 민감도 레이블

[IRM(정보 권한 관리)에서는](set-up-irm-in-sp-admin-center.md) 파일을 다운로드할 때 암호화 및 제한을 적용하여 목록 및 라이브러리 수준에서 파일을 보호하는 이전 기술입니다. 이 기존 보호 기술은 SharePoint 외부에 있는 동안 권한이 없는 사용자가 파일을 열지 못하도록 방지하기 위해 지정되었습니다.

비교할 때 민감도 레이블은 암호화 뿐만 이용 되는 시각적 표시(머리글, 바닥글, 워터마크) 보호 설정을 제공합니다. 암호화 설정은 사용자가 콘텐츠로 수행할 수 [있는 작업을](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) 제한하기 위한 전체 사용 권한을 지원하며, 많은 시나리오에서 동일한 민감도 [레이블이 지원됩니다.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) 워크로드 및 앱에 일관된 설정을 적용한 동일한 보호 방법을 사용하면 일관된 보호 전략이 구현됩니다.

그러나 두 보호 솔루션을 함께 사용할 수 있고 동작은 다음과 같습니다.

- 암호화를 적용하는 민감도 레이블을 사용하여 파일을 업로드하는 경우 SharePoint는 이 파일을 처리할 수 없습니다. 따라서 공동 작성, eDiscovery, DLP 및 검색이 이 파일에 작동하지 않습니다.

- 웹용 Office를 사용하여 파일에 레이블을 지정하면 레이블의 암호화 설정이 적용됩니다. 이러한 파일, 공동 작성, eDiscovery, DLP 및 검색이 지원됩니다.

- 웹에서 Office를 사용하여 레이블이 지정된 파일을 다운로드하면, 레이블이 유지되고 레이블의 암호화 설정이 IRM 제한 설정이 적용되지 않습니다.

- 민감도 레이블로 암호화되지 않은 Office 또는 PDF 파일을 다운로드하는 경우 IRM 설정이 적용됩니다.

- 사용자가 IRM을 지원하지 않는 문서를 업로드하지 못하도록 방지하는 추가 IRM 라이브러리 설정을 사용한 경우 이러한 설정을 적용합니다.

이 동작을 통해 레이블이 지정되지 않아도 모든 Office 및 PDF 파일이 다운로드되면 무단 액세스로부터 보호될 수 있습니다. 그러나 업로드되는 레이블이 지정된 파일은 새로운 기능을 사용할 수 없습니다.

## <a name="search-for-documents-by-sensitivity-label"></a>민감도 레이블별로 문서 검색

관리 속성 **InformationProtectionLabelId 관리 속성 Id를** 사용하여 SharePoint 또는 OneDrive에서 특정 민감도 레이블이 지정된 모든 문서를 찾습니다. 다음 구문을 사용합니다. `InformationProtectionLabelId:<GUID>`

예를 들어 "기밀"이라는 레이블이 지정된 모든 문서를 검색하려면 해당 레이블의 GUID는 "8faca7b8-8d20-48a3-8ea2-0f96310a848e"로 지정됩니다. 검색 상자에 다음을 입력합니다.

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

민감도 레이블에 대한 GUID를 가져오려면 [Get-Label cmdlet을 사용합니다.](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps)

1. 우선 [Office 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다.

    예를 들어 관리자로 실행하는 PowerShell 세션에서 전역 관리자 계정으로 로그인합니다.

2. 그런 후 다음 명령을 실행합니다.

    ```powershell
    Get-Label |ft Name, Guid
    ```

관리 속성을 사용하는 방법에 대한 자세한 내용은 [SharePoint에서 검색 스키마 관리를 참조하십시오.](https://docs.microsoft.com/sharepoint/manage-search-schema)

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>SharePoint 및 OneDrive에 대해 민감도 레이블을 사용하지 않도록 설정하는 방법(옵트아웃)

이러한 새 기능을 사용하지 않도록 설정하는 경우, 레이블 설정을 계속 적용하기 때문에 SharePoint 및 OneDrive에 대해 민감도 레이블을 사용하도록 설정한 후에 업로드한 파일은 레이블로 계속 보호됩니다. 이러한 새 기능을 사용하지 않도록 설정한 후 새 파일에 민감도 레이블을 적용하면 전체 텍스트 검색, eDiscovery 및 공동 작성이 더 이상 작동하지 않습니다.

이러한 새 기능을 비활성화하려면 PowerShell을 사용해야 합니다. SharePoint Online 관리 셸 및 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet을 사용하여 PowerShell을 사용하여 민감도 레이블에 대한 지원을 사용하도록 설정하는 방법에 설명된 것과 동일한 *EnableAIPIntegration* [매개 변수를 지정합니다.](#use-powershell-to-enable-support-for-sensitivity-labels) 하지만 이번에서는 매개 변수 값을 false로 설정하고 Y 키를 눌러 **다음을** 확인합니다.

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Microsoft 365 Multi-Geo를 사용하는 경우 각 지리적 위치에 대해 이 명령을 실행해야 합니다.

## <a name="next-steps"></a>다음 단계

SharePoint 및 OneDrive에서 Office 파일에 대해 민감도 레이블을 사용하도록 설정한 경우 자동 레이블 지정 정책을 사용하여 해당 파일에 자동으로 레이블을 지정하는 것이 좋습니다. 자세한 내용은 [민감도 레이블을 콘텐츠에 자동으로 적용을 참조하세요.](apply-sensitivity-label-automatically.md)
