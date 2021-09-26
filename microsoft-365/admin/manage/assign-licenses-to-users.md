---
title: 사용자에게 라이선스 할당
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: 제품 라이선스를 특정 사용자에게 할당할지 아니면 사용자 라이선스를 특정 제품에 할당할지 여부에 따라 라이선스를 할당합니다.
ms.date: 09/16/2021
ms.openlocfilehash: b9fb8a670b649437a894619369731a5085c36804
ms.sourcegitcommit: 24bff8a546491ff32ebf04d1f51abb3197035706
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59785942"
---
# <a name="assign-licenses-to-users"></a>사용자에게 라이선스 할당

**활성 사용자** 페이지 또는 **라이선스** 페이지에서 사용자에게 라이선스를 할당할 수 있습니다. 제품 라이선스를 특정 사용자에게 할당할지 아니면 사용자 라이선스를 특정 제품에 할당할지 여부에 따라 사용하는 방법이 다릅니다.

> [!NOTE]
> 
> - 관리자는 조직의 사용자가 구입한 셀프 서비스 구매 구독의 라이선스를 할당하거나 할당 취소할 수 없습니다. [셀프 서비스 구매 구독을 이어 받은 다음](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)할당 또는 할당 취소할 수 있습니다.
> - 일부 구독의 경우 구독을 구입하거나 갱신한 후 제한된 기간 동안만 취소할 수 있습니다. 취소 기간이 지난 경우 되풀이 청구를 해제하여 기간이 끝날 때 구독을 취소합니다.

[사용자를 추가하는 동시에 라이선스를 할당하는 방법에 대해 알아봅니다.](../add-users/add-users.md)

## <a name="before-you-begin"></a>시작하기 전에 다음의 조건을 만족해야 합니다.

- 라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자여야 합니다. 자세한 내용은 [Microsoft 365 관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.
- [PowerShell을 사용하여 사용자 계정에 Microsoft 365 라이선스를 할당](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)할 수 있습니다.
- 그룹 기반 라이선싱을 사용하려면 [Azure Active Directory에서 그룹 구성원으로 사용자에게 라이선스 할당](/azure/active-directory/users-groups-roles/licensing-groups-assign)을 참조하세요.
- Sway와 같은 일부 서비스는 사용자에게 자동으로 할당되므로 개별적으로 할당할 필요가 없습니다.


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>라이선스 페이지를 사용하여 사용자에게 라이선스 할당

**라이선스** 페이지를 사용하여 라이선스를 할당하는 경우 특정 제품에 대한 라이선스를 최대 20명의 사용자에게 할당합니다. **라이선스** 페이지에는 구독하고 있는 모든 제품이 목록에 표시됩니다. 각 제품에 대한 총 라이선스 수, 할당된 라이선스 수 및 사용할 수 있는 라이선스 수를 확인할 수도 있습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

2. 제품을 선택합니다.

3. 제품 세부 정보 페이지에서 **라이선스 할당** 을 선택합니다.

4. **사용자에게 라이선스 할당** 창에서 이름을 입력한 다음 결과에서 해당 이름을 선택하여 목록에 추가합니다. 한 번에 최대 20명의 사용자를 추가할 수 있습니다.

4. **앱 및 서비스를 설정 또는 해제** 를 선택하여 특정 항목에 대한 액세스 권한을 할당하거나 제거합니다.

6. 작업을 마치면 **할당** 을 선택한 다음 **닫기** 를 선택합니다.

충돌이 발생한 경우 메시지가 표시되고 문제 및 수정 방법에 대해 알 수 있습니다. 예를 들어 충돌하는 서비스를 포함하는 라이선스를 선택한 경우 각 라이선스에 포함된 서비스를 검토하라는 오류 메시지가 표시되고 다시 시도합니다.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>사용자가 액세스할 수 있는 앱 및 서비스의 변경

::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">라이선스</a> 페이지로 이동합니다.

::: moniker-end

2. **라이선스** 페이지에서 특정 사용자에 대한 행을 선택합니다.

3. 오른쪽 창에서 액세스 권한을 부여 또는 제거할 앱과 서비스를 선택하거나 선택 취소합니다.

4. 작업을 마치면 **저장** 을 선택한 다음 **닫기** 를 선택합니다.

## <a name="use-the-active-users-page-to-assign-licenses"></a>활성 사용자 페이지를 사용하여 라이선스 할당

**활성 사용자** 페이지를 사용하여 라이선스를 할당할 때 사용자에게 제품에 대한 라이선스를 할당합니다.

### <a name="assign-licenses-to-multiple-users"></a>여러 사용자에게 라이선스 할당

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

::: moniker-end

2. 라이선스를 할당하려는 사용자의 이름 옆에 원을 선택합니다.

3. 맨 위에 있는 **제품 라이선스 관리** 를 선택합니다.

4. **제품 라이선스 관리** 창에서 **추가 할당: 기존 라이선스를 유지하고 추가 항목 할당** \>**다음** 을 선택합니다.

5. **라이선스** 에서 선택한 사용자에게 부여할 라이선스 상자를 선택합니다.\
    기본적으로 해당 라이선스와 연결된 모든 서비스가 사용자에게 자동으로 할당됩니다. 사용자가 이용할 수 있는 서비스를 제한할 수 있습니다. 사용자에게 부여하지 않으려는 서비스의 상자를 선택 취소합니다.

6. 창 아래쪽에서 **변경 내용 저장** 을 선택합니다.  
    모든 사용자에게 충분한 라이선스가 없는 경우 추가 라이선스를 구입해야 할 수 있습니다.

> [!NOTE]
> 많은 수의 사용자에게 라이선스를 할당하려는 경우 [Azure Active Directory에서 그룹 구성원으로 사용자에게 라이선스 할당](/azure/active-directory/enterprise-users/licensing-groups-assign)을 사용하세요.

### <a name="assign-licenses-to-one-user"></a>한 명의 사용자에게 라이선스 할당

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

2. 라이선스를 할당하려는 사용자의 행을 선택합니다.

3. 오른쪽 창에서 **라이선스 및 앱** 를 선택합니다.

4. **라이선스** 섹션을 확장하고 할당하려는 라이선스의 확인란을 선택한 다음 **변경 내용 저장** 을 선택합니다.

## <a name="assign-a-license-to-a-guest-user"></a>게스트 사용자에게 라이선스를 할당

Azure Active Directory 관리 센터에서 게스트 사용자를 조직과 공동 작업하도록 초대할 수 있습니다. 게스트 사용자에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란 무엇인가요?](/azure/active-directory/external-identities/what-is-b2b)를 참조하세요. 게스트 사용자가 없는 경우 [빠른 시작: Azure portal에서 디렉터리에 게스트 사용자 추가](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)를 참조하세요.

> [!IMPORTANT]
> 다음 단계를 수행하려면 전역 관리자여야 합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 관리 센터</a>로 이동합니다.

2. 탐색 창에서 **사용자** 를 선택합니다.

3. **사용자 | 모든 사용자(미리 보기)** 페이지에서 **필터 추가** 를 선택합니다.

4. **필드 선택** 메뉴에서 **사용자 유형** 을 선택한 다음 **적용** 을 선택합니다.

5. 다음 메뉴에서 **게스트** 를 선택합니다.

6. 결과 목록에서 라이선스가 필요한 사용자를 선택합니다.

7. **관리** 에서 **라이선스** 를 선택합니다.

8. **과제** 를 선택합니다.

9. **라이선스 할당 업데이트** 페이지에서 라이선스를 할당하려는 제품을 선택합니다.

10. 오른쪽에서 게스트 사용자가 액세스하지 않을 서비스에 대한 확인란의 선택을 취소합니다.

11. **저장** 을 선택합니다.

## <a name="next-steps"></a>다음 단계

사용자가 아직 Office 앱을 설치하지 않은 경우 [직원 빠른 시작 가이드](../../business-video/employee-quick-setup.md)를 사용자와 공유하여 [PC 또는 Mac에서 Microsoft 365 또는 Office 2019를 다운로드하고 설치하는 방법](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 및 [모바일 장치에서 Office 앱 및 전자 메일을 설정하는 방법](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)과 같은 항목을 설정할 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[구독 및 라이선스 이해](../../commerce/licenses/subscriptions-and-licenses.md) (문서)\
[사용자의 라이선스 할당 취소](remove-licenses-from-users.md) (문서)\
[구독에 대한 라이선스 구입 또는 제거](../../commerce/licenses/buy-licenses.md) (문서)
