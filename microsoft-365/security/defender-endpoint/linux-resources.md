---
title: Linux 리소스의 끝점용 Microsoft Defender
ms.reviewer: ''
description: Linux의 끝점용 Microsoft Defender에 대한 리소스( 제거 방법, 진단 로그 수집 방법, CLI 명령 및 제품에 대한 알려진 문제 포함)에 대해 설명
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
ms.openlocfilehash: 8596cf95c7aa4479d1900ba99c98bc10025ee738
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187484"
---
# <a name="resources"></a>리소스

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>진단 정보 수집

문제를 재현할 수 있는 경우 먼저 로깅 수준을 높이고, 시스템을 어느 정도 실행한 다음 로깅 수준을 기본값으로 복원합니다.

1. 로깅 수준 증가:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. 문제를 재현합니다.

3. 다음 명령을 실행하여 끝점 로그에 대한 Defender를 백업합니다. 파일은 보관 파일 내부에 .zip 저장됩니다.

   ```bash
   sudo mdatp diagnostic create
   ```

    또한 이 명령은 작업이 성공한 후 백업에 대한 파일 경로를 출력합니다.

   ```Output
   Diagnostic file created: <path to file>
   ```

4. 로깅 수준 복원:

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>로그 설치 문제

설치 중에 오류가 발생하면 설치 관리자에서 일반적인 오류만 보고합니다.

자세한 로그는 에 `/var/log/microsoft/mdatp/install.log` 저장됩니다.
설치 중에 문제가 발생하면 이 파일을 보내 원인을 진단하는 데 도움을 받을 수 있습니다.

## <a name="uninstall"></a>제거

Linux에서 끝점용 Defender를 제거하는 방법에는 여러 가지가 있습니다. Puppet과 같은 구성 도구를 사용하는 경우 구성 도구에 대한 패키지 제거 지침을 따릅니다.

### <a name="manual-uninstallation"></a>수동 제거

- `sudo yum remove mdatp` RHEL 및 variants(CentOS 및 Oracle Linux)의 경우
- `sudo zypper remove mdatp` SLES 및 변형의 경우
- `sudo apt-get purge mdatp` Ubuntu 및 데비안 시스템용입니다.

## <a name="configure-from-the-command-line"></a>명령줄에서 구성

명령줄에서 제품 설정 제어 및 명령 시 검사 트리거와 같은 중요한 작업을 수행할 수 있습니다.

### <a name="global-options"></a>전역 옵션

기본적으로 명령줄 도구는 결과를 사람이 읽을 수 있는 형식으로 출력합니다. 또한 이 도구는 결과를 JSON으로 출력할 수 있습니다. 이는 자동화 시나리오에 유용합니다. 출력을 JSON으로 변경하기 위해 다음 명령 `--output json` 중 한 개를 전달합니다.

### <a name="supported-commands"></a>지원되는 명령

다음 표에는 가장 일반적인 몇 가지 시나리오에 대한 명령이 나열됩니다. 터미널에서 `mdatp help` 실행하여 지원되는 명령의 전체 목록을 볼 수 있습니다.

<br>

****

|그룹|시나리오|명령|
|---|---|---|
|구성|실시간 보호 켜기/끄기|`mdatp config real-time-protection --value [enabled\|disabled]`|
|구성|동작 모니터링 켜기/끄기|`mdatp config behavior-monitoring --value [enabled\|disabled]`
|구성|클라우드 보호 켜기/끄기|`mdatp config cloud --value [enabled\|disabled]`|
|구성|제품 진단 켜기/끄기|`mdatp config cloud-diagnostic --value [enabled\|disabled]`|
|구성|자동 샘플 제출 켜기/끄기|`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`|
|구성|AV 수동 모드 켜기/끄기|`mdatp config passive-mode --value [enabled\|disabled]`|
|구성|파일 확장명에 대한 바이러스 백신 제외 추가/제거|`mdatp exclusion extension [add\|remove] --name [extension]`|
|구성|파일에 대한 바이러스 백신 제외 추가/제거|`mdatp exclusion file [add\|remove] --path [path-to-file]`|
|구성|디렉터리에 대한 바이러스 백신 제외 추가/제거|`mdatp exclusion folder [add\|remove] --path [path-to-directory]`|
|구성|프로세스에 대한 바이러스 백신 제외 추가/제거|`mdatp exclusion process [add\|remove] --path [path-to-process]` <p> `mdatp exclusion process [add\|remove] --name [process-name]`|
|구성|모든 바이러스 백신 제외 목록|`mdatp exclusion list`|
|구성|허용 목록에 위협 이름 추가|`mdatp threat allowed add --name [threat-name]`|
|구성|허용된 목록에서 위협 이름 제거|`mdatp threat allowed remove --name [threat-name]`|
|구성|허용된 모든 위협 이름 나열|`mdatp threat allowed list`|
|구성|PUA 보호 켜기|`mdatp threat policy set --type potentially_unwanted_application --action block`|
|구성|PUA 보호 끄기|`mdatp threat policy set --type potentially_unwanted_application --action off`|
|구성|PUA 보호에 대한 감사 모드 켜기|`mdatp threat policy set --type potentially_unwanted_application --action audit`|
|진단|로그 수준 변경|`mdatp log level set --level verbose [error|warning|info|verbose]`|
|진단|진단 로그 생성|`mdatp diagnostic create --path [directory]`|
|상태|제품의 상태 확인|`mdatp health`|
|보호|경로 검사|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|보호|빠른 검사 실행|`mdatp scan quick`|
|보호|전체 검사 실행|`mdatp scan full`|
|보호|지속적인 주문형 검사 취소|`mdatp scan cancel`|
|보호|보안 인텔리전스 업데이트 요청|`mdatp definitions update`|
|보호 기록|전체 보호 기록 인쇄|`mdatp threat list`|
|보호 기록|위협 세부 정보 확인|`mdatp threat get --id [threat-id]`|
|Quarantine management|모든 고지된 파일 나열|`mdatp threat quarantine list`|
|Quarantine management|Quarantine에서 모든 파일 제거|`mdatp threat quarantine remove-all`|
|Quarantine management|위협으로 감지된 파일 추가|`mdatp threat quarantine add --id [threat-id]`|
|Quarantine management|위협으로 감지된 파일 제거|`mdatp threat quarantine remove --id [threat-id]`|
|Quarantine management|Quarantine에서 파일 복원|`mdatp threat quarantine restore --id [threat-id]`|
|끝점 검색 및 응답|초기 미리 보기 설정(사용되지 않은)|`mdatp edr early-preview [enable|disable]`|
|끝점 검색 및 응답|group-id 설정|`mdatp edr group-ids --group-id [group-id]`|
|끝점 검색 및 응답|태그 설정/제거(지원되는 `GROUP` 태그만)|`mdatp edr tag set --name GROUP --value [tag]`|
|끝점 검색 및 응답|목록 제외(루트)|`mdatp edr exclusion list [processes|paths|extensions|all]`|
|

## <a name="microsoft-defender-for-endpoint-portal-information"></a>끝점 포털 정보용 Microsoft Defender

끝점용 Defender 포털에는 다음과 같은 두 가지 범주의 정보가 있습니다.

- 다음을 비롯한 바이러스 백신 경고
  - 심각도
  - 검사 유형
  - 장치 정보(호스트 이름, 장치 식별자, 테넌트 식별자, 앱 버전 및 OS 유형)
  - 파일 정보(이름, 경로, 크기 및 해시)
  - 위협 정보(이름, 유형 및 상태)
- 다음을 비롯한 장치 정보
  - 장치 식별자
  - 테넌트 식별자
  - 앱 버전
  - Hostname(호스트 이름)
  - OS 유형
  - OS 버전
  - 컴퓨터 모델
  - 프로세서 아키텍처
  - 디바이스가 가상 컴퓨터인지 여부

### <a name="known-issues"></a>알려진 문제

- 제품이 예상대로 작동하고 있도 Microsoft 365 Defender 포털의 컴퓨터 정보 페이지에 "센서 데이터 없음, 통신 장애가 있습니다."가 표시될 수 있습니다. We are working on addressing this issue.
- 로그온한 사용자가 로그인 포털에 Microsoft 365 Defender 않습니다.
- SUSE 배포에서 *libatomic1* 설치가 실패하면 OS가 등록되어 있는지 유효성을 검사해야 합니다.

   ```bash
   sudo SUSEConnect --status-text
   ```
