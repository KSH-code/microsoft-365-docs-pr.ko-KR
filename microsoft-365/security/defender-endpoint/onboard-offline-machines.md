---
title: 끝점용 Microsoft Defender에 인터넷 액세스 없이 장치 온보딩
ms.reviewer: ''
description: 끝점용 Microsoft Defender 센서로 센서 데이터를 보낼 수 있도록 인터넷에 연결하지 않고 장치 온보딩
keywords: 온보드, 서버, vm, 온-프레미스, oms 게이트웨이, 로그 분석, Azure 로그 분석, mma
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
ms.openlocfilehash: e490123a06c2384568e4aabe9119936ed618b2c2
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240487"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에 인터넷 액세스 없이 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


인터넷에 연결하지 않고 장치를 온보드하려면 다음과 같은 일반적인 단계를 따라야 합니다.

> [!IMPORTANT] 
> 아래 단계는 이전 버전의 Windows 실행 중인 디바이스에만 적용할 수 있습니다. Windows Server 2016 이하 Windows 8.1.

> [!NOTE]
> - 'TelemetryProxyServer' 레지스트리 또는 GPO를 통해 구성된 경우 연결이 끊어진 Windows 또는 Windows Server 장치에 대한 프록시로 OMS 게이트웨이 서버를 사용할 수 없습니다.
> - Windows Windows 서버 - TelemetryProxyServer를 사용할 수 있는 동안 표준 프록시 장치 또는 어플라이언스를 지점으로 해야 합니다.
> - 또한 연결이 Windows 또는 Windows 서버가 내부 파일 또는 웹 서버를 통해 오프라인으로 인증서 신뢰 목록을 업데이트할 수 있어야 합니다.
> - 오프라인으로 CTL을 업데이트하는 데 대한 자세한 내용은 CTL 파일을 다운로드하도록 파일 또는 웹 서버 [구성을 참조하세요.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)

온보더링 방법에 대한 자세한 내용은 다음 문서를 참조하세요.
- [이전 버전의 Windows 온보딩](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [끝점용 Microsoft Defender 서비스에 서버 온보딩](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [디바이스 프록시 및 인터넷 연결 설정 구성](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premises-devices"></a>On-premises devices

- 프록시 또는 허브 역할을 하게 Azure Log Analytics(이전의 OMS 게이트웨이)를 설치합니다.
  - [Azure Log Analytics 에이전트](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [끝점 작업 영역 Microsoft Monitoring Agent MMA(Defender)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) 지점 설치 및 & ID

[이전 버전의 Windows 온보딩](onboard-downlevel.md)

- Azure Log Analytics의 동일한 네트워크에서 오프라인 장치
  - MMA를 구성하여:
    - 프록시로 Azure Log Analytics IP
    - Endpoint 작업 영역용 Defender & ID

## <a name="azure-virtual-machines"></a>Azure 가상 컴퓨터

- 프록시 또는 허브 역할을 하게 Azure Log Analytics Gateway(이전의 OMS 게이트웨이)를 설치합니다.
    - [Azure Log Analytics 게이트웨이](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - [끝점 작업 영역 Microsoft Monitoring Agent MMA(Defender)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) 지점 설치 및 & ID
- 동일한 OMS 게이트웨이 네트워크의 오프라인 Azure VM
    - Azure Log Analytics IP를 프록시로 구성
    - Azure Log Analytics 작업 영역 키 & ID
- Azure Defender
    - [보안 정책 \> 로그 분석 작업 영역](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
    - [위협 감지 끝점에서 내 데이터에 액세스할 수 있도록 \> 허용](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

    자세한 내용은 보안 정책 [작업을 참조하세요.](/azure/security-center/tutorial-security-policy)
