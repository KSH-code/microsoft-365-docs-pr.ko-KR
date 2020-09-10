---
title: Microsoft 예약 켜기 또는 끄기
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft 365에서 Microsoft 예약에 액세스 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 815aa3a859db15364aa18d3550001a28d085b711
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419919"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft 예약 켜기 또는 끄기

전체 조직 또는 특정 사용자에 대해 예약을 설정 하거나 해제할 수 있습니다. 사용자에 대해 예약을 켜면 예약 페이지를 만들고 일정을 만든 다음 다른 사용자가이를 사용 하 여 시간을 예약할 수 있습니다.

> [!NOTE]
> 이 섹션에서 설명 하는 관리 컨트롤은 21Vianet (중국) 고객이 운영 하는 Office 365에서는 사용할 수 없습니다.

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용 하 여 조직에 대해 예약 설정 또는 해제

1. 전역 관리자 권한으로 Microsoft 365 관리 센터에 로그인 합니다.

2. 관리 센터에서 **설정** 설정으로 이동 하 여   \> **Settings** **예약**을 선택 합니다.

3. **조직에서 예약을 사용** 하 여 조직에 대해 예약을 사용 하거나 사용 하지 않도록 설정할 수 있는 확인란을 선택 합니다.

   > [!NOTE]
   > 예약을 끄면 예약 페이지 만들기 및 관리를 포함 하 여 서비스에 대 한 모든 액세스를 사용할 수 없게 됩니다.

4. **변경 내용 저장**을 선택 합니다.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell을 사용 하 여 조직에 대해 예약 설정 또는 해제

PowerShell cmdlet [set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)를 사용 하 여 조직에 대해 예약을 설정 하거나 해제 하려면 [Exchange Online PowerShell에 연결]() 하 고 다음 명령을 실행 합니다.

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>개별 사용자에 대해 예약 설정 또는 해제

개별 사용자에 대해 예약을 사용 하지 않도록 설정할 수 있습니다.

1. Microsoft 365 관리 센터로 이동한 후 **사용자** \> **활성 사용자**를 선택 합니다.

1. 원하는 사용자를 선택한 다음 **라이선스 및 앱**을 선택 합니다.

1. **앱** 을 확장 하 고 Microsoft 예약에 대 한 확인란의 선택을 취소 합니다.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>약속 있음/없음 정보를 공유 하기 전에 직원 승인 필요

관리자는 조직의 직원 들이 예약을 통해 사용 가능 정보를 공유 하기 전에 예약 페이지를 통해 게시할 수 있도록 해야 합니다. 이 설정은 예약 **설정 아래의 Microsoft** 365 관리 센터에서 사용할 수 있습니다 \> **Settings** \> **Bookings**.

이 설정을 사용 하도록 설정 하면 예약 일정에서 직원으로 추가 된 직원은 수신 하는 전자 메일 알림에 승인/거부 링크를 찾습니다.

이 기능은 세계 전체를 Microsoft 365 고객에 게 점진적으로 배포 하는 기능입니다. Microsoft 365 관리 센터에서이 옵션이 표시 되지 않으면 곧 다시 확인 하세요.

## <a name="block-social-sharing-options"></a>소셜 공유 옵션 차단

관리자는 공유 네트워크에서 예약 페이지를 공유 하는 방법을 제어할 수 있습니다. 이 설정은 예약 **설정 아래의 Microsoft** 365 관리 센터에서 사용할 수 있습니다 \> **Settings** \> **Bookings**.

이 기능은 세계 전체를 Microsoft 365 고객에 게 점진적으로 배포 하는 기능입니다. Microsoft 365 관리 센터에서이 옵션이 표시 되지 않으면 곧 다시 확인 하세요.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>선택한 사용자만 예약 일정을 만들 수 있도록 허용

정책 제한을 사용 하면 사용이 허가 된 사용자가 예약 일정을 만들 수 없도록 제한할 수 있습니다. 먼저 전체 조직에 대해 예약을 사용 하도록 설정 해야 합니다. 조직의 모든 사용자에 게는 예약 라이선스가 포함 되지만, 정책에 포함 된 사람만 예약 일정을 만들 수 있으며 자신이 만든 일정에 액세스할 수 있는 사용자에 대 한 모든 권한이 있습니다.

이 정책에 포함 된 사용자는 새 예약 캘린더를 만들 수 있으며, 모든 용량 (관리자 역할 포함)에서 기존 예약 일정에 직원으로 추가할 수 있습니다. 이 정책에 포함 되지 않은 사용자는 새 예약 일정을 만들 수 없으며, 만들려고 하면 오류 메시지가 표시 됩니다.

Exchange Online PowerShell을 사용 하 여 다음 명령을 실행 해야 합니다. Exchange Online cmdlet을 실행 하는 방법에 대 한 자세한 내용은 [Connect To Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조 하십시오.

> [!IMPORTANT]
> 아래 단계에서는 다른 OWA (Outlook Web App) 사서함 정책이 조직에 만들어지지 않은 것으로 가정 합니다.

1. 예약 일정을 만들도록 허용 해야 하는 사용자에 대 한 새 사서함 정책을 만듭니다. 기본적으로는 새 사서함 정책에 의해 예약이 일정을 만들 수 있습니다.

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   자세한 내용은 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)를 참조 하십시오.

2. 예약 일정을 만들 수 있는 권한을 부여 하려는 각 사용자에 대해이 명령을 실행 하 여 관련 사용자에 게이 정책을 할당 합니다.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   자세한 내용은 [설정-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)를 참조 하십시오.

3. 선택 사항: 조직의 다른 모든 사용자에 대해 예약을 사용 하지 않도록 설정 하려면이 명령을 실행 합니다.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   자세한 내용은 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)를 참조 하십시오.

OWA 사서함 정책에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

- [Exchange Online에서 웹 사서함 정책에 대 한 Outlook 만들기](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Exchange Online에서 사서함에 대 한 웹 사서함 정책에서 Outlook 적용 또는 제거](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)