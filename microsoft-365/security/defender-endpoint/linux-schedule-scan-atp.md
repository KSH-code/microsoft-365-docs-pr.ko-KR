---
title: 끝점용 Microsoft Defender를 통해 검사 예약 방법(Linux)
description: 조직의 자산을 보다 잘 보호하기 위해 끝점용 Microsoft Defender(Linux)에 대한 자동 검사 시간을 예약하는 방법을 학습합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 검사, 바이러스 백신, 끝점용 Microsoft Defender(linux)
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 89e4c7fa5462f65d11b36cad205e18ccbee8542b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211036"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>끝점용 Microsoft Defender를 통해 검사 예약(Linux)

Linux에 대한 검색을 실행하기 위해 [지원되는 명령을 참조합니다.](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)

Linux(및 Unix)에는 예약된 작업을 실행할 수 있는 **크로ntab(작업** 스케줄러와 유사)라는 도구가 있습니다.

## <a name="pre-requisite"></a>필수 조건

> [!NOTE]
> 모든 표준 시간대 목록을 얻습니다. 다음 명령을 실행합니다. `timedatectl list-timezones`<br>
> 타임존의 예:
>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Cron 작업을 설정하는 경우

다음 명령을 사용 합니다.

### <a name="backup-crontab-entries"></a>크로ntab 항목 백업

```bash
sudo crontab -l > /var/tmp/cron_backup_200919.dat
```

> [!NOTE]
> 여기서 200919 == YRMMDD

> [!TIP]
> 편집하거나 제거하기 전에 이 작업을 합니다.

크로ntab를 편집하고 루트 사용자로 새 작업을 추가하려면

```bash
sudo crontab -e
```

> [!NOTE]
> 기본 편집기는 VIM입니다.

다음이 표시될 수 있습니다.

```outbou
0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh
```

"Insert" 누르기

다음 항목을 추가합니다.

```bash
CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log
```

> [!NOTE]
> 이 예제에서는 이 예제를 00분, 2시로 설정하고 있습니다. (24시간 형식의 시간), 월의 모든 일, 모든 월, 토요일 즉, 토요일은 토요일 오후 2시에 실행됩니다. 태평양(UTC -8).

"Esc" 누르기

따옴표 `:wq` 없이 " "를 입력합니다.

> [!NOTE]
> w == write, q == quit

크로인 작업을 보시고 입력합니다. `sudo crontab -l`

:::image type="content" source="../../media/linux-mdatp-1.png" alt-text="linux mdatp.":::

#### <a name="to-inspect-cron-job-runs"></a>크론 작업 실행을 검사하기 위해

```bash
sudo grep mdatp /var/log/cron
```

#### <a name="to-inspect-the-mdatp_cron_joblog"></a>mdatp_cron_job.log*

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Ansible, 정적 또는 Puppet을 사용하는 사람

다음 명령을 사용 합니다.

### <a name="to-set-cron-jobs-in-ansible"></a>Ansible에서 크론 작업을 설정

```bash
cron - Manage cron.d and crontab entries

See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.

### To set crontabs in Chef

```bash
cron resource
```bash

```
자세한 내용은 <https://docs.chef.io/resources/cron/>을(를) 참조하세요. 

### <a name="to-set-cron-jobs-in-puppet"></a>Puppet에서 크론 작업을 설정하는 경우

```bash
Resource Type: cron
```

자세한 내용은 <https://puppet.com/docs/puppet/5.5/types/cron.html>을(를) 참조하세요. 

Puppet으로 자동화: Cron 작업 및 예약된 작업

자세한 내용은 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)을 참조하세요. 

## <a name="additional-information"></a>추가 정보

### <a name="to-get-help-with-crontab"></a>크로ntab에 대한 도움말을 얻은 경우

```bash
man crontab
```

### <a name="to-get-a-list-of-crontab-file-of-the-current-user"></a>현재 사용자의 크로ntab 파일 목록을 얻은 경우

```bash
crontab -l
```

### <a name="to-get-a-list-of-crontab-file-of-another-user"></a>다른 사용자의 크로ntab 파일 목록을 얻은 경우

```bash
crontab -u username -l
```

### <a name="to-backup-crontab-entries"></a>크로ntab 항목을 백업하는 경우

```bash
crontab -l > /var/tmp/cron_backup.dat
```

> [!TIP]
> 편집하거나 제거하기 전에 이 작업을 합니다.

### <a name="to-restore-crontab-entries"></a>크로ntab 항목을 복원하는 경우

```bash
crontab /var/tmp/cron_backup.dat
```

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>크로ntab를 편집하고 루트 사용자로 새 작업을 추가하려면

```bash
sudo crontab -e
```

### <a name="to-edit-the-crontab-and-add-a-new-job"></a>크로ntab를 편집하고 새 작업을 추가하려면

```bash
crontab -e
```

### <a name="to-edit-other-users-crontab-entries"></a>다른 사용자의 크로ntab 항목을 편집하려면

```bash
crontab -u username -e
```

### <a name="to-remove-all-crontab-entries"></a>모든 크로ntab 항목을 제거하려면

```bash
crontab -r
```

### <a name="to-remove-other-users-crontab-entries"></a>다른 사용자의 크로ntab 항목을 제거하려면

```bash
crontab -u username -r
```

### <a name="explanation"></a>설명

+—————- 분(값: 0 - 59)(특수 문자: , - * /)  <br>
| +————- 시간(값: 0 - 23)(특수 문자: , - * /) <br>
| | +———- 일 수(값: 1 - 31)(특수 문자: , - * / L W C)  <br>
| | | +——-(값: 1 - 12)(특수 문자: ,- * / )  <br>
| | | | +-- 주(값: 0 - 6)(Sunday=0 또는 7)(특수 문자: , - * / L W C) <br>
| | | | |*****명령을 실행합니다.
