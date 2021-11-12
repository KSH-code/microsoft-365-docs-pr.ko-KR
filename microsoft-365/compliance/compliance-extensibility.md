---
title: Microsoft 365 규정 준수 extensibility
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 타사 데이터 커넥터 및 Microsoft Microsoft 365 API를 사용하여 규정 준수 솔루션을 확장하는 Graph 대해 자세히 알아보십시오.
ms.openlocfilehash: 0957cb0f874964740697516a1cd8a37a2f8dca27
ms.sourcegitcommit: 6dbf879f769a825ed7039363f3a91d676e355ee0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60940737"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 규정 준수 extensibility

Microsoft 365 솔루션은 조직이 규정 준수 위험을 지능적으로 평가하고, 중요한 데이터를 제어 및 보호하며, 규정 요구 사항에 효과적으로 대응하는 데 도움이 됩니다. Microsoft 365 규정 준수는 다양한 확장성 시나리오를 지원하며 조직에서 규정 준수 솔루션을 조정, 확장, 통합, 가속화 및 지원할 수 있도록 합니다.

규정 준수 Extensibility에는 두 가지 주요 구성 요소가 있습니다.

- **데이터 커넥터.** 타사 데이터에 보호 및 거버넌스 기능을 적용할 Microsoft 365 타사 데이터를 가져오고 보관하는 데 사용할 수 있습니다.

- **API.** 규정 준수 기능에 Microsoft 365 액세스할 수 있습니다.

## <a name="data-connectors"></a>데이터 커넥터

Microsoft는 Microsoft에서 구성할 수 있는 타사 데이터 커넥터를 Microsoft 365 규정 준수 센터. Microsoft에서 제공하는 데이터 커넥터 목록은 타사 데이터 커넥터 [테이블을 참조하세요.](archiving-third-party-data.md#third-party-data-connectors) 또한 타사 데이터 커넥터 표에는 데이터 가져오기 및 보관 후 타사 데이터에 적용할 수 있는 규정 Microsoft 365 및 각 커넥터에 대한 단계별 지침에 대한 링크가 요약되어 있습니다.

데이터 커넥터의 Microsoft 365 자세한 내용은 타사 데이터 [보관을 참조합니다.](archiving-third-party-data.md) 타사 데이터 형식이 타사에서 사용할 수 있는 데이터 커넥터에서 지원되지 Microsoft 365 규정 준수 센터 사용자 지정 커넥터를 제공할 수 있는 파트너와 협력할 수 있습니다. 함께 작업할 수 있는 파트너 목록 및 이 방법에 대한 단계별 프로세스는 파트너와 협력하여 타사 데이터 [보관을 참조하세요.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>데이터 커넥터의 선행 준비

타사에서 타사 데이터를 Microsoft 365 규정 준수 센터 데 사용할 수 있는 많은 데이터 커넥터를 사용하려면 타사 데이터 원본에서 구성 작업을 준비하고 수행해야 합니다. 이러한 선행 사항은 각 타사 데이터 커넥터에 대해 자세히 설명되어 있습니다.

Microsoft 파트너 중 하나에서 Microsoft 365 규정 준수 센터 데이터 커넥터의 경우 조직에서 파트너와의 비즈니스 관계가 필요한 경우 커넥터를 배포할 수 있습니다.

타사 데이터 커넥터에 대한 라이선스 요구 사항은 보안 및 준수에 대한 Microsoft 365 라이선싱 지침의 "데이터 커넥터" [& 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-connectors)

## <a name="apis"></a>API

Microsoft 365 준수 API는 Microsoft Information Protection SDK, Microsoft Graph API 및 Office 365 관리 활동 API에서 사용할 수 있습니다. 일부 규정 준수 API는 Microsoft 365 고객, 독립 소프트웨어 공급업체, 시스템 통합자 및 관리되는 보안 서비스 공급자가 고가치 보안 및 규정 준수 솔루션을 빌드할 수 있도록 하는 새로운 보안 및 규정 준수 API 집합의 일부입니다.

GRAPH 액세스하는 방법에 대한 자세한 내용은 [Microsoft](/graph/overview)Graph.

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection(MIP) SDK

MIP SDK는 보안 및 준수 센터의 레이블 Microsoft 365 및 보호 서비스를 타사 응용 프로그램 및 서비스에 노출합니다. 개발자는 SDK를 사용하여 파일에 레이블 및 보호를 적용하는 기본 지원을 구축할 수 있습니다. 개발자는 특정 레이블이 감지될 때 취해야 하는 작업과 MIP 암호화 정보에 대한 이유를 결정할 수 있습니다.

높은 수준의 MIP SDK 사용 사례는 다음과 같습니다.

- 내보낼 파일에 분류 레이블을 적용하는 업무용 응용 프로그램입니다.

- MIP 레이블 지정에 대한 기본 지원을 제공하는 CAD/CAM 디자인 응용 프로그램입니다.

- Azure Information Protection을 사용하여 데이터를 암호화할 수 있는 클라우드 액세스 보안 브로커 또는 데이터 손실 방지 솔루션입니다.

MIP SDK, 선행 시나리오, 추가 시나리오 및 샘플에 대한 자세한 내용은 [MIP SDK 개요 를 참조하세요.](/information-protection/develop/overview)

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph DLP용 Microsoft Teams API

[DLP(데이터 손실 방지)](dlp-microsoft-teams.md) 기능은 특히 조직이 원격 Microsoft Teams 때 널리 사용됩니다. 올해 [초에는](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) Microsoft Graph 메시지에 대한 Microsoft Graph 알림 API의 공개 미리 보기를 Teams. 이 API를 통해 개발자는 거의 실시간으로 Microsoft Teams 들을 수 있는 앱을 빌드한 다음 고객과 파트너 모두에 대해 DLP 시나리오를 구현할 수 있습니다. 또한 Microsoft Graph 패치 API를 사용하면 메시지에 DLP Teams 적용할 수 있습니다.

이러한 두 API는 DLP용 Microsoft Graph API를 Teams 구성합니다. 샘플 앱을 사용해 보면 시작할 [수 있습니다.](https://github.com/microsoftgraph/csharp-webhook-with-resource-data) 메시징 webhook의 Microsoft Teams 자세한 내용은 설명서를 [참조하십시오.](/graph/api/subscription-post-subscriptions)

DLP에 대한 라이선스 요구 사항에 Teams 보안 Microsoft 365 규정 준수에 대한 & [참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API for eDiscovery(미리 보기)

[조직은](overview-ediscovery-20.md)Advanced eDiscovery 사용하여 데이터가 있는 데이터를 검색하고 지능형 기계 학습 및 분석 기능이 있는 더 많은 엔드-엔드 eDiscovery 워크플로를 관리하여 데이터가 관련 집합에 대한 데이터만 Microsoft 365 보안 및 규정 준수 경계 내에 유지될 수 있습니다.

Graph API를 Advanced eDiscovery 사례를 만들고 관리하고, 검토 집합을 검토하고, 확장 가능하고 반복 가능한 방식으로 집합 쿼리를 검토하는 데 사용할 수 있습니다. 이를 통해 고객과 파트너는 사례 만들기, 보유자 및 법적 보유 관리와 같은 일반 및 반복 프로세스를 자동화하는 앱 및 워크플로를 만들 수 있습니다.

eDiscovery용 Graph API의 첫 번째 집합은 공개 미리 보기에서 사용할 수 있습니다. 연말까지 더 많은 기능을 추가할 계획입니다. 이러한 API 및 기타 업데이트에 대한 자세한 내용은 이 Advanced eDiscovery 를 [참조하세요.](https://aka.ms/Ignite2020AeDAA)

Advanced eDiscovery API에 대한 라이선스 요구 사항에 대한 자세한 내용은 보안 및 준수에 대한 Microsoft 365 라이선싱 지침의 "eDiscovery" [& 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)

### <a name="microsoft-graph-api-for-teams-export"></a>Microsoft Graph 내보내기용 Microsoft Teams API

Enterprise EIA(Microsoft Teams 보관)는 고객이 규정 요구 사항을 해결할 수 있도록 하는 주요 시나리오입니다. 고객 및 파트너는 Microsoft Teams 콘텐츠를 보관하는 기본 제공 기능 외에도 사용자 지정 응용 프로그램 Teams 통합 시나리오를 위해 API 내보내기 기능을 사용할 수 있습니다. 이 Teams 내보내기 API는 메시지 및 메시지 첨부 파일로 대량 내보내기(앱/테넌트당 최대 200개Teams 수 있습니다. 삭제된 메시지는 API에서 삭제된 후 최대 30일 동안 액세스할 수도 있습니다. 이러한 API 내보내기 Teams 및 응용 프로그램에서 사용하는 방법에 대한 자세한 내용은 Api 내보내기 에서 콘텐츠 [Microsoft Teams 참조하세요.](/microsoftteams/export-teams-content)

Teams API를 사용하기 위한 라이선스 요구 사항은 Microsoft 365 규정 준수에 대한 Microsoft 365 [라이선스 지침을 & 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph 커넥터 API(미리 보기)

[Microsoft Graph](/microsoftsearch/connectors-overview)커넥터를 사용하여 조직은 타사 데이터를 인덱싱하여 모든 결과에 표시될 Microsoft Search 있습니다. 이 기능은 생산성 앱 및 더 광범위한 Microsoft 에코시스템에서 Microsoft 365 콘텐츠 원본 유형을 확장합니다. 타사 데이터는 사내 또는 공용 또는 사설 클라우드에서 호스팅할 수 있습니다. 이 Advanced eDiscovery 시작으로 연결된 앱의 기본 제공 준수 값에 대한 개발자 미리 보기를 Microsoft 365 있습니다. 이렇게 하면 앱에 대한 규정 준수가 Microsoft 365 에코시스템에 통합되어 원활한 규정 준수 환경을 사용자에게 부여할 수 있습니다. 앱 보기에 Microsoft Graph 커넥터 API를 통합하는 방법에 대한 자세한 내용은 Microsoft Graph에서 연결 만들기, 업데이트 및 [삭제를 참조하세요.](/graph/search-index-manage-connections)
