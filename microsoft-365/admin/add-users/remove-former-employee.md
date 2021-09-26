---
title: 이전 직원 제거 - 개요
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 이 솔루션의 단계에 따라 이전 직원을 제거하고 Microsoft 365 데이터를 보호합니다.
ms.openlocfilehash: ef89160f52c03bfe92a48b5432e3fdad700b1b40
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775351"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>개요: 이전 직원 및 보안 데이터 제거

자주 묻는 질문은 "직원이 퇴사할 때 데이터를 보호하고 액세스를 보호하기 위해 어떻게 해야 나요?"입니다. 이 문서 시리즈에서는 이러한 사용자가 Microsoft 365 로그인할 수 없는 Microsoft 365, 조직 데이터를 보호하기 위해 취해야 하는 단계 및 다른 직원이 전자 메일 및 전자 메일 데이터에 액세스하도록 허용하는 OneDrive 설명되어 있습니다.

## <a name="before-you-begin"></a>시작하기 전에 다음의 조건을 만족해야 합니다.

이 솔루션의 단계를 완료하려면 전역 관리자로 설정해야 합니다.

이 시리즈의 단계를 완료하기 위해 이러한 Microsoft 365 기능을 사용하세요.

|제품 또는 구성 요소|기능 또는 특징|
|---|---|
|Microsoft 365 관리 센터|사서함 변환, 전자 메일 전달, 액세스 해지, 사용자 제거 |
|Exchange 관리 센터|사용자 차단, 전자 메일에 대한 액세스 차단, 장치 지우기 |
|OneDrive 및 SharePoint |다른 사용자에게 액세스 권한을 부여합니다. |
|Outlook|pst 파일 가져오기, 사서함 추가 |
|PowerShell 연결|하이브리드 환경에서 사용자 제거 |

## <a name="solution-remove-a-former-employee"></a>해결 방법: 이전 직원 제거

> [!IMPORTANT]
> 이 솔루션의 단계에 번호를 매기며 정확한 순서를 사용하여 솔루션을 완료할 것은 아니어도 됩니다. 이러한 방식으로 단계를 수행해보는 것이 좋습니다.

:::image type="content" source="../../media/delete-user-account.png" alt-text="Screenshot: Steps for removing a former employee from your organization":::

<br>

****

|단계|이렇게 하는 이유|
|---|---|
|[1단계 - 이전 직원이 로그인하지 못하게 방지하고 Microsoft 365 액세스 차단](remove-former-employee-step-1.md)|이렇게 하면 이전 직원이 로그인하지 못하고 Microsoft 365 액세스하지 못하게 Microsoft 365 있습니다.|
|[2단계 - 이전 직원 사서함의 내용 저장](remove-former-employee-step-2.md)|이 기능은 직원의 작업을 인계할 사람이나 소송이 있는 경우 유용합니다.|
|[3단계 - 이전 직원의 전자 메일을 다른 직원에게 전달하거나 공유 사서함으로 변환](remove-former-employee-step-3.md)|이렇게 하면 이전 직원의 전자 메일 주소를 활성 상태로 유지할 수 있습니다. 이전 직원의 주소로 여전히 전자 메일을 보내는 고객 또는 파트너가 있는 경우 업무를 인수하는 사람에게 전자 메일이 전달됩니다.|
|[4단계 - 다른 직원에게 데이터 및 OneDrive 액세스 Outlook 부여](remove-former-employee-step-4.md)|사용자의 라이선스만 제거하고 계정을 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다. <p> 계정을 삭제하기 전에 해당 계정에 대한 액세스 권한을 OneDrive Outlook 합니다. 직원의 계정을 삭제하면 해당 계정 및 OneDrive Outlook **30일** 동안 보존됩니다. 그러나 해당 30일 동안 사용자 계정을 복원하고 해당 콘텐츠에 액세스할 수 있습니다. 사용자 계정을 복원하면 30일이 OneDrive Outlook 콘텐츠에 계속 액세스할 수 있습니다.|
|[5단계 - 이전 직원의 모바일 장치 지우기 및 차단](remove-former-employee-step-5.md)|휴대폰 또는 태블릿에서 비즈니스 데이터를 제거합니다.|
|[6단계 - 이전 직원의 Microsoft 365 라이선스 제거 및 삭제](remove-former-employee-step-6.md)|라이선스를 제거하면 다른 사람에게 해당 라이선스를 할당할 수 있습니다. 또는 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않도록 라이선스를 삭제할 수 있습니다.  <p> 라이선스를 제거하거나 삭제하면 사용자의 이전 전자 메일, 연락처 및 일정이 **30일** 간 보존된 후 영구적으로 삭제됩니다. 라이선스를 제거하거나 삭제하되 계정은 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  |
|[7단계 - 이전 직원의 사용자 계정 삭제](remove-former-employee-step-7.md)|그러면 관리 센터에서 계정이 제거됩니다. 깔끔하게 정리됩니다.|
|

## <a name="related-content"></a>관련 콘텐츠

[사용자](restore-user.md) 복원(문서)\
[Microsoft 365에 새 직원 추가](add-new-employee.md)(문서)\
[사용자에게 라이선스 할당](../manage/assign-licenses-to-users.md)(문서)\
[사용자로부터 라이선스를 배포하지](../manage/remove-licenses-from-users.md) 않습니다(문서)
