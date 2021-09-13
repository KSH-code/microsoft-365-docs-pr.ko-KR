---
title: 클라우드 솔루션 공급자에 대한 추가 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 도이치란드 Microsoft 클라우드의 마이그레이션과 관련된 클라우드 솔루션 공급자에 대한 추가 정보입니다.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191272"
---
# <a name="additional-information-for-cloud-solution-providers"></a>클라우드 솔루션 공급자에 대한 추가 정보

고객을 지원하는 CSP(클라우드 솔루션 공급자)는 독일 Microsoft 클라우드에서 독일 신규 데이터 센터 지역으로 마이그레이션하는 동안 추가 단계를 수행해야 합니다.

## <a name="partner-tenant-migration"></a>파트너 테넌트 마이그레이션

파트너 Microsoft 클라우드 도이치랜드 테넌트는 마이그레이션되지 않습니다. 대신 새 Office 365 독일 데이터 센터 지역의 각 Microsoft 파트너에 대해 새 서비스 테넌트가 만들어집니다.

CSP 고객 테넌트는 새 독일 데이터 센터 지역으로 마이그레이션되어 동일한 파트너의 새 Office 365 서비스 테넌트에 연결됩니다. 고객이 전환된 후 파트너는 독일 데이터 센터 지역의 새로운 Office 365 서비스 테넌트로 고객을 관리할 수 있습니다.

## <a name="missing-subscriptions-in-azure"></a>Azure에서 구독 누락

구독 [및 라이선스 전환(3단계)이](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) 완료된 후 클라우드 솔루션 공급자는 더 이상 Azure 구독에 액세스할 수 없습니다.

액세스를 복구하려면 다음 단계에 따라 모든 Azure 구독 및 관리 그룹을 관리하기 위한 액세스 권한을 [상승합니다.](/azure/role-based-access-control/elevate-access-global-admin)
