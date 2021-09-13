---
title: 끝점용 Microsoft Defender 업데이트를 예약하는 방법(Linux)
description: 조직의 자산을 보다 잘 보호하기 위해 끝점용 Microsoft Defender(Linux)의 업데이트를 예약하는 방법을 배워야 합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 검사, 바이러스 백신, 끝점용 Microsoft Defender(linux)
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
ms.openlocfilehash: 05747374e2a28331ec0742fe11ca2dbc660771c5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220504"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>엔드포인트용 Microsoft Defender(Linux) 업데이트 예약

Linux의 끝점용 Microsoft Defender에서 업데이트를 실행하기 위해 Linux에서 [끝점용 Microsoft Defender 업데이트 배포를 참조하세요.](/microsoft-365/security/defender-endpoint/linux-updates)

Linux(및 Unix)에는 예약된 작업을 실행할 수 있는 **크로ntab(작업** 스케줄러와 유사)라는 도구가 있습니다.

## <a name="pre-requisite"></a>필수 조건

> [!NOTE]
> 모든 표준 시간대 목록을 얻습니다. 다음 명령을 실행합니다. `timedatectl list-timezones`
>
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
sudo crontab -l > /var/tmp/cron_backup_201118.dat
```

> [!NOTE]
> 여기서 201118 == YYMMDD

> [!TIP]
> 편집하거나 제거하기 전에 이 작업을 합니다.

크로ntab를 편집하고 루트 사용자로 새 작업을 추가하려면

```bash
sudo crontab -e
```

> [!NOTE]
> 기본 편집기는 VIM입니다.

다음이 표시될 수 있습니다.

```output
0****/etc/opt/microsoft/mdatp/logrorate.sh
```

및

```output
02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log
```

끝점에 대한 [Microsoft Defender 검사 예약(Linux) 참조](linux-schedule-scan-atp.md)

"Insert" 누르기

다음 항목을 추가합니다.

```bash
CRON_TZ=America/Los_Angeles
```

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL 및 변형(CentOS 및 Oracle Linux)
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo yum update mdatp >> ~/mdatp_cron_job.log
> ```

> #<a name="sles-and-variants"></a>! SLES 및 변형
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo zypper update mdatp >> ~/mdatp_cron_job.log
> ```

> #<a name="ubuntu-and-debian-systems"></a>! Ubuntu 및 데비안 시스템
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo apt-get install --only-upgrade mdatp >> ~/mdatp_cron_job.log
> ```

> [!NOTE]
> 위의 예제에서는 일요일, 모든 월의 하루를 00분, 오후 6시(24시간 형식의 시간)로 설정하고 있습니다. [$(date + \% d) -le 15] == 15일(3주)보다 작거나 같지 않으면 실행되지 않습니다. 즉, 이 매월 3일 일요일(7)은 매일 아침 6시에 실행됩니다. 태평양(UTC -8).

"Esc" 누르기

" `:wq` " w/o를 입력합니다.

> [!NOTE]
> w == write, q == quit

크로인 작업을 보시고 입력합니다. `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="Linux에서 끝점용 Defender를 업데이트합니다.":::

크론 작업을 검사하기 위해 실행됩니다.

```bash
sudo grep mdatp /var/log/cron
```

mdatp_cron_job.log

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Ansible, 정적 또는 Puppet을 사용하는 사람

다음 명령을 사용 합니다.

### <a name="to-set-cron-jobs-in-ansible"></a>Ansible에서 크론 작업을 설정

```bash
cron - Manage cron.d and crontab entries
```

자세한 내용은 <https://docs.ansible.com/ansible/latest/modules/cron_module.html>을(를) 참조하세요. 

### <a name="to-set-crontabs-in-chef"></a>To set crontabs in아이프리드

```bash
cron resource
```

자세한 내용은 <https://docs.chef.io/resources/cron/>을(를) 참조하세요. 

### <a name="to-set-cron-jobs-in-puppet"></a>Puppet에서 크론 작업을 설정하는 경우

자원 유형: cron

자세한 내용은 <https://puppet.com/docs/puppet/5.5/types/cron.html>을(를) 참조하세요. 

Puppet으로 자동화: Cron 작업 및 예약된 작업

자세한 내용은 <https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/>을(를) 참조하세요. 

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

<pre>
+—————- minute (values: 0 - 59) (special characters: , - * /)  <br>
| +————- hour (values: 0 - 23) (special characters: , - * /) <br>
| | +———- day of month (values: 1 - 31) (special characters: , - * / L W C)  <br>
| | | +——- month (values: 1 - 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 - 6) (Sunday=0 or 7) (special characters: , - * / L W C) <br>
| | | | |*****command to be executed
</pre>
