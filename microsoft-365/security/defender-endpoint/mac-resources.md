---
title: Mac의 끝점용 Microsoft Defender 리소스
description: Mac의 끝점용 Microsoft Defender 리소스(제거 방법, 진단 로그 수집 방법, CLI 명령 및 제품에서 알려진 문제 포함)
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 6b74732a54d875dfe08469b15e35fda9f59a8351
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156261"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>macOS의 끝점용 Microsoft Defender 리소스

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>진단 정보 수집

문제를 재현할 수 있는 경우 로깅 수준을 높이고, 시스템을 어느 정도 실행하고, 로깅 수준을 기본값으로 복원합니다.

1. 로깅 수준 증가:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. 문제 재현

3. 를 `sudo mdatp diagnostic create` 실행하여 끝점 로그에 대한 Microsoft Defender를 백업합니다. 파일은 보관 파일 내부에 .zip 저장됩니다. 또한 이 명령은 작업이 성공한 후 백업에 대한 파일 경로를 출력합니다.

   > [!TIP]
   > 기본적으로 진단 로그는 에 `/Library/Application Support/Microsoft/Defender/wdavdiag/` 저장됩니다. 진단 로그가 저장되는 디렉터리를 변경하려면 아래 명령으로 전달하여 원하는 디렉터리로 `--path [directory]` `[directory]` 바꿔야 합니다.

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. 로깅 수준 복원:

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>로깅 설치 문제

설치 중에 오류가 발생하면 설치 관리자에서 일반적인 오류만 보고합니다.

자세한 로그는 에 `/Library/Logs/Microsoft/mdatp/install.log` 저장됩니다. 설치 중에 문제가 발생하면 이 파일을 보내 원인을 진단하는 데 도움을 받을 수 있습니다.

## <a name="uninstalling"></a>Uninstalling

macOS에서 끝점용 Microsoft Defender를 제거하는 방법에는 여러 가지가 있습니다. JAMF에서 중앙에서 관리되는 제거를 사용할 수 있는 동안에는 아직 제거되지 Microsoft Intune.

### <a name="interactive-uninstallation"></a>대화형 제거

- Open **Finder > Applications**. **Endpoint용 Microsoft Defender를 마우스 오른쪽 단추로 > 휴지통으로 이동을 클릭합니다.**

### <a name="from-the-command-line"></a>명령줄에서

- `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`

## <a name="configuring-from-the-command-line"></a>명령줄에서 구성

명령줄에서 제품 설정 제어 및 명령 시 검사 트리거와 같은 중요한 작업을 수행할 수 있습니다.

|그룹|시나리오|명령|
|---|---|---|
|구성|실시간 보호 켜기/끄기|`mdatp config real-time-protection --value [enabled/disabled]`|
|구성|클라우드 보호 켜기/끄기|`mdatp config cloud --value [enabled/disabled]`|
|구성|제품 진단 켜기/끄기|`mdatp config cloud-diagnostic --value [enabled/disabled]`|
|구성|자동 샘플 제출 켜기/끄기|`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`|
|구성|허용 목록에 위협 이름 추가|`mdatp threat allowed add --name [threat-name]`|
|구성|허용된 목록에서 위협 이름 제거|`mdatp threat allowed remove --name [threat-name]`|
|구성|허용된 모든 위협 이름 나열|`mdatp threat allowed list`|
|구성|PUA 보호 켜기|`mdatp threat policy set --type potentially_unwanted_application -- action block`|
|구성|PUA 보호 끄기|`mdatp threat policy set --type potentially_unwanted_application -- action off`|
|구성|PUA 보호에 대한 감사 모드 켜기|`mdatp threat policy set --type potentially_unwanted_application -- action audit`|
|구성|바이러스 백신 수동 모드 켜기/끄기|`mdatp config passive-mode --value [enabled/disabled]`|
|구성|요구 시 검사에 대한 병렬 처리 수준 구성|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|구성|보안 인텔리전스 업데이트 후 검사 켜기/끄기|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|구성|보관 검색 켜기/끄기(요구 시 검사만 해당)|`mdatp config scan-archives --value [enabled/disabled]`|
|진단|로그 수준 변경|`mdatp log level set --level [error/warning/info/verbose]`|
|진단|진단 로그 생성|`mdatp diagnostic create --path [directory]`|
|상태|제품의 상태 확인|`mdatp health`|
|상태|spefic 제품 특성 확인|`mdatp health --field [attribute: healthy/licensed/engine_version...]`|
|보호|경로 검사|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|보호|빠른 검사 실행|`mdatp scan quick`|
|보호|전체 검사 실행|`mdatp scan full`|
|보호|지속적인 주문형 검사 취소|`mdatp scan cancel`|
|보호|보안 인텔리전스 업데이트 요청|`mdatp definitions update`|
|EDR|디바이스에 그룹 태그를 추가합니다. EDR 태그는 장치 그룹을 관리하는 데 사용됩니다. 자세한 내용은 /microsoft-365/security/defender-endpoint/machine-groups을 방문하세요.|`mdatp edr tag set --name GROUP --value [name]`|
|EDR|장치에서 그룹 태그 제거|`mdatp edr tag remove --tag-name [name]`|
|EDR|그룹 ID 추가|`mdatp edr group-ids --group-id [group]`|

### <a name="how-to-enable-autocompletion"></a>자동 작성을 사용하도록 설정하는 방법

bash에서 자동completion을 사용하도록 설정하려면 다음 명령을 실행하고 터미널 세션을 다시 시작합니다.

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

zsh에서 자동completion을 사용하도록 설정하려면

- 장치에서 자동completion을 사용할 수 있는지 확인합니다.

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- 위의 명령이 출력을 생성하지 않는 경우 다음 명령을 사용하여 자동 작성을 사용하도록 설정할 수 있습니다.

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- MacOS의 끝점용 Microsoft Defender에 대해 자동Completion을 사용하도록 설정하려면 다음 명령을 실행하고 터미널 세션을 다시 시작합니다.

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions

   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>클라이언트 Microsoft Defender for Endpoint quarantine directory

`/Library/Application Support/Microsoft/Defender/quarantine/` 에 의해 검색된 파일이 들어 `mdatp` 있습니다. 파일의 이름은 Threat trackingId의 이름입니다. 현재 trackingIds는 와 함께 `mdatp threat list` 표시됩니다.

## <a name="microsoft-defender-for-endpoint-portal-information"></a>끝점 포털 정보용 Microsoft Defender

[EDR macOS의](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)새로운 기능이 도착했습니다. 끝점용 Microsoft Defender 블로그에서는 끝점용 Microsoft Defender 보안 센터에서 기대할 수 있는 기능에 대한 자세한 지침을 제공합니다.
