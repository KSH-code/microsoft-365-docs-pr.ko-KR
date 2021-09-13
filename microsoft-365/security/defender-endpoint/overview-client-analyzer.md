---
title: Endpoint Client Analyzer용 Microsoft Defender를 사용하여 센서 상태 문제 해결
description: 장치의 센서 상태 문제를 해결하여 센서 데이터 또는 기능에 영향을 주는 잠재적인 구성, 환경, 연결 또는 원격 분석 문제를 식별합니다.
keywords: 센서, 센서 상태, 잘못 구성된, 비활성, 센서 데이터 없음, 센서 데이터, 통신 장애, 통신
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 604a7d98b25d7b5b858db87c8b8f467ffb8edb83
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192662"
---
#  <a name="troubleshoot-sensor-health-using-microsoft-defender-for-endpoint-client-analyzer"></a>Endpoint Client Analyzer용 Microsoft Defender를 사용하여 센서 상태 문제 해결

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)

MDECA(Microsoft Defender for Endpoint Client Analyzer)는 Windows, Linux 또는 macOS를 실행하는 온보딩 장치에서 센서 상태 또는 안정성 문제를 감지할 때 유용할 수 있습니다. [](/microsoft-365/security/defender-endpoint/onboard-configure) 예를 들어 보안 포털에 표시된 센서 상태(비활성, 센서 데이터 없음 또는 [](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors) 통신 장애)에 따라 상태가 상태가 불안정한 것으로 표시되는 컴퓨터의 분석기를 실행할 수 있습니다.

MDECA는 명확한 센서 상태 문제 외에도 다음과 같은 복잡한 시나리오 문제를 해결하기 위해 다른 추적, 로그 및 진단 정보를 수집할 수 있습니다.  
응용 프로그램 호환성(AppCompat), 성능, 네트워크 연결 또는 [끝점](/microsoft-365/compliance/endpoint-dlp-learn-about)데이터 손실 방지와 관련된 예기치 않은 동작

## <a name="privacy-notice"></a>개인 정보 알림


-   Endpoint용 Microsoft Defender 클라이언트 분석기 도구는 Microsoft CSS(고객 지원 서비스)에서 정기적으로 사용하여 끝점용 Microsoft Defender에서 발생하는 문제를 해결하는 데 도움이 되는 정보를 수집합니다.

-   수집된 데이터에는 IP 주소, PC 이름 및 사용자 이름과 같은 PII(개인 식별 정보) 및/또는 중요한 데이터가 포함될 수 있습니다(이에 국한되지는 않습니다).

-   데이터 수집이 완료되면 도구는 데이터를 컴퓨터의 하위 폴더 및 압축된 zip 파일 내에 로컬로 저장합니다.

-   데이터가 자동으로 Microsoft로 전송되지 않습니다. 지원 문제를 공동으로 작업하는 동안 이 도구를 사용하는 경우 보안 파일 도구를 사용하여 Microsoft CSS로 압축된 데이터를 보내 Exchange 수 있습니다.

보안 파일 관리에 Exchange Microsoft 지원 서비스에서 보안 파일 파일을 Exchange 방법을 [참조하세요.](/troubleshoot/azure/general/secure-file-exchange-transfer-files)  

개인 정보 취급 방침에 대한 자세한 내용은 Microsoft 개인 정보 [취급 방침을 참조하세요.](https://privacy.microsoft.com/privacystatement)

## <a name="requirements"></a>요구 사항

-   분석기를 실행하기 전에 프록시 또는 방화벽 구성에서 끝점 서비스 [URL용 Microsoft Defender에](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)액세스할 수 있도록 하는 것이 좋습니다.

-   분석기는 Endpoint용 Microsoft Defender에 [온보딩하기 Windows](minimum-requirements.md#supported-windows-versions)이전의 지원되는 Windows 버전에서 실행할 수 있습니다. [](microsoft-defender-endpoint-linux.md#system-requirements) [](microsoft-defender-endpoint-mac.md#system-requirements)

-   Windows 장치의 경우 원격으로 라이브 응답을 통해가 아니라 특정 장치에서 [](/microsoft-365/security/defender-endpoint/troubleshoot-collect-support-log)직접 분석기를 실행하는 경우 SysInternals [](/sysinternals/downloads/psexec)PsExec.exe(적어도 일시적으로)를 실행할 수 있습니다.  
    분석기는 로컬 시스템으로 PsExec.exe 클라우드 연결 검사를 실행하고 SENSE 서비스의 동작을 에뮬레이터로 호출합니다.

    > [!NOTE]
    > Windows 장치에서 [PSExec](attack-surface-reduction-rules.md#block-process-creations-originating-from-psexec-and-wmi-commands)및 WMI 명령에서 시작된 ASR(공격 표면 축소) 규칙 프로세스 만들기 차단을 사용하는 경우 일시적으로 규칙을 사용하지 않도록 설정하거나 분석기가 예상대로 클라우드에 대한 연결 검사를 실행할 수 있도록 [ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 규칙에 대한 제외를 구성할 수 있습니다.
