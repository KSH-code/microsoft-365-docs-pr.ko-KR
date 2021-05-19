---
title: McAfee에서 끝점용 Microsoft Defender로의 준비
description: McAfee에서 끝점용 Microsoft Defender로 마이그레이션하기 위한 준비 1단계입니다.
keywords: migration, Microsoft Defender for Endpoint, edr
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 171c9b4ff02e7f6ddb6918e430af772f44b1777a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538786"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>McAfee에서 마이그레이션 - 1단계: 마이그레이션 준비

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![1 단계: 준비](images/phase-diagrams/prepare.png)<br/>1 단계: 준비 |[![2 단계: 설정](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[2 단계: 설정](mcafee-to-microsoft-defender-setup.md) |[![3 단계: 온보딩](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[3 단계: 온보딩](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*여기 있습니다!*| | |


**[McAfee 끝점 보안(McAfee)에서 Endpoint용 Defender로](mcafee-to-microsoft-defender-migration.md#the-migration-process)** 마이그레이션하는 준비 단계에 오신 것을 환영합니다. 

이 마이그레이션 단계에는 다음 단계가 포함됩니다.
1. [조직 장치에 업데이트 다운로드 및 배포](#get-and-deploy-updates-across-your-organizations-devices)

2. [끝점용 Defender를 을(를) 얻습니다.](#get-microsoft-defender-for-endpoint)

3. [에 대한 액세스 권한을 Microsoft Defender 보안 센터.](#grant-access-to-the-microsoft-defender-security-center)

4. [장치 프록시 및 인터넷 연결 설정을 구성합니다.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>조직 장치에 업데이트 다운로드 및 배포

조직의 장치 및 끝점을 최신으로 유지하는 것이 가장 좋은 모범 사례입니다. McAfee 끝점 보안(McAfee) 솔루션이 최신 버전이고 조직에 최신 업데이트가 적용된 운영 체제 및 앱도 있는지 확인합니다. 이렇게 하면 나중에 Endpoint용 Defender로 마이그레이션할 때 문제를 방지하는 데 도움이 됩니다.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>McAfee 솔루션이 최신지 확인

McAfee를 최신으로 유지하고 조직의 장치에 최신 보안 업데이트가 있는지 확인합니다. 도움이 필요하신가요? 다음은 몇 가지 McAfee 리소스입니다.

- [McAfee Enterprise 제품 설명서: Endpoint 보안 작동 방식](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [McAfee 기술 문서: Windows 보안 센터에서 실행 시 끝점 보안이 사용하지 않도록 설정되어 있는 경우 간헐적으로 잘못 Windows 10](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [McAfee 기술 문서: Windows 보안 센터 보고서는 끝점 보안이 실행 중일 때 끝점 보안을 사용할 수 없습니다.](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- McAfee 지원 ServicePortal( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>조직의 장치를 최신으로 유지해야 합니다.

조직의 장치를 업데이트하는 데 도움이 필요하세요? 다음 리소스를 참조하십시오.

|OS | 리소스 |
|:--|:--|
|Windows |[Microsoft 업데이트](https://www.update.microsoft.com) |
|macOS | [Mac에서 소프트웨어를 업데이트하는 방법](https://support.apple.com/HT201541)|
|iOS |[iPhone, iPad 또는 iPod 터치 업데이트](https://support.apple.com/HT204204)|
|Android |[Android & 업데이트 확인](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: 시스템 업데이트](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender 다운로드

조직의 장치를 업데이트한 후 다음 단계는 Endpoint용 Defender를 다운로드하고 라이선스를 할당한 다음 서비스가 프로비전되어 있는지를 확인 하는 것입니다.

1. 지금 끝점용 Defender를 구입하거나 사용해 보아야 합니다. [무료 평가판을 시작하거나 견적을 요청합니다.](https://aka.ms/mdatp) 

2. 라이선스가 올바르게 프로비전되었는지 확인합니다. [라이선스 상태를 확인 합니다.](production-deployment.md#check-license-state)

3. 전역 관리자 또는 보안 관리자는 끝점용 Defender의 전용 클라우드 인스턴스를 설정합니다. [Endpoint 설치: 테넌트 구성에 대한 Defender를 참조합니다.](production-deployment.md#tenant-configuration)

4. 조직의 끝점(예: 장치)이 프록시를 사용하여 인터넷에 액세스하는 경우 Endpoint 설치용 [Defender: 네트워크 구성을 참조합니다.](production-deployment.md#network-configuration)
 
이제 Microsoft Defender 보안 센터()를 사용할 보안 관리자 및 보안 운영자에 대한 액세스 권한을 부여할 준비가 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 보안 센터. 

> [!NOTE]
> 이 Microsoft Defender 보안 센터 끝점 포털의 Defender라고도 합니다. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>사용자 액세스 권한 Microsoft Defender 보안 센터

Microsoft Defender 보안 센터 ()는 끝점용 Defender의 기능에 액세스하고 구성하는 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 위치입니다. 자세한 내용은 의 [개요를 Microsoft Defender 보안 센터.](use.md)

기본 사용 Microsoft Defender 보안 센터 RBAC(역할 기반 액세스 제어)를 사용하여 사용 권한을 부여할 수 있습니다. 사용 권한을 보다 세밀하게 제어할 수 있도록 RBAC를 사용하는 것이 좋습니다.

1. 보안 관리자 및 보안 운영자에 대한 역할 및 사용 권한을 계획합니다. 역할 [기반 액세스 제어를 참조합니다.](prepare-deployment.md#role-based-access-control)

2. RBAC를 설정하고 구성합니다. [Intune을](/mem/intune/fundamentals/what-is-intune) 사용하여 RBAC를 구성하는 것이 좋습니다. 특히 조직에서 Windows 10, macOS, iOS 및 Android 장치의 조합을 사용하는 경우입니다. [Intune을 사용하여 RBAC 설정을 참조합니다.](/mem/intune/fundamentals/role-based-access-control)

    조직에서 Intune 외의 방법이 필요한 경우 다음 옵션 중 하나를 선택합니다.

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [고급 그룹 정책 관리](/microsoft-desktop-optimization-pack/agpm)

    - [Windows 관리 센터](/windows-server/manage/windows-admin-center/overview)

3. 앱에 대한 액세스 권한을 Microsoft Defender 보안 센터. (도움이 필요하세요? [RBAC를 사용하여 포털 액세스 관리를 참조합니다.](rbac.md)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>장치 프록시 및 인터넷 연결 설정 구성

장치와 끝점용 Defender 간의 통신을 사용하도록 설정하려면 프록시 및 인터넷 설정을 구성합니다. 다음 표에는 다양한 운영 체제 및 기능에 대한 프록시 및 인터넷 설정을 구성하는 데 사용할 수 있는 리소스에 대한 링크가 포함되어 있습니다.

|기능  | 운영 체제 | 리소스 |
|--|--|--|
| [끝점 검색 및](overview-endpoint-detection-response.md) 응답(EDR) | [Windows 10](/windows/release-health/release-information) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows 서버 1803 이상](/windows-server/get-started/whats-new-in-windows-server-1803)  | [컴퓨터 프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md) |
|EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) | [프록시 및 인터넷 연결 설정 구성](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <p>11.3.1(Big Sur)<p>10.15(카탈로나)<p>10.14(모잡)  | [MacOS의 끝점용 Defender: 네트워크 연결](microsoft-defender-endpoint-mac.md#network-connections) |
|[Windows Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md) | [Windows 10](/windows/release-health/release-information) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows 서버 1803 이상](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사](configure-network-connections-microsoft-defender-antivirus.md) |
|바이러스 검사 |macOS: <p>11.3.1(Big Sur)<p>10.15(카탈로나)<p>10.14(모잡) |[MacOS의 끝점용 Defender: 네트워크 연결](microsoft-defender-endpoint-mac.md#network-connections) |
|바이러스 검사 |Linux: <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS 이상<p>SLES 12+<p>데비안 9+<p>Oracle Linux 7.2 |[Linux의 끝점용 Defender: 네트워크 연결](microsoft-defender-endpoint-linux.md#network-connections) 

## <a name="next-step"></a>다음 단계

**축하합니다!** [McAfee에서 끝점용 Defender로](mcafee-to-microsoft-defender-migration.md#the-migration-process)마이그레이션하는 준비 단계를 완료했습니다! 

- [끝점에 대한 Defender 설정으로 진행합니다.](mcafee-to-microsoft-defender-setup.md)
