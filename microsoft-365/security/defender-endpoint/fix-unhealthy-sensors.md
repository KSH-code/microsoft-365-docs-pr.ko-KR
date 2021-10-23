---
title: Endpoint용 Microsoft Defender에서 불안정한 센서 수정
description: 서비스가 장치에서 데이터를 수신할 수 있도록 잘못 구성되거나 비활성으로 보고되는 장치 센서를 수정합니다.
keywords: 잘못 구성, 비활성, 센서 수정, 센서 상태, 센서 데이터 없음, 센서 데이터, 통신 장애, 통신
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: a01fa71e8d52a9e6de522483ee982458f04141af
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555287"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Endpoint용 Microsoft Defender에서 불안정한 센서 수정

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-fixsensor-abovefoldlink)

잘못 구성되거나 비활성으로 분류된 장치는 다양한 원인으로 인해 플래그가 지정될 수 있습니다. 이 섹션에서는 장치가 비활성 또는 잘못 구성된 것으로 분류될 수 있는 원인에 대한 몇 가지 설명을 제공합니다.

## <a name="inactive-devices"></a>비활성 장치

비활성 장치는 문제로 인해 플래그가 지정되지 않을 수 있습니다. 장치에서 수행한 다음 작업을 수행하면 장치가 비활성으로 분류될 수 있습니다.

### <a name="device-is-not-in-use"></a>디바이스가 사용되지 않습니다.

어떤 이유로든 장치를 7일 이상 사용하지 않은 경우 포털에서 '비활성' 상태로 유지됩니다.

### <a name="device-was-reinstalled-or-renamed"></a>장치가 다시 설치되거나 이름을 변경했습니다.
다시 설치되거나 이름을 변경하면 디바이스에서 새 장치 엔터티가 Microsoft Defender 보안 센터. 이전 장치 엔터티는 포털에서 '비활성' 상태로 유지됩니다. 장치를 다시 설치하고 Endpoint용 Defender 패키지를 배포한 경우 새 장치 이름을 검색하여 장치가 정상적으로 보고하고 있는지 확인합니다.

### <a name="device-was-offboarded"></a>디바이스가 오프보더된 경우
장치가 오프보더된 경우 장치 목록에 계속 표시됩니다. 7일이 지난 후 장치 상태는 비활성으로 변경됩니다.

### <a name="device-is-not-sending-signals"></a>장치가 신호를 보내지 않습니다.
장치가 잘못된 구성 장치 분류에 속하는 조건을 포함하여 어떤 이유로든 끝점 채널에 대한 Microsoft Defender에 7일 넘게 신호를 보내지 않는 경우 비활성으로 간주될 수 있습니다. 

장치가 '활성' 상태일 것으로 예상하나요? [지원 티켓 을 열 수 있습니다.](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)

## <a name="misconfigured-devices"></a>잘못 구성된 장치
잘못 구성된 장치는 다음으로 더 분류될 수 있습니다.
- 통신 장애
- 센서 데이터 없음

### <a name="impaired-communications"></a>통신 장애
이 상태는 장치와 서비스 간에 통신이 제한되어 있습니다.

다음 제안된 작업은 통신 장애가 있는 잘못 구성된 장치와 관련된 문제를 해결하는 데 도움이 될 수 있습니다.

- [디바이스가 인터넷에 연결되어 있는지 확인](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  엔드포인트용 Microsoft Defender 센서를 사용하려면 센서 데이터를 보고하고 엔드포인트용 Microsoft Defender 서비스와 통신하기 위해 WinHTTP(Microsoft Windows HTTP)가 필요합니다.

- [끝점 서비스 URL용 Microsoft Defender에 대한 클라이언트 연결 확인](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  프록시 구성이 성공적으로 완료되어 WinHTTP가 사용자 환경의 프록시 서버를 검색하고 통신할 수 있는지, 프록시 서버에서 끝점 서비스 URL에 대한 Microsoft Defender에 대한 트래픽을 허용하는지 확인

수정 작업을 수행한 경우 장치 상태가 여전히 잘못 구성된 경우 지원 [티켓 을 를 열 수 있습니다.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

### <a name="no-sensor-data"></a>센서 데이터 없음
'센서 데이터 없음' 상태의 잘못 구성된 장치는 서비스와 통신하지만 부분 센서 데이터만 보고할 수 있습니다.
다음 작업을 수행하여 '센서 데이터 없음' 상태의 잘못 구성된 장치와 관련된 알려진 문제를 해결합니다.

- [디바이스가 인터넷에 연결되어 있는지 확인](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  엔드포인트용 Microsoft Defender 센서를 사용하려면 센서 데이터를 보고하고 엔드포인트용 Microsoft Defender 서비스와 통신하기 위해 WinHTTP(Microsoft Windows HTTP)가 필요합니다.

- [끝점 서비스 URL용 Microsoft Defender에 대한 클라이언트 연결 확인](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  프록시 구성이 성공적으로 완료되어 WinHTTP가 사용자 환경의 프록시 서버를 검색하고 통신할 수 있는지, 프록시 서버에서 끝점 서비스 URL에 대한 Microsoft Defender에 대한 트래픽을 허용하는지 확인

- [진단 데이터 서비스를 사용하도록 설정되어 있는지 확인](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
장치가 올바르게 보고되지 않는 경우 Windows 진단 데이터 서비스가 자동으로 시작되고 끝점에서 실행 중인지 확인해야 할 수 있습니다.

- [정책에 Microsoft Defender 바이러스 백신 사용하지 않도록 설정되어 있지 않은지 확인](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
장치에서 타사 맬웨어 방지 클라이언트를 실행하는 경우 끝점용 Defender 에이전트는 ELAM(Microsoft Defender 바이러스 백신 맬웨어 방지 조기 실행) 드라이버를 사용하도록 설정해야 합니다.

수정 작업을 수행한 경우 장치 상태가 여전히 잘못 구성된 경우 지원 [티켓 을 를 열 수 있습니다.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

## <a name="see-also"></a>참고 항목
- [끝점에 대한 Microsoft Defender의 센서 상태 확인](check-sensor-status.md)
- [클라이언트 분석기 개요](overview-client-analyzer.md)
- [클라이언트 분석기 다운로드 및 실행](download-client-analyzer.md)
- [Windows에서 클라이언트 분석기 실행](run-analyzer-windows.md)
- [macOS 또는 Linux에서 클라이언트 분석기 실행](run-analyzer-macos-linux.md)
- [Windows에서 고급 문제 해결을 위한 데이터 수집](data-collection-analyzer.md)

