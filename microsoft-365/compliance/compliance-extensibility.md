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
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 타사 데이터 커넥터 및 Microsoft Graph API를 사용하여 Microsoft 365 규정 준수 솔루션을 확장하는 방법을 알아보십시오.
ms.openlocfilehash: 676c0ba41e517dd0c3692fec29a1d4034641b634
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919724"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 규정 준수 extensibility

Microsoft 365 규정 준수 솔루션은 조직이 규정 준수 위험을 지능적으로 평가하고, 중요한 데이터를 제어 및 보호하며, 규정 요구 사항에 효과적으로 대응하도록 지원합니다. Microsoft 365 규정 준수는 다양한 확장성 시나리오를 지원하며 조직에서 규정 준수 솔루션을 조정, 확장, 통합, 가속화 및 지원할 수 있도록 합니다.

규정 준수 Extensibility에는 두 가지 주요 구성 요소가 있습니다.

- **데이터 커넥터.** 타사 데이터에 Microsoft 365 보호 및 거버넌스 기능을 적용할 수 있도록 타사 데이터를 가져오고 보관하는 데 사용할 수 있습니다.

- **API.** Microsoft 365 규정 준수 기능에 프로그래밍된 액세스를 허용합니다.

## <a name="data-connectors"></a>데이터 커넥터

Microsoft는 Microsoft 365 규정 준수 센터에서 구성할 수 있는 타사 데이터 커넥터를 제공합니다. Microsoft에서 제공하는 데이터 커넥터 목록은 타사 데이터 커넥터 [테이블을 참조하세요.](archiving-third-party-data.md#third-party-data-connectors) 타사 데이터 커넥터 표에는 Microsoft 365에서 데이터를 가져오고 보관한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션과 각 커넥터에 대한 단계별 지침에 대한 링크도 요약됩니다.

Microsoft 365 데이터 커넥터에 대한 자세한 내용은 타사 데이터 [보관을 참조합니다.](archiving-third-party-data.md) Microsoft 365 규정 준수 센터에서 사용할 수 있는 데이터 커넥터에서 타사 데이터 형식이 지원되지 않는 경우 사용자 지정 커넥터를 제공할 수 있는 파트너와 협력할 수 있습니다. 함께 작업할 수 있는 파트너 목록 및 이 방법에 대한 단계별 프로세스는 파트너와 협력하여 타사 데이터 [보관을 참조하세요.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>데이터 커넥터의 선행 준비

타사 데이터를 가져오고 보관하기 위해 Microsoft 365 규정 준수 센터에서 사용할 수 있는 많은 데이터 커넥터를 사용하려면 타사 데이터 원본에서 구성 작업을 준비하고 수행해야 합니다. 이러한 선행 사항은 각 타사 데이터 커넥터에 대해 자세히 설명되어 있습니다.

Microsoft의 파트너 중 하나에서 제공하는 Microsoft 365 규정 준수 센터의 데이터 커넥터의 경우 조직에서 파트너와의 비즈니스 관계가 필요해야 커넥터를 배포할 수 있습니다.

[Microsoft 365](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 규정 준수 라이선싱 비교 문서에서 타사 데이터 커넥터에 대한 라이선스 요구 사항을 확인할 수 있습니다.

## <a name="apis"></a>API

Microsoft 365 규정 준수 API는 Microsoft Information Protection SDK, Microsoft Graph API 및 Office 365 관리 활동 API에서 사용할 수 있습니다. 일부 규정 준수 API는 Microsoft 365 고객, 독립 소프트웨어 공급업체, 시스템 통합자 및 관리되는 보안 서비스 공급자가 고가치 보안 및 규정 준수 솔루션을 빌드할 수 있도록 하는 새로운 보안 및 규정 준수 API 집합의 일부입니다.

Graph API에 액세스하는 방법에 대한 자세한 내용은 [Microsoft Graph 개요를 참조하세요.](/graph/overview)

### <a name="microsoft-information-protection-mip-sdk"></a>MIP(Microsoft Information Protection) SDK

MIP SDK는 Microsoft 365 보안 및 규정 준수 센터의 레이블 지정 및 보호 서비스를 타사 응용 프로그램 및 서비스에 노출합니다. 개발자는 SDK를 사용하여 파일에 레이블 및 보호를 적용하는 기본 지원을 구축할 수 있습니다. 개발자는 특정 레이블이 감지될 때 취해야 하는 작업과 MIP 암호화 정보에 대한 이유를 결정할 수 있습니다.

높은 수준의 MIP SDK 사용 사례는 다음과 같습니다.

- 내보낼 파일에 분류 레이블을 적용하는 업무용 응용 프로그램입니다.

- MIP 레이블 지정에 대한 기본 지원을 제공하는 CAD/CAM 디자인 응용 프로그램입니다.

- Azure Information Protection을 사용하여 데이터를 암호화할 수 있는 클라우드 액세스 보안 브로커 또는 데이터 손실 방지 솔루션입니다.

MIP SDK, 선행 시나리오, 추가 시나리오 및 샘플에 대한 자세한 내용은 [MIP SDK 개요 를 참조하세요.](/information-protection/develop/overview)

### <a name="microsoft-graph-api-for-teams-dlp"></a>Teams DLP용 Microsoft Graph API

[DLP(데이터 손실 방지)](dlp-microsoft-teams.md) 기능은 조직이 원격 작업으로 전환할 때 특히 Microsoft Teams에서 널리 사용됩니다. 올해 초 [Teams의](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) 메시지에 대한 Microsoft Graph Change Notification API의 공개 미리 보기를 발표했습니다. 이 API를 통해 개발자는 거의 실시간으로 Microsoft Teams 메시지를 들을 수 있는 앱을 빌드한 다음 고객과 파트너 모두에 대해 DLP 시나리오를 구현할 수 있습니다. 또한 Microsoft Graph 패치 API를 사용하여 Teams 메시지에 DLP 작업을 적용할 수 있습니다.

이러한 두 API는 Teams DLP용 Microsoft Graph API를 구성합니다. 샘플 앱을 사용해 보면 시작할 [수 있습니다.](https://github.com/microsoftgraph/csharp-webhook-with-resource-data) Microsoft Teams 메시징 webhook에 대한 자세한 내용은 설명서를 [참조하십시오.](/graph/api/subscription-post-subscriptions)

Teams DLP에 대한 라이선싱 요구 사항은 보안 및 규정 준수에 대한 [Microsoft 365 & 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>eDiscovery용 Microsoft Graph API(미리 보기)

[Advanced eDiscovery를](overview-ediscovery-20.md)사용하면 조직은 데이터가 있는 데이터를 검색하고 지능형 기계 학습 및 분석 기능을 사용하여 더 많은 종단-종단-종단 eDiscovery 워크플로를 관리하여 데이터가 Microsoft 365 보안 및 규정 준수 경계 내에 유지되는 동안 관련 집합으로 데이터를 줄일 수 있습니다.

Advanced eDiscovery용 그래프 API를 사용하여 사례를 만들고 관리하고, 검토 집합을 검토하고, 집합 쿼리를 확장 가능하고 반복 가능한 방식으로 검토할 수 있습니다. 이를 통해 고객과 파트너는 사례 만들기, 보유자 및 법적 보유 관리와 같은 일반 및 반복 프로세스를 자동화하는 앱 및 워크플로를 만들 수 있습니다.

eDiscovery용 그래프 API의 첫 번째 집합은 공개 미리 보기에서 사용할 수 있습니다. 연말까지 더 많은 기능을 추가할 계획입니다. Advanced eDiscovery의 이러한 API 및 기타 업데이트에 대한 자세한 내용은 이 블로그를 [참조하세요.](https://aka.ms/Ignite2020AeDAA)

Advanced eDiscovery 및 API에 대한 라이선스 요구 사항에 대한 자세한 내용은 보안 및 준수를 위한 [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)라이선싱 지침의 "eDiscovery" & 참조하세요.

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Teams 내보내기용 Microsoft Graph API(미리 보기)

Microsoft Teams용 EIA(엔터프라이즈 정보 보관)는 고객이 규정 요구 사항을 해결할 수 있도록 하여 고객의 주요 시나리오입니다. Microsoft Teams에 콘텐츠를 보관하기 위한 기본 제공 기능 외에도 고객 및 파트너는 이제 Teams 내보내기 API를 사용하여 사용자 지정 응용 프로그램 및 통합 시나리오를 해결할 수 있습니다. Teams 내보내기 API는 Teams 메시지 및 메시지 첨부 파일의 대량 내보내기(앱/테넌트당 최대 200개 요청)를 지원합니다. 삭제된 메시지는 API에서 삭제된 후 최대 30일 동안 액세스할 수도 있습니다. 이러한 Teams 내보내기 API 및 응용 프로그램에서 사용하는 방법에 대한 자세한 내용은 Microsoft Teams 내보내기 API를 사용하여 콘텐츠 [내보내기 를 참조하세요.](/microsoftteams/export-teams-content)

Teams 내보내기 API 사용에 대한 라이선스 요구 사항은 보안 및 규정 준수에 대한 [Microsoft 365 라이선싱 & 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)