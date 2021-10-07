---
title: Linux에서 끝점용 Microsoft Defender에 대한 누락된 이벤트 또는 경고 문제 해결
description: Linux의 끝점용 Microsoft Defender에서 누락된 이벤트 또는 경고 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 이벤트
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e53f959e75551fdd5b065514a1c990663a667201
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194144"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender에 대한 누락된 이벤트 또는 경고 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [Microsoft Defender for Endpoint(Linux용)](microsoft-defender-endpoint-linux.md)

이 문서에서는 사이트 포털 에서 누락된 이벤트 또는 알림을 완화하는 몇 가지 일반적인 [Microsoft 365 Defender 제공합니다.](https://security.microsoft.com/)

**끝점용 Microsoft Defender가** 장치에 올바르게 설치되면  포털에 장치 페이지가 생성됩니다. 디바이스 페이지의 시간 표시 막대 탭 또는 고급 헌팅 페이지에서 기록된 모든 이벤트를 검토할 수 있습니다. 이 섹션에서는 일부 또는 모든 예상 이벤트가 누락된 경우를 해결합니다.
예를 들어 _모든 CreatedFile_ 이벤트가 누락된 경우입니다.

## <a name="missing-network-and-login-events"></a>네트워크 및 로그인 이벤트 누락

끝점용 Microsoft Defender는 linux의 프레임워크를 활용하여 네트워크 및 로그인 `audit` 활동을 추적합니다.

1. 감사 프레임워크가 작동하고 있는지 확인

    ```bash
    service auditd status
    ```

    예상 출력:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. `auditd`중지됨으로 표시된 경우 시작합니다.

    ```bash
    service auditd start
    ```

**SLES 시스템에서** SYSCALL 감사는 기본적으로 사용하지 않도록 설정되어 있으며 누락된 이벤트를 `auditd` 고려할 수 있습니다.

1. SYSCALL 감사가 사용하지 않도록 설정되어 있지 않은지 확인을 위해 현재 감사 규칙을 나열합니다.

    ```bash
    sudo auditctl -l
    ```

    다음 줄이 있는 경우 해당 줄을 제거하거나 편집하여 끝점용 Microsoft Defender가 특정 SYSCAL을 추적할 수 있도록 합니다.

    ```output
    -a task, never
    ```

    감사 규칙은 에 `/etc/audit/rules.d/audit.rules` 있습니다.

## <a name="missing-file-events"></a>파일 이벤트 누락

파일 이벤트는 프레임워크를 통해 `fanotify` 수집됩니다. 일부 또는 모든 파일 이벤트가 누락되는 경우 장치에서 사용하도록 설정되어 있으며 파일 시스템이 `fanotify` 지원되는지 [확인합니다.](microsoft-defender-endpoint-linux.md#system-requirements)

컴퓨터의 파일 시스템 목록을 다음으로 나열합니다.

```bash
df -Th
```
