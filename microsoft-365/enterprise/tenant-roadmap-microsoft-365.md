---
title: Microsoft 365에 대 한 테 넌 트 로드맵
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365initiative-coredeploy
ms.custom: it-pro
description: Microsoft 365에 대 한 테 넌 트를 설정 하기 위한 로드맵
ms.openlocfilehash: e4b2af9143070caa1ebd8fd66ef9f367f85d3bb9
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357913"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365에 대 한 테 넌 트 로드맵

Microsoft 365 테 넌 트가 조직에 할당 된 서비스 집합입니다. 일반적으로이 테 넌 트는 하나 이상의 DNS 도메인 이름과 연결 되어 있으며 사용자 계정에 할당 하는 다른 구독 및 라이선스 내의 중앙 컨테이너 역할을 합니다.

Microsoft 365 테 넌 트를 만들 때이를 특정 지리적 위치에 할당 합니다. 여러 지리적 위치를 사용 하 여 테 넌 트를 만들고 테 넌 트를 한 위치에서 다른 위치로 이동할 수도 있습니다.

네트워킹 및 id의 기본 서비스에 대 한 테 넌 트를 준비 하려면 테 넌 트 구성을 신중 하 게 계획 하 고 실행 하는 것이 중요 합니다.

## <a name="plan"></a>계획

다음을 수행 하 여 테 넌 트 구현을 계획 합니다.

- [구독, 라이선스 및 Azure AD (Active Directory) 테 넌 트 이해](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [타사 SSL 인증서 사용 방법 이해](plan-for-third-party-ssl-certificates.md)
- [Microsoft 365 테 넌 트가 Azure AD services와 통합 되는 방식 이해](integrated-apps-and-azure-ads.md)
- [클라이언트 앱 지원 계획](microsoft-365-client-support-certificate-based-authentication.md)
- [하이브리드 최신 인증을 사용 하는 방법 결정](hybrid-modern-auth-overview.md)
- [Office 2007 및 Office 2010 업그레이드 계획](plan-upgrade-previous-versions-office.md)
- [테 넌 트 격리 이해](microsoft-365-tenant-isolation-overview.md)
- [Microsoft 365 서비스 보증에 대 한 세부 정보 얻기](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>배포

테 넌 트를 배포 하려면 조직의 [DNS 도메인을 추가](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 하 고 [Microsoft 365 관리 센터에서 설치 가이드](setup-guides-for-microsoft-365.md)를 사용 합니다.

## <a name="tenants-with-multiple-geographic-locations"></a>여러 지리적 위치가 있는 테 넌 트

Microsoft 365 Multi-Geo를 사용하면 Microsoft 365 범위를 기존 테넌트 내 여러 지리적 지역 및 / 또는 국가로 확장할 수 있습니다.

이를 계획, 구성 및 관리 하는 방법을 포함 하 여 Microsoft 365 다중 위치에 대 한 자세한 내용은 [여기에서 시작](microsoft-365-multi-geo.md)합니다.

## <a name="move-a-tenants-geographic-locations"></a>테 넌 트의 지리적 위치 이동

Microsoft는 Microsoft 365 서비스에 대 한 새로운 데이터 센터 지리적 위치 (geos)를 계속 해 서 엽니다. 이러한 새 데이터 센터 지역는 고객 요구 및 사용 증가를 지원 하기 위해 용량을 추가 하 고 리소스를 계산 합니다. 또한 새 데이터 센터 지역는 핵심 고객 데이터에 대 한 상주 데이터를 제공 합니다.

지리적 데이터 이동을 요청 하는 방법을 포함 하 여 Microsoft 365 데이터 센터 geo에 대 한 자세한 내용은 [여기에서 시작](moving-data-to-new-datacenter-geos.md)합니다.

## <a name="next-step"></a>다음 단계

[구독, 라이선스, 계정, 테](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)넌 트를 사용 하 여 테 넌 트 계획을 시작 합니다.

