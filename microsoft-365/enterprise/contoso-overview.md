---
title: Contoso Corporation 개요
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
description: Contoso Corporation의 기업 정보와 전 세계 사무소의 계층 구조를 파악합니다.
ms.openlocfilehash: b0c00ed5657d914851f28278a2f4cf80660b53b0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754271"
---
# <a name="overview-of-contoso-corporation"></a>Contoso Corporation 개요

Contoso Corporation은 서울에 본사가 있는 다국적 기업입니다. 회사가 10만 개 이상의 제품을 포함 하는 제조, 판매 및 지원 조직입니다.

## <a name="contoso-around-the-world"></a>전 세계 Contoso

그림 1에서는 파리의 본사와 해외 허브 및 다양 한 대륙의 위성 사무실을 보여 줍니다.

![전 세계의 Contoso 사무소](../media/contoso-overview/contoso-overview-fig1.png)

**그림 1: 전 세계의 Contoso 사무소**
 
Contoso에는 3 계층의 사무소가 있습니다.

- 본사

  Contoso 본부는 관리, 엔지니어링 및 제조 시설에서 수십 개의 건물을 사용 하 여 파리 outskirts의 기업 캠퍼스입니다. 모든 Contoso 데이터 센터와 인터넷 현재 상태는 파리 본사에 있습니다.

  본사의 직원 수는 25,000명입니다.

- 지역 허브

  허브 사무소는 60%의 판매 및 지원 직원이 있는 전세계의 특정 지역을 충족 합니다. 각 지역 허브는 고대역폭 WAN 링크를 통해 파리 본사에 연결 됩니다.

  지역별 허브는 평균적으로 2000 작업자입니다.

- 위성 사무소

  위성 사무소에는 80%의 판매 및 지원 담당자가 포함 됩니다. 주요 도시 또는 부 지역의 Contoso 고객에 대 한 현장 현재 상태를 제공 합니다. 각 위성 사무실은 고대역폭 WAN 링크를 통해 지역 허브에 연결 됩니다.

  위성 사무소에는 평균적으로 250의 작업 자가 있습니다.

Contoso 직원 중 25%는 모바일 전용입니다. 지역별 허브 및 위성 사무소에는 이러한 작업자의 백분율이 더 높습니다. 모바일 전용 작업자에 대 한 향상 된 지원을 제공 하는 것은 Contoso의 중요 한 비즈니스 목표입니다.

## <a name="design-considerations-for-microsoft-365-for-enterprise"></a>Microsoft 365 for enterprise에 대 한 디자인 고려 사항

Contoso IT 설계자는 Microsoft 365 for enterprise 배포에 대 한 다음과 같은 디자인 요구 사항 요인을 확인 했습니다.

- 현지 규정 및 준수 요구 사항이 있는 여러 지리적 위치
- 본사의 중앙 인트라넷 데이터 센터와 내부 lob (기간 업무) 응용 프로그램을 호스트 하는 지역 응용 프로그램 서버
- 기존 Microsoft Endpoint Configuration Manager 인프라
- Windows, Mac 및 Linux를 실행 하는 클라이언트 컴퓨팅 장치 조합
- iOS(iPhone 및 iPad) 및 Android 스마트폰과 태블릿을 포함하는 개인용 및 회사 소유의 모바일 장치
- 많은 원격 및 모바일 근로자
- 많은 비즈니스 파트너
- 관리 및 보호를 위한 많은 고객 및 기타 기밀 개인 정보
- 디자인 사양 형태로 제공되는 제품 및 제조 영업 비밀에 대한 고가치의 방대한 지적 재산권

## <a name="next-step"></a>다음 단계

Contoso Corporation [온-프레미스 IT 인프라](contoso-infra-needs.md) 와 회사의 비즈니스 요구 사항에 대 한 자세한 내용은 Microsoft 365 for enterprise를 참고 하세요.

## <a name="see-also"></a>참고 항목

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
