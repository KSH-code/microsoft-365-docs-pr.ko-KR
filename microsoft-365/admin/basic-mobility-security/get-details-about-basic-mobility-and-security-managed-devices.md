---
title: 기본 이동성 및 보안 관리 장치에 대 한 세부 정보 보기
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
description: Windows PowerShell을 사용 하 여 조직의 기본 이동성 및 보안 장치에 대 한 세부 정보를 확인할 수 있습니다.
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337003"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>기본 이동성 및 보안 관리 장치에 대 한 세부 정보 보기

이 문서에서는 Windows PowerShell을 사용 하 여 기본 이동성 및 보안을 위해 설정한 조직의 장치에 대 한 세부 정보를 가져오는 방법을 설명 합니다.

여기에는 사용자가 사용할 수 있는 장치 세부 정보에 대 한 분석 과정이 나와 있습니다.

|**자세한 정보**|**PowerShell에서 조회할 작업**|
|:----------------|:------------------------------------------------------------------------------|
|장치가 기본 이동성 및 보안에 등록 되어 있습니다. 자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device-using-basic-mobility-and-security.md) 을 참조 하세요.| *IsManaged*   매개 변수의 값은 다음과 같습니다.<br/>**True**= 디바이스가 등록 됩니다.<br/>**False**= 디바이스가 등록 되지 않음 |
|장치가 장치 보안 정책을 준수 합니다. 자세한 내용은 [장치 보안 정책 만들기](create-device-security-policies-in-basic-mmobility-and-security.md) 를 참조 하세요.| *Iscompliant*   매개 변수의 값은 다음과 같습니다.<br/>**True**   = 장치가 정책을 준수 합니다.<br/>**False**   = 장치가 정책을 준수 하지 않습니다.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="기본 모바일 및 보안 PowerShell 매개 변수":::

>[!NOTE]
>이 문서의 명령 및 스크립트는 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)에서 관리 되는 모든 장치에 대 한 세부 정보를 반환 합니다.

## <a name="before-you-begin"></a>시작하기 전에

이 문서에서 설명 하는 명령과 스크립트를 실행 하려면 몇 가지 사항을 설정 해야 합니다.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>1 단계: Windows PowerShell 용 Azure Active Directory 모듈 다운로드 및 설치

이러한 단계에 대 한 자세한 내용은 [PowerShell을 사용 하 여 Microsoft 365에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조 하십시오.

1.  [IT 전문가 용 Microsoft Online Services 로그인 도우미](https://www.microsoft.com/download/details.aspx?id=41950)로 이동 하 여    **Microsoft online services 로그인 도우미에**대 한 다운로드를 선택 합니다.   

2. 다음 단계에 따라 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 설치합니다.   

    1. 관리자 수준 PowerShell 명령 프롬프트를 엽니다.  

    2. Install-Module MSOnline 명령을 실행합니다.
    
    3. NuGet 공급자를 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.   

    4. PSGallery에서 모듈을 설치할지 묻는 메시지가 표시되면 Y를 입력하고 Enter 키를 누릅니다.   

    5. 설치 후 PowerShell 명령 창을 닫습니다.
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>2 단계: Microsoft 365 구독에 연결

1. Windows PowerShell 용 Windows Azure Active Directory 모듈에서 다음 명령을 실행 합니다.  

    $UserCredential = Get-Credential

2. Windows PowerShell 자격 증명 요청 대화 상자에서 Microsoft 365 전역 관리자 계정의 사용자 이름 및 암호를 입력 한 다음 **확인**을 선택 합니다.
    
3. 다음 명령을 실행합니다.
    
    Connect-msolservice-자격 증명 $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>3 단계: PowerShell 스크립트를 실행할 수 있는지 확인

>[!NOTE]
>PowerShell 스크립트를 실행 하도록 이미 설정 되어 있는 경우에는이 단계를 건너뛸 수 있습니다.

Get-MsolUserDeviceComplianceStatus.ps1 스크립트를 실행 하려면 PowerShell 스크립트를 실행 하도록 설정 해야 합니다.

1. Windows 바탕 화면에서 **시작**을 선택 하 고 windows PowerShell을 입력 합니다. Windows PowerShell을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.

2. 다음 명령을 실행합니다.
    
    ExecutionPolicy RemoteSigned

3. 메시지가 표시 되 면 Y를 입력 한 다음 enter 키를 누릅니다.
    
**MsolDevice cmdlet을 실행 하 여 조직의 모든 장치에 대 한 세부 정보를 표시 합니다.**

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.  

2. 다음 명령을 실행합니다.
    
    MsolDevice-All-ReturnRegisteredOwners | 여기에서-개체 {$ _. RegisteredOwners-gt 0}

자세한 예는  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)를 참조 하세요.

## <a name="run-a-script-to-get-device-details"></a>스크립트를 실행 하 여 장치 세부 정보 가져오기

먼저, 스크립트를 컴퓨터에 저장 합니다.

1. 다음 텍스트를 복사 하 여 메모장에 붙여 넣습니다.  

2.  a
    

3.  [PSObject []] $users = @ (),
    

4.  [스위치] $export
    

5.  [String] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ".csv",
    

6.  [String] $exportPath = [Environment]:: GetFolderPath ("Desktop")
    

7.  )
    

9.  [System.object] $script: schema = @ {
    

11.  DeviceId = ' '
    

12.  DeviceOSType = ' '
    

13.  DeviceOSVersion = ' '
    

14.  DeviceTrustLevel = ' '
    

15.  DisplayName = ' '
    

16.  IsCompliant = ' '
    

17.  IsManaged = ' '
    

18.  ApproximateLastLogonTimestamp = ' '
    

19.  DeviceObjectId = ' '
    

20.  RegisteredOwnerUpn = ' '
    

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  함수 createResultObject
    

26.  {
    

28.  [PSObject] $resultObject = 새 개체-TypeName PSObject-속성 $script: schema
    

30.  반환 $resultObject
    

31.  }
    

33.  If ($users Count-eq 0)
    

34.  {
    

35.  $users = Get-msoluser
    

36.  }
    

38.  [PSObject []] $result = foreach ($users의 $u)
    

39.  {
    

41.  [PSObject] $devices = msoldevice-RegisteredOwnerUpn $u. UserPrincipalName
    

42.  foreach ($devices의 $d)
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult. DeviceId = $d. DeviceId
    

46.  $deviceResult DeviceOSType = $d DeviceOSType
    

47.  $deviceResult DeviceOSVersion = $d DeviceOSVersion
    

48.  $deviceResult DeviceTrustLevel = $d DeviceTrustLevel
    

49.  $deviceResult DisplayName = $d. DisplayName
    

50.  $deviceResult. IsCompliant = $d GraphDeviceObject. IsCompliant
    

51.  $deviceResult IsManaged = $d. GraphDeviceObject
    

52.  $deviceResult DeviceObjectId = $d. ObjectId
    

53.  $deviceResult RegisteredOwnerUpn = $u UserPrincipalName
    

54.  $deviceResult RegisteredOwnerObjectId = $u. ObjectId
    

55.  $deviceResult RegisteredOwnerDisplayName = $u. DisplayName
    

56.  $deviceResult ApproximateLastLogonTimestamp = $d ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-.Csv 경로 ($exportPath + " \" + $exportFileName)-NoTypeInformation
    

66.  }
    

67.  알리게
    

68.  {
    

69.  $result
    

70.  }
    

71.  파일 확장명. ps1;을 사용 하 여 Windows PowerShell 스크립트 파일로 저장 합니다. 예를 Get-MsolUserDeviceComplianceStatus.ps1 합니다.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>스크립트를 실행 하 여 단일 사용자 계정에 대 한 장치 정보 가져오기

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.
    
2. 스크립트를 저장 한 폴더로 이동 합니다. 예를 들어 C:\PS-Scripts에 저장 한 경우 다음 명령을 실행 합니다.
    
    cd C:\PS-Scripts

3. 다음 명령을 실행 하 여 장치 세부 정보를 가져올 사용자를 식별 합니다. 이 예에서는 bar@example.com에 대 한 세부 정보를 가져옵니다.
    
    $u = Get-msoluser-UserPrincipalName bar@example.com

4. 다음 명령을 실행 하 여 스크립트를 시작 합니다.

    .\Get-MsolUserDeviceComplianceStatus.ps1-사용자 $u-내보내기

정보는 Windows 데스크톱에 CSV 파일로 내보내집니다. 추가 매개 변수를 사용 하 여 CSV의 파일 이름과 경로를 지정할 수 있습니다.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>스크립트를 실행 하 여 사용자 그룹에 대 한 장치 정보 가져오기

1. Windows PowerShell용 Microsoft Azure Active Directory 모듈을 엽니다.
    
2. 스크립트를 저장 한 폴더로 이동 합니다. 예를 들어 C:\PS-Scripts에 저장 한 경우 다음 명령을 실행 합니다.   

    cd C:\PS-Scripts

3. 다음 명령을 실행 하 여 장치 세부 정보를 가져올 그룹을 식별 합니다. 이 예에서는 FinanceStaff 그룹의 사용자에 대 한 세부 정보를 가져옵니다. 

    $u = MsolGroupMember-SearchString "FinanceStaff" | % {Get-Get-msoluser-ObjectId $ _를 사용 합니다. Id

4. 다음 명령을 실행 하 여 스크립트를 시작 합니다.   

    .\Get-MsolUserDeviceComplianceStatus.ps1-사용자 $u-내보내기

정보는 Windows 데스크톱에 CSV 파일로 내보내집니다. 추가 매개 변수를 사용 하 여 CSV의 파일 이름과 경로를 지정할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft Connect가 만료 되었습니다.](https://docs.microsoft.com/collaborate/connect-redirect)

[기본 이동성 및 보안 개요](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)