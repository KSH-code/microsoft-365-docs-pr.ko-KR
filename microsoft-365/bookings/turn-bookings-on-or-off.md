---
title: Microsoft Bookings 설정 또는 해제
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft 365에서 Microsoft Bookings에 액세스하는 방법을 알아보십시오.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913769"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings 설정 또는 해제

전체 조직 또는 특정 사용자에 대해 예약을 설정하거나 해제할 수 있습니다. 사용자에 대해 Bookings를 켜면 Bookings 페이지를 만들고, 일정을 만들고, 다른 사용자가 함께 시간을 예약할 수 있습니다.

> [!NOTE]
> 이 섹션에 설명된 관리 컨트롤은 21Vianet(중국)에서 운영하는 Office 365 고객은 사용할 수 없습니다.

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용하여 조직의 예약 설정 또는 해제

1. 전역 관리자로 Microsoft 365 관리 센터에 로그인합니다.

2. 관리 센터에서 설정  **구성**   \> **설정으로 이동하여** **예약을 선택합니다.**

3. 조직에서 **Bookings를 사용하여 조직에 Bookings를** 사용하도록 설정하거나 사용하지 않도록 설정하려면 확인란을 선택합니다.

   > [!NOTE]
   > Bookings를 해제하면 Bookings 페이지 만들기 및 관리를 포함하여 서비스에 대한 모든 액세스가 비활성화됩니다.

4. 변경 **내용 저장을 선택합니다.**

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell을 사용하여 조직의 Bookings 설정 또는 해제

PowerShell cmdlet [Set-OrganizationConfig를](/powershell/module/exchange/set-organizationconfig)사용하여 조직에서 Bookings를 켜거나 끄기 위해 [Exchange Online PowerShell에 연결하고](/powershell/exchange/connect-to-exchange-online-powershell) 다음 명령을 실행합니다.

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>개별 사용자에 대해 Bookings 설정 또는 해제

개별 사용자에 대해 Bookings를 사용하지 않도록 설정할 수 있습니다.

1. Microsoft 365 관리 센터로 이동한 다음 사용자 활성 **사용자를** \> **선택합니다.**

1. 원하는 사용자를 선택한 다음 라이선스 및 **앱을 선택합니다.**

1. 앱을 **확장하고** Microsoft Bookings 확인란의 선택을 취소합니다.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>사용 중/바우트 정보를 공유하기 전에 직원 승인 필요

관리자는 Bookings를 통해 가용성 정보를 공유하기 전에 또는 예약 페이지를 통해 예약할 수 있도록 조직의 직원이 옵트인(opt in)을 요구할 수 있습니다. 이 설정은 설정 예약의 Microsoft 365 **관리** \> **센터에서** \> **사용할 수 있습니다.**

이 설정을 사용하도록 설정하면 예약 일정에서 직원으로 추가된 직원은 받은 전자 메일 알림에서 승인/거부 링크를 찾을 수 있습니다.

이 기능은 전 세계 Microsoft 365 고객에게 점진적으로 배포하고 있습니다. Microsoft 365 관리 센터에 이 옵션이 없는 경우 곧 다시 확인하세요.

## <a name="block-social-sharing-options"></a>공유 공유 옵션 차단

관리자는 소셜 네트워크에서 예약 페이지가 공유되는 방법을 제어할 수 있습니다. 이 설정은 설정 예약의 Microsoft 365 **관리** \> **센터에서** \> **사용할 수 있습니다.**

이 기능은 전 세계 Microsoft 365 고객에게 점진적으로 배포하고 있습니다. Microsoft 365 관리 센터에 이 옵션이 없는 경우 곧 다시 확인하세요.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>선택한 사용자만 Bookings 일정을 만들 수 있도록 허용

정책 제한을 사용하면 라이선스가 부여된 사용자가 Bookings 일정을 만들 수 없는 것을 제한할 수 있습니다. 먼저 전체 조직에 대해 Bookings를 사용하도록 설정해야 합니다. 조직의 모든 사용자에게 Bookings 라이선스가 있지만 정책에 포함된 사용자만 Bookings 일정을 만들고 만든 일정에 액세스할 수 있는 사용자를 제어할 수 있습니다.

이 정책에 포함된 사용자는 새 Bookings 일정을 만들 수 있으며 모든 용량(관리자 역할 포함)의 직원으로 기존 Bookings 일정에 추가할 수 있습니다. 이 정책에 포함되지 않은 사용자는 새 Bookings 일정을 만들 수 없습니다. 이렇게 하면 오류 메시지가 표시됩니다.

Exchange Online PowerShell을 사용하여 다음 명령을 실행해야 합니다. Exchange Online cmdlet 실행에 대한 자세한 내용은 [Exchange Online PowerShell에 연결을 참조하세요.](/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> 아래 단계에서는 조직에서 OWA(Outlook Web App) 사서함 정책이 만들어졌다고 가정합니다.

1. Bookings 일정을 만들 수 있도록 허용해야 하는 사용자에 대한 새 사서함 정책을 만들 수 있습니다. Bookings 일정 만들기는 기본적으로 새 사서함 정책에 의해 허용됩니다.

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   자세한 내용은 [New-OwaMailboxPolicy를 참조하십시오.](/powershell/module/exchange/new-owamailboxpolicy)

2. Bookings 일정 만들기 권한을 부여할 각 사용자에 대해 이 명령을 실행하여 관련 사용자에게 이 정책을 할당합니다.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   자세한 내용은 [Set-CASMailbox를 참조하세요.](/powershell/module/exchange/set-casmailbox)

3. 선택 사항: 조직의 다른 모든 사용자에 대해 Bookings를 사용하지 않도록 설정하려는 경우 이 명령을 실행합니다.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   자세한 내용은 [Set-OwaMailboxPolicy를 참조하세요.](/powershell/module/exchange/set-owamailboxpolicy)

OWA 사서함 정책에 대한 자세한 내용은 다음 항목을 참조하세요.

- [Exchange Online에서 웹에서 Outlook 사서함 정책 만들기](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Exchange Online의 사서함에서 웹에서 Outlook 사서함 정책 적용 또는 제거](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)