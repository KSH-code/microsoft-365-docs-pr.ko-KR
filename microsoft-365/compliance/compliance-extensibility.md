---
title: Microsoft 365 준수 확장성
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
description: 타사 데이터 커넥터 및 Microsoft Graph Api를 사용 하 여 Microsoft 365 규정 준수 솔루션을 확장 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 284125db8243b10f5c8de7e0a37c1b7284709c28
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204398"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 준수 확장성

Microsoft 365 준수 솔루션은 조직에서 준수 위험을 지능적으로 평가 하 고, 중요 한 데이터를 제어 및 보호 하며, 규정 요구 사항에 효과적으로 대응 합니다. Microsoft 365 준수는 확장성 시나리오의 풍부한 기능을 제공 하며 조직이 준수 솔루션을 조정, 확장, 통합, 속도를 지원 하 고 지원할 수 있도록 합니다.

준수 확장을 위한 두 가지 주요 구성 요소는 다음과 같습니다.

- **데이터 커넥터** 타사 데이터를 가져오고 보관 하기 위해 microsoft 365 보호 및 거 버 넌 스 기능을 적용할 수 있도록 하는 데 사용 됩니다.

- **Api**입니다. Microsoft 365 준수 기능에 프로그래밍 방식으로 액세스할 수 있도록 합니다.

## <a name="data-connectors"></a>데이터 커넥터

Microsoft는 Microsoft 365 준수 센터에서 구성할 수 있는 타사 데이터 커넥터를 제공 합니다. Microsoft에서 제공 하는 데이터 커넥터 목록은 [타사 데이터 커넥터](archiving-third-party-data.md#third-party-data-connectors) 테이블을 참조 하십시오. 타사 데이터 커넥터의 표에는 Microsoft 365에서 데이터를 가져오고 보관 한 후 타사 데이터에 적용할 수 있는 규정 준수 솔루션 및 각 커넥터에 대 한 단계별 지침 링크가 요약 되어 있습니다.

Microsoft 365 데이터 커넥터에 대 한 자세한 내용은 [보관 타사 데이터](archiving-third-party-data.md)를 참조 하십시오. 타사 데이터 형식을 Microsoft 365 준수 센터에서 사용할 수 있는 데이터 커넥터에서 지원 하지 않는 경우에는 사용자 지정 커넥터를 제공할 수 있는 파트너와 함께 작업할 수 있습니다. 사용할 수 있는 파트너의 목록과이 방법의 단계별 프로세스에 대 한 자세한 내용은 [파트너와 협력 하 여 타사 데이터 보관](work-with-partner-to-archive-third-party-data.md)을 참조 하십시오.

### <a name="prerequisites-for-data-connectors"></a>데이터 커넥터의 필수 구성 요소

타사 데이터를 가져오고 보관 하기 위해 Microsoft 365 준수 센터에서 사용할 수 있는 많은 데이터 커넥터를 사용 하려면 타사 데이터 원본에서 구성 작업을 준비 하 고 수행 해야 합니다. 이러한 필수 구성 요소는 각 타사 데이터 커넥터에 대해 자세히 설명 되어 있습니다.

Microsoft의 파트너 중 하나가 제공 하는 Microsoft 365 준수 센터의 데이터 커넥터의 경우 커넥터를 배포 하려면 조직에 파트너와의 비즈니스 관계가 필요 합니다.

[Microsoft 365 준수 라이선스 비교](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) 문서에서 타사 데이터 커넥터에 대 한 라이선스 요구 사항을 확인할 수 있습니다.

## <a name="apis"></a>API

Microsoft 365 준수 Api는 Microsoft Information Protection SDK, Microsoft Graph API 및 Office 365 관리 활동 API에서 사용할 수 있습니다. 일부 준수 Api는 Microsoft 365 고객, 독립 소프트웨어 공급 업체, 시스템 통합자 및 관리 되는 보안 서비스 공급자가 높은 가치 보안 및 규정 준수 솔루션을 작성할 수 있도록 하는 새로운 보안 및 준수 Api 집합의 일부입니다.

Graph Api에 액세스 하는 방법에 대 한 자세한 내용은 [Overview In Microsoft Graph](https://docs.microsoft.com/graph/overview)를 참조 하십시오.

### <a name="microsoft-information-protection-mip-sdk"></a>밉 (Microsoft Information Protection) SDK

밉 SDK는 Microsoft 365 보안 및 준수 센터의 레이블 및 보호 서비스를 타사 응용 프로그램 및 서비스에 제공 합니다. 개발자는 SDK를 사용 하 여 파일에 레이블 및 보호를 적용 하는 기본 지원을 작성할 수 있습니다. 개발자는 특정 레이블이 검색 될 때 수행 해야 하는 작업을 결정 하 고, 밉 암호화 된 정보에 대 한 이유를 결정할 수 있습니다.

높은 수준의 밉 SDK 사용 사례는 다음과 같습니다.

- 내보낼 때 파일에 분류 레이블을 적용 하는 기간 업무 (lob) 응용 프로그램입니다.

- 밉에 대 한 기본 지원을 제공 하는 CAD/CAM 디자인 응용 프로그램입니다.

- Azure Information Protection을 사용 하 여 데이터를 암호화할 수 있는 클라우드 액세스 보안 브로커 또는 데이터 손실 방지 솔루션입니다.

밉 SDK, 필수 구성 요소, 추가 시나리오 및 샘플에 대 한 자세한 내용은 [밉 Sdk Overview](https://docs.microsoft.com/information-protection/develop/overview)를 참조 하세요.

### <a name="microsoft-graph-api-for-teams-dlp"></a>팀 DLP 용 Microsoft Graph API

Microsoft 팀에서는 조직이 원격 작업으로 이동 했을 때 [DLP (데이터 손실 방지)](dlp-microsoft-teams.md) 기능을 광범위 하 게 사용 합니다. 올해에는 팀의 메시지에 대 한 Microsoft Graph 변경 알림 API의 [공개 미리 보기가 발표](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) 되었습니다. 개발자는이 API를 사용 하 여 Microsoft 팀의 메시지를 거의 실시간으로 청취 한 다음 고객 및 파트너에 대해 DLP 시나리오를 구현할 수 있습니다. 또한 Microsoft Graph 패치 API를 사용 하 여 팀 메시지에 DLP 작업을 적용할 수 있습니다.

이러한 두 Api는 팀 DLP 용 Microsoft Graph API를 형성 합니다. [샘플 앱](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)을 사용해 볼 수 있습니다. Microsoft 팀 메시징 webhooks 대 한 자세한 내용은 [설명서](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)를 참조 하세요.

팀 DLP에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [보안 & 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)을 참조 하세요.

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>EDiscovery (미리 보기) 용 Microsoft Graph API

[고급 eDiscovery](overview-ediscovery-20.md)를 사용 하면 조직에서 데이터를 검색 하 고, 지능형 기계 학습 및 분석 기능을 통해 더 많은 종단 간 eDiscovery 워크플로를 관리 하 여 데이터를 Microsoft 365 보안 및 규정 준수 경계 내에서 유지 하면서도 데이터를 적절 한 집합으로 줄일 수 있습니다.

Graph for Advanced eDiscovery를 사용 하면 사례를 만들고 관리 하며, 집합을 검토 하 고, 확장 가능 하며 반복 가능한 방식으로 쿼리를 검토할 수 있습니다. 이렇게 하면 고객 및 파트너가 사례를 만들고 custodians 및 법적 보존을 관리 하는 등의 일반적인 프로세스를 자동화 하는 앱 및 워크플로를 만들 수 있습니다.

EDiscovery에 대 한 첫 번째 Graph Api 집합은 공개 미리 보기에서 사용할 수 있습니다. 일년 말까지 더 많은 기능을 추가할 예정입니다. 이러한 Api 및 고급 eDiscovery 용 기타 업데이트에 대 한 자세한 내용은이 [블로그](https://aka.ms/Ignite2020AeDAA)를 참조 하세요.

고급 eDiscovery 및 API에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [Microsoft 365 라이선스 지침에서 보안 & 준수에 대 한](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)"eDiscovery" 섹션을 참조 하십시오.

### <a name="microsoft-graph-api-for-teams-export-preview"></a>팀을 위한 Microsoft Graph API 내보내기 (미리 보기)

Microsoft 팀에 대 한 EIA (엔터프라이즈 정보 보관)는 고객의 주요 시나리오로, 규정 요구 사항에 대 한 해결이 가능 합니다. 고객 및 파트너는 Microsoft 팀의 콘텐츠를 보관 하기 위한 기본 제공 기능 외에도 사용자 지정 응용 프로그램 및 통합 시나리오에서 팀 내보내기 Api를 사용 하 여 해결할 수 있습니다. 팀 메시지 및 메시지 첨부 파일에 대 한 팀원 내보내기 Api는 대량 내보내기 (초당 최대 200 요청/테 넌 트/i e c e/i e 1/i a e/1/2 삭제 된 메시지는 삭제 후 최대 30 일 동안 API에서 액세스할 수 있습니다. 이러한 팀의 내보내기 Api와 응용 프로그램에서 사용 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 내보내기 api를 사용 하 여 콘텐츠 내보내기를](https://docs.microsoft.com/microsoftteams/export-teams-content)참조 하세요.

팀 내보내기 Api 사용에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [보안 & 준수에 대 한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조 하세요.
