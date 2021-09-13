---
title: 장치 검색 개요
description: 네트워크에서 관리되지 않는 장치를 찾기 위해 Microsoft 365 Defender 끝점 검색을 활용하는 방법에 대해 자세히 알아보기
keywords: 장치 검색, 검색, 수동, 사전, 네트워크, 표시 여부, 서버, Workstation, 온보드, 관리되지 않는 장치
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4c1d24119ee8f403b168d6b2f2d97b9842f89d9b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222796"
---
# <a name="device-discovery-overview"></a>장치 검색 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


환경을 보호하려면 네트워크에 있는 장치의 인벤토리를 보유해야 합니다. 그러나 네트워크에서 디바이스 매핑은 비용이 많이 들고, 어렵고, 시간이 많이 소요될 수 있습니다.

Microsoft Defender for Endpoint는 추가 어플라이언스 또는 번거로운 프로세스 변경 없이도 회사 네트워크에 연결된 관리되지 않는 장치를 찾는 데 도움이 되는 장치 검색 기능을 제공합니다.

디바이스 검색 기능을 사용하여 다음을 할 수 있습니다.

- **회사 네트워크에 연결된 엔터프라이즈 끝점 검색**

  기본 또는 표준 검색 옵션을 사용하여 아직 끝점용 Microsoft Defender에 온보딩되지 않은 작업, 서버 및 모바일 끝점을 검색할 수 있습니다.

- **검색된 끝점 온보드**

  네트워크에서 관리되지 않는 끝점은 네트워크에 취약성 및 위험을 도입합니다. 서비스를 온보더링하면 서비스에 대한 보안 가시성을 강화할 수 있습니다.

이 기능과 함께, 기존 위협 및 취약성 관리 환경의 일부로 끝점용 Microsoft Defender에 장치를 온보딩하기 위한 새로운 보안 권장을 사용할 수 있습니다.

## <a name="discovery-methods"></a>검색 방법

검색 모드에는 두 가지가 있습니다.

- 기본 검색
- 표준 검색(권장)

> [!IMPORTANT]
> 검색이 기본 모드로 설정됩니다. 설정 페이지를 통해 이 구성을 보존할 수 있습니다. 표준 검색은 이 날짜 전에 설정 페이지를 통해 수정하지 않는 한 2021년 7월 19일부터 모든 고객의 기본 모드가 됩니다.

### <a name="basic-discovery"></a>기본 검색

이 모드에서 끝점은 네트워크에서 수동적으로 이벤트를 수집하고 해당 네트워크에서 장치 정보를 추출합니다. 기본 검색에서는 수동 SenseNDR.exe 이진 파일을 사용하며 네트워크 트래픽은 시작되지 않습니다. 끝점은 단순히 온보더된 장치에서 볼 수 있는 모든 네트워크 트래픽에서 데이터를 추출합니다.

### <a name="standard-discovery"></a>표준 검색

이 모드를 사용하면 끝점에서 네트워크에서 관찰된 디바이스를 적극적으로 프로브하여 수집된 데이터를 강화할 수 있습니다. 이를 통해 신뢰할 수 있고 확실한 장치 인벤토리를 구축할 수 있습니다. 표준 모드는 스마트하고 활성 프로비전을 사용하여 관찰된 장치에 대한 더 많은 정보를 검색하여 기존 장치 정보를 보강합니다.

표준 모드를 사용하도록 설정하면 조직의 네트워크 모니터링 도구에서 검색 센서에 의해 생성된 최소한의 무시할 수 있는 네트워크 활동이 관찰될 수 있습니다.

 이 모드를 사용하도록 설정하지 않는 경우 네트워크에서 관리되지 않는 끝점만 제한적으로 볼 수 있습니다.

표준 검색은 다양한 PowerShell 스크립트를 사용하여 네트워크에서 장치를 능동적으로 프로브합니다. 이러한 PowerShell 스크립트는 Microsoft에 서명되고 다음 위치에서 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` 실행됩니다. . 예를 들면 `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`와 같습니다.

검색 설정을 변경하고 사용자 지정할 수 있습니다. 자세한 내용은 장치 검색 [구성을 참조하세요.](configure-device-discovery.md)

> [!NOTE]
> 검색 엔진은 회사 네트워크에서 수신되는 네트워크 이벤트와 회사 네트워크 외부에서 수신되는 네트워크 이벤트를 구분합니다. 회사 네트워크에 연결되지 않은 장치는 장치 인벤토리에서 검색되거나 나열되지 않습니다.

## <a name="device-inventory"></a>디바이스 인벤토리

검색했지만 아직 끝점용 Microsoft Defender에 의해 온보딩 및 보호되지 않은 장치는 끝점 탭의 장치 인벤토리에 나열됩니다. 이제 다음 값을 사용할 수 있는 온보더링 상태라는 장치 인벤토리 목록에서 새 필터를 사용할 수 있습니다.

- 온보딩: 끝점이 끝점용 Microsoft Defender에 온보딩됩니다.
- 온보딩할 수 있습니다. 끝점이 네트워크에서 검색되었습니다. 운영 체제는 끝점용 Microsoft Defender에서 지원되는 끝점으로 식별했지만 현재는 온보딩되지 않았습니다. 이러한 장치를 온보드하는 것이 좋습니다.
- 지원되지 않습니다. 끝점은 네트워크에서 검색했지만 끝점용 Microsoft Defender에서 지원되지 않습니다.
- 정보 부족: 시스템에서 장치의 지원 여부를 확인할 수 없습니다. 네트워크의 더 많은 장치에서 표준 검색을 사용하도록 설정하면 검색된 특성을 강화할 수 있습니다.

![장치 인벤토리 대시보드의 이미지입니다.](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> 항상 필터를 적용하여 관리되지 않는 장치를 장치 인벤토리 목록에서 제외할 수 있습니다. API 쿼리의 등록 상태 열을 사용하여 관리되지 않는 장치를 필터링할 수도 있습니다.

## <a name="vulnerability-assessment-on-discovered-devices"></a>검색된 장치에 대한 취약점 평가

네트워크에서 검색된 다른 관리되지 않는 장치뿐만 아니라 장치의 취약성 및 위험은 "보안 권장 사항"에 따라 현재 TVM 흐름의 일부로 포털의 엔터티 페이지에 표시됩니다.
"SSH" 관련 보안 권장 사항을 검색하여 관리되지 않는 장치 및 관리되는 장치와 관련된 SSH 취약성을 검색합니다.

![보안 권장 사항 대시보드의 이미지입니다.](images/1156c82ffadd356ce329d1cf551e806c.png)

## <a name="use-advanced-hunting-on-discovered-devices"></a>검색된 장치에서 고급 헌팅 사용

고급 헌팅 쿼리를 사용하여 검색된 디바이스를 볼 수 있습니다.
DeviceInfo 테이블에서 검색된 끝점에 대한 세부 정보 또는 DeviceNetworkInfo 테이블에서 해당 장치에 대한 네트워크 관련 정보를 찾아볼 수 있습니다.

![고급 헌팅 사용의 이미지입니다.](images/f48ba1779eddee9872f167453c24e5c9.png)

장치 검색은 네트워크 데이터 원본으로 끝점용 Microsoft Defender를 네트워크 데이터 원본으로 활용하여 활동을 비보딩된 장치에 특성화합니다. 즉, 온보딩되지 않은 장치와 통신한 끝점용 Microsoft Defender 온보딩 디바이스의 경우 온보딩되지 않은 장치의 활동은 타임라인 및 고급 헌팅 DeviceNetworkEvents 테이블을 통해 볼 수 있습니다.

새 이벤트는 TCP(Transmission Control Protocol) 연결 기반 이벤트로, 현재 DeviceNetworkEvents 스키마에 맞습니다. TCP는 끝점 사용이 가능한 비 Microsoft Defender에서 끝점용 Microsoft Defender 사용 디바이스로 다시 연결합니다. 

다음 작업 유형도 추가되었습니다.

- ConnectionAttempt - TCP 연결(syn)을 설정하려는 시도 
- ConnectionAcknowledged - TCP 연결이 수락되었습니다(syn\ack) 

다음 예제 쿼리를 시도할 수 있습니다.

```text
DeviceNetworkEvents
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"
| take 10
```

## <a name="changed-behavior"></a>변경된 동작

다음 섹션에서는 이 기능을 사용하는 경우 Microsoft Defender for Endpoint 및/또는 Microsoft 365 보안 센터에서 관찰할 변경 내용을 나열합니다.

1. Microsoft Defender에서 끝점으로 온보딩되지 않은 장치는 장치 인벤토리, 고급 헌팅 및 API 쿼리에 표시될 것으로 예상됩니다. 이렇게 하여 쿼리 결과의 크기가 크게 증가할 수 있습니다.
    1. 고급 헌팅의 "DeviceInfo" 및 "DeviceNetworkInfo" 테이블은 이제 검색된 장치를 보유합니다. "OnboardingStatus" 특성을 사용하여 이러한 장치를 필터링할 수 있습니다.
    2. 검색된 장치는 스트리밍 API 쿼리 결과에 표시될 것으로 예상됩니다. 쿼리에서 필터를 사용하여 이러한 장치를 `OnboardingStatus` 필터링할 수 있습니다.
2. 관리되지 않는 장치는 정의된 기준에 따라 기존 장치 그룹에 할당됩니다.
3. 드문 경우지만 표준 검색은 네트워크 모니터 또는 보안 도구에서 경고를 트리거할 수 있습니다. 이러한 이벤트가 재발하지 않도록 피드백을 제공하세요. 특정 대상 또는 전체 서브넷이 Standard 검색에 의해 적극적으로 프로브되는 것을 명시적으로 제외할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [장치 검색 구성](configure-device-discovery.md)
- [장치 검색 FAQ](device-discovery-faq.md)
