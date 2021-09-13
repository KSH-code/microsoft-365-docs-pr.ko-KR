---
title: 테넌트에 대한 Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 테넌트에 대한 테넌트 설정 로드맵을 Microsoft 365.
ms.openlocfilehash: d041c87e12bfb3025592cb14cda5413c805dc880
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187852"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>테넌트에 대한 Microsoft 365

사용자 Microsoft 365 테넌트는 조직에 할당된 서비스 집합입니다. 일반적으로 이 테넌트는 공용 DNS 도메인 이름 중 하나 이상과 연결되고, 사용자 계정에 할당한 여러 구독 및 해당 구독 내의 라이선스에 대한 중앙 및 격리된 컨테이너 역할을 합니다. 자세한 내용은 Microsoft 클라우드 서비스 구독, 라이선스, 계정 및 [테넌트 를 참조하세요.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)

테넌트 Microsoft 365 특정 지리적 위치에 할당합니다. 여러 지리적 위치가 있는 테넌트가 있을 수도 있으며 테넌트는 한 위치에서 다른 위치로 이동할 수 있습니다.

테넌트가 사용자, 그룹, 라이선스 및 클라우드 앱을 사용할 수 있도록 준비하려면 테넌트 구성을 신중하게 계획하고 실행하는 것이 중요합니다.

## <a name="set-up-your-microsoft-365-tenant"></a>테넌트 Microsoft 365 설정

네트워킹이 Microsoft 365 및 원격 작업자 모두에 대한 액세스에 최적화된 경우 다음 큰 작업은 DNS 도메인 이름, 일반 서비스 및 보안 사용자 로그인을 지원하는 해당 ID 인프라에 대한 Microsoft 365 테넌트에 대한 계획 및 구성을 계획하고 있습니다.

### <a name="plan"></a>계획

테넌트 구현을 계획하는 경우:

- [구독, 라이선스 및 Azure AD(Azure Active Directory) 테넌트 이해](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [타사 SSL 인증서 사용 방법 이해](plan-for-third-party-ssl-certificates.md)
- [테넌트가 Azure AD Microsoft 365 통합되는 방식 이해](integrated-apps-and-azure-ads.md)
- [클라이언트 앱 지원 계획](microsoft-365-client-support-certificate-based-authentication.md)
- [하이브리드 최신 인증 사용 방법 결정](hybrid-modern-auth-overview.md)
- [Office 2007 및 Office 업그레이드 계획](plan-upgrade-previous-versions-office.md)
- [테넌트 고리 이해](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a>배포

테넌트 배포: 

- 조직의 [DNS](../admin/setup/add-domain.md) 도메인을 추가합니다.
- 의 [설치 가이드를 Microsoft 365 관리 센터.](setup-guides-for-microsoft-365.md)
- ID 인프라를 [구축하고](identity-roadmap-microsoft-365.md) [사용자 로그인을 보호합니다.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>테넌트의 지리적 위치 이동

Microsoft는 계속해서 서비스용 새 데이터 센터 지리적 위치(지리적 위치)를 Microsoft 365 있습니다. 이러한 새로운 데이터 센터 지역은 고객 요구 및 사용 증가를 지원하기 위해 용량 및 계산 리소스를 추가합니다. 또한 새 데이터 센터 지역은 핵심 고객 데이터에 대한 지역 내 데이터 레지스터를 제공합니다.

자세한 내용은 핵심 데이터를 새 데이터 센터 지역으로 [Microsoft 365 이동을 참조하세요.](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Multi-Microsoft 365 배포

Microsoft 365 Multi-Geo를 사용하면 Microsoft 365 범위를 기존 테넌트 내 여러 지리적 지역 및 / 또는 국가로 확장할 수 있습니다.

자세한 내용은 [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md)을 참조하세요.

## <a name="manage-multiple-microsoft-365-tenants"></a>여러 Microsoft 365 테넌트 관리 

조직에 단일 테넌트가 있는 것이 이상적이기는 하지만 여러 테넌트가 있는 많은 조직 중 하나일 수 있습니다. 인수 합병, 관리적 고리 사용, 분산된 IT 등 다양한 이유가 있습니다.

테넌트가 여러 개인 Microsoft 365 자세한 내용은 다음 문서를 참조하세요.

- [테넌트 간 공동 작업](microsoft-365-inter-tenant-collaboration.md)
- [교차 테넌트 사서함 마이그레이션](cross-tenant-mailbox-migration.md)
- [테넌트 간 마이그레이션](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>다음 단계

[구독, 라이선스,](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)계정 및 테넌트로 테넌트 계획을 시작하세요.