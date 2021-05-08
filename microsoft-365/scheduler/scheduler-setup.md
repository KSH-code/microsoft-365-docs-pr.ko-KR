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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286255"
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

- 새 Microsoft 365 관리 센터를 사용하여 새 사서함을 만들 수 있습니다. 30일 보존 정책이 권장됩니다. 사서함의 기본 SMTP 주소에 Cortana 이름을 사용하세요. "Cortana@yourdomain.com, 'CortanaScheduler@contoso.com' 또는 'Cortana.Scheduler@yourdomain.com' 같은 이름을 권장합니다.
- Cortana 사서함을 scheduler_m365@microsoft.com Microsoft(scheduler_m365@microsoft.com)에 문의합니다. 

> [!IMPORTANT]
> 스케줄러 서비스를 사용하도록 Cortana 사서함을 구성하려면 Microsoft에 문의해야 scheduler_m365@microsoft.com. Cortana 사서함을 사용하도록 설정하는 데 최대 2주가 걸릴 수 있습니다.

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
