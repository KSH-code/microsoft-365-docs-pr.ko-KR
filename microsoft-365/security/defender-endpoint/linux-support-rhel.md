---
title: Linux RHEL6의 끝점용 Microsoft Defender 문제 해결
ms.reviewer: ''
description: Linux에서 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 클라우드, 연결, 통신
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0abb5615b0c1a51b06ec47eeb0c0e0718ebb7f9b
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "60479019"
---
# <a name="troubleshoot-issues-for-microsoft-defender-for-endpoint-on-linux-rhel6"></a>Linux RHEL6의 끝점용 Microsoft Defender 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

이 문서에서는 RED Hat Linux 6(RHEL 6) 이상에서 Linux용 Microsoft Defender에서 발생할 수 있는 문제를 해결하는 방법에 대한 지침을 제공합니다. 

패키지(mdatp_XXX.XX.XX.XX.x86_64.rpm)를 설치한 후 제공된 작업을 수행하여 설치가 성공적이지 확인합니다. 


## <a name="check-the-service-health"></a>서비스 상태 확인

다음 명령을 사용하여 서비스 상태 확인

```bash
mdatp health 
```

## <a name="verify-that-the-service-is-running"></a>서비스가 실행 중인지 확인

다음 명령을 사용하여 서비스가 실행되고 있는지 확인할 수 있습니다.

```bash
service mdatp status 
```

예상 출력: `mdatp start/running, process 4517`

## <a name="verify-the-distribution-and-kernel-version"></a>배포 및 커널 버전 확인
배포 및 커널 버전은 지원되는 목록에 표시해야 합니다.

다음 명령을 사용하여 배포 버전을 다운로드합니다.

```bash
cat /etc/redhat-release (or /etc/system-release) 
```

다음 명령을 사용하여 커널 버전을 다운로드합니다.

```bash
uname -r
```
## <a name="check-if-mdatp-audisp-process-is-running"></a>mdatp audisp 프로세스가 실행 중인지 확인 
예상된 출력은 프로세스가 실행되고 있는 것입니다.

다음 명령을 사용하여 다음을 검사합니다.

```bash
pidof mdatp_audisp_plugin 
```

## <a name="check-talpa-modules"></a>TALPA 모듈 확인
9개의 모듈이 로드됩니다. 

다음 명령을 사용하여 다음을 검사합니다.

```bash
lsmod | grep talpa
```

예상 출력: 사용

```bash
talpa_pedconnector       878  0 

talpa_pedevice          5189  2 talpa_pedconnector 

talpa_vfshook          32300  1 

talpa_vcdevice          4947  1 

talpa_syscall           9127  0 

talpa_core             90699  4 talpa_vfshook,talpa_vcdevice,talpa_syscall 

talpa_linux            29424  5 talpa_vfshook,talpa_vcdevice,talpa_syscall,talpa_core 

talpa_syscallhookprobe      882  0 

talpa_syscallhook      14987  2 talpa_vfshook,talpa_syscallhookprobe 
```


```bash
lsmod | grep talpa | wc -l 
```

예상 출력: 9

## <a name="check-talpa-status"></a>TALPA 상태 확인

```bash
cat /proc/sys/talpa/interceptors/VFSHookInterceptor/status 
```

로그 파일 디버그('mdatp 진단 만들기' 번들 외에도) 

```bash
/var/log/audit/audit.log 

/var/log/messages 

semanage fcontext -l > selinux.log 
```
 

성능 및 메모리 

```bash
top -p <wdavdaemon pid>      

pmap -x <wdavdaemon pid> 
```

를 `<wdavdaemon pid>` 사용하여 찾을 수 `pidof wdavdaemon` 있습니다.

