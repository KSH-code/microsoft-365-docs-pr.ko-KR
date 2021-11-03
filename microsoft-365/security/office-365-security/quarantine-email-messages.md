---
title: Quarantined email messages
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 관리자는 잠재적으로 위험하거나 원치 않는 메시지를 보유하는 EOP(Exchange Online Protection)에서 검사에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58097b5dba60c1ea085ea6e78c878982abe24021
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703624"
---
# <a name="quarantined-email-messages-in-eop-and-defender-for-office-365"></a>EOP 및 2013에 대한 Defender의 Quarantined 전자 메일 Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 Exchange Online 조직에서는 잠재적으로 위험하거나 원치 않는 메시지를 보유할 수 있습니다.

맬웨어 방지 정책은 첨부 파일이  맬웨어를 포함하는 것으로 확인된 경우 메시지를 자동으로 검지합니다. 자세한 내용은 EOP에서 맬웨어 [방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)

기본적으로 스팸 방지 정책은 피싱 및 높은 신뢰도 피싱 메시지를 차단하고 스팸, 높은 스팸 및 대량 전자 메일 메시지를 사용자의 정크 메일 폴더로 전달합니다. 그러나 스팸 방지 정책을 만들고 사용자 지정하여 스팸, 높은 신뢰도 스팸 및 대량 전자 메일 메시지를 차단할 수도 있습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

사용자와 관리자는 모두 다음을 통해 분리된 메시지로 작업할 수 있습니다.

- _Quarantine policies_ define what users are allowed to do or not do to quarantined messages based on why the message was quarantined why the message was quarantined (for supported features). 기본 검역 정책은 아래 설명된 기록 기능을 적용합니다. 관리자는 사용자에 대해 덜 제한적이거나 더 제한적인 기능을 정의하는 사용자 지정 검지 정책을 만들고 적용할 수 있으며, 또한 검지 알림을 켜도 됩니다. 자세한 내용은 [격리 정책](quarantine-policies.md)을 참조하세요.

- 관리자는 모든 사용자에 대해 모든 유형의 분리된 메시지로 작업할 수 있습니다. 기본적으로 관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙의 결과로(전송 규칙) 메시지로 작업할 수 있습니다. 자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.

- 기본적으로 사용자는 받는 사람이고 메시지가 스팸, 대량 전자 메일 또는 피싱(높은 신뢰도의 피싱이 아닌 피싱)으로 차단된 메시지로 작업할 수 있습니다. 자세한 내용은 EOP에서 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)

  사용자가 자체적으로 분리된 피싱 메시지를 관리하지 못하게 방지하기 위해 관리자는 스팸 방지 정책의 피싱 전자 메일 필터링 판정에서 검지된 메시지에 대한 액세스를 거부하는 검지 정책을 할당할 수 있습니다.  자세한 내용은 스팸 방지 정책 [Quarantine policies](quarantine-policies.md#anti-spam-policies)에서[Quarantine policies 할당을 참조하세요.](quarantine-policies.md)

- 관리자와 사용자는 Microsoft에 가짓 긍정을 검지에서 보고할 수 있습니다.

- 메시지가 만료되기 전에 메시지에 대해 검지된 메시지를 보전하는 기간은 메시지가 검사된 이유에 따라 다릅니다. 다음 표에서는 메시지와 해당 보존 기간을 검사하는 기능에 대한 설명을 제공합니다.

  <br>

  ****

  |격리 이유:|기본 보존 기간|사용자 지정 가능 여부|설명|
  |---|:---:|:---:|---|
  |스팸 방지 정책(스팸, 높은 지수 스팸, 피싱, 높은 신뢰도 피싱 또는 대량)에 의해 차단된 메시지입니다.|30일|예|스팸 방지 정책에서 이 값을 구성(더 낮음)할 수 있습니다. 자세한 내용은 Configure  anti-spam policies 에서 이 며칠 동안 스팸을 스팸 보존(QuarantineRetentionPeriod ) 설정을 [참조하세요.](configure-your-spam-filter-policies.md)|
  |피싱 방지 정책에 의해 분리된 메시지: EOP의 스푸핑 인텔리전스 사용자 가장, 도메인 가장 또는 사용자에 대한 Defender의 사서함 인텔리전스 Office 365.|30일|예|또한 이 보존 기간은  스팸 방지 정책에서 이 기간 동안 스팸 _보존(QuarantineRetentionPeriod)_ 설정에 **의해 제어됩니다.** 사용되는 보존 기간은 받는 사람이 정의된 첫  번째 일치하는 스팸 방지 정책의 값입니다.|
  |맬웨어 방지 정책(맬웨어 메시지)으로 차단된 메시지입니다.|15일|아니요||
  |Defender for 금고 첨부 파일 정책에 의해 Office 365(맬웨어 메시지)|15일|아니요||
  |메일 흐름 규칙에 의해 검사된 메시지: 작업은 메시지를 호스팅된 _검사(Quarantine)에 배달합니다._ |30일|아니요||
  |금고, OneDrive 및 파일(맬웨어 파일)에 SharePoint 파일로 Microsoft Teams 파일입니다.|15일|아니요||
  |

  메시지가 검지에서 만료되면 복구할 수 없습니다.

Quarantine에 대한 자세한 내용은 [Quarantine FAQ 를 참조하십시오.](quarantine-faq.yml)
