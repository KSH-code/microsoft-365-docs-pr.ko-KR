---
title: 6단계 - 이전 직원의 Microsoft 365 라이선스 제거 및 삭제
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 다음 단계에 따라 이전 Microsoft 365 라이선스를 제거합니다.
ms.openlocfilehash: 0491a28daac7b85c23037a722f3f810bb4eab71d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161585"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>6단계 - 이전 Microsoft 365 라이선스 제거

조직을 떠날 때 라이선스 비용을 지불하지 않는 경우 해당 Microsoft 365 라이선스를 제거한 다음 구독에서 삭제해야 합니다. 라이선스를 삭제하지 않는 경우 다른 사용자에게 라이선스를 할당할 수 있습니다.
  
라이선스를 제거하면 해당 사용자의 모든 데이터가 30일간 보존됩니다. 데이터에 [액세스](get-access-to-and-back-up-a-former-user-s-data.md)하거나 해당 사용자가 복귀하면 계정을 [복원](restore-user.md)할 수 있습니다. 30일이 지난 후 모든 사용자 데이터(SharePoint Online에 저장된 문서 제외)는 Microsoft 365 영구적으로 삭제되고 복구할 수 없습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..
2. 차단할 직원의 이름을 선택한 다음 라이선스 및 앱 **탭을** 선택합니다.
3. 제거할 라이선스의 확인란 선택을 취소한 다음 변경 내용 저장 **을 선택합니다.**

**다른 사람을** 고용할 때까지 비용을 지불하는 라이선스 수를 줄이십시오. 다음 단계를 수행합니다.

1. 관리 센터에서 청구 제품  페이지로 이동하여 제품 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"></a> **탭을** 선택합니다.
2. 라이선스를 제거할 구독을 선택합니다.
3. 세부 정보 페이지에서 라이선스 **제거를 선택합니다.**
4. 라이선스 **제거 창의** 새 수량 아래에 있는  총 라이선스 상자에 이 구독에 대해 원하는 총 라이선스 수를 입력합니다. 예를 들어 라이선스가 25개인 경우 라이선스 중 하나를 제거하려면 24를 입력합니다.
5. **저장** 을 선택합니다.

When you [add another person](add-users.md) to your business, you'll be prompted to buy a license at the same time, with just one step!

비즈니스용 Microsoft 365 사용자 라이선스를 관리하는 데 대한 자세한 내용은 비즈니스용 Microsoft 365 사용자에 라이선스 할당 [및](../manage/assign-licenses-to-users.md)비즈니스용 Microsoft 365 사용자의 라이선스 할당을 Microsoft 365 [참조하세요.](../manage/remove-licenses-from-users.md)
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>삭제된 직원 계정이 비즈니스용 Skype에 영향을 미치는 방식

Office 365에서 사용자 라이선스를 제거하면 사용자와 연결된 PSTN 호출 번호가 해제됩니다. 이 PSTN 호출 번호를 다른 사용자에게 할당할 수 있습니다.
  
사용자가 큐 그룹에 속하는 경우 더 이상 통화 큐 에이전트의 실행 가능한 대상이 아닙니다. 따라서 통화 큐와 연결된 그룹에서도 사용자를 제거하는 것이 좋습니다.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>조직의 사용자에 대한 통화 전달 설정

종료된 직원의 전화 번호에 대해 통화 전달을 설정해야 하는 경우 통화 정책의 통화 전달 설정에서 수신 전화를 다른 사용자에게 전달하거나 동시에 다른 사용자에게 벨을 울리는 전달을 설정할 수 있습니다. 자세한 내용은 에서 [정책 호출을 Microsoft Teams.](/microsoftteams/teams-calling-policy)
