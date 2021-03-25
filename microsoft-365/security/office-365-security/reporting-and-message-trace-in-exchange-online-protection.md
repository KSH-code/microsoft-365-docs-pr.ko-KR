---
title: 보고 및 메시지 추적
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 EOP(Microsoft Exchange Online 보호) 관리자에게 사용할 수 있는 보고서 및 문제 해결 도구에 대해 알아보고 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5e5493925a17725bfb9d6698b3f94050960ccc7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205721"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP의 보고 및 메시지 추적

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 조직의 전반적인 상태를 확인하는 데 도움이 되는 다양한 보고서를 제공합니다. 받는 사람에게 메시지가 도착하지 않는 등 특정 이벤트에 대한 문제를 해결할 수 있는 도구와 규정 준수 요구 사항을 지원하는 감사 보고서도 있습니다.

## <a name="usage-reports"></a>사용 현황 보고서

**Microsoft 365 그룹 활동:** 생성 및 사용되는 Microsoft 365 그룹의 수에 대한 정보를 볼 수 있습니다.

**전자 메일 활동:** 전체 조직 및 특정 사용자가 보내고, 받고, 읽은 메시지 수에 대한 정보를 읽습니다.

**전자 메일 앱 사용:** 사용되는 전자 메일 앱에 대한 정보를 볼 수 있습니다. 여기에는 각 앱의 총 연결 수와 연결되는 Outlook 버전이 포함됩니다.

**사서함 사용:** 사서함에 대해 사용된 저장소, 할당량 소비, 항목 수 및 마지막 활동(보내기 또는 읽기 활동)에 대한 정보를 읽습니다.

자세한 내용은 다음 리소스를 참조하세요.

- [관리 센터의 Microsoft 365 보고서 - Microsoft 365 그룹](../../admin/activity-reports/office-365-groups.md)

- [관리 센터의 Microsoft 365 보고서 - 전자 메일 활동](../../admin/activity-reports/email-activity.md)

- [관리 센터의 Microsoft 365 보고서 - 전자 메일 앱 사용 현황](../../admin/activity-reports/email-apps-usage.md)

- [관리 센터의 Microsoft 365 보고서 - 사서함 사용량](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Microsoft & 센터의 보안 및 규정 준수 보고서

이러한 향상된 보고서는 요약 정보와 자세한 내용을 드릴다운하는 기능을 포함하는 EOP 관리자를 위한 대화형 보고 환경을 제공합니다.

**Defender for Office 365: Office 365용** Microsoft Defender의 일부인 안전한 링크 및 안전한 첨부 파일에 대한 정보를 볼 수 있습니다.

**EOP:** 맬웨어 검색, 스푸핑된 메일, 스팸 검색 및 조직과의 메일 흐름에 대한 정보를 볼 수 있습니다.

[Office 365용 Defender에 대한 보고서 보기](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph를 사용한 사용자 지정 보고서

Microsoft Graph를 사용하여 관리 센터에서 사용할 수 있는 보고서를 프로그래밍식으로 만들 수 있습니다. 자세한 내용은 [Microsoft Graph 개요](/graph/overview) 및 Microsoft [Graph에서 Office 365](/graph/api/resources/report)사용 현황 보고서 작업을 참조하세요.

## <a name="message-trace"></a>Message trace

EOP를 통과하는 전자 메일 메시지를 추적합니다. 이를 통해 서비스에서 전자 메일 메시지를 수신, 거부, 지연 또는 배달했는지 여부를 확인할 수 있습니다. 또한 최종 상태에 도달하기 전에 메시지에 대해 수행된 작업도 보여 주며,

이 정보를 사용하여 사용자의 질문에 효율적으로 답변하고, 메일 흐름 문제를 해결하고, 정책 변경의 유효성을 검사하고, 기술 지원에 도움을 요청해야 하는 필요성을 해결할 수 있습니다.

보안 [및 준수 센터에서 & 추적을 참조합니다.](message-trace-scc.md)

## <a name="audit-logging"></a>감사 로깅

조직 관리자가 변경한 특정 내용을 추적합니다. 이러한 보고서를 사용하면 구성 문제를 해결하거나 보안 또는 규정 준수 관련 문제의 원인을 찾을 수 있습니다. [EOP의 감사 보고서를 참조합니다.](auditing-reports-in-eop.md)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>보고 및 메시지 추적 데이터 사용 가능 여부 및 대기 시간

다음 표에는 EOP 보고 및 메시지 추적 데이터를 사용할 수 있는 시기와 기간에 대한 설명이 나와 있습니다.

****

|보고서 유형|데이터 사용 가능 기간(확인 기간)|대기 시간|
|---|---|---|
|메일 보호 요약 보고서|90일|메시지 데이터 집계는 대부분 24~48시간 이내에 완료됩니다. 일부 사소한 증분 집계 변경의 경우 5일까지 소요될 수 있습니다.|
|메일 보호 세부 정보 보고서|90일|7일 미만의 세부 데이터는 24시간 이내에 표시되지만 48시간이 될 때까지 완료되지 않을 수 있습니다. 일부 사소한 증분 변경의 경우 5일까지 소요될 수 있습니다. <p> 7일이 지난 메시지에 대한 상세 보고서를 보려면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.|
|메시지 추적 데이터|90일|7일 미만의 메시지에 대해 메시지 추적을 실행하면 메시지가 5~30분 이내에 표시되어야 합니다.<p> 7일이 지난 메시지에 대해 메시지 추적을 실행하면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.|
|

> [!NOTE]
> 데이터 가용성 및 대기 시간은 관리 센터 또는 원격 PowerShell을 통해 요청된 경우와 동일합니다.