---
title: 사용자에 대한 성능 Microsoft Defender 바이러스 백신
description: 사용자 및 사용자에 대한 성능 조정 절차를 Microsoft Defender 바이러스 백신.
keywords: tune, performance, microsoft defender for endpoint, defender antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fa6206628d8652aef9c8b31dd2ee74d4b6023829
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60659228"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>사용자에 대한 성능 Microsoft Defender 바이러스 백신

**성능 Microsoft Defender 바이러스 백신란?**

경우에 따라 특정 파일 및 폴더를 검색할 때 Microsoft Defender 바이러스 백신 성능 조정이 필요할 수 있습니다. 성능 분석기는 개별 끝점에서 성능 문제를 유발할 수 있는 파일, 파일 확장명 및 프로세스를 확인하는 데 도움이 되는 PowerShell 명령줄 도구입니다. 이 정보를 사용하여 성능 문제를 보다 잘 평가하고 수정 작업을 적용할 수 있습니다.

분석할 수 있는 몇 가지 옵션은 다음과 같습니다.

- 검사 시간 영향을 미치는 상위 파일
- 검사 시간 영향을 미치는 상위 프로세스
- 검사 시간 영향을 미치는 상위 파일 확장명
- 조합 - 예를 들어 확장명당 상위 파일, 파일당 상위 검색, 프로세스당 파일당 상위 검색

## <a name="running-performance-analyzer"></a>성능 분석기 실행

성능 분석기를 실행하는 개개인 프로세스에는 다음 단계가 수행됩니다.

1. 성능 분석기를 실행하여 끝점에서 Microsoft Defender 바이러스 백신 성능 기록을 수집합니다.

   > [!NOTE]
   > Microsoft Microsoft Defender 바이러스 백신 **맬웨어** 방지 엔진 유형의 성능은 성능 분석기를 통해 기록됩니다.

2. 다른 녹음/녹화 보고서를 사용하여 검색 결과를 분석합니다.

## <a name="using-performance-analyzer"></a>성능 분석기 사용

시스템 이벤트 기록을 시작하고 관리 모드에서 PowerShell을 열고 다음 단계를 수행합니다.

1. 다음 명령을 실행하여 기록을 시작하십시오.

   `New-MpPerformanceRecording -RecordTo <recording.etl>`
 
    where 매개 변수는 추적 파일이 저장되는 전체 경로 `-RecordTo` 위치를 지정합니다. cmdlet에 대한 자세한 내용은 [Defender 를 참조하세요.](/powershell/module/defender)

2. 성능에 영향을 주는 것으로 생각되는 프로세스나 서비스가 있는 경우 관련 작업을 수행하여 상황을 재현합니다.

3. Enter를 **눌러** 녹음/녹화를 중지하고 저장하거나 **Ctrl+C를** 눌러 녹음/녹화를 취소합니다.

4. 성능 분석기 매개 변수를 사용하여 결과를 `Get-MpPerformanceReport` 분석합니다. 예를 들어 명령을 실행할 때 사용자에게 성능에 영향을 주는 상위 3개 파일에 대한 상위 `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10` 10개 검사 목록이 제공됩니다. 

명령줄 매개 변수 및 옵션에 대한 자세한 내용은 [New-MpPerformanceRecording](#new-mpperformancerecording) 및 [Get-MpPerformanceReport를 참조하십시오.](#get-mpperformancereport)

> [!NOTE]
> 기록을 실행할 때 "Windows Performance Recorder가 이미 기록 중이기 때문에 성능 기록을 시작할 수 없습니다."라는 오류가 표시되면 다음 명령을 실행하여 새 명령을 사용하여 기존 추적을 **중지합니다. wpr -cancel -instancename MSFT_MpPerformanceRecording**

### <a name="performance-tuning-data-and-information"></a>성능 조정 데이터 및 정보

사용자는 쿼리에 따라 검사 횟수, 기간(총/최소/평균/최대/미디어), 경로, 프로세스 및 검사 이유에 대한 데이터를 볼 수 있습니다. 아래 이미지는 검사 영향에 대한 상위 10개 파일의 간단한 쿼리에 대한 샘플 출력을 보여줍니다. 

:::image type="content" source="images/example-output.png" alt-text="기본 TopFiles 쿼리에 대한 출력 예제":::

### <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>추가 기능: CSV 및 JSON 내보내기 및 변환

성능 분석기 결과를 CSV 또는 JSON 파일로 내보내고 변환할 수도 있습니다.
예제 코드를 통해 "내보내기" 및 "변환" 프로세스를 설명하는 예제는 아래를 참조하세요.

#### <a name="for-csv"></a>CSV의 경우

- **내보내기:**`(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **을 변환하는 경우**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

#### <a name="for-json"></a>JSON의 경우

- **을 변환하는 경우**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

### <a name="requirements"></a>요구 사항
Microsoft Defender 바이러스 백신 성능 분석기에는 다음과 같은 전제가 있습니다.

- 지원되는 Windows 버전: Windows 10, Windows 11 및 Windows Server 2016 이상
- 플랫폼 버전: 4.18.2108.7+
- PowerShell 버전: PowerShell 버전 5.1

## <a name="powershell-reference"></a>PowerShell 참조
새 PowerShell cmdlet은 두 가지 새로운 PowerShell cmdlet을 사용하여 성능 조정을 Microsoft Defender 바이러스 백신. 

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)


### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

다음 섹션에서는 새 PowerShell cmdlet New-MpPerformanceRecording에 대한 참조에 대해 설명합니다. 이 cmdlet은 검색에 대한 성능 Microsoft Defender 바이러스 백신 수집합니다.

#### <a name="syntax-new-mpperformancerecording"></a>구문: New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>설명: New-MpPerformanceRecording
이 `New-MpPerformanceRecording` cmdlet은 검색에 대한 성능 Microsoft Defender 바이러스 백신 수집합니다. 이러한 성능 기록에는 Microsoft-Antimalware-Engine 및 NT 커널 프로세스 이벤트가 포함되어 [있으며, Get-MpPerformanceReport](#get-mpperformancereport) cmdlet을 사용하여 수집 후 분석할 수 있습니다.

이 cmdlet은 문제가 있는 파일에 대한 정보를 제공하면 문제가 있는 파일의 성능이 `New-MpPerformanceRecording` 저하될 수 Microsoft Defender 바이러스 백신. 이 도구는 "AS IS"로 제공된 것이고 제외에 대한 제안을 제공하지 않습니다. 제외는 끝점에 대한 보호 수준을 줄일 수 있습니다. 제외(있는 경우)는 신중하게 정의해야 합니다.

성능 분석기에 대한 자세한 내용은 [Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) docs를 참조하십시오.

> [!IMPORTANT]
> 이 cmdlet을 사용하려면 관리자 권한이 필요합니다.

**지원되는 OS 버전**

Windows 버전 10 이상.

> [!NOTE]
> 이 기능은 플랫폼 버전 4.18.2108.X 이상부터 사용할 수 있습니다.

#### <a name="examples-new-mpperformancerecording"></a>예: New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>예제 1: 성능 기록 수집 및 저장

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

위의 명령은 성능 기록을 수집하여 지정된 경로인 **.\Defender-scans.etl에 저장합니다.**

#### <a name="parameters-new-mpperformancerecording"></a>매개 변수: New-MpPerformanceRecording

##### <a name="-recordto"></a>-RecordTo
Microsoft Defender 맬웨어 방지 성능 기록을 저장할 위치를 지정합니다.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

다음 섹션에서는 PowerShell cmdlet의 Get-MpPerformanceReport 설명합니다. MDAV(Microsoft Defender 바이러스 백신 기록)를 분석하고 보고합니다.

#### <a name="syntax-get-mpperformancereport"></a>구문: Get-MpPerformanceReport

```powershell
Get-MpPerformanceReport    [-Path] <String>
[-TopScans <Int32>]
[-TopFiles  <Int32>
    [-TopScansPerFile <Int32>]
    [-TopProcessesPerFile  <Int32>  
        [-TopScansPerProcessPerFile <Int32>]
    ]
] 
[-TopExtensions  <Int32>
    [-TopScansPerExtension <Int32>]
    [-TopProcessesPerExtension <Int32>
        [-TopScansPerProcessPerExtension <Int32>]
        ]
    [-TopFilesPerExtension  <Int32>
        [-TopScansPerFilePerExtension <Int32>]
        ]
    ] 
]
[-TopProcesses  <Int32>
    [-TopScansPerProcess <Int32>]
    [-TopExtensionsPerProcess <Int32>
        [-TopScansPerExtensionPerProcess <Int32>]
    ]
]
[-TopFilesPerProcess  <Int32>
    [-TopScansPerFilePerProcess <Int32>]
]
[-MinDuration <String>]
```

#### <a name="description-get-mpperformancereport"></a>설명: Get-MpPerformanceReport
이 cmdlet은 이전에 수집한 Microsoft Defender 바이러스 백신 성능 `Get-MpPerformanceReport` [기록(New-MpPerformanceRecording)을](#new-mpperformancerecording)분석하고 파일 검색에 가장 큰 영향을 미치는 파일 경로, 파일 확장명 및 프로세스를 Microsoft Defender 바이러스 백신 보고합니다.

성능 분석기는 문제가 있는 파일에 대한 정보를 제공합니다. 이로 인해 문제가 있는 파일의 성능이 저하될 수 Microsoft Defender 바이러스 백신. 이 도구는 "AS IS"로 제공된 것이고 제외에 대한 제안을 제공하지 않습니다. 제외는 끝점에 대한 보호 수준을 줄일 수 있습니다. 제외(있는 경우)는 신중하게 정의해야 합니다.

성능 분석기에 대한 자세한 내용은 [Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) docs를 참조하십시오.

**지원되는 OS 버전**

Windows 버전 10 이상.

> [!NOTE]
> 이 기능은 플랫폼 버전 4.18.2108.X 이상부터 사용할 수 있습니다.

#### <a name="examples-get-mpperformancereport"></a>예: Get-MpPerformanceReport

##### <a name="example-1-single-query"></a>예제 1: 단일 쿼리 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:20
```

##### <a name="example-2-multiple-queries"></a>예제 2: 여러 쿼리 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10
```

##### <a name="example-3-nested-queries"></a>예제 3: 중첩된 쿼리 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopExtensionsPerProcess:3 -TopScansPerExtensionPerProcess:3
```

##### <a name="example-4-using--minduration-parameter"></a>예제 4: -MinDuration 매개 변수 사용

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:100 -MinDuration:100ms
```

#### <a name="parameters-get-mpperformancereport"></a>매개 변수: Get-MpPerformanceReport

##### <a name="-minduration"></a>-MinDuration
보고서에 포함된 파일, 확장명 및 프로세스의 최소 검사 기간 또는 총 검사 기간을 지정합니다.  **0.1234567sec,** **0.1234ms,** **0.1us** 또는 유효한 TimeSpan과 같은 값을 허용합니다.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

##### <a name="-path"></a>-Path
하나 이상의 위치에 대한 경로를 지정합니다.

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### <a name="-topextensions"></a>-TopExtensions 
출력할 상위 확장 수를 "Duration"별로 정렬하여 지정합니다.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess 
"Duration"으로 정렬된 각 상위 프로세스에 대해 출력할 상위 확장 수를 지정합니다.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfiles"></a>-TopFiles
최상위 파일 보고서를 요청하고 출력할 최상위 파일 수를 "Duration"별로 정렬하여 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperextension"></a>-TopFilesPerExtension 
"Duration"을 정렬하여 각 상위 확장명에 대해 출력할 최상위 파일 수를 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperprocess"></a>-TopFilesPerProcess
"Duration"을 정렬하여 각 상위 프로세스에 대해 출력할 상위 파일 수를 지정합니다.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocesses"></a>-TopProcesses
최상위 프로세스 보고서를 요청하고 출력할 상위 프로세스의 수를 "Duration"별로 정렬하여 지정합니다.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension 
"Duration"을 정렬하여 각 상위 확장에 대해 출력할 상위 프로세스 수를 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topprocessesperfile"></a>-TopProcessesPerFile
"Duration"을 정렬하여 각 상위 파일에 대해 출력할 상위 프로세스 수를 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscans"></a>-TopScans
최상위 검색 보고서를 요청하고 출력할 상위 검색 수를 "Duration"별로 정렬하여 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextension"></a>-TopScansPerExtension
"Duration"으로 정렬된 각 상위 확장에 대해 출력할 상위 검색 수를 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess 
각 상위 프로세스의 각 상위 확장명에 대해 출력할 상위 검색 수를 "Duration"으로 정렬하여 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfile"></a>-TopScansPerFile
"Duration"을 정렬하여 각 상위 파일에 대해 출력할 상위 검색 수를 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension 
각 상위 확장명에 대해 출력할 상위 검색 수를 "Duration"으로 정렬하여 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess 
각 상위 프로세스의 각 상위 파일에 대해 출력에 대한 최상위 검색 수를 "Duration"으로 정렬하여 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperprocess"></a>-TopScansPerProcess 
상위 프로세스 보고서에서 각 상위 프로세스에 대해 출력할 상위 검색 수를 "Duration"으로 정렬하여 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension
"Duration"별로 정렬된 각 상위 확장의 각 상위 프로세스에 대한 출력에 대한 상위 검색 수를 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile
"Duration"을 정렬하여 각 상위 파일에 대한 각 상위 프로세스의 출력에 대한 상위 검색 수를 지정합니다.


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

