---
title: 예약 달력 삭제
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Microsoft 365 관리 센터 또는 Windows PowerShell을 사용 하 여 예약 일정을 삭제할 수 있습니다.
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422445"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>예약에서 예약 달력 삭제

이 문서에서는 원하지 않는 예약 일정을 삭제 하는 방법에 대해 설명 합니다. Microsoft 365 관리 센터에서 예약 일정을 삭제 하거나 PowerShell을 사용할 수 있습니다. 예약 일정은 Exchange Online의 사서함 이므로 해당 사용자 계정을 삭제 하 여 예약 일정을 삭제할 수 있습니다.

> [!IMPORTANT]
> 2017 이상에서 만든 모든 예약 일정은이 항목의 PowerShell 지침을 사용 하 여 삭제 해야 합니다. 2018 또는 이후에 만든 모든 예약 일정은 Microsoft 365 관리 센터에서 삭제할 수 있습니다.

예약 일정은 다음과 같은 해당 예약 일정과 데이터에 대 한 모든 관련 정보가 저장 되는 위치입니다.

- 예약 일정을 만들 때 추가 된 회사 정보, 로고 및 근무 시간
- 예약 일정을 만들 때 추가 된 관련 직원 및 서비스
- 예약 된 모든 예약 및 휴가 약속이 만들어진 일정에 추가 됩니다.

> [!WARNING]
> 예약 일정이 삭제 되 면이 추가 정보도 영구적으로 삭제 되며 복구할 수 없습니다.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 예약 달력 삭제

1. Microsoft 365 관리 센터로 이동합니다.

1. 관리 센터에서 **사용자** 를 선택합니다.

   ![Microsoft 365 관리 센터의 사용자 UI의 이미지](../media/bookings-admin-center-users.png)

1. **활성 사용자** 페이지에서 삭제할 사용자의 이름을 선택한 다음 **사용자 삭제**를 선택합니다.

   ![Microsoft 365 관리 센터의 사용자 UI 삭제 이미지](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Exchange Online PowerShell을 사용 하 여 예약 달력 삭제

필수 구성 요소는 exchange [Online powershell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 및 Exchange online powershell에 연결 하기 위한 지침을 참조 하세요.

이 단계를 수행 하려면 "관리자 권한으로 실행" 옵션을 선택 하 여 실행 한 활성 Microsoft PowerShell 명령 창을 사용 해야 합니다.

1. 다음 명령을 입력 합니다.

   ```PowerShell
    $user = get-credential
   ```

1. 메시지가 표시 되 면 영구적으로 삭제 하려는 예약 일정을 호스트 하는 Microsoft 365 테 넌 트에 테 넌 트 관리자 자격 증명을 사용 하 여 로그온 합니다.

1. PowerShell 명령 프롬프트에 다음 명령을 입력 합니다.

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. 다음 명령을 입력 합니다.

   ```PowerShell
    Import-PSSession $s
   ```

1. 이 명령 처리가 완료 되 면 다음 명령을 입력 하 여 테 넌 트의 예약 사서함 목록을 가져옵니다.

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. 다음 명령을 입력합니다.

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 영구적으로 삭제 하려는 예약 사서함 별칭의 정확한 이름을 입력 하는 것이 좋습니다.

1. 일정이 삭제 되었는지 확인 하려면 다음 명령을 입력 합니다.

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   삭제 된 달력이 출력에 표시 되지 않습니다.
