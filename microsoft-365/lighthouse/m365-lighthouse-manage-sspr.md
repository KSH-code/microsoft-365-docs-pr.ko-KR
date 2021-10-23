---
title: 셀프 서비스 암호 재설정 관리
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 서비스 공급자를 사용하여 MSP(관리 Microsoft 365 Lighthouse)의 경우 셀프 서비스 암호 재설정을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 0444fac94ee4a3037b4387e3ad344b374e6a3f1d
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557245"
---
# <a name="manage-self-service-password-reset"></a>셀프 서비스 암호 재설정 관리

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse 통해 파트너는 Azure AD(Azure Active Directory SSPR(셀프 서비스 암호 재설정)을 관리할 수 있습니다. SSPR을 사용하면 관리자나 지원 센터의 개입이 없는 사용자에게 암호를 변경하거나 다시 설정할 수 있습니다. 사용자의 계정이 잠기거나 암호를 잊어버린 경우 프롬프트에 따라 차단을 해제하고 다시 작업할 수 있습니다. 이 기능을 사용하면 사용자가 장치 또는 응용 프로그램에 로그인할 수 없는 경우 지원 센터 통화 및 생산성 손실이 줄어듭니다.

## <a name="before-you-begin"></a>시작하기 전에

테넌트가 목록에 표시되기 전에 다음 조건을 충족해야 합니다.

- 고객 테넌트에는 각 사용자에 대한 Azure AD Premium 라이선스가 있어야 합니다. SSPR을 지원하는 라이선스에 대한 자세한 내용은 셀프 서비스 암호 재설정에 대한 [Azure Active Directory 요구 사항을 참조하세요.](/azure/active-directory/authentication/concept-sspr-licensing)

- 고객 테넌트는 Lighthouse 내에서 활성화되어야 합니다. 테넌트가 활성 상태인지 확인하는 방법에 대한 자세한 내용은 Microsoft 365 Lighthouse [목록 개요를 참조하세요.](m365-lighthouse-tenant-list-overview.md)

## <a name="view-sspr-tenant-status"></a>SSPR 테넌트 상태 보기

1. Lighthouse의 왼쪽 탐색 창에서 사용자를 **선택합니다.**

2. 암호 **재설정 탭을** 선택합니다.

암호 재설정 탭에서는 권장 설정을 통해 SSPR을 사용하도록 설정한 테넌트, SSPR에 등록하지 않은 사용자 수 및 관리하는 조직 전체에서 SSPR 배포 진행률의 테넌트별 세부적인 분석 정보를 제공합니다.

## <a name="enable-sspr-for-a-tenant"></a>테넌트에 대해 SSPR 사용

1. Lighthouse의 왼쪽 탐색 창에서 사용자를 **선택합니다.**

2. 암호 **재설정 탭을** 선택합니다.

3. 테넌트 목록에서 세부 정보 창을 열 테넌트 를 선택합니다.

4. Azure **AD(Azure AD)로 Azure Active Directory SSPR** Azure Active Directory 선택합니다.

5. Azure AD에서 전체 또는 선택한 사용자에 대해 SSPR을 사용하도록 설정하세요. 자세한 내용은 자습서: 셀프 서비스 암호 재설정을 사용하여 사용자가 계정 잠금을 해제하거나 암호를 [Azure Active Directory 사용을 참조하세요.](/azure/active-directory/authentication/tutorial-enable-sspr)

## <a name="notify-users-to-register-for-sspr"></a>사용자에게 SSPR 등록 알림

1. Lighthouse의 왼쪽 탐색 창에서 사용자를 **선택합니다.**

2. 암호 **재설정 탭을** 선택합니다.

3. 테넌트 목록에서 세부 정보 창을 열 테넌트 를 선택합니다.

4. 알림하려는 사용자를 선택합니다.

5. 메일 **만들기 를 선택합니다.**

Lighthouse는 기본 전자 메일 클라이언트를 열고 SSPR에 등록하기 위한 지침이 있는 전자 메일 메시지를 미리 채우습니다. 선택한 모든 사용자가 BCC 줄에 포함됩니다. 사용자에게 개별적으로 전자 메일을 보내고자 하는 경우 사용자 이름 옆에 있는 전자 메일 아이콘을 선택할 수 있습니다.

다른 전자 메일 계정을 사용하려는 경우 사용자 목록을 파일로 내보낼 수 있습니다. 회사 브랜랜드를 사용하여 사용자 지정할 수 있는 예제 전자 메일 서식 파일을 다운로드할 수도 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[셀프 Azure Active Directory](/azure/active-directory/authentication/howto-sspr-deployment) 암호 재설정 배포 계획(문서)\
[자습서: 사용자가 셀프](/azure/active-directory/authentication/tutorial-enable-sspr) 서비스 암호 재설정(문서)을 사용하여 Azure Active Directory 암호를 다시 설정할 수 있습니다.
[Azure AD에서 SSPR을 사용하도록](https://www.youtube.com/watch?v=rA8TvhNcCvQ) 설정하고 구성하는 방법(비디오)\
[다단계 인증](m365-lighthouse-manage-mfa.md) 관리(문서)
