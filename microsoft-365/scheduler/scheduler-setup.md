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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809194"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>사용자에 대한 스케줄러 Microsoft 365

다음의 선행 Microsoft 365 스케줄러를 설정해야 합니다.

|**필요한 것** |**설명** |
|-------------------|-------------|
|Cortana 사서함 |테넌트 관리자는 "Cortana" 사서함(즉, cortana@yourdomain.com) 역할을 하게 cortana@yourdomain.com.         |
|Exchange Online 사서함 |사용자에게 메일 및 Exchange Online 있어야 합니다.         |
|스케줄러 라이선스 |라이선스 및 가격 정보는 에 대한 [스케줄러를 Microsoft 365.](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)        |

## <a name="create-a-mailbox-for-cortana"></a>Cortana용 사서함 만들기
테넌트의 Exchange 사서함은 Cortana와의 전자 메일을 보내고 받을 테넌트의 Cortana 사서함 역할을 합니다. Cortana로 전송된 모든 전자 메일은 보존 정책에 따라 테넌트의 Cortana 사서함에 보존됩니다.

- Microsoft 365 관리 센터를 사용하여 사용자 사서함을 만들 수 있습니다. 30일 보존 정책이 권장됩니다. 
- 사서함의 기본 SMTP 주소에 Cortana 이름을 사용하세요. "Cortana@yourdomain.com, 'CortanaScheduler@contoso.com' 또는 'Cortana.Scheduler@yourdomain.com' 같은 이름을 권장합니다.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>사서함을 스케줄러 도우미로 지정

Cortana 스케줄러에 대한 고유한 사서함을 만든 후 공식적으로 사서함을 Microsoft 365 합니다. Cortana 스케줄러 사서함을 지정한 후 사용자를 대신하여 모임을 예약할 수 있습니다.

Cortana 스케줄러 사서함을 지정하려면 권한이 부여된 관리자가 한 줄 PowerShell 명령을 실행해야 합니다. 

1. 커넥트 Microsoft 365 원격 PowerShell 실행 공간을 지원할 수 있습니다.
2. 다음 PowerShell 스크립트를 실행하여 스케줄러에 대한 사서함을 지정합니다.

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

Cortana 스케줄러 사서함에서 이 "설정" 명령을 실행한 후 사서함에 새 "PersistedCapability"가 설정되어 이 사서함은 "SchedulerAssistant"입니다.

> [!NOTE]
> 이전에 수행하지 않은 경우 PowerShell에 조직을 연결하기 위해 PowerShell을 사용하여 커넥트 [Microsoft 365 단계에 Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)

조직에서 현재 Cortana 스케줄러 도우미로 설정된 사서함을 검색하기 위해 get 함수를 실행합니다.
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> Scheduler 사서함이 전체 프로비전을 완료하여 SchedulerAssistant 기능을 설정하는 데 최대 2시간이 걸릴 수 있습니다.

## <a name="exchange-online-mailbox"></a>Exchange Online 사서함
스케줄러는 사용자에 대한 추가 Microsoft 365. 모임 이끌이가 스케줄러가 작동하려면 Exchange Online 사서함 및 일정이 있어야 합니다.

## <a name="exchange-requirements"></a>Exchange 요구 사항

라이선싱 스케줄러 외에 다음 라이선스 중 하나도 있어야 합니다.

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online 계획 1 또는 계획 2 라이선스. 

> [!Note]
> **Microsoft 365** 대한 스케줄러는 중국의 21Vianet에서 운영하는 Office 365 사용할 수 없습니다. 데이터 수탁자 German Telekom을 사용하는 Microsoft 365 클라우드를 사용하는 사용자도 사용할 수 없습니다. 데이터 위치가 독일 데이터 센터가 아닌 독일 사용자의 경우에는 지원됩니다.
>
>GCC, Consumer, GCC High 또는 DoD를 비롯한 정부 클라우드 사용자에게도 이 기능을 지원하지 않습니다.
