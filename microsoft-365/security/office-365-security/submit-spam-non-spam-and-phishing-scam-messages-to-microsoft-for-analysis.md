---
title: 분석을 위해 Microsoft에 수동으로 메시지 전송
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 관리자 및 최종 사용자는 분석을 위해 Microsoft에 전자 메일 메시지 (잘못 되었거나 잘못 된 메일을 허용 하는 것으로 표시 된 좋은 메일)를 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e90382b39b0cebb70568a53ac5aaeb40ac935f92
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653596"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>분석을 위해 Microsoft에 수동으로 메시지 전송

> [!NOTE]
> Exchange Online 사서함을 사용 하는 조직의 관리자 인 경우 보안 & 준수 센터에서 전송 포털을 사용 하는 것이 좋습니다. 자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.

조직의 사용자가 받은 편지함에서 정크 메시지 (스팸) 나 피싱 메시지를 받거나, 정크로 표시 되어 합법적인 전자 메일 메시지를 받지 못하는 경우에는 혼란을 가져올 수 있습니다. Microsoft는 스팸 필터를 보다 정확 하 게 미세 조정 하 고 있습니다.

귀하와 사용자는 가양성 (잘못 된 것으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 메일 허용), 분석을 위해 Microsoft에 피싱 메시지를 제출 하 여이 프로세스를 지원할 수 있습니다.

> [!NOTE]
> 수신 되는 전송 양이 많기 때문에 분석을 위해 모든 요청에 응답 하지 못할 수 있습니다.

## <a name="submit-false-negatives-to-microsoft"></a>Microsoft에 거짓 네거티브 전송

> [!TIP]
> 다음 절차를 사용 하 여 거짓 네거티브를 보고 하는 대신 Outlook 및 웹용 Outlook (이전의 Outlook Web App)에 있는 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다. 이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.

스팸 또는 피싱으로 식별 되어야 하는 스팸 필터링을 통해 전달 된 메시지를 수신 하는 경우 Microsoft 스팸 분석 및 Microsoft 피싱 분석 팀에 적절 하 게 메시지를 제출할 수 있습니다. 분석가는 메시지를 검토 하 고 해당 메시지가 분류 기준을 충족 하는 경우 서비스 전체 필터에 추가 합니다.

1. 다음 받는 사람 중 하 나와의 비어 있는 새 전자 메일 메시지를 만듭니다.

   - **정크 메일**: `junk@office365.microsoft.com`

   - **피싱**: `phish@office365.microsoft.com`

2. 정크 또는 피싱 메시지를 새 메시지에 끌어서 놓습니다. 이렇게 하면 정크 또는 피싱 메시지가 새 메시지에 첨부 파일로 저장 됩니다. 메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).

   > [!NOTE]
   >
   > - 새 메시지에 여러 메시지를 첨부할 수 있습니다. 모든 메시지의 유형 (피싱 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.
   >
   > - 새 메시지의 본문은 비워 둡니다.
   >
   > - 첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.

3. 작업이 완료 되 면 **보내기를**클릭 합니다.

> [!TIP]
> 관리자는 스팸으로 잘못 식별 되어는 특정 메시지를 차단 하는 여러 가지 방법을 제공 합니다. 자세한 내용은 [EOP에서 차단 된 보낸 사람 목록 만들기](create-block-sender-lists-in-office-365.md)를 참조 하십시오.

## <a name="submit-false-positives-to-microsoft"></a>Microsoft에 가양성 제출

> [!TIP]
> 다음 절차를 사용 하 여 가양성을 보고 하는 대신 Outlook 및 웹용 Outlook의 사용자가 Microsoft Outlook 용 보고서 메시지 추가 기능을 사용할 수 있습니다. 이 도구를 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 [보고서 메시지 추가 기능을 사용 하도록 설정을](enable-the-report-message-add-in.md)참조 하십시오.

메시지가 스팸으로 잘못 식별 된 경우 Microsoft 스팸 분석 팀에 메시지를 제출할 수 있습니다. 분석가는 메시지를 평가 하 고, 분석 결과에 따라, 서비스 전체 필터를 통해 메시지를 통과 하도록 조정할 수 있습니다.

1. 받는 사람이 다음과 같은 비어 있는 새 전자 메일 메시지를 만듭니다 `not_junk@office365.microsoft.com` .

2. 잘못 식별 되어 메시지를 끌어서 새 메시지에 놓습니다. 이렇게 하면 잘못 식별 되어 메시지가 새 메시지에 첨부 파일로 저장 됩니다. 메시지의 내용을 복사 하 여 붙여넣거나 메시지를 전달 하지 않습니다 (메시지 헤더를 검사할 수 있도록 원본 메시지가 필요 함).

   > [!NOTE]
   >
   > - 새 메시지에 여러 메시지를 첨부할 수 있습니다. 모든 메시지의 유형 (피싱 메시지 또는 정크 메일 메시지)이 동일한 지 확인 합니다.
   >
   > - 새 메시지의 본문은 비워 둡니다.
   >
   > - 첨부 된 메시지의 형식은 .msg (기본 Outlook 형식) 또는 .eml (기본 outlook 형식) 중 하나를 사용 합니다.

3. 작업이 완료 되 면 **보내기를**클릭 합니다.

> [!TIP]
> 관리자는 특정 메시지에서 스팸 필터링을 건너뛰는 여러 가지 방법을 사용할 수 있습니다. 자세한 내용은 [EOP에서 수신 허용-보낸 사람 목록 만들기](create-safe-sender-lists-in-office-365.md)를 참조 하십시오.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft에 보고 되는 메시지의 복사본을 수신 하는 메일 흐름 규칙 만들기

자세한 내용은 [메일 흐름 규칙을 사용 하 여 사용자가 Microsoft에 보고 하는 항목 보기](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)를 참조 하세요.
