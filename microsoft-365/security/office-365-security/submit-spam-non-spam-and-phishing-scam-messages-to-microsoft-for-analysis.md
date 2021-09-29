---
title: 수동으로 Microsoft에 분석용 메시지 제출
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 관리자와 최종 사용자는 분석을 위해 Microsoft에 전자 메일 메시지(잘못된 메일 또는 잘못된 메일로 표시된 양호한 메일)를 Microsoft에 전자 메일로 전송하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ea2aa0fd8d325113a1891d40e392ac5e3be6e35b
ms.sourcegitcommit: 4b1bf6e4f4a0c016d148cdde7f7880dd774403d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2021
ms.locfileid: "59988226"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>수동으로 Microsoft에 분석용 메시지 제출

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 사서함이 있는 조직의 관리자인 Exchange Online 포털의 제출 페이지를 사용하는 Microsoft 365 Defender  좋습니다. 자세한 내용은 제출 포털을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 [Microsoft에 제출을 참조하세요.](admin-submission.md)

조직의 사용자가 받은 편지함에서 정크 메시지(스팸) 또는 피싱 메시지를 받거나 정크 메일로 표시되어 합법적인 전자 메일 메시지를 받지 못하면 좌절할 수 있습니다. 스팸 필터의 정확도를 더 정확하게 조정하고 있습니다.

사용자와 사용자는 분석을 위해 가음성(나쁜 것으로 표시된 양호한 전자 메일), 거짓 부정(잘못된 메일 허용) 및 피싱 메시지를 Microsoft에 제출하여 이 프로세스를 지원할 수 있습니다.

> [!NOTE]
> 수신하는 제출의 양이 높기 때문에 분석에 대한 모든 요청에 응답하지 않을 수 있습니다.

## <a name="submit-false-negatives-to-microsoft"></a>Microsoft에 거짓 부정 제출

> [!TIP]
> 다음 절차에 따라 거짓 부정을 보고하는 대신 Outlook 및 웹용 Outlook(이전의 Outlook Web App)의 사용자는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용할 수 있습니다. 이러한 도구를 설치하고 사용하는 방법에 대한 자세한 내용은 [보고서](enable-the-report-message-add-in.md) 메시지 추가 기능 사용 및 피싱 보고서 추가 기능 사용을 [참조하세요.](enable-the-report-phish-add-in.md)

스팸 필터링을 통과하여 스팸 또는 피싱으로 식별된 메시지를 받은 경우 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀에 적절하게 메시지를 제출할 수 있습니다. 분석가가 메시지를 검토하고 분류 기준을 충족하는 경우 서비스 전체 필터에 추가합니다.

1. 다음 받는 사람 중 하나를 사용하여 비어 있는 새 전자 메일 메시지를 만드십시오.

   - **정크**: `junk@office365.microsoft.com`
   - **피싱**: `phish@office365.microsoft.com`

2. 정크 또는 피싱 메시지를 새 메시지로 끌어서 놓습니다. 이렇게 하면 정크 또는 피싱 메시지가 새 메시지의 첨부 파일로 저장됩니다. 메시지 헤더를 검사할 수 있도록 원본 메시지가 필요하여 메시지의 내용을 복사하여 붙여 넣지 않습니다.

   > [!NOTE]
   >
   > - 새 메시지에 여러 메시지를 첨부할 수 있습니다. 모든 메시지가 피싱 메시지 또는 정크 메일 메시지와 같은 유형으로 표시해야 합니다.
   > - 새 메시지의 본문은 비워 둡니다.
   > - 첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(웹 Outlook 형식의 기본 형식) 형식을 사용할 수 있습니다.

3. 완료되면 보내기 를 **클릭합니다.**

> [!TIP]
> 관리자는 스팸으로 오인되는 특정 메시지를 차단하는 여러 가지 방법을 사용할 수 있습니다. 자세한 내용은 [EOP에서 차단된 보낸 사람 목록 만들기를 참조하세요.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Microsoft에 가짓 긍정 제출

> [!TIP]
> 다음 절차에 따라 가짓 긍정을 보고하는 대신, Outlook 및 웹용 Outlook 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용할 수 있습니다. 이러한 도구를 설치하고 사용하는 방법에 대한 자세한 내용은 [보고서](enable-the-report-message-add-in.md) 메시지 추가 기능 사용 및 피싱 보고서 추가 기능 사용을 [참조하세요.](enable-the-report-phish-add-in.md)

메시지가 스팸으로 잘못 식별된 경우 Microsoft 스팸 분석 팀에 메시지를 제출할 수 있습니다. 분석가가 메시지를 평가하고 분석 결과에 따라 메시지 통과를 허용하도록 서비스 전체 필터를 조정할 수 있습니다.

1. 받는 사람으로 새 비어 있는 전자 `not_junk@office365.microsoft.com` 메일 메시지를 만들 수 있습니다.

2. 잘못 확인된 메시지를 새 메시지로 끌어서 놓습니다. 이렇게 하면 잘못 확인된 메시지가 새 메시지의 첨부 파일로 저장됩니다. 메시지 헤더를 검사할 수 있도록 원본 메시지가 필요하여 메시지의 내용을 복사하여 붙여 넣지 않습니다.

   > [!NOTE]
   >
   > - 새 메시지에 여러 메시지를 첨부할 수 있습니다. 모든 메시지가 피싱 메시지 또는 정크 메일 메시지와 같은 유형으로 표시해야 합니다.
   > - 새 메시지의 본문은 비워 둡니다.
   > - 첨부된 메시지에 .msg(기본 Outlook 형식) 또는 .eml(웹 Outlook 형식의 기본 형식) 형식을 사용할 수 있습니다.

3. 완료되면 보내기 를 **클릭합니다.**

> [!TIP]
> 관리자는 특정 메시지가 스팸 필터링을 건너뛸 수 있도록 여러 가지 방법을 사용할 수 있습니다. 자세한 내용은 EOP에서 수신이 가능한 보낸 사람 [목록 만들기를 참조하세요.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Microsoft에 전송되는 데이터는 어디에 저장되어 있나요?

데이터는 북미 데이터 센터의 Office 365 규정 준수 경계에 있습니다. 이 데이터는 필터링 효과를 개선하는 데 도움을 주기 위해 엔지니어링 팀의 분석가가 검토합니다.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft에 보고된 메시지의 복사본을 받는 메일 흐름 규칙 만들기

자세한 내용은 메일 흐름 규칙을 사용하여 Microsoft에 보고하는 사용자 [확인을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)
