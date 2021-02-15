---
title: 기본 이동성 및 보안 관리 장치에 대한 세부 정보 확인
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
description: 이 Windows PowerShell 사용하여 조직의 기본 이동성 및 보안 장치에 대한 세부 정보를 얻을 수 있습니다.
ms.openlocfilehash: 7c6a0365dfd573377c3675bbcee8ee8280e33816
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876891"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>기본 이동성 및 보안 관리 장치에 대한 세부 정보 확인

이 문서에서는 기본 이동성 및 Windows PowerShell 설정한 조직의 장치에 대한 세부 정보를 표시하는 방법을 보여줍니다.

다음은 사용할 수 있는 장치 세부 정보의 분석입니다.

|**자세한 정보**|**PowerShell에서 찾아야 할 것**|
|:----------------|:------------------------------------------------------------------------------|
|장치가 기본 이동성 및 보안에 등록됩니다. 자세한 내용은 기본 이동성 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)|isManaged 매개 *변수의 값은*   다음입니다.<br/>**True**= 장치가 등록됩니다.<br/>**False**= 장치가 등록되지 않습니다. |
|장치가 장치 보안 정책을 준수합니다. 자세한 내용은 장치 보안 [정책 만들기를 참조하세요.](create-device-security-policies.md)| *isCompliant* 매개 변수의   값은 다음입니다.<br/>**True**   = 장치가 정책을 준수합니다.<br/>**False**   = 장치가 정책을 준수하지 않습니다.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="기본 Mobility and Security PowerShell 매개 변수":::

>[!NOTE]
>이 문서의 명령 및 스크립트는 Microsoft Intune에서 관리하는 장치에 대한 세부 [정보도 반환합니다.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>시작하기 전에

이 문서에 설명된 명령 및 스크립트를 실행하려면 몇 가지를 설정해야 합니다.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>1단계: Azure Active Directory 모듈을 다운로드하여 Windows PowerShell

이러한 단계에 대한 자세한 내용은 [PowerShell을 사용하여 Microsoft 365에 연결합니다.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)

1. IT [Microsoft Online Services Sign-In RTWl용](https://www.microsoft.com/download/details.aspx?id=41950)Microsoft Online Services 도우미로    **이동하여 다운로드를 선택합니다.**   

2. 다음 단계에 따라 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 설치합니다.

    1. 관리자 수준 PowerShell 명령 프롬프트를 엽니다.  

    2. Install-Module MSOnline 명령을 실행합니다.

    3. NuGet 공급자를 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.

    4. PSGallery에서 모듈을 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.

    5. 설치 후 PowerShell 명령 창을 닫습니다.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>2단계: Microsoft 365 구독에 연결

1. 다음 Windows Azure Active Directory 모듈에서 Windows PowerShell 명령을 실행합니다.  

    $UserCredential = Get-Credential

2. 자격 증명 Windows PowerShell 대화 상자에 Microsoft 365 전역 관리자 계정의 사용자 이름과 암호를 입력한 다음 확인을 **선택합니다.**

3. 다음 명령을 실행합니다.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>3단계: PowerShell 스크립트를 실행할 수 있는지 확인

>[!NOTE]
>PowerShell 스크립트를 실행하기 위해 이미 설정한 경우 이 단계를 건너뛸 수 있습니다.

Get-MsolUserDeviceComplianceStatus.ps1 실행하려면 PowerShell 스크립트를 실행하도록 설정해야 합니다.

1. Windows 바탕 화면에서 **** 시작을 선택한 다음 시작을 Windows PowerShell. 이 Windows PowerShell 마우스 오른쪽 단추로 클릭한 다음 **관리자 권한으로 실행을 선택합니다.**

2. 다음 명령을 실행합니다.

    Set-ExecutionPolicy RemoteSigned

3. 메시지가 표시될 때 Y를 입력한 다음 Enter를 누를 수 있습니다.

**Get-MsolDevice cmdlet을 실행하여 조직의 모든 장치에 대한 세부 정보를 표시합니다.**

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.  

2. 다음 명령을 실행합니다.

    Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_를 사용합니다. RegisteredOwners.Count -gt 0}

자세한 예는  [Get-MsolDevice를 참조합니다.](https://go.microsoft.com/fwlink/?linkid=841721)

## <a name="run-a-script-to-get-device-details"></a>스크립트를 실행하여 장치 세부 정보 확인

먼저 스크립트를 컴퓨터에 저장합니다.

1. 다음 텍스트를 복사하여 메모장에 붙여 넣습니다.  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  반환 $resultObject
    

31.  }
    

33.  ($users. Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach($d $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If($export)
    

64.  {
    

65.  $result | Export-Csv -path($exportPath + " + \" $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  파일 확장명 .ps1을 Windows PowerShell 스크립트 파일로 저장합니다. 예를 들어 Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>스크립트를 실행하여 단일 사용자 계정에 대한 장치 정보 얻기

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.
    
2. 스크립트를 저장한 폴더로 이동합니다. 예를 들어 C:\PS-Scripts에 저장한 경우 다음 명령을 실행합니다.
    
    cd C:\PS-Scripts

3. 다음 명령을 실행하여 장치 세부 정보를 얻을 사용자를 식별합니다. 이 예제에서는 이 예제의 세부 정보를 bar@example.com.
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. 다음 명령을 실행하여 스크립트를 초기화합니다.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

정보는 CSV 파일로 Windows 데스크톱으로 내보낼 수 있습니다. 추가 매개 변수를 사용하여 CSV의 파일 이름과 경로를 지정할 수 있습니다.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>스크립트를 실행하여 사용자 그룹에 대한 장치 정보 얻기

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.
    
2. 스크립트를 저장한 폴더로 이동합니다. 예를 들어 C:\PS-Scripts에 저장한 경우 다음 명령을 실행합니다.   

    cd C:\PS-Scripts

3. 다음 명령을 실행하여 장치 세부 정보를 확인할 그룹을 식별합니다. 이 예에서는 FinanceStaff 그룹의 사용자에 대한 세부 정보를 얻습니다. 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. 다음 명령을 실행하여 스크립트를 초기화합니다.   

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

정보는 CSV 파일로 Windows 데스크톱으로 내보낼 수 있습니다. 추가 매개 변수를 사용하여 CSV의 파일 이름과 경로를 지정할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft Connect 사용 중지](https://docs.microsoft.com/collaborate/connect-redirect)

[기본 모바일 및 보안 개요](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)