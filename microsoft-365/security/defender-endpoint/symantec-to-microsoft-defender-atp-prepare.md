---
title: Symantec에서 끝점용 Microsoft Defender로 - 1단계, 준비
description: 이것은 Symantec에서 끝점용 Microsoft Defender로 마이그레이션하는 1단계, 준비입니다.
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: bba48803863cd330b371c24600239462b1ca9250
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327417"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Symantec에서 마이그레이션 - 1단계: 마이그레이션 준비

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![1 단계: 준비](images/phase-diagrams/prepare.png)<br/>1 단계: 준비 |[![2 단계: 설정](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[2 단계: 설정](symantec-to-microsoft-defender-atp-setup.md) |[![3 단계: 온보딩](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[3 단계: 온보딩](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*여기 있습니다!*| | |


**[Symantec에서 끝점용 Microsoft Defender로 마이그레이션하는 준비 단계에 오신 것을 환영합니다.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** 

이 마이그레이션 단계에는 다음 단계가 포함됩니다.
1. [끝점용 Microsoft Defender를 다운로드합니다.](#get-microsoft-defender-for-endpoint)
2. [에 대한 액세스 권한을 Microsoft Defender 보안 센터.](#grant-access-to-the-microsoft-defender-security-center)
3. [장치 프록시 및 인터넷 연결 설정을 구성합니다.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender 다운로드

시작하려면 라이선스가 할당 및 프로비전된 Microsoft Defender for Endpoint가 있어야 합니다.

1. 지금 끝점용 Microsoft Defender를 구입하거나 사용해 볼 수 있습니다. [Microsoft Defender for Endpoint를](https://aka.ms/mdatp)방문하여 무료 평가판을 시작하거나 견적을 요청합니다. 
2. 라이선스가 올바르게 프로비전되었는지 확인합니다. [라이선스 상태를 확인 합니다.](production-deployment.md#check-license-state)
3. 전역 관리자 또는 보안 관리자는 끝점용 Microsoft Defender의 전용 클라우드 인스턴스를 설정합니다. 끝점 설정: 테넌트 구성에 대한 [Microsoft Defender를 참조합니다.](production-deployment.md#tenant-configuration)
4. 조직의 끝점(예: 장치)이 프록시를 사용하여 인터넷에 액세스하는 경우 [끝점용 Microsoft Defender 설치: 네트워크 구성을 참조합니다.](production-deployment.md#network-configuration)
 
이제 Microsoft Defender 보안 센터()를 사용할 보안 관리자 및 보안 운영자에 대한 액세스 권한을 부여할 준비가 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 보안 센터. 

> [!NOTE]
> 이 Microsoft Defender 보안 센터 Microsoft Defender for Endpoint 포털이라고도 합니다. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>사용자 액세스 권한 Microsoft Defender 보안 센터

Microsoft Defender 보안 센터 ()는 끝점용 Microsoft Defender의 기능에 액세스하고 기능을 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 구성하는 위치입니다. 자세한 내용은 의 [개요를 Microsoft Defender 보안 센터.](use.md)

기본 사용 Microsoft Defender 보안 센터 RBAC(역할 기반 액세스 제어)를 사용하여 사용 권한을 부여할 수 있습니다. 사용 권한을 보다 세밀하게 제어할 수 있도록 RBAC를 사용하는 것이 좋습니다.

1. 보안 관리자 및 보안 운영자에 대한 역할 및 사용 권한을 계획합니다. 역할 [기반 액세스 제어를 참조합니다.](prepare-deployment.md#role-based-access-control)
2. RBAC를 설정하고 구성합니다. [Intune을](/mem/intune/fundamentals/what-is-intune) 사용하여 RBAC를 구성하는 것이 좋습니다. 특히 조직에서 Windows 10, macOS, iOS 및 Android 장치의 조합을 사용하는 경우입니다. [Intune을 사용하여 RBAC 설정을 참조합니다.](/mem/intune/fundamentals/role-based-access-control)<br/>
   조직에서 Intune 외의 방법이 필요한 경우 다음 옵션 중 하나를 선택합니다.
    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [고급 그룹 정책 관리](/microsoft-desktop-optimization-pack/agpm)
    - [Windows 관리 센터](/windows-server/manage/windows-admin-center/overview)
3. 앱에 대한 액세스 권한을 Microsoft Defender 보안 센터. (도움이 필요하세요? [RBAC를 사용하여 포털 액세스 관리를 참조합니다.](rbac.md)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>장치 프록시 및 인터넷 연결 설정 구성

장치와 끝점용 Microsoft Defender 간의 통신을 사용하도록 설정하려면 프록시 및 인터넷 설정을 구성합니다. 다음 표에는 다양한 운영 체제 및 기능에 대한 프록시 및 인터넷 설정을 구성하는 데 사용할 수 있는 리소스에 대한 링크가 포함되어 있습니다.

|기능  | 운영 체제 | 리소스 |
|:----|:----|:---|
|[끝점 검색 및](overview-endpoint-detection-response.md) 응답(EDR) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows 서버 1803 이상](/windows-server/get-started/whats-new-in-windows-server-1803)  |[컴퓨터 프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[프록시 및 인터넷 연결 설정 구성](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15(카탈로나)<br/>- 10.14(Mojave) <br/>- 10.13(High Sierra)  |[MacOS의 끝점용 Microsoft Defender: 네트워크 연결](microsoft-defender-endpoint-mac.md#network-connections) |
|[Windows Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows 서버 1803 이상](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|바이러스 검사 |macOS: <br/>- 11.3.1(Big Sur)<br/>- 10.15(카탈로나)<br/>- 10.14(Mojave)  |[Mac의 끝점용 Microsoft Defender: 네트워크 연결](microsoft-defender-endpoint-mac.md#network-connections) |
|바이러스 검사 |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 이상<br/>- SLES 12+<br/>- 데비안 9+<br/>- Oracle Linux 7.2 |[Linux의 끝점용 Microsoft Defender: 네트워크 연결](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>다음 단계

**축하합니다!** [Symantec에서 끝점용 Microsoft Defender로 마이그레이션하는](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)준비 단계를 완료했습니다. 
- [끝점에 대한 Microsoft Defender 설정으로 진행합니다.](symantec-to-microsoft-defender-atp-setup.md)
