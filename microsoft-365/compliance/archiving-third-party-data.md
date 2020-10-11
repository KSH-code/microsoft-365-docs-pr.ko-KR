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
description: 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 Microsoft 365 사서함으로 타사 데이터를 가져오는 방법에 대해 알아봅니다.
ms.openlocfilehash: 53077dec46a0e64db1c790e96ae0107047d68f9c
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408966"
---
# <a name="archive-third-party-data"></a>타사 데이터 보관

Microsoft 365에서는 관리자가 데이터 커넥터를 사용 하 여 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 타사 데이터를 가져오고 Microsoft 365 조직의 사서함으로 보관할 수 있습니다. 데이터 커넥터를 사용 하 여 Microsoft 365에서 타사 데이터를 가져오고 보관할 때의 주요 이점은 다양 한 Microsoft 365 준수 솔루션을 가져온 후에 적용할 수 있다는 것입니다. 이를 통해 조직의 비 Microsoft 데이터가 조직에 영향을 주는 규정 및 표준을 준수 하도록 할 수 있습니다.

## <a name="third-party-data-connectors"></a>타사 데이터 커넥터

다음 표에는 Microsoft 365 준수 센터에서 사용할 수 있는 타사 데이터 커넥터가 나와 있습니다. 또한이 표에는 Microsoft 365에서 가져오고 보관 한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션도 요약 되어 있습니다. 각 준수 솔루션에 대 한 자세한 내용과 타사 데이터에 이익이 되는 방식에 대 한 자세한 내용은 [다음 섹션](#overview-of-compliance-solutions-that-support-third-party-data) 을 참조 하십시오.

> [!TIP]
> 타사 **데이터** 열의 링크를 클릭 하 여 해당 데이터 형식에 대 한 커넥터를 만들기 위한 단계별 지침을 참조 하십시오.

|타사 데이터  |소송 보존|eDiscovery  |보존 설정  |레코드 관리  |커뮤니케이션 규정 준수  |내부자 위험 관리  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[&T 네트워크 <sup>1</sup>](archive-att-network-archiver-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[벨 네트워크 <sup>1</sup>](archive-bell-network-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[블룸버그 메시지](archive-bloomberg-message-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Enterprise 번호 <sup>1</sup>](archive-enterprise-number-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[FX 연결 <sup>2</sup>](archive-fxconnect-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[인적 자원 (HR)](import-hr-data.md) ||||||![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)
|[ICE 채팅](archive-icechat-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[LinkedIn](archive-linkedin-data.md)   |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[O2 네트워크 <sup>1</sup>](archive-o2-network-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[실제 배지 획득](import-physical-badging-data.md) ||||||![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[피벗 <sup>2</sup>](archive-pivot-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[여유 시간 eDiscovery <sup>2</sup>](archive-slack-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Symphony <sup>2</sup>](archive-symphony-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[TELUS 네트워크 <sup>1</sup>](archive-telus-network-data.md)    |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[텍스트 구분 <sup>2</sup>](archive-text-delimited-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Verizon 네트워크 <sup>1</sup>](archive-verizon-network-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Webex 팀 <sup>2</sup>](archive-webexteams-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[웹 페이지 <sup>2</sup>](archive-webpagecapture-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook <sup>2</sup> 의 작업 공간](archive-workplacefromfacebook-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[확대/축소 모임 <sup>2</sup>](archive-zoommeetings-data.md)     |![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![확인 표시](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
||||||||

> [!NOTE]
> TeleMessage에서 제공 하는 데이터 커넥터 <sup>1 개</sup> Microsoft 365에서 데이터를 보관 하려면 먼저 TeleMessage을 사용 하 여 조직에 대 한 보관 서비스를 설정 해야 합니다. 자세한 내용은이 데이터 형식에 대 한 단계별 지침에서 필수 구성 요소 섹션을 참조 하십시오.<br/><br/><sup>2</sup> Globanet에서 제공 하는 데이터 커넥터입니다. Microsoft 365에서 데이터를 보관 하려면 먼저 Globanet을 사용 하 여 조직에 대 한 보관 서비스를 설정 해야 합니다. 자세한 내용은이 데이터 형식에 대 한 단계별 지침에서 필수 구성 요소 섹션을 참조 하십시오.

HR 데이터 및 실제 배지 획득 데이터를 제외 하 고 이전 표에 나열 된 타사 데이터를 사용자 사서함으로 가져옵니다. 타사 데이터를 지 원하는 해당 하는 준수 솔루션은 데이터가 저장 된 사용자 사서함에 적용 됩니다.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>타사 데이터를 지 원하는 규정 준수 솔루션 개요

다음 섹션에서는 Microsoft 365 규정 준수 솔루션이 이전 표에 나열 된 타사 데이터를 관리 하는 데 도움이 될 수 있는 몇 가지 사항에 대해 설명 합니다.

### <a name="litigation-hold"></a>소송 보존

사용자 사서함에 [소송 보존](create-a-litigation-hold.md) 을 배치 하 여 타사 데이터를 유지 합니다. 보류를 만들 때 삭제 및 수정 된 타사 데이터가 지정 된 기간 동안 보존 되 고 사서함에서 영구적으로 삭제 되도록 보존 기간 ( *시간 기반 보류*)을 지정할 수 있습니다. 또는 콘텐츠를 무기한 보존 ( *무기한 보류*라고 함) 하거나 소송 보존을 제거할 때까지 가능 합니다.

### <a name="ediscovery"></a>eDiscovery

Microsoft 365의 세 가지 기본 eDiscovery 도구는 콘텐츠 검색, 핵심 eDiscovery 및 고급 eDiscovery입니다.

- **[콘텐츠 검색](content-search.md)** 콘텐츠 검색 도구를 사용 하 여 가져온 타사 데이터에 대 한 사서함을 검색할 수 있습니다. 검색 쿼리 및 조건을 사용 하 여 검색 결과의 범위를 좁히고 검색 결과를 내보낼 수 있습니다.

- **[필수 eDiscovery](get-started-core-ediscovery.md)** 이 도구는 사례 데이터에 액세스할 수 있는 사용자를 제어 하는 사례를 만드는 데 사용 되는 기본 검색 및 내보내기 기능을 지원 하 고, 검색 조건과 일치 하는 사람 사서함 이나 사서함 콘텐츠를 보존 합니다. 즉, 사용자 사서함으로 가져온 타사 데이터에 eDiscovery 보류를 배치할 수 있습니다.

- **[고급 eDiscovery](overview-ediscovery-20.md)** 이 강력한 도구는 사례에 custodians을 추가 하 고 custodian의 데이터를 보류할 수 있도록 하 고, custodian의 타사 데이터를 검토로 로드 하 여 테마 및 중복 검색 등의 추가 분석을 위해 주요 eDiscovery의 사례 기능을 확장 합니다. 타사 데이터를 검토 집합으로 로드 한 후에는이를 쿼리 하 여 좁은 결과 집합으로 필터링 할 수 있습니다.

   핵심 eDiscovery 및 고급 eDiscovery를 모두 사용 하면 조직의 법적/내부 조사와 관련 된 타사 데이터를 관리할 수 있습니다.

### <a name="retention-settings"></a>보존 설정

보존 기간이 만료 된 후에는 사용자 사서함에 [보존 정책을](retention.md) 적용 하 여 타사 데이터 및 기타 사서함 콘텐츠를 유지 하 고 삭제할 수 있습니다. 또한 보존 정책을 사용 하 여 특정 기간의 타사 데이터를 삭제 하거나 [보존 레이블을 사용](disposition.md) 하 여 타사 데이터의 보존 기간이 만료 되는 경우 처리 검토를 트리거할 수 있습니다.

### <a name="records-management"></a>레코드 관리

Microsoft 365의 [레코드 관리](records-management.md) 기능을 사용 하면 타사 데이터를 레코드로 선언할 수 있습니다. 사서함의 타사 데이터를 레코드로 표시 하는 보존 레이블을 적용 하는 사용자가 수동으로이 작업을 수행할 수 있습니다. 또는 타사 데이터의 중요 한 정보, 키워드 또는 콘텐츠 형식을 식별 하 여 보존 레이블을 자동으로 적용할 수 있습니다.

### <a name="communication-compliance"></a>커뮤니케이션 규정 준수

[통신 준수](communication-compliance.md) 를 사용 하 여 타사 데이터를 검사 하 고 조직의 데이터 표준과 호환 되는지 확인할 수 있습니다. 조직의 부적절 한 메시지에 대 한 검색, 캡처 및 재구성 작업을 수행 하 여이 작업을 수행할 수 있습니다. 예를 들어 원하지 않는 언어, 중요 한 정보 및 규정 준수를 위해 가져오는 타사 데이터를 모니터링할 수 있습니다.

### <a name="insider-risk-management"></a>내부자 위험 관리

선택적 HR 데이터와 같은 타사 데이터의 신호를 [참가자 위험 관리](insider-risk-management.md) 솔루션에서 사용 하 여 조직에서 위험한 활동을 감지, 조사 및 처리할 수 있는 방법으로 내부 위험을 최소화 합니다. 예를 들어 HR 데이터 커넥터에서 가져오는 데이터는 departing 직원 데이터 절도를 검색 하는 데 도움이 되는 위험 표시기로 사용 됩니다.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft 파트너와 협력 하 여 타사 데이터 보관

타사 데이터를 가져오고 보관 하는 또 다른 옵션은 조직이 Microsoft 파트너와 함께 작업할 수 있도록 하는 것입니다. 타사 데이터 형식을 Microsoft 준수 센터에서 사용할 수 있는 데이터 커넥터에서 지원 하지 않는 경우 타사 데이터 원본에서 정기적으로 항목을 추출 하 고 타사 API를 통해 Microsoft 클라우드에 연결한 다음 해당 항목을 Microsoft 365로 가져오는 사용자 지정 커넥터를 제공할 수 있는 파트너와 함께 작업할 수 있습니다. 또한 파트너 커넥터는 타사 데이터 원본에서 전자 메일 메시지로 항목의 콘텐츠를 변환한 다음 Microsoft 365에서 사서함으로 가져옵니다.

사용할 수 있는 파트너의 목록과이 방법의 단계별 프로세스에 대 한 자세한 내용은 [Microsoft 365에서 파트너와 협력 하 여 타사 데이터 보관](work-with-partner-to-archive-third-party-data.md)을 참조 하십시오.
