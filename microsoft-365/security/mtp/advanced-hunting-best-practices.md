---
title: Microsoft Threat Protection의 고급 구하기 쿼리 모범 사례
description: 고급 구하기로 빠르고 효율적이 고 오류 없는 위협 구하기 쿼리를 구성 하는 방법을 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마, kusto, timeout,, 명령 줄, 프로세스 id, optimize, 모범 사례, 구문 분석, 조인, 요약
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
ms.openlocfilehash: e3b29a8182e38fa05e5f791478157c978632fb13
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477008"
---
# <a name="advanced-hunting-query-best-practices"></a>고급 헌팅 쿼리 모범 사례

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft Threat Protection

이러한 권장 사항을 적용 하 여 결과를 더 빠르게 얻고 복잡 한 쿼리를 실행 하는 동안 시간 제한을 방지 합니다. 쿼리 성능을 개선하는 방법에 대한 자세한 내용은 [Kusto 쿼리 모범 사례](https://docs.microsoft.com/azure/kusto/query/best-practices)를 참조하세요.

## <a name="understand-cpu-resource-limits"></a>CPU 리소스 제한 이해
각 테 넌 트의 크기에 따라 고급 구하기 쿼리를 실행 하는 데 할당 된 CPU 리소스 집합에 액세스할 수 있습니다. 다양 한 서비스 제한에 대 한 자세한 내용은 [고급 구하기 제한](advanced-hunting-limits.md)정보를 참조 하세요.

정기적으로 여러 쿼리를 실행 하는 고객은 사용을 추적 하 고이 문서의 최적화 지침을 적용 하 여 제한을 초과 하 여 발생 하는 혼란을 최소화 해야 합니다.

## <a name="general-optimization-tips"></a>일반 최적화 팁

- **크기 새 쿼리**-쿼리가 큰 결과 집합을 반환 하는 것으로 의심 되는 경우에는 [count 연산자](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)를 사용 하 여 먼저 쿼리를 평가 합니다. 결과 집합이 커지지 않도록 [제한](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 또는 해당 동의어 `take` 를 사용 합니다.
- **필터 적용 초기 단계**-특히 변환 및 구문 분석 함수 (예: [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper (](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)) 또는 [parse_json)](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)를 사용 하기 전에 데이터 집합을 줄이기 위한 시간 필터 및 기타 필터를 적용 합니다. 아래 예제에서는 필터링 연산자가 레코드 수를 낮춘 후 구문 분석 함수 [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) 을 사용 합니다.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **이 비트 포함**-단어 내의 하위 문자열을 불필요 하 게 검색 하지 않으려면 `has` 대신 연산자를 사용 `contains` 합니다. [문자열 연산자에 대 한 자세한 정보](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **특정 열에서 찾기**-모든 열에서 전체 텍스트 검색을 실행 하는 것이 아니라 특정 열에서 찾습니다. `*`모든 열을 확인 하는 데 사용 하지 않습니다.
- **속도를 중요**하 게 구분-대/소문자 구분 검색은 보다 구체적이 고 일반적으로 성능이 더 좋습니다. And와 같이 일반적으로 끝나는와 같은 대/소문자 구분 [문자열 연산자](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)의 이름 `has_cs` `contains_cs` `_cs` 입니다. 대신 대/소문자를 구분 하는 equals 연산자를 사용할 수도 있습니다 `==` `=~` .
- **구문 분석,** 가능한 경우 parse [연산자](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 또는 [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)와 같은 구문 분석 함수를 사용 합니다. `matches regex`정규식을 사용 하는 문자열 연산자나 [extract () 함수](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)는 사용할 필요가 없습니다. 좀 더 복잡 한 시나리오의 경우 정규식 사용을 예약 합니다. [구문 분석 함수에 대 한 자세한 정보](#parse-strings)
- 테이블 열을 기준으로 필터링 할 수 있는 경우에는 계산 된 열을 필터링 **하지 않습니다.**
- **세 문자 용어 없음**-세 개 이하의 용어를 사용 하 여 비교 하거나 필터링 하지 않습니다. 이러한 용어는 인덱싱되지 않으며 일치 하지 않으므로 리소스가 더 많이 필요 합니다.
- **Project 선택적**-필요한 열만 프로젝션 하 여 결과를 보다 쉽게 이해할 수 있도록 합니다. [Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 또는 유사 작업을 실행 하기 전에 특정 열을 프로젝션 하면 성능도 향상 됩니다.

## <a name="optimize-the-join-operator"></a>교환원 최적화 `join`
[Join 연산자](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 는 지정 된 열의 값을 일치 시켜 두 테이블의 행을 병합 합니다. 이 연산자를 사용 하는 쿼리를 최적화 하려면 다음 팁을 적용 합니다.

- **왼쪽에 대 한 작은 테이블**-이 `join` 연산자는 join 문의 왼쪽에 있는 테이블의 레코드를 오른쪽의 레코드와 일치 시킵니다. 왼쪽에 작은 표가 있으므로 일치 해야 하는 레코드가 줄어들어 쿼리 속도가 빨라집니다. 

    아래 표에서는 `DeviceLogonEvents` 계정 sid로 연결 하기 전에 세 가지 특정 장치만 포함 하도록 왼쪽 테이블을 줄입니다 `IdentityLogonEvents` .
 
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

- **내부 조인 버전 사용**-기본 [조인 버전](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) 또는 [innerunique 조인](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) 에서는 right 테이블의 각 일치 항목에 대해 행을 반환 하기 전에 join 키로 left 테이블의 행을 중복 하지 않습니다. 왼쪽 테이블에 키에 대해 같은 값을 갖는 행이 여러 개 있으면 `join` 각 고유 값에 대해 임의의 단일 행을 유지 하도록 해당 행이 중복 제거 됩니다.

    이 기본 동작은 유용한 통찰력을 제공할 수 있는 왼쪽 표에서 중요 한 정보를 남길 수 있습니다. 예를 들어 아래 쿼리는 여러 전자 메일 메시지를 사용 하 여 동일한 첨부 파일을 보낸 경우라도 특정 첨부 파일이 포함 된 전자 메일을 하나만 표시 합니다.

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    이 제한을 해결 하기 위해 왼쪽 테이블의 모든 행을 오른쪽의 일치 하는 값으로 표시 하도록 지정 하 여 [내부 조인](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 버전을 적용 합니다 `kind=inner` .
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **시간 창에서 레코드 조인**-보안 이벤트를 조사할 때 분석가가 같은 기간에 발생 하는 관련 이벤트를 찾습니다. `join`확인할 레코드 수를 줄임으로써 혜택 성과를 사용할 때 동일한 접근 방식을 적용 하는 경우
    
    아래 쿼리는 악성 파일 수신 30 분 이내에 로그온 이벤트를 확인 합니다.

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- 양쪽 **에 시간 필터 적용**-특정 기간을 조사 하지 않는 경우에도, 왼쪽과 오른쪽 테이블에 시간 필터를 적용 하면 확인할 레코드 수가 줄어들고 성능이 향상 될 수 있습니다 `join` . 아래 쿼리는 한 `Timestamp > ago(1h)` 시간 동안의 레코드만 조인 하도록 두 테이블에 모두 적용 됩니다.

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **성능에 힌트 사용**- `join` 리소스 사용량이 많은 작업을 실행할 때 힌트를 사용 하 여 백 엔드에서 부하를 분산 하도록 지시할 수 있습니다. [조인 힌트에 대해 자세히 알아보기](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    예를 들어 **[순서 섞기 힌트](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 는 높은 카디널리티를 사용 하 여 테이블을 조인할 때 쿼리 성능을 개선 하는 데 도움이 됩니다 (아래 쿼리와 같이 고유한 값이 많은 키) `AccountObjectId` .

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    **[브로드캐스트 힌트](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 는 왼쪽 테이블이 작을 때 (최대 10만 레코드) 오른쪽 테이블이 매우 크다는 것을 지원 합니다. 예를 들어 아래 쿼리는 특정 제목이 있는 몇몇 전자 메일에 테이블의 링크가 포함 된 _모든_ 메시지를 가입시 키 려 고 시도 합니다 `EmailUrlInfo` .

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>교환원 최적화 `summarize`
[요약 연산자](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 는 테이블의 내용을 집계 합니다. 이 연산자를 사용 하는 쿼리를 최적화 하려면 다음 팁을 적용 합니다.

- **고유한 값 찾기**-일반적으로를 사용 하 여 `summarize` 반복 될 수 있는 고유 값을 찾습니다. 반복 되는 값이 없는 열을 집계 하는 데이를 사용 하지 않아도 될 수 있습니다.

    단일 전자 메일이 여러 이벤트에 포함 될 수 있지만, _not_ `summarize` 개별 전자 메일의 네트워크 메시지 ID는 항상 고유한 보낸 사람 주소와 함께 제공 되므로 아래 예제는 효율적으로 사용 되지 않습니다.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    `summarize`이 연산자는 다음과 같이 쉽게 바꿀 수 있으며 `project` 리소스를 적게 소비 하면서 동일한 결과를 얻을 수도 있습니다.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    다음 예는 `summarize` 보낸 사람 주소가 동일한 받는 사람 주소에 전자 메일을 보낼 수 있기 때문에 보다 효율적으로 사용 됩니다. 이러한 조합은 서로 다르며 중복 되는 경우가 많습니다.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **쿼리 순서 섞기**- `summarize` 열에서 반복 되는 값을 사용 하는 경우에는 동일한 열에 _높은 카디널리티_ 또는 다 수의 고유 값이 있을 수도 있습니다. `join`또한 연산자와 마찬가지로 [순서 섞기 힌트](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) 를 적용 `summarize` 하 여 처리 부하를 분산 하 고 높은 카디널리티로 열을 작동할 때 성능을 향상 시킬 수 있습니다.

    아래 쿼리는 `summarize` 대규모 조직에서 수십만 명으로 실행 될 수 있는 고유한 받는 사람 전자 메일 주소 개수를 계산 하는 데 사용 됩니다. 성능을 개선 하기 위해 다음을 통합 합니다 `hint.shufflekey` .

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>쿼리 시나리오

### <a name="identify-unique-processes-with-process-ids"></a>프로세스 Id를 사용 하 여 고유 프로세스 식별
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
여러 가지 방법으로 작업을 수행할 수 있는 명령줄을 만들 수 있습니다. 예를 들어 공격자가 경로 없이 파일 확장명, 환경 변수 또는 따옴표를 사용 하지 않고 이미지 파일을 참조할 수 있습니다. 공격자가 매개 변수의 순서를 변경 하거나 여러 개의 따옴표와 공백을 추가할 수도 있습니다.

명령줄에 보다 영속적 쿼리를 만들려면 다음 방법을 적용 합니다.

- 명령줄 자체에서 필터링 하는 대신 파일 이름 필드를 일치 시켜 *net.exe* 또는 *psexec.exe*와 같은 알려진 프로세스를 식별 합니다.
- [Parse_command_line () 함수](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 를 사용 하 여 명령줄 섹션 구문 분석 
- 명령줄 인수에 대해 쿼리할 때 관련이 없는 여러 인수에서 특정 순서로 정확하게 일치하는 항목을 찾지 마세요. 대신 정규 표현식을 사용하거나 별도의 여러 포함 연산자를 사용합니다.
- 대/소문자를 구분하지 않는 일치 항목을 사용합니다. 예를 들어, `=~` , `in~` 및를 `contains` 대신 사용 `==` `in` `contains_cs` 합니다.
- 명령줄 난독 처리 기법을 완화 하려면 따옴표를 제거 하 고 쉼표를 공백으로 바꾼 다음 여러 개의 연속 된 공백을 단일 공백으로 바꿉니다. 다른 접근 방식을 필요로 하는 좀 더 복잡 한 난독 처리 기법이 있습니다.

다음 예에서는 "MpsSvc" 방화벽 서비스를 중지 *net.exe* 파일을 찾는 다양 한 방법을 보여 줍니다.

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

### <a name="ingest-data-from-external-sources"></a>외부 소스에서 데이터 수집
쿼리에 긴 목록 또는 큰 테이블을 통합 하려면 [externaldata 연산자](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 를 사용 하 여 지정 된 URI에서 데이터를 수집 합니다. TXT, CSV, JSON 또는 [기타 형식의](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)파일에서 데이터를 가져올 수 있습니다. 아래 예에서는 MalwareBazaar (abuse.ch)에서 제공 하는 맬웨어 SHA 256 해시의 광범위 한 목록을 활용 하 여 전자 메일의 첨부 파일을 확인 하는 방법을 보여 줍니다.

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>구문 분석 문자열
구문 분석 이나 변환이 필요한 문자열을 효율적으로 처리 하는 데 사용할 수 있는 다양 한 함수가 있습니다. 

| 문자열 | 함수 | 사용 예제 |
|--|--|--|
| 명령줄 | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | 명령 및 모든 인수를 추출 합니다. | 
| 경로도 | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | 파일 또는 폴더 경로의 섹션을 추출 합니다. |
| 버전 번호 | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct 최대 4 개의 섹션 및 섹션 당 최대 8 자까지 버전 번호를 표시 합니다. 구문 분석 된 데이터를 사용 하 여 버전 기간을 비교 합니다. |
| IPv4 주소 | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | IPv4 주소를 정수 (long)로 변환 합니다. IPv4 주소를 변환 하지 않고 비교 하려면 [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)를 사용 합니다. |
| IPv6 주소 | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | IPv4 또는 IPv6 주소를 정식 IPv6 표시법으로 변환 합니다. IPv6 주소를 비교 하려면 [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)를 사용 합니다. |

지원 되는 모든 구문 분석 함수에 대 한 자세한 내용은 [Kusto string Function을 참조](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)하십시오. 

## <a name="related-topics"></a>관련 항목
- [Kusto 쿼리 언어 설명서](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [서비스 제한](advanced-hunting-limits.md)
- [고급 구하기 오류 처리](advanced-hunting-errors.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
