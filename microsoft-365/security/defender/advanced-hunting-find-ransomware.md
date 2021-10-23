---
title: 고급 헌팅으로 랜섬웨어 찾기
description: 고급 헌팅을 사용하여 랜섬웨어의 영향을 받을 수 있는 장치를 찾습니다.
keywords: 고급 헌팅, 랜섬웨어, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f856e13804d777f5405d5368529252f958f25de1
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555503"
---
# <a name="hunt-for-ransomware"></a>랜섬웨어 찾기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

랜섬웨어는 개별 컴퓨터 사용자에게 영향을 주는 단순한 상품 맬웨어에서 산업 및 정부 기관에 심각한 영향을 미치는 엔터프라이즈 위협으로 빠르게 발전했습니다. Microsoft 365 Defender [](microsoft-365-defender.md) 랜섬웨어 및 관련 침입 활동을 감지하고 차단하는 많은 기능을 제공 하지만 손상 징후에 대한 사전 검사를 수행하면 네트워크를 보호하는 데 도움이 될 수 있습니다.

> [인간이 운영하는 랜섬웨어에 대한 읽기](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

고급 [헌팅을](advanced-hunting-overview.md) Microsoft 365 Defender 랜섬웨어 활동과 관련된 개별 아티팩트를 찾는 쿼리를 만들 수 있습니다. 활동의 징후를 찾고 해당 기호의 가중치가 즉시 주의가 필요한 장치를 찾을 수 있는 좀 더 정교한 쿼리를 실행할 수도 있습니다.

## <a name="signs-of-ransomware-activity"></a>랜섬웨어 활동의 징후
Microsoft 보안 연구원들은 정교한 침입자가 시작한 많은 랜섬웨어 캠페인에서 다양한 공통적이지만 미묘한 아티팩트를 관찰했습니다. 이러한 기호는 주로 시스템 도구를 사용하여 암호화를 준비하고, 탐지를 방지하고, 명확한 포렌식 증거를 사용합니다.

| 랜섬웨어 활동 | 일반적인 도구 | 의도 |
|--|--|--|
| 프로세스 중지 | _taskkill.exe_, _net stop_ | 암호화 대상 파일이 다양한 응용 프로그램에 의해 잠겨 있지 않은지 확인 |
| 서비스 끄기 | _sc.exe_ | - 암호화 대상 파일이 다양한 응용 프로그램에 의해 잠겨 있지 않은지 확인<br>- 보안 소프트웨어가 암호화 및 기타 랜섬웨어 활동을 중단하지 못하게 합니다.<br>- 백업 소프트웨어가 복구 가능한 복사본을 만들지 못하게 합니다.  |
| 로그 및 파일 삭제 | _cipher.exe_, _wevtutil_, _fsutil.exe_ | 포렌식 증거를 제거합니다. |
| 섀도 복사본 삭제  | _vsadmin.exe_, _wmic.exe_ | 암호화된 파일을 복구하는 데 사용할 수 있는 드라이브 섀도 복사본을 제거합니다. |
| 백업 삭제 및 중지 | _wbadmin.exe_ | 기존 백업을 삭제하고 예약된 백업 작업을 중지하여 암호화 후 복구를 방지합니다. |
| 부팅 설정 수정 | _bcdedit.exe_ | 암호화 프로세스로 인해 발생할 수 있는 부팅 오류 후 경고 및 자동 복구를 끄기. |
| 복구 도구 끄기 | _schtasks.exe_, _regedit.exe_. | 시스템 복원 및 기타 시스템 복구 옵션을 해제합니다. |

## <a name="check-for-individual-signs-of-ransomware-activity"></a>랜섬웨어 활동의 개별 징후 확인
위 섹션에 설명된 활동을 포함하여 랜섬웨어 동작을 구성하는 많은 활동은 무의미할 수 있습니다. 다음 쿼리를 사용하여 랜섬웨어를 찾는 경우 두 개 이상의 쿼리를 실행하여 동일한 장치가 가능한 랜섬웨어 활동의 다양한 징후를 표시하는지 여부를 검사합니다.

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a>데이터를 사용하여 여러 _프로세스taskkill.exe_
이 쿼리는taskkill.exe유틸리티를 사용하여 별도의 프로세스를 10개 이상 중지하려는 _시도를_ 검사합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a>net stop을 사용하여 _프로세스 중지_
이 쿼리는 net stop 명령을 사용하여 10개 이상의 개별 프로세스를 중지하려는 _시도를 검사합니다._ [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a>데이터를 사용하여 여러 드라이브에서 데이터 _cipher.exe_
이 쿼리는 를 사용하여 여러 드라이브에서 데이터를 삭제하려는 시도를 _cipher.exe._ 이 활동은 일반적으로 암호화 후 데이터 복구를 방지하기 위해 랜섬웨어에 의해 수행됩니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a>_wevtutil을_ 사용하여 이벤트 로그에서 포렌식 증거 지우기
이 쿼리는 _wevtutil을_ 사용하여 이벤트 로그에서 로그 항목을 10개 이상 지우는 시도를 검사합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a>서비스를 사용하여 서비스 _sc.exe_
이 쿼리는 를 사용하여 기존 서비스를 10개 이상 해제하려는 _시도를sc.exe._ [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a>시스템 복원 끄기
이 쿼리는 시스템 복원을 중지하고 시스템이 랜섬웨어로 암호화된 데이터를 복구하는 데 사용할 수 있는 복원 지점을 만들지 못하도록 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a>백업 지우기
이 쿼리는 암호화  전에wmic.exe섀도 복사본 스냅숏을 삭제하는 데 사용할 수 있는 방법을 식별합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a>랜섬웨어 활동의 여러 징후 확인
여러 쿼리를 별도로 실행하는 대신 여러 랜섬웨어 활동의 징후를 확인하는 포괄적인 쿼리를 사용하여 영향을 받는 장치를 식별할 수도 있습니다. 다음 통합 쿼리
- 랜섬웨어 활동의 비교적 구체적이고 미묘한 징후를 모두 밝히는 방법
- 이러한 기호의 존재에 가중치
- 랜섬웨어의 대상이 되는 확률이 높은 장치를 식별합니다. 

실행 시 이 통합 쿼리는 여러 공격의 징후가 있는 장치 목록을 반환합니다. 각 유형의 랜섬웨어 활동 수도 표시됩니다. 이 통합 쿼리를 실행하기 위해 고급 헌팅 쿼리 편집기로 [직접 복사합니다.](https://security.microsoft.com/advanced-hunting) 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a>쿼리 결과 이해 및 조정
통합 쿼리는 다음 결과를 반환합니다.

- **DeviceId**- 영향을 받는 장치를 식별합니다. 
- **TimeStamp**- 장치에서 랜섬웨어 활동의 징후가 처음으로 관찰된 경우
- **특정 활동 표시**- _BcdEdit_ 또는 _FsUtil과_ 같은 여러 열에 표시되는 각 기호의 수입니다.
- **TotalEvidenceCount**- 관찰된 기호 수입니다.
- **UniqueEvidenceCount**- 관찰된 표지의 수

![랜섬웨어 활동에 대한 쿼리 결과의 이미지입니다.](../../media/advanced-hunting-ransomware-query.png)

*영향을 받는 장치 및 랜섬웨어 활동의 다양한 징후 수를 보여 주는 쿼리 결과*

기본적으로 쿼리 결과에는 두 가지 이상의 유형의 랜섬웨어 활동이 있는 장치만 나열됩니다. 랜섬웨어 활동의 부호가 있는 모든 장치를 표시하려면 다음 연산자를 수정하고 번호를 `where` 0으로 설정합니다. 더 적은 장치를 표시하기 위해 더 높은 수를 설정하십시오. 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과로 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)

## <a name="additional-ransomware-resources"></a>추가 랜섬웨어 리소스

Microsoft의 주요 정보:

- [랜섬웨어 위협 증가](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), 2021년 7월 20일 Microsoft On the Issue 블로그 게시물
- [사람이 조작하는 랜섬웨어](/security/compass/human-operated-ransomware)
- [랜섬웨어 및 탈취로부터 신속하게 보호](/security/compass/protect-against-ransomware)
- [2021 Microsoft Digital Defense 보고서](https://www.microsoft.com/security/business/microsoft-digital-defense-report)(10-19페이지 참조)
- [랜섬웨어:](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview) 랜섬웨어 포털의 보행 및 지속적인 위협 분석 Microsoft 365 Defender 보고서

Microsoft 365:

- [Microsoft 365 테넌트용 랜섬웨어 보호 배포](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Azure 및 Microsoft 365를 사용하여 랜섬웨어 복원력 최대화](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [랜섬웨어 공격으로부터 복구](/microsoft-365/security/office-365-security/recover-from-ransomware)
- [맬웨어 및 랜섬웨어 보호](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [랜섬웨어로부터 Windows PC 보호](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [SharePoint Online에서 랜섬웨어 처리](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [보안 포털의 랜섬웨어에](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag) 대한 위협 Microsoft 365 Defender 보고서

Microsoft Azure:

- [랜섬웨어 공격용 Azure 방어](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Azure 및 Microsoft 365를 사용하여 랜섬웨어 복원력 최대화](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [랜섬웨어로부터 보호하기 위한 백업 및 복원 계획](/security/compass/backup-plan-to-protect-against-ransomware)
- [랜섬웨어로부터](https://www.youtube.com/watch?v=VhLOr2_1MCg) 보호하는 Microsoft Azure 백업(26분 비디오)
- [시스템 ID 손상 복구](/azure/security/fundamentals/recover-from-identity-compromise)
- [Azure Sentinel에서 고급 다단계 공격 탐지](/azure/sentinel/fusion#ransomware)
- [Azure Sentinel의 랜섬웨어 퓨전 탐지](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Cloud App Security:

-  [Cloud App Security에서 이상 탐지 정책 생성](/cloud-app-security/anomaly-detection-policy)

Microsoft 보안 팀 블로그 게시물:

- [랜섬웨어 방지 및 복구를 위한 3단계(2021년 9월)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [사이버 보안 위험 파악을 통한 탄력성 강화: 제4부—현재 위협 탐색(2021년 5월)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  **랜섬웨어** 섹션을 참조하세요.

- [인간 운영 랜섬웨어 공격: 예방 가능한 재해(2020년 3월)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  실제 공격에 대한 공격 체인 분석을 포함합니다.

- [랜섬웨어 대응—지불 여부(2019년 12월)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro가 랜섬웨어 공격에 투명하게 대응(2019년 12월)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
