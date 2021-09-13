---
title: 관리자 계정 보호
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
ms.openlocfilehash: 44b5f9bb07736e06f7e427e521b5c85364091020
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188684"
---
# <a name="protect-your-administrator-accounts"></a>관리자 계정 보호

관리자 계정에는 상승된 권한이 있기 때문에 해커와 사이버 범죄자에 대한 중요한 대상입니다. 이 문서에서는 다음에 대해 설명합니다.

- 긴급에 대한 추가 관리자 계정을 설정하는 방법
- 이러한 계정을 보호하는 방법

등록한 Microsoft 365 정보를 입력하면 자동으로 전역 관리자가 됩니다. 전역 관리자는 Microsoft 관리 센터의 사용자 계정 및 다른 모든 설정을 최종적으로 제어할 수 있지만 액세스 권한이 다양한 다양한 종류의 관리자 계정이 있습니다. 각 [관리자 역할 종류에](/office365/admin/add-users/about-admin-roles) 대한 다양한 액세스 수준에 대한 자세한 내용은 관리자 역할 정보를 참조하세요.

## <a name="create-additional-admin-accounts"></a>추가 관리자 계정 만들기

관리에만 관리자 계정을 사용하세요. 관리자는 앱 앱을 정기적으로 사용하기 위해 별도의 사용자 계정을 Office 계정과 계정 및 장치를 관리하고 다른 관리자 기능을 사용하는 데 필요한 경우만 관리 계정을 사용해야 합니다. 또한 관리자 계정에서 Microsoft 365 라이선스를 제거하여 비용을 지불하지 않는 것이 좋습니다.

하나 이상의 추가 전역 관리자 계정을 설정하여 다른 신뢰할 수 있는 직원에게 관리자 액세스 권한을 부여할 수 있습니다. 사용자 관리를 위한 별도의 관리자 계정을 만들 수도 있습니다(이 역할을 사용자 관리 **관리자라고도 합니다).** 자세한 내용은 관리자 역할 [정보를 참조하세요.](/office365/admin/add-users/about-admin-roles)

추가 관리자 계정을 만들 수 있는 경우:

 1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">센터로 이동한</a> 다음 왼쪽 네비게이트에서 **사용자** \> **활성** 사용자를 선택하세요.

    ![왼쪽에서 사용자를 선택한 다음 활성 사용자를 선택 합니다.](../media/Activeusers.png)

 2. 활성 **사용자 페이지에서** 페이지  맨 위에 있는 사용자 추가를 선택하고  새 사용자 패널에서 이름 및 기타 정보를 입력합니다.
 3. 역할 **섹션을 확장하고** 전역 관리자를 **선택해** 이 사용자에게 전역 관리자 액세스 권한을 부여합니다. 사용자 지정 **관리자를 선택하고** 표시되는 역할을 선택할 수도 있습니다.

    대체 전자 메일 주소 텍스트 **상자에** 대체 전자 메일을 입력합니다. 잠긴 경우 이 주소를 사용하여 암호 정보를 복구할 수 있습니다. 전역 관리자의 경우 청구서도 이 주소로 전송됩니다.

    ![관리자 역할을 선택 합니다.](../media/adminroles.png)

 4. 제품 라이선스 **섹션에서** 비즈니스용 선택기 Microsoft 365 해제로  이동하고 제품 **라이선스가** 없는 사용자 만들기를 **으로** **이동합니다.**

    ![제품 라이선스를 선택하십시오.](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>응급 관리자 계정 만들기

또한 MFA(다단계 인증)로 설정되지 않은 백업 계정을 만들어 실수로 자신을 잠그지 않도록 해야 합니다(예: 두 번째 확인 양식으로 사용하는 휴대폰을 분실하는 경우). 이 계정의 암호가 구 또는 16자 이상인지 확인 이를 "차단 계정"이라고도 합니다.

## <a name="create-a-user-account-for-yourself"></a>자신에 대한 사용자 계정 만들기

사용자 계정을 사용하여 메일 확인을 포함하여 조직과 공동 작업할 수 있습니다. 즉, 관리자 자격 증명이  *Alice.Chavez <span></span> @Contoso.org* 사용자 계정이 *Alice <span></span> @Contoso.com*.

새 사용자 계정을 만들하려면

1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">센터로 이동한</a> 다음 왼쪽 네비게이트에서 **사용자** \> **활성** 사용자를 선택하세요.
2. 활성 **사용자 페이지에서** 페이지  맨 위에 있는 사용자 추가를 선택하고  새 사용자 패널에서 이름 및 기타 정보를 입력합니다.
3. 역할 **섹션을 확장하고** 사용자(관리 액세스 **권한 없음)를 선택하십시오.**
4. 제품 **라이선스 섹션에서** 비즈니스용 선택기 **Microsoft 365 으로** **이동합니다.**

## <a name="turn-on-security-defaults"></a>보안 기본값 켜기

보안 기본값은 Microsoft가 조직을 대신하여 관리하는 미리 구성한 보안 설정을 제공하여 ID 관련 공격으로부터 조직을 보호하는 데 도움이 됩니다. 이러한 설정에는 모든 관리자 및 사용자 계정에 대해 MFA(다단계 인증)를 사용하도록 설정하는 것이 포함됩니다. 보안 기본값에 대한 자세한 내용을 보고 설정하는 방법에 대한 자세한 내용은 보안 기본값 [켜기 을 참조하세요.](m365-campaigns-conditional-access.md)

## <a name="additional-recommendations"></a>추가 권장 사항

- 관리자 계정을 사용하려면 먼저 개인 전자 메일 계정을 포함하여 관련 없는 모든 브라우저 세션 및 앱을 닫습니다. 개인 또는 시그니치 브라우저 창에서 사용할 수도 있습니다.
- 관리 작업을 완료한 후 브라우저 세션에서 로그인해야 합니다.
