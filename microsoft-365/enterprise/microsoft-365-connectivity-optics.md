---
title: Microsoft 365 연결 광학
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 이 문서에는 연결 광학에 대한 Microsoft 365 포함되어 있습니다.
ms.openlocfilehash: c1ee14966f13ff50ff809ebbdf4c578bf949e956
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150548"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365 연결 광학

이 문서에서는 Microsoft가 일반적으로 고객 장치에서 수집하는 일부 연결 광학에 대해 설명하고 Microsoft가 이러한 데이터를 사용하여 서비스 제공을 분석 및 최적화하고 가능한 최상의 최종 사용자 환경을 평가하고 보장하는 몇 가지 방법에 대해 설명하고 있습니다.

연결 광학은 일반적으로 최종 사용자 장치에 설치되거나 브라우저에서 액세스할 수 있는 Microsoft 응용 프로그램에서 수집됩니다. Microsoft 365 서비스 내의 선택적 데이터 수집과 달리 여기에 설명된 많은 연결 광학은 Microsoft가 고객에게 대한 가용성 및 성능 약정을 충족하는 데 필수입니다. 이러한 광학 기능을 통해 Microsoft는 최종 사용자와 Microsoft 서비스 끝점 간의 연결 경로에서 문제를 빠르게 감지하고 대응할 수 있습니다. 이러한 광학 중 일부는 Microsoft 365 관리 센터에서 네트워크 연결과 [같은 기능을 사용하도록 설정하는 데도 사용됩니다.](office-365-network-mac-perf-overview.md)

## <a name="optics-collected-from-microsoft-365-applications"></a>Microsoft 365 응용 프로그램에서 수집된 광학

광학은 현재 모든 디바이스에서 불연수 샘플링을 사용하여 수집됩니다. 일반적으로 특정 기록에서 측정할 특정 광학 및 대상(서비스 끝점)은 Microsoft에서 서비스 요구 사항을 기반으로 구성하고 샘플링을 위해 임의로 지정합니다.
각 광학 수집 간격에서 최종 사용자 장치를 측정 원본으로 사용하고 Microsoft 365 서비스 끝점을 측정 대상으로 사용하여 다음 측정 중 하나 이상을 수집할 수 있습니다.

| 측정 | 설명 |
| --- | --- |
| 대기 시간 | HTTP를 통해 작은 파일을 검색하는 데 경과된 시간 |
| 처리량 | HTTP를 통해 더 큰 파일을 검색하는 데 시간이 많이 소비되고 대역폭이 과도하게 소비되지 않도록 측정된 경우는 거의 없습니다. |
| RTT(왕복 시간) | ICMP ping |
| Traceroute | ICMP 추적 |

각 측정은 일반적으로 다음 항목을 포함할 수 있는 추가 정보와 연결됩니다.

| 항목 | 설명 |
| --- | --- |
| 테넌트 ID | 최종 사용자 장치와 연결된 고객의 Azure Active Directory 테넌트의 고유 식별자입니다. |
| 모니터 ID | 측정을 수행하는 클라이언트 응용 프로그램에서 제공하는 요청(예: Outlook, OneDrive 등)을 생성하는 응용 프로그램의 식별자입니다. |
| 요청 ID | Microsoft에서 제공하는 측정 구성에 지정된 측정 요청의 식별자입니다. |
| 원격 IP | 측정 요청을 수신하고 Microsoft에 표시되는 클라이언트 원본 IP 주소를 기반으로 계산된 서버에서 제공한 클라이언트에서 서비스 끝점으로의 요청과 연결된 마스킹된 원본 IP입니다. IP 주소는 IPv4 주소의 경우 /24 서브넷으로 마스킹되거나 IPv6 주소의 경우 /48 서브넷으로 마스킹됩니다. 따라서 Microsoft에서 개별 장치나 사용자를 식별할 수 없습니다. |
| 프런트 엔드 | Microsoft 365 요청을 받은 서버에서 제공하는 서비스 프런트 엔드 식별자입니다. |
| 끝점 | Microsoft 365 받은 서버에서 제공하는 서비스 끝점 위치입니다. |
| 발급한 인증서 | 서비스 끝점에 연결하는 동안 제공된 SSL 인증서의 "발급된 인증서" 속성입니다. 이는 서비스 끝점에 인증서를 발급한 인증 기관을 나타냅니다. |
| 인증서 지문 | 인증서의 공개적으로 액세스할 수 있는 고유 식별자인 서비스 끝점에 연결하는 동안 제공된 SSL 인증서의 "인증서 지문" 속성입니다. |
| 위도/위도 | 최종 사용자 장치의 추상화 위도 및 위도입니다. 이 정보는 최종 사용자 장치에서 Windows 위치 서비스를 사용하도록 설정하고 Microsoft 365 관리 포털에서 이 정보의 컬렉션을 사용하도록 설정한 [테넌트에 한해 수집됩니다.](office-365-network-mac-perf-overview.md#1-enable-windows-location-services) |

## <a name="measurement-process"></a>측정 프로세스

각 최종 사용자 장치는 일반적으로 일정에 따라(설치된 응용 프로그램의 경우) 또는 브라우저 페이지 로드 작업(웹 기반 응용 프로그램용)에 따라 측정을 수행하게 됩니다. 측정 활동은 백그라운드 작업으로 수행하며 사용자의 응용 프로그램 환경에는 영향을 주지 않습니다. 이 프로세스의 특정 실행에 사용되는 측정 유형 및 대상이 임의로 설정될 때 고객은 일반 응용 프로그램 연결을 위해 최종 사용자 장치에서 수행한 일반적인 요청과 유사한 해당 지역의 Microsoft 서비스 끝점에 대한 요청을 알 수 있습니다. 또한 고객은 현지 지역 외부에 있는 Microsoft 서비스 끝점에 대한 요청을 알 수 있습니다. 이러한 측정값은 고객 및 ISP 인프라의 변경으로 Microsoft에서 요청 라우팅 정책을 지속적인 기준으로 변경해야 할 수 있습니다. Microsoft에서 트래픽을 최상의 서비스 끝점으로 라우팅하는 방법 및 Microsoft 365 네트워킹 연결 개요에서 Microsoft 365 서비스에 대한 연결을 최적화하는 Microsoft 365 [대해 자세히 알아보습니다.](microsoft-365-networking-overview.md)

## <a name="service-endpoints"></a>서비스 끝점

이러한 측정의 대상으로 사용되는 Microsoft 서비스 끝점은 게시된 OFFICE 365 URL 및 IP 주소 [범위에 포함되어 있습니다.](urls-and-ip-address-ranges.md) 이러한 연결 광학을 수집하는 데는 추가 서비스 끝점에 액세스할 필요가 없습니다.
