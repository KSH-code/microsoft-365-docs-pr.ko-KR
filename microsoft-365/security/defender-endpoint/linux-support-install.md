---
title: Linux의 끝점용 Microsoft Defender 설치 문제 해결
ms.reviewer: ''
description: Linux의 끝점용 Microsoft Defender 설치 문제 해결
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 설치
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
ms.openlocfilehash: a8f30a42fac3cc52de38e06b4193ab4098258262
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "60478904"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux의 끝점용 Microsoft Defender 설치 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-that-the-installation-succeeded"></a>설치가 성공한지 확인

설치 시 오류가 발생하거나 패키지 관리자가 의미 있는 오류 메시지를 표시하지 않을 수 있습니다. 설치가 성공적이지 확인하려면 다음을 사용하여 설치 로그를 구하고 검사합니다.

```bash
 sudo journalctl --no-pager|grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

올바른 설치 날짜와 시간이 있는 이전 명령의 출력은 성공을 나타냅니다.

또한 [클라이언트 구성을 확인하여](linux-install-manually.md#client-configuration) 제품의 상태와 EICAR 텍스트 파일을 검색합니다.

## <a name="make-sure-you-have-the-correct-package"></a>올바른 패키지가 있는지 확인

설치하는 패키지가 호스트 배포 및 버전과 일치하는지 확인

<br>

****

|package|distribution|
|---|---|
|mdatp-rhel8. Linux.x86_64.rpm|Oracle, RHEL 및 CentOS 8.x|
|mdatp-sles12. Linux.x86_64.rpm|SUSE Linux Enterprise Server 12.x|
|mdatp-sles15. Linux.x86_64.rpm|SUSE Linux Enterprise Server 15.x|
|mdatp. Linux.x86_64.rpm|Oracle, RHEL 및 CentOS 7.x|
|mdatp. Linux.x86_64.deb|데비안 및 Ubuntu 16.04, 18.04 및 20.04|
|

수동 [배포의 경우](linux-install-manually.md)올바른 배포판과 버전이 선택되어 있는지 확인합니다.

## <a name="installation-failed"></a>설치 실패

Endpoint용 Defender 서비스가 실행 중인지 확인:

```bash
service mdatp status
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-the-mdatp-service-isnt-running"></a>mdatp 서비스가 실행되고 있지 않은 경우 문제 해결 단계

1. "mdatp" 사용자가 존재하는지 확인:

    ```bash
    id "mdatp"
    ```

    출력이 없는 경우 를 실행합니다.

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. 다음을 사용하여 서비스를 사용하도록 설정하고 다시 시작하십시오.

    ```bash
    sudo service mdatp start
    ```

    ```bash
    sudo service mdatp restart
    ```

3. 이전 명령을 실행할 때 mdatp.service를 찾을 수 없는 경우 다음을 실행합니다.

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path> 
    ```

    여기서 `<systemd_path>` `/lib/systemd/system` 는 Rhel, CentOS, Oracle 및 SLES용 Ubuntu 및 Debian 배포 및 /usr/lib/systemd/system'에 대한 것입니다. 그런 다음 2단계를 다시 진행합니다.

4. 위의 단계가 작동하지 않는 경우 SELinux가 설치되어 있으며 실행 모드로 설정하는지 확인합니다. 이 경우 이를 사용(가급적) 또는 비활성화 모드로 설정해 보십시오. 이 매개 변수는 파일에서 매개 변수를 "사용" 또는 "사용 안 하게"로 설정한 다음 다시 부팅하여 `SELINUX` `/etc/selinux/config` 수행될 수 있습니다. 자세한 내용은 selinux의 man-page를 참조하세요.
이제 2단계를 사용하여 mdatp 서비스를 다시 시작합니다. 보안상의 이유로 구성 변경을 시도한 후 다시 시작한 후 즉시 구성 변경을 되버려야 합니다.

5. 디렉터리가 기호 링크인 경우 에 `/opt` 대한 바인딩 탑재를 만드십시오. `/opt/microsoft`

6. 데몬에 실행 권한이 있는지 확인

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    데몬에 실행 권한이 없는 경우 다음을 사용하여 실행할 수 있도록 합니다.

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    2단계를 실행하여 다시 시도합니다.

7. wdavdaemon을 포함하는 파일 시스템이 "noexec"로 탑재되어 있지 않은지 확인

## <a name="if-the-defender-for-endpoint-service-is-running-but-the-eicar-text-file-detection-doesnt-work"></a>Endpoint용 Defender 서비스가 실행 중이지만 EICAR 텍스트 파일 검색이 작동하지 않는 경우

1. 다음을 사용하여 파일 시스템 형식을 검사합니다.

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    액세스 활동에 대해 현재 지원되는 파일 시스템은 여기에 [나열되어 있습니다.](microsoft-defender-endpoint-linux.md#system-requirements) 이러한 파일 시스템 외부의 파일은 검색되지 않습니다.

## <a name="command-line-tool-mdatp-isnt-working"></a>명령줄 도구 "mdatp"가 작동하지 않습니다.

1. 명령줄 도구를 실행하면 오류가 `mdatp` `command not found` 발생하면 다음 명령을 실행합니다.

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    다시 시도하세요.

    위의 단계 중 도움이 해결하지 못하면 진단 로그를 수집합니다.

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    로그가 포함된 zip 파일의 경로가 출력으로 표시됩니다. 이러한 로그를 사용하여 고객 지원에 문의합니다.
