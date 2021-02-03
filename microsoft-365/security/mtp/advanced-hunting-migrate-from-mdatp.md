---
title: 끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션
description: Microsoft 365 Defender에서 사용할 수 있도록 끝점용 Microsoft Defender 쿼리를 조정하는 방법에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, microsoft defender atp, mdatp, 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, microsoft 365, 매핑
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080746"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

끝점용 Microsoft Defender의 고급 헌팅 워크플로를 이동하여 광범위한 데이터 집합을 사용하여 위협을 사전 예방적으로 헌팅합니다. Microsoft 365 Defender에서 다음을 비롯한 다른 Microsoft 365 보안 솔루션의 데이터에 액세스할 수 있습니다.

- 엔드포인트용 Microsoft Defender
- Office 365용 Microsoft Defender
- Microsoft Cloud App Security
- ID용 Microsoft Defender

>[!NOTE]
>대부분의 엔드포인트용 Microsoft Defender 고객은 추가 라이선스 없이 [Microsoft 365 Defender를 사용할 수 있습니다.](prerequisites.md#licensing-requirements) 끝점용 Defender에서 고급 헌팅 워크플로 전환을 시작하고 [Microsoft 365 Defender를 켜야 합니다.](mtp-enable.md)

끝점 워크플로에 대한 기존 Defender에 영향을 주지 않고 전환할 수 있습니다. 저장된 쿼리는 그대로 유지되고 사용자 지정 검색 규칙은 계속 실행되고 경고를 생성합니다. 그러나 Microsoft 365 Defender에서 표시됩니다. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Microsoft 365 Defender의 Schema 테이블만
[Microsoft 365 Defender 고급 헌팅](advanced-hunting-schema-tables.md) 계획은 다양한 Microsoft 365 보안 솔루션의 데이터를 포함하는 추가 테이블을 제공합니다. 다음 표는 Microsoft 365 Defender에서만 사용할 수 있습니다.

| 테이블 이름 | 설명 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 경고와 연결된 파일, IP 주소, URL, 사용자 또는 장치 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | 심각도 정보 및 위협 범주를 포함하여 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 ID용 Microsoft Defender의 알림  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | 클라우드 앱 및 서비스의 파일 관련 활동 |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 전자 메일에 첨부된 파일에 대한 정보 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 전자 메일 이벤트(전자 메일 배달 및 차단 이벤트 포함) |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365에서 받는 사람 사서함으로 전자 메일을 배달한 후의 배달 후 발생하는 보안 이벤트 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 전자 메일의 URL에 대한 정보 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | AD(Active Directory)를 실행하는 On-프레미스 도메인 컨트롤러와 관련된 이벤트입니다. 이 표에는 도메인 컨트롤러의 ID 관련 이벤트 및 시스템 이벤트 범위가 포함됩니다. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Azure Active Directory를 비롯한 다양한 원본의 계정 정보 |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 및 Microsoft 온라인 서비스의 인증 이벤트 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | 사용자, 그룹, 장치 및 도메인과 같은 Active Directory 개체에 대한 쿼리 |

## <a name="map-devicealertevents-table"></a>DeviceAlertEvents 맵 테이블
테이블과 `AlertInfo` `AlertEvidence` `DeviceAlertEvents` 테이블은 끝점용 Microsoft Defender의 테이블을 대체합니다. 이러한 두 테이블에는 장치 경고에 대한 데이터 외에도 ID, 앱 및 전자 메일에 대한 경고에 대한 데이터가 포함됩니다.

다음 표를 사용하여 열이 열과 표의 열에 `DeviceAlertEvents` 매핑되는 방법을 `AlertInfo` 확인할 수 `AlertEvidence` 있습니다.

>[!TIP]
>이 표에는 다음 표의 열 외에도 다양한 원본의 경고에 대한 보다 전체적인 그림을 제공하는 다른 여러 `AlertEvidence` 열이 포함되어 있습니다. [모든 AlertEvidence 열 보기](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 열 | Microsoft 365 Defender에서 동일한 데이터를 찾을 수 있는 위치 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` 및  `AlertEvidence` 테이블 |
| `Timestamp` | `AlertInfo` 및  `AlertEvidence` 테이블 |
| `DeviceId` | `AlertEvidence` table |
| `DeviceName` | `AlertEvidence` table |
| `Severity` | `AlertInfo` table |
| `Category` | `AlertInfo` table |
| `Title` | `AlertInfo` table |
| `FileName` | `AlertEvidence` table |
| `SHA1` | `AlertEvidence` table |
| `RemoteUrl` | `AlertEvidence` table |
| `RemoteIP` | `AlertEvidence` table |
| `AttackTechniques` | `AlertInfo` table |
| `ReportId` | 이 열은 일반적으로 끝점용 Microsoft Defender에서 다른 테이블의 관련 레코드를 찾는 데 사용됩니다. Microsoft 365 Defender에서 테이블에서 직접 관련 데이터를 얻을 수 `AlertEvidence` 있습니다. |
| `Table` | 이 열은 일반적으로 다른 테이블의 추가 이벤트 정보에 대해 끝점용 Microsoft Defender에서 사용됩니다. Microsoft 365 Defender에서 테이블에서 직접 관련 데이터를 얻을 수 `AlertEvidence` 있습니다. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>끝점 쿼리에 대한 기존 Microsoft Defender 조정
끝점용 Microsoft Defender 쿼리는 테이블을 참조하지 않는 한 있는 것으로 `DeviceAlertEvents` 작동됩니다. Microsoft 365 Defender에서 이러한 쿼리를 사용 하 고 다음 변경 내용을 적용 합니다.

- `DeviceAlertEvents`.로 바꾸기 `AlertInfo`
- 해당 데이터를 얻기 위해 테이블과 `AlertInfo` `AlertEvidence` `AlertId` 테이블을 조인합니다.

### <a name="original-query"></a>원래 쿼리
다음 쿼리는 `DeviceAlertEvents` 끝점용 Microsoft Defender에서 다음을 __ 사용하여 다음과 같은 경고를powershell.exe.

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>수정된 쿼리
다음 쿼리는 Microsoft 365 Defender에서 사용하기 위해 조정되었습니다. 파일 이름을 직접 확인하지 않고 해당 테이블의 파일 이름을 조인하고 `DeviceAlertEvents` `AlertEvidence` 검사합니다.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>사용자 지정 검색 규칙 마이그레이션

Microsoft 365 Defender에서 끝점용 Microsoft Defender 규칙을 편집하면 결과 쿼리가 장치 테이블만 볼 때처럼 계속 이전과 같은 기능을 합니다. 예를 들어 장치 테이블만 쿼리하는 사용자 지정 검색 규칙에 의해 생성된 경고는 끝점용 Microsoft Defender에서 구성한 방식에 따라 SIEM으로 계속 배달되고 전자 메일 알림을 생성합니다. 끝점용 Defender의 기존 제거 규칙도 계속 적용됩니다.

끝점용 Defender 규칙을 편집하여 Microsoft 365 Defender에서만 사용할 수 있는 ID 및 전자 메일 테이블을 쿼리하면 규칙이 Microsoft 365 Defender로 자동 이동됩니다. 

마이그레이션된 규칙에 의해 생성된 경고:

- 끝점 포털용 Defender에 더 이상 표시되지 않습니다(Microsoft Defender 보안 센터).
- SIEM으로 배달되는 것을 중지하거나 전자 메일 알림을 생성합니다. 이 변경을 해결하기 위해 Microsoft 365 Defender를 통해 알림을 구성하여 알림을 얻습니다. [Microsoft 365 Defender API를](api-incident.md) 사용하여 고객 검색 경고 또는 관련 인시던트에 대한 알림을 받을 수 있습니다.
- 끝점 제거 규칙에 대한 Microsoft Defender에 의해 억제되지 않습니다. 특정 사용자, 장치 또는 사서함에 대한 알림이 생성되지 않도록 방지하려면 해당 쿼리를 수정하여 해당 엔터티를 명시적으로 제외합니다.

이러한 방식으로 규칙을 편집하면 변경 내용이 적용되기 전에 확인 메시지가 표시됩니다.

Microsoft 365 Defender 포털의 사용자 지정 검색 규칙에 의해 생성된 새 경고는 다음 정보를 제공하는 경고 페이지에 표시됩니다.

- 경고 제목 및 설명 
- 영향을 미치는 자산
- 경고에 응답하여 수행된 작업
- 경고를 트리거한 쿼리 결과 
- 사용자 지정 검색 규칙에 대한 정보 
 
![새 경고 페이지의 이미지](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a>DeviceAlertEvents 없이 쿼리 작성

Microsoft 365 Defender schema에서는 다양한 원본의 경고와 함께 제공되는 다양한 정보 집합을 수용할 수 있도록 `AlertInfo` `AlertEvidence` 테이블이 제공됩니다. 

끝점용 Microsoft Defender의 테이블에서 다운로드하는 데 사용한 경고 정보를 얻습니다. 그런 다음 테이블을 필터링한 다음 각 고유 ID를 테이블에 조인하여 자세한 이벤트 및 엔터티 정보를 `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` 제공합니다. 

아래 예제 쿼리를 참조하세요.

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

이 쿼리는 끝점용 Microsoft Defender 스마마보다 많은 `DeviceAlertEvents` 열을 산출합니다. 결과를 관리할 수 있도록 유지 관리하기 위해 관심 있는 열만 `project` 얻습니다. 조사에서 PowerShell 활동을 감지할 때 관심 있는 프로젝트 열 아래의 예:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

경고와 관련된 특정 엔터티를 필터링할 경우 엔터티 형식과 필터링할 값을 지정하여 필터링할 `EntityType` 수 있습니다. 다음 예에서는 특정 IP 주소를 검색합니다.

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>참고 항목
- [Microsoft 365 Defender 켜기](advanced-hunting-query-language.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [끝점용 Microsoft Defender의 고급 헌팅](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)