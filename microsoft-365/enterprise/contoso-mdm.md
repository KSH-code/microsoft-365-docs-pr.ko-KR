---
title: Contoso의 모바일 장치 관리
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
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 엔터프라이즈용 Microsoft 365의 Microsoft Intune을 사용하여 디바이스 및 장치에서 실행되는 앱을 관리하는 방법을 이해합니다.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754000"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso의 모바일 장치 관리

엔터프라이즈용 Microsoft 365에는 Intune과 모바일 장치 및 응용 프로그램 관리 및 보안을 지원하는 Azure 서비스 집합이 포함되어 있습니다.

Contoso에는 많은 모바일 지원 직원이 있습니다. 일부는 Contoso 위치에 사무실을 가지며, 일부는 사무실이 없습니다. Contoso는 직원 생산성을 높이고 디바이스, 해당 장치에 저장된 Contoso 데이터 및 응용 프로그램 동작을 안전하게 유지하는 방법이 필요했습니다.

## <a name="plan"></a>계획

Contoso는 엔터프라이즈용 Microsoft 365의 모바일 장치 관리에 대한 다음과 같은 Intune 사용 사례를 확인했습니다.

- 모바일 장치에서 안전하게 액세스할 수 있도록 Exchange Online 전자 메일 및 데이터를 보호합니다.
- Contoso 직원을 위한 BYOD(Bring Your Own Device) 프로그램을 구현합니다.
- Contoso 직원에게 조직 소유의 휴대폰 및 제한된 사용 공유 태블릿을 발급합니다.

Contoso는 다음을 위해 Intune을 사용하지 않습니다.

- 직원이 관리되지 않는 공용 키오스크에서 Microsoft 365에 안전하게 액세스할 수 있도록 허용합니다.
- 모바일 장치에서 안전하게 액세스할 수 있도록 프레미스 전자 메일 및 데이터를 보호합니다. 이는 Microsoft Exchange 서버가 없습니다.

## <a name="deploy"></a>배포

Contoso가 모바일 장치 관리 인프라를 설정하는 방법은 다음과 같습니다.

- Intune을 MDM(모바일 장치 관리) 기관으로 설정하고 Azure에서 Intune을 사용하여 콘텐츠를 관리하고 디바이스를 관리합니다.
- 등록 및 Intune 설정 및 장치 기반 조건부 액세스 정책에 대한 장치용 Azure AD(Azure Active Directory) 그룹 생성

  자세한 내용은 [Contoso 조건부 액세스 정책을 참조하십시오.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)

- iPad, iMacs 및 iPhone과 회사 소유의 iPhone을 사용하는 직원을 지원하기 위해 Apple 장치 플랫폼을 사용하도록 설정
- 모바일 장치에 Contoso의 회사 포털을 설치하는 동안 표시되는 Contoso 고유의 사용 약관 정책 생성
- 등록되지 않은 장치의 경우 Microsoft 365 서비스에 액세스하기 위해 인증을 요구하는 MAM(모바일 응용 프로그램 관리) 정책 집합을 구현했습니다.
- 다음을 적용하는 Intune 정책 생성:
  - 허용된 앱.
  - 무단 액세스를 방지하는 데 도움이 되는 장치 암호화
  - 6자리 PIN 또는 암호입니다.
  - 비활성 시간 제한 기간입니다.
  - Windows 10 장치에서 바이러스 백신 Windows Defender 및 서명 업데이트.
  - 최신 보안 업데이트를 포함 하는 Windows 10 장치의 자동 업데이트.
  - 관리되는 장치에 인증서 푸시
  - 기업 및 개인 데이터의 명확한 분리. 사용자 또는 관리자는 그림, 개인 전자 메일 계정 및 개인 파일과 같은 개인 데이터는 그대로 두면서 장치에서 회사 데이터를 선택적으로 초기화할 수 있습니다.

Contoso는 PC 및 회사 소유의 스마트폰 및 태블릿을 적절한 Intune 장치 그룹에 추가하여 배포했습니다. 또한 직원이 개인 장치를 등록할 수 있도록 BYOD 프로그램을 설정했습니다. 등록된 디바이스는 관리 및 보안 장치와 응용 프로그램을 보장하는 Intune 정책을 수신합니다. 등록되지 않은 장치에는 허용되는 응용 프로그램을 지정하는 MAM(모바일 응용 프로그램 관리) 정책이 있습니다.

다음은 Contoso 모바일 장치 관리 배포 아키텍처입니다.

![Contoso 모바일 장치 관리 배포 인프라](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>다음 단계

Contoso가 엔터프라이즈용 [](contoso-info-protect.md) Microsoft 365의 정보 보호 기능을 사용하여 조직 전체에서 중요한 디지털 자산을 분류, 식별 및 보호하는 방법을 알아보습니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365의 장치 관리](device-management-roadmap-microsoft-365.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

