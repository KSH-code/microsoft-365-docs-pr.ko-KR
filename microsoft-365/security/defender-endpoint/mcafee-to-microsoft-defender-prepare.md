---
title: McAfee에서 끝점용 Microsoft Defender로의 준비
description: McAfee에서 Microsoft Defender ATP로 마이그레이션하기 위한 준비 1단계입니다.
keywords: 마이그레이션, Windows Defender Advanced Threat Protection, atp, edr
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
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: adc8c1259be1e226bf1c2592090cf6008c976cf8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186632"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>McAfee에서 마이그레이션 - 1단계: 마이그레이션 준비

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![1단계: 준비](images/phase-diagrams/prepare.png)<br/>1단계: 준비 |[![2단계: 설정](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[2단계: 설정](mcafee-to-microsoft-defender-setup.md) |[![3단계: 온보더](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[3단계: 온보더](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*여기 있습니다!*| | |


**[McAfee 끝점 보안(McAfee)에서 끝점용 Microsoft Defender로](mcafee-to-microsoft-defender-migration.md#the-migration-process)** 마이그레이션하는 준비 단계에 오신 것을 환영합니다. 

이 마이그레이션 단계에는 다음 단계가 포함됩니다.
1. [조직 장치에 업데이트 다운로드 및 배포](#get-and-deploy-updates-across-your-organizations-devices)
2. [끝점용 Microsoft Defender를 다운로드합니다.](#get-microsoft-defender-for-endpoint)
3. [Microsoft Defender 보안 센터에 대한 액세스 권한을 부여합니다.](#grant-access-to-the-microsoft-defender-security-center)
4. [장치 프록시 및 인터넷 연결 설정을 구성합니다.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>조직 장치에 업데이트 다운로드 및 배포

조직의 장치 및 끝점을 최신으로 유지하는 것이 가장 좋은 모범 사례입니다. McAfee 끝점 보안(McAfee) 솔루션이 최신 버전이고 조직에 최신 업데이트가 적용된 운영 체제 및 앱도 있는지 확인합니다. 이렇게 하면 나중에 Endpoint 및 Microsoft Defender 바이러스 백신용 Microsoft Defender로 마이그레이션할 때 문제를 방지하는 데 도움이 될 수 있습니다.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>McAfee 솔루션이 최신지 확인

McAfee를 최신으로 유지하고 조직의 장치에 최신 보안 업데이트가 있는지 확인합니다. 도움이 필요하신가요? 다음은 몇 가지 McAfee 리소스입니다.

- [McAfee 엔터프라이즈 제품 설명서: Endpoint Security의 작동 방식](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [McAfee 기술 문서: Windows 보안 센터에서 Windows 10을 실행하면 끝점 보안이 사용하지 않도록 설정되어 있는 경우 간헐적으로 잘못 보고](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [McAfee 기술 문서: Windows 보안 센터 보고서 끝점 보안이 실행 중일 때 끝점 보안이 사용되지 않도록 설정되어 있습니다.](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

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

조직의 장치를 업데이트한 후 다음 단계는 끝점용 Microsoft Defender를 다운로드하고 라이선스를 할당하고 서비스가 프로비전되어 있는지 확인하는 것입니다.

1. 지금 끝점용 Microsoft Defender를 구입하거나 사용해 볼 수 있습니다. [무료 평가판을 시작하거나 견적을 요청합니다.](https://aka.ms/mdatp) 

2. 라이선스가 올바르게 프로비전되었는지 확인합니다. [라이선스 상태를 확인 합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)

3. 전역 관리자 또는 보안 관리자는 끝점용 Microsoft Defender의 전용 클라우드 인스턴스를 설정합니다. 끝점 설정: 테넌트 구성에 대한 [Microsoft Defender를 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration)

4. 조직의 끝점(예: 장치)이 프록시를 사용하여 인터넷에 액세스하는 경우 [끝점용 Microsoft Defender 설치: 네트워크 구성을 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)
 
이제 Microsoft Defender 보안 센터()를 사용할 보안 관리자 및 보안 운영자에게 액세스 권한을 부여할 준비가 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 완료되었습니다. 

> [!NOTE]
> Microsoft Defender 보안 센터를 끝점용 Microsoft Defender 포털이라고도 합니다. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터에 대한 액세스 권한 부여

Microsoft Defender 보안 센터()에서는 끝점용 Microsoft Defender의 기능에 액세스하고 기능을 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 구성할 수 있습니다. 자세한 내용은 Microsoft Defender 보안 센터 [개요를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

Microsoft Defender 보안 센터에 대한 사용 권한은 기본 사용 권한 또는 RBAC(역할 기반 액세스 제어)를 사용하여 부여할 수 있습니다. 사용 권한을 보다 세밀하게 제어할 수 있도록 RBAC를 사용하는 것이 좋습니다.

1. 보안 관리자 및 보안 운영자에 대한 역할 및 사용 권한을 계획합니다. 역할 [기반 액세스 제어를 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control)

2. RBAC를 설정하고 구성합니다. 특히 조직에서 Windows 10, macOS, iOS 및 Android 장치의 조합을 사용하는 경우 [Intune을](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 사용하여 RBAC를 구성하는 것이 좋습니다. [Intune을 사용하여 RBAC 설정을 참조합니다.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)

    조직에서 Intune 외의 방법이 필요한 경우 다음 옵션 중 하나를 선택합니다.
    - [구성 관리자](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [고급 그룹 정책 관리](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. Microsoft Defender 보안 센터에 대한 액세스 권한을 부여합니다. (도움이 필요하세요? [RBAC를 사용하여 포털 액세스 관리를 참조합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>장치 프록시 및 인터넷 연결 설정 구성

장치와 끝점용 Microsoft Defender 간의 통신을 사용하도록 설정하려면 프록시 및 인터넷 설정을 구성합니다. 다음 표에는 다양한 운영 체제 및 기능에 대한 프록시 및 인터넷 설정을 구성하는 데 사용할 수 있는 리소스에 대한 링크가 포함되어 있습니다.

|기능  | 운영 체제 | 리소스 |
|--|--|--|
|[끝점 검색 및](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 응답(EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 이상](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[컴퓨터 프록시 및 인터넷 연결 설정 구성](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[프록시 및 인터넷 연결 설정 구성](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15(카탈로나)<br/>- 10.14(Mojave) <br/>- 10.13(High Sierra)  |[Mac용 끝점용 Microsoft Defender: 네트워크 연결](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender 바이러스 백신](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 이상](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|바이러스 검사 |macOS: <br/>- 10.15(카탈로나)<br/>- 10.14(Mojave) <br/>- 10.13(High Sierra) |[Mac용 끝점용 Microsoft Defender: 네트워크 연결](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|바이러스 검사 |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 이상<br/>- SLES 12+<br/>- 데비안 9+<br/>- Oracle Linux 7.2 |[Linux용 끝점용 Microsoft Defender: 네트워크 연결](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a>다음 단계

**축하합니다!** [McAfee에서 끝점용 Microsoft Defender로 마이그레이션하는](mcafee-to-microsoft-defender-migration.md#the-migration-process)준비 단계를 완료했습니다! 

- [끝점에 대한 Microsoft Defender 설정으로 진행합니다.](mcafee-to-microsoft-defender-setup.md)
