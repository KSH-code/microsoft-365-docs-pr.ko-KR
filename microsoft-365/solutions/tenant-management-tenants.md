---
title: 1단계. 엔터프라이즈용 Microsoft 365 테넌트
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: 다중 위치 및 이동 위치에 대한 옵션을 사용하여 단일 또는 여러 Microsoft 365 테넌트를 배포하고 관리합니다.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908718"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>1단계. 엔터프라이즈용 Microsoft 365 테넌트

첫 번째 테넌트 결정 중 하나는 가지는 수입니다. 각 Microsoft 365 테넌트는 다른 모든 Microsoft 365 테넌트와는 고유하며 고유합니다. 또한 해당 Azure AD 테넌트는 다른 모든 Microsoft 365 테넌트와는 고유하며 고유합니다.

## <a name="single-tenant"></a>단일 테넌트
테넌트가 하나만 있는 경우 조직에서 Microsoft 365를 사용하는 다양한 측면이 간소화됩니다. 단일 테넌트는 단일 계정, 그룹 및 정책 집합이 있는 단일 Azure AD 테넌트입니다. 조직 전체의 사용 권한 및 리소스 공유는 이 중앙 ID 공급자를 통해 수행될 수 있습니다.

단일 테넌트는 사용자에게 가장 기능이 풍부하고 간소화된 공동 작업 및 생산성 환경을 제공합니다.

다음은 Microsoft 365 테넌트의 기본 위치 및 Azure AD 테넌트에 대한 예제입니다.

![Azure AD 테넌트가 있는 단일 Microsoft 365 테넌트](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>여러 테넌트

조직에 여러 테넌트가 있을 수 있는 이유는 여러 가지가 있습니다.

- 관리 에지
- 분산된 IT
- 기록 결정
- 합병, 인수 또는 매입
- 대기업 조직에 대한 브랜딩 명확한 분리
- 사전 프로덕션, 테스트 또는 샌드박스 테넌트

다음은 동일한 기본 데이터 센터 지리적으로 두 테넌트(테넌트 A 및 테넌트 B)가 있는 조직의 예입니다. 각 테넌트는 별도의 Azure AD 테넌트로 구성됩니다.

![자체 Azure AD 테넌트가 있는 여러 Microsoft 365 테넌트](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

테넌트가 여러 개인 경우 테넌트 관리 및 사용자에게 서비스를 제공하는 경우 제한 사항 및 추가 고려 사항이 있습니다.

### <a name="inter-tenant-collaboration"></a>테넌트 간 공동 작업

사용자가 안전한 방식으로 다른 Microsoft 365 테넌트에서 보다 효과적으로 공동 작업을 하게 하려는 경우 테넌트 간 공동 작업 옵션으로는 파일 및 대화에 대한 중앙 위치 사용, 일정 공유, 통신을 위한 IM 사용, 오디오/비디오 통화 사용, 리소스 및 응용 프로그램에 대한 액세스 보안이 포함됩니다.

자세한 내용은 [Microsoft 365](../enterprise/microsoft-365-inter-tenant-collaboration.md)테넌트 간 공동 작업을 참조하세요.

### <a name="cross-tenant-mailbox-migration-preview"></a>테넌트 간 사서함 마이그레이션(미리 보기)

테넌트 간에 Exchange Online 사서함을 이동하기 전에(미리 보기) 현재 테넌트(원본 테넌트)에서 온-프레미스로 사용자 사서함을 완전히 오프보드한 다음 새 테넌트(대상 테넌트)에 온보드해야 합니다. 새로운 테넌트 간 사서함 마이그레이션 기능을 사용하면 원본 테넌트와 대상 테넌트의 테넌트 관리자가 모두 해당 테넌트 간에 사서함을 이동할 수 있으며, 해당 테넌트 간의 인프라 종속성은 최소 수준으로 유지될 수 있습니다. 이렇게 하여 사서함을 오프보드하고 온보드할 필요가 없습니다.

다음은 테넌트 간 사서함 마이그레이션 전에 두 가지 예로 테넌트와 해당 사서함을 예로 들 수 있습니다.

![여러 Microsoft 365 테넌트 및 해당 사서함](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

이 그림에서는 두 개의 개별 테넌트에 자체 도메인과 Exchange 사서함 집합이 있습니다.

다음은 테넌트 간 사서함 마이그레이션 후의 대상 테넌트(테넌트 A)입니다.

![테넌트 간 사서함 마이그레이션 후의 대상 테넌트](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

이 그림에서는 단일 테넌트에 도메인과 Exchange 사서함 집합이 모두 있습니다.

자세한 내용은 테넌트 간 사서함 [마이그레이션을 참조하십시오.](../enterprise/cross-tenant-mailbox-migration.md)

### <a name="tenant-to-tenant-migrations"></a>테넌트 간 마이그레이션

합병, 인수, 매입 및 기존 Microsoft 365 테넌트의 마이그레이션을 새 테넌트로 마이그레이션할 수 있는 기타 시나리오에 대한 아키텍처 방식이 여러 가지 있습니다. 

자세한 지침은 [Microsoft 365 테넌트 대 테넌트](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)마이그레이션을 참조하세요.

## <a name="multi-geo-for-a-tenant"></a>테넌트에 대한 Multi-Geo

Microsoft 365 Multi-Geo를 사용하면 데이터 보관 요구 사항을 충족하기 위해 선택한 다른 데이터 센터 지리적 위치에 미사용 데이터를 프로비전하고 저장할 수 있으며, 동시에 최신 생산성 환경의 글로벌 롤아웃을 작업자에게 제공합니다.

Multi-Geo 환경에서 Microsoft 365 테넌트는 Microsoft 365 구독이 원래 만들어진 기본 위치 또는 중앙 위치와 하나 이상의 위성 위치로 구성됩니다. 다중 위치 테넌트에서 지리적 위치, 그룹 및 사용자 정보에 대한 정보는 전역 Azure AD 테넌트에서 마스터됩니다. 테넌트 정보는 중앙에서 마스터된 후 각 지리적 위치로 동기화하기 때문에 회사의 모든 사용자와 관련된 공동 작업 환경이 여러 위치에서 공유됩니다.

다음은 유럽의 기본 위치와 북미의 위성 위치를 가지는 조직의 예입니다. 두 위치는 단일 Microsoft 365 테넌트에 대해 동일한 전역 Azure AD 테넌트를 공유합니다.

![Multi-Geo Microsoft 365 테넌트의 예](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

자세한 내용은 [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)을 참조하세요.

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>핵심 데이터를 새 데이터 센터 지역으로 이동

Microsoft는 계속해서 Microsoft 365 서비스에 대한 새 데이터 센터 지역을 열고 있습니다. 이러한 새로운 데이터 센터 지역은 지속적인 고객 수요 및 사용 증가를 지원하기 위해 용량 및 계산 리소스를 추가합니다. 또한 새로운 데이터 센터 지역은 핵심 고객 데이터에 대한 지역 내 데이터 레지스터를 제공합니다.

새 데이터 센터 지역을 열면 사용자 및 기존 데이터 센터 위치에 저장된 핵심 데이터에 영향을 미치는 것은 아니며, Microsoft는 휴지 상태의 조직의 핵심 고객 데이터를 새 데이터 센터 지역으로 조기 마이그레이션할 것을 요청할 수 있습니다.

다음은 Microsoft 365 테넌트가 유럽 연합(EU) 데이터 센터 지역에서 영국(영국)에 있는 테넌트로 이동된 예입니다.

![데이터 센터 지역 간에 Microsoft 365 테넌트 이동의 예](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

자세한 내용은 핵심 데이터를 새 Microsoft 365 데이터 센터 지역으로 [이동을 참조하세요.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>테넌트의 제품 및 라이선스

Microsoft 365 E3와 같은 첫 번째 제품을 구매하면 Microsoft 365 테넌트가 만들어집니다. 제품과 함께 월별 또는 연간 요금을 부과하는 라이선스가 있습니다. 그런 다음 관리자는 직접 또는 그룹 구성원 자격을 통해 제품 중 하나에서 사용 가능한 라이선스를 사용자 계정에 할당합니다. 조직의 비즈니스 요구에 따라 각각 자체 라이선스 풀이 있는 제품 집합이 있을 수 있습니다. 

제품 집합 및 각 제품의 라이선스 수를 결정하려면 다음을 계획해야 합니다.

- 고급 기능이 필요한 사용자 계정에 대한 라이선스가 충분한지 확인
- 조직의 직원 관리 변경에 따라 라이선스가 많지 않은 경우나 너무 많은 허가되지 않은 라이선스가 있는 것을 방지할 수 있습니다.


## <a name="results-of-step-1"></a>1단계 결과

엔터프라이즈용 Microsoft 365 테넌트의 경우 다음을 결정했습니다.

- 필요한 테넌트 수
- 각 테넌트에 대해 구매해야 하는 제품 및 라이선스
- 테넌트가 데이터 레지던스 요구 사항을 준수하기 위해 Multi-Geo가 필요한지 여부
- 테넌트 간 공동 작업을 설정해야 하는지 여부
- 테넌트 하나를 다른 테넌트로 마이그레이션해야 하는지 여부
- 핵심 데이터를 한 데이터 센터 지역에서 새 데이터 센터 지역으로 이동해야 하는지 여부

다음은 새 테넌트의 예입니다.

![새 테넌트의 예](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

이 그림에서 테넌트에는 다음이 있습니다.

- Microsoft 365 데이터 센터 지리적 위치에 해당하는 기본 위치입니다.
- 제품 및 라이선스 집합입니다.
- 클라우드 생산성 앱 집합(일부는 제품과 관련이 있습니다.)
- 전역 관리자 계정과 초기 DNS 도메인 이름을 포함하는 Azure AD 테넌트입니다.

이 솔루션의 추가 단계를 진행할 때 이 그림을 작성합니다.

## <a name="ongoing-maintenance-for-tenants"></a>테넌트에 대한 지속적인 유지 관리

지속적인 기준에 따라 다음을 해야 할 수 있습니다.

- 새 테넌트 추가
- 초기 라이선스 수가 있는 테넌트에 새 제품을 추가합니다.
- 테넌트의 제품에 대한 라이선스 집합을 변경하여 직원 요구 사항을 변경합니다.
- 테넌트에서 새 데이터 센터 지리적 위치로 핵심 데이터를 이동합니다.
- 데이터 저장 요구 사항에 대해 Multi-Geo를 추가합니다.
- 테넌트 간 공동 작업을 설정합니다.

## <a name="next-step"></a>다음 단계

[![2단계. 액세스를 위해 네트워크에 대한 테넌트 최적화](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

네트워킹을 [계속하여](tenant-management-networking.md) 작업자에서 Microsoft 365 클라우드 서비스로의 최적의 네트워킹을 제공합니다.
