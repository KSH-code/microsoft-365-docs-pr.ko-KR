---
title: 관리자 계정 보호
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 관리자 계정을 설정하고 보호하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044491"
---
# <a name="protect-your-administrator-accounts"></a>관리자 계정 보호

관리자 계정에는 높은 권한이 있기 때문에 해커와 사이버 범죄자에 대한 중요한 대상이 됩니다. 이 문서에서는 다음에 대해 설명합니다.

- 긴급에 대한 추가 관리자 계정을 설정하는 방법
- 이러한 계정을 보호하는 방법

Microsoft 365에 등록하고 정보를 입력하면 자동으로 전역 관리자가 됩니다. 전역 관리자는 Microsoft 관리 센터의 사용자 계정 및 다른 모든 설정을 궁극적으로 제어할 수 있지만 액세스 정도가 다양한 다양한 종류의 관리자 계정이 있습니다. 각 [관리자 역할 종류에](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 대한 다양한 액세스 수준에 대한 자세한 내용은 관리자 역할에 대해 참조하세요.

## <a name="create-additional-admin-accounts"></a>추가 관리자 계정 만들기

관리에만 관리자 계정을 사용하세요. 관리자는 Office 앱을 정기적으로 사용하기 위해 별도의 사용자 계정이 있으며 필요한 경우 계정 및 장치를 관리하고 다른 관리자 기능을 사용하는 동안 관리 계정만 사용해야 합니다. 또한 관리자 계정에서 Microsoft 365 라이선스를 제거하여 비용을 지불하지 않는 것이 좋습니다.

하나 이상의 추가 전역 관리자 계정을 설정하여 관리자에게 신뢰할 수 있는 다른 직원에 대한 액세스 권한을 부여할 수 있습니다. 사용자 관리를 위한 별도의 관리자 계정을 만들 수도 있습니다(이 역할을 사용자 관리 **관리자라고도 합니다).** 자세한 내용은 관리자 [역할에 대해 참조하세요.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

추가 관리자 계정을 만들하려면

 1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">센터로 이동한</a> 다음 왼쪽 네비게이트에서 **사용자** \> **활성** 사용자를 선택하세요.

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. 활성 **사용자** 페이지에서 페이지  맨 위에 있는 사용자 추가를 선택하고  새 사용자 패널에서 이름 및 기타 정보를 입력합니다.
 3. 역할 **섹션을** 확장하고  전역 관리자를 선택하면 이 사용자에게 전역 관리자 액세스 권한이 부여됩니다. 사용자 지정된 관리자를 **선택하고** 표시되는 역할을 선택할 수도 있습니다.

    대체 전자 메일 주소 텍스트 **상자에** 대체 전자 메일을 입력합니다. 잠긴 경우 이 주소를 사용하여 암호 정보를 복구할 수 있습니다. 전역 관리자의 경우 청구서도 이 주소로 전송됩니다.

    ![관리자 역할 선택](../media/adminroles.png)

 4. 제품 라이선스 **섹션에서** **Microsoft 365 Business용** 선택기  를  해제로 이동하고 제품 라이선스가 없는 사용자 만들기를 **On으로 하세요.**

    ![제품 라이선스 선택](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>응급 관리자 계정 만들기

또한 MFA(다단계 인증)로 설정되지 않은 백업 계정을 만들어 실수로 잠그지 않도록 해야 합니다(예: 두 번째 인증 형태로 사용하는 휴대폰을 분실하는 경우). 이 계정의 암호가 구 또는 16자 이상인지 확인 이를 "중단 유리 계정"이라고도 합니다.

## <a name="create-a-user-account-for-yourself"></a>자신에 대한 사용자 계정 만들기

사용자 계정을 사용하여 메일 확인을 포함하여 조직과 공동 작업할 수 있습니다. 즉, 관리자 자격 증명은 *Alice.Chavez <span></span> @Contoso.org* 사용자 계정이 *Alice <span></span> @Contoso.com.*

새 사용자 계정을 만들하려면

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">센터로 이동한</a> 다음 왼쪽 네비게이트에서 **사용자** \> **활성** 사용자를 선택하세요.
2. 활성 **사용자** 페이지에서 페이지  맨 위에 있는 사용자 추가를 선택하고  새 사용자 패널에서 이름 및 기타 정보를 입력합니다.
3. 역할 **섹션을** 확장하고 사용자(관리 액세스 **권한 없음)를 선택하십시오.**
4. 제품 라이선스 **섹션에서** **Microsoft 365 Business용** 선택기 를 On으로 **이동합니다.**

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>다단계 인증을 위해 이러한 각 계정 등록

이러한 계정이 다단계 [인증을 사용하고 있는지 확인](m365-campaigns-multifactor-authenication.md)

## <a name="additional-recommendations"></a>추가 권장 사항

- 다단계 인증을 위해 관리자 계정도 설정해야 합니다. 조건부 액세스 정책 구성에서 이 작업을 하는 [방법을 보여 주도록 합니다.](m365-campaigns-conditional-access.md)
- 관리자 계정을 사용하려면 개인 전자 메일 계정을 포함하여 관련 없는 모든 브라우저 세션 및 앱을 닫습니다. 개인 또는 시차 없는 브라우저 창에서 사용할 수도 있습니다.
- 관리 작업을 완료한 후 브라우저 세션에서 로그인해야 합니다.
