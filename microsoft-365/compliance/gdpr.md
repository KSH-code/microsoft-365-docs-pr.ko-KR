---
title: 일반 데이터 보호 규정
description: GDPR(일반 데이터 보호 규정)에 대한 Microsoft 기술 지침
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: d64d9b98fe3cf24a14b3f3126ff3f38b1d84087d
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2020
ms.locfileid: "41557985"
---
# <a name="general-data-protection-regulation-summary"></a>일반 데이터 보호 규정 요약

GDPR(일반 데이터 보호 규제)는 EU(유럽 연합) 회원국 국민에게 제품과 서비스를 제공하거나 귀하 또는 귀사가 어디에 있는지 관계없이 EU 거주자의 데이터를 수집하고 분석하는 조직에 새로운 규칙을 도입합니다.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQI] 

이 문서에서는 Microsoft 제품 및 서비스를 사용하는 경우 GDPR에서 권리를 부여하고 의무를 이행하는 데 도움이 되는 정보를 안내합니다. [GDPR에 대한 권장 실행 계획](gdpr-action-plan.md) 및 [책임 준비 상태 검사 목록](gdpr-arc.md)에서는 GDPR 규정 준수를 평가하고 구현하기 위한 추가 리소스를 제공합니다.

## <a name="terminology"></a>용어

이 문서에서 사용된 GDPR 용어에 대한 유용한 정의:

- *데이터 컨트롤러(컨트롤러)*: 개인 데이터 처리의 목적과 수단을 결정하는 법인, 공공 기관, 에이전시 또는 다른 사람과 독립적으로 또는 공동으로 작업하는 기타 단체입니다.  
- *개인 데이터* 및 *데이터 주체*: 식별되거나 식별 가능한 자연인(데이터 주체)과 관련된 모든 정보. 식별 가능한 자연인은 직접 또는 간접적으로 식별될 수 있는 사람입니다.  
- *프로세서*: 컨트롤러를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 에이전시 또는 기타 단체입니다.  
- *고객 데이터*: 비즈니스 운영의 일상적인 작업에서 생성되고 저장되는 데이터입니다.

## <a name="what-is-the-gdpr"></a>GDPR이란?

GDPR에서는 조직에서 수집한 개인 데이터를 관리할 수 있는 권한을 사용자에 게 제공합니다. 이러한 권한은 DSR(데이터 주체 요청)을 통해 행사할 수 있습니다. 조직은 DSR 및 데이터 위반과 관련된 시기 적절한 정보를 제공하고, DPIA(데이터 보호 영향 평가)를 수행해야 합니다.

GDPR 요구 사항을 구현하거나 평가할 때는 몇 가지 사항을 고려해야 합니다.

- GDPR 규정 준수 데이터 개인 정보 보호 정책 개발 또는 평가
- 조직의 데이터 보안 평가.
- 누가 데이터 컨트롤러인가요?
- 수행해야 하는 데이터 보안 프로세스는 무엇인가요?

[GDPR에 대한 권장 실행 계획](gdpr-action-plan.md) 및 [책임 준비 상태 검사 목록](gdpr-arc.md)에 따라 추가적인 사항들을 고려해야 할 수 있습니다.

GDPR 표준을 충족하기 위해 다음과 같은 작업이 수행됩니다. 구현에 대 한 자세한 내용을 보려면 목록에 있는 링크를 따라 이동합니다.  

- **[DSR(데이터 주체 요청)](gdpr-data-subject-requests.md)**. 데이터 주체가 개인 데이터와 관련해서 작업(변경, 제한, 액세스)을 수행하도록 컨트롤러에게 공식적으로 요청하는 것입니다.
- **[위반 알림](gdpr-breach-notification.md)**. GDPR에서 개인 데이터 위반은 “전송, 저장 또는 기타 방식으로 처리되는 개인 데이터의 의도치 않았거나 불법적인 파괴, 손실, 변경, 무단 공개 또는 액세스를 야기하는 보안 침해”를 의미합니다.
- **[DPIA(데이터 보호 영향 평가)](gdpr-data-protection-impact-assessments.md)**. 데이터 컨트롤러는 GDPR에 따라 "자연인의 권리와 자유에 대한 높은 위험을 초래할 가능성이 있는" 데이터 작업에 대해 DPIA를 준부히야 합니다.

위에서 설명한 것처럼, GDPR의 권장 실행 계획 및 책임 준비 상태 검사 목록은 Microsoft 제품 및 서비스를 사용하여 GDPR 준수을 구현하거나 평가하기 위한 지침을 제공합니다.

## <a name="the-gdpr-in-action"></a>GDPR 수행

이 섹션에서는 위에 언급된 GDPR 작업을 완료하는 간략한 방법과 고려 사항을 설명합니다. 이러한 작업의 완료는 Microsoft 구성에 따라 다를 수 있습니다.

### <a name="data-subject-request-dsr"></a>DSR(데이터 주체 요청)

데이터 주체 요청은 데이터 주체가 GDPR에 따라 자신의 권한을 행사하는 수단을 제공합니다. 컨트롤러는 시기 적절한 GDPR 일치 응답을 제공해야 합니다. 아래에 고려해야 하는 질문이 나와 있습니다. 기술 세부 정보에 대해서는 [데이터 주체 요청](gdpr-data-subject-requests.md)을 참조하세요.  

- **DSR을 완료하는 데 필요한 작업은 무엇인가요?**: DSR에는 6가지 활동인 검색, 액세스, 수정, 제한, 내보내기 및 삭제가 포함됩니다.
- **데이터 원본이란 무엇인가요?**: Excel 및 Outlook과 같은 [Office 애플리케이션](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)에서 조직 데이터의 상당 부분이 생성됩니다.  Microsoft 제품 및 서비스에서 생성된 [인사이트](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)와 [시스템 생성 로그](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)에서도 DSR 관련 데이터를 찾을 수 있습니다.
- **어떤 종류의 데이터를 검색해야 하나요?**: 개인 데이터는 고객 데이터, Microsoft 제품 및 서비스에서 생성된 인사이트 및 시스템 생성 로그에서 찾을 수 있습니다.
- **개인 데이터는 어떤 방식으로 검색되나요?**: 개인 데이터 검색은 Microsoft 제품 및 서비스에 따라 다를 수 있습니다. 검색 도구에는 [콘텐츠 검색](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) 또는 [앱 내 검색](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs) 용량이 포함됩니다. 관리자는 사용자 활동과 연결된 [시스템 생성 로그](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)에 액세스할 수 있습니다.  
- **개인 데이터는 어떤 형식으로 사용할 수 있어야 하나요?**: GDPR "데이터 이동권"을 통해 데이터 주체는 "구조화되고 자주 사용되며 컴퓨터가 읽을 수 있는 형식"으로 된 개인 데이터의 복사본을 요청하고, 조직에서 이러한 파일을 다른 데이터 통제자에게 전송하도록 요청할 수 있습니다.

### <a name="data-protection-impact-assessment"></a>데이터 보호 영향 평가

GDPR에 따라 데이터 컨트롤러는 "자연인의 권리와 자유에 대한 높은 위험을 초래할 가능성이 있는" 작업을 처리하기 위해 DPIA([데이터 보호 영향 평가](gdpr-data-protection-impact-assessments.md))를 준비해야 합니다. DPIA를 만들어야 하는 Microsoft 제품 및 서비스에는 아무것도 내제되어 있지 않습니다. 오히려 Microsoft 구성의 세부 정보에 따라 다릅니다.

DPIA와 관련된 몇 가지 고려 사항은 다음과 같습니다. Office에서 고려해야 하는 세부 정보 목록은 [DPIA 콘텐츠](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)에서 찾을 수 있습니다.

- 개인 데이터 보안을 침해할 수 있는 조직의 데이터 작업에는 어떤 것이 있나요?
- Microsoft 제품 및 서비스 구성이 데이터 위반에 취약해질 수 있나요?
- DPIA는 언제 수행해야 하나요?

    - 컨트롤러는 개인 데이터 보안 위험이나 데이터 위반이 발생할 경우 DPIA 조치를 수행해야 합니다. Office의 위험 요인에 대한 구체적인 예는 [DPIA가 필요한지 여부 파악](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed)에 나와 있습니다.  

- DPIA를 완료하는 데 필요한 것은 무엇인가요?

    DPIA에 포함되는 GDPR 권한에는 다음이 포함됩니다.  
    - DPIA의 목적과 관련한 데이터 처리의 필요성 및 비례의 원칙 평가
    - 데이터 주체의 권리와 자유에 대한 위험 평가
    - 의도된 위험 해결 조치, 안전 조치, 보안 조치 및 개인 정보 보호를 보장하고 GDPR 준수를 입증하는 메커니즘.

### <a name="breach-notification"></a>위반 알림

Microsoft는 데이터 프로세서로서, 고객이 GDPR의 위반 알림 요구 사항을 충족할 수 있도록 합니다. 데이터 컨트롤러는 데이터 개인 정보에 대한 위험을 평가하고 고객의 DPA에게 알려야 하는 위반인지 여부를 파악해야 합니다. Microsoft는 이러한 평가에 필요한 정보를 제공합니다. Microsoft에서 개인 데이터 위반을 감지하고 대처하는 방법에 대한 자세한 내용은 [GDPR에서 데이터 위반 알림](gdpr-breach-notification.md)에 나와 있습니다. 몇 가지 위반 알림 질문은 다음과 같습니다.

- 데이터 주체에게 위반에 대한 어떤 정보를 제공해야 하나요?
- 데이터 주체에게 어떤 방법(전자 메일, 작성된 알림 등)으로 알리나요?

### <a name="accountability-readiness-checklists-for-the-gdpr"></a>GDPR에 대한 책임 준비 상태 검사 목록

이러한 [검사 목록](gdpr-arc.md)은 Microsoft 제품 사용 시 GDPR을 지원하는 데 필요할 수 있는 정보에 편리하게 액세스할 수 있습니다. GDPR 타일의 고객 관리 컨트롤에서 컨트롤 ID 및 컨트롤 제목을 참조하여 [준수 점수](compliance-score.md)를 통해 이 검사 목록의 항목을 관리할 수 있습니다.

## <a name="learn-more"></a>자세한 정보

- [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
