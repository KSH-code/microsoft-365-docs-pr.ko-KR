---
title: 엔드포인트용 Microsoft Defender(Linux용)
ms.reviewer: ''
description: Linux에서 끝점용 Microsoft Defender를 설치하고 사용하는 방법을 설명 합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, linux, 설치, 배포, 제거, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 1b8fceed1e749a21323ade7ee87ab54a7fcffde8
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "60478988"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>엔드포인트용 Microsoft Defender(Linux용)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

이 항목에서는 Linux에서 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.

> [!CAUTION]
> Linux에서 끝점용 Microsoft Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 부작용이 발생할 수 있습니다. 사용자 환경에서 비 Microsoft 끝점 보호가 절대적인 요구 사항이면 수동 모드에서 실행될 바이러스 백신 기능을 구성한 후에도 Linux EDR 끝점용 Defender를 안전하게 활용할 [수 있습니다.](linux-preferences.md#enable--disable-passive-mode)

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender를 설치하는 방법

### <a name="prerequisites"></a>필수 구성 요소

- Microsoft 365 Defender 액세스
- 시스템 [관리자를](https://systemd.io/) 사용하여 Linux 배포
- Linux 및 BASH 스크립팅의 초보자 수준 환경
- 디바이스의 관리 권한(수동 배포의 경우)

> [!NOTE]
> Linux 에이전트의 끝점용 Microsoft Defender는 [OMS 에이전트와 독립적입니다.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent) 끝점용 Microsoft Defender는 자체의 독립적인 원격 분석 파이프라인을 사용 합니다.


### <a name="installation-instructions"></a>설치 지침

Linux에서 끝점용 Microsoft Defender를 설치 및 구성하는 데 사용할 수 있는 몇 가지 방법 및 배포 도구가 있습니다.

일반적으로 다음 단계를 수행해야 합니다.

- Endpoint용 Microsoft Defender 구독이 있으며 끝점 포털용 [Microsoft Defender에](microsoft-defender-security-center.md)액세스할 수 있도록 합니다.
- 다음 배포 방법 중 하나를 사용하여 Linux에서 끝점용 Microsoft Defender를 배포합니다.
  - 명령줄 도구:
    - [수동 배포](linux-install-manually.md)
  - 타사 관리 도구:
    - [Puppet 구성 관리 도구를 사용하여 배포](linux-install-with-puppet.md)
    - [Ansible 구성 관리 도구를 사용하여 배포](linux-install-with-ansible.md)
    - [구성 관리 도구를 사용하여 배포](linux-deploy-defender-for-endpoint-with-chef.md)

설치 오류가 발생하면 [Linux의 끝점용 Microsoft Defender에서](linux-support-install.md)설치 실패 문제 해결을 참조하세요.

### <a name="system-requirements"></a>시스템 요구 사항

- 지원되는 Linux 서버 배포 및 x64(AMD64/EM64T) 버전:

  - Red Hat Enterprise Linux 6.7 이상
  - Red Hat Enterprise Linux 7.2 이상 
  - CentOS 6.7 이상 
  - CentOS 7.2 이상
  - Ubuntu 16.04 LTS 이상 LTS
  - 데비안 9 이상
  - SUSE Linux Enterprise Server 12 이상
  - Oracle Linux 7.2 이상
  - Amazon Linux 2
  - Fedora 33 이상

    > [!NOTE]
    > 명시적으로 나열되지 않은 배포 및 버전은 지원되지 않습니다(공식적으로 지원되는 배포에서 파생된 경우에도).


    Red Hat Enterprise Linux 6 및 CentOS 6의 경우 지원되는 커널 버전 목록은 다음입니다.
       - 6.7: 2.6.32-573.* 
       - 6.8: 2.6.32-642.* 
       - 6.9: 2.6.32-696.* 
       - 6.10의 경우: 2.6.32.754.2.1.el6.x86_64 2.6.32-754.41.2로:

    버전 목록:

    - 2.6.32-754.2.1.el6.x86_64 
    - 2.6.32-754.17.1.el6.x86_64
    - 2.6.32-754.29.1.el6.x86_64
    - 2.6.32-754.3.5.el6.x86_64 
    - 2.6.32-754.18.2.el6.x86_64
    - 2.6.32-754.29.2.el6.x86_64
    - 2.6.32-754.6.3.el6.x86_64 
    - 2.6.32-754.22.1.el6.x86_64
    - 2.6.32-754.30.2.el6.x86_64
    - 2.6.32-754.9.1.el6.x86_64 
    - 2.6.32-754.23.1.el6.x86_64
    - 2.6.32-754.33.1.el6.x86_64
    - 2.6.32-754.10.1.el6.x86_64
    - 2.6.32-754.24.2.el6.x86_64
    - 2.6.32-754.35.1.el6.x86_64
    - 2.6.32-754.11.1.el6.x86_64
    - 2.6.32-754.24.3.el6.x86_64
    - 2.6.32-754.39.1.el6.x86_64
    - 2.6.32-754.12.1.el6.x86_64
    - 2.6.32-754.25.1.el6.x86_64
    - 2.6.32-754.41.2.el6.x86_64
    - 2.6.32-754.14.2.el6.x86_64
    - 2.6.32-754.27.1.el6.x86_64
    - 2.6.32-754.15.3.el6.x86_64
    - 2.6.32-754.28.1.el6.x86_64       


- 최소 커널 버전 3.10.0-327

- 커널 `fanotify` 옵션을 사용하도록 설정해야 합니다.

  > [!CAUTION]
  > Linux에서 끝점용 Defender를 다른 기반 보안 솔루션과 나란히 실행하는 것은 `fanotify` 지원되지 않습니다. 운영 체제 중단을 포함하여 예측할 수 없는 결과가 발생할 수 있습니다.

- 디스크 공간: 1GB

- /opt/microsoft/mdatp/sbin/wdavdaemon에는 실행 권한이 필요합니다. 자세한 내용은 Linux의 끝점용 Microsoft Defender 설치 문제 해결에서 "디먼이 실행 가능한 권한을 가지는지 [확인"을 참조하세요.](/microsoft-365/security/defender-endpoint/linux-support-install)

- 코어: 최소 2개, 기본 설정 4개

- 메모리: 최소 1GB, 기본 설정 4개

    > [!NOTE]
    > /var에 디스크 공간이 있는지 확인하시기 바랍니다.

- 이 솔루션은 현재 다음과 같은 파일 시스템 형식에 대한 실시간 보호 기능을 제공합니다.

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

서비스를 사용하도록 설정한 후 네트워크 또는 방화벽에서 해당 서비스 및 끝점 간의 아웃바운드 연결을 허용하도록 구성해야 할 수 있습니다.

- 감사 프레임워크( `auditd` )를 사용하도록 설정해야 합니다.

  > [!NOTE]
  > 추가된 규칙에 의해 캡처된 시스템 이벤트는 (s)에 추가될 것이고 호스트 감사 및 업스트림 컬렉션에 영향을 `/etc/audit/rules.d/` `audit.log` 줄 수 있습니다. Linux의 끝점용 Microsoft Defender에서 추가한 이벤트는 키로 태그가 `mdatp` 지정됩니다.

### <a name="configuring-exclusions"></a>제외 구성

제외를 추가하는 Microsoft Defender 바이러스 백신 일반적인 제외 실수를 염두에 [두어야 Microsoft Defender 바이러스 백신](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)

### <a name="network-connections"></a>네트워크 연결

다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다. 이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인해야 합니다. 있는 경우 해당 규칙에 대해  특별히 허용 규칙을 만들어야 할 수 있습니다.

<br>

****

|도메인 목록의 스프레드시트|설명|
|---|---|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지입니다.](images/mdatp-urls.png)|서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다. <p> 여기에서 스프레드시트를 [다운로드합니다.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)|
|||

> [!NOTE]
> 보다 구체적인 URL 목록은 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

Endpoint용 Defender는 다음 검색 방법을 사용하여 프록시 서버를 검색할 수 있습니다.

- 투명한 프록시
- 수동 정적 프록시 구성

프록시 또는 방화벽에서 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인 투명한 proxies의 경우 끝점용 Defender에 대한 추가 구성이 필요하지 않습니다. 정적 프록시의 경우 수동 정적 프록시 [구성의 단계를 따릅니다.](linux-static-proxy-configuration.md)

> [!WARNING]
> PAC, WPAD 및 인증된 proxies는 지원되지 않습니다. 정적 프록시 또는 투명 프록시만 사용 중이지 않도록 합니다.
>
> 보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다. SSL 검사 및 프록시 서버에 대한 예외를 구성하여 Linux 끝점용 Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달합니다. 전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.

문제 해결 단계는 [Linux에서 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결을 참조하세요.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender를 업데이트하는 방법

Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다. Linux에서 끝점용 Microsoft Defender를 업데이트하기 위해 Linux에서 [끝점용 Microsoft Defender 업데이트 배포를 참조하세요.](linux-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 엔드포인트용 Microsoft Defender를 구성하는 방법

엔터프라이즈 환경에서 제품을 구성하는 방법에 대한 지침은 [Linux의 끝점용 Microsoft Defender](linux-preferences.md)기본 설정에서 사용할 수 있습니다.

## <a name="common-applications-to-microsoft-defender-for-endpoint-can-impact"></a>끝점용 Microsoft Defender에 대한 일반 응용 프로그램이 영향을 줄 수 있습니다.

특정 응용 프로그램의 I/O 워크로드가 높을 경우 끝점용 Microsoft Defender가 설치될 때 성능 문제가 생략될 수 있습니다. 여기에는 Jenkins 및 Jira와 같은 개발자 시나리오용 응용 프로그램과 OracleDB 및 Postgres와 같은 데이터베이스 워크로드가 포함됩니다. 성능 저하가 발생하는 경우 신뢰할 수 있는 응용 프로그램에 대해 [](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus) 제외를 설정하고 일반적인 제외 실수를 Microsoft Defender 바이러스 백신 고려합니다. 추가 지침은 타사 응용 프로그램의 바이러스 백신 제외와 관련한 컨설팅 설명서를 참조하세요.

## <a name="resources"></a>리소스

- 로깅, 지우기 또는 기타 항목에 대한 자세한 내용은 Resources 을 [참조하십시오.](linux-resources.md)
