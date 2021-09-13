---
title: Microsoft 365 네트워크 연결 평가
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 인터넷 연결을 사용하여 전 세계 고객이 서비스에 연결할 수 있도록 합니다. 서비스가 발전함에 따라 Microsoft 365 인터넷을 사용하여 서비스에 대한 연결을 설정하는 고객을 기반으로 보안, 성능 및 안정성이 향상됩니다.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213895"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Microsoft 365 네트워크 연결 평가

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 인터넷 연결을 사용하여 전 세계 고객이 서비스에 연결할 수 있도록 합니다. 서비스가 발전함에 따라 Microsoft 365 인터넷을 사용하여 서비스에 대한 연결을 설정하는 고객을 기반으로 보안, 성능 및 안정성이 향상됩니다.
  
이 기능을 Microsoft 365 고객은 배포 프로젝트의 일부로 기존 및 예측된 인터넷 연결 요구 사항을 평가해야 합니다. 엔터프라이즈급 배포의 경우 안정적이고 적절한 크기의 인터넷 연결을 사용하는 것이 Microsoft 365 중요한 부분입니다.
  
네트워크 평가는 크기 및 기본 설정에 따라 여러 사용자와 조직에서 수행할 수 있습니다. 평가의 네트워크 범위는 배포 프로세스의 위치도 다를 수 있습니다. 네트워크 평가를 수행하는 데 필요한 작업을 보다 잘 이해할 수 있도록 사용 가능한 옵션을 이해하는 데 도움이 되는 네트워크 평가 가이드를 생성했습니다. 이 평가를 통해 배포 프로젝트에 추가해야 하는 단계 및 리소스를 결정하여 배포 프로젝트를 성공적으로 채택할 수 Microsoft 365.
  
포괄적인 네트워크 평가는 네트워킹 디자인 문제에 대한 가능한 해결 방법과 구현 세부 정보를 제공합니다. 일부 네트워크 평가는 기존 네트워크 및 인터넷 Microsoft 365 구성 또는 디자인 변경 사항을 수용할 수 있는 최적의 네트워크 연결을 보여 주게 됩니다.

일부 평가는 네트워킹 구성 요소에 대한 Microsoft 365 추가 투자가 필요한 네트워크 연결을 나타냅니다. 예를 들어 지사 및 여러 지역에 걸쳐 있는 엔터프라이즈 네트워크에는 SD-WAN 솔루션 또는 최적화된 라우팅 인프라에 대한 투자가 필요할 수 Microsoft 365. 경우에 따라 온라인 미디어 품질과 같은 시나리오에 대한 Microsoft 365 또는 성능 요구 사항에 따라 네트워크에 비즈니스용 Skype [나타냅니다.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) 이러한 추가 요구 사항은 인터넷 연결 인프라, 라우팅 최적화 및 특수한 직접 연결에 대한 투자로 이어질 수 있습니다.

네트워크를 평가하는 데 도움이 되는 몇 가지 리소스:

- 네트워크 [Microsoft 365 대한](microsoft-365-networking-overview.md) 개념 정보는 Microsoft 365 네트워크 연결 개요를 참조하세요.
- 네트워크 [Microsoft 365](./microsoft-365-network-connectivity-principles.md) 원칙을 참조하여 트래픽을 안전하게 관리하고 Microsoft 365 성능을 확보하기 위한 연결 원칙을 이해하세요.
- Microsoft [FastTrack](https://www.microsoft.com/fasttrack) 계획, 디자인 및 배포에 대한 Microsoft 365 지원을 요청하세요. 
- 아래 [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) 연결 테스트 섹션을 참조하여 특정 사용자 위치와 사용자 위치 간에 수행될 수 있는 네트워킹 연결 개선에 대한 특정 지침을 제공하는 기본 연결 테스트를 Microsoft 365.

> [!NOTE]
> Microsoft 인증은 사용자에 대해 ExpressRoute를 사용하려면 Office 365. Microsoft는 고객의 규정 요구 사항에 따라 직접 연결을 Office 365 모든 고객 요청을 검토하고 고객 사용에 대한 ExpressRoute만 승인합니다. 이러한 요구 사항이 있는 경우 Microsoft 검토를 시작하려면 Office 365 요청 양식에 직접 연결이 필요하다는 의미로 [해석되는](https://aka.ms/O365ERReview) 규정에 대한 텍스트 발췌 및 웹 링크를 제공하세요. 사용자에 대한 경로 필터를 만들려고 Office 365 오류 메시지가 [표시됩니다.](https://support.microsoft.com/kb/3181709)
  
네트워크 평가를 계획할 때 고려할 주요 Microsoft 365.
  
- Microsoft 365 공용 인터넷을 통해 실행되는 안전하고 신뢰할 수 있는 고성능 서비스입니다. 서비스의 이러한 측면을 개선하기 위해 계속 투자하고 있습니다. 모든 Microsoft 365 서비스는 인터넷 연결을 통해 사용할 수 있습니다.

- 당사는 가용성, 전역 도달 Microsoft 365 인터넷 기반 연결의 성능과 같은 핵심적인 측면을 지속적으로 최적화하고 있습니다. 예를 들어 많은 Microsoft 365 인터넷 연결 에지 노드 집합을 활용합니다. 이 에지 네트워크는 인터넷을 통해 연결에 가장 근접하고 성능을 제공합니다.

- Microsoft 365 온라인 음성, 비디오 또는 모임 기능과 같은 Teams 또는 비즈니스용 Skype Online 음성, 비디오 또는 모임 기능에 대해 서비스를 사용할 때 고객은 종단 간 네트워크 평가를 완료하고 [Microsoft](https://www.microsoft.com/fasttrack)FastTrack.

네트워크 평가를 Microsoft 365 어디서 시작해야 할지 잘 모를 경우 또는 해결해야 할 지원이 필요한 네트워크 디자인 문제를 발견한 경우 Microsoft 계정 팀과 함께 작업하세요.

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 연결 테스트

Microsoft 365 [](https://aka.ms/netonboard) 연결 테스트는 Microsoft 365 테넌트에 대해 기본 연결 테스트를 실행하고 최적의 성능에 대한 특정 네트워크 디자인 권장 사항을 Microsoft 365 POC(개념 증명) 네트워크 평가 도구입니다. 이 도구는 일반적인 대규모 엔터프라이즈 네트워크 경계 디자인 선택을 강조하여 인터넷 웹 검색에 유용하지만 검색과 같은 대규모 SaaS 응용 프로그램의 성능에는 영향을 Microsoft 365.

네트워크 온보드 도구는 다음을 실행합니다.

- 위치를 검색하거나 테스트할 위치를 지정할 수 있습니다.
- 네트워크 유선의 위치 확인
- 가장 가까운 서비스 프런트 도어에 Microsoft 365 경로 테스트
- 프록시 서버, 방화벽 및 DNS와 관련된 경계 Windows 10 권장하는 다운로드 가능한 응용 프로그램을 사용하여 고급 테스트를 제공합니다. 또한 이 도구는 비즈니스용 Skype Online, Microsoft Teams Online 및 SharePoint 성능 테스트를 Exchange Online.

이 도구에는 기본 연결 정보를 수집하는 브라우저 기반 UI와 고급 테스트를 실행하고 추가 평가 데이터를 반환하는 다운로드 가능한 Windows 10 응용 프로그램 등 두 가지 구성 요소가 있습니다.

브라우저 기반 도구에 다음 정보가 표시됩니다.

- 결과 및 영향 탭
  - 사용 중 서비스 프런트 도어의 지도 위치
  - 최적의 연결을 제공하는 다른 서비스 프런트 도어의 지도 위치
  - 가까운 다른 고객에 비해 Microsoft 365 상대적인 성과
- 세부 정보 및 솔루션 탭
  - 도시 및 국가당 사용자 위치
  - 도시, 주 및 국가에 따라 네트워크의 위치
  - 사용자와 네트워크로의 거리
  - Microsoft 365 Exchange Online 서비스 프런트 도어 위치
  - 사용자 Microsoft 365 Exchange Online 최적의 서비스 프런트 도어
  - 더 나은 성능으로 대도시 지역에 있는 고객

다운로드 가능한 고급 테스트 응용 프로그램은 다음과 같은 추가 정보를 제공합니다.

- 세부 정보 및 솔루션 탭(추가)
  - 사용자의 기본 게이트웨이
  - 클라이언트 DNS 서버
  - 클라이언트 DNS 재발 문제 해결사
  - Exchange Online DNS 서버
  - SharePoint 온라인 DNS 서버
  - 프록시 서버 식별
  - 미디어 연결 확인
  - 미디어 품질 패킷 손실
  - 미디어 품질 대기 시간
  - 미디어 품질 지터
  - 미디어 품질 패킷 다시 오더
- 여러 기능별 끝점에 대한 연결 테스트
- Exchange Online Online 및 SharePoint 서비스에 대한 추적 및 대기 Teams 진단

Microsoft 365 연결 테스트에 대해 읽고 새 네트워크 디자인 권장 사항으로 업데이트된 Microsoft 365 연결 테스트 POC 블로그 [게시물에서](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) 의견을 제공할 수 있습니다. 이 도구 및 기타 Microsoft 365 업데이트에 대한 정보는 네트워킹 Office 365 [게시될](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) 예정입니다.
  
돌아오는 데 사용할 수 있는 짧은 링크는 [ https://aka.ms/o365networkconnectivity 입니다. .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 네트워크 연결 개요](microsoft-365-networking-overview.md)

[Microsoft 365 네트워크 연결 원칙](./microsoft-365-network-connectivity-principles.md)

[Office 365 엔드포인트 관리](managing-office-365-endpoints.md)

[Office 365 URL 및 IP 주소 범위](urls-and-ip-address-ranges.md)

[Office 365 IP 주소 및 URL 웹 서비스](microsoft-365-ip-web-service.md)

[Microsoft 365 및 성능 조정](network-planning-and-performance.md)

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)