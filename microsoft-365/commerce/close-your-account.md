---
title: '계정 사용 중지 '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376320"
---
# <a name="close-your-account"></a>계정 사용 중지 

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end

Microsoft 계정을 폐쇄하면 계정과 관련된 모든 정보가 삭제됩니다. 이 정보에는 구독, 라이선스, 지불 방법, 사용자 및 사용자 데이터가 포함됩니다.

## <a name="before-you-begin"></a>시작하기 전에

이 프로세스를 시작하기 전에 보존하려는 데이터를 백업하세요.

이 문서의 작업을 수행 하려면 전역 또는 대금 청구 관리자 여야 합니다. 자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="step-1-delete-users"></a>1 단계: 사용자 삭제

전역 관리자 한 명을 제외한 모든 사용자를 삭제 합니다. 전역 관리자가 계정을 닫는 단계를 완료 합니다. 이 프로세스가 완료 될 때 디렉터리를 삭제 하려면 먼저 다른 모든 사용자를 삭제 해야 합니다.

사용자가 온-프레미스 로부터 동기화 되 면 먼저 동기화를 해제 한 다음 Azure portal 또는 Azure PowerShell cmdlet을 사용 하 여 클라우드 디렉터리의 사용자를 삭제 합니다.

사용자를 삭제 하려면 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">사용자 관리 관리자: 하나 이상의 사용자 삭제</a>를 참조 하십시오.

<a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell cmdlet을 사용 하 여 사용자를 대량으로 삭제할 수도 있습니다.

조직에서 Microsoft Azure Active Directory (Azure AD)와 동기화 하는 Active Directory를 사용 하는 경우 대신 Active Directory에서 사용자 계정을 삭제 합니다. 자세한 내용은 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Azure Active Directory에서 사용자 대량 삭제</a>를 참조 하세요.

## <a name="step-2-cancel-all-active-subscriptions"></a>2 단계: 모든 활성 구독 취소

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. **제품** 탭에서 활성 구독을 찾습니다. **추가 작업**(점 3개)을 선택한 다음 **구독 취소** 를 선택합니다.
3. **구독 취소** 창에서 취소 이유를 선택합니다. 원하는 경우, 피드백을 제공하세요.
4. **저장** 을 선택합니다.
5. 1 ~ 4 단계를 반복 하 여 모든 활성 구독을 취소 합니다.

## <a name="step-3-delete-all-disabled-subscriptions"></a>3 단계: 사용 하지 않는 구독 모두 삭제

1. 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">제품</a> 페이지로 이동하세요.
2. **제품** 탭에서 사용 하지 않도록 설정 된 구독을 선택 합니다.
3. 구독 정보 페이지의 **구독 및 지불 설정** 섹션에서 **구독 삭제** 를 선택 합니다.
4. **구독 삭제** 창에서 **구독 삭제** 를 선택 합니다.
5. **구독 삭제** 대화 상자에서 **예** 를 선택 합니다.
6. 사용 하지 않도록 설정 된 각 구독에 대해 3 ~ 5 단계를 반복 하 여 모든 구독을 삭제 합니다.

> [!NOTE]
> 사용 하지 않도록 설정 된 구독을 즉시 삭제할 수 없는 경우 <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">지원 서비스에 문의 하세요</a> .

## <a name="step-4-disable-multi-factor-authentication"></a>4 단계: 다단계 인증 사용 안 함

1. 전역 관리자 계정을 사용 하 여 관리 센터에 로그인 합니다. 보유 하 고 있는 역할을 확인 하려면 [조직에서 관리자 역할 확인](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)을 참조 하십시오.
2. **사용자**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동 합니다.
3. **다단계 인증** 을 선택 합니다.
4. Multi-factor authentication 페이지에서 현재 사용 중인 전역 관리자 계정을 제외한 모든 계정을 사용 하지 않도록 설정 합니다.

또한 <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell을 사용 하 여 여러 사용자에 대해 multi-factor authentication을 사용 하지 않도록 설정할</a>수 있습니다.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>5 단계: Azure Active Directory에서 디렉터리 삭제

1. 전역 관리자 계정을 사용 하 여 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 관리 센터</a> 에 로그인 합니다.
2. **Azure Active Directory** 를 선택합니다.
3. 삭제할 조직으로 전환 합니다.
4. **테 넌 트 삭제** 를 선택 합니다.
5. 조직에서 하나 이상의 검사에 실패 하면 검사 통과 방법에 대 한 자세한 내용을 확인할 수 있는 링크가 표시 됩니다. 모든 검사를 통과 한 후에 **삭제** 를 선택 하 여 프로세스를 완료 합니다.

마지막 단계를 완료 한 후에는 Microsoft의 계정을 닫고 삭제 합니다.