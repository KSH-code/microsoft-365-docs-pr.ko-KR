---
title: Microsoft Defender for Endpoint에서 Windows 버전의 온보딩
description: 센서 데이터를 끝점용 Microsoft Defender 센서로 보낼 수 있도록 Windows 지원되는 이전 버전의 장치 온보딩
keywords: 온보드, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.openlocfilehash: dcfbef4e728a3b29a2d23f55d5bd96aeffd19b00
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206832"
---
# <a name="onboard-previous-versions-of-windows"></a>이전 버전의 Windows 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**플랫폼**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)

Endpoint용 Defender는 지원되는 운영 체제 버전에 고급 공격 감지 및 조사 기능을 제공함으로써 지원되는 운영 체제를 포함하기 Windows 확장합니다.

클라이언트 끝점의 Windows 끝점을 Defender에 온보딩하려면 다음을 해야 합니다.

- 클라이언트를 구성하고 System Center Endpoint Protection 업데이트합니다.
- 아래에 설명된 Microsoft Monitoring Agent 끝점용 Defender에 센서 데이터를 보고하도록 MMA(관리자)를 설치하고 구성합니다.

> [!TIP]
> 장치를 온보드한 후 검색 테스트를 실행하여 서비스에 올바르게 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 Endpoint 끝점에 대한 검색 테스트 [실행을 참조하세요.](run-detection-test.md)

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>클라이언트 구성 및 System Center Endpoint Protection 업데이트

> [!IMPORTANT]
> 이 단계는 조직에서 SCEP(ScEP)를 사용하는 System Center Endpoint Protection 필요합니다.

Endpoint용 Defender는 System Center Endpoint Protection 맬웨어 감지에 대한 가시성을 제공하고 잠재적으로 악성 파일이나 의심되는 맬웨어를 금지하여 조직의 공격 전파를 중지하기 위해 통합되었습니다.

이 통합을 사용하려면 다음 단계가 필요합니다.

- 클라이언트용 맬웨어 방지 플랫폼 [2017년 1월 Endpoint Protection 업데이트 설치](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)
- 고급 설정으로 SCEP 클라이언트 클라우드 보호 서비스 멤버 자격 **구성**
- 클라우드에 대한 연결을 허용하도록 Microsoft Defender 바이러스 백신 구성합니다. 자세한 내용은 클라우드에 대한 연결 [Microsoft Defender 바이러스 백신 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>MMA(Microsoft Monitoring Agent)를 설치 및 구성하여 끝점용 Microsoft Defender에 센서 데이터 보고

### <a name="before-you-begin"></a>시작하기 전에

다음 세부 정보를 검토하여 최소 시스템 요구 사항을 확인합니다.

- [2018년 2월 월별 업데이트 롤업 설치](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > Windows 7 SP1 Enterprise 및 Windows 7 SP1 Pro.

- 고객 환경 및 진단 원격 [분석에](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) 대한 업데이트 설치

- [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) 이상 또는 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) 설치

    > [!NOTE]
    > Windows 7 SP1 Enterprise 및 Windows 7 SP1 Pro.
    > 4.0.x는 위의 .NET Framework 아니기 때문에 설치하지 않습니다.

- Azure Log Analytics 에이전트 최소 시스템 요구 사항을 충족합니다. 자세한 내용은 Log Analytics를 사용하여 환경의 컴퓨터에서 데이터 [수집을 참조하세요.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)

1. [64비트](https://go.microsoft.com/fwlink/?LinkId=828603) 에이전트 또는 Windows [32비트](https://go.microsoft.com/fwlink/?LinkId=828604)Windows 설치 파일을 다운로드합니다.

2. 작업 영역 ID를 구합니다.
   - 끝점용 Defender 탐색 창에서 온보딩을 설정 > 끝점 > **끝점을 > 선택합니다.**
   - 운영 **Windows 7 SP1 및 8.1을** 선택합니다.
   - 작업 영역 ID 및 작업 영역 키 복사

3. 작업 영역 ID 및 작업 영역 키를 사용하여 다음 설치 방법 중 원하는 경우 에이전트를 설치합니다.
    - [설치 프로그램을 사용하여 에이전트를 수동으로 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)

      에이전트 설정 **옵션 페이지에서** 에이전트를 **커넥트 OMS(Azure Log Analytics)를 선택합니다.**

    - [명령줄을 사용하여 에이전트를 설치합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)
    - [스크립트를 사용하여 에이전트를 구성합니다.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

   > [!NOTE]
   > 미국 정부 [](gov.md)고객인 경우 "Azure Cloud"에서 설치 마법사를 사용하는 경우 또는 명령줄 또는 스크립트를 사용하는 경우 "azure US Government"를 선택해야 합니다. "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 매개 변수를 1로 설정해야 합니다.

4. 프록시를 사용하여 인터넷에 연결하는 경우 프록시 설정 구성 섹션을 참조하세요.

완료되면 1시간 이내에 포털에 온보드 엔드포인트가 표시될 것입니다.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>프록시 및 인터넷 연결 설정 구성

- 각 Windows 끝점은 HTTPS를 사용하여 인터넷에 연결할 수 있어야 합니다. 이 연결은 프록시를 사용하여 직접 연결하거나 [OMS 게이트웨이를 통해](/azure/log-analytics/log-analytics-oms-gateway)할 수 있습니다.
- 프록시 또는 방화벽이 기본적으로 모든 트래픽을 차단하고 특정 도메인만 허용하거나 SSL 검사(SSL 검사)를 통해 허용하는 경우 끝점 서비스 URL용 [Defender에](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)대한 액세스를 사용하도록 설정해야 합니다.

## <a name="run-a-detection-test-to-verify-onboarding"></a>검색 테스트를 실행하여 온보더링 확인

장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)

## <a name="offboard-client-endpoints"></a>오프보드 클라이언트 끝점

오프보딩을 위해 끝점에서 MMA 에이전트를 제거하거나 끝점 작업 영역용 Defender에 보고에서 이 에이전트를 제거하면 됩니다. 에이전트를 오프보딩한 후 끝점은 더 이상 끝점용 Defender에 센서 데이터를 전송하지 않습니다.

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevele-belowfoldlink)
