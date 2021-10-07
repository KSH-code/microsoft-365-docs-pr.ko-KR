---
title: Microsoft 365 네트워크 연결 개요
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/27/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: SaaS 서비스에 네트워크 최적화가 중요한 이유, Microsoft 365 네트워킹의 목표 및 SaaS가 다른 워크로드와 다른 네트워킹을 요구하는 방법에 대해 논의합니다.
ms.openlocfilehash: e5dcbae5a1fbac3b0b4fd4472fdcac2380b84382
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209708"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365 연결 개요

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 다양한 마이크로 서비스 및 응용 프로그램을 통해 생산성 및 공동 작업 시나리오를 제공하는 분산 SaaS(Software-as-a-Service) 클라우드입니다. Microsoft 365, Outlook, Word 및 PowerPoint 같은 클라이언트 구성 요소는 사용자 컴퓨터에서 실행되어 Microsoft 데이터 센터에서 Microsoft 365 구성 요소에 연결합니다. 최종 사용자 환경의 품질을 결정하는 가장 중요한 요소는 Microsoft 365 클라이언트와 서비스 프런트 도어 간의 네트워크 안정성과 Microsoft 365 낮은 Microsoft 365 요인입니다.

이 문서에서는 Microsoft 365 네트워킹의 목표에 대해 알아보고, Microsoft 365 네트워킹에 일반 인터넷 트래픽과 다른 최적화 방식이 필요한 이유에 대해 알아보고 있습니다.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 네트워킹 목표

네트워킹을 Microsoft 365 가장 가까운 끝점과 클라이언트 간에 가장 제한적인 액세스를 사용하도록 설정하여 최종 사용자 환경을 최적화하는 Microsoft 365 있습니다. 최종 사용자 환경의 품질은 사용자가 사용하는 응용 프로그램의 성능 및 응답 성능과 직접적인 관련이 있습니다. 예를 들어 Microsoft Teams 전화 통화, 회의 및 공유 화면 공동 작업에서 문제가 없는 낮은 대기 시간을 사용할 수 있으며, Outlook 서버 쪽 인덱싱 및 AI 기능을 적용하는 인스턴트 검색 기능에 대한 훌륭한 네트워킹 연결을 사용할 수 있습니다.

네트워크 디자인의 기본 목표는 전 세계에 분산된 대기 시간이 짧은 고가용성 클라우드 응용 프로그램 진입점으로 모든 Microsoft의 데이터 센터를 상호 연결하는 Microsoft의 공용 네트워크 백본인 클라이언트 컴퓨터의 RTT(왕복 시간)를 줄여 대기 시간을 최소화하는 것입니다. [Microsoft가 빠르고 안정적인 글로벌 네트워크를 구축하는 방법](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)에서 Microsoft 글로벌 네트워크에 대해 자세히 알아볼 수 있습니다.

네트워크 Microsoft 365 최적화하는 것은 복잡할 필요가 없습니다. 다음과 같은 몇 가지 주요 원칙에 따라 최상의 성능을 얻을 수 있습니다.

- 네트워크 Microsoft 365 식별
- 사용자가 연결되는 각 위치에서 인터넷으로의 Microsoft 365 네트워크 트래픽의 로컬 분기 Microsoft 365
- 전송 Microsoft 365 및 패킷 검사 장치를 무시하도록 허용

네트워크 연결 원칙에 Microsoft 365 자세한 내용은 Microsoft 365 [네트워크 연결 원칙을 참조하세요.](microsoft-365-network-connectivity-principles.md)

## <a name="traditional-network-architectures-and-saas"></a>기존 네트워크 아키텍처 및 SaaS

클라이언트/서버 워크로드에 대한 기존 네트워크 아키텍처 원칙은 클라이언트와 끝점 간의 트래픽이 회사 네트워크 경계 외부로 확장되지 않는다는 가정 하에 설계되었습니다. 또한 많은 엔터프라이즈 네트워크에서 모든 아웃바운드 인터넷 연결이 회사 네트워크를 트래버스하고 중앙 위치에서 나갈 수 있습니다.

기존 네트워크 아키텍처에서 일반 인터넷 트래픽의 대기 시간은 네트워크 경계 보안을 유지 관리하기 위해 필요한 장단점이고, 인터넷 트래픽에 대한 성능 최적화에는 일반적으로 네트워크 전송 지점에서 장비를 업그레이드 또는 수리하는 과정이 있습니다. 그러나 이 접근 방식은 365와 같은 SaaS 서비스의 최적의 네트워크 성능에 대한 요구 Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>네트워크 Microsoft 365 식별

네트워크 트래픽을 보다 쉽게 식별하고 Microsoft 365 쉽게 관리할 수 있도록 지원하고 있습니다.

- 인터넷 대기 시간의 영향을 들이지 않는 네트워크 트래픽과 매우 중요한 네트워크 트래픽을 구분하기 위해 새로운 범주의 네트워크 끝점입니다. 가장 중요한 "최적화" 범주에는 소수의 URL과 지원 IP 주소가 있습니다.
- 스크립트 사용 또는 직접 장치 구성 및 네트워크 식별 변경 관리를 위한 Microsoft 365 서비스입니다. 변경 내용은 웹 서비스 또는 RSS 형식 또는 전자 메일에서 사용할 수 Microsoft Flow 있습니다.
- [Office 365](./microsoft-365-networking-partner-program.md) 연결 원칙을 따르고 간단한 구성을 가지는 장치 또는 서비스를 Microsoft 365 Microsoft 파트너와 네트워크 파트너 프로그램을 구성합니다.

## <a name="securing-microsoft-365-connections"></a>연결 Microsoft 365 보안

기존 네트워크 보안의 목표는 침입과 악의적인 악용으로부터 회사 네트워크 경계를 강화하는 것입니다. 대부분의 엔터프라이즈 네트워크는 프록시 서버, 방화벽, SSL 중단 및 조사, 심층 패킷 검사 및 데이터 손실 방지 시스템과 같은 기술을 사용하여 인터넷 트래픽에 대한 네트워크 보안을 적용합니다. 이러한 기술은 일반적인 인터넷 요청에 대한 중요한 위험을 완화하지만, Microsoft 365 엔드포인트에 적용되는 경우 성능, 확장성 및 최종 사용자 환경의 질을 크게 저하시킬 수 있습니다.

Microsoft 365 기능을 위해 특별히 설계된 기본 제공 보안 및 거버넌스 기능을 사용하여 콘텐츠 보안 및 데이터 사용 규정 준수에 대한 조직의 요구를 Microsoft 365 도움이 됩니다. 보안 및 규정 Microsoft 365 대한 자세한 내용은 보안 Office 365 [로드맵을 참조하세요.](/office365/securitycompliance/security-roadmap) Microsoft 365 트래픽에 대해 고급 수준의 처리를 수행하는 고급 네트워크 솔루션에 대한 Microsoft의 권장 사항 및 지원 위치에 대한 자세한 내용은 Office 365 트래픽에 타사 네트워크 장치 또는 솔루션 사용을 [Office 365 참조하세요.](https://support.microsoft.com/help/2690045)

## <a name="why-is-microsoft-365-networking-different"></a>네트워크 Microsoft 365 다른 이유는 무엇입니까?

Microsoft 365 및 암호화된 네트워크 연결을 사용하여 성능을 최적화하도록 설계되어 경계 보안 적용의 필요성이 줄어 습니다. Microsoft 365 데이터 센터는 전 세계에 있으며, 이 서비스는 클라이언트를 사용 가능한 최상의 서비스 끝점에 연결하는 다양한 방법을 사용할 수 있도록 디자인되었습니다. 사용자 데이터와 처리는 여러 Microsoft 데이터 센터 간에 분산되어 있으며 클라이언트 컴퓨터를 연결할 수 있는 단일 네트워크 끝점이 없습니다. 실제로 Microsoft 365 테넌트의 데이터 및 서비스는 Microsoft 전역 네트워크에서 동적으로 최적화되어 최종 사용자가 액세스하는 지리적 위치에 맞게 조정됩니다.

특정 일반적인 성능 문제는 Microsoft 365 검사 및 중앙 집중식 전송이 적용될 때 생성됩니다.

- 대기 시간이 길면 비디오 및 오디오 스트림의 성능이 저하되고 데이터 검색, 검색, 실시간 공동 작업, 약속이 있는 일정 정보, 제품 내 콘텐츠 및 기타 서비스에 대한 응답 속도가 느려질 수 있습니다.
- 중앙 위치에서 연결을 유출하면 Microsoft 365 네트워크의 동적 라우팅 기능이 제거되어 대기 시간 및 왕복 시간이 추가됩니다.
- 네트워크 트래픽을 Microsoft 365 SSL 보안 암호를 해독하고 다시 암호화하면 프로토콜 오류가 발생할 수 있으며 보안 위험이 있습니다.

클라이언트 트래픽이 지리적 위치에 최대한 가깝게 유입될 수 있도록 하여 Microsoft 365 진입점에 대한 네트워크 경로를 단축하면 연결 성능과 최종 사용자 환경이 Microsoft 365. 또한 네트워크 아키텍처가 향후 변경될 경우 성능 및 안정성에 미치는 영향을 줄일 Microsoft 365 있습니다. 최적의 연결 모델은 회사 네트워크 또는 집, 커피숍, 공항 등의 원격 위치에 있는지에 관계없이 항상 사용자 위치에 네트워크 발신을 제공하는 것입니다. 일반 인터넷 트래픽 및 WAN 기반 회사 네트워크 트래픽은 별도로 라우팅될 것이고 로컬 직접 발신 모델을 사용하지 않습니다. 이 로컬 직접 송신 모델은 아래 다이어그램에 표시되어 있습니다.

![로컬 송신 네트워크 아키텍처](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

로컬 송신 아키텍처는 기존 모델과 비교할 때 다음과 같은 Microsoft 365 네트워크 트래픽의 이점을 제공합니다.
  
- 경로 길이를 최적화하여 최적의 Microsoft 365 성능을 제공합니다. 최종 사용자 연결은 Microsoft 글로벌 네트워크의 분산 서비스 프런트 도어 인프라를  통해 가장 가까운 Microsoft 365 진입점으로 동적으로 라우팅되고 트래픽은 Microsoft의 매우 낮은 대기 시간 고가용성 파이버를 통해 내부적으로 데이터 및 서비스 끝점으로 라우팅됩니다.
- 회사 네트워크 인프라에 대한 부하를 줄이면 Microsoft 365 및 트래픽 검사 장치를 우회하여 로컬로 유출할 수 있습니다.
- 중복 네트워크 보안 기술을 적용하지 않도록 클라이언트 끝점 보안 및 클라우드 보안 기능을 적용하여 양 끝에서 연결을 보호합니다.

> [!NOTE]
> 분산 _서비스 Front Door_ 인프라는 지리적으로 분산된 위치가 있는 Microsoft 전역 네트워크의 고가용성 및 확장 가능한 네트워크 에지입니다. 최종 사용자 연결을 종료하고 Microsoft 전역 네트워크 내에서 효율적으로 라우팅합니다. [Microsoft가 빠르고 안정적인 글로벌 네트워크를 구축하는 방법](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)에서 Microsoft 글로벌 네트워크에 대해 자세히 알아볼 수 있습니다.

네트워크 연결 원칙을 이해하고 적용하는 Microsoft 365 자세한 내용은 Microsoft 365 네트워크 연결 원칙을 [참조하세요.](microsoft-365-network-connectivity-principles.md)

## <a name="conclusion"></a>결론

네트워크 Microsoft 365 최적화를 수행하면 불필요한 단점을 제거할 수 있습니다. 이러한 Microsoft 365 트러스트된 트래픽으로 처리하면 패킷 검사 및 프록시 대역폭 경쟁으로 인해 대기 시간이 도입되지 않도록 할 수 있습니다. 클라이언트 컴퓨터와 Office 365 로컬 연결을 허용하면 트래픽을 Microsoft 전역 네트워크를 통해 동적으로 라우팅할 수 있습니다.

## <a name="related-topics"></a>관련 주제

[Microsoft 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md)

[Office 365 엔드포인트 관리](managing-office-365-endpoints.md)

[Office 365 URL 및 IP 주소 범위](urls-and-ip-address-ranges.md)

[Office 365 IP 주소 및 URL 웹 서비스](microsoft-365-ip-web-service.md)

[Microsoft 365 네트워크 연결 평가](assessing-network-connectivity.md)

[Microsoft 365의 네트워크 계획 및 성능 조정](network-planning-and-performance.md)

[초기 계획 및 성능 기록을 사용하여 Office 365 성능 조정](performance-tuning-using-baselines-and-history.md)

[Office 365 성능 문제 해결 계획](performance-troubleshooting-plan.md)

[콘텐츠 배달 네트워크](content-delivery-networks.md)

[Microsoft 365 연결 테스트](https://aka.ms/netonboard)

[Microsoft가 빠르고 안정적인 글로벌 네트워크를 구축하는 방법](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 네트워킹 블로그](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
