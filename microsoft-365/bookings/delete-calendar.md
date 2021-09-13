---
title: 예약 일정 삭제
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: 예약 Microsoft 365 관리 센터 Windows PowerShell 일정을 삭제합니다.
ms.openlocfilehash: fc5975e25fa3b1f2d2aab991cc7aac8038181f3f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186499"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Bookings에서 예약 일정 삭제

이 문서에서는 원치 않는 예약 일정을 삭제하는 방법에 대해 설명하고 있습니다. 사용자 계정에서 예약 일정을 삭제하거나 Microsoft 365 관리 센터 PowerShell을 사용할 수 있습니다. Bookings 일정은 예약 Exchange Online 사서함으로, 해당 사용자 계정을 삭제하여 예약 일정을 삭제합니다.

> [!IMPORTANT]
> 2017년 또는 그 전에 만든 모든 예약 일정은 이 항목의 PowerShell 지침을 사용하여 삭제해야 합니다. 2018년 또는 그 이후에 만들어진 모든 예약 일정은 일정에서 삭제할 수 Microsoft 365 관리 센터.

예약 일정은 다음을 포함하여 예약 일정 및 데이터에 대한 모든 관련 정보가 저장되는 위치입니다.

- 예약 일정을 만들 때 추가된 업무 정보, 로고 및 작업 시간
- 예약 일정을 만들 때 추가된 관련 직원 및 서비스
- 예약 일정을 만든 후 예약 일정에 추가된 모든 예약 및 약속이 벗어났습니다.

> [!WARNING]
> 예약 일정이 삭제되면 이 추가 정보도 영구적으로 삭제되고 복구할 수 없습니다.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>일정에서 예약 일정 Microsoft 365 관리 센터

1. Microsoft 365 관리 센터로 이동합니다.

1. 관리 센터에서 **사용자** 를 선택합니다.

   ![사용자 UI의 Microsoft 365 관리 센터.](../media/bookings-admin-center-users.png)

1. **활성 사용자** 페이지에서 삭제할 사용자의 이름을 선택한 다음 **사용자 삭제** 를 선택합니다.

   ![사용자 UI 삭제의 Microsoft 365 관리 센터.](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>PowerShell을 사용하여 예약 Exchange Online 삭제

PowerShell에 커넥트 대한 Exchange Online 및 지침은 [PowerShell을](/powershell/exchange/exchange-online-powershell-v2) Exchange Online 참조하세요.

이러한 단계를 수행하려면 "관리자 권한으로 실행" 옵션을 선택하여 실행한 활성 Microsoft PowerShell 명령 창을 사용하고 있어야 합니다.

1. PowerShell 창에서 다음 명령을 실행하여 EXO V2 모듈을 로드합니다.

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > [EXO V2 모듈을 이미 설치](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)한 경우 이전 명령은 기록된 대로 작동합니다.
   
2. 실행해야 하는 명령은 다음 구문을 사용합니다.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ 은(는) 사용자 계정 이름 형식(예: `john@contoso.com`)의 계정입니다.

3. 메시지가 표시되면 영구적으로 삭제할 예약 일정을 호스팅하는 Microsoft 365 테넌트에 테넌트 관리자 자격 증명으로 로그온합니다.

4. 이 명령의 처리가 완료되면 다음 명령을 입력하여 테넌트의 예약 사서함 목록을 얻습니다.

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. 다음 명령을 입력합니다.

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 영구적으로 삭제할 예약 사서함 별칭의 정확한 이름을 입력해야 합니다.

6. 일정이 삭제된 것을 확인하려면 다음 명령을 입력합니다.

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   삭제된 달력은 출력에 나타나지 않습니다.
