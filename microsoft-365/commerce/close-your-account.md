---
title: '계정 사용 중지 '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
- AdminTemplateSet
search.appverid: MET150
description: Microsoft 계정을 닫을 때 라이선스, 사용자 및 사용자 데이터를 포함하여 계정과 관련된 모든 정보가 삭제됩니다.
ms.date: 04/02/2021
ms.openlocfilehash: b19328ffaf785479b81d6253c602c8f80fca99ae
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202024"
---
# <a name="close-your-account"></a>계정 사용 중지 

Microsoft 계정을 폐쇄하면 계정과 관련된 모든 정보가 삭제됩니다. 이 정보에는 구독, 라이선스, 지불 방법, 사용자 및 사용자 데이터가 포함됩니다.

## <a name="before-you-begin"></a>시작하기 전에

이 프로세스를 시작하기 전에 보존하려는 데이터를 백업하세요.

이 문서의 작업을 수행하려면 전역 관리자 또는 청구 관리자여야 합니다. 자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="step-1-delete-users"></a>1단계: 사용자 삭제

전역 관리자 한 명을 제외한 모든 사용자를 삭제합니다. 전역 관리자가 계정을 닫는 단계를 완료합니다. 이 프로세스가 끝나면 디렉터리를 삭제하려면 먼저 다른 모든 사용자를 삭제해야 합니다.

사용자가 오프-프레미스에서 동기화되는 경우 먼저 동기화를 해제한 다음 Azure Portal 또는 Azure PowerShell cmdlet을 사용하여 클라우드 디렉터리의 사용자를 삭제합니다.

사용자를 삭제하려면 사용자 관리 관리자: 하나 이상의 사용자 [삭제를 참조하세요.](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)

[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet을 사용하여 사용자를 대량으로 삭제할 수도 있습니다.

조직에서 Azure AD(Active Directory)와 동기화되는 Active Directory를 Microsoft Azure Active Directory Active Directory에서 사용자 계정을 삭제합니다. 자세한 내용은 [에서 사용자 일괄 삭제를 Azure Active Directory.](/azure/active-directory/users-groups-roles/users-bulk-delete)

## <a name="step-2-cancel-all-active-subscriptions"></a>2단계: 활성 구독 모두 취소

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. 제품 **탭에서** 활성 구독을 찾을 수 있습니다. 점 3개(추가 작업)를 선택한 다음 **구독 취소** 를 선택합니다.
3. **구독 취소** 창에서 취소 이유를 선택합니다. 또는 피드백을 입력합니다.
4. **저장** 을 선택합니다.
5. 활성 구독을 모두 취소하려면 1~4단계를 반복합니다.

## <a name="step-3-delete-all-disabled-subscriptions"></a>3단계: 사용하지 않도록 설정한 모든 구독 삭제

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. 제품 **탭에서** 비활성화된 구독을 선택합니다.
3. 구독 세부 정보 페이지의 구독 및 결제 설정 **섹션에서** 구독 **삭제를 선택합니다.**
4. 구독 **삭제 창에서** 구독 **삭제를 선택합니다.**
5. 구독 **삭제 대화** 상자에서 예를 **선택합니다.**
6. 사용하지 않도록 설정한 각 구독에 대해 모든 구독이 삭제될 때까지 3-5단계를 반복합니다.

> [!NOTE]
> 사용하지 않도록 설정한 구독을 즉시 삭제할 수 없는 경우 고객 [지원에 문의하세요.](../business-video/get-help-support.md)

## <a name="step-4-disable-multi-factor-authentication"></a>4단계: 다단계 인증 사용 안 하도록 설정

1. 전역 관리자 계정으로 관리 센터에 로그인합니다. 역할이 있는지 확인하려면 [조직에서 관리자 역할 확인을 참조하세요.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)
2. 사용자 활성 **사용자**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">페이지로</a> 이동합니다.
3. 다단계 **인증 을 선택 합니다.**
4. 다단계 인증 페이지에서 현재 사용 중인 전역 관리자 계정을 제외한 모든 계정을 사용하지 않도록 설정합니다.

PowerShell을 사용하여 여러 사용자에 대해 [다단계 인증을](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)사용하지 않도록 설정할 수도 있습니다.


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>5단계: 2단계에서 디렉터리 Azure Active Directory

1. 전역 관리자 계정으로 <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> 관리 센터에 로그인합니다.
2. **Azure Active Directory** 를 선택합니다.
3. 삭제할 조직으로 전환합니다.
4. **테넌트 삭제를 선택합니다.**
5. 조직에서 하나 이상의 검사에 실패하면 검사를 통과하는 방법에 대한 추가 정보 링크가 표시됩니다. 모든 검사를 통과한 후 삭제를 **선택하여** 프로세스를 완료합니다.

이 마지막 단계를 완료하면 Microsoft 계정이 닫히고 삭제됩니다.

## <a name="related-content"></a>관련 콘텐츠 

[비즈니스용 Microsoft 365 청구서](./billing-and-payments/understand-your-invoice2.md) 또는 송장 이해(문서)\
[구독 취소(문서)](./subscriptions/cancel-your-subscription.md)

