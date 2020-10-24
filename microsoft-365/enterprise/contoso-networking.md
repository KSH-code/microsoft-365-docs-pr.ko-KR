---
title: Contoso Corporation에 대한 네트워킹
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 네트워킹 인프라와 회사에서 엔터프라이즈 클라우드 서비스용 Microsoft 365에 대 한 최적의 네트워킹 성능을 위해 SD WAN 기술을 사용 하는 방법을 이해 합니다.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754017"
---
# <a name="networking-for-the-contoso-corporation"></a>Contoso Corporation에 대한 네트워킹

클라우드 포함 인프라를 채택 하기 위해 Contoso는 클라우드 서비스에 대 한 네트워크 트래픽이 이동 하는 근본적인 변화를 고안 했습니다. Office 계층 구조의 다음 수준에 대 한 네트워크 연결 및 트래픽에 중점을 둔 내부 허브 및 스포크 모델 대신 사용자 위치를 로컬 인터넷 송신으로 매핑하고 인터넷에서 가장 가까운 Microsoft 365 네트워크 위치로 로컬 연결 합니다.

## <a name="networking-infrastructure"></a>네트워킹 인프라

다음은 전 세계에서 Contoso 사무실을 연결 하는 네트워크 요소입니다.

- 멀티 프로토콜 레이블 전환 (MPLS) WAN 네트워크

  MPLS WAN 네트워크는 서울 본사를 지역 사무소와 지역 사무소에 연결 하 고, 스포크 및 허브 구성에서는 위성 사무소를 대상으로 합니다. 사용자는 네트워크를 사용 하 여 파리 본사의 기간 업무 (lob) 응용 프로그램을 구성 하는 온-프레미스 서버에 액세스할 수 있습니다. 또한 모든 일반 인터넷 트래픽을 파리 사무실로 라우트 (네트워크 보안 장치에서 요청을 삭제) 합니다. 각 사무실 내에서 라우터는 개인 IP 주소 공간을 사용 하는 서브넷의 유선 호스트 또는 무선 액세스 지점에 트래픽을 전달 합니다.

- Microsoft 365 트래픽에 대 한 로컬 직접 인터넷 액세스

  각 사무실에는 프록시 서버를 통한 자체 인터넷 연결을 사용 하는 하나 이상의 로컬 인터넷 ISP 네트워크 회로가 포함 된 소프트웨어 정의 WAN (SD WAN) 장치가 있습니다. 이는 일반적으로 공용 IP 주소와 로컬 DNS 서버도 제공 하는 로컬 ISP에 대 한 WAN 링크로 구현 됩니다.

- 인터넷 서비스

  Contoso는 contoso \. com 공용 도메인 이름을 소유 합니다. Products 주문에 사용 되는 Contoso 공용 웹 사이트는 파리 캠퍼스의 인터넷 연결 데이터 센터에 있는 서버 집합입니다. Contoso는 인터넷에서 a/24 공용 IP 주소 범위를 사용 합니다.

그림 1은 Contoso 네트워킹 인프라와 인터넷에 대 한 연결을 보여 줍니다.

![Contoso 네트워크](../media/contoso-networking/contoso-networking-fig1.png)
 
**그림 1: Contoso 네트워크**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Microsoft에 대한 최적 네트워크 연결을 위해 SD-WAN 사용

Contoso는 다음과 같은 [Microsoft 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md)을 준수했습니다.

- Microsoft 365 네트워크 트래픽 식별 및 차별화
- 네트워크 연결을 로컬로 송신
- 네트워크 헤어핀 방지
- 중복된 네트워크 보안 장치 우회

Microsoft 365에 대 한 세 가지 범주의 네트워크 트래픽 ( *최적화*, *허용*및 *기본값*)이 있습니다. 최적화 및 허용 트래픽은 끝점에서 암호화 되 고 보안 되며 Microsoft 365 네트워크로 향하는 트러스트 된 네트워크 트래픽입니다.

Contoso는 다음의 사항을 결정했습니다:

- 최적화 및 허용 범주 트래픽에 대해 직접 인터넷 송신을 사용 하 고 모든 기본 범주 트래픽을 파리 기반 중앙 인터넷 연결로 전달 합니다.

- 각 사무실에서 SD-WAN 장치를 배포 하 여 이러한 원칙을 따르고 Microsoft 365 클라우드 기반 서비스에 대해 최적의 네트워크 성능을 얻는 방법을 확인할 수 있습니다.

  SD-WAN 장치에는 로컬 사무실 네트워크와 여러 대의 WAN 포트용 LAN 포트가 있습니다. 하나의 WAN 포트가 해당 MPLS 네트워크에 연결 됩니다. 다른 것은 로컬 ISP 회로에 연결 됩니다. SD-WAN 장치는 ISP 링크를 통해 최적화 및 허용범주 네트워크 트래픽을 라우팅합니다.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Contoso lob (기간 업무) 응용 프로그램 인프라

Contoso는 다음에 대 한 기간 업무 (lob) 응용 프로그램 및 서버 인트라넷 인프라를 설계 했습니다.

- 위성 사무소는 로컬 캐싱 서버를 사용하여 자주 액세스하는 문서 및 내부 웹 사이트를 저장합니다.
- 지역 허브는 지역 사무소와 위성 사무소에 지역 응용 프로그램 서버를 사용합니다. 이러한 서버는 파리 본사의 서버와 동기화됩니다.
- 파리 캠퍼스 데이터 센터에는 전체 조직에 서비스를 제공 하는 중앙 집중식 응용 프로그램 서버가 포함 되어 있습니다.

그림 2에서는 Contoso 인트라넷을 통해 서버에 액세스할 때 사용 되는 네트워크 트래픽 용량 비율을 보여 줍니다.

![내부 응용 프로그램에 대 한 Contoso 인프라](../media/contoso-networking/contoso-networking-fig2.png)
 
**그림 2: 내부 응용 프로그램에 대 한 Contoso 인프라**

위성 또는 지역별 허브 사무소의 경우 직원에 게 필요한 리소스의 60%가 위성 및 지역별 허브 office 서버에서 제공 될 수 있습니다. 리소스 요청의 추가 40 비율은 파리 캠퍼스에 대 한 WAN 링크를 방문 해야 합니다.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Microsoft 365 for enterprise의 네트워크 분석 및 준비

Contoso 사용자의 엔터프라이즈 서비스용 Microsoft 365을 성공적으로 채택 하는 것은 가용성이 높고 인터넷에 대 한 집중적인 연결에 의존 하 고 있으며 Microsoft 클라우드 서비스에 직접 연결할 수 있다는 것입니다. Contoso는 다음 단계를 수행 하 여 엔터프라이즈 클라우드 서비스용 Microsoft 365에 대 한 최적화 된 연결을 계획 하 고 구현 합니다.

1. 계획에 도움이 되는 회사 WAN 네트워크 다이어그램 만들기

   네트워크 계획을 시작 하기 위해 Contoso는 네트워크에서 관리 되는 office 위치, 기존 네트워크 연결, 기존 네트워크 경계 장치 및 서비스 클래스를 보여 주는 다이어그램을 만들었습니다. 이 다이어그램은 네트워킹 연결 계획 및 구현에서 이어지는 각 단계에 사용 됩니다.

2. 엔터프라이즈 네트워크 연결용 Microsoft 365 계획 만들기

   Contoso는 [microsoft 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md) 및 샘플 참조 네트워크 아키텍처를 사용 하 여 SD-WAN을 microsoft 365 연결에 대 한 기본 설정 토폴로지로 식별 했습니다.

3. 각 사무실의 인터넷 연결 사용률 및 MPLS-WAN 대역폭을 분석 하 고 필요한 경우 대역폭을 늘립니다.

   각 사무실의 현재 사용 현황이 분석 되었으며, Microsoft 365 클라우드 기반 트래픽이 평균 20%의 사용 하지 않는 용량을 사용 하 여 작동할 수 있도록 회선이 증가 했습니다.

4. Microsoft 네트워크 서비스에 대 한 성능 최적화

   Contoso는 최적의 성능을 위해 Office 365, Intune 및 Azure 끝점 집합을 확인 하 고 인터넷 경로에 방화벽, 보안 장치 및 기타 시스템을 구성 합니다. Office 365에 대 한 끝점 최적화 및 허용 범주 트래픽을 ISP 회로를 통한 라우팅을 위해 SD-WAN 장치로 구성 했습니다.

5. 내부 DNS 구성

   DNS가 작동해야 하고 Microsoft 365 트래픽 여부를 로컬에서 조회해야 합니다.

6. 네트워크 끝점 및 포트 연결 유효성 검사

   Contoso는 Microsoft 네트워크 연결 테스트 도구를 실행 하 여 엔터프라이즈 클라우드 서비스용 Microsoft 365에 대 한 연결을 확인 했습니다.

7. 네트워크 연결을 위해 직원 컴퓨터 최적화

   개별 컴퓨터에서 최신 운영 체제 업데이트가 설치 되었으며 끝점 보안 모니터링이 모든 클라이언트에서 활성 상태 인지 확인 합니다.

## <a name="next-step"></a>다음 단계

Contoso가 직원을 위해 [클라우드에서 온-프레미스 Active Directory 도메인 서비스를 활용](contoso-identity.md) 하 고 고객 및 비즈니스 파트너에 대 한 인증을 페더레이션 하는 방법을 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365에 대 한 네트워킹 로드맵](networking-roadmap-microsoft-365.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
