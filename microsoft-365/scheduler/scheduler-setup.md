---
title: 사용자에 대한 스케줄러 Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 사용자에 대한 스케줄러 Microsoft 365.
ms.openlocfilehash: bebb2befa6a24f8913b70aa77ca66ef7e664e9d2
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042569"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Microsoft 365용 스케줄러 설정

테넌트 관리자는 스케줄러 도우미 사서함을 설정하고 모임 이끌이에 대한 스케줄러 라이선스를 획득하여 예약 서비스에 대한 스케줄러를 Microsoft 365 합니다. 

## <a name="licensing"></a>라이선싱

자세한 내용은 다음을 Microsoft 365 [라이선싱을 위한 스케줄러를 통해 확인할 수 있습니다.](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)

> [!Note]
> 모임 참석자에는 스케줄러 또는 예약 Microsoft 365 없습니다. <br>스케줄러 도우미 사서함에는 스케줄러 Microsoft 365 라이선스가 필요하지 않습니다.

## <a name="prerequisites"></a>필수 구성 요소

| 필수 구성 요소 | 설명 |
|-------------------|-------------|
|테넌트의 스케줄러 도우미 사서함 |Exchange 장비는 테넌트의 스케줄러 도우미 사서함 역할을 하여 전자 메일을 보내고 받는 리소스 사서함을 Cortana. 모든 전자 메일이 Cortana 정책에 따라 테넌트의 Cortana 사서함에 보존됩니다. 스케줄러 도우미 사서함의 이름은 일반적으로 "Cortana" 또는 "Cortana Scheduler"로 지정됩니다. 이 경우 도우미의 모든 전자 메일에 서명이 Cortana.<ul><li>리소스 사서함에 대한 Exchange 유형 만들기</li><li>사서함의 표시 이름과 기본 SMTP 주소 또는 의 이름을 `Cortana <cortana@yourdomain.com>` `Cortana Scheduler <cortana.scheduler@yourdomain.com>` 지정합니다.</li></ul>**참고:** 스케줄러 도우미 사서함에는 스케줄러 Microsoft 365 라이선스가 필요하지 않습니다.|
|Exchange Online 사서함 |모임 이끌이는 일반적으로 Exchange Online 라이선스의 일부로 사서함 및 일정을 Microsoft 365 합니다. 또한 모임 이끌이에게 스케줄러 라이선스가 있어야 합니다. 스케줄러 라이선스를 사용하면 스케줄러 도우미가 모임 이끌이의 사서함과 일정을 사용하여 모임을 예약할 수 있습니다.<br/><br/> 라이선스 및 가격 정보는 Microsoft 365 대한 스케줄러를 참조하세요.  <br/><br/>**참고:** 모임 참석자에는 스케줄러 또는 예약 Microsoft 365 없습니다. 모임 참석자만 테넌트 내부 또는 외부에 있을 수 있습니다. 모임 참석자만 전자 메일 주소에 액세스하면 됩니다.|


## <a name="setting-up-the-scheduler-assistant-mailbox"></a>스케줄러 도우미 사서함 설정

스케줄러 도우미 사서함은 추가 Exchange 또는 스케줄러 라이선스가 필요하지 않은 Microsoft 365 유형 사서함입니다. 스케줄러 도우미의 모든 전자 메일이 서명될 예정이기 때문에 사서함의 표시 이름과 기본 SMTP 주소에는 Cortana 포함되어야 Cortana(또는 )가 포함되어야 `Cortana <cortana@yourdomain.com>` `Cortana Scheduler <cortana.scheduler@yourdomain.com>` 합니다. 스케줄러 도우미 사서함을 만든 후 사서함을 스케줄러 도우미 사서함으로 지정해야 합니다. 스케줄러 도우미 사서함을 지정하면 Cortana 대신 모임을 예약할 수 있습니다.

- 사용자 Microsoft 365 관리 센터 사서함을 만들 수 있습니다. 30일 보존 정책이 권장됩니다. 
- 사서함의 Cortana SMTP 주소에 있는 이름을 사용하세요. `Cortana@yourdomain.com`, , `CortanaScheduler@contoso.com` 같은 이름 또는 `Cortana.Scheduler@yourdomain.com` 권장되는 이름입니다.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>사서함을 스케줄러 도우미로 지정

사용자 지정 스케줄러에 Cortana 사서함을 만든 후 공식적으로 사서함을 Microsoft 365 합니다. 사용자 Cortana 사서함을 지정한 후 사용자를 대신하여 모임을 예약할 수 있습니다.

#### <a name="connect-to-powershell"></a>커넥트 PowerShell로

사용자 Microsoft 365 관리 센터 사서함을 만들 수 있습니다. 30일 보존 정책이 권장됩니다.
사서함의 Cortana SMTP 주소에 있는 이름을 사용하세요. `Cortana@yourdomain.com`, , `CortanaScheduler@contoso.com` 같은 이름 또는 `Cortana.Scheduler@yourdomain.com` 권장되는 이름입니다.

```PowerShell
$domain="yourdomain.com"
$tenantAdmin="<tenantadmin>@$domain"
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $tenantAdmin
```

#### <a name="create-the-scheduler-assistant-mailbox"></a>스케줄러 도우미 사서함 만들기

```PowerShell
New-Mailbox -Name Cortana -Organization $domain -DisplayName "Cortana Scheduler" -Equipment 
Set-CalendarProcessing Cortana@$domain -DeleteNonCalendarItems $false 
```
    
#### <a name="designate-the-scheduler-assistant-mailbox"></a>스케줄러 도우미 사서함 지정

```PowerShell
Set-mailbox cortana@$domain -SchedulerAssistant:$true
```

Cortana 스케줄러 도우미 사서함에서 이 "set" 명령을 실행하면 사서함에 새 "PersistedCapability"가 설정되어 이 사서함이 "SchedulerAssistant"입니다.

> [!Note]
> 조직을 PowerShell에 연결하는 방법에 대한 자세한 내용은 PowerShell을 사용하여 커넥트 [Microsoft 365 참조합니다.](/microsoft-365/enterprise/connect-to-microsoft-365-powershell)

### <a name="verifying-the-scheduler-assistant-mailbox"></a>스케줄러 도우미 사서함 확인

스케줄러 도우미 사서함이 만들어졌다는 확인

```PowerShell
Get-CalendarProcessing cortana@$domain | fl DeleteNonCalendarItems
```

결과는 "false"입니다.

<br>

```PowerShell
Get-Mailbox -Identity cortana@$domain | fl *type*
```

결과는
- ResourceType: Equipment
- Remote RecipientType: None
- RecipientType: UserMailbox
- RecipientTypeDetails: EquipmentMailbox

<br/>

### <a name="to-discover-which-mailbox-is-the-scheduler-assistant-mailbox"></a>스케줄러 도우미 사서함인 사서함을 검색하기 위해

```PowerShell
Get-Mailbox -ResultSize Unlimited | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!Important]
> 스케줄러 도우미 사서함이 전체 프로비전을 완료하여 SchedulerAssistant 기능을 설정하는 데 몇 시간이 걸릴 수 있습니다.


## <a name="exchange-online-mailbox"></a>Exchange Online 사서함

스케줄러 라이선스는 모임 이끌이가 모임 일정 작업을 스케줄러 Microsoft 365 도우미에 위임할 수 있도록 하는 추가 기능입니다. 모임 이끌이는 사서함을 스케줄러 도우미 사서함으로 지정하는 것 외에도 일반적으로 스케줄러가 작동하기 위해 Microsoft 365 라이선스를 통해 Exchange Online 사서함 및 일정을 예약하고 예약자 라이선스가 필요합니다. 모임 참석자에는 스케줄러 라이선스 또는 예약 Microsoft 365 필요하지 않습니다.

스케줄러 추가 기능을 구입하려면 다음 라이선스 중 하나가 필요합니다.

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online 계획 1 또는 계획 2 라이선스. 

> [!Note]
> Microsoft 365 대한 스케줄러는 영어로만 전 세계 다중 테넌트 환경에서 사용할 수 있습니다. **다음 Microsoft 365** 사용자에 대한 스케줄러를 사용할 수 없습니다.
> 
> - Microsoft 365 21Vianet에서 운영하는 중국
> - Microsoft 365 수탁자 German Telekom을 사용하는 독일 클라우드와 함께 사용
> - 정부 클라우드(GCC, 소비자, GCC High 또는 DoD 포함)
> 
> 스케줄러는 데이터 위치가 독일 데이터 센터가 아닌 독일의 사용자를 지원합니다.
