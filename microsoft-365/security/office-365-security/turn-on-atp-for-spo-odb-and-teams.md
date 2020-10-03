---
title: Office 365 ATP 사용-SharePoint, OneDrive, & 팀
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 검색 된 파일에 대 한 알림을 설정 하는 방법을 포함 하 여 SharePoint, OneDrive 및 팀에 대 한 ATP를 설정 하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c717a89492ea1160f26f26f13be6c36f348c79c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350658"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams의 ATP 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

SharePoint, OneDrive 및 Microsoft 팀의 Office 365 Advanced Threat Protection (ATP)은 악의적인 파일을 실수로 공유 하지 않도록 조직을 보호 합니다. 자세한 내용은 [SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP](atp-for-spo-odb-and-teams.md)를 참조 하세요.

이 문서에는 SharePoint, OneDrive 및 Microsoft 팀에서 ATP를 사용 하도록 설정 하 고 구성 하는 단계가 포함 되어 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com>에서 보안 및 준수 센터를 엽니다. **ATP 안전한 첨부 파일** 페이지로 바로 이동 하려면를 엽니다 <https://protection.office.com/safeattachmentv2> .

- SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 설정 하려면 보안 & 준수 센터에서 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다. 자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

- SharePoint Online PowerShell을 사용 하 여 사용자가 악성 파일을 다운로드 하지 못하도록 하려면 Azure AD에서 [전역 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 또는 [SharePoint 관리자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) 역할의 구성원 이어야 합니다.

- 조직에 대해 감사 로깅이 사용 하도록 설정 되어 있는지 확인 합니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](../../compliance/turn-audit-log-search-on-or-off.md)를 참조하세요.

- 설정이 적용 되도록 최대 30 분을 허용 합니다.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>1 단계: 보안 & 준수 센터를 사용 하 여 SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 설정 합니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동한 다음 **전역 설정을**클릭 합니다.

2. 화면에 표시 되는 **전역 설정** 에서 **SharePoint, OneDrive 및 Microsoft 팀 설정에 대 한 ATP** 설정으로 이동 합니다. ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 켜려면 오른쪽으로 설정/해제를 차례로 이동 합니다.

   작업을 마쳤으면 **저장**을 클릭합니다.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Exchange Online PowerShell을 사용 하 여 SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 설정 합니다.

PowerShell을 사용 하 여 SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 설정 하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 하 고 다음 명령을 실행 합니다.

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

구문 및 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)를 참조 하십시오.

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>2 단계: (권장) SharePoint Online PowerShell을 사용 하 여 사용자가 악성 파일을 다운로드 하지 못하도록 차단

기본적으로 사용자는 ATP에서 검색 된 악의적 파일을 열거나, 이동 하거나 복사 하거나, 공유할 수 없습니다. 그러나 악성 파일을 삭제 하 고 다운로드할 수 있습니다.

사용자가 악성 파일을 다운로드 하지 못하도록 하려면 [SharePoint Online PowerShell에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 하 고 다음 명령을 실행 합니다.

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**참고:**

- 이 설정은 사용자와 관리자 모두에 게 영향을 줍니다.
- 사용자는 여전히 악성 파일을 삭제할 수 있습니다.

구문 및 매개 변수에 대 한 자세한 내용은 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)를 참조 하십시오.

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>3 단계 (권장) 보안 & 준수 센터를 사용 하 여 검색 된 파일에 대 한 경고 정책 만들기

SharePoint, OneDrive 및 Microsoft 팀이 악성 파일을 검색할 때 사용자에 게 알려 주고 다른 관리자에 게 알리는 경고 정책을 만들 수 있습니다. 경고에 대 한 자세한 내용은 [보안 & 준수 센터에서 활동 경고 만들기](../../compliance/create-activity-alerts.md)를 참조 하십시오.

1. [보안 & 준수 센터](https://protection.office.com)에서 **알림** \> **경고 정책** 으로 이동 하거나 엽니다 <https://protection.office.com/alertpolicies> .

2. **경고 정책** 페이지에서 **새 경고 정책을**클릭 합니다.

3. **새 경고 정책** 마법사가 즉시 열립니다. **알림 이름** 설정 페이지에서 다음 설정을 구성 합니다.

   - **이름**: 고유한 이름을 입력 합니다. 예를 들어 라이브러리의 악성 파일
   - **설명**: 선택적 설명을 입력 합니다. 예를 들어 SharePoint Online, OneDrive 또는 Microsoft 팀에서 악성 파일이 검색 되 면 관리자에 게 알립니다.
   - **심각도**: 기본값을 **낮은** 값으로 선택 하거나 **중간** 또는 **높음을**선택 합니다.
   - **범주 선택**: **위협 관리**를 선택 합니다.

   작업을 마친 후 **다음**을 클릭합니다.

4. **알림 설정 만들기** 페이지에서 다음 설정을 구성 합니다.

   - **어떤 사항에 알림을 하시 겠어요?: 작업**: **검색 된 맬웨어를 파일에서**선택 합니다.
   - **알림을 어떻게 트리거하거나 요?**: **활동이 선택한 규칙과 일치 하는 시간 마다** 기본값을 유지 합니다.

   작업을 마친 후 **다음**을 클릭합니다.

5. **받는 사람 설정** 페이지에서 다음 설정을 구성 합니다.

   - **전자 메일 알림 보내기**:이 설정이 선택 되어 있는지 확인 합니다. **전자 메일 받는 사람** 상자에서 악의적인 파일을 검색할 때 알림을 받을 전역 관리자, 보안 관리자 또는 보안 판독기를 하나 이상 선택 합니다.
   - **일별 알림 제한**: 기본값은 제한을 선택 **하지 않습니다** .

   작업을 마친 후 **다음**을 클릭합니다.

6. **설정 검토** 페이지에서 설정을 검토 하 고 원하는 섹션에서 **편집** 을 클릭 하 여 변경을 수행 합니다.

   정책을 즉시 **사용할 수 있도록 설정** 하 시겠습니까? 섹션에서 기본값 **예를** 그대로 둔 채 설정 합니다.

   작업이 완료 되 면 **마침을**클릭 합니다.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>보안 & 준수 PowerShell을 사용 하 여 검색 된 파일에 대 한 경고 정책 만들기

PowerShell을 사용 하 여 이전 섹션에 설명 된 것과 동일한 경고 정책을 만드는 경우 [보안 & 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 하 고 다음 명령을 실행 합니다.

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**참고**: 기본 _심각도_ 값이 낮음을 확인 합니다. 중간 또는 높음을 지정 하려면 명령에 _심각도_ 매개 변수와 값을 포함 합니다.

구문과 매개 변수에 대 한 자세한 내용은 [신규-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)를 참조 하십시오.

### <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

- SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP가 성공적으로 설정 되었는지 확인 하려면 다음 단계 중 하나를 사용 합니다.

  - [보안 & 준수 센터](https://protection.office.com)에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 하 여 **전역 설정을**선택 하 고 **SharePoint, OneDrive 및 Microsoft 팀 설정에 대 한 ATP** 설정 값을 확인 합니다.

  - Exchange Online PowerShell에서 다음 명령을 실행 하 여 속성 설정을 확인 합니다.

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    구문과 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)를 참조 하십시오.

- 사용자가 악성 파일을 다운로드 하지 못하도록 올바르게 차단 되었는지 확인 하려면 SharePoint Online PowerShell을 열고 다음 명령을 실행 하 여 속성 값을 확인 합니다.

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  구문과 매개 변수에 대 한 자세한 내용은 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)를 참조 하십시오.

- 검색 된 파일에 대 한 경고 정책이 성공적으로 구성 되었는지 확인 하려면 다음 단계 중 하나를 사용 합니다.

  - 보안 & 준수 센터에서 **알림** \> **경고 정책** 으로 이동 하 여 \> 경고 정책을 선택 하 고 설정을 확인 합니다.

  - 보안 & 준수 센터 PowerShell에서 \<AlertPolicyName\> 경고 정책의 이름으로 바꾸고 다음 명령을 실행 하 여 속성 값을 확인 합니다.

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    구문 및 매개 변수에 대 한 자세한 내용은 [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)를 참조 하십시오.

- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report) 를 사용 하 여 SharePoint, OneDrive 및 Microsoft 팀에서 검색 된 파일에 대 한 정보를 볼 수 있습니다. 특히 **데이터 보기 기준: 콘텐츠 \> 맬웨어** 보기를 사용할 수 있습니다.
