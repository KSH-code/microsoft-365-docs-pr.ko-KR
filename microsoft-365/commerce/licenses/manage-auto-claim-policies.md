---
title: 자동 클레임 정책 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.review: yinggiy, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
description: 특정 앱에 대한 라이선스를 사용자에게 자동으로 할당하는 자동 클레임 정책을 만들고 관리하는 방법을 학습합니다.
search.appverid: MET150
ms.date: 04/06/2021
ms.openlocfilehash: 28d05e0e3b1d1e8692672bf741a612ebee02e39f
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753496"
---
# <a name="manage-auto-claim-policies"></a>자동 클레임 정책 관리

자동 클레임 정책을 사용하면 사용자가 앱에 처음 로그인할 때 제품에 대한 라이선스를 자동으로 클레임할 수 있습니다. 관리자는 일반적으로 수동으로 또는 그룹 기반 라이선싱을 사용하여 사용자에게 라이선스를 할당합니다. 자동 클레임 정책을 사용하면 사용자가 라이선스를 자동으로 클레임할 수 있는 제품을 관리합니다. 또한 해당 라이선스가 시작되는 제품을 제어할 수 있습니다.

자동 클레임 정책을 만든 후 다음 작업을 수행하여 정책을 관리할 수 있습니다.

- [정책 켜기 또는 끄기](#turn-a-policy-on-or-off)
- [정책 이름 편집](#edit-the-policy-friendly-name)
- [백업 제품 추가 또는 제거](#add-or-remove-backup-products)
- [할당 앱 및 서비스 관리](#change-the-assigning-apps-and-services)
- [할당 순서 변경](#change-the-assigning-order-for-backup-products)
- [정책 보고서 보기](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> 자동 클레임 정책은 현재 해당 정책에 대해 Microsoft Teams. 향후에 더 많은 제품을 사용할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

자동 클레임 정책을 만들고 관리하려면 전역, 사용자 또는 라이선스 관리자 되어야 합니다. 자세한 내용은 [Microsoft 365 관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>자동 클레임 정책 기능 켜기 또는 끄기

기본적으로 자동 클레임 정책 기능은 꺼져 있습니다. 기능을 사용하려면 먼저 켜야 합니다. 기능을 켜고 나면 자동 클레임 정책을 만들 수 있습니다.

### <a name="turn-on-auto-claim-policies"></a>자동 클레임 정책 켜기

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 페이지 가운데에서 설정 **켜기 단추를** 선택합니다.

### <a name="turn-off-auto-claim-policies"></a>자동 클레임 정책 끄기

전역 관리자만 자동 클레임 정책 설정을 해제할 수 있습니다.

1. 관리 센터에서 설정  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">설정 페이지로</a> 이동합니다.
2. 표 아래쪽에서 사용자 소유 앱 및 **서비스를 선택합니다.**
3. 오른쪽 창에서 사용자가 처음 로그인할 때 라이선스를 자동 클레임할 수 있도록 합니다. 상자의 **선택을 취소합니다.**

이미 활성 정책이 있지만 더 이상 사용자가 라이선스를 클레임하지 못하게 하려는 경우 [정책을 해제합니다.](#turn-a-policy-on-or-off) 자동 클레임 정책을 끄면 더 이상 사용자가 해당 시점부터 라이선스를 클레임할 수 없습니다. 이미 라이선스를 요구한 사용자는 라이선스를 잃지 않습니다.

## <a name="create-an-auto-claim-policy"></a>자동 클레임 정책 만들기

자동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">클레임 정책</a> 탭에는 만든 정책이 나열됩니다. 이 탭에서 정책의 이름, 정책과 연결된 앱, 정책에 할당된 제품, 사용 가능한 라이선스 수 및 정책 상태를 확인할 수 있습니다.

자동 클레임 정책을 만들 때 백업 제품을 추가할 수 있습니다. 기본 제품이 라이선스가 부재 중이면 백업 제품을 사용하여 사용자에게 라이선스를 할당합니다. 최대 4개의 백업 제품을 추가하고 백업 제품을 사용하는 순서를 [변경할 수 있습니다.](#change-the-assigning-order-for-backup-products) 자세한 내용은 백업 제품 [추가 또는 제거를 참조합니다.](#add-or-remove-backup-products)

> [!NOTE]
> 현재는 자동 클레임 정책을 하나만 만들 수 있습니다. 더 많은 제품이 이 기능을 사용할 수 있게 수록 만들 수 있는 정책의 수가 증가합니다.

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 정책 **추가를 선택합니다.**
3. 이 **자동 클레임** 정책 이름 지정 페이지에서 정책의 이름을 입력하고 다음 을 **선택합니다.**
4. 자동 **클레임** 앱 및 제품 설정 페이지에서 라이선스를 할당할 앱 및 구독을 선택합니다.
5. 백업 제품을 추가하려면 이 정책에 백업 제품 추가를 선택한 다음 목록에서 제품을 선택합니다. 
6. **다음** 을 선택합니다.
7. 앱 **선택 페이지에서** 제외하거나 라이선스에 포함할 앱의 상자를 선택 취소하거나 선택한 후 다음 을 **선택합니다.**
8. 백업 제품을 하나 이상 추가한 경우 각 제품에 대해 7단계를 반복합니다. 그렇지 않으면 9단계로 이동해야 합니다.
9. 검토 **및 완료 페이지에서** 새 정책 정보를 확인하고 필요한 사항을 변경한 다음 정책 만들기 **를 선택합니다.**
10. **닫기** 를 선택합니다.

## <a name="turn-a-policy-on-or-off"></a>정책 켜기 또는 끄기

정책을 해제하면 더 이상 사용자가 해당 정책에 따라 라이선스를 클레임할 수 없습니다. 이 변경은 해당 정책에 따라 라이선스를 이미 클레임한 사용자에게는 영향을 주지 않습니다.

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 편집할 정책을 선택합니다.
3. 세부 정보 창의 이 정책을 켜거나 끄기에서 확인란을 선택하거나 선택을 취소합니다.
4. **저장을** 선택하여 세부 정보 창을 닫습니다.

## <a name="edit-the-policy-friendly-name"></a>정책 이름 편집

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 편집할 정책을 선택합니다.
3. 세부 정보 창의 정책 **이름 섹션에서** 편집 을 **선택합니다.**
4. 새 정책 이름을 입력한 다음 저장 을 **선택합니다.**
5. **저장을** 선택하여 세부 정보 창을 닫습니다.

## <a name="add-or-remove-backup-products"></a>백업 제품 추가 또는 제거

정책을 만들 때 제품에 제품을 추가합니다. 그러면 해당 라이선스 풀의 사용자에게 라이선스가 자동으로 할당됩니다. 자동 클레임 정책에 대한 제품을 추가하거나 제거할 수 있습니다. 정책과 연결된 제품이 하나 이미 있는 경우 추가하는 제품은 백업 제품으로 간주됩니다. 첫 번째 제품의 사용 가능한 라이선스 수를 사용하는 경우 정책은 목록의 다음 백업 제품을 사용하여 라이선스를 할당합니다. 원하는 경우 제품 목록의 다시 [오더를 할](#change-the-assigning-apps-and-services) 수 있습니다.

백업 제품을 제거하면 라이선스를 할당하는 데 더 이상 사용이 안 됩니다. 기존 라이선스가 있는 사용자는 해당 라이선스를 계속 사용하지만 새 사용자는 해당 제품에 대한 라이선스를 받을 수 없습니다.

> [!NOTE]
> 자동 클레임 정책에는 제품이 하나 이상 포함되어야 합니다. 정책에서 모든 제품을 제거할 수 없습니다. 더 이상 특정 자동 클레임 정책에서 라이선스를 할당하지 않는 경우 [정책을 해제합니다.](#view-an-auto-claim-policy-report)

### <a name="add-a-backup-product"></a>백업 제품 추가

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 편집할 정책을 선택합니다.
3. 세부 정보 창의 아래쪽에서 이 정책에 백업 **제품 추가를 선택합니다.**
    > [!NOTE]
    > 이 링크가 없는 경우 계정과 연결된 제품이 하나뿐이기 때문에 이 링크가 표시됩니다.
4. 제품 **추가 창에서** 드롭다운을 사용하여 정책에 추가할 제품을 선택한 다음 추가를 **선택합니다.**
5. **저장을** 선택하여 세부 정보 창을 닫습니다.

### <a name="remove-a-backup-product"></a>백업 제품 제거

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 편집할 정책을 선택합니다.
3. 세부 정보 창의 아래쪽에서 제품 **제거를 선택합니다.**
4. 정책에서 제품 제거 **창에서** 제거할 정책의 상자를 선택한 다음 저장을 **선택합니다.**
5. 세부 정보 창을 닫습니다.

## <a name="change-the-assigning-apps-and-services"></a>할당 앱 및 서비스 변경

각 제품에는 앱 및 서비스 모음이 연결되어 있습니다. 자동 클레임 정책의 각 제품에 대해 사용자에게 해당 제품에 대한 라이선스가 자동으로 할당될 때 포함할 앱 및 서비스를 지정할 수 있습니다.

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 편집할 정책을 선택합니다.
3. 세부 정보 창의 앱 및 서비스 **에서** 편집 을 **선택합니다.**
4. 앱 **및 서비스 창의** 제품  드롭다운에서 단일 제품을 선택하거나 모든 제품을 **선택합니다.**
5. 사용자가 액세스할 수 있도록 할 앱 및 서비스에 대한 확인란을 선택하거나 선택을 취소합니다.
6. 완료되면 저장을 선택한 다음 세부 정보 창을 닫습니다.

## <a name="change-the-assigning-order-for-backup-products"></a>백업 제품의 할당 순서 변경

정책에 할당된 백업 제품이 있는 경우 사용자가 앱에 로그인할 때 라이선스를 할당하는 데 사용되는 순서를 변경할 수 있습니다.

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 편집할 정책을 선택합니다.
3. 세부 정보 창의 제품  라이선스 섹션에서 이동할 제품 옆의 상자를 선택한 다음 아래로  이동 또는 아래로 **이동을 선택합니다.**
4. 다시 오더할 각 제품에 대해 3단계를 반복합니다.
5. 제품 재배치가 끝나면 저장을 선택하여 세부  정보 창을 닫습니다.

## <a name="view-an-auto-claim-policy-report"></a>자동 클레임 정책 보고서 보기

1. 관리 센터에서 청구 라이선스  페이지로 이동한 다음 자동 클레임 정책 \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">탭을</a> 선택합니다.
2. 보고서 **보기 를 선택합니다.** 자동 **클레임 정책 보고서 페이지에** 지난 90일 동안 각 정책에서 할당된 모든 라이선스가 나열됩니다. 기본적으로 페이지에 지난 90일이 표시됩니다.
3. 표시된 기간을 변경하려면 지난 **30일** 드롭다운 목록을 선택합니다. 지난 1, 7, 30 및 90 일에 대 한 보고서를 볼 수 있습니다.

## <a name="next-steps"></a>다음 단계

주기적으로 자동 클레임  정책 탭으로 돌아가서 만든 정책에 따라 라이선스가 클레임된 사용자 목록을 볼 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[사용자에게 라이선스 할당](../../admin/manage/assign-licenses-to-users.md)(문서)\
[구독 라이선스 구입 또는](buy-licenses.md) 제거(문서)\
[구독 및 라이선스](subscriptions-and-licenses.md) 이해(문서)
