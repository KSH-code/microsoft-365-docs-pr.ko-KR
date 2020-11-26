---
title: 고급 사냥을 사용 하 여 랜 섬 웨어 찾기
description: 고급 검색을 사용 하 여 랜 섬 웨어의 영향을 받을 수 있는 장치를 찾습니다.
keywords: 고급 구하기, 랜 섬 웨어, 위협 검색, 사이버 위협 구하기, search, 쿼리, 원격 분석, Microsoft 365, microsoft Threat Protection, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: aaee2af4b3df849b57b8e1c18ab330603042fe96
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422907"
---
# <a name="hunt-for-ransomware"></a>랜 섬 웨어 사냥

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

랜 섬 웨어는 산업 및 정부 기관에 심각한 영향을 주는 엔터프라이즈 위협에 개별 컴퓨터 사용자에 게 영향을 주는 단순한 필수품 맬웨어를 신속 하 게 발전 했습니다. [Microsoft 365 Defender](microsoft-threat-protection.md) 는 랜 섬 웨어 및 연결 된 침입 활동을 감지 하 고 차단 하는 여러 기능을 제공 하며, 손상의 징후에 대 한 사전 확인을 수행 하는 것은 네트워크 보호를 유지

> [사용자가 운영 하는 랜 섬에 대해 자세히 알아봅니다.](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

Microsoft 365 Defender의 [고급 구하기](advanced-hunting-overview.md) 를 사용 하 여 랜 섬 웨어 작업과 연결 된 개별 아티팩트를 찾는 쿼리를 만들 수 있습니다. 또한 작업의 신호를 확인 하 고 이러한 서명을 평가 하 여 즉각적인 주의가 필요한 장치를 찾도록 하는 보다 정교한 쿼리를 실행할 수 있습니다.

## <a name="signs-of-ransomware-activity"></a>랜 섬 웨어 활동의 징후
Microsoft 보안 연구는 복잡 한 침입자가 시작한 많은 랜 섬 웨어 캠페인의 다양 하 고 미묘한 여러 가지 아티팩트를 관찰 했습니다. 이러한 서명에는 대부분 시스템 도구를 사용 하 여 암호화를 준비 하 고 검색을 방지 하 고 법적 증거를 정리 합니다.

| 랜 섬 웨어 활동 | 일반 도구 | 문이 |
|--|--|--|
| 중지 프로세스 | _taskkill.exe_, _net stop_ | 암호화 대상이 지정 된 파일이 여러 응용 프로그램에 의해 잠기지 않았는지 확인 합니다. |
| 서비스 해제 | _sc.exe_ | -암호화를 대상으로 하는 파일이 여러 응용 프로그램에 의해 잠기지 않았는지 확인 합니다.<br>-보안 소프트웨어가 암호화 및 기타 랜 섬 웨어 활동을 방해 하지 않도록 합니다.<br>-백업 소프트웨어가 복구 가능한 복사본을 만들지 않도록 합니다.  |
| 로그 및 파일 삭제 | _cipher.exe_, _wevtutil_, _fsutil.exe_ | 법적 증거를 제거 합니다. |
| 섀도 복사본 삭제  | _vsadmin.exe_ _wmic.exe_ | 암호화 된 파일을 복구 하는 데 사용할 수 있는 드라이브 섀도 복사본을 제거 합니다. |
| 백업 삭제 및 중지 | _wbadmin.exe_ | 기존 백업을 삭제 하 고 예약 된 백업 작업을 중지 하 여 암호화 후 복구를 방지 합니다. |
| 부팅 설정 수정 | _bcdedit.exe_ | 암호화 프로세스에 의해 발생할 수 있는 부팅 오류가 발생 한 후 경고 및 자동 복구를 해제 합니다. |
| 복구 도구 해제 | _schtasks.exe_, _regedit.exe_, | 시스템 복원 및 기타 시스템 복구 옵션을 해제 합니다. |

## <a name="check-for-individual-signs-of-ransomware-activity"></a>랜 섬 웨어 활동의 개별 신호 확인
이전 섹션에서 설명한 작업을 포함 하 여 랜 섬 웨어 동작을 구성 하는 많은 작업이 심각 하지는 않습니다. 다음 쿼리를 사용 하 여 랜 섬 웨어를 찾을 때 두 개 이상의 쿼리를 실행 하 여 동일한 장치가 가능한 랜 섬 웨어 활동의 징후를 여러 개 나타내는지 확인 합니다.

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a>_taskkill.exe_ 을 사용 하 여 여러 프로세스 중지
이 쿼리는 _taskkill.exe_ 유틸리티를 사용 하 여 최소 10 개의 개별 프로세스를 중지 하려는 시도를 확인 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a>_Net stop_ 을 사용 하 여 프로세스 중지
이 쿼리는 _net stop_ 명령을 사용 하 여 최소 10 개의 개별 프로세스를 중지 하려는 시도를 확인 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a>_cipher.exe_ 을 사용 하 여 여러 드라이브에서 데이터 삭제
이 쿼리는 _cipher.exe_ 을 사용 하 여 여러 드라이브에서 데이터를 삭제 하려는 시도를 확인 합니다. 이 작업은 일반적으로 랜 섬 웨어에서 암호화 후에 데이터를 복구할 수 없도록 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

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

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a>_Wevtutil_ 을 사용 하 여 이벤트 로그에서 법적 증거 지우기
이 쿼리는 _wevtutil_ 을 사용 하 여 이벤트 로그에서 최소 10 개의 로그 항목을 지우려는 시도를 확인 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a>_sc.exe_ 을 사용 하 여 서비스 해제
이 쿼리는 _sc.exe_ 을 사용 하 여 최소 10 개의 기존 서비스를 끌 시도를 확인 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a>시스템 복원 해제
이 쿼리는 시스템 복원을 중지 하 고 시스템에서 랜 섬 웨어로 암호화 된 데이터를 복구 하는 데 사용할 수 있는 복원 지점을 만들지 못하도록 하는 시도를 식별 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

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

### <a name="backup-deletion"></a>백업 삭제
이 쿼리는 암호화 전에 섀도 복사본 스냅숏을 삭제 하기 위한 _wmic.exe_ 의 사용을 식별 합니다. [쿼리 실행](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a>랜 섬 웨어 활동의 여러 징후 확인
여러 쿼리를 개별적으로 실행 하는 대신, 영향을 받는 장치를 식별 하기 위해 랜 섬 웨어 활동의 여러 징후가 있는지 확인 하는 포괄적인 쿼리를 사용할 수도 있습니다. 통합 쿼리는 다음과 같습니다.
- 비교적 구체적이 고도 랜 섬 웨어 활동의 약한 표지판을 찾습니다.
- 신뢰도의 현재 상태
- 랜 섬 웨어의 표적을 높일 가능성이 높은 장치를 식별 합니다. 

이 통합 쿼리를 실행 하면 여러 공격 징후를 표시 한 장치 목록이 반환 됩니다. 각 랜 섬 웨어 활동 유형의 수도 표시 됩니다. 이 통합 쿼리를 실행 하려면 [고급 구하기 쿼리 편집기](https://security.microsoft.com/advanced-hunting)에 직접 복사 합니다. 

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
통합 쿼리를 실행 하면 다음과 같은 결과가 반환 됩니다.

- **DeviceId**-영향을 받는 장치를 식별 합니다. 
- **TimeStamp**-장치에서 최대 섬 웨어 활동의 신호를 처음으로 관찰 한 시간입니다.
- **특정 작업 신호**- _BcdEdit_ 또는 _FsUtil_ 과 같은 여러 열에 표시 되는 각 표지판의 수
- **TotalEvidenceCount**-관찰 되는 서명 수
- **UniqueEvidenceCount**-관찰 된 서명 유형의 수

![랜 섬 웨어 활동에 대 한 쿼리 결과 이미지](../../media/advanced-hunting-ransomware-query.png)

*영향을 받는 장치와 각 랜 섬 웨어 활동의 다양 한 징후 개수를 보여 주는 쿼리 결과*

기본적으로 쿼리 결과에는 2 개 유형의 랜 섬 웨어 활동이 두 개 이상 있는 장치만 나열 됩니다. 랜 섬 웨어 활동의 모든 표지판이 있는 모든 장치를 보려면 다음 연산자를 수정 하 `where` 고 숫자를 영 (0)으로 설정 합니다. 더 많은 장치를 보려면 보다 큰 번호를 설정 합니다. 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)