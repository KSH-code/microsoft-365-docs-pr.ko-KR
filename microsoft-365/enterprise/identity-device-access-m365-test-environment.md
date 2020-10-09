---
title: Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: b8e91a58bb6e1c00013b963c77151080a419b836
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398810"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*

[Id 및 장치 액세스 구성은](../security/office-365-security/microsoft-365-policies-configurations.md) Azure Active Directory (azure AD)와 통합 된 모든 서비스에 대 한 액세스를 보호 하기 위한 기능 및 조건부 액세스 정책의 집합입니다.

일반적인 id 및 장치 액세스 구성을 사용 하는 테스트 환경을 만들려면 다음을 수행 합니다.

1. 선택한 ID 모델 및 인증 방법에 따라 필수 구성 요소 ID 및 보안 기능을 사용하여 테스트 환경을 구성합니다.

  - [클라우드 전용](cloud-only-prereqs-m365-test-environment.md)
  - [암호 해시 동기화 (PHS)](phs-prereqs-m365-test-environment.md)
  - [통과 인증(PTA)](pta-prereqs-m365-test-environment.md)

2. [일반 id 및 장치 액세스 정책을](identity-access-policies.md) 사용 하 여 테스트 환경에 구성 된 필수 구성 요소를 기반으로 하는 정책을 구성 하 고 id 및 장치에 대 한 보호를 탐색 하 고 확인 합니다.

## <a name="see-also"></a>참고 항목

[추가 ID 테스트 랩 가이드](m365-enterprise-test-lab-guides.md#identity)

[Id 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
