---
title: 사용자 Microsoft 365 암호 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 사용자 계정 암호를 관리하는 Microsoft 365 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: 85d3c42a7aca977472e44fce63af3968fc8e9705
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221011"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>사용자 Microsoft 365 암호 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

ID 구성에 Microsoft 365 여러 가지 방법으로 사용자 계정 암호를 관리할 수 있습니다. AD [DS(Active](../admin/add-users/index.yml)Directory 도메인 서비스) 또는 Microsoft 365 관리 센터(Azure AD) 관리 센터에서 사용자 계정을 Azure Active Directory 있습니다.

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>사용자 계정 암호를 관리하는 위치 및 방법 계획

사용자 계정을 관리하는 위치 및 방법은 사용자 계정의 ID 모델에 따라 Microsoft 365. 두 모델은 클라우드 전용 및 하이브리드입니다.
  
### <a name="cloud-only"></a>클라우드 전용

다음에서 사용자 계정 암호를 관리합니다.

- [Microsoft 365 관리 센터](../admin/add-users/index.yml)
- Azure AD 관리 센터
    
### <a name="hybrid"></a>하이브리드

하이브리드 ID를 사용하면 암호가 AD DS에 저장됩니다. 따라서 사용자 계정 암호를 관리하려면 사내 AD DS 도구를 사용해야 합니다. Azure AD가 이미 해시된 버전의 해시된 버전을 AD DS에 저장하는 PHS(암호 해시 동기화)를 사용하는 경우에도 사용자와 사용자는 AD DS에서 암호를 관리해야 합니다.

암호 [쓰기 저장을](#pw_writeback)사용하여 사용자는 Azure AD를 통해 AD DS 암호를 변경할 수 있습니다.

## <a name="prevent-bad-passwords"></a>잘못된 암호 방지

모든 사용자가 [Microsoft의 암호 지침](https://www.microsoft.com/research/publication/password-guidance) 을 사용하여 사용자 계정 암호를 만들어야 합니다.

사용자가 쉽게 확인할 수 있는 암호를 만들지 못하도록 하려면 전역 금지 암호 목록과 사용자가 지정한 선택적 사용자 지정 금지 암호 목록을 사용하는 Azure AD 암호 보호를 사용합니다. 예를 들어, 다음과 같이 조직에 맞는 조건을 지정할 수 있습니다.

- 브랜드 이름
- 제품 이름
- 위치(예: 본사)
- 회사 관련 내부 조건
- 특정 회사 의미를 갖는 약어

클라우드 및 사내 [](/azure/active-directory/authentication/concept-password-ban-bad) [AD DS의](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)잘못된 암호를 금지할 수 있습니다.

## <a name="simplify-user-sign-in"></a>사용자 로그인 간소화

Azure AD Seamless Single Sign-On(Azure AD Seamless SSO)는 PHS 및 PTA(Pass-Through Authentication)와 함께 작동하여 사용자가 암호 및 대부분의 경우 사용자 이름을 입력하지 않고도 Azure AD 사용자 계정을 사용하는 서비스에 로그인할 수 있도록 합니다. 이는 사용자의 계정이 Office 365와 같은 클라우드 기반 응용 프로그램에 identity 페더레이션 서버와 같은 추가적인 온 프레미스 구성 요소 필요없이 더 쉽게 액세스할 수 있습니다.

Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다. [Azure AD Seamless SSO 구성 지침](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>AD DS에 대한 암호 업데이트 간소화

암호 쓰기 저장을 사용하면 사용자가 Azure AD를 통해 암호를 다시 설정하도록 허용하고 AD DS로 복제할 수 있습니다. 사용자는 암호를 업데이트하기 위해 자신의 사내 AD DS에 액세스할 필요가 없습니다. 온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 유용합니다.

암호 쓰기 저장은 계정 손상의 높은 위험이 감지된 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 Azure AD ID 보호 기능을 최대한 활용하기 위해 필요합니다.

추가 정보 및 구성 지침은 [암호 쓰기 저장을 지원하는 Azure AD SSPR](/azure/active-directory/active-directory-passwords-writeback)을 참조하세요.

>[!Note]
>가능한 최상의 환경 및 새로운 기능(릴리스될 때)을 유지하도록 최신 버전의 Azure AD Connect로 업그레이드하세요. 자세한 내용은 [Azure AD Connect의 사용자 지정 설치](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)를 참조하세요.
>

## <a name="simplify-password-resets"></a>암호 재설정 간소화

SSPR(셀프 서비스 암호 재설정)을 사용하면 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있습니다. 오용 또는 남용에 대한 경고로 사용자가 시스템에 언제 액세스하는지 추적하는 상세한 보고서와 알림을 사용할 수 있습니다. 암호 [재설정을 배포하려면](#pw_writeback) 먼저 암호 쓰기 저장을 사용하도록 설정해야 합니다.

[암호 재설정을 시작하기 위한 지침](/azure/active-directory/authentication/howto-sspr-deployment)을 참조하십시오.