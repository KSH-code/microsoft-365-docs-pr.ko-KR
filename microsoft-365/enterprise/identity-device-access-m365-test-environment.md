---
title: Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: 9195f532222511fc9dce474617ed52916d8e382a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073598"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스

[ID 및 장치 액세스 구성](microsoft-365-policies-configurations.md)은 Microsoft 365 Enterprise의 Office 365 및 Enterprise Mobility + Security(EMS) 등 Azure Directory(Azure AD)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 일련의 기능 및 조건부 액세스 정책입니다.

다음 정책을 적용한 테스트 환경을 만들기 위해서는 아래 내용을 따릅니다.

1. 선택한 ID 모델 및 인증 방법에 따라 필수 구성 요소 ID 및 보안 기능을 사용하여 테스트 환경을 구성합니다.

  - [클라우드 전용](cloud-only-prereqs-m365-test-environment.md)
  - [암호 해시 동기화(PHS)](phs-prereqs-m365-test-environment.md)
  - [통과 인증(PTA)](pta-prereqs-m365-test-environment.md)

2. [일반 ID 및 장치 액세스 정책](identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치 보호 기능을 테스트하는 정책을 구성합니다.

## <a name="see-also"></a>참고 항목

[추가 ID 테스트 랩 가이드](m365-enterprise-test-lab-guides.md#identity)

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
