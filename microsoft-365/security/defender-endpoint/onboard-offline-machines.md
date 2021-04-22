---
title: 끝점용 Microsoft Defender에 인터넷 액세스 없이 장치 온보딩
ms.reviewer: ''
description: 끝점용 Microsoft Defender 센서로 센서 데이터를 보낼 수 있도록 인터넷에 연결하지 않고 장치 온보딩
keywords: 온보드, 서버, vm, 온-프레미스, oms 게이트웨이, 로그 분석, Azure 로그 분석, mma
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee06f927579445825a2b2813e483c24357d2ed78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934924"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에 인터넷 액세스 없이 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


인터넷에 연결하지 않고 장치를 온보드하려면 다음과 같은 일반적인 단계를 따라야 합니다.

> [!IMPORTANT] 
> 아래 단계는 Windows Server 2016 이하 또는 Windows 8.1 이하와 같은 이전 버전의 Windows를 실행하는 디바이스에만 적용할 수 있습니다.

> [!NOTE]
> - 'TelemetryProxyServer' 레지스트리 또는 GPO를 통해 구성된 경우 연결이 끊어진 Windows 10 또는 Windows Server 2019 장치의 프록시로 OMS 게이트웨이 서버를 사용할 수 없습니다.
> - Windows 10 또는 Windows Server 2019의 경우 - TelemetryProxyServer를 사용할 수 있는 동안 표준 프록시 장치 또는 어플라이언스를 설정해야 합니다.
> - 또한 연결이 끊어진 환경의 Windows 10 또는 Windows Server 2019는 내부 파일 또는 웹 서버를 통해 오프라인으로 인증서 신뢰 목록을 업데이트할 수 있어야 합니다.
> - 오프라인으로 CTL을 업데이트하는 데 대한 자세한 내용은 CTL 파일을 다운로드하도록 파일 또는 웹 서버 [구성을 참조하세요.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)

온보더링 방법에 대한 자세한 내용은 다음 문서를 참조하세요.
- [이전 버전의 Windows 온보딩](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [끝점용 Microsoft Defender 서비스에 서버 온보딩](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [장치 프록시 및 인터넷 연결 설정 구성](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>사내 장치

- 프록시 또는 허브 역할을 하게 Azure Log Analytics(이전의 OMS 게이트웨이)를 설치합니다.
  - [Azure Log Analytics 에이전트](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [끝점 작업 영역용 Defender를 위한 MMA(Microsoft](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) 모니터링 에이전트) 지점 설치 및 & ID

- Azure Log Analytics의 동일한 네트워크에서 오프라인 장치
  -  MMA를 구성하여:
     - 프록시로 Azure Log Analytics IP
     - Endpoint 작업 영역용 Defender & ID

## <a name="azure-virtual-machines"></a>Azure 가상 컴퓨터
- [Azure Log Analytics 작업](https://docs.microsoft.com/azure/azure-monitor/platform/gateway) 영역 구성 및 사용

    - 프록시 또는 허브 역할을 하게 Azure Log Analytics Gateway(이전의 OMS 게이트웨이)를 설치합니다.
      - [Azure Log Analytics 게이트웨이](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [끝점 작업 영역용 Defender를 위한 MMA(Microsoft](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) 모니터링 에이전트) 지점 설치 및 & ID
    - 동일한 OMS 게이트웨이 네트워크의 오프라인 Azure VM
      - Azure Log Analytics IP를 프록시로 구성
      - Azure Log Analytics 작업 영역 키 & ID

    - Azure Defender
      - [보안 정책 \> 로그 분석 작업 영역](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [위협 감지 끝점에서 내 데이터에 액세스할 수 있도록 \> 허용](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        자세한 내용은 보안 정책 [작업을 참조하세요.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)
