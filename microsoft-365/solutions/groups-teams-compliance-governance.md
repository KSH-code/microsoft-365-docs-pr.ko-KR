---
title: Microsoft 365 그룹, 팀 및 SharePoint 공동 작업에 대 한 준수 옵션
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 그룹, 팀 및 SharePoint 공동 작업에 대 한 준수 옵션에 대해 알아봅니다.
ms.openlocfilehash: 0383b0728d9b8ea12ce75de8bf0e250932d14ae5
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377536"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365 그룹, 팀 및 SharePoint 공동 작업에 대 한 준수 옵션

Microsoft 365에서는 사용자가 공동 작업을 수행 하는 동안 준수를 유지 관리 하는 완전 한 도구를 제공 합니다. 이러한 옵션을 검토 하 여 비즈니스 요구 사항, 데이터의 민감도, 사용자가 공동 작업을 수행 하는 데 필요한 사용자 범위 등을 고려해 야 합니다.

다음 표에서는 Microsoft 365에서 사용할 수 있는 준수 컨트롤에 대 한 빠른 참조를 제공 합니다. 다음 섹션에서는 자세한 정보를 제공 합니다.

|범주|설명|참조|
|:-------|:----------|:--------|
|정보 보존|||
||그룹 보존 메일 및 SharePoint 콘텐츠|[SharePoint 및 OneDrive의 보존 정책에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||채팅 및 메시지 보존|[Microsoft Teams의 보존 정책에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|정보 분류|||
||그룹 및 팀 분류|[민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||중요 한 콘텐츠 자동 분류|[민감도 레이블을 콘텐츠에 자동으로 적용](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||중요 한 콘텐츠 암호화|[민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|정보 보호|||
||중요 한 정보의 손실을 방지 합니다.|[데이터 손실 방지 개요](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||채팅의 중요 한 정보를 보호 합니다.|[데이터 손실 방지 및 Microsoft 팀](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||조직의 중요 한 정보 정의|[사용자 지정 중요한 정보 유형](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|사용자 분할|||
||사용자 세그먼트 간 통신 제한|[정보 장벽](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>정보 보존

보존 정책은 파일, 메시지 및 메일을 포함 하 여 그룹 및 팀에서 공동 작업에 사용 되는 항목을 보존 하거나 삭제 하는 데 사용할 수 있습니다. 정책을 보존 및 삭제, 보존 전용 또는 삭제로 설정할 수 있습니다. 보존 정책이 적용 되는 정보는 그룹이 나 팀이 만료 되거나 삭제 될 경우 보호 됩니다.

Microsoft 365 그룹에 대 한 보존 정책을 구성 하면 그룹 사서함과 연결 된 SharePoint 사이트 및 파일이 포함 됩니다.

- [SharePoint 및 OneDrive의 보존 정책에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

팀에 대 한 보존 정책은 채팅 및 채널 메시지를 유지 합니다. 채팅 및 채널 메시지는 Exchange 사서함에 저장 되지만 Exchange 보존 정책의 영향을 받지 않습니다. 팀 대화방 및 팀 채널 메시지에 적용 되도록 보존 정책을 설정 해야 합니다.

- [Microsoft Teams의 보존 정책에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Microsoft Teams의 보존 정책](https://docs.microsoft.com/microsoftteams/retention-policies)

단일 보존 정책을 Microsoft 365 그룹, 팀 채팅 및 팀 채널 메시지에 적용 하도록 설정할 수 있습니다. 

추가 리소스:

- [보존 정책에 대한 자세한 정보](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- Exchange의 [보존 태그 및 보존 정책](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="information-classification"></a>정보 분류

민감도 레이블을 사용 하 여 게스트 액세스, 그룹 및 팀 개인 정보를 제어 하 고 그룹 및 팀을 위한 관리 되지 않는 장치에 대 한 액세스를 제어할 수 있습니다. 이 설정은 레이블을 적용 하 여 레이블 설정에 의해 지정 된 대로 자동으로 구성 됩니다.

- [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Trainable 분류자와 함께 중요 한 정보 유형 또는 패턴 일치를 검색 하는 등 지정한 조건에 따라 민감도 레이블을 자동으로 파일 및 전자 메일에 적용 하도록 Microsoft 365을 구성할 수 있습니다.

- [민감도 레이블을 콘텐츠에 자동으로 적용](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

민감도 레이블을 사용 하 여 파일을 암호화할 수 있으며,이를 해독 하 고 읽을 사용 권한이 있는 사용자만 허용 됩니다.

- [민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [보안 격리를 사용하여 팀 구성하기](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

추가 리소스:

- [민감도 레이블에 대해 알아보기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>정보 보호

DLP 정책을 통해 SharePoint, Exchange 및 팀 간에 중요 한 정보가 실수로 공유 되지 않도록 할 수 있습니다. 규칙 집합에 따라 수행 해야 하는 작업 (예: 액세스 차단)을 지정 하는 정책을 만들 수 있습니다.

- [데이터 손실 방지 개요](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

팀의 DLP는 중요 한 정보가 포함 된 메시지를 삭제 하 여 팀 채팅 및 채널 메시지의 중요 한 정보를 보호 하는 데 도움이 됩니다.

- [데이터 손실 방지 및 Microsoft 팀](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

프로젝트 코드 이름과 같이 조직에 고유한 중요 한 정보가 있는 경우 고유한 중요 한 정보 유형을 만들고이를 DLP 정책에 적용 하 여 그룹, 팀 및 Sharepoint의 콘텐츠를 보호할 수 있습니다.

- [사용자 지정 중요한 정보 유형](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>사용자 분할

정보 장애물을 사용 하 여 데이터와 사용자를 분할 하 여 그룹 간의 원치 않는 통신 및 공동 작업을 제한 하 고 조직에서 발생할 수 있는 충돌을 방지할 수도 있습니다. 정보 장애물을 사용 하면 조직 내 사용자 그룹 간의 파일 공동 작업, 채팅, 통화 또는 모임 초대를 허용 하거나 방지 하는 정책을 만들 수 있습니다.

- [정보 장벽](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Microsoft 팀의 정보 장벽](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [SharePoint에서 정보 장벽 사용](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>관련 항목

[Exchange Online의 보안 및 규정 준수](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[정보를 보호](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


