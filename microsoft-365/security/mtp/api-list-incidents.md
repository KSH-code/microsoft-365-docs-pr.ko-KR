---
title: Microsoft Threat Protection의 문제 해결 API 목록
description: Microsoft Threat Protection에서 문제 API를 나열 하는 방법 알아보기
keywords: 목록, 인시던트, 인시던트, api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775114"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 문제 해결 API 목록

**적용 대상:**

- Microsoft 위협 방지

> [!IMPORTANT]
> 일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API 설명

인시던트 API를 사용 하면 인시던트를 정렬 하 여 우선 순위를 지정 하 고 의사 cybersecurity 응답을 만들 수 있습니다. 이는 환경 보존 정책에서 지정한 시간 범위 내에서 장치, 전자 메일 계정 및 네트워크 사용자 로부터 플래그가 지정 된 인시던트 모음을 노출 합니다. 가장 최근 인시던트가 목록 맨 위에 표시 됩니다. 각 인시던트에는 관련 된 경고의 배열과 관련 엔터티가 포함 되어 있습니다.

<br>이 API는 다음 **OData** 연산자를 지원 합니다.
<br>```$filter``` 설정: ```lastUpdateTime``` , ```createdTime``` ```status``` 및 ```assignedTo``` 속성
<br>```$top``` max 값 **100**
<br>```$skip```

## <a name="limitations"></a>제한 사항

1. 최대 페이지 크기는 **100 인시던트**입니다.
2. 최대 요청 속도는 **분당 50 통화** 이 고 **시간당 1500 통화**입니다.

## <a name="permissions"></a>사용 권한

이 API를 호출 하려면 다음 사용 권한 중 하나가 필요 합니다. 사용 권한을 선택 하는 방법을 비롯 하 여 자세히 알아보려면 [Access Microsoft Threat Protection api](api-access.md) 를 참조 하세요.

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   보안 문제를 모두 읽고 | ' 모든 인시던트 읽기 '
응용 프로그램 |   인시던트의 모든 | ' 모든 인시던트 읽기 및 쓰기 '
위임 됨 (회사 또는 학교 계정) | 문제점. 읽기 | ' 인시던트 읽기 '
위임 됨 (회사 또는 학교 계정) | 인시던트-ReadWrite | ' 인시던트 읽기 및 쓰기 '

> [!Note]
> 사용자 자격 증명을 사용 하 여 토큰을 가져올 때:
> - 사용자에 게 포털의 인시던트에 대 한 보기 권한이 있어야 합니다.
> - 응답에는 사용자에 게 노출 되는 인시던트만 포함 됩니다.

## <a name="http-request"></a>HTTP 요청

```
GET /api/incidents
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | 전달자 {토큰}. **필수**입니다.


## <a name="request-body"></a>요청 본문
없음

## <a name="response"></a>응답
성공한 경우이 메서드는 200 OK를 반환 하 고 응답 본문에 [인시던트](api-incident.md) 목록을 표시 합니다.

## <a name="schema-mapping"></a>스키마 매핑

| 필드 이름                                | 설명                                                                                                                                                                                                                                                                                                                                                                                | 예제 값                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **인시던트 메타 데이터**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| incidentId                                | 인시던트를 나타내는 고유 식별자입니다.                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | 인시던트 처리 논리의 일부로 사고가 다른 인시던트에 함께 그룹화 되는 경우에만 채워집니다.                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| incidentName                              | 모든 인시던트에 제공 되는 문자열 값입니다.                                                                                                                                                                                                                                                                                                                                                  | 랜 섬 웨어 활동                                                                                                                                                                                                                               |
| createdTime                               | 인시던트를 처음으로 만든 시간입니다.                                                                                                                                                                                                                                                                                                                                                      | 2020-09-06T14:46:57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | 백 엔드에서 인시던트를 마지막으로 업데이트 한 시간입니다.<br> 이 필드는 인시던트가 검색 되는 범위에 대해 request 매개 변수를 설정할 때 사용할 수 있습니다.                                                                                                                                                                                                                      | 2020-09-06T14:46:57.29 Z                                                                                                                                                                                                                           |
| assignedTo                                | 인시던트의 소유자 이거나 소유자가 할당 되지 않은 경우 *null* 입니다.                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| 유형을                            | 인시던트에 대 한 사양입니다. 속성 값은 *Unknown*, *FalsePositive*, *TruePositive* 입니다.                                                                                                                                                                                                                                                                           | 알 수 없음                                                                                                                                                                                                                                           |
| 가져옴을                             | 문제에 대 한 결정을 지정 합니다. 속성 값은 *Notavailable*, *Apt*, *맬웨어*, *securitypersonnel*, *securitypersonnel*, *UnwantedSoftware*등입니다. *Other*                                                                                                                                                                                                                | NotAvailable                                                                                                                                                                                                                                      |
| 상태별                                    | 인시던트를 *활성*또는 *확인*된 것으로 분류 합니다. 이를 통해 인시던트에 대 한 응답을 구성 하 고 관리할 수 있습니다.                                                                                                                                                                                                                                                                  | 활성                                                                                                                                                                                                                                            |
| 이상인                                  | 자산에 미칠 수 있는 영향을 나타냅니다. 심각도가 높을수록 영향은 더 커집니다. 일반적으로 심각도가 높은 항목은 즉각적인 주의가 필요 합니다.<br>*정보용*, *Low*, * Medium 및 *High*값 중 하나입니다.                                                                                                                                | 보통                                                                                                                                                                                                                                            |
| 사이                                      | 인시던트에 연결 된 사용자 지정 태그의 배열로, 인시던트 그룹에 공통 특성을 지정 하는 것을 예로 들 수 있습니다.                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| 경고가                                    | 문제와 관련 된 모든 경고 및 기타 정보 (예: 경고에 포함 된 엔터티, 경고 원본)의 배열입니다.                                                                                                                                                                                                                     | \[\] (아래의 경고 필드에 대 한 세부 정보 참조)                                                                                                                                                                                                          |
| **경고 메타 데이터**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| Alertid로 변경                                   | 경고를 나타내는 고유 식별자입니다.                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| incidentId                                | 이 경고가 연결 된 인시던트를 나타내는 고유 식별자입니다.                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| servic                             | Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP 또는 Office 365 ATP와 같은 알림을 보낸 서비스입니다.                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| creationTime                              | 알림을 처음 만든 시간입니다.                                                                                                                                                                                                                                                                                                                                                         | 2020-09-06T14:46:55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | 백 엔드에서 경고가 마지막으로 업데이트 된 시간입니다.                                                                                                                                                                                                                                                                                                                                           | 2020-09-06T14:46:57.2433333 Z                                                                                                                                                                                                                      |
| resolvedTime                              | 경고가 해결 된 시간입니다.                                                                                                                                                                                                                                                                                                                                                              | 2020-09-10T05:22:59Z                                                                                                                                                                                                                              |
| firstActivity                             | 경고 처음에 작업이 백 엔드에서 업데이트 되었음을 보고 한 시간입니다.                                                                                                                                                                                                                                                                                                                             | 2020-09-04T05:22:59Z                                                                                                                                                                                                                              |
| title                                     | 각 경고에 대해 사용할 수 있는 간단한 식별 문자열 값입니다.                                                                                                                                                                                                                                                                                                                                                     | 랜 섬 웨어 활동                                                                                                                                                                                                                               |
| 설명                               | 각 경고를 설명 하는 문자열 값입니다.                                                                                                                                                                                                                                                                                                                                                        | 사용자 테스트 (testUser2@contoso.com)는 여러 확장명을 포함 하는 99 파일을 흔히 사용 되지 않는 확장 *herunterladen*로 종료 합니다. 이는 비정상적으로 발생 하는 파일 조작 수 이며 잠재적인 랜 섬 웨어 공격을 표시 합니다. |
| 범주                                  | Kill 체인을 따라 공격이 진행 된 정도에 대 한 시각적인 및 수치 보기입니다. [MITRE at&t&접시 헤드™ 프레임 워크](https://attack.mitre.org/)에 맞춥니다.                                                                                                                                                                                                                           | 영향                                                                                                                                                                                                                                            |
| 상태별                                    | 알림을 *새*, *활성*또는 *확인*된 것으로 분류 합니다. 이를 통해 경고에 대 한 응답을 구성 하 고 관리할 수 있습니다.                                                                                                                                                                                                                                                                   | 신규                                                                                                                                                                                                                                               |
| 이상인                                  | 자산에 미칠 수 있는 영향을 나타냅니다. 심각도가 높을수록 영향은 더 커집니다. 일반적으로 심각도가 높은 항목은 즉각적인 주의가 필요 합니다.<br>*정보용*, *Low*, * Medium 및 *High*값 중 하나입니다.                                                                                                                                   | 보통                                                                                                                                                                                                                                            |
| investigationId                           | 이 경고에 의해 트리거되는 자동화 된 조사 id입니다.                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | 조사의 현재 상태에 대 한 정보입니다. *알 수 없음*, *종료*됨, *SuccessfullyRemediated*, *양성*, *실패*, *PartiallyRemediated*, *실행*, *pendingapproval*, *pendingapproval*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *대기*, *innerfailure*, *preexistingalert*, *UnsupportedOs*, *unsupportedalerttype*, *SuppressedAlert*중 하나입니다. | UnsupportedAlertType                                                                                                                                                                                                                              |
| 유형을                            | 인시던트에 대 한 사양입니다. 속성 값은 *Unknown*, *FalsePositive*, *TruePositive* 또는 *null* 입니다.                                                                                                                                                                                                                                                                   | 알 수 없음                                                                                                                                                                                                                                           |
| 가져옴을                             | 문제에 대 한 결정을 지정 합니다. 속성 값은 *Notavailable*, *Apt*, *맬웨어*, *securitypersonnel*, *securitypersonnel*, *UnwantedSoftware*, *Other* 또는 *null* 입니다.                                                                                                                                                                                                     | Apt                                                                                                                                                                                                                                               |
| assignedTo                                | 인시던트의 소유자 이거나 소유자가 할당 되지 않은 경우 *null* 입니다.                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actorName                                 | 이 경고와 연결 된 활동 그룹 (있는 경우)입니다.                                                                                                                                                                                                                                                                                                                                        | BORON                                                                                                                                                                                                                                             |
| threatFamilyName                          | 이 경고와 연결 된 위협 계열입니다.                                                                                                                                                                                                                                                                                                                                                   | null                                                                                                                                                                                                                                              |
| mitreTechniques                           | [MITRE at&t&접시 헤드](https://attack.mitre.org/)™ 프레임 워크에 맞춰진 공격 기술입니다.                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| 장치                                   | 인시던트와 관련 된 알림을 보낸 모든 장치입니다.                                                                                                                                                                                                                                                                                                     | \[\] (아래 엔터티 필드에 대 한 세부 정보 참조)                                                                                                                                                                                                         |
| **장치 형식**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | Microsoft Defender ATP에 지정 된 장치 ID입니다.                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  AAD ( [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) )에 지정 된 장치 Id입니다. 도메인에 가입 된 장치에만 사용할 수 있습니다.                                                                                                                                                                                                                                                                                                                              | null                                                                                                                                                                                                                                              |
| deviceDnsName                             | 장치에 대 한 정규화 된 도메인 이름입니다.                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | 장치가 실행 되 고 있는 OS 플랫폼입니다.                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | 장치에서 실행 중인 OS의 빌드 버전입니다.                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | 장치와 연결 된 RBAC ( [역할 기반 액세스 제어](https://docs.microsoft.com/azure/role-based-access-control/overview) ) 그룹                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | 장치를 처음으로 본 시간입니다.                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06-06T14:16:01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | 장치의 상태입니다.                                                                                                                                                                                                                                                                                                                                                                        | 활성                                                                                                                                                                                                                                            |
| riskScore                                 | 장치에 대 한 위험 점수입니다.                                                                                                                                                                                                                                                                                                                                                                       | 높음                                                                                                                                                                                                                                              |
| 엔터티                                  | 지정 된 경고에 포함 되거나 연결 되는 것으로 식별 된 모든 엔터티입니다.                                                                                                                                                                                                                                                                                | \[\] (아래 엔터티 필드에 대 한 세부 정보 참조)                                                                                                                                                                                                         |
| **엔터티 형식**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| 이어야                                | 지정 된 경고에 포함 되거나이에 연결 되는 것으로 식별 된 엔터티입니다.<br>Properties 값은 *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *mailcluster*, *Registry* 입니다.                                                                                                                                                                                                     | 사용자                                                                                                                                                                                                                                              |
| sha1                                      | EntityType이 *파일인*경우에만 사용할 수 있습니다.<br>파일 또는 프로세스와 연결 된 경고에 대 한 파일 해시입니다.                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| sha256                                    | EntityType이 *파일인*경우에만 사용할 수 있습니다.<br>파일 또는 프로세스와 연결 된 경고에 대 한 파일 해시입니다.                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| 이름을                                  | EntityType이 *파일인*경우에만 사용할 수 있습니다.<br>파일 또는 프로세스와 연결 된 알림의 파일 이름입니다.                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| filePath                                  | EntityType이 *파일인*경우에만 사용할 수 있습니다.<br>파일 또는 프로세스와 연결 된 경고의 파일 경로입니다.                                                                                                                                                                                                                                                                                    | C: \\ \\ 에이전트 \\ \\ \_ 작업 \\ \\ \_ temp \\ \\ 배포 \_ 시스템 2020-09-06 12 \_ 14 \_ 54 \\ \\                                                                                                                                                                    |
| processId                                 | EntityType이 *프로세스*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | EntityType이 *프로세스*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                     | " \\ " 파일 다운로드 준비 완료 \_1911150169.exe\\ ""                                                                                                                                                                                           |
| processCreationTime                       | EntityType이 *프로세스*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T03:25:38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | EntityType이 *프로세스*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | EntityType이 *프로세스*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T02:12:32.8616797 Z                                                                                                                                                                                                                      |
| Address                                 | EntityType이 *Ip*인 경우 사용 가능 합니다. <br>네트워크 이벤트에 연결 된 경고의 IP 주소 (예: *악의적인 네트워크 대상에 대 한 통신*)                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| url                                       | EntityType이 *Url*인 경우 사용 가능 합니다. <br>네트워크 이벤트에 연결 된 경고의 Url (예: *악의적인 네트워크 대상에*대 한 통신)입니다.                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| 계정                               | EntityType 인 경우 사용 *가능 합니다.*                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| 도메인                                | EntityType 인 경우 사용 *가능 합니다.*                                                                                                                                                                                                                                                                                                                                                        | 동유럽                                                                                                                                                                                                                              |
| userSid                                   | EntityType 인 경우 사용 *가능 합니다.*                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | EntityType 인 경우 사용 *가능 합니다.*                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | EntityType이 *사용자* / *사서함* / *MailMessage*경우에만 사용할 수 있습니다.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | EntityType이 *사서함*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                     | test%                                                                                                                                                                                                                                        |
| mailboxAddress                            | EntityType이 *사용자* / *사서함* / *MailMessage*경우에만 사용할 수 있습니다.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | EntityType이  *Mailcluster*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                 | 주체 P2SenderDomain; ContentType                                                                                                                                                                                                                |
| 보낸 사람                                    | EntityType이 *사용자* / *사서함* / *MailMessage*경우에만 사용할 수 있습니다.                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| 받는 사람                                 | EntityType이 *MailMessage*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| subject                                   | EntityType이 *MailMessage*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                 | \[외부 \] 주의                                                                                                                                                                                                                            |
| deliveryAction                            | EntityType이 *MailMessage*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                 | 배달                                                                                                                                                                                                                                         |
| securityGroupId                           | EntityType이  *Securitygroup*인 경우에만 사용할 수 있습니다.                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-ab09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | EntityType이  *Securitygroup*인 경우에만 사용할 수 있습니다.                                                                                                                                                                                                                                                                                                                                               | 네트워크 구성 운영자                                                                                                                                                                                                                   |
| registryHive                              | EntityType이  *Registry*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                    | HKEY \_ 로컬 \_ 컴퓨터                                                                                                                                                                                                                              |
| registryKey                               | EntityType이  *Registry*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                     | 소프트웨어 \\ \\ MICROSOFT \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | EntityType이  *Registry*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                    | 문자열                                                                                                                                                                                                                                            |
| registryValue                             | EntityType이  *Registry*인 경우 사용 가능 합니다.                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | 엔터티와 관련 된 장치의 ID (있는 경우)입니다.                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>예제

**요청이**

```
GET https://api.security.microsoft.com/api/incidents
```

**응답률**
```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-topic"></a>관련 항목
- [인시던트 Api](api-incident.md)
- [인시던트 업데이트](api-update-incidents.md)
