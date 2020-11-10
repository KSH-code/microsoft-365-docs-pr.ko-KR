---
title: Microsoft 365에 대 한 테 넌 트 로드맵
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Microsoft 365에 대 한 테 넌 트를 설정 하기 위한 로드맵
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948400"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365에 대 한 테 넌 트 로드맵

Microsoft 365 테 넌 트가 조직에 할당 된 서비스 집합입니다. 일반적으로이 테 넌 트는 하나 이상의 공용 DNS 도메인 이름과 연결 되며, 다른 구독 및 사용자 계정에 할당 된 라이선스의 중앙 및 격리 된 컨테이너 역할을 합니다. 자세한 내용은 [구독, 라이선스, 계정 및 Microsoft 클라우드 서비스에 대 한 테 넌 트](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)를 참조 하세요.

Microsoft 365 테 넌 트를 만들 때이를 특정 지리적 위치에 할당 합니다. 여러 지리적 위치를 사용 하 여 테 넌 트를 만들고 테 넌 트를 한 위치에서 다른 위치로 이동할 수도 있습니다.

사용자, 그룹, 라이선스 및 클라우드 앱에 대 한 테 넌 트를 준비 하려면 테 넌 트 구성을 신중 하 게 계획 하 고 실행 하는 것이 중요 합니다.

## <a name="set-up-your-microsoft-365-tenant"></a>Microsoft 365 테 넌 트 설정

사용자가 온-프레미스 및 원격 작업자 모두에 대해 Microsoft 365에 액세스할 수 있도록 네트워킹을 최적화 한 후에는 다음 대규모 작업에서 DNS 도메인 이름, 일반 서비스 및 보안 사용자 로그인을 지 원하는 해당 id 인프라에 대 한 Microsoft 365 테 넌 트를 계획 하 고 구성 합니다.

### <a name="plan"></a>계획

다음을 수행 하 여 테 넌 트 구현을 계획 합니다.

- [구독, 라이선스 및 Azure AD (Active Directory) 테 넌 트 이해](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [타사 SSL 인증서 사용 방법 이해](plan-for-third-party-ssl-certificates.md)
- [Microsoft 365 테 넌 트가 Azure AD services와 통합 되는 방식 이해](integrated-apps-and-azure-ads.md)
- [클라이언트 앱 지원 계획](microsoft-365-client-support-certificate-based-authentication.md)
- [하이브리드 최신 인증을 사용 하는 방법 결정](hybrid-modern-auth-overview.md)
- [Office 2007 및 Office 2010 업그레이드 계획](plan-upgrade-previous-versions-office.md)
- [테 넌 트 격리 이해](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>배포

테 넌 트를 배포 하려면 

- 조직의 [DNS 도메인](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 을 추가 합니다.
- [Microsoft 365 관리 센터의 설치 가이드](setup-guides-for-microsoft-365.md)를 사용 합니다.
- [Id 인프라](identity-roadmap-microsoft-365.md) 를 구축 하 고 [사용자 로그인을 보호](microsoft-365-secure-sign-in.md)합니다.

### <a name="move-a-tenants-geographic-locations"></a>테 넌 트의 지리적 위치 이동

Microsoft는 Microsoft 365 서비스에 대 한 새로운 데이터 센터 지리적 위치 (geos)를 계속 해 서 엽니다. 이러한 새 데이터 센터 지역는 고객 요구 및 사용 증가를 지원 하기 위해 용량을 추가 하 고 리소스를 계산 합니다. 또한 새 데이터 센터 지역는 핵심 고객 데이터에 대 한 상주 데이터를 제공 합니다.

자세한 내용은 [핵심 데이터를 새로운 Microsoft 365 datacenter 지역로 이동을](moving-data-to-new-datacenter-geos.md)참조 하세요.


## <a name="deploy-microsoft-365-multi-geo"></a>Microsoft 365 다중 지역 배포

Microsoft 365 Multi-Geo를 사용하면 Microsoft 365 범위를 기존 테넌트 내 여러 지리적 지역 및 / 또는 국가로 확장할 수 있습니다.

자세한 내용은 [Microsoft 365 다중 Geo](microsoft-365-multi-geo.md)를 참조 하십시오.

## <a name="manage-multiple-microsoft-365-tenants"></a>여러 Microsoft 365 테 넌 트 관리 

Oganization에 대 한 테 넌 트를 하나만 사용할 수 있기는 하지만 여러 테 넌 트가 있는 여러 조직 중 하나일 수도 있습니다. 합병에는 인수 및 합병이 포함 되거나, 관리 격리가 필요 하거나, 분산 되어 있는 이유가 있습니다.

Microsoft 365 테 넌 트가 여러 개 있는 경우 다음 문서에서 자세한 내용을 참조 하세요.

- [테넌트 간 공동 작업](microsoft-365-inter-tenant-collaboration.md)
- [교차 테넌트 사서함 마이그레이션](cross-tenant-mailbox-migration.md)
- [테넌트 간 마이그레이션](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>다음 단계

[구독, 라이선스, 계정, 테](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)넌 트를 사용 하 여 테 넌 트 계획을 시작 합니다.
