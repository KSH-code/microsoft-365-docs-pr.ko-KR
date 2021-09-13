---
title: 기본 모바일 및 보안 관리 장치에 대한 세부 정보 확인
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 조직의 Windows PowerShell 모바일 및 보안 장치에 대한 세부 정보를 얻습니다.
ms.openlocfilehash: 231eeb87d3f72ca4107c0ee6bef5bd60c713bb3f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185059"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>기본 모바일 및 보안 관리 장치에 대한 세부 정보 확인

이 문서에서는 기본 이동성 및 Windows PowerShell 설정한 조직의 장치에 대한 세부 정보를 얻을 수 있는 방법을 보여줍니다.

다음은 사용할 수 있는 장치 세부 정보의 분석입니다.

|**자세한 정보**|**PowerShell에서 찾아야 할 것**|
|:----------------|:------------------------------------------------------------------------------|
|장치가 기본 모바일 및 보안에 등록됩니다. 자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)| *isManaged* 매개   변수의 값은 다음입니다.<br/>**True**= 장치가 등록됩니다.<br/>**False**= 장치가 등록되지 않습니다. |
|장치가 장치 보안 정책을 준수합니다. 자세한 내용은 장치 보안 [정책 만들기를 참조하세요.](create-device-security-policies.md)| *isCompliant* 매개 변수의   값은 다음입니다.<br/>**True**   = 장치가 정책을 준수합니다.<br/>**False**   = 장치가 정책을 준수하지 않습니다.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="기본 Mobility and Security PowerShell 매개 변수입니다.":::

> [!NOTE]
> 이 문서의 명령 및 스크립트는 또한 에서 관리하는 모든 장치에 대한 세부 [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>시작하기 전에

이 문서에 설명된 명령 및 스크립트를 실행하려면 몇 가지를 설정해야 합니다.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>1단계: Azure Active Directory 모듈 다운로드 및 Windows PowerShell

이러한 단계에 대한 자세한 내용은 [PowerShell을 사용하여 커넥트 Microsoft 365 참조하세요.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. IT 전문가용 Microsoft Online Services Sign-In 도우미 [RTWl로](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)이동하고 로그인 도우미에 Microsoft Online Services    **다운로드를 선택합니다.**

2. 다음 단계에 따라 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 설치합니다.

    1. 관리자 수준 PowerShell 명령 프롬프트를 엽니다.

    2. `Install-Module MSOnline` 명령을 실행합니다.

    3. NuGet 공급자를 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.

    4. PSGallery에서 모듈을 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.

    5. 설치 후 PowerShell 명령 창을 닫습니다.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>2단계: 커넥트 구독에 Microsoft 365 수 있습니다.

1. 다음 Windows Azure Active Directory 모듈에서 Windows PowerShell 명령을 실행합니다.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. 자격 증명 Windows PowerShell 대화 상자에 전역 관리자 계정의 사용자 이름과 암호를 Microsoft 365 확인을 **선택합니다.**

3. 다음 명령을 실행합니다.

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>3단계: PowerShell 스크립트를 실행할 수 있는지 확인

> [!NOTE]
> PowerShell 스크립트를 실행하기로 이미 설정한 경우 이 단계를 건너뛸 수 있습니다.

Get-MsolUserDeviceComplianceStatus.ps1 실행하려면 PowerShell 스크립트 실행을 사용하도록 설정해야 합니다.

1. 데스크톱에서 Windows **를** 선택하고 시작을 Windows PowerShell. 사용자 Windows PowerShell 마우스 오른쪽 단추로 클릭한 다음 관리자 권한으로 실행 **을 선택합니다.**

2. 다음 명령을 실행합니다.

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. 메시지가 표시될 때 Y를 입력한 다음 Enter를 누를 수 있습니다.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Get-MsolDevice cmdlet을 실행하여 조직의 모든 장치에 대한 세부 정보를 표시합니다.

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.

2. 다음 명령을 실행합니다.

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

자세한 예제는  [Get-MsolDevice 를 참조합니다.](https://go.microsoft.com/fwlink/?linkid=2157939)

## <a name="run-a-script-to-get-device-details"></a>스크립트를 실행하여 장치 세부 정보 확인

먼저 스크립트를 컴퓨터에 저장합니다.

1. 다음 텍스트를 복사하여 텍스트에 메모장.

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. 파일 확장명 Windows PowerShell 사용하여 스크립트 파일로 .ps1. 예를 들어 Get-MsolUserDeviceComplianceStatus.ps1.

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>스크립트를 실행하여 단일 사용자 계정에 대한 장치 정보 얻기

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.

2. 스크립트를 저장한 폴더로 이동합니다. 예를 들어 C:\PS-Scripts에 저장한 경우 다음 명령을 실행합니다.

   ```powershell
   cd C:\PS-Scripts
   ```

3. 다음 명령을 실행하여 장치 세부 정보를 확인할 사용자를 식별합니다. 이 예제에서는 자세한 정보를 bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. 다음 명령을 실행하여 스크립트를 초기화합니다.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

정보는 사용자 데스크톱으로 Windows CSV 파일로 내보낼 수 있습니다. 추가 매개 변수를 사용하여 CSV의 파일 이름과 경로를 지정할 수 있습니다.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>스크립트를 실행하여 사용자 그룹에 대한 장치 정보 얻기

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.

2. 스크립트를 저장한 폴더로 이동합니다. 예를 들어 C:\PS-Scripts에 저장한 경우 다음 명령을 실행합니다.

   ```powershell
   cd C:\PS-Scripts
   ```

3. 다음 명령을 실행하여 장치 세부 정보를 확인할 그룹을 식별합니다. 이 예에서는 FinanceStaff 그룹의 사용자에 대한 세부 정보를 얻습니다.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. 다음 명령을 실행하여 스크립트를 초기화합니다.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

정보는 사용자 데스크톱으로 Windows CSV 파일로 내보낼 수 있습니다. 추가 매개 변수를 사용하여 CSV의 파일 이름과 경로를 지정할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 커넥트 사용 중지](/collaborate/connect-redirect)

[기본 모바일 및 보안 개요](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
