---
title: Microsoft 365 수비수에 인시던트 API 목록
description: Microsoft 365 Defender에서 인시던트 API를 나열하는 방법 알아보기
keywords: 목록, 인시던트, 인시던트, API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572156"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Microsoft 365 수비수에 인시던트 API 목록

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.


## <a name="api-description"></a>API 설명

목록 인시던트 API를 사용하면 인시던트를 정렬하여 정보에 입각한 사이버 보안 응답을 만들 수 있습니다. 환경 보존 정책에 지정한 시간 범위 내에서 네트워크에 플래그가 지정된 인시던트 컬렉션을 노출합니다. 가장 최근의 인시던트는 목록의 맨 위에 표시됩니다. 각 인시던트에는 관련 경고 배열과 관련 엔터티가 포함됩니다.

API는 다음과 같은 **OData** 연산업체를 지원합니다.

- `$filter` 에 `lastUpdateTime` `createdTime` , `status` 및 `assignedTo` 속성
- `$top`최대 **값100**
- `$skip`

## <a name="limitations"></a>제한 사항

1. 최대 페이지 크기는 **100인시입니다.**
2. 최대 요청 속도는 **분당 50회 통화,** **시간당 1,500건의 통화입니다.**

## <a name="permissions"></a>권한

다음 권한 중 하나는 이 API를 호출해야 합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [액세스 Microsoft 365 수비수 API를 참조하십시오.](api-access.md)

권한 유형 | 사용 권한 | 권한 표시 이름
-|-|-
응용 프로그램 | 사건.읽기.모든 | 모든 인시던트 읽기
응용 프로그램 | 인시던트.읽기쓰기.모든 것 | 모든 인시던트 읽기 및 쓰기
위임(직장 또는 학교 계정) | 인시던트.읽기 | 인시던트 읽기
위임(직장 또는 학교 계정) | 인시던트.읽기 | 인시던트 읽기 및 쓰기

> [!Note]
> 사용자 자격 증명을 사용하여 토큰을 획득하는 경우:
>
> - 사용자는 포털에서 인시던트에 대한 보기 권한이 있어야 합니다.
> - 응답에는 사용자가 노출되는 인시던트만 포함됩니다.

## <a name="http-request"></a>HTTP 요청

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
-|-|-
권한 부여 | 문자열 | 베어러 {토큰}. **필수**


## <a name="request-body"></a>요청 본문

없음

## <a name="response"></a>응답

성공하면 이 `200 OK` 메서드가 반환되고 응답 본문에 [인시던트](api-incident.md) 목록이 표시됩니다.

## <a name="schema-mapping"></a>스키마 매핑

### <a name="incident-metadata"></a>인시던트 메타데이터

필드 이름 | 설명 | 예제 값
-|-|-
인시던트Id | 인시던트를 나타내는 고유 식별자 | 924565
리디렉션우연히이드 | 인시던트 처리 논리의 일부로 인시던트가 다른 인시던트와 함께 그룹화되는 경우에만 채워집니다. | 924569
인시던트 이름 | 모든 인시던트에 사용할 수 있는 문자열 값입니다. | 랜섬웨어 활동
만든 시간 | 인시던트를 처음 만든 시간입니다. | 2020-09-06T14:46:57.0733333Z
마지막 업데이트 시간 | 백엔드에서 사건이 마지막으로 업데이트된 시간입니다.<br /><br /> 이 필드는 인시던트가 검색되는 시간 범위에 대한 요청 매개 변수를 설정할 때 사용할 수 있습니다. | 2020-09-06T14:46:57.29Z
할당To | 인시던트 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.* | secop2@contoso.com
분류 | 인시던트 사양입니다. 속성 값은 다음과 같습니다: *알 수 없는,* *거짓 긍정,* *TruePositive* | 알 수 없음
결심 | 인시던트 의 결정을 지정합니다. 속성 값은 다음과 같습니다 사용할 *수 없음,* *Apt,* *악성 코드,* *보안 담당자,* *보안 테스트,* *원치 않는 소프트웨어,* *기타* | 사용할 수 없음
상태 | 인시던트를 *분류합니다(활성* 또는 *해결됨).* 그것은 당신이 조직하고 인시던트에 대한 응답을 관리하는 데 도움이 될 수 있습니다. | 활성
심각도 | 자산에 미치는 영향을 나타냅니다. 심각도가 높을수록 영향이 커지를 수 있습니다. 일반적으로 심각도가 높을수록 가장 즉각적인 주의가 필요합니다.<br /><br />다음 값 중 하나: *정보, 낮음,**중간 값 및 *높음*.  | 보통
태그 | 인시던트와 관련된 사용자 지정 태그배열(예: 공통 특성을 가진 인시던트 그룹에 플래그지정). | \[\]
코멘트 | 인시던트를 관리할 때 secops에서 만든 주석 배열(예: 분류 선택에 대한 추가 정보). | \[\]
경고 | 인시던트와 관련된 모든 경고와 심각도, 경고에 관련된 엔터티 및 경고소스와 같은 기타 정보가 포함된 배열입니다. | \[\] (아래 경고 필드에 대한 세부 정보 참조)

### <a name="alerts-metadata"></a>알림 메타데이터

필드 이름 | 설명 | 예제 값
-|-|-
경고Id | 경고를 나타내는 고유 식별자 | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
인시던트Id | 이 경고가 연관된 인시던트를 나타내는 고유 식별자 | 924565
서비스 소스 | 엔드포인트에 대한 Microsoft Defender, Microsoft Cloud App Security, 신원에 대한 Microsoft 수비수 또는 Office 365 대한 Microsoft Defender와 같이 경고가 시작된 서비스입니다. | 마이크로소프트클라우드앱시큐리티
창조시간 | 경고가 처음 생성된 시간입니다. | 2020-09-06T14:46:55.7182276Z
마지막 업데이트 시간 | 백엔드에서 경고가 마지막으로 업데이트된 시간입니다. | 2020-09-06T14:46:57.2433333Z
해결시간 | 경고가 해결된 시간입니다. | 2020-09-10T05:22:59Z
첫 번째 활동 | 경고가 백엔드에서 활동이 업데이트되었다고 처음 보고한 시간입니다.| 2020-09-04T05:22:59Z
title | 각 경고에 사용할 수 있는 문자열 값을 간략하게 식별합니다. | 랜섬웨어 활동
설명 | 각 경고를 설명하는 문자열 값입니다. | 사용자 테스트 User2(testUser2@contoso.com)는 99개의 파일을 조작하여 여러 개의 확장이 드문 확장 으로 끝나는 *경우를 대지* 않습니다. 이것은 파일 조작의 특이한 수이며 잠재적 인 랜섬웨어 공격을 나타냅니다.
범주 | 공격이 킬 체인을 따라 얼마나 진행되었는지에 대한 시각적 이고 숫자보기입니다. [MITRE ATT&CK™ 프레임워크에](https://attack.mitre.org/)정렬됩니다. | 영향
상태 | 경고를 *분류합니다(새,* *활성* 또는 *해결됨).* 경고에 대한 응답을 구성하고 관리하는 데 도움이 될 수 있습니다. | 신규
심각도 | 자산에 미치는 영향을 나타냅니다. 심각도가 높을수록 영향이 커지를 수 있습니다. 일반적으로 심각도가 높을수록 가장 즉각적인 주의가 필요합니다.<br>다음 값 중 하나: *정보, 낮음,**중간 값 및 *높음*.  | 보통
조사 Id | 이 경고로 트리거된 자동 조사 ID입니다. | 1234
조사 상태 | 조사의 현재 상태에 대한 정보입니다. 다음 값 중 하나 : *알 수없는,* *종료,* *성공적으로 Remediated,* *양성,* *실패,* *부분적으로 Remediated,* *실행,* *보류 중인 승인, 보류* *자원,* *부분적으로 조사,* *종료ByUser,* *종료BySystem,* *대기열,* *내부 실패,* *기존 경고,* *지원되지* 않는 *경고 유형,* 억제 *경고.* | 지원되지 않는 경고 유형
분류 | 인시던트 사양입니다. 속성 값은 다음과 같습니다: *알 수 없음,* *거짓 긍정,* *TruePositive* 또는 *null* | 알 수 없음
결심 | 인시던트 의 결정을 지정합니다. 속성 값은 다음과 같습니다 사용할 *수 없음,* *Apt,* *악성 코드,* *보안 담당자,* *보안 테스트,* *원치 않는 소프트웨어,* *기타* 또는  *null* | Apt
할당To | 인시던트 소유자 또는 소유자가 할당되지 않은 경우 *null입니다.* | secop2@contoso.com
배우 이름 | 이 경고와 연결된 활동 그룹(있는 경우)입니다. | 붕소
위협가족이름 | 이 경고와 관련된 위협 패밀리입니다. | null
미트레테크닉 | [MITRE ATT&CK](https://attack.mitre.org/)™ 프레임워크와 정렬된 공격 기술입니다. | \[\]
장치 | 인시던트와 관련된 경고가 전송된 모든 장치입니다. | \[\] (아래 엔터티 필드에 대한 세부 정보 참조)

### <a name="device-format"></a>장치 형식

필드 이름 | 설명 | 예제 값
-|-|-
DeviceId | 엔드포인트에 대한 Microsoft Defender에 지정된 장치 ID입니다. | 24c222b0b60fe148eece49ac83910cc6a7ef491
aadDeviceId |  [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)지정된 장치 ID. 도메인에 가입한 장치에서만 사용할 수 있습니다. | null
장치DnsName | 장치에 대한 완전히 인증된 도메인 이름입니다. | user5cx.middleeast.corp.contoso.com
오스 플랫폼 | 장치가 실행 중인 OS 플랫폼입니다.| 윈도우 서버2016
osBuild | 장치가 실행 중인 OS의 빌드 버전입니다. | 14393
rbac그룹이름 | 장치와 연결된 역할 기반 액세스 제어(RBAC) 그룹입니다. [](/azure/role-based-access-control/overview) | WDATP-Ring0
첫 번째 본 | 장치가 처음 본 시간입니다. | 2020-02-06T14:16:01.9330135Z
건강 상태 | 장치의 상태입니다. | 활성
위험점수 | 장치의 위험 점수입니다. | 높음
엔터티 | 지정된 경고의 일부 또는 관련 것으로 확인된 모든 엔터티입니다. | \[\] (아래 엔터티 필드에 대한 세부 정보 참조)

### <a name="entity-format"></a>엔터티 형식

필드 이름 | 설명 | 예제 값
-|-|-
엔터티Type | 지정된 경고의 일부 또는 관련 것으로 확인된 엔터티입니다.<br>속성 값은 : *사용자,* *IP,* *URL,* *파일,* *프로세스,* *사서함,* *사서 함,* *우편 클러스터,* *레지스트리* | 사용자
샤1 | 엔터티Type이 *파일인* 경우 사용할 수 있습니다.<br>파일 또는 프로세스와 연결된 경고에 대한 파일 해시입니다. | 5de839186691aa96e2ca6d74f0a38fb8d1bd6dd
샤256 | 엔터티Type이 *파일인* 경우 사용할 수 있습니다.<br>파일 또는 프로세스와 연결된 경고에 대한 파일 해시입니다. | 28cb017dfc907a1b477c1b30f413e3ce7744c49991eb4158de50f9dbb36d80433
파일 | 엔터티Type이 *파일인* 경우 사용할 수 있습니다.<br>파일 또는 프로세스와 연결된 경고의 파일 이름 | Detector.UnitTests.dll
파일 경로 | 엔터티Type이 *파일인* 경우 사용할 수 있습니다.<br>파일 또는 프로세스와 연결된 경고에 대한 파일 경로 | C: \\ \agent_work_temp\배포\시스템\2020-09-06 12_14_54\Out
프로세스Id | 엔터티Type이 *프로세스인* 경우 사용할 수 있습니다. | 24348
프로세스 커맨드라인 | 엔터티Type이 *프로세스인* 경우 사용할 수 있습니다. | "파일은1911150169.exe 다운로드할 준비가 \_ 되었습니다."
프로세스창조시간 | 엔터티Type이 *프로세스인* 경우 사용할 수 있습니다. | 2020-07-18T03:25:38.5269993Z
부모 프로세스Id | 엔터티Type이 *프로세스인* 경우 사용할 수 있습니다. | 16840
부모 프로세스 창조시간 | 엔터티Type이 *프로세스인* 경우 사용할 수 있습니다. | 2020-07-18T02:12:32.8616797Z
ipAddress | 엔터티Type이 Ip인 경우 사용할 수 *있습니다.* <br>*악성 네트워크 대상에* 대한 통신과 같은 네트워크 이벤트와 관련된 경고에 대한 IP 주소입니다. | 62.216.203.204
URL | 엔터티Type이 *URL인* 경우 사용할 수 있습니다. <br>*악성 네트워크 대상에* 대한 통신과 같은 네트워크 이벤트와 관련된 경고에 대한 URL입니다. | down.esales360.cn
계정 이름 | 엔터티Type이 *사용자인* 경우 사용할 수 있습니다. | testUser2
도메인 이름 | 엔터티Type이 *사용자인* 경우 사용할 수 있습니다. | europe.corp.contoso
사용자 시드 | 엔터티Type이 *사용자인* 경우 사용할 수 있습니다. | S-1-5-21-1721254763-462695806-153882281-4156657
아드두이지드 | 엔터티Type이 *사용자인* 경우 사용할 수 있습니다. | fc8f7484-f813-4db2-afab-bc1507913fb6
사용자PrincipalName | 엔터티Type이 *사용자* / *사서함* / *사서메시지인* 경우 사용할 수 있습니다. | testUser2@contoso.com
사서함디스플레이이름 | 엔터티Type이 *사서함인* 경우 사용할 수 있습니다. | 테스트 사용자2
사서함 주소 지정 | 엔터티Type이 *사용자* / *사서함* / *사서메시지인* 경우 사용할 수 있습니다. | testUser2@contoso.com
클러스터바이 | 엔터티Type이  *메일클러스터인* 경우 사용할 수 있습니다. | 주제; P2센더도메인; 콘텐츠 유형
보낸 사람 | 엔터티Type이 *사용자* / *사서함* / *사서메시지인* 경우 사용할 수 있습니다. | user.abc@mail.contoso.co.in
받는 사람 | 엔터티Type이 *메일메시지인* 경우 사용할 수 있습니다. | testUser2@contoso.com
subject | 엔터티Type이 *메일메시지인* 경우 사용할 수 있습니다. | \[외부 \] 주의
배달 조치 | 엔터티Type이 *메일메시지인* 경우 사용할 수 있습니다. | 배달
보안 그룹Id | 엔터티Type이  *보안 그룹인* 경우 사용할 수 있습니다. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
보안 그룹 이름 | 엔터티Type이  *보안 그룹인* 경우 사용할 수 있습니다. | 네트워크 구성 연산자
레지스트리하이브 | 엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.* | HKEY \_ 로컬 \_ 기계 |
레지스트리 키 | 엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.* | 소프트웨어\마이크로소프트\Windows NT\현재버전\윈로곤
레지스트리 값 유형 | 엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.* | 문자열
레지스트리값 | 엔터티Type이 레지스트리인 경우 사용할 수 *있습니다.* | 31-00-00-00
장치Id | 엔터티와 관련된 장치의 ID(있는 경우)입니다. | 986e5df8b73dacd43c8917e523e76b13c75cd

## <a name="example"></a>예제

**요청**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**응답**

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 수비수 API에 액세스](api-access.md)
- [API 제한 및 라이선스에 대해 알아보기](api-terms.md)
- [오류 코드 이해](api-error-codes.md)
- [인시던트 개요](incidents-overview.md)
- [인시던트 API](api-incident.md)
- [인시던트 API 업데이트](api-update-incidents.md)
