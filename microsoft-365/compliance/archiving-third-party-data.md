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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 타사 데이터를 가져오고 사서함에 보관하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 26b183770599d3c740ad311b759c1bf696e30461
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "60478784"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>타사 데이터를 데이터 저장소에 Microsoft 365

Microsoft 365 사용하여 관리자는 데이터 커넥터를 사용하여 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 타사 데이터를 조직 내 사서함으로 가져오고 보관할 Microsoft 365 있습니다. 데이터 커넥터를 사용하여 타사 데이터를 가져오고 Microsoft 365 한 가지 주요 이점은 가져온 후 다양한 Microsoft 365 규정 준수 솔루션을 적용할 수 있는 것입니다. 이렇게 하면 조직의 비 Microsoft 데이터가 조직에 영향을 주는 규정 및 표준을 준수하는지 보장할 수 있습니다.

## <a name="third-party-data-connectors"></a>타사 데이터 커넥터

이 Microsoft 365 규정 준수 센터 Microsoft의 네이티브 타사 데이터 커넥터를 사용하여 LinkedIn, Instant Bloomberg, Twitter 등의 다양한 데이터 원본과 내부자 위험 관리 솔루션을 지원하는 데이터 커넥터에서 데이터를 가져올 수 있습니다. Microsoft는 이러한 데이터 커넥터 외에도 다음 파트너와 협력하여 데이터 커넥터에 더 많은 세 번째 부분 데이터 커넥터를 Microsoft 365 규정 준수 센터. 조직은 조직에서 해당 데이터 커넥터를 만들기 전에 이러한 파트너와 협력하여 보관 서비스를 Microsoft 365 규정 준수 센터.

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

다음 섹션에 나열된 타사 데이터(Microsoft 365 내부자 위험 관리 솔루션에 사용되는 HR 데이터 및 물리적 배지 데이터 제외)는 사용자 사서함으로 가져오기됩니다. 타사 Microsoft 365 지원하는 규정 준수 솔루션은 데이터가 저장되는 사용자 사서함에 적용됩니다.

### <a name="microsoft-data-connectors"></a>Microsoft 데이터 커넥터

다음 표에는 타사에서 사용할 수 있는 기본 타사 데이터 커넥터가 Microsoft 365 규정 준수 센터. 또한 이 표에는 타사 데이터를 가져오고 보관한 후에 적용할 수 있는 규정 준수 솔루션이 요약되어 Microsoft 365. 각 준수 [솔루션에](#overview-of-compliance-solutions-that-support-third-party-data) 대한 자세한 설명과 타사 데이터를 지원하는 방법에 대한 자세한 내용은 타사 데이터를 지원하는 규정 준수 솔루션 개요 섹션을 참조하세요.

타사 데이터 열의 링크를 클릭하여 해당 데이터 형식에 대한 커넥터를 만들기 위한 단계별 지침으로 이동하십시오. 

|타사 데이터  |소송 보류|eDiscovery  |보존 설정  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[블룸버그 메시지](archive-bloomberg-message-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[인사(인사)](import-hr-data.md) ||||||![확인 표시](../media/checkmark.png)
|[ICE 채팅](archive-icechat-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[물리적 배지](import-physical-badging-data.md) ||||||![확인 표시](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Veritas 데이터 커넥터

이 섹션의 표에는 Veritas와 함께 사용할 수 있는 타사 데이터 커넥터가 나열됩니다. 또한 이 표에는 타사 데이터를 가져와 보관한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션이 요약되어 Microsoft 365. 각 준수 [솔루션에](#overview-of-compliance-solutions-that-support-third-party-data) 대한 자세한 설명과 타사 데이터를 지원하는 방법에 대한 자세한 내용은 타사 데이터를 지원하는 규정 준수 솔루션 개요 섹션을 참조하세요.

타사 데이터를 조직에 보관하기 Microsoft 365 먼저 Veritas와 함께 조직에 대한 보관 *서비스(Merge1)를* 설정해야 합니다. 자세한 내용은 타사 데이터 열의 링크를 클릭하여 해당 데이터 형식에 대한 커넥터를 만들기 위한 단계별 지침으로 이동하십시오. 

|타사 데이터  |소송 보류|eDiscovery  |보존 설정  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[MS SQL의 Cisco Jabber](archive-ciscojabberonmssql-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Oracle의 Cisco Jabber](archive-ciscojabberonoracle-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[PostgreSQL의 Cisco Jabber](archive-ciscojabberonpostgresql-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[FX 연결](archive-fxconnect-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[MS SQL Database](archive-mssqldatabaseimporter-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Pivot](archive-pivot-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[RingCentral](archive-ringcentral-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[비즈니스용 Skype](archive-skypeforbusiness-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Slack eDiscovery](archive-slack-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[텍스트 구분](archive-text-delimited-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Webex Teams](archive-webexteams-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[웹 페이지](archive-webpagecapture-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Facebook의 작업 영역](archive-workplacefromfacebook-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[YouTube](archive-youtube-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|||
|[Zoom 모임](archive-zoommeetings-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage 데이터 커넥터

이 섹션의 표에는 TeleMessage와 함께 사용할 수 있는 타사 데이터 커넥터가 나열됩니다. 또한 이 표에는 타사 데이터를 가져와 보관한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션이 요약되어 Microsoft 365. 각 준수 [솔루션에](#overview-of-compliance-solutions-that-support-third-party-data) 대한 자세한 설명과 타사 데이터를 지원하는 방법에 대한 자세한 내용은 타사 데이터를 지원하는 규정 준수 솔루션 개요 섹션을 참조하세요.

타사 데이터를 보관할 수 Microsoft 365 조직에 대한 보관 서비스를 설정하기 위해 TeleMessage와 함께 작업해야 합니다. 자세한 내용은 타사 데이터 열의 링크를 클릭하여 해당 데이터 형식에 대한 커넥터를 만들기 위한 단계별 지침으로 이동하십시오. 

TeleMessage 데이터 커넥터는 미국 GCC 클라우드의 Microsoft 365 있습니다. 자세한 내용은 이 문서의 [미국 정부](#data-connectors-in-the-us-government-cloud) 클라우드의 데이터 커넥터 섹션을 참조하세요.

|타사 데이터  |소송 보류|eDiscovery  |보존 설정  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[AT&T 네트워크](archive-att-network-archiver-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Bell Network](archive-bell-network-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[기업 번호](archive-enterprise-number-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[O2 Network](archive-o2-network-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Rogers Network](archive-rogers-network-archiver-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[신호](archive-signal-archiver-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Telegram](archive-telegram-archiver-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[TELUS Network](archive-telus-network-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Verizon Network](archive-verizon-network-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[WeChat(미리 보기)](archive-wechat-data.md)|![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4 데이터 커넥터

이 섹션의 표에는 17a-4 LLC와 함께 사용할 수 있는 타사 데이터 커넥터가 나열됩니다. 또한 이 표에는 타사 데이터를 가져와 보관한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션이 요약되어 Microsoft 365. 각 준수 [솔루션에](#overview-of-compliance-solutions-that-support-third-party-data) 대한 자세한 설명과 타사 데이터를 지원하는 방법에 대한 자세한 내용은 타사 데이터를 지원하는 규정 준수 솔루션 개요 섹션을 참조하세요.

타사 데이터를 조직에 Microsoft 365 보관 *서비스(DataParser)를* 설정하기 위해 17a-4 LLC와 함께 작업해야 합니다. 자세한 내용은 타사 데이터 열의 링크를 클릭하여 해당 데이터 형식에 대한 커넥터를 만들기 위한 단계별 지침으로 이동하십시오. 

17a-4 데이터 커넥터는 GCC 미국 정부 클라우드의 Microsoft 365 사용할 수 있습니다. 자세한 내용은 이 문서의 [미국 정부](#data-connectors-in-the-us-government-cloud) 클라우드의 데이터 커넥터 섹션을 참조하세요.

|타사 데이터  |소송 보류|eDiscovery  |보존 설정  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Bloomberg](archive-17a-4-bloomberg-data.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Fuze](archive-17a-4-fuze-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[FX 연결](archive-17a-4-fxconnect-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[ICE 채팅](archive-17a-4-ice-im-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[LivePerson 대화 클라우드](archive-17a-4-liveperson-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Quip](archive-17a-4-quip-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
[비즈니스용 Skype 서버](archive-17a-4-skype-for-business-server-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[여유 시간](archive-17a-4-slack-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
|[확대/축소](archive-17a-4-zoom-data.md)    |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust 데이터 커넥터

이 섹션의 표에는 CellTrust와 함께 사용할 수 있는 타사 데이터 커넥터가 나열됩니다. 또한 이 표에는 타사 데이터를 가져와 보관한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션이 요약되어 Microsoft 365. 각 준수 [솔루션에](#overview-of-compliance-solutions-that-support-third-party-data) 대한 자세한 설명과 타사 데이터를 지원하는 방법에 대한 자세한 내용은 타사 데이터를 지원하는 규정 준수 솔루션 개요 섹션을 참조하세요.

타사 데이터를 보관할 수 Microsoft 365 조직에 대한 보관 서비스(CellTrust SL2)를 설정하기 위해 *CellTrust와* 함께 작업해야 합니다. 자세한 내용은 **타사** 데이터 열의 링크를 클릭하여 CellTrust SL2 커넥터를 만들기 위한 단계별 지침으로 이동하세요.

|타사 데이터  |소송 보류|eDiscovery  |보존 설정  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![확인 표시입니다.](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)|![확인 표시](../media/checkmark.png)||
||||||||

CellTrust SL2 데이터 커넥터는 미국 GCC 클라우드의 Microsoft 365 사용할 수 있습니다. 자세한 내용은 이 문서의 [미국 정부](#data-connectors-in-the-us-government-cloud) 클라우드의 데이터 커넥터 섹션을 참조하세요.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>타사 데이터를 지원하는 규정 준수 솔루션 개요

다음 섹션에서는 Microsoft 365 규정 준수 솔루션이 이전 표에 나열된 타사 데이터를 관리하는 데 도움이 되는 몇 가지 방법을 설명합니다.

### <a name="litigation-hold"></a>소송 보류

사용자 [사서함에](create-a-litigation-hold.md) 소송 보존을 설정하여 타사 데이터를 보존합니다. 보류를 만들 때 삭제 및 수정된 타사 데이터가 지정된 기간 동안 보존된 다음 사서함에서 영구적으로 삭제될 수 있도록 보존 기간(시간 기반 보류라고도함)을 지정할 수 있습니다. 또는 콘텐츠를 무기한 보존(무한 보존)하거나 소송 보존이 제거될 때까지 보존할 수 있습니다. 

### <a name="ediscovery"></a>eDiscovery

이 도구의 세 가지 기본 eDiscovery 도구는 Microsoft 365, Core eDiscovery 및 Advanced eDiscovery.

- **[콘텐츠 검색](content-search.md).** 콘텐츠 검색 도구를 사용하여 사서함에서 가져온 타사 데이터를 검색할 수 있습니다. 검색 쿼리 및 조건을 사용하여 검색 결과 범위를 좁히고 검색 결과를 내보낼 수 있습니다.

- **[Core eDiscovery](get-started-core-ediscovery.md).** 이 도구는 사례 데이터에 액세스할 수 있는 사용자를 제어하고, 검색 조건과 일치하는 사용자 사서함 또는 사서함 콘텐츠를 보류할 수 있는 사례를 만들 수 있도록 하여 기본 검색 및 내보내기 기능을 구축합니다. 즉, 사용자 사서함으로 가져온 타사 데이터에 eDiscovery 보류를 사용할 수 있습니다.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** 이 강력한 도구는 보유자도 사례에 추가하고 보유자 데이터를 보류한 다음 테마 및 중복 검색과 같은 추가 분석을 위해 보유자 데이터를 검토에 로드하여 Core eDiscovery의 사례 기능을 확장합니다. 타사 데이터를 검토 집합에 로드한 후 쿼리하고 좁은 결과 집합으로 필터링할 수 있습니다.

   Core eDiscovery 및 Advanced eDiscovery 조직의 법률 또는 내부 조사와 관련이 있을 수 있는 타사 데이터를 관리할 수 있습니다.

### <a name="retention-settings"></a>보존 설정

보존 기간이 [](retention.md) 만료된 후 사용자 사서함에 보존 정책을 적용하여 타사 데이터(및 기타 사서함 콘텐츠)를 보존하고 삭제할 수 있습니다. 또한 보존 정책을 사용하여 특정 보존 기간의 타사 [](disposition.md) 데이터를 삭제하거나 보존 레이블을 사용하여 타사 데이터의 보존 기간이 만료될 때 처리 검토를 트리거할 수 있습니다.

### <a name="records-management"></a>레코드 관리

[타사의](records-management.md) 레코드 관리 Microsoft 365 레코드로 선언할 수 있습니다. 사서함의 타사 데이터를 레코드로 표시하는 보존 레이블을 적용하는 사용자가 수동으로 이행할 수 있습니다. 또는 타사 데이터에서 중요한 정보, 키워드 또는 콘텐츠 형식을 식별하여 보존 레이블을 자동으로 적용할 수 있습니다.

### <a name="communication-compliance"></a>커뮤니케이션 규정 준수

커뮤니케이션 규정 [준수를](communication-compliance.md) 사용하여 타사 데이터를 검사하여 조직의 데이터 표준을 준수하는지 검사할 수 있습니다. 이 작업은 조직에서 부적절한 메시지에 대한 수정 작업을 검색, 캡처 및 수행하여 수행할 수 있습니다. 예를 들어, 비방적인 언어, 중요한 정보 및 규정 준수에 대해 가져오는 타사 데이터를 모니터링할 수 있습니다.

### <a name="insider-risk-management"></a>내부자 위험 관리

선택적 HR 데이터와 같은 타사 데이터의 신호를 내부자 [](insider-risk-management.md) 위험 관리 솔루션에서 사용하여 조직의 위험한 활동을 감지, 조사 및 작업할 수 있도록 하여 내부 위험을 최소화할 수 있습니다. 예를 들어 HR 데이터 커넥터에서 가져온 데이터는 퇴사하는 직원 데이터 도용을 감지하는 데 도움이 되는 위험 지표로 사용됩니다.

## <a name="using-ediscovery-tools-to-search-for-third-party-data"></a>eDiscovery 도구를 사용하여 타사 데이터 검색

데이터 커넥터를 사용하여 사용자 사서함에 타사 데이터를 가져오고 보관한 후 Microsoft 365 eDiscovery 도구를 사용하여 타사 데이터를 검색할 수 있습니다. 또한 eDiscovery 도구를 사용하여 Core eDiscovery 및 타사 사례와 연결된 쿼리 기반 보류를 Advanced eDiscovery 타사 데이터를 보존할 수 있습니다. eDiscovery 도구에 대한 자세한 내용은 [eDiscovery solutions in Microsoft 365.](ediscovery.md)

데이터 커넥터를 사용하여 사용자 사서함으로 가져온 모든 유형의 타사 데이터를 검색하거나 보류하기 위해 다음 검색 쿼리를 사용할 수 있습니다. 검색 범위를 사용자 사서함으로 지정해야 합니다.

```powershell
kind:externaldata
```

콘텐츠 검색, Core  eDiscovery 사례와 연결된 검색 또는 콘텐츠의 컬렉션에 대해 키워드 상자에서 이 쿼리를 사용할 Advanced eDiscovery.

![타사 데이터를 검색하는 쿼리입니다.](..\media\SearchThirdPartyData1.png)

property:value 쌍을 사용하여 검색 범위를 타사 데이터로 `kind:externaldata` 좁힐 수도 있습니다. 예를 들어 가져온 항목의 **Subject** 속성에 *contoso* 단어가 포함된 타사 데이터 원본에서 가져온 항목을 검색하기 위해 키워드 상자에 다음 쿼리를 **사용합니다.**

```powershell
subject:contoso AND kind:externaldata
```

또는 메시지 종류 조건을  사용하여 동일한 쿼리를 구성할 수 있습니다.

![메시지 종류 조건을 사용하여 검색 범위를 타사 데이터로 좁힐 수 있습니다.](..\media\SearchThirdPartyData2.png)

보관된 특정 유형의 타사 데이터를 검색하기 위해 검색 쿼리에서 **itemclass** 사서함 속성을 사용합니다. 다음 속성 값 형식을 사용 합니다.

```powershell
itemclass:ipm.externaldata.<third-party data type>
```

타사 데이터 커넥터에서 가져온 모든 항목에는 타사 데이터 형식에 해당하는 값이 있는 **itemclass** 속성이 포함됩니다. 예를 들어 가져온 항목의 Subject 속성에서 *contoso* 이라는 단어가 포함된 **Facebook** 데이터를 검색하기 위해 다음 쿼리를 사용합니다.

```powershell
subject:contoso AND itemclass:ipm.externaldata.facebook*
```

다음은 서로 다른 형식의 타사 데이터에 대한 **itemclass** 값에 대한 몇 가지 예입니다.

| **타사 데이터 형식** | **itemclass 속성 값**   |
|---------------------------|-------------------------------------|
| 블룸버그 메시지         | ipm.externaldata.bloombergmessage* |
| CellTrust                 | ipm.externaldata.celltrust*        |
| Pivot                     | ipm.externaldata.pivot*            |
| WhatsApp 보관 장치         | ipm.externaldata.whatsapparchiver* |
|||

*itemclass* 속성의 값은 대소문자 구분이 없습니다. 일반적으로 타사 데이터 형식의 이름(공백 없이)과 와일드카드( * ) 문자를 사용 합니다.

eDiscovery 검색 쿼리를 만드는 데 대한 자세한 내용은 [eDiscovery에](keyword-queries-and-search-conditions.md)대한 키워드 쿼리 및 검색 조건을 참조하세요.

## <a name="data-connectors-in-the-us-government-cloud"></a>미국 정부 클라우드의 데이터 커넥터

일부 데이터 커넥터는 미국 정부 클라우드에서 사용할 수 있습니다. 다음 섹션에서는 타사 데이터 커넥터를 지원하는 특정 정부 환경을 나타냅니다. 미국 정부 클라우드에 대한 자세한 내용은 미국 [Microsoft 365 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)

### <a name="telemessage-data-connectors"></a>원격 분석 데이터 커넥터

|데이터 커넥터  |GCC  |GCC 높음  |DoD  |
|:---------|:---------|:---------|:---------|
|Android 보관 장치 | 예 | 아니요 | 아니요 |
|AT&T SMS/MMS 네트워크 보관 장치 | 예 | 아니요 | 아니요 |
|Bell SMS/MMS 네트워크 보관 장치 | 예 | 아니요 | 아니요 |
|엔터프라이즈 번호 보관 장치 | 예 | 아니요 | 아니요 |
|O2 SMS 및 음성 네트워크 보관 | 예         | 아니요 | 아니요 |
|Rogers Network Archiver | 예         | 아니요 | 아니요 |
|신호 보관기 | 예 | 아니요 | 아니요 |
|텔레그램 보관기 | 예 | 아니요 | 아니요 |
|TELUS SMS 네트워크 보관함 | 예 | 아니요 | 아니요 |
|Verizon SMS/MMS 네트워크 보관 장치 | 예 | 아니요 | 아니요 |
|WeChat 보관 장치 | 예 | 아니요 | 아니요 |
|WhatsApp 보관 장치 | 예 | 아니요 | 아니요 |
|||||

### <a name="celltrust-data-connectors"></a>CellTrust 데이터 커넥터

|데이터 커넥터  |GCC  |GCC 높음  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust SL2 | 예 | 아니요 | 아니요 |
|||||

### <a name="17a-4-data-connectors"></a>17a-4 데이터 커넥터

|데이터 커넥터  |GCC  |GCC 높음  |DoD  |
|:---------|:---------|:---------|:---------|
|BlackBerry DataParser | 예 | 아니요 | 아니요 |
|Bloomberg DataParser  | 예 | 아니요 | 아니요 |
|Cisco Jabber DataParser  | 예 | 아니요 | 아니요 |
|Cisco Webex DataParser  | 예 | 아니요 | 아니요 |
|FactSet DataParser  | 예 | 아니요 | 아니요 |
|Fuze DataParser  | 예 | 아니요 | 아니요 |
|FX Connect DataParser  | 예 | 아니요 | 아니요 |
|ICE DataParser  | 예 | 아니요 | 아니요 |
|InvestEdge DataParser  | 예 | 아니요 | 아니요 |
|LivePerson Conversational Cloud DataParser  | 예 | 아니요 | 아니요 |
|Quip DataParser  | 예 | 아니요 | 아니요 |
|Refinitiv Eikon Messenger DataParser  | 예 | 아니요 | 아니요 |
|ServiceNow DataParser  | 예 | 아니요 | 아니요 |
|비즈니스용 Skype 서버 DataParser | 예 | 아니요 | 아니요 |
|Slack DataParser | 예 | 아니요 | 아니요 |
|SQL DataParser  | 예 | 아니요 | 아니요 |
|Symphony DataParser | 예 | 아니요 | 아니요 |
|Zoom DataParser | 예 | 아니요 | 아니요 |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft 파트너와 협력하여 타사 데이터 보관

타사 데이터를 가져오고 보관하는 또 다른 옵션은 조직이 Microsoft 파트너와 협력할 수 있도록 하는 것입니다. Microsoft 규정 준수 센터에서 사용할 수 있는 데이터 커넥터에서 타사 데이터 형식이 지원되지 않는 경우 타사 데이터 원본에서 항목을 정기적으로 추출하도록 구성할 사용자 지정 커넥터를 제공할 수 있는 파트너와 협력한 다음 타사 API를 통해 Microsoft 클라우드에 연결하여 해당 항목을 Microsoft 365. 또한 파트너 커넥터는 타사 데이터 원본의 항목 콘텐츠를 전자 메일 메시지로 변환한 다음 해당 항목의 사서함으로 Microsoft 365.

함께 작업할 수 있는 파트너 목록과 이 방법에 대한 단계별 프로세스는 [파트너와](work-with-partner-to-archive-third-party-data.md)협력하여 타사 데이터를 Microsoft 365.
