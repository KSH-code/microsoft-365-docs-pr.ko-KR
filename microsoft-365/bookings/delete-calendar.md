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
description: Microsoft 365 관리 센터 또는 Windows PowerShell 예약 일정을 삭제합니다.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126652"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Bookings에서 예약 일정 삭제

이 문서에서는 원치 않는 예약 일정을 삭제하는 방법에 대해 설명합니다. Microsoft 365 관리 센터에서 예약 일정을 삭제하거나 PowerShell을 사용할 수 있습니다. Bookings 일정은 Exchange Online의 사서함으로, 해당 사용자 계정을 삭제하여 예약 일정을 삭제합니다.

> [!IMPORTANT]
> 2017년 또는 그 전에 만든 모든 예약 일정은 이 항목의 PowerShell 지침을 사용하여 삭제해야 합니다. 2018년 또는 그 이후에 만든 모든 예약 일정은 Microsoft 365 관리 센터에서 삭제할 수 있습니다.

예약 일정은 다음을 포함하여 예약 일정 및 데이터에 대한 모든 관련 정보가 저장되는 위치입니다.

- 예약 일정을 만들 때 추가된 비즈니스 정보, 로고 및 작업 시간
- 예약 일정을 만들 때 추가된 관련 직원 및 서비스
- 모든 예약 및 약속을 만든 후 예약 일정에 추가된 약속의 시간입니다.

> [!WARNING]
> 예약 일정이 삭제되면 이 추가 정보도 영구적으로 삭제되고 복구할 수 없습니다.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 예약 일정 삭제

1. Microsoft 365 관리 센터로 이동합니다.

1. 관리 센터에서 **사용자** 를 선택합니다.

   ![Microsoft 365 관리 센터의 사용자 UI 이미지](../media/bookings-admin-center-users.png)

1. **활성 사용자** 페이지에서 삭제할 사용자의 이름을 선택한 다음 **사용자 삭제** 를 선택합니다.

   ![Microsoft 365 관리 센터에서 사용자 UI 삭제 이미지](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Exchange Online PowerShell을 사용하여 예약 일정 삭제

Exchange [Online PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) 연결하기 위한 전제 및 지침은 Exchange Online PowerShell에 연결하기를 참조하세요.

이러한 단계를 수행하려면 "관리자 권한으로 실행" 옵션을 선택하여 실행한 활성 Microsoft PowerShell 명령 창을 사용하고 있어야 합니다.

1. 다음 명령을 입력합니다.

   ```PowerShell
    $user = get-credential
   ```

1. 메시지가 표시되면 영구적으로 삭제할 예약 일정을 호스트하는 Microsoft 365 테넌트에 테넌트 관리자 자격 증명으로 로그온합니다.

1. PowerShell 명령 프롬프트에 다음 명령을 입력합니다.

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. 다음 명령을 입력합니다.

   ```PowerShell
    Import-PSSession $s
   ```

1. 이 명령이 처리된 후 다음 명령을 입력하여 테넌트의 예약 사서함 목록을 얻습니다.

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. 다음 명령을 입력합니다.

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 영구적으로 삭제할 예약 사서함 별칭의 정확한 이름을 입력해야 합니다.

1. 일정이 삭제된 것을 확인하려면 다음 명령을 입력합니다.

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   삭제된 달력은 출력에 나타나지 않습니다.
