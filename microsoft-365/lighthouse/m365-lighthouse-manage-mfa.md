---
title: 다단계 인증 관리
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
description: 서비스를 사용하여 MSP(관리되는 서비스 공급자)Microsoft 365 Lighthouse 다단계 인증을 관리하는 방법을 알아보아야 합니다.
ms.openlocfilehash: 4587dffbe45eacaf62c49d0c84aeef86455980e1
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557281"
---
# <a name="manage-multifactor-authentication"></a>다단계 인증 관리

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Azure Active Directory(Azure AD) 다단계 인증(MFA)을 사용하면 데이터 및 응용 프로그램에 대한 액세스를 보호하여 두 번째 인증 형식을 사용하여 다른 보안 계층을 제공합니다. 다단계 인증 탭에서는 테넌트 전체의 MFA 사용 상태에 대한 자세한 정보를 제공합니다. MFA를 요구하는 조건부 액세스 정책과 아직 MFA에 등록되지 않은 사용자를 포함하여 해당 테넌트에 대한 자세한 내용을 확인하려면 목록에서 테넌트를 선택합니다.

SMB(중소기업) 고객의 경우 최소한 보안 기본값을 사용하도록 [설정하는](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 것이 좋습니다. 더 복잡한 시나리오의 경우 조건부 [액세스를](/azure/active-directory/conditional-access/overview) 사용하여 특정 정책을 구성할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

테넌트가 목록에 표시되기 전에 다음 조건을 충족해야 합니다.

- 고객 테넌트에는 각 사용자에 대한 Azure AD Premium 라이선스가 있어야 합니다. MFA를 지원하는 라이선스에 대한 자세한 내용은 Azure AD 다단계 인증에 대한 기능 및 [라이선스를 참조하세요.](/azure/active-directory/authentication/concept-mfa-licensing)

- 고객 테넌트는 고객 테넌트 내에서 활성 상태 Microsoft 365 Lighthouse. 테넌트가 활성 상태인지 확인하는 방법에 대한 자세한 내용은 Microsoft 365 Lighthouse [목록 개요를 참조하세요.](/microsoft-365/lighthouse/m365-lighthouse-tenant-list-overview)

## <a name="enable-mfa-for-a-tenant"></a>테넌트에 대해 MFA 사용

1. Lighthouse의 왼쪽 탐색 창에서 사용자를 **선택합니다.**

2. 다단계 **인증 탭을** 선택합니다.

3. 테넌트 목록에서 세부 정보 창을 열 테넌트를 선택합니다.

4. **MFA 사용 설정 탭의** **보안 기본값이 있는 MFA에서** 보안 기본값 **사용 을 선택합니다.**

5. **변경 사항 저장** 을 선택합니다.

조건부 액세스를 통해 MFA를 사용하도록 설정하려면 자습서: Azure AD 다단계 인증을 사용하여 사용자 로그인 이벤트 [보호를 참조하세요.](/azure/active-directory/authentication/tutorial-enable-azure-mfa)

## <a name="notify-users-who-arent-registered-for-mfa"></a>MFA에 등록되지 않은 사용자에게 알림

1. Lighthouse의 왼쪽 창에서 사용자를 **선택합니다.**

2. 다단계 **인증 탭을** 선택합니다.

3. 테넌트 목록에서 세부 정보 창을 열 테넌트를 선택합니다.

4. **MFA에 등록되지 않은** 사용자 탭에서 알릴 사용자를 선택합니다.

5. 메일 **만들기 를 선택합니다.**

Lighthouse는 기본 전자 메일 클라이언트를 열고 MFA에 등록하기 위한 지침이 있는 전자 메일 메시지를 미리 채우습니다. 선택한 모든 사용자가 BCC 줄에 포함됩니다. 사용자에게 개별적으로 전자 메일을 보내고자 하는 경우 사용자 이름 옆에 있는 전자 메일 아이콘을 선택할 수 있습니다.

다른 전자 메일 계정을 사용하려는 경우 사용자 목록을 파일로 내보낼 수 있습니다. 회사 브랜랜드를 사용하여 사용자 지정할 수 있는 예제 전자 메일 서식 파일을 다운로드할 수도 있습니다.

## <a name="next-steps"></a>다음 단계

MFA를 사용하도록 설정한 후 Azure AD(Azure Active Directory 서비스 암호 재설정)를 사용하도록 설정할 수 있습니다. 이 기능을 사용하면 관리자나 지원 센터의 개입이 없는 사용자 암호를 변경하거나 다시 설정할 수 있습니다. 자세한 내용은 셀프 서비스 암호 재설정 [관리를 참조하세요.](m365-lighthouse-manage-sspr.md)

## <a name="related-content"></a>관련 콘텐츠

[다중 Azure Active Directory](/azure/active-directory/authentication/howto-mfa-getstarted) 배포 계획(문서)\
[보안 기본값이란?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) (기사)\
[조건부 액세스란?](/azure/active-directory/conditional-access/overview) (기사)\
[사용자 단위 MFA에서](/azure/active-directory/authentication/howto-mfa-getstarted#convert-users-from-per-user-mfa-to-conditional-access-based-mfa) 조건부 액세스로 사용자를 변환하는 방법 학습(문서)
