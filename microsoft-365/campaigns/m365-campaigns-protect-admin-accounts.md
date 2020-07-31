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
description: 관리자 계정을 설정 하 고 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: dc5f72cda0255641d7d2407d266a6ae584560733
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527189"
---
# <a name="protect-your-administrator-accounts"></a>관리자 계정 보호

관리 계정에 상승 된 권한이 제공 되므로 해커 및 사이버 범죄자를 대상으로 하는 것이 중요 합니다. 이 문서에서는 다음에 대해 설명합니다.

- 응급 상황에 대 한 추가 관리자 계정을 설정 하는 방법
- 이러한 계정을 보호 하는 방법
 
Microsoft 365에 등록 하 고 정보를 입력 하면 자동으로 전역 관리자가 됩니다. 전역 관리자는 Microsoft 관리 센터의 사용자 계정 및 기타 모든 설정에 대 한 궁극적인 제어를 제공 하지만, 액세스 수준이 다양 한 다양 한 종류의 관리자 계정을 사용할 수 있습니다. 각 관리자 역할 유형에 대 한 다양 한 액세스 수준에 대 한 자세한 내용은 [관리자 역할](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 정보를 참조 하십시오.


## <a name="create-additional-admin-accounts"></a>추가 관리자 계정 만들기

관리 계정만 관리자에 게 사용 합니다. 관리자는 Office 앱을 정기적으로 사용 하기 위한 별도의 사용자 계정을 가져야 하며, 계정 및 장치를 관리 하는 데 필요한 경우와 다른 관리 기능을 사용 하는 경우에만 관리 계정을 사용할 수 있습니다. 관리자 계정에서 Microsoft 365 라이선스를 제거 하 여 요금을 지불할 필요가 없도록 하는 것도 좋습니다.

다른 신뢰할 수 있는 직원에 게 관리자 액세스 권한을 부여 하려면 하나 이상의 추가 전역 관리자 계정을 설정 하는 것이 좋습니다. 사용자 관리를 위해 별도의 관리자 계정을 만들 수도 있습니다 (이 역할은 **사용자 관리 관리자**라고 함). 자세한 내용은 [관리 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)를 참조 하세요.

추가 관리자 계정을 만들려면 다음을 수행 합니다.

 1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">관리 센터로</a> 이동한 후 왼쪽 탐색 창에서 **사용자** \> **활성 사용자** 를 선택 합니다.

    ![사용자를 선택한 다음 왼쪽 탐색 창에서 활성 사용자를 선택 합니다.](../media/Activeusers.png)

2. **활성 사용자** 페이지에서 페이지 맨 위에 있는 **사용자 추가** 를 선택 하 고 **새 사용자** 패널에서 이름과 기타 정보를 입력 합니다.
3. **역할** 섹션을 확장 하 고 **전역 관리자** 를 선택 하 여이 사용자에 게 전역 관리자 액세스 권한을 부여 합니다. 또한 **사용자 지정 된 관리자** 를 선택 하 고 표시 되는 역할 중 하나를 선택할 수 있습니다.

    대체 전자 메일 **주소** 텍스트 상자에 대체 전자 메일을 입력 합니다. 잠긴 경우이 주소를 사용 하 여 암호 정보를 복구할 수 있습니다. 전역 관리자의 경우에는이 주소로 대금 청구 문도 전송 됩니다.

    ![관리자 역할 선택](../media/adminroles.png)
    
4. **제품 라이선스** 섹션에서 **Microsoft 365 Business** 에 대 한 선택기를 **Off** 로, **제품 라이선스 없이 사용자 만들기** 를 **설정**으로 이동 합니다.

    ![제품 라이선스 선택](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>비상 관리자 계정 만들기

또한 MFA (multi-factor authentication)를 사용 하 여 설정 되지 않은 백업 계정을 만들어야 하 여 실수로 잠금을 해제 하지 않는 경우 (예: 두 번째 확인 형태의 전화가 사용 되지 않는 경우) 이 계정의 암호가 구 또는 16 자 이상 인지 확인 합니다. 이를 "사용이 가능한 계정" 이라고 하는 경우가 많습니다.

## <a name="create-a-user-account-for-yourself"></a>자신을 위한 사용자 계정 만들기

사용자 계정을 사용 하 여 메일 검사를 포함 하 여 조직과 공동 작업에 참여 합니다. 즉, 관리자 자격 증명은 *Chavez <span></span> @Contoso* 와 유사할 수 있으며 일반 사용자 계정은 *alice <span></span> @Contoso*와 비슷할 수 있습니다.

새 사용자 계정을 만들려면 다음을 수행 합니다.
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">관리 센터로</a> 이동한 후 왼쪽 탐색 창에서 **사용자** \> **활성 사용자** 를 선택 합니다.
2. **활성 사용자** 페이지에서 페이지 맨 위에 있는 **사용자 추가** 를 선택 하 고 **새 사용자** 패널에서 이름과 기타 정보를 입력 합니다.
3. **역할** 섹션을 확장 하 고 **사용자 (관리 권한 없음)** 를 선택 합니다.
1. **제품 라이선스** 섹션에서 **Microsoft 365 Business** 에 대 한 선택기를 **설정**으로 이동 합니다. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>각 계정에 다단계 인증을 등록 합니다.


## <a name="additional-recommendations"></a>추가 권장 사항

- 관리 계정도 다단계 인증용으로 설정 해야 합니다. 여기서는 [조건부 액세스 정책 구성](m365-campaigns-conditional-access.md)에서이 작업을 수행 하는 방법을 알아봅니다.
- 관리 계정을 사용 하기 전에 개인 전자 메일 계정을 포함 하 여 관련 없는 브라우저 세션과 앱을 모두 닫으십시오. 전용 또는 incognito 브라우저 창 에서도 사용할 수 있습니다.
- 관리 작업을 완료 한 후에는 브라우저 세션에서 로그 아웃 해야 합니다.
