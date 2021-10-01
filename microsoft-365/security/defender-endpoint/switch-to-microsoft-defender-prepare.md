---
title: 끝점용 Microsoft Defender로 전환 - 준비
description: 끝점용 Microsoft Defender로 전환할 준비를 합니다. 장치를 업데이트하고 네트워크 연결을 구성합니다.
keywords: 마이그레이션, 끝점용 Microsoft Defender, 모범 사례
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.date: 09/23/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 436b6725db916fdbf4497988343b4fc1b8ec9110
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60043002"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>끝점용 Microsoft Defender로 전환 - 1단계: 준비

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![1단계: 준비.](images/phase-diagrams/prepare.png)<br/>1 단계: 준비 | [![2 단계: 설정](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[2 단계: 설정](switch-to-microsoft-defender-setup.md) | [![3 단계: 온보딩](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[3 단계: 온보딩](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*여기 있습니다!*| | |

**[Endpoint용 Defender로 전환하는 준비 단계에 오신 것을 환영합니다.](switch-to-microsoft-defender-migration.md#the-migration-process)**

이 마이그레이션 단계에는 다음 단계가 포함됩니다.

1. [조직 장치에 업데이트 다운로드 및 배포](#get-and-deploy-updates-across-your-organizations-devices)
2. [끝점용 Defender를 을(를) 얻습니다.](#get-microsoft-defender-for-endpoint)
3. [Microsoft 365 Defender 액세스 권한을 부여합니다.](#grant-access-to-the-microsoft-365-defender-portal)
4. [장치 프록시 및 인터넷 연결 설정을 구성합니다.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>조직 장치에 업데이트 다운로드 및 배포

조직의 장치 및 끝점을 최신으로 유지하는 것이 가장 좋은 모범 사례입니다. 기존 끝점 보호 및 바이러스 백신 솔루션이 최신 상태로 유지 관리되는 운영 체제 및 앱에도 최신 업데이트가 있는지 확인합니다. 이제 이 작업을 수행하면 나중에 Endpoint 및 2013용 Defender로 마이그레이션할 때 문제를 방지하는 데 도움이 Microsoft Defender 바이러스 백신.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>기존 솔루션을 최신으로 유지해야 합니다.

기존 끝점 보호 솔루션을 최신으로 유지하고 조직의 장치에 최신 보안 업데이트가 있는지 확인합니다.

도움이 필요하신가요? 솔루션 공급자 설명서를 참조하세요.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>조직의 장치를 최신으로 유지해야 합니다.

조직의 장치를 업데이트하는 데 도움이 필요하세요? 다음 리소스를 참조하십시오.

<br/><br/>

|OS|리소스|
|---|---|
|Windows|[Microsoft 업데이트](https://www.update.microsoft.com)|
|macOS|[Mac에서 소프트웨어를 업데이트하는 방법](https://support.apple.com/HT201541)|
|iOS|[iPhone, iPad 또는 iPod 터치 업데이트](https://support.apple.com/HT204204)|
|Android|[Android & 업데이트 확인](https://support.google.com/android/answer/7680439)|
|Linux|[Linux 101: 시스템 업데이트](https://www.linux.com/training-tutorials/linux-101-updating-your-system)|

## <a name="get-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender 다운로드

조직의 장치를 업데이트한 후 다음 단계는 Endpoint용 Defender를 다운로드하고 라이선스를 할당한 다음 서비스가 프로비전되어 있는지를 확인 하는 것입니다.

1. 지금 끝점용 Defender를 구입하거나 사용해 보아야 합니다. [무료 평가판을 시작하거나 견적을 요청합니다.](https://aka.ms/mdatp)

2. 라이선스가 올바르게 프로비전되었는지 확인합니다. [라이선스 상태를 확인 합니다.](production-deployment.md#check-license-state)

3. 끝점용 Defender의 전용 클라우드 인스턴스를 설정합니다. [Endpoint 설치: 테넌트 구성에 대한 Defender를 참조합니다.](production-deployment.md#tenant-configuration)

4. 조직의 끝점(예: 장치)이 프록시를 사용하여 인터넷에 액세스하는 경우 Endpoint 설치용 [Defender: 네트워크 구성을 참조합니다.](production-deployment.md#network-configuration)

이제 Microsoft 365 Defender 포털()을 사용할 보안 관리자 및 보안 운영자에 대한 액세스 권한을 부여할 수 [https://security.microsoft.com](https://security.microsoft.com) 있습니다.

> [!NOTE]
> Microsoft 365 Defender 포털을 끝점용 Defender 포털이라고도 하며 에서 액세스할 수 [https://security.microsoft.com](https://security.microsoft.com) 있습니다. 이전 Microsoft Defender 보안 센터(는 곧 Microsoft 365 Defender https://securitycenter.windows.com) 포털로 리디렉션됩니다. 자세한 내용은 Microsoft 365 Defender [개요를 참조하세요.](portal-overview.md)

## <a name="grant-access-to-the-microsoft-365-defender-portal"></a>웹 사이트 포털에 Microsoft 365 Defender 권한 부여

Microsoft 365 Defender 포털()에서는 끝점용 Defender의 기능에 액세스하고 [https://security.microsoft.com](https://security.microsoft.com) 구성할 수 있습니다. 자세한 내용은 포털 [개요를 Microsoft 365 Defender 참조하세요.](use.md)

기본 사용 Microsoft 365 Defender RBAC(역할 기반 액세스 제어)를 사용하여 사이트 포털에 대한 사용 권한을 부여할 수 있습니다. 사용 권한을 보다 세밀하게 제어할 수 있도록 RBAC를 사용하는 것이 좋습니다.

1. 보안 관리자 및 보안 운영자에 대한 역할 및 사용 권한을 계획합니다. 역할 [기반 액세스 제어를 참조합니다.](prepare-deployment.md#role-based-access-control)

2. RBAC를 설정하고 구성합니다. [Intune을](/mem/intune/fundamentals/what-is-intune) 사용하여 RBAC를 구성하는 것이 좋습니다. 특히 조직에서 Windows 10, macOS, iOS 및 Android 장치의 조합을 사용하는 경우입니다. [Intune을 사용하여 RBAC 설정을 참조합니다.](/mem/intune/fundamentals/role-based-access-control)

    조직에서 Intune 외의 방법이 필요한 경우 다음 옵션 중 하나를 선택합니다.

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [고급 그룹 정책 관리](/microsoft-desktop-optimization-pack/agpm)
    - [Windows 관리 센터](/windows-server/manage/windows-admin-center/overview)

3. 사이트 포털에 대한 Microsoft 365 Defender 부여합니다. (도움이 필요하세요? [RBAC를 사용하여 포털 액세스 관리를 참조합니다.](rbac.md)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>장치 프록시 및 인터넷 연결 설정 구성

장치와 끝점용 Defender 간의 통신을 사용하도록 설정하려면 프록시 및 인터넷 설정을 구성합니다. 다음 표에는 다양한 운영 체제 및 기능에 대한 프록시 및 인터넷 설정을 구성하는 데 사용할 수 있는 리소스에 대한 링크가 포함되어 있습니다.

<br/><br/>

|기능|운영 체제|리소스|
|---|---|---|
|[끝점 검색 및](overview-endpoint-detection-response.md) 응답(EDR)|[Windows 10](/windows/release-health/release-information) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019) <p>Windows Server 2022 <p> <p> [Windows Server 1803 이상](/windows-server/get-started/whats-new-in-windows-server-1803)|[컴퓨터 프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md)|
|EDR|[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p> [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p> [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) <p> [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p> [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)|[프록시 및 인터넷 연결 설정 구성](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings)|
|EDR|macOS: 11.3.1(Big Sur); 10.15(카탈로나); 10.14(모잡)|[MacOS의 끝점용 Defender: 네트워크 연결](microsoft-defender-endpoint-mac.md#network-connections)|
|[Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)|[Windows 10](/windows/release-health/release-information) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p> Windows Server 2022 <p> [Windows Server 1803 이상](/windows-server/get-started/whats-new-in-windows-server-1803) <p> [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)|[Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사](configure-network-connections-microsoft-defender-antivirus.md)|
|바이러스 검사|macOS: 11.3.1(Big Sur); 10.15(카탈로나); 10.14(모잡)|[MacOS의 끝점용 Defender: 네트워크 연결](microsoft-defender-endpoint-mac.md#network-connections)|
|바이러스 검사|Linux: RHEL 7.2+; CentOS Linux 7.2+; Ubuntu 16 LTS 이상; SLES 12+; 데비안 9+; Oracle Linux 7.2|[Linux의 끝점용 Defender: 네트워크 연결](microsoft-defender-endpoint-linux.md#network-connections)|


## <a name="next-step"></a>다음 단계

**축하합니다!** 끝점용 [Defender로 전환하는 준비 단계를 완료했습니다!](switch-to-microsoft-defender-migration.md#the-migration-process) 

- [끝점에 대한 Defender 설정으로 진행합니다.](switch-to-microsoft-defender-setup.md)
