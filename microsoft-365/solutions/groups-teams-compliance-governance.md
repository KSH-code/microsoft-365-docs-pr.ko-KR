---
title: Microsoft 365, Teams 및 SharePoint 준수 옵션
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 사용자 그룹, Microsoft 365 및 Teams 준수 옵션에 대해 SharePoint 대해 자세히 알아보습니다.
ms.openlocfilehash: acc32d6cff18e9535a29eeec773a5034480a3595
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207418"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365, Teams 및 SharePoint 준수 옵션

Microsoft 365 사용자는 공동 작업을 할 때 규정 준수를 유지하기 위한 전체 도구 모음을 제공합니다. 이러한 옵션을 검토하고 비즈니스 요구, 데이터의 민감도 및 사용자가 공동 작업해야 하는 사용자의 범위에 매핑되는 방법을 고려합니다.

다음 표에서는 이 문서에서 사용할 수 있는 준수 컨트롤에 대한 빠른 참조를 Microsoft 365. 추가 정보는 다음 섹션에서 제공됩니다.

|범주|설명|참조|
|:-------|:----------|:--------|
|정보 보존|||
||그룹 메일 및 SharePoint 보존|[SharePoint 및 OneDrive의 보존 정책에 대해 자세히 알아보기](../compliance/retention-policies-sharepoint.md)|
||채팅 및 메시지 보존|[Microsoft Teams의 보존 정책에 대해 자세히 알아보기](../compliance/retention-policies-teams.md)|
|정보 분류|||
||그룹 및 팀 분류|[민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)|
||중요한 콘텐츠 자동 분류|[민감도 레이블을 콘텐츠에 자동으로 적용](../compliance/apply-sensitivity-label-automatically.md)|
||중요한 콘텐츠 암호화|[민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한](../compliance/encryption-sensitivity-labels.md)|
|정보 보호|||
||중요한 정보 손실 방지|[데이터 손실 방지에 대해 알아보기](../compliance/dlp-learn-about-dlp.md)|
||채팅에서 중요한 정보를 보호합니다.|[데이터 손실 방지 및 Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||조직의 중요한 정보 정의|[사용자 지정 중요한 정보 유형](../compliance/sensitive-information-type-learn-about.md)|
|사용자 분할|||
||사용자 세그먼트 간 통신 제한|[정보 장벽](../compliance/information-barriers.md)|
|데이터 보존|||
||특정 지리적 위치에 데이터 저장|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>정보 보존

보존 정책은 파일, 메시지 및 메일을 포함하여 그룹 및 팀의 공동 작업에 사용되는 항목을 보존하거나 삭제할 수 있습니다. 정책을 보존 및 삭제, 보존만 또는 삭제만 하여 설정할 수 있습니다. 보존 정책이 적용하는 정보는 그룹 또는 팀이 만료되거나 다른 삭제될 경우 보호됩니다.

Microsoft 365 그룹에 대한 보존 정책을 구성하면 그룹 사서함 및 연결된 SharePoint 파일에 대해 다를 수 있습니다.

- [SharePoint 및 OneDrive의 보존 정책에 대해 자세히 알아보기](../compliance/retention-policies-sharepoint.md)

채팅 및 채널 Teams 보존 정책 채팅 및 채널 메시지는 Exchange 보존 정책의 영향을 받지 Exchange 않습니다. 채팅 및 채널 메시지에 적용할 보존 Teams 설정해야 Teams 합니다. 

사용자 계정이 삭제된 경우에도 사용자 채팅은 무기한 유지됩니다. 이 데이터를 무기한 보존하지 않는 경우 보존 정책을 사용하여 지정된 시간 후에 사용자 채팅을 삭제하거나 사용자 삭제 프로세스에 이 삭제를 포함하세요.

- [Microsoft Teams의 보존 정책에 대해 자세히 알아보기](../compliance/retention-policies-teams.md)

- [Microsoft Teams의 보존 정책](/microsoftteams/retention-policies)

단일 보존 정책을 설정하여 채팅 및 Teams 메시지에 적용할 Teams 있습니다. 

추가 리소스:

- [보존 정책에 대해 자세히 알아보기](../compliance/retention.md)

- [보존 태그 및](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) 보존 정책 Exchange

## <a name="information-classification"></a>정보 분류

민감도 레이블을 사용하여 게스트 액세스, 그룹 및 팀 개인 정보 보호, 그룹 및 팀에 대한 관리되지 않는 디바이스 액세스를 관리할 수 있습니다. 레이블을 적용하면 레이블 설정에 지정된 경우 이러한 설정이 자동으로 구성됩니다.

- [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](../compliance/sensitivity-labels-teams-groups-sites.md)

중요한 Microsoft 365 분류자와 패턴 일치를 검색하는 등 지정한 기준에 따라 파일 및 전자 메일에 민감도 레이블을 자동으로 적용하도록 구성할 수 있습니다.

- [민감도 레이블을 콘텐츠에 자동으로 적용](../compliance/apply-sensitivity-label-automatically.md)

민감도 레이블을 사용하여 파일을 암호화할 수 있으며, 사용 권한이 있는 레이블만 암호를 해독하고 읽을 수 있습니다.

- [민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한](../compliance/encryption-sensitivity-labels.md)

- [보안 격리를 사용하여 팀 구성하기](./secure-teams-security-isolation.md)

추가 리소스:

- [민감도 레이블에 대해 알아보기](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>정보 보호

DLP 정책은 사용자, 사용자 및 사용자 SharePoint 중요한 정보를 실수로 Exchange 방지할 수 Teams. 규칙 집합에 따라 수행할 작업(예: 액세스 차단)을 지정하는 정책을 만들 수 있습니다.

- [데이터 손실 방지에 대해 알아보기](../compliance/dlp-learn-about-dlp.md)

DLP는 Teams 포함된 메시지를 삭제하여 Teams 및 채널 메시지의 중요한 정보를 보호하는 데 도움이 될 수 있습니다.

- [데이터 손실 방지 및 Microsoft Teams](../compliance/dlp-microsoft-teams.md)

프로젝트 코드 이름과 같이 조직에 고유한 중요한 정보가 있는 경우 고유한 중요한 정보 유형을 만들어 DLP 정책에 적용하여 그룹, 팀 및 조직의 콘텐츠를 보호할 SharePoint.

- [사용자 지정 중요한 정보 유형](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>사용자 분할

정보 장벽을 사용하면 데이터와 사용자를 분할하여 그룹 간의 원치 않는 통신 및 공동 작업을 제한하고 조직에서 이해의 상충을 방지할 수 있습니다. 정보 장벽을 통해 조직의 사용자 그룹 간에 파일 공동 작업, 채팅, 통화 또는 모임 초대를 허용하거나 차단하는 정책을 만들 수 있습니다.

- [정보 장벽](../compliance/information-barriers.md)

- [Microsoft Teams의 정보 장벽](/microsoftteams/information-barriers-in-teams)

- [사용자와 정보 장벽 SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>데이터 보존

Multi-Microsoft 365 사용하여 데이터 상주 요구 사항을 충족하기 위해 선택한 지리적 위치에 미사용 데이터를 프로비전하고 저장할 수 있습니다. Multi-Geo 환경에서 Microsoft 365 테넌트는 중앙 위치(Microsoft 365 구독이 원래 프로비전된 위치)와 데이터를 저장할 수 있는 하나 이상의 위성 위치로 구성됩니다.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Microsoft 365 Business를 위한 계획](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>관련 항목

[공동 작업 거버넌스 계획 단계별](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[공동 작업 거버넌스 계획 만들기](collaboration-governance-first.md)

[보안 및 규정 Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[정보 보호](../compliance/information-protection.md)
