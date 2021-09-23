---
title: Linux에서 끝점용 Microsoft Defender에 대한 기본 설정 설정
ms.reviewer: ''
description: 엔터프라이즈에서 Linux에서 끝점에 대한 Microsoft Defender를 구성하는 방법을 설명 합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, linux, 설치, 배포, 제거, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 36d4c90eb02bc9fb147ed0a28481444508be068e
ms.sourcegitcommit: 0ed93816e2c1e6620e68bd1c0f00390062911606
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59483522"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender에 대한 기본 설정 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> 이 항목에는 엔터프라이즈 환경에서 Linux에서 끝점용 Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다. 명령줄에서 디바이스에서 제품을 구성하는 데 관심이 있는 경우 리소스를 [참조하세요.](linux-resources.md#configure-from-the-command-line)

엔터프라이즈 환경에서 Linux의 끝점용 Defender는 구성 프로필을 통해 관리할 수 있습니다. 이 프로필은 선택한 관리 도구에서 배포됩니다. 엔터프라이즈에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다. 즉, 기업의 사용자는 이 구성 프로필을 통해 설정된 기본 설정을 변경할 수 없습니다.

이 문서에서는 이 프로필의 구조(시작하는 데 사용할 수 있는 권장 프로필 포함)와 프로필 배포 방법에 대한 지침을 제공합니다.

## <a name="configuration-profile-structure"></a>구성 프로필 구조

구성 프로필은 키(기본 설정의 이름을 나타임)로 식별되는 항목과 기본 설정의 특성에 따라 값이 이어지는 .json 파일입니다. 값은 숫자 값과 같이 단순하거나 중첩된 기본 설정 목록과 같은 복잡한 값일 수 있습니다.

일반적으로 구성 관리 도구를 사용하여 위치에 이름이 있는 파일을 ```mdatp_managed.json``` ```/etc/opt/microsoft/mdatp/managed/``` 푸시합니다.

구성 프로필의 최상위 수준에는 제품 수준 기본 설정 및 제품의 하위 항목에 대한 항목이 포함되어 있으며, 이 내용은 다음 섹션에서 자세히 설명합니다.

### <a name="antivirus-engine-preferences"></a>바이러스 백신 엔진 기본 설정

구성 *프로필의 antivirusEngine* 섹션은 제품의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|antivirusEngine|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|

#### <a name="enable--disable-real-time-protection"></a>실시간 보호 사용/사용 안 하도록 설정

실시간 보호(액세스할 때 파일 검색)를 사용할지 여부를 확인합니다.

<br>

****

|설명|값|
|---|---|
|**키**|enableRealTimeProtection|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|

#### <a name="enable--disable-passive-mode"></a>수동 모드 사용/사용 안 하도록 설정

바이러스 백신 엔진이 수동 모드에서 실행될지 여부를 결정합니다. 수동 모드:

- 실시간 보호가 꺼져 있습니다.
- On-demand scanning is turned on.
- 자동 위협 수정이 꺼져 있습니다.
- 보안 인텔리전스 업데이트가 켜져 있습니다.
- 상태 메뉴 아이콘이 숨겨집니다.

<br>

****

|설명|값|
|---|---|
|**키**|passiveMode|
|**Data type**|부울|
|**사용 가능한 값:**|false(기본값) <p> true|
|**Comments**|Endpoint 버전 100.67.60 이상용 Defender에서 사용할 수 있습니다.|
|
  
#### <a name="run-a-scan-after-definitions-are-updated"></a>정의가 업데이트된 후 검사 실행

디바이스에서 새 보안 인텔리전스 업데이트를 다운로드한 후 프로세스 검색을 시작할지 여부를 지정합니다. 이 설정을 사용하도록 설정하면 장치의 실행 중인 프로세스에서 바이러스 백신 검사가 트리거됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|scanAfterDefinitionUpdate|
|**Data type**|부울|
|**사용 가능한 값:**|false(기본값) <p> true|
|**Comments**|Endpoint 버전 101.41.51 이상용 Defender에서 사용할 수 있습니다.|
|
  

#### <a name="exclusion-merge-policy"></a>제외 병합 정책

제외에 대한 병합 정책을 지정합니다. 관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()만 조합할 `merge` 수 `admin_only` 있습니다. 이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.

<br>

****

|설명|값|
|---|---|
|**키**|exclusionsMergePolicy|
|**Data type**|String|
|**사용 가능한 값:**|병합(기본값) <p> admin_only|
|**Comments**|Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.|
|

#### <a name="scan-exclusions"></a>제외 검사

검사에서 제외된 엔터티입니다. 제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.
제외는 항목 배열로 지정됩니다. 관리자는 필요한 수의 요소를 순서에 따라 지정할 수 있습니다.

<br>

****

|설명|값|
|---|---|
|**키**|제외|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|

##### <a name="type-of-exclusion"></a>제외 유형

검색에서 제외된 콘텐츠의 형식을 지정합니다.

<br>

****

|설명|값|
|---|---|
|**키**|$type|
|**Data type**|String|
|**사용 가능한 값:**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|

##### <a name="path-to-excluded-content"></a>제외된 콘텐츠의 경로

전체 파일 경로로 검색에서 콘텐츠를 제외하는 데 사용됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|path|
|**Data type**|String|
|**사용 가능한 값:**|유효한 경로|
|**Comments**|제외된 *$type* 적용 *가능*|
|

##### <a name="path-type-file--directory"></a>경로 유형(파일/디렉터리)

path *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.

<br>

****

|설명|값|
|---|---|
|**키**|isDirectory|
|**Data type**|부울|
|**사용 가능한 값:**|false(기본값) <p> true|
|**Comments**|제외된 *$type* 적용 *가능*|
|

##### <a name="file-extension-excluded-from-the-scan"></a>검사에서 제외된 파일 확장명

파일 확장명에 의해 검색에서 콘텐츠를 제외하는 데 사용됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|extension|
|**Data type**|String|
|**사용 가능한 값:**|유효한 파일 확장명|
|**Comments**|제외된  *$type FileExtension만 적용할 수 있습니다.*|
|

##### <a name="process-excluded-from-the-scan"></a>검사에서 제외된 프로세스*

모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다. 프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.

<br>

****

|설명|값|
|---|---|
|**키**|name|
|**Data type**|String|
|**사용 가능한 값:**|모든 문자열|
|**Comments**|*excludedFileName이 $type만 적용할 수 있습니다.* |
|

#### <a name="allowed-threats"></a>허용되는 위협

제품에서 차단되지 않고 대신 실행할 수 있는 위협 목록(해당 이름으로 식별)입니다.

<br>

****

|설명|값|
|---|---|
|**키**|allowedThreats|
|**Data type**|문자열 배열|
|

#### <a name="disallowed-threat-actions"></a>위협 작업 수 없습니다.

위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다. 이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.

<br>

****

|설명|값|
|---|---|
|**키**|disallowedThreatActions|
|**Data type**|문자열 배열|
|**사용 가능한 값:**|allow (restricts users from allow threats) <p> restore(사용자가 검지에서 위협을 복원하는 것을 제한함)|
|**Comments**|Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.|
|

#### <a name="threat-type-settings"></a>위협 유형 설정

바이러스 *백신 엔진의 threatTypeSettings* 기본 설정은 특정 위협 유형이 제품에서 처리되는 방법을 제어하는 데 사용됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|threatTypeSettings|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|

##### <a name="threat-type"></a>위협 유형

동작이 구성된 위협 유형입니다.

<br>

****

|설명|값|
|---|---|
|**키**|키|
|**Data type**|String|
|**사용 가능한 값:**|potentially_unwanted_application <p> archive_bomb|
|

##### <a name="action-to-take"></a>수행할 작업

이전 섹션에 지정된 유형의 위협에 부과될 때 취할 조치입니다. 다음이 될 수 있습니다.

- **감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.
- **차단:** 이 유형의 위협으로부터 장치가 보호되고 보안 콘솔에 알림을 제공합니다.
- **Off:** 이 유형의 위협으로부터 장치가 보호되지는 않습니다. 아무것도 기록되지 않습니다.

<br>

****

|설명|값|
|---|---|
|**키**|값|
|**Data type**|String|
|**사용 가능한 값:**|감사(기본값) <p> block <p> off|
|

#### <a name="threat-type-settings-merge-policy"></a>위협 유형 설정 병합 정책

위협 유형 설정에 대한 병합 정책을 지정합니다. 이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다. 이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.

<br>

****

|설명|값|
|---|---|
|**키**|threatTypeSettingsMergePolicy|
|**Data type**|String|
|**사용 가능한 값:**|병합(기본값) <p> admin_only|
|**Comments**|Defender for Endpoint 버전 100.83.73 이상에서 사용할 수 있습니다.|
|

#### <a name="antivirus-scan-history-retention-in-days"></a>바이러스 백신 검사 기록 보존(일)

장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다. 이전 검사 결과가 기록에서 제거됩니다. 디스크에서 제거된 오래된 고지된 파일입니다.

<br>

****

|설명|값|
|---|---|
|**키**|scanResultsRetentionDays|
|**Data type**|String|
|**사용 가능한 값:**|90(기본값) 허용되는 값은 1일에서 180일까지입니다.|
|**Comments**|Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>바이러스 백신 검사 기록의 최대 항목 수

검사 기록에 유지할 최대 항목 수를 지정합니다. 항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|scanHistoryMaximumItems|
|**Data type**|String|
|**사용 가능한 값:**|10000(기본값) 허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.|
|**Comments**|Endpoint 버전 101.04.76 이상용 Defender에서 사용할 수 있습니다.|
|

### <a name="cloud-delivered-protection-preferences"></a>클라우드 제공 보호 기본 설정

구성 *프로필의 cloudService* 항목은 제품의 클라우드 기반 보호 기능을 구성하는 데 사용됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|cloudService|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|

#### <a name="enable--disable-cloud-delivered-protection"></a>클라우드 제공 보호 사용/사용 안 하도록 설정

장치에서 클라우드 제공 보호를 사용할지 여부를 확인합니다. 서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.

<br>

****

|설명|값|
|---|---|
|**키**|활성화됨|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|

#### <a name="diagnostic-collection-level"></a>진단 수집 수준

진단 데이터는 Endpoint용 Defender를 안전하고 최신 상태를 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다. 이 설정은 제품이 Microsoft에 전송한 진단 수준을 결정하는 설정입니다.

<br>

****

|설명|값|
|---|---|
|**키**|diagnosticLevel|
|**Data type**|String|
|**사용 가능한 값:**|선택 사항(기본값) <p> 필수|
|

#### <a name="enable--disable-automatic-sample-submissions"></a>자동 샘플 제출 사용/사용 안 하도록 설정

의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다. 샘플 제출을 제어하는 세 가지 수준이 있습니다.

- **없음:** 의심스러운 샘플이 Microsoft에 제출하지 않습니다.
- **금고**: PII(개인 식별 정보)를 포함하지 않는 의심스러운 샘플만 자동으로 제출됩니다. 이 설정의 기본값입니다.
- **모두:** 의심스러운 모든 샘플이 Microsoft에 제출됩니다.

<br>

****

|설명|값|
|---|---|
|**키**|automaticSampleSubmissionConsent|
|**Data type**|String|
|**사용 가능한 값:**|없음 <p> 안전(기본값) <p> all|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정

보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.

<br>

****

|설명|값|
|---|---|
|**키**|automaticDefinitionUpdateEnabled|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|

## <a name="recommended-configuration-profile"></a>권장 구성 프로필

시작하려면 엔터프라이즈에서 다음과 같은 구성 프로필을 사용하여 Endpoint용 Defender에서 제공하는 모든 보호 기능을 활용하는 것이 좋습니다.

다음 구성 프로필은 다음과 같습니다.

- RTP(실시간 보호) 사용
- 다음 위협 유형을 처리하는 방법을 지정합니다.
  - **잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.
  - **보관함(압축률이** 높은 파일)이 제품 로그에 감사됩니다.
- 자동 보안 인텔리전스 업데이트 사용
- 클라우드 제공 보호 사용
- 수준에서 자동 샘플 제출 `safe` 사용

### <a name="sample-profile"></a>샘플 프로필

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>전체 구성 프로필 예제

다음 구성 프로필에는 이 문서에 설명된 모든 설정에 대한 항목이 포함되어 있으며 제품을 보다 잘 제어하려는 고급 시나리오에 사용할 수 있습니다.

### <a name="full-profile"></a>전체 프로필

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "maximumOnDemandScanThreads":1,
      "passiveMode":false,
      "scanAfterDefinitionUpdate":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "<EXAMPLE DO NOT USE>EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>구성 프로필 유효성 검사

구성 프로필은 유효한 JSON 형식 파일되어야 합니다. 이를 확인하는 데 사용할 수 있는 도구는 여러 가지가 있습니다. 예를 들어 장치에 `python` 설치한 경우:

```bash
python -m json.tool mdatp_managed.json
```

JSON이 잘 구성되면 위의 명령은 터미널에 다시 출력하고 의 종료 코드를 `0` 반환합니다. 그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>mdatp_managed.json 파일이 예상대로 작동하고 있는지 확인

/etc/opt/microsoft/mdatp/managed/mdatp_managed.json이 제대로 작동하고 있는지 확인하려면 다음 설정 옆에 "[관리]"가 표시됩니다.

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> mdatp_managed.json을 적용하려면 wdavdaemon을 다시 시작할 필요는 없습니다.

## <a name="configuration-profile-deployment"></a>구성 프로필 배포

엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 도구를 통해 배포할 수 있습니다. Linux의 끝점용 Defender는 */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* 파일에서 관리되는 구성을 읽습니다.
