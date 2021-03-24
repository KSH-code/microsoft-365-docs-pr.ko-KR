---
title: Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스
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
description: ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: e90c27edbf4ad5a78c337bf2488956ce82a1ec3e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051321"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*

[ID 및 장치 액세스 구성은](../security/defender-365-security/microsoft-365-policies-configurations.md) Azure AD(Azure Active Directory)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 권장 구성 및 조건부 액세스 정책 집합입니다.

공통 ID 및 장치 액세스 구성이 적용된 테스트 환경을 만들 수 있는 경우:

1. 선택한 ID 모델 및 인증 방법에 따라 필수 구성 요소 ID 및 보안 기능을 사용하여 테스트 환경을 구성합니다.

  - [클라우드 전용](cloud-only-prereqs-m365-test-environment.md)
  - [PHS(암호 해시 동기화)](phs-prereqs-m365-test-environment.md)
  - [통과 인증(PTA)](pta-prereqs-m365-test-environment.md)

2. 일반 [ID](../security/defender-365-security/identity-access-policies.md) 및 장치 액세스 정책을 사용하여 테스트 환경에 대해 구성된 선행 구성을 토대한 정책을 구성하고 ID 및 장치에 대한 보호를 탐색하고 확인합니다.

## <a name="see-also"></a>참고 항목

[추가 ID 테스트 랩 가이드](m365-enterprise-test-lab-guides.md#identity)

[ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)
