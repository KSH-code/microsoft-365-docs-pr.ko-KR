---
title: '계정 사용 중지 '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Microsoft에서 계정을 닫는 방법을 알아봅니다.
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898924"
---
# <a name="close-your-account"></a>계정 사용 중지 

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

Microsoft 계정을 폐쇄하면 계정과 관련된 모든 정보가 삭제됩니다. 이 정보에는 구독, 라이선스, 지불 방법, 사용자 및 사용자 데이터가 포함됩니다. 이 프로세스를 시작 하기 전에 보존 하려는 모든 데이터를 백업 해야 합니다.

## <a name="step-1-delete-users"></a>1 단계: 사용자 삭제

계정을 닫는 단계를 완료 한 전역 관리자를 제외한 모든 사용자를 삭제 합니다. 이 프로세스가 완료 될 때 디렉터리를 삭제 하려면 먼저 다른 모든 사용자를 삭제 해야 합니다.

사용자가 온-프레미스 로부터 동기화 되 면 먼저 동기화를 해제 한 다음 Azure portal 또는 Azure PowerShell cmdlet을 사용 하 여 클라우드 디렉터리의 사용자를 삭제 합니다.

사용자를 삭제 하려면 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">사용자 관리 관리자: 하나 이상의 사용자 삭제</a>를 참조 하십시오.

<a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell cmdlet을 사용 하 여 사용자를 대량으로 삭제할 수도 있습니다.

조직에서 Azure AD와 동기화 되는 Active Directory를 사용 하는 경우 대신 Active Directory에서 사용자 계정을 삭제 합니다. 자세한 내용은 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory에서 사용자 대량 삭제</a>를 참조 하세요.

## <a name="step-2-cancel-all-active-subscriptions"></a>2 단계: 모든 활성 구독 취소

1. 관리 센터에서 **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 청구 페이지로 이동 합니다.

2. 구독 목록이 **표** 보기에 있는 경우 오른쪽에서 **카드**를 선택 합니다.

3. 활성 구독을 찾고 **& 작업 설정** 섹션에서 **구독 취소**를 선택 합니다.

4. 화면의 지시에 따라 프로세스를 완료 합니다.

5. 1 ~ 4 단계를 반복 하 여 모든 활성 구독을 취소 합니다.

## <a name="step-3-delete-all-disabled-subscriptions"></a>3 단계: 사용 하지 않는 구독 모두 삭제

1. 관리 센터에서 **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 청구 페이지로 이동 합니다.

2. 구독 목록이 **표** 보기에 있는 경우 오른쪽에서 **카드**를 선택 합니다.

3. **구독 상태**옆에서 **사용 안 함을**선택 합니다.

4. 사용 하지 않도록 설정 된 구독을 찾은 다음, **& 동작** 섹션에서 **삭제**를 선택 합니다.

5. **구독 삭제** 대화 상자에서 **영향** 확인 확인란을 선택 하 고 **구독 삭제**를 선택 합니다.

6. 사용 하지 않도록 설정 된 각 구독에 대해 4 ~ 5 단계를 반복 하 여 모든 구독을 삭제 합니다.

## <a name="step-4-disable-multi-factor-authentication"></a>4 단계: 다단계 인증 사용 안 함

1. 관리 센터에서 **사용자**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동 합니다.

2. **다단계 인증**을 선택 합니다.

3. Multi-factor authentication 페이지에서 현재 사용 중인 전역 관리자 계정을 제외한 모든 계정을 사용 하지 않도록 설정 합니다.

또한 <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell을 사용 하 여 여러 사용자에 대해 multi-factor authentication을 사용 하지 않도록 설정할</a>수 있습니다.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>5 단계: Azure Active Directory에서 디렉터리 삭제

1. 전역 관리자 계정을 사용 하 여 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 관리 센터</a> 에 로그인 합니다.

2. **Azure Active Directory**를 선택합니다.

3. 삭제 하려는 디렉터리로 전환 합니다.

4. **디렉터리 삭제**를 선택 합니다.

5. 디렉터리에서 하나 이상의 검사가 실패 하면 검사 통과 방법에 대 한 자세한 내용을 확인할 수 있는 링크가 표시 됩니다. 모든 검사를 통과 한 후에 **삭제** 를 선택 하 여 프로세스를 완료 합니다.

마지막 단계를 완료 한 후에는 Microsoft의 계정을 닫고 삭제 합니다.
