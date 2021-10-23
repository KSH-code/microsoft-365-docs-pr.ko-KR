---
title: Mac의 끝점에 대한 Microsoft Defender 기본 설정 설정
description: 엔터프라이즈 조직에서 Mac의 끝점에 대한 Microsoft Defender를 구성합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 관리, 기본 설정, 엔터프라이즈, intune, jamf, macos, 카탈로나, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aeb78768db5426c249ab71f01a4e4d5d1fc154e0
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552611"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>macOS의 끝점에 대한 Microsoft Defender 기본 설정 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [Microsoft Defender for Endpoint(macOS용)](microsoft-defender-endpoint-mac.md)

> [!IMPORTANT]
> 이 문서에는 엔터프라이즈 조직의 macOS에서 끝점용 Microsoft Defender에 대한 기본 설정을 설정하는 방법에 대한 지침이 포함되어 있습니다. 명령줄 인터페이스를 사용하여 macOS에서 끝점에 대한 Microsoft Defender를 구성하는 데 필요한 리소스는 리소스를 [참조합니다.](mac-resources.md#configuring-from-the-command-line)

## <a name="summary"></a>요약

엔터프라이즈 조직에서 macOS의 끝점용 Microsoft Defender는 여러 관리 도구 중 하나를 사용하여 배포되는 구성 프로필을 통해 관리할 수 있습니다. 보안 운영 팀에서 관리하는 기본 설정이 디바이스에서 로컬로 설정된 기본 설정보다 우선합니다. 구성 프로필을 통해 설정된 기본 설정을 변경하려면 에스컬레이터된 권한이 필요하며 관리 권한이 없는 사용자는 사용할 수 없습니다.

이 문서에서는 구성 프로필의 구조에 대해 설명하고 시작하는 데 사용할 수 있는 권장 프로필을 포함하며 프로필을 배포하는 방법에 대한 지침을 제공합니다.

## <a name="configuration-profile-structure"></a>구성 프로필 구조

구성 프로필은 키로 식별된 항목(기본 설정 이름을 나타임)으로 구성되는 *.plist* 파일로, 그 다음에 기본 설정의 특성에 따라 값이 표시됩니다. 값은 숫자 값과 같은 단순하거나 중첩된 기본 설정 목록과 같은 복잡할 수 있습니다.

> [!CAUTION]
>구성 프로필의 레이아웃은 사용하는 관리 콘솔에 따라 다릅니다. 다음 섹션에는 JAMF 및 Intune에 대한 구성 프로필의 예가 포함되어 있습니다.

구성 프로필의 최상위 수준에는 다음 섹션에서 자세히 설명하는 Microsoft Defender for Endpoint 하위 항목에 대한 제품 수준 기본 설정 및 항목이 포함되어 있습니다.

### <a name="antivirus-engine-preferences"></a>바이러스 백신 엔진 기본 설정

구성 *프로필의 antivirusEngine* 섹션은 끝점용 Microsoft Defender의 바이러스 백신 구성 요소의 기본 설정을 관리하는 데 사용됩니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|antivirusEngine|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|||

#### <a name="enable--disable-real-time-protection"></a>실시간 보호 사용/사용 안 하도록 설정

파일에 액세스할 때 검색하는 실시간 보호를 사용할지 여부를 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|enableRealTimeProtection|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|||

#### <a name="enable--disable-passive-mode"></a>수동 모드 사용/사용 안 하도록 설정

바이러스 백신 엔진이 수동 모드에서 실행되는지 여부를 지정합니다. 수동 모드에는 다음과 같은 의미가 있습니다.

- 실시간 보호가 꺼져 있습니다.
- On-Demand scanning is turned on(요구 시 검사가 켜져 있습니다.)
- 자동 위협 수정이 꺼져 있습니다.
- 보안 인텔리전스 업데이트가 켜져 있습니다.
- 상태 메뉴 아이콘이 숨겨져 있습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|passiveMode|
|**Data type**|부울|
|**사용 가능한 값:**|false(기본값) <p> true|
|**Comments**|Microsoft Defender for Endpoint 버전 100.67.60 이상에서 사용할 수 있습니다.|
|||

#### <a name="run-a-scan-after-definitions-are-updated"></a>정의가 업데이트된 후 검사 실행

디바이스에서 새 보안 인텔리전스 업데이트를 다운로드한 후 프로세스 검색을 시작할지 여부를 지정합니다. 이 설정을 사용하도록 설정하면 장치의 실행 중인 프로세스에서 바이러스 백신 검사가 트리거됩니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|scanAfterDefinitionUpdate|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|**Comments**|Microsoft Defender for Endpoint 버전 101.41.10 이상에서 사용할 수 있습니다.|
|||

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>보관함 검사(요구 시 바이러스 백신 검사만 해당)

요구 시 바이러스 백신 검사 중에 보관 파일을 검사할지 여부를 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|scanArchives|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|**Comments**|Microsoft Defender for Endpoint 버전 101.41.10 이상에서 사용할 수 있습니다.|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>요구 시 검사에 대한 병렬 처리 수준

요구 시 검사에 대한 병렬 처리의 정도를 지정합니다. 이는 검색을 수행하는 데 사용되는 스레드 수에 해당하며, CPU 사용량과 필요한 검사 기간에 영향을 줍니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|maximumOnDemandScanThreads|
|**Data type**|정수|
|**사용 가능한 값:**|2(기본값) 허용되는 값은 1에서 64 사이의 정수입니다.|
|**Comments**|Microsoft Defender for Endpoint 버전 101.41.10 이상에서 사용할 수 있습니다.|
|||

#### <a name="exclusion-merge-policy"></a>제외 병합 정책

제외에 대한 병합 정책을 지정합니다. 이는 관리자 정의 및 사용자 정의 제외( ) 또는 관리자 정의 제외()의 조합일 `merge` 수 `admin_only` 있습니다. 이 설정을 사용하여 로컬 사용자가 자신의 제외를 정의하지 못하도록 제한할 수 있습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|exclusionsMergePolicy|
|**Data type**|String|
|**사용 가능한 값:**|병합(기본값) <p> admin_only|
|**Comments**|끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.|
|||

#### <a name="scan-exclusions"></a>제외 검사

검사에서 제외된 엔터티를 지정합니다. 제외는 전체 경로, 확장명 또는 파일 이름으로 지정할 수 있습니다.
제외는 항목 배열로 지정됩니다. 관리자는 필요한 수의 요소를 순서에 따라 지정할 수 있습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|제외|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|||

##### <a name="type-of-exclusion"></a>제외 유형

검색에서 제외된 콘텐츠를 유형별로 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|$type|
|**Data type**|String|
|**사용 가능한 값:**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|||

##### <a name="path-to-excluded-content"></a>제외된 콘텐츠의 경로

전체 파일 경로에서 검사에서 제외된 콘텐츠를 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|path|
|**Data type**|String|
|**사용 가능한 값:**|유효한 경로|
|**Comments**|제외된 *$type* 적용 *가능*|
|||

## <a name="supported-exclusion-types"></a>지원되는 제외 유형

다음 표에는 Mac의 끝점용 Defender에서 지원하는 제외 유형이 표시됩니다.

<br>

****

|제외|정의|예제|
|---|---|---|
|파일 확장명|디바이스의 아무 곳이나 확장명을 사용하여 모든 파일|`.test`|
|파일|전체 경로로 식별된 특정 파일|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`|
|폴더|지정된 폴더에 있는 모든 파일(재발성)|`/var/log/` <p> `/var/*/`|
|프로세스|전체 경로 또는 파일 이름으로 지정된 특정 프로세스 및 이 프로세스에서 연 모든 파일|`/bin/cat` <p> `cat` <p> `c?t`|
||||

> [!IMPORTANT]
> 위의 경로는 기호 링크가 아니라 하드 링크되어야만 성공적으로 제외됩니다. 를 실행하여 경로가 기호 링크인지 확인할 수 `file <path-name>` 있습니다.

파일, 폴더 및 프로세스 제외는 다음 와일드카드를 지원합니다.

<br>

****

|와일드카드|설명|예제|일치|일치하지 않습니다.|
|---|---|---|---|---|
|\*|none을 포함한 모든 문자와 일치합니다(경로 내에서 이 와일드카드를 사용하는 경우 폴더 하나만 대체).|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`|
|?|단일 문자와 일치|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`|
||||||

### <a name="path-type-file--directory"></a>경로 유형(파일/디렉터리)

경로 *속성이* 파일 또는 디렉터리를 참조하는지 나타냅니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|isDirectory|
|**Data type**|부울|
|**사용 가능한 값:**|false(기본값) <p> true|
|**Comments**|제외된 *$type* 적용 *가능*|
|||

### <a name="file-extension-excluded-from-the-scan"></a>검사에서 제외된 파일 확장명

파일 확장명에 의해 검색되지 않을 콘텐츠를 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|extension|
|**Data type**|String|
|**사용 가능한 값:**|유효한 파일 확장명|
|**Comments**|제외된  *$type FileExtension만 적용할 수 있습니다.*|
|||

### <a name="process-excluded-from-the-scan"></a>검사에서 제외된 프로세스

모든 파일 활동이 검사에서 제외되는 프로세스를 지정합니다. 프로세스는 이름(예: ) 또는 전체 경로(예: )로 지정할 `cat` 수 `/bin/cat` 있습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|name|
|**Data type**|String|
|**사용 가능한 값:**|모든 문자열|
|**Comments**|*excludedFileName이 $type만 적용할 수 있습니다.* |
|||

#### <a name="allowed-threats"></a>허용되는 위협

Mac의 끝점에 대한 Defender에 의해 차단되지 않는 이름으로 위협을 지정합니다. 이러한 위협은 실행될 수 있습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|allowedThreats|
|**Data type**|문자열 배열|
|||

#### <a name="disallowed-threat-actions"></a>위협 작업 수 없습니다.

위협이 감지될 때 장치의 로컬 사용자가 수행할 수 있는 작업을 제한합니다. 이 목록에 포함된 작업은 사용자 인터페이스에 표시되지 않습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|disallowedThreatActions|
|**Data type**|문자열 배열|
|**사용 가능한 값:**|allow (restricts users from allow threats) <p> restore(사용자가 검지에서 위협을 복원하는 것을 제한함)|
|**Comments**|끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.|
|||

#### <a name="threat-type-settings"></a>위협 유형 설정

macOS의 끝점에 대한 Microsoft Defender에서 특정 위협 유형을 처리하는 방법을 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|threatTypeSettings|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|||

##### <a name="threat-type"></a>위협 유형

위협 유형을 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|키|
|**Data type**|String|
|**사용 가능한 값:**|potentially_unwanted_application <p> archive_bomb|
|||

##### <a name="action-to-take"></a>수행할 작업

이전 섹션에 지정된 유형의 위협이 감지될 때 취할 작업을 지정합니다. 다음 옵션 중에서 선택합니다.

- **감사:** 장치가 이러한 유형의 위협으로부터 보호되지 않지만 위협에 대한 항목이 기록됩니다.
- **차단:** 장치가 이러한 유형의 위협으로부터 보호되고 사용자 인터페이스 및 보안 콘솔에 알림을 제공합니다.
- **Off:** 장치가 이러한 유형의 위협으로부터 보호되지는 않습니다. 아무것도 기록되지 않습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|값|
|**Data type**|String|
|**사용 가능한 값:**|감사(기본값) <p> block <p> off|
|||

#### <a name="threat-type-settings-merge-policy"></a>위협 유형 설정 병합 정책

위협 유형 설정에 대한 병합 정책을 지정합니다. 이는 관리자 정의 및 사용자 정의 설정( ) 또는 관리자 정의 설정()의 `merge` 조합일 수 `admin_only` 있습니다. 이 설정을 사용하여 로컬 사용자가 서로 다른 위협 유형에 대한 자체 설정을 정의하지 못하도록 제한할 수 있습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|threatTypeSettingsMergePolicy|
|**Data type**|String|
|**사용 가능한 값:**|병합(기본값) <p> admin_only|
|**Comments**|끝점용 Microsoft Defender 버전 100.83.73 이상에서 사용할 수 있습니다.|
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>바이러스 백신 검사 기록 보존(일)

장치의 검사 기록에 결과가 보존되는 일 수를 지정합니다. 이전 검사 결과가 기록에서 제거됩니다. 디스크에서 제거된 오래된 고지된 파일입니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|scanResultsRetentionDays|
|**Data type**|String|
|**사용 가능한 값:**|90(기본값) 허용되는 값은 1일에서 180일까지입니다.|
|**Comments**|Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.|
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>바이러스 백신 검사 기록의 최대 항목 수

검사 기록에 유지할 최대 항목 수를 지정합니다. 항목에는 과거에 수행된 모든 요구 시 검사와 모든 바이러스 백신 검색이 포함됩니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|scanHistoryMaximumItems|
|**Data type**|String|
|**사용 가능한 값:**|10000(기본값) 허용되는 값은 5,000개 항목에서 15,000개 항목까지입니다.|
|**Comments**|Microsoft Defender for Endpoint 버전 101.07.23 이상에서 사용할 수 있습니다.|
|||

### <a name="cloud-delivered-protection-preferences"></a>클라우드 제공 보호 기본 설정

MacOS의 끝점에 대한 Microsoft Defender의 클라우드 기반 보호 기능을 구성합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|cloudService|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>클라우드 제공 보호 사용/사용 안 하도록 설정

디바이스에서 클라우드 제공 보호를 사용할지 여부를 지정합니다. 서비스의 보안을 개선하기 위해 이 기능을 켜져 있는 것이 좋습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|활성화됨|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|||

#### <a name="diagnostic-collection-level"></a>진단 수집 수준

진단 데이터는 끝점용 Microsoft Defender를 안전하고 최신으로 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다. 이 설정은 끝점용 Microsoft Defender에서 Microsoft로 전송하는 진단 수준을 결정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|diagnosticLevel|
|**Data type**|String|
|**사용 가능한 값:**|선택 사항(기본값) <p> 필수|
|||

#### <a name="enable--disable-automatic-sample-submissions"></a>자동 샘플 제출 사용/사용 안 하도록 설정

의심스러운 샘플(위협이 포함될 가능성이 높음)을 Microsoft로 보낼지 여부를 결정합니다. 전송된 파일에 개인 정보가 포함될 가능성이 있는 경우 메시지가 표시됩니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|automaticSampleSubmission|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>자동 보안 인텔리전스 업데이트 사용/사용 안 하도록 설정

보안 인텔리전스 업데이트가 자동으로 설치될지 여부를 확인합니다.

<br>

****

|섹션|값|
|---|---|
|**키**|automaticDefinitionUpdateEnabled|
|**Data type**|부울|
|**사용 가능한 값:**|true(기본값) <p> false|
|||

### <a name="user-interface-preferences"></a>사용자 인터페이스 기본 설정

macOS에서 끝점용 Microsoft Defender의 사용자 인터페이스에 대한 기본 설정을 관리합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|userInterface|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|||

#### <a name="show--hide-status-menu-icon"></a>상태 메뉴 아이콘 표시/숨기기

화면의 오른쪽 위 모서리에 상태 메뉴 아이콘을 표시하거나 숨길지 여부를 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|hideStatusMenuIcon|
|**Data type**|부울|
|**사용 가능한 값:**|false(기본값) <p> true|
|||

#### <a name="show--hide-option-to-send-feedback"></a>피드백을 보내기 위한 표시/숨기기 옵션

사용자가 로 진행하여 Microsoft에 피드백을 제출할 수 있는지 여부를 `Help`  >  `Send Feedback` 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|userInitiatedFeedback|
|**Data type**|String|
|**사용 가능한 값:**|사용(기본값) <p> 비활성화됨|
|**Comments**|끝점 버전 101.19.61 이상용 Microsoft Defender에서 사용할 수 있습니다.|
|||

### <a name="endpoint-detection-and-response-preferences"></a>끝점 검색 및 응답 기본 설정

macOS에서 끝점용 Microsoft Defender의 끝점 EDR(검색 및 응답) 구성 요소의 기본 설정을 관리합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|edr|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|||

#### <a name="device-tags"></a>장치 태그

태그 이름 및 해당 값을 지정합니다.

- GROUP 태그는 지정된 값으로 디바이스에 태그를 지정합니다. 태그는 장치 페이지 아래에 있는 포털에 반영되어 디바이스 필터링 및 그룹화에 사용할 수 있습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|tags|
|**Data type**|사전(중첩된 기본 설정)|
|**Comments**|사전 콘텐츠에 대한 설명은 다음 섹션을 참조하세요.|
|||

##### <a name="type-of-tag"></a>태그 유형

태그 유형을 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|키|
|**Data type**|String|
|**사용 가능한 값:**|`GROUP`|
|||

##### <a name="value-of-tag"></a>태그 값

태그 값을 지정합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.wdav`|
|**키**|값|
|**Data type**|String|
|**사용 가능한 값:**|모든 문자열|
|||

> [!IMPORTANT]
>
> - 태그 유형당 하나의 값만 설정할 수 있습니다.
> - 태그 유형은 고유하며 동일한 구성 프로필에서 반복하면 안 됩니다.

## <a name="recommended-configuration-profile"></a>권장 구성 프로필

시작하려면 엔터프라이즈에서 Microsoft Defender for Endpoint에서 제공하는 모든 보호 기능을 활용하기 위해 다음 구성을 구성하는 것이 좋습니다.

다음 구성 프로필(또는 JAMF의 경우 사용자 지정 설정 구성 프로필에 업로드할 수 있는 속성 목록)은 다음과 같습니다.

- RTP(실시간 보호) 사용
- 다음 위협 유형을 처리하는 방법을 지정합니다.
  - **잠재적으로 원치 않는 응용 프로그램(PUA)이** 차단됩니다.
  - **보관함(압축률이** 높은 파일)이 끝점 로그에 대한 Microsoft Defender에 감사됩니다.
- 자동 보안 인텔리전스 업데이트 사용
- 클라우드 제공 보호 사용
- 자동 샘플 제출 사용

### <a name="property-list-for-jamf-recommended-configuration-profile"></a>JAMF 권장 구성 프로필의 속성 목록

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-recommended-profile"></a>Intune 권장 프로필

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>전체 구성 프로필 예제

다음 템플릿은 이 문서에 설명된 모든 설정에 대한 항목을 포함하며 macOS에서 끝점용 Microsoft Defender를 더 많이 제어하려는 고급 시나리오에 사용할 수 있습니다.

### <a name="property-list-for-jamf-full-configuration-profile"></a>JAMF 전체 구성 프로필에 대한 속성 목록

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>scanAfterDefinitionUpdate</key>
        <true/>
        <key>scanArchives</key>
        <true/>
        <key>maximumOnDemandScanThreads</key>
        <integer>2</integer>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-full-profile"></a>Intune 전체 프로필

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>scanAfterDefinitionUpdate</key>
                    <true/>
                    <key>scanArchives</key>
                    <true/>
                    <key>maximumOnDemandScanThreads</key>
                    <integer>1</integer>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>속성 목록 유효성 검사

속성 목록은 유효한 *.plist 파일입니다.* 다음을 실행하여 확인할 수 있습니다.

```bash
plutil -lint com.microsoft.wdav.plist
```

```Output
com.microsoft.wdav.plist: OK
```

파일이 잘 형식이면 위의 명령은 의 종료 코드를 `OK` 출력하고 `0` 반환합니다. 그렇지 않으면 문제를 설명하는 오류가 표시되고 명령은 의 종료 코드를 `1` 반환합니다.

## <a name="configuration-profile-deployment"></a>구성 프로필 배포

엔터프라이즈의 구성 프로필을 작성한 후 엔터프라이즈에서 사용하는 관리 콘솔을 통해 배포할 수 있습니다. 다음 섹션에서는 JAMF 및 Intune을 사용하여 이 프로필을 배포하는 방법에 대한 지침을 제공합니다.

### <a name="jamf-deployment"></a>JAMF 배포

JAMF 콘솔에서 컴퓨터  구성 프로필을 열고 사용할 구성 프로필로 이동한 다음 사용자 지정 프로필을 \>  **설정.** 기본 설정 도메인으로 항목을 만들고 앞에서 생성한 `com.microsoft.wdav` *.plist를* 업로드합니다.

> [!CAUTION]
> 올바른 기본 설정 도메인( )을 입력해야 합니다. 그렇지 않으면 끝점용 Microsoft Defender에서 기본 설정이 `com.microsoft.wdav` 인식되지 않습니다.

### <a name="intune-deployment"></a>Intune 배포

1. 장치 **구성 관리를** \> **니다.** 프로필 **만들기** \> **를** \> **선택합니다.**

2. 프로필 이름을 선택하세요. **Platform=macOS를** **프로필 유형=사용자 지정으로 변경합니다.** 구성을 선택합니다.

3. 앞에서 생성한 .plist를 로 `com.microsoft.wdav.xml` 저장합니다.

4. 사용자 `com.microsoft.wdav` 지정 구성 프로필 이름으로 **를 입력합니다.**

5. 구성 프로필을 열고 파일을 `com.microsoft.wdav.xml` 업로드합니다. 이 파일은 3단계에서 만들어졌습니다.

6. **확인** 을 선택합니다.

7. 배정  \> **관리를 선택합니다.** 포함 **탭에서** 모든 사용자 및 모든 & **할당을 선택합니다.**

> [!CAUTION]
> 올바른 사용자 지정 구성 프로필 이름을 입력해야 합니다. 그렇지 않으면 이러한 기본 설정이 끝점용 Microsoft Defender에서 인식되지 않습니다.

## <a name="resources"></a>리소스

- [구성 프로필 참조(Apple 개발자 문서)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
