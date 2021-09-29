---
title: Microsoft에 스팸, 스팸이 아닌 메시지 및 피싱 메시지 보고
f1.keywords:
- NOCSH
ms.author: dansimp
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
ms.openlocfilehash: 77b370bcd0a1ee59e80a638669598cf27ef32942
ms.sourcegitcommit: 4b1bf6e4f4a0c016d148cdde7f7880dd774403d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2021
ms.locfileid: "59988922"
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

|방법|설명|
|---|---|
|[제출 포털을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출](admin-submission.md)|사서함이 있는 조직의 관리자에게 권장되는 보고 Exchange Online(독립 실행형 EOP에서는 사용할 수 없습니다).|
|[보고서 메시지 또는 보고서 피싱 추가 기능 사용](enable-the-report-message-add-in.md)|Outlook 및 웹용 Outlook(이전의 Outlook Web App). <p> 구독에 따라 사용자가 추가 기능으로 보고한 메시지는 [관리](admin-submission.md)제출 포털, 자동화된 조사 및 [응답(AIR)](air-view-investigation-results.md)결과, [사용자가](view-email-security-reports.md#user-reported-messages-report)보고한 메시지 보고서 및 탐색기 에서 사용할 수 [있습니다.](threat-explorer-views.md#email--submissions) <p> 보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)
|[Outlook에서 가양성 및 가음성 보고](report-false-positives-and-false-negatives.md)|보고서 메시지 기능을 사용하여 가양성(차단되거나 정크 폴더로 전송된 양호한 전자 메일) 및 가음성(받은 편지함으로 배달된 원치 않는 전자 메일 또는 피싱)을 EOP(Exchange Online Protection)에 제출합니다.|
|[분석을 위해 수동으로 Microsoft에 메시지 제출](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|특정 Microsoft 전자 메일 주소에 수동으로 스팸과 스팸이 아닌 메일, 피싱에 관한 첨부 메시지를 보냅니다.|
|[메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|사용자가 분석을 위해 Microsoft에 메시지를 보고할 때 이를 알 수 있는 메일 흐름 규칙(전송 규칙)을 만드는 방법을 학습합니다.|
|[분석을 위해 맬웨어 및 비 맬웨어를 Microsoft에 제출](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft 보안 인텔리전스 사이트를 사용해 첨부 파일 및 기타 파일을 제출합니다.|
|

> [!NOTE]
> Microsoft에 제출하는 데이터는 북미 데이터 센터의 Office 365 규정 준수 경계 안에서 보관됩니다. 이 데이터는 필터링 효과를 개선하는 데 도움을 주기 위해 엔지니어링 팀의 분석가가 검토합니다.
