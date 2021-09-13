---
title: Linux의 끝점용 Microsoft Defender 개인 정보
description: 개인 정보 제어, Linux의 끝점용 Microsoft Defender에서 수집된 진단 데이터에 대한 개인 정보 및 정보에 영향을 미치는 정책 설정을 구성하는 방법.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 개인 정보, 진단
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3d6ce59ec83e8271ff0c665386bd33942084d9ad
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218382"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-linux"></a>Linux의 끝점용 Microsoft Defender 개인 정보

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft는 Linux에서 Endpoint용 Defender를 사용할 때 데이터를 수집하고 사용하는 방법에 대해 선택해야 하는 정보와 컨트롤을 사용자에게 제공하기 위해 최선을 다하고 있습니다.

이 항목에서는 제품 내에서 사용할 수 있는 개인 정보 컨트롤, 정책 설정으로 이러한 컨트롤을 관리하는 방법 및 수집된 데이터 이벤트에 대한 세부 정보를 제공합니다.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-linux"></a>Linux의 끝점용 Microsoft Defender의 개인 정보 컨트롤 개요

이 섹션에서는 Linux의 끝점용 Defender에서 수집한 다양한 유형의 데이터에 대한 개인 정보 컨트롤에 대해 설명합니다.

### <a name="diagnostic-data"></a>진단 데이터

진단 데이터는 Endpoint용 Defender를 안전하고 최신 상태를 유지하며, 문제를 감지, 진단 및 해결하며, 제품을 개선하는 데 사용됩니다.

일부 진단 데이터는 필수 사항이지만, 일부 진단 데이터는 선택 사항입니다. 조직의 정책 설정과 같은 개인 정보 보호 컨트롤 사용을 통해 필수 또는 선택 사항 진단 데이터를 전송할지 여부를 선택할 수 있습니다.

끝점용 Defender 클라이언트 소프트웨어에 대한 진단 데이터에는 다음 두 가지 수준 중 선택할 수 있습니다.

- **필수:** Endpoint용 Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.
- **선택** 사항: Microsoft가 제품을 개선하고 문제를 감지, 진단 및 수정하는 데 도움이 되는 향상된 정보를 제공하는 추가 데이터입니다.

기본적으로 필수 진단 데이터만 Microsoft로 전송됩니다.

### <a name="cloud-delivered-protection-data"></a>클라우드 제공 보호 데이터

클라우드 제공 보호는 클라우드의 최신 보호 데이터에 액세스할 수 있도록 증가하고 더 빠른 보호를 제공하는 데 사용됩니다.

클라우드 제공 보호 서비스를 사용하도록 설정하는 것은 선택 사항이지만 끝점 및 네트워크 전체에서 맬웨어에 대한 중요한 보호 기능을 제공하기 때문에 이 서비스를 사용하도록 설정하는 것이 좋습니다.

### <a name="sample-data"></a>예제 데이터

샘플 데이터는 의심스러운 Microsoft 샘플을 전송하여 분석할 수 있도록 제품의 보호 기능을 개선하는 데 사용됩니다. 자동 샘플 제출을 사용하도록 설정하는 것은 선택 사항입니다.

샘플 제출을 제어하는 세 가지 수준이 있습니다.

- **없음:** 의심스러운 샘플이 Microsoft에 제출하지 않습니다.
- **금고**: PII(개인 식별 정보)를 포함하지 않는 의심스러운 샘플만 자동으로 제출됩니다. 이 설정의 기본값입니다.
- **모두:** 의심스러운 모든 샘플이 Microsoft에 제출됩니다.

## <a name="manage-privacy-controls-with-policy-settings"></a>정책 설정을 사용하여 개인 정보 관리

IT 관리자인 경우 엔터프라이즈 수준에서 이러한 컨트롤을 구성할 수 있습니다.

이전 섹션에서 설명한 다양한 유형의 데이터에 대한 개인 정보 컨트롤은 [Linux에서 끝점용 Defender에](linux-preferences.md)대한 기본 설정 설정에 자세히 설명되어 있습니다.

새 정책 설정과 함께, 조직에서 정책 설정을 보다 광범위하게 구현하기 전에 구성한 설정이 원하는 영향을 미치도록 제한되고 제어되는 환경에서 신중하게 테스트해야 합니다.

## <a name="diagnostic-data-events"></a>진단 데이터 이벤트

이 섹션에서는 필수 진단 데이터로 간주되는 항목과 선택적 진단 데이터로 간주되는 항목과 수집된 이벤트 및 필드에 대한 설명을 설명합니다.

### <a name="data-fields-that-are-common-for-all-events"></a>모든 이벤트에 공통적인 데이터 필드

범주 또는 데이터 하위 형식에 관계없이 모든 이벤트에 공통적인 이벤트에 대한 몇 가지 정보가 있습니다.

다음 필드는 모든 이벤트에서 공통으로 간주됩니다.

|필드|설명|
|---|---|
|플랫폼|앱이 실행되는 플랫폼의 광범위한 분류입니다. Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생한 플랫폼을 식별할 수 있도록 허용합니다.|
|machine_guid|장치와 연결된 고유 식별자입니다. Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.|
|sense_guid|장치와 연결된 고유 식별자입니다. Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.|
|org_id|장치가 속한 엔터프라이즈와 연결된 고유 식별자입니다. Microsoft에서 문제가 선택한 엔터프라이즈 집합에 영향을 미치는지 여부와 영향을 미치는 엔터프라이즈 수를 식별할 수 있도록 합니다.|
|hostname|로컬 장치 이름(DNS 접미사 불포기). Microsoft에서 문제가 선택된 설치 집합에 영향을 미치는지 여부와 영향을 미치는 사용자 수를 식별할 수 있도록 합니다.|
|product_guid|제품의 고유 식별자입니다. Microsoft에서 제품의 다양한 특징에 영향을 미치는 문제를 차별화할 수 있습니다.|
|app_version|Linux 응용 프로그램의 끝점용 Defender 버전입니다. Microsoft에서 문제를 표시하는 제품 버전을 식별하여 제품의 우선 순위를 올바르게 지정할 수 있도록 허용합니다.|
|sig_version|보안 인텔리전스 데이터베이스의 버전입니다. Microsoft에서 문제를 표시하는 보안 인텔리전스 버전을 식별하여 우선 순위를 올바르게 지정할 수 있도록 할 수 있습니다.|
|supported_compressions|응용 프로그램에서 지원하는 압축 알고리즘 목록(예: `['gzip']` ). Microsoft에서 응용 프로그램과 통신할 때 사용할 수 있는 압축 유형을 이해할 수 있습니다.|
|release_ring|디바이스가 연결된 링(예: Insider Fast, Insider Slow, Production)입니다. Microsoft에서 문제의 우선 순위를 올바르게 지정할 수 있도록 문제가 발생될 수 있는 릴리스 링을 식별할 수 있습니다.|

### <a name="required-diagnostic-data"></a>필수 진단 데이터

**필수 진단 데이터는** Endpoint용 Defender를 안전하고 최신으로 유지하며 설치된 디바이스에서 예상대로 수행하는 데 필요한 최소 데이터입니다.

필수 진단 데이터는 장치 또는 소프트웨어 구성과 관련이 있을 수 있는 끝점용 Microsoft Defender의 문제를 식별하는 데 도움이 됩니다. 예를 들어, 새로운 기능이 도입된 특정 운영 체제 버전에서 또는 특정 Endpoint용 Defender 기능이 비활성화된 경우 끝점용 Defender 기능이 더 자주 충돌하는지 여부를 확인하는 데 도움이 될 수 있습니다. 필수 진단 데이터는 Microsoft에서 이러한 문제를 더 빠르게 감지, 진단 및 해결하여 사용자 또는 조직에 미치는 영향을 줄일 수 있도록 합니다.

#### <a name="software-setup-and-inventory-data-events"></a>소프트웨어 설치 및 인벤토리 데이터 이벤트

**Microsoft Defender for Endpoint 설치/제거**:

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|correlation_id|설치와 연결된 고유 식별자입니다.|
|버전|패키지의 버전입니다.|
|심각도|메시지의 심각도(예: 정보)|
|code|작업을 설명하는 코드입니다.|
|text|제품 설치와 관련된 추가 정보입니다.|

**끝점 구성에 대한 Microsoft Defender :**

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|antivirus_engine.enable_real_time_protection|장치에서 실시간 보호를 사용할 수 있는지 여부입니다.|
|antivirus_engine.passive_mode|디바이스에서 수동 모드가 활성화되어 있는지 여부입니다.|
|cloud_service.enabled|클라우드 제공 보호가 장치에서 활성화되어 있는지 여부입니다.|
|cloud_service.timeout|응용 프로그램이 끝점용 Defender 클라우드와 통신할 때의 시간 종료입니다.|
|cloud_service.heartbeat_interval|제품이 클라우드로 전송한 연속 하트비트 사이의 간격입니다.|
|cloud_service.service_uri|클라우드와 통신하는 데 사용되는 URI입니다.|
|cloud_service.diagnostic_level|디바이스의 진단 수준(필수, 선택 사항)|
|cloud_service.automatic_sample_submission|장치의 자동 샘플 제출 수준(없음, 안전, 모두)입니다.|
|cloud_service.automatic_definition_update_enabled|자동 정의 업데이트가 켜져 있는지 여부입니다.|
|edr.early_preview|디바이스가 초기 미리 보기 EDR 실행해야 하는지 여부입니다.|
|edr.group_id|검색 및 응답 구성 요소에서 사용하는 그룹 식별자입니다.|
|edr.tags|사용자 정의 태그.|
|기능을 제공합니다. \[ 선택적 기능 이름\]|미리 보기 기능 목록과 해당 기능의 사용 여부|

#### <a name="product-and-service-usage-data-events"></a>제품 및 서비스 사용 데이터 이벤트

**보안 인텔리전스 업데이트 보고서**:

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|from_version|원래 보안 인텔리전스 버전입니다.|
|to_version|새 보안 인텔리전스 버전입니다.|
|status|성공 또는 실패를 나타내는 업데이트 상태입니다.|
|using_proxy|업데이트가 프록시를 통해 수행된 것인지 여부입니다.|
|error|업데이트가 실패한 경우 오류 코드입니다.|
|이유|업데이트가 실패한 경우 오류 메시지가 표시됩니다.|

#### <a name="product-and-service-performance-data-events-for-required-diagnostic-data"></a>필수 진단 데이터에 대한 제품 및 서비스 성능 데이터 이벤트

**커널 확장 통계**:

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|버전|Linux의 끝점용 Defender 버전입니다.|
|instance_id|커널 확장 시작 시 생성된 고유 식별자입니다.|
|trace_level|커널 확장의 추적 수준입니다.|
|subsystem|실시간 보호에 사용되는 밑이 있는 하위입니다.|
|ipc.connects|커널 확장에서 수신한 연결 요청 수입니다.|
|ipc.rejects|커널 확장에서 거부된 연결 요청 수입니다.|
|ipc.connected|커널 확장에 대한 활성 연결이 있는지 여부입니다.|

#### <a name="support-data"></a>지원 데이터

**진단 로그**:

진단 로그는 피드백 제출 기능의 일부로 사용자의 동의로만 수집됩니다. 다음 파일은 지원 로그의 일부로 수집됩니다.

- */var/log/microsoft/mdatp* 아래에 있는 모든 파일
- Linux의 Endpoint용 Defender에서 만들어 사용하는 */etc/opt/microsoft/mdatp* 아래에 있는 파일의 하위 집합
- */var/log/microsoft_mdatp_ \* .log* 아래에 있는 제품 설치 및 제거 로그

### <a name="optional-diagnostic-data"></a>선택적 진단 데이터

**선택적 진단 데이터는** Microsoft가 제품을 개선하는 데 도움이 되는 추가 데이터이며 문제를 감지, 진단 및 해결하는 데 도움이 되는 향상된 정보를 제공합니다.

선택 사항 진단 데이터를 보내시는 경우 필수 진단 데이터도 함께 보내야 합니다.

선택적 진단 데이터의 예로는 Microsoft가 제품 구성(예: 장치에 설정된 제외 수) 및 제품 성능(제품의 구성 요소 성능에 대한 집계 측정값)에 대해 수집하는 데이터가 포함됩니다.

#### <a name="software-setup-and-inventory-data-events-for-optional-diagnostic-data"></a>선택적 진단 데이터에 대한 소프트웨어 설정 및 인벤토리 데이터 이벤트

**끝점 구성에 대한 Microsoft Defender :**

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|connection_retry_timeout|연결은 클라우드와 통신할 때 시간 아웃을 다시 시도합니다.|
|file_hash_cache_maximum|제품 캐시의 크기입니다.|
|crash_upload_daily_limit|매일 업로드된 크래시 로그 제한.|
|antivirus_engine.exclusions[].is_directory|검사 제외가 디렉터리인지 여부입니다.|
|antivirus_engine.exclusions[].path|검사에서 제외된 경로입니다.|
|antivirus_engine.exclusions[].extension|검색에서 제외된 확장명입니다.|
|antivirus_engine.exclusions[].name|검사에서 제외된 파일의 이름입니다.|
|antivirus_engine.scan_cache_maximum|제품 캐시의 크기입니다.|
|antivirus_engine.maximum_scan_threads|검색에 사용되는 최대 스레드 수입니다.|
|antivirus_engine.threat_restoration_exclusion_time|파일에서 복원된 파일을 다시 검색하기 전의 시간입니다.|
|antivirus_engine.threat_type_settings|제품에서 다양한 위협 유형을 처리하는 방법에 대한 구성입니다.|
|filesystem_scanner.full_scan_directory|전체 검사 디렉터리.|
|filesystem_scanner.quick_scan_directories|빠른 검사에 사용되는렉터리 목록입니다.|
|edr.latency_mode|검색 및 응답 구성 요소에서 사용되는 대기 시간 모드입니다.|
|edr.proxy_address|검색 및 응답 구성 요소에서 사용하는 프록시 주소입니다.|

**Microsoft 자동 업데이트 구성**:

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|how_to_check|자동 또는 수동과 같은 제품 업데이트를 확인하는 방법을 확인합니다.|
|channel_name|장치와 연결된 채널을 업데이트합니다.|
|manifest_server|업데이트를 다운로드하는 데 사용되는 서버입니다.|
|update_cache|업데이트를 저장하는 데 사용되는 캐시 위치입니다.|

### <a name="product-and-service-usage"></a>제품 및 서비스 사용

#### <a name="diagnostic-log-upload-started-report"></a>진단 로그 업로드 시작 보고서

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|sha256|지원 로그의 SHA256 식별자입니다.|
|size|지원 로그의 크기입니다.|
|original_path|지원 로그 경로(항상 */var/opt/microsoft/mdatp/wdavdiag/ 아래).*|
|형식|지원 로그의 형식입니다.|

#### <a name="diagnostic-log-upload-completed-report"></a>진단 로그 업로드 완료된 보고서

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|request_id|지원 로그 업로드 요청의 상관 관계 ID입니다.|
|sha256|지원 로그의 SHA256 식별자입니다.|
|blob_sas_uri|응용 프로그램에서 지원 로그를 업로드하는 데 사용하는 URI입니다.|

#### <a name="product-and-service-performance-data-events-for-product-service-and-usage"></a>제품 서비스 및 사용에 대한 제품 및 서비스 성능 데이터 이벤트

**예기치 않은 응용 프로그램 종료(크래시)**:

예기치 않은 응용 프로그램 종료 및 종료 시의 응용 프로그램 상태입니다.

**커널 확장 통계**:

다음 필드가 수집됩니다.

|필드|설명|
|---|---|
|pkt_ack_timeout|다음 속성은 커널 확장 시작 이후 발생된 이벤트 수를 나타내는 집계된 숫자 값입니다.|
|pkt_ack_conn_timeout||
|ipc.ack_pkts||
|ipc.nack_pkts||
|ipc.send.ack_no_conn||
|ipc.send.nack_no_conn||
|ipc.send.ack_no_qsq||
|ipc.send.nack_no_qsq||
|ipc.ack.no_space||
|ipc.ack.timeout||
|ipc.ack.ackd_fast||
|ipc.ack.ackd||
|ipc.recv.bad_pkt_len||
|ipc.recv.bad_reply_len||
|ipc.recv.no_waiter||
|ipc.recv.copy_failed||
|ipc.kauth.vnode.mask||
|ipc.kauth.vnode.read||
|ipc.kauth.vnode.write||
|ipc.kauth.vnode.exec||
|ipc.kauth.vnode.del||
|ipc.kauth.vnode.read_attr||
|ipc.kauth.vnode.write_attr||
|ipc.kauth.vnode.read_ex_attr||
|ipc.kauth.vnode.write_ex_attr||
|ipc.kauth.vnode.read_sec||
|ipc.kauth.vnode.write_sec||
|ipc.kauth.vnode.take_own||
|ipc.kauth.vnode.link||
|ipc.kauth.vnode.create||
|ipc.kauth.vnode.move||
|ipc.kauth.vnode.mount||
|ipc.kauth.vnode.denied||
|ipc.kauth.vnode.ackd_before_deadline||
|ipc.kauth.vnode.missed_deadline||
|ipc.kauth.file_op.mask||
|ipc.kauth_file_op.open||
|ipc.kauth.file_op.close||
|ipc.kauth.file_op.close_modified||
|ipc.kauth.file_op.move||
|ipc.kauth.file_op.link||
|ipc.kauth.file_op.exec||
|ipc.kauth.file_op.remove||
|ipc.kauth.file_op.unmount||
|ipc.kauth.file_op.fork||
|ipc.kauth.file_op.create||

## <a name="resources"></a>리소스

- [Microsoft 개인 정보](https://privacy.microsoft.com/)
