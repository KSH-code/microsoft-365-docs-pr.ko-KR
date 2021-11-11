---
title: 중요한 정보 원본 테이블 파일 새로 고침
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 중요한 정보 원본 테이블 파일을 새로 고침합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fd083b798785f0dbfca8603f8b7bc28fece6004e
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914850"
---
# <a name="refresh-your-sensitive-information-source-table-file"></a>중요한 정보 원본 테이블 파일 새로 고침 

24시간마다 중요한 정보 데이터베이스를 두 번 새로 고칠 수 있습니다. 중요한 정보 원본 테이블을 다시 해시하고 업로드해야 합니다.

1. 중요한 데이터를 앱으로 다시 내보내고 Microsoft Excel.tsv 형식 또는 파이프(.csv) 구분된 형식으로 파일을 | 저장합니다. 이전에 파일을 해시하고 업로드할 때 사용한 파일 이름과 위치를 동일하게 유지하십시오. 중요한 [데이터를](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type) 내보내 올바른 형식으로 내보내는 데 대한 자세한 내용은 정확한 데이터 일치 기반의 중요한 정보 유형에 대한 원본 데이터 내보내기를 참조하세요.

      > [!NOTE]
      > 중요한 정보 원본 테이블 파일의 구조(필드 이름)가 변경되지 않은 경우 데이터를 새로 고칠 때 데이터베이스 체계 파일을 변경할 필요가 없습니다. 하지만 변경해야 하는 경우 데이터베이스 스키마와 규칙 패키지를 적절하게 편집해야 합니다. 자세한 내용은 [Manage your exact data match schema(정확한](sit-use-exact-data-manage-schema.md#manage-your-exact-data-match-schema) 데이터 일치를 관리하세요.)를 참조하여 해당 스마마를 편집하거나 제거하는 단계를 참조하세요. EDM SIT/규칙 패키지를 편집하거나 제거하는 단계는 정확한 데이터 일치 중요한 정보 [유형/규칙](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) 패키지 만들기를 참조하세요.

2. [해시의](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) 절차를 수행하고 중요한 정보 유형과 일치하는 중요한 정보 유형에 대한 중요한 정보 원본 테이블을 업로드하여 중요한 정보 테이블 원본 파일을 업로드합니다.

2. 작업 [스케줄러를](/windows/desktop/TaskSchd/task-scheduler-start-page) 사용하여 해시를 자동화하고 중요한 정보 유형과 일치하는 정확한 데이터에 대한 중요한 정보 원본 테이블을 [업로드할 수](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) 있습니다. 다음과 같은 여러 방법을 사용하여 작업을 예약할 수 있습니다.

   |메서드|수행할 작업|
   |---|---|
   |Windows PowerShell|[ScheduledTasks](/powershell/module/scheduledtasks/) 문서와 이 문서에 있는 [예제 Windows PowerShell 스크립트](#example-powershell-script-for-task-scheduler)를 참조하세요.|
   |작업 스케줄러 API|[작업 스케줄러](/windows/desktop/TaskSchd/using-the-task-scheduler) 문서를 참조하세요.|
   |Windows 사용자 인터페이스|Windows에서 **시작** 을 클릭하고 작업 스케줄러를 입력합니다. 그런 다음 결과 목록에서 **작업 스케줄러** 를 마우스 오른쪽 단추로 클릭하고 **관리자로 실행** 을 선택합니다.|

### <a name="example-powershell-script-for-task-scheduler"></a>작업 스케줄러의 예제 Windows PowerShell 스크립트 

이 섹션에는 데이터를 해시하고 해시 데이터를 업로드하는 작업을 예약하는 데 사용할 수 있는 예제 PowerShell 스크립트가 포함되어 있습니다.

#### <a name="schedule-hashing-and-upload-in-a-combined-step"></a>결합된 단계에서 해시 예약 및 업로드

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="schedule-hashing-and-upload-as-separate-steps"></a>해시 예약 및 별도의 단계로 업로드

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```
