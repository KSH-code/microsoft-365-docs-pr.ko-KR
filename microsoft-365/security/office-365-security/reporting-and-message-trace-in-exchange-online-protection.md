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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 EOP(Microsoft Exchange Online Protection) 관리자에게 사용할 수 있는 보고서 및 문제 해결 도구에 대해 알아봅니다.
ms.openlocfilehash: 149f7fa36a717a92d3cda5f6f3f82651f0144d73
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827632"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP의 보고 및 메시지 추적

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 조직의 전체 상태를 확인할 수 있는 다양한 보고서를 제공합니다. 받는 사람에게 메시지가 도착하지 않는 등 특정 이벤트에 대한 문제를 해결할 수 있는 도구와 규정 준수 요구 사항을 지원하는 감사 보고서도 있습니다.

## <a name="usage-reports"></a>사용 현황 보고서

**Microsoft 365 그룹 활동:** 생성되고 사용되는 Microsoft 365 그룹 수에 대한 정보를 확인하세요.

**전자 메일 활동:** 전체 조직에서 보내고, 받은 메시지 수 및 특정 사용자에 대한 정보를 확인합니다.

**메일 앱 사용:** 사용되는 메일 앱에 대한 정보를 봅니다. 각 앱에 대한 총 연결 수 및 연결하고 있는 Outlook 버전이 포함됩니다.

**사서함 사용량:** 사서함의 사용된 저장소, 할당량 소비, 항목 수 및 마지막 활동(보내기 또는 읽기 활동)에 대한 정보를 확인합니다.

자세한 내용은 다음 리소스를 참조하세요.

- [관리 센터의 Microsoft 365 보고서 - Microsoft 365 그룹](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [관리 센터의 Microsoft 365 보고서 - 전자 메일 활동](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [관리 센터의 Microsoft 365 보고서 - 전자 메일 앱 사용](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [관리 센터의 Microsoft 365 보고서 - 사서함 사용량](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>보안 & Microsoft 365 관리 센터의 보안 정책 준수 보고서

이 향상된 보고서에서는 EOP 관리자에게 요약 정보 및 자세한 내용을 예로 다루는 기능을 제공하는 EOP 관리용 대화형 보고 환경이 제공됩니다.

**ATP(Advanced Threat Protection): ATP의**일부인 안전한 링크 및 안전한 첨부 파일에 대한 정보를 확인합니다.

**EOP**: 맬웨어 검색, 스푸핑된 메일, 스팸 검색 및 조직과의 메일 흐름에 대한 정보를 확인합니다.

[Office 365 Advanced Threat Protection 보고서 보기](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph를 사용한 사용자 지정 보고서

프로그래밍 방식으로 Microsoft Graph를 사용하여 관리 센터에서 사용할 수 있는 보고서를 만듭니다. 자세한 내용은 Microsoft [Graph의 개요를 확인하고 Microsoft](https://docs.microsoft.com/graph/overview) [Graph에서 Office 365 사용 현황 보고서 작업을 수행합니다.](https://docs.microsoft.com/graph/api/resources/report)

## <a name="message-trace"></a>Message trace

EOP를 통과하는 전자 메일 메시지를 추적합니다. 이를 통해 서비스에서 전자 메일 메시지를 수신, 거부, 지연 또는 배달했는지 여부를 확인할 수 있습니다. 또한 메시지가 최종 상태에 도달하기 전에 메시지에서 수행된 작업을 확인할 수 있습니다.

이 정보를 사용하여 사용자질에 대한 질문에 효율적으로 대답하고, 메일 흐름 문제를 해결하고, 정책 변경 사항의 유효성을 검사할 수 있을 수 있을 것이며 기술 지원팀에 문의해야 하는 수고를 제한할 수 있습니다.

보안 [센터에서 메시지 & 참조하십시오.](message-trace-scc.md)

## <a name="audit-logging"></a>감사 로깅

조직 관리자가 변경한 특정 내용을 추적합니다. 이러한 보고서를 사용하면 구성 문제를 해결하거나 보안 또는 규정 준수 관련 문제의 원인을 찾을 수 있습니다. [EOP에서 감사 보고서를 참조하세요.](auditing-reports-in-eop.md)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>보고 및 메시지 추적 데이터 사용 가능 여부 및 대기 시간

다음 표에는 EOP 보고 및 메시지 추적 데이터를 사용할 수 있는 시기와 기간에 대한 설명이 나와 있습니다.

****

|보고서 유형|데이터 사용 가능 기간(확인 기간)|대기 시간|
|---|---|---|
|메일 보호 요약 보고서|90일|메시지 데이터 집계는 대부분 24~48시간 이내에 완료됩니다. 일부 사소한 증분 집계 변경의 경우 5일까지 소요될 수 있습니다.|
|메일 보호 세부 정보 보고서|90일|7일 미만의 세부 데이터는 24시간 이내에 표시되지만 48시간이 될 때까지 완료되지 않을 수 있습니다. 일부 사소한 증분 변경의 경우 5일까지 소요될 수 있습니다. <br/><br/> 7일이 지난 메시지에 대한 상세 보고서를 보려면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.|
|메시지 추적 데이터|90일|7일 미만의 메시지에 대해 메시지 추적을 실행하면 메시지가 5~30분 이내에 표시되어야 합니다.<br/><br/> 7일이 지난 메시지에 대해 메시지 추적을 실행하면 결과가 표시되는 데 최대 몇 시간이 걸릴 수 있습니다.|
|

> [!NOTE]
> 데이터 사용 가능 여부 및 대기 시간은 관리 센터 또는 원격 PowerShell을 통해 요청하더에 동일한 기능입니다.
