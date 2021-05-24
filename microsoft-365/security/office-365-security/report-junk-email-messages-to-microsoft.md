---
title: Microsoft에 스팸, 스팸이 아닌 메시지 및 피싱 메시지 보고
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 관리자는 분석을 위해 Microsoft에 좋은 메시지와 잘못된 메시지와 파일을 보고하는 다양한 방법에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d7534d5d88fe19fba39ac1ebef16c72cac25cae7
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625044"
---
# <a name="report-messages-and-files-to-microsoft"></a>Microsoft에 메시지와 파일 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection)에 사서함이 있는 Exchange Online 조직에서는 사용자와 관리자 모두 Microsoft에 전자 메일 메시지와 파일을 보고하는 여러 가지 방법이 있습니다.

<br>

****

|메서드|설명|
|---|---|
|[관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출](admin-submission.md)|사서함이 있는 조직의 관리자에게 권장되는 보고 Exchange Online(독립 실행형 EOP에서는 사용할 수 없습니다).|
|[보고서 메시지 또는 피싱 보고 추가 기능 사용](enable-the-report-message-add-in.md)|웹에서 Outlook 및 Outlook(이전의 Outlook Web App). <p> 구독에 따라 사용자가 추가 기능으로 보고한 메시지는 [관리](admin-submission.md)제출 포털, 자동화된 조사 및 [응답(AIR)](air-view-investigation-results.md)결과, [사용자가](view-email-security-reports.md#user-reported-messages-report)보고한 메시지 보고서 및 [위협](threat-explorer-views.md#email--submissions)탐색기 에서 사용할 수 있습니다. <p> 보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)
|[가짓 긍정 및 거짓 부정을 Outlook](report-false-positives-and-false-negatives.md)|보고서 메시지 기능을 사용하여 가음성(차단되거나 정크 폴더로 전송된 양호한 전자 메일) 및 거짓 부정(받은 편지함으로 배달된 원치 않는 전자 메일 또는 피싱)을 Exchange Online Protection(EOP)에 제출합니다.|
|[분석을 위해 Microsoft에 수동으로 메시지 전송](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|스팸 및 피싱이 아닌 스팸에 대해 특정 Microsoft 전자 메일 주소로 첨부된 메시지를 수동으로 전송합니다.|
|[메일 흐름 규칙을 사용하여 Microsoft에 보고하는 사용자 확인](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|사용자가 분석을 위해 Microsoft에 메시지를 보고할 때 이를 알 수 있는 메일 흐름 규칙(전송 규칙)을 만드는 방법을 학습합니다.|
|[분석을 위해 Microsoft에 맬웨어 및 맬웨어가 아닌 제출](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|사이트 Microsoft 보안 인텔리전스 사용하여 첨부 파일 및 기타 파일을 제출합니다.|
|

스팸 또는 피싱 메시지가 배달되지 않고 검리된 경우 사용자는 보안 및 준수 센터의 검량 포털에서 Microsoft에 메시지를 & 수 있습니다. 자세한 내용은 [Find and release quarantined messages as a user in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Microsoft로 전송되는 데이터는 북미 데이터 센터의 Office 365 규정 준수 경계에 있습니다. 이 데이터는 엔지니어링 팀의 분석가가 필터의 효율성을 개선하는 데 도움을 주며 검토합니다.
