---
title: Microsoft 365 및 서비스 앱 지원
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 클라이언트 및 서비스 Microsoft 365 지원에 대한 세부 정보를 찾아야 합니다.
ms.openlocfilehash: 4ae294865bb506ae9e8a25e8f5ab28fff967171e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173333"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365 및 서비스 앱 지원

Microsoft는 고객 데이터를 안전하게 유지할 수 있도록 광범위한 보안, 인증 및 규정 준수 기능을 지원하며, IT 관리자가 사용자에 대해 조직 내에서 정책을 Microsoft 365 관리 센터 수 있습니다. 다음 기능은 사용자 구독에 따라 구성할 수 있는 많은 엔터프라이즈 기능의 Microsoft 365 있습니다.

## <a name="client-and-service-support"></a>클라이언트 및 서비스 지원

### <a name="continuous-access-evaluation-preview"></a>연속 액세스 평가(미리 보기)

지속적인 액세스 평가는 Exchange Online, SharePoint Online 및 Teams 같은 서비스가 거의 실시간으로 평가 및 적용될 수 있도록 Azure Active Directory 중요한 이벤트를 구독할 수 있도록 하여 구현됩니다. 중요한 이벤트 평가는 조건부 액세스 정책을 사용하지 않습니다. 따라서 모든 테넌트에서 사용할 수 있습니다.

현재 다음 이벤트가 평가됩니다.

- 사용자 계정이 삭제되거나 사용되지 않도록 설정되었습니다.
- 사용자의 암호가 변경되거나 다시 설정되었습니다.
- 사용자에 대해 다단계 인증 사용
- 관리자가 사용자에 대한 모든 새로 고침 토큰을 명시적으로 해지
- Azure AD ID 보호에서 감지된 높은 사용자 위험

클라이언트 및 서비스 앱 지원에 대한 지속적인 액세스 평가에 대한 자세한 내용은 연속 액세스 평가(미리 [보기)를 참조하세요.](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>클라이언트 지원

### <a name="certificate-based-authentication"></a>인증서 기반 인증

CBA(인증서 기반 인증)는 리소스, 네트워크, 응용 프로그램 또는 서비스에 대한 액세스 권한을 부여하기 전에 디지털 인증서를 사용하여 사용자, 컴퓨터 또는 장치를 식별하는 것입니다. 사용자 인증에서는 사용자 이름 및 암호와 같은 기존 방법과 함께 배포되는 경우가 종종 있습니다.

일부 기존 솔루션은 생체 인식 및 OTP(일회용 암호)과 같은 사용자만 사용할 수 있습니다. 인증서 기반 인증을 사용하는 경우 모든 끝점에 동일한 솔루션을 사용할 수 있습니다. 사용자, 장치 및 점점 증가하는 IoT(사물 인터넷)

클라이언트 및 서비스 앱 지원에 대한 인증서 기반 인증에 대한 자세한 내용은 Microsoft 365 클라이언트 앱 지원: 인증서 기반 인증을 [참조하세요.](microsoft-365-client-support-certificate-based-authentication.md)

### <a name="conditional-access"></a>조건부 액세스

조건부 액세스는 신호 Azure Active Directory 의사 결정을 내리고 조직 액세스 정책을 적용하는 데 사용하는 도구입니다. 조건부 액세스는 새로운 ID 기반 컨트롤 모델의 핵심입니다.

조건부 액세스 정책은 리소스에 대한 액세스 권한을 부여하기 위한 if-then 문입니다. 사용자가 리소스에 액세스하려는 경우 사용자가 작업을 완료해야 합니다. 정책 액세스 결정을 내릴 때 조건부 액세스에서 사용할 수 있는 일반적인 신호는 다음과 같습니다.

- 사용자 또는 그룹 구성원
- IP 위치 정보
- 장치 정보
- 응용 프로그램 정보
- 실시간 및 계산된 위험 감지
- Microsoft Cloud App Security(MCAS)

이러한 액세스 결정을 내릴 때 정책은 다른 작업을 수행할 수 있습니다.

- 이 정책은 액세스를 차단할 수 있습니다. 이 구성은 가장 제한적인 작업으로, 사용자가 리소스에 액세스하지 못하도록 합니다.
- 이 정책은 액세스 권한을 부여할 수 있습니다. 이 구성은 덜 제한적인 결정으로, 다음 옵션 중 하나 이상이 필요할 수 있습니다.

    - 다단계 인증
    - 규격으로 표시될 장치
    - 장치가 하이브리드 Azure AD에 가입된 경우
    - 승인된 클라이언트 앱
    - 구성된 앱 보호 정책(미리 보기)

클라이언트 및 서비스 앱 지원에 대한 조건부 액세스에 대한 자세한 내용은 다음을 참조하세요.

- [Microsoft 365 클라이언트 앱 지원: 장치 기반 조건부 액세스](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>모바일 응용 프로그램 관리

사용자는 종종 동일한 모바일 장치에서 조직 및 개인 문서, 전자 메일 및 데이터에 모두 액세스합니다. 이러한 장치는 종종 개인적으로 소유하며 조직 데이터와 사용자의 개인 정보를 모두 보호하도록 구성해야 합니다.

사용자가 조직 데이터에 액세스할 때 조직은 구성 정책 및 보호 정책과 같은 조직 정책이 장치의 조직 데이터를 보호하는 데 도움이 되어야 합니다. 또한 장치의 사용자 개인 콘텐츠는 조직의 제어 외부에 유지해야 합니다.

조직 관리 콘텐츠의 경우 응용 프로그램 관리 정책을 적용하여 응용 프로그램 관리 정책을 사용하여 데이터를 액세스, 공유 및 사용하는 방법을 제어할 수 Microsoft Intune. 예를 들어 다음 작업이 지원됩니다.

- 관리되는 조직 콘텐츠(조직 데이터라고도 하는 원격 지우기)
- 조직 콘텐츠를 비조직 위치에 붙여넣지 못하게 합니다.
- 조직 콘텐츠에 액세스하려면 PIN 필요
- 무단 또는 루팅된 장치에서 관리되는 앱이 실행되지 않도록 방지
- 조직 콘텐츠가 승인되지 않은 클라우드 저장소 공급자에 저장되지 않도록 방지
- 승인되지 않은 콘텐츠가 관리되는 응용 프로그램으로 전송되지 않도록 방지
- 정책이 적용된 후에만 조직 콘텐츠에 대한 액세스 허용
- 응용 프로그램 구성을 전달하여 응용 프로그램의 동작 및 설정 관리
- 다중 ID 기능 또는 개인 사용을 사용 안 하도록 설정하여 관리되는 응용 프로그램을 정의된 ID로 제한

모바일 응용 프로그램을 통해 모바일 응용 프로그램 관리에 Microsoft Intune 앱 관리의 Microsoft Intune [참조하세요.](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>다단계 인증

[MFA(다단계 인증)는 인증 메커니즘에 여러 가지 별도의 증거 조각을 성공적으로 제공한 후에만 사용자에게 액세스 권한을 부여하는 컴퓨터 액세스 제어 방법입니다. 이 메서드는 일반적으로 다음 범주 중 두 개 이상을 사용합니다.

- 지식(알고 있는 정보)
- 소유(보유한 것)
- 본질(있는 것)

클라이언트 및 서비스 앱 지원에 대한 다단계 인증에 대한 자세한 내용은 Microsoft 365 클라이언트 앱 [지원: 다단계](microsoft-365-client-support-multi-factor-authentication.md)인증을 참조하세요.

### <a name="single-sign-on"></a>Single Sign-On

SSO(Single Sign-On)는 사용자가 로그인할 때 보안과 편의성을 Azure Active Directory. Single Sign-On을 사용하면 사용자는 한 계정으로 한 번 로그인하여 조직의 사내 AD DS(Active Directory 도메인 서비스) 도메인 가입 장치, SaaS(Software as a Service) 응용 프로그램 및 웹 응용 프로그램에 액세스합니다.

클라이언트 및 서비스 앱 지원에 대한 Single Sign-On에 대한 자세한 내용은 Microsoft 365 클라이언트 앱 [지원: Single Sign-On을 참조하세요.](microsoft-365-client-support-single-sign-on.md)

## <a name="services-support"></a>서비스 지원

### <a name="modern-authentication"></a>최신 인증

최신 인증을 사용하면 고객이 Office 365 테넌트 관리자를 위해 다음과 같은 특정 인증 요구 사항을 Office 365 수 있습니다.

- 테넌트 및 서비스와의 관리 상호 작용, 응용 프로그램 및 해당 데이터와의 최종 사용자 상호 작용에 대한 다단계 인증 지원
- 조건부 액세스
- SAML 기반 타사 ID 공급자 로그인
- 개인 컴퓨터의 스마트 카드 로그
- 모바일 장치에서 인증서 기반 인증
- 더 이상 기본 인증을 통해 자격 증명을 전송할 필요가 없습니다.

최신 인증 서비스 지원에 대한 자세한 내용은 인증 및 [권한 부여를 참조하세요.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Azure Active Directory 조건부 액세스

Azure Active Directory(Azure AD) 조건부 액세스 규칙을 통해 고객은 장치 준수 또는 네트워크 위치와 같은 특성에 따라 온라인 서비스에 대한 액세스를 제어할 수 있습니다. 다음 솔루션을 사용할 수 있습니다.

- Azure AD 다단계 인증 기반 조건부 액세스
- Azure AD 위치 기반 조건부 액세스
- Azure AD 장치 기반 조건부 액세스

Azure AD 조건부 액세스 규칙은 응용 프로그램마다 적용되고 고객이 다양한 조건에 따라 액세스를 제어할 수 있습니다. MDM(모바일 장치 관리) 또는 [Intune을](/mem/intune/fundamentals/what-is-device-management)사용하여 고객은 조직 장치를 Microsoft 365 관리하기 위해 개인 장치를 등록한 사용자만 액세스할 수 있도록 제한할 수 있어야 합니다. 예를 들어 고객은 다음과 같은 컨트롤을 적용하도록 조건부 액세스 규칙을 구성할 수 있습니다.

- 도메인에 가입되거나 도메인을 준수하는 장치에서만 액세스 허용
- Exchange Online 서비스에 대한 다단계 인증 적용

조건부 액세스에 대한 Azure Active Directory 내용은 [조건부 액세스란?을 참조하세요.](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>TLS 1.2 지원

고객에게 동급 최고의 암호화를 제공하기 위해 Microsoft는 TLS(전송 계층 보안) 버전 1.0 및 1.1에 대한 지원을 중단하고 Office 365 Office 365 GCC.

데이터 보안이 중요하다는 점을 이해하고 있으며 TLS 서비스 사용에 영향을 줄 수 있는 변경 사항에 대해 투명성을 유지할 것을 약속드립니다. 모든 클라이언트-서버 및 브라우저-서버 조합은 TLS 1.2(이상 버전)를 사용하여 모든 클라이언트 서비스에 대한 연결을 Office 365 좋습니다. 특정 클라이언트-서버 및 브라우저-서버 조합을 업데이트해야 할 수 있습니다.

TLS 1.2 지원 및 서비스 지원에 대한 자세한 내용은 Office 365 및 서비스 지원에서 [TLS 1.2](../compliance/prepare-tls-1.2-in-office-365.md)Office 365 GCC.