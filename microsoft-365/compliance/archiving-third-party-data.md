---
title: 타사 데이터 보관
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 Microsoft 365 사서함으로 타사 데이터를 가져오는 방법을 학습합니다.
ms.openlocfilehash: 83ba81907a9db8dd1f4e95e5df3306366838c1ba
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163653"
---
# <a name="archive-third-party-data"></a>타사 데이터 보관

Microsoft 365를 사용하면 관리자가 데이터 커넥터를 사용하여 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 Microsoft 365 조직의 사서함으로 타사 데이터를 가져오고 보관할 수 있습니다. 데이터 커넥터를 사용하여 Microsoft 365에서 타사 데이터를 가져오고 보관할 때의 한 가지 주요 이점은 가져온 후 다양한 Microsoft 365 규정 준수 솔루션을 적용할 수 있습니다. 이렇게 하면 조직의 비 Microsoft 데이터가 조직에 영향을 주는 규정 및 표준을 준수하는지 보장할 수 있습니다.

## <a name="third-party-data-connectors"></a>타사 데이터 커넥터

다음 표에는 Microsoft 365 규정 준수 센터에서 사용할 수 있는 타사 데이터 커넥터가 나열됩니다. 이 표에는 Microsoft 365에서 가져오고 보관한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션도 요약됩니다. 각 규정 [준수 솔루션에](#overview-of-compliance-solutions-that-support-third-party-data) 대한 자세한 설명과 타사 데이터에 도움이 될 수 있는 방법에 대한 자세한 내용은 다음 섹션을 참조하세요.

> [!TIP]
> 타사 데이터 열의 링크를 클릭하여 해당 데이터 형식에 대한 커넥터를 만들기 위한 단계별 지침으로 이동하십시오. 

|타사 데이터  |소송 보류|eDiscovery  |보존 설정  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[AT&T 네트워크 <sup>1</sup>](archive-att-network-archiver-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[종 네트워크 <sup>1</sup>](archive-bell-network-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[블룸버그 메시지](archive-bloomberg-message-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Enterprise 번호 <sup>1</sup>](archive-enterprise-number-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[인사(인사)](import-hr-data.md) ||||||![확인 표시](../media/checkmark.png)
|[ICE 채팅](archive-icechat-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[MS SQL 데이터베이스 <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[O2 네트워크 <sup>1</sup>](archive-o2-network-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[물리적 배지](import-physical-badging-data.md) ||||||![확인 표시](../media/checkmark.png)|
|[피벗 <sup>2</sup>](archive-pivot-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[<sup>2를</sup> 다루는 Reuters](archive-reutersdealing-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Symphony <sup>2</sup>](archive-symphony-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[TELUS 네트워크 <sup>1</sup>](archive-telus-network-data.md)    |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[텍스트로 나타선 <sup>2</sup>](archive-text-delimited-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[웹 페이지 <sup>2</sup>](archive-webpagecapture-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Facebook <sup>2의</sup> Workplace](archive-workplacefromfacebook-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[확대/축소 모임 <sup>2</sup>](archive-zoommeetings-data.md)     |![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> TeleMessage에서 제공하는 데이터 커넥터입니다. Microsoft 365에서 데이터를 보관하기 전에 TeleMessage와 함께 조직에 대한 보관 서비스를 설정해야 합니다. 자세한 내용은 이 데이터 형식에 대한 단계별 지침의 선행 단계 섹션을 참조하세요.<br/><br/><sup>2</sup> Veritas에서 제공하는 데이터 커넥터입니다. Microsoft 365에서 데이터를 보관하기 전에 Veritas와 함께 조직의 보관 서비스를 설정해야 합니다. 자세한 내용은 이 데이터 형식에 대한 단계별 지침의 선행 단계 섹션을 참조하세요.

이전 표에 나열된 타사 데이터(HR 데이터 및 물리적 배지 데이터 제외)는 사용자 사서함으로 가져오기됩니다. 타사 데이터를 지원하는 해당 준수 솔루션은 데이터가 저장되는 사용자 사서함에 적용됩니다.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>타사 데이터를 지원하는 규정 준수 솔루션 개요

다음 섹션에서는 Microsoft 365 규정 준수 솔루션이 이전 표에 나열된 타사 데이터를 관리하는 데 도움이 되는 몇 가지 방법을 설명합니다.

### <a name="litigation-hold"></a>소송 보류

사용자 [사서함에](create-a-litigation-hold.md) 소송 보존을 설정하여 타사 데이터를 보존합니다. 보류를 만들 때 삭제 및 수정된 타사 데이터가 지정된 기간 동안 보존된 다음 사서함에서 영구적으로 삭제될 수 있도록 보존 기간(시간 기반 보류라고도함)을 지정할 수 있습니다. 또는 콘텐츠를 무기한 보존(무한 보존)하거나 소송 보존이 제거될 때까지 보존할 수 있습니다. 

### <a name="ediscovery"></a>eDiscovery

Microsoft 365의 세 가지 기본 eDiscovery 도구는 콘텐츠 검색, Core eDiscovery 및 Advanced eDiscovery입니다.

- **[콘텐츠 검색](content-search.md).** 콘텐츠 검색 도구를 사용하여 사서함에서 가져온 타사 데이터를 검색할 수 있습니다. 검색 쿼리 및 조건을 사용하여 검색 결과 범위를 좁히고 검색 결과를 내보낼 수 있습니다.

- **[Core eDiscovery](get-started-core-ediscovery.md).** 이 도구는 사례 데이터에 액세스할 수 있는 사용자를 제어하고, 검색 조건과 일치하는 사용자 사서함 또는 사서함 콘텐츠를 보류할 수 있는 사례를 만들 수 있도록 하여 기본 검색 및 내보내기 기능을 구축합니다. 즉, 사용자 사서함으로 가져온 타사 데이터에 eDiscovery 보류를 사용할 수 있습니다.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** 이 강력한 도구는 보유자도 사례에 추가하고 보유자 데이터를 보류한 다음 테마 및 중복 검색과 같은 추가 분석을 위해 보유자 데이터를 검토에 로드하여 Core eDiscovery의 사례 기능을 확장합니다. 타사 데이터를 검토 집합에 로드한 후 쿼리하고 좁은 결과 집합으로 필터링할 수 있습니다.

   Core eDiscovery 및 Advanced eDiscovery를 통해 조직의 법률 또는 내부 조사와 관련이 있을 수 있는 타사 데이터를 관리할 수 있습니다.

### <a name="retention-settings"></a>보존 설정

보존 기간이 [](retention.md) 만료된 후 사용자 사서함에 보존 정책을 적용하여 타사 데이터(및 기타 사서함 콘텐츠)를 보존하고 삭제할 수 있습니다. 또한 보존 정책을 사용하여 특정 보존 기간의 타사 [](disposition.md) 데이터를 삭제하거나 보존 레이블을 사용하여 타사 데이터의 보존 기간이 만료될 때 처리 검토를 트리거할 수 있습니다.

### <a name="records-management"></a>레코드 관리

Microsoft [](records-management.md) 365의 레코드 관리 기능을 사용하면 타사 데이터를 레코드로 선언할 수 있습니다. 사서함의 타사 데이터를 레코드로 표시하는 보존 레이블을 적용하는 사용자가 수동으로 이행할 수 있습니다. 또는 타사 데이터에서 중요한 정보, 키워드 또는 콘텐츠 형식을 식별하여 보존 레이블을 자동으로 적용할 수 있습니다.

### <a name="communication-compliance"></a>커뮤니케이션 규정 준수

커뮤니케이션 규정 [준수를](communication-compliance.md) 사용하여 타사 데이터를 검사하여 조직의 데이터 표준을 준수하는지 검사할 수 있습니다. 이 작업은 조직에서 부적절한 메시지에 대한 수정 작업을 검색, 캡처 및 수행하여 수행할 수 있습니다. 예를 들어, 비방적인 언어, 중요한 정보 및 규정 준수에 대해 가져오는 타사 데이터를 모니터링할 수 있습니다.

### <a name="insider-risk-management"></a>내부 위험 관리

선택적 HR 데이터와 같은 타사 데이터의 신호를 내부자 [](insider-risk-management.md) 위험 관리 솔루션에서 사용하여 조직의 위험한 활동을 감지, 조사 및 작업할 수 있도록 하여 내부 위험을 최소화할 수 있습니다. 예를 들어 HR 데이터 커넥터에서 가져온 데이터는 퇴사하는 직원 데이터 도용을 감지하는 데 도움이 되는 위험 지표로 사용됩니다.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft 파트너와 협력하여 타사 데이터 보관

타사 데이터를 가져오고 보관하는 또 다른 옵션은 조직이 Microsoft 파트너와 협력할 수 있도록 하는 것입니다. Microsoft 규정 준수 센터에서 사용할 수 있는 데이터 커넥터에서 타사 데이터 형식이 지원되지 않는 경우 타사 데이터 원본에서 항목을 정기적으로 추출하도록 구성되는 사용자 지정 커넥터를 제공할 수 있는 파트너와 협력한 다음 타사 API를 통해 Microsoft 클라우드에 연결하고 해당 항목을 Microsoft 365로 가져올 수 있습니다. 또한 파트너 커넥터는 타사 데이터 원본의 항목 콘텐츠를 전자 메일 메시지로 변환한 다음 Microsoft 365의 사서함으로 가져와야 합니다.

함께 작업할 수 있는 파트너 목록과 이 방법에 대한 단계별 프로세스는 [Microsoft 365에서](work-with-partner-to-archive-third-party-data.md)타사 데이터를 보관하기 위해 파트너와 협력을 참조하세요.
