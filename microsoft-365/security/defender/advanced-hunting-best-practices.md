---
title: 고급 헌팅 쿼리의 모범 Microsoft 365 Defender
description: 고급 헌팅을 사용하여 빠르고 효율적이며 오류가 없는 위협 헌팅 쿼리를 생성하는 방법을 학습합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema, kusto, 시간 제한 방지, 명령줄, 프로세스 ID, 최적화, 모범 사례, 구문 분석, 참가, 요약
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae2e7fb960dd8ce2a42ce62fe0b8da7675e00ce5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189349"
---
# <a name="advanced-hunting-query-best-practices"></a>고급 헌팅 쿼리 모범 사례

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

이러한 권장 사항을 적용하여 결과를 더 빠르게 얻고 복잡한 쿼리를 실행하는 동안 시간 제한을 방지합니다. 쿼리 성능을 개선하는 방법에 대한 자세한 내용은 [Kusto 쿼리 모범 사례](/azure/kusto/query/best-practices)를 참조하세요.

## <a name="understand-cpu-resource-quotas"></a>CPU 리소스 할당량 이해
크기에 따라 각 테넌트는 고급 헌팅 쿼리를 실행하기 위해 할당된 CPU 리소스 집합에 액세스할 수 있습니다. 다양한 서비스 제한에 대한 자세한 내용은 고급 헌팅 할당량 및 사용 매개 변수 를 [참조하세요.](advanced-hunting-limits.md)

여러 쿼리를 정기적으로 실행하는 고객은 사용을 추적하고 이 문서의 최적화 지침을 적용하여 할당량 또는 사용 매개 변수 초과로 인한 중단을 최소화해야 합니다.

## <a name="general-optimization-tips"></a>일반 최적화 팁

- **새 쿼리** 크기 -쿼리가 큰 결과 집합을 반환하는 것으로 의심되는 경우 먼저 개수 연산자를 사용하여 [평가합니다.](/azure/data-explorer/kusto/query/countoperator) 제한 [또는](/azure/data-explorer/kusto/query/limitoperator) 동의어를 사용하여 큰 결과 집합을 `take` 방지합니다.
- **필터를** 초기에 적용 - 특히 [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)또는 [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction)등의 변환 및 구문 분석 함수를 사용하기 전에 데이터 집합을 줄이기 위해 시간 필터 및 기타 필터를 적용합니다. 아래 예제에서는 필터링 연산자가 레코드 수를 줄인 후 구문 분석 함수 [extractjson()이](/azure/data-explorer/kusto/query/extractjsonfunction) 사용됩니다.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **비트에 포함**- 단어 내에서 하위 스트링을 불필요하게 검색하지 않도록 에는 대신 `has` 연산자를 `contains` 사용합니다. [문자열 연산자에 대한 자세한 내용은](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **특정 열을 찾아**-모든 열에서 전체 텍스트 검색을 실행하는 대신 특정 열을 살펴 봐야 합니다. 모든 열을 `*` 검사하는 데는 사용하지 않습니다.
- **속도에 대한 대소문자** 구분 - 대소문자 구분 검색은 보다 구체적이며 일반적으로 더 많은 기능을 합니다. 대소문자 구분 [문자열](/azure/data-explorer/kusto/query/datatypes-string-operators)연산자(예: `has_cs` 및)의 `contains_cs` 이름은 일반적으로 로 `_cs` 끝됩니다. 대신 대소문자 구분 등호 연산자를 사용할 `==` 수 `=~` 있습니다.
- **구문 분석,** 추출 안 하세요 . [](/azure/data-explorer/kusto/query/parseoperator) 가능한 경우 구문 분석 연산자 또는 [parse_json() 같은 구문 분석 함수를 사용하세요.](/azure/data-explorer/kusto/query/parsejsonfunction) 정규식을 사용하는 문자열 `matches regex` [연산자나 extract()](/azure/data-explorer/kusto/query/extractfunction)함수는 사용하지 않습니다. 좀 더 복잡한 시나리오에서는 정규식을 사용할 수 있습니다. [구문 분석 함수에 대한 자세한 내용을 읽어 읽습니다.](#parse-strings)
- **식이 아닌** 필터 테이블 - 테이블 열을 필터링할 수 있는 경우 계산된 열에는 필터링하지 않습니다.
- **3자 용어** 없음 - 3자 이하의 용어를 사용하여 비교하거나 필터링하지 않습니다. 이러한 용어는 인덱싱되지 않습니다. 이러한 용어와 일치하면 더 많은 리소스가 필요합니다.
- **Project 선택적으로**-필요한 열만 투영하여 결과를 보다 쉽게 이해할 수 있도록 합니다. 조인 또는 유사한 작업을 [](/azure/data-explorer/kusto/query/joinoperator) 실행하기 전에 특정 열을 투영하면 성능을 개선하는 데도 도움이 됩니다.

## <a name="optimize-the-join-operator"></a>연산자 `join` 최적화
조인 [연산자는](/azure/data-explorer/kusto/query/joinoperator) 지정된 열의 값과 일치하여 두 테이블의 행을 병합합니다. 다음 팁을 적용하여 이 연산자를 사용하는 쿼리를 최적화합니다.

- **왼쪽에 작은** 테이블 - 연산자는 조인 문 왼쪽에 있는 테이블의 레코드를 오른쪽의 레코드와 `join` 일치합니다. 테이블을 왼쪽에 두면 더 적은 수의 레코드를 일치해야 하여 쿼리 속도를 향상할 수 있습니다.

    아래 표에서는 계정 SID로 연결하기 전에 세 개의 특정 장치만 다루기 위해 왼쪽 테이블을 `DeviceLogonEvents` `IdentityLogonEvents` 줄입니다.

    ```kusto
    DeviceLogonEvents
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- **안쪽 조인** 특징 사용 [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) - 오른쪽 표에 일치하는 각 행을 반환하기 전에 왼쪽 표의 기본 조인 특징 또는 내부 [유니크](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) 조인 중복 제거 행을 조인 키로 제거합니다. 왼쪽 표에 키 값이 같은 행이 여러 개 있는 경우 해당 행은 중복 제거하여 각 고유 값에 대해 단일 임의의 행을 `join` 남기게 됩니다.

    이 기본 동작은 유용한 정보를 제공할 수 있는 중요한 정보를 왼쪽 표에 남길 수 있습니다. 예를 들어 아래 쿼리는 동일한 첨부 파일이 여러 전자 메일 메시지를 사용하여 전송된 경우에도 특정 첨부 파일이 포함된 전자 메일 하나만 표시됩니다.

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    이 제한을 해결하기 위해 [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 왼쪽 테이블의 모든 행이 오른쪽에 일치하는 값을 표시하는 것으로 지정하여 내부 조인 형식을 `kind=inner` 적용합니다.

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- **시간 창에서** 레코드에 참가 - 보안 이벤트를 조사할 때 분석가가 같은 기간에 발생하는 관련 이벤트를 검색합니다. 또한 사용할 때 동일한 방법을 적용하면 확인할 레코드 수를 줄여 성능이 `join` 향상됩니다.

    아래 쿼리는 악성 파일을 수신한 후 30분 이내에 로그온 이벤트를 검사합니다.

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **양쪽에** 시간 필터 적용 - 특정 시간 창을 조사하지 않는 경우에도 왼쪽 테이블과 오른쪽 테이블 모두에 시간 필터를 적용하면 레코드 수를 줄이고 성능을 향상시킬 수 `join` 있습니다. 아래 쿼리는 지난 한 시간의 레코드만 조인할 수 있도록 두 테이블에 `Timestamp > ago(1h)` 모두 적용됩니다.

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- **성능에 대한 힌트** 사용 - 연산자와 힌트를 사용하여 리소스를 많이 사용하는 작업을 실행하는 경우 백end에 부하를 분산할 `join` 수 있도록 지시합니다. [조인 힌트에 대해 자세히 알아보시고](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    예를 들어 **[](/azure/data-explorer/kusto/query/shufflequery)** 셔플 힌트는 기수 값이 많은 키(예: 아래 쿼리의 키)를 사용하여 테이블을 조인할 때 쿼리 성능을 `AccountObjectId` 향상시키는 데 도움이 됩니다.

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    **[브로드캐스트](/azure/data-explorer/kusto/query/broadcastjoin)** 힌트는 왼쪽 테이블이 작고(최대 100,000개 레코드) 오른쪽 테이블이 매우 큰 경우 도움이 됩니다. 예를 들어 아래 쿼리는 표의 링크가 포함된 모든 메시지에  특정 제목이 있는 몇 가지 전자 메일에 참가하려고 `EmailUrlInfo` 합니다.

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a>연산자 `summarize` 최적화
요약 [연산자는](/azure/data-explorer/kusto/query/summarizeoperator) 테이블의 내용을 집계합니다. 다음 팁을 적용하여 이 연산자를 사용하는 쿼리를 최적화합니다.

- **고유한 값 찾기**- 일반적으로 반복할 수 있는 고유한 값을 찾는 `summarize` 데 사용합니다. 이 값을 사용하여 반복 값이 없는 열을 집계할 필요가 없습니다.

    단일 전자 메일이 여러 이벤트의 일부가  될 수 있는 반면, 개별 전자 메일의 네트워크 메시지 ID에는 항상 고유한 보낸 사람 주소가 있기 때문에 아래 예제에서는 효율적이지 `summarize` 않습니다.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    연산자를 으로 쉽게 대체할 수 있습니다. 그러면 더 적은 리소스를 사용하면서 잠재적으로 동일한 결과를 `summarize` `project` 얻을 수 있습니다.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    다음 예에서는 동일한 받는 사람 주소로 전자 메일을 보내는 보낸 사람 주소의 고유한 인스턴스가 여러 개 있을 수 있기 때문에 보다 효율적으로 `summarize` 사용할 수 있습니다. 이러한 조합은 고유하지 않습니다. 중복 항목일 가능성이 뚜렷합니다.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- **쿼리 셔플**-을(를) 반복적인 값을 사용하는 열에 사용하는 것이 가장 좋은 반면 동일한 열에는 기수도 높거나 고유 값이 많이 사용될 `summarize` 수 있습니다.  연산자와 마찬가지로 처리 부하를 분산하고 카디널리티가 높은 열에서 작업할 때 성능을 잠재적으로 개선하기 위해 셔플 힌트를 적용할 `join` 수도 [](/azure/data-explorer/kusto/query/shufflequery) `summarize` 있습니다.

    아래 쿼리는 수만 개의 대규모 조직에서 실행할 수 있는 고유한 받는 사람 전자 메일 주소의 개수를 `summarize` 계산하는 데 사용합니다. 성능을 향상하기 위해 다음을 `hint.shufflekey` 통합합니다.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>쿼리 시나리오

### <a name="identify-unique-processes-with-process-ids"></a>프로세스 ID를 사용하여 고유한 프로세스 식별
PID(프로세스 ID)는 Windows에서 재활용할 수 있으며 새 프로세스를 위해 다시 사용됩니다. 즉, 특정 프로세스에 대한 고유 식별자로는 사용할 수 없습니다.

특정 컴퓨터에서 프로세스에 대한 고유 식별자를 얻으려면 프로세스 생성 시간과 함께 프로세스 ID를 사용합니다. 프로세스 주변의 데이터를 합치거나 요약할 때는 컴퓨터 식별자에 대한 열 (`DeviceId` 또는 `DeviceName`), 프로세스 ID (`ProcessId` 또는 `InitiatingProcessId`), 프로세스 만들기 시간 (`ProcessCreationTime` 또는 `InitiatingProcessCreationTime`)을 포함합니다.

다음의 예제 쿼리는 포트 445(SMB)를 통해 10 개가 넘는 IP 주소에 액세스하는 프로세스를(잠정적으로 파일 공유를 검색하며) 찾습니다.

쿼리 예제:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

쿼리는 여러 프로세스를 동일한 프로세스 ID와 함께 사용하지 않고 단일 프로세스를 보여주는 `InitiatingProcessId`과 `InitiatingProcessCreationTime` 모두에 대해 요약을 합니다.

### <a name="query-command-lines"></a>쿼리 명령줄
여러 가지 방법으로 작업을 수행할 수 있는 명령줄을 만들 수 있습니다. 예를 들어 공격자는 파일 확장명 없이 환경 변수를 사용하거나 따옴표를 사용하여 경로 없이 이미지 파일을 참조할 수 있습니다. 또한 공격자는 매개 변수 순서를 변경하거나 여러 따옴표와 공백을 추가할 수 있습니다.

명령줄에 대해 지속적 쿼리를 더 많이 만들 수 있는 방법은 다음과 같습니다.

- 명령줄 자체를 필터링하는 대신 ** 파일 이름 *필드에* 일치하여 알려진 프로세스(예:net.exe또는psexec.exe)를 식별합니다.
- parse_command_line 함수를 사용하여 [명령줄 섹션 구문](/azure/data-explorer/kusto/query/parse-command-line) 분석
- 명령줄 인수에 대해 쿼리할 때 관련이 없는 여러 인수에서 특정 순서로 정확하게 일치하는 항목을 찾지 마세요. 대신 정규 표현식을 사용하거나 별도의 여러 포함 연산자를 사용합니다.
- 대/소문자를 구분하지 않는 일치 항목을 사용합니다. 예를 들어 , 및 대신 `=~` `in~` , `contains` `==` `in` 를 `contains_cs` 사용합니다.
- 명령줄 난침 기술을 완화하기 위해 따옴표를 제거하고, 콤보를 공백으로 바꾸고, 여러 개의 연속된 공백을 단일 공백으로 바꾸는 것이 고려됩니다. 다른 접근 방식이 필요한 더 복잡한 난 난급법이 있지만 이러한 조정을 통해 일반적인 문제를 해결할 수 있습니다.

다음 예에서는 방화벽 서비스 "MpsSvc"를net.exe파일을 검색하는 쿼리를 생성하는 다양한 방법을 보여집니다. 

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc"

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc"
```

### <a name="ingest-data-from-external-sources"></a>외부 원본에서 데이터 수집
긴 목록이나 큰 테이블을 쿼리에 통합하기 위해 [externaldata](/azure/data-explorer/kusto/query/externaldata-operator) 연산자를 사용하여 지정된 URI에서 데이터를 수집합니다. TXT, CSV, JSON 또는 기타 형식의 파일에서 데이터를 얻을 [수 있습니다.](/azure/data-explorer/ingestion-supported-formats) 아래 예제에서는 MalwareBazaar(abuse.ch)에서 제공하는 맬웨어 SHA-256 해시의 광범위한 목록을 사용하여 전자 메일의 첨부 파일을 검사하는 방법을 보여줍니다.

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string)
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo
| where Timestamp > ago(1d)
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>문자열 구문 분석
구문 분석 또는 변환이 필요한 문자열을 효율적으로 처리하는 데 사용할 수 있는 다양한 함수가 있습니다.

| 문자열 | 함수 | 사용 예제 |
|--|--|--|
| 명령줄 | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | 명령과 모든 인수를 추출합니다. |
| 경로 | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | 파일 또는 폴더 경로의 섹션을 추출합니다. |
| 버전 번호 | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | 섹션당 최대 4개의 섹션과 섹션당 최대 8자까지 버전 번호를 해제합니다. 구문 분석된 데이터를 사용하여 버전 나이를 비교합니다. |
| IPv4 주소 | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | IPv4 주소를 긴 정수로 변환합니다. IPv4 주소를 변환하지 않고 비교하기 위해 [ipv4_compare() 를 사용합니다.](/azure/data-explorer/kusto/query/ipv4-comparefunction) |
| IPv6 주소 | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | IPv4 또는 IPv6 주소를 정형 IPv6로 변환합니다. IPv6 주소를 비교하기 위해 [ipv6_compare() 를 사용합니다.](/azure/data-explorer/kusto/query/ipv6-comparefunction) |

지원되는 모든 구문 분석 함수에 대한 자세한 내용은 [Kusto 문자열 함수 를 읽어 보아야 합니다.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)

>[!NOTE]
>이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다. [더 많은 Microsoft 365 Defender](m365d-enable.md) 사용하여 위협을 헌팅할 수 있습니다. Endpoint용 Microsoft Defender에서 고급 헌팅 Microsoft 365 Defender [Microsoft Defender에서](advanced-hunting-migrate-from-mde.md)고급 헌팅 쿼리 마이그레이션의 단계를 수행하여 고급 헌팅 워크플로를 끝점으로 이동할 수 있습니다.

## <a name="related-topics"></a>관련 항목
- [Kusto 쿼리 언어 설명서](/azure/data-explorer/kusto/query/)
- [할당량 및 사용량 매개 변수](advanced-hunting-limits.md)
- [고급 헌팅 오류 처리](advanced-hunting-errors.md)
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)