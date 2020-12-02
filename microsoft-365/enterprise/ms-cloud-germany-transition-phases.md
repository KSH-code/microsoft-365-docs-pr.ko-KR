---
title: 마이그레이션 단계 작업 및 영향
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 새 독일어 데이터 센터 지역의 Office 365 서비스로 Microsoft Cloud 전라남도 (Microsoft 클라우드 독일)로 이동 하는 경우의 마이그레이션 단계 작업 및 영향에 대해 설명 합니다.'
ms.openlocfilehash: 9ffdb0bbe60bdb96d6e110ac08cba4030272c7e9
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551660"
---
# <a name="migration-phases-actions-and-impacts"></a>마이그레이션 단계 작업 및 영향

Microsoft Cloud 독일에서 Microsoft Office 365 services의 독일 지역으로의 테 넌 트 마이그레이션은 각 작업에 대해 구성 된 작업 집합으로 실행 됩니다. 이러한 작업은 중요 한 데이터 및 환경이 Office 365 서비스로 마이그레이션될 수 있도록 합니다. 테 넌 트가 마이그레이션 큐에 추가 되 면 각 작업은 백엔드 서비스에서 실행 되는 일련의 단계에 따라 완료 됩니다. 일부 작업을 수행 하려면 관리자 또는 사용자가 작업을 수행 해야 하거나 마이그레이션이 [구성 된 방법](ms-cloud-germany-transition.md#how-is-the-migration-organized) 에 따라 실행 되는 단계에 대 한 사용 현황에 영향을 줄 수 있습니다.

다음 섹션에는 다양 한 마이그레이션 단계에서 진행 되는 작업에 대 한 작업 및 결과가 포함 되어 있습니다. 테이블을 검토 하 여 조직에 적용할 수 있는 작업 또는 효과를 확인 합니다. 필요에 따라 각 단계의 단계를 실행할 준비가 되었는지 확인 합니다. 필요한 단계를 완료 하지 못하면 서비스가 중단 될 수 있으며 Office 365 서비스에 대 한 마이그레이션 완료가 지연 될 수 있습니다.

## <a name="exchange-online"></a>Exchange Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 기존 조직 설정에 새 독일 지역이 추가 되 고 사서함이 Office 365 서비스로 이동 됩니다. | Exchange Online 구성은 새 로컬 이동 독일어 지역에 전환 조직에 추가 합니다. 이 Office 365 서비스 지역이 기본값으로 설정 되어 내부 부하 분산 서비스에서 Office 365 서비스의 해당 기본 지역으로 사서함을 다시 배포할 수 있도록 합니다. 이 전환에서는 두 사용자 (독일 또는 Office 365 서비스)가 동일한 조직에 있고 두 URL을 모두 사용할 수 있습니다. | Exchange Online | -사용자 및 서비스를 독일 Url에서 Office 365 서비스 Url ()로 전환 `https://outlook.office365.com` 합니다. <br><br> -사용자는 마이그레이션 중에 레거시 독일 Url을 통해 서비스에 계속 액세스 합니다. 즉시 동작이 필요 하지 않습니다. <br><br> -사용자는 Office Online 기능 (일정, 메일, 사용자)에 대해 office.com 포털 사용을 시작 해야 합니다. Office 365 서비스에 아직 마이그레이션되지 않은 서비스에 대 한 탐색은 마이그레이션될 때까지 작동 하지 않습니다. <br><br> -Outlook Web App은 마이그레이션 중에 공용 폴더 환경을 제공 하지 않습니다. |
|||||

마이그레이션 중인 조직의 차이점에 대 한 자세한 내용을 확인 하 고 Exchange Online 리소스를 마이그레이션한 후에는 [새 독일어 데이터 센터 지역에서 Office 365 서비스로 마이그레이션하는 동안 고객 환경의](ms-cloud-germany-transition-experience.md)정보를 검토 하십시오.

## <a name="exchange-online-protection"></a>Exchange Online Protection

백 엔드 Exchange Online Protection (EOP) 기능은 새 독일 지역으로 복사 됩니다. 

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| Exchange Online 라우팅 및 기록 메시지 세부 정보 마이그레이션 | Exchange Online에서는 외부 호스트에서 Office 365로의 라우팅을 사용할 수 있습니다. 외부 MX 레코드는 EOP 서비스에 대 한 경로로 전환 됩니다. 테 넌 트 구성 및 기록 세부 정보는 마이그레이션됩니다. | Exchange Online 고객 | -Microsoft-관리 되는 DNS 항목은 Office 365 전라남도 EOP에서 Office 365 서비스로 업데이트 됩니다. <br><br> -고객은 EOP 마이그레이션에 대 한 EOP 이중 쓰기 후 30 일 동안 기다립니다. 그렇지 않으면 데이터가 손실 될 수 있습니다. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

<!--

| Step(s) | Description | Applies to | Impact |
|:-------|:-----|:-------|:-------|
| SharePoint and OneDrive are transitioned. | SharePoint and OneDrive are migrated from Microsoft Cloud Deutschland to Office 365 services in this phase. Existing Microsoft Cloud Deutschland URLs are preserved (for example, `contoso.sharepoint.de`). Tokens that were issued by Microsoft Cloud Deutschland or Office 365 services are valid during the transition. | SharePoint customers | - Content will be read-only for two brief periods (less than x minutes) during migration. During this time, expect a "you can't edit content" banner in SharePoint. <br><br> - The search index won't be preserved, and may take up to 10 days to be rebuilt. <br><br> - SharePoint/OneDrive content will be read-only for two brief periods (less than x minutes) during migration. Users will see a "you can't edit content" banner briefly during this time. <br><br> - The search index may be unavailable while the index is rebuilt. During this period, search queries might not return complete results. <br><br> - Existing sites are preserved. |
|||||

--> 

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| SharePoint 및 OneDrive가 전환 되었습니다. | 이 단계에서는 SharePoint 및 OneDrive가 Microsoft Cloud 독일에서 Office 365 서비스로 마이그레이션됩니다. 기존 Microsoft Cloud 독일 Url은 보존 됩니다 (예: `contoso.sharepoint.de` ). Microsoft Cloud 독일 또는 Office 365 services에서 발급 한 토큰은 전환 중에 유효 합니다. | SharePoint 고객 | -마이그레이션하는 동안 두 가지 짧은 기간 동안 콘텐츠가 읽기 전용으로 설정 됩니다. 이 시간 동안에는 SharePoint에서 "콘텐츠를 편집할 수 없습니다." 배너가 예상 됩니다. <br><br> -검색 인덱스는 보존 되지 않으며 다시 작성 하는 데 최대 10 일이 걸릴 수 있습니다. <br><br> -마이그레이션 중 두 가지 짧은 기간 동안 SharePoint/OneDrive 콘텐츠가 읽기 전용으로 설정 됩니다. 이 시간 동안에는 "콘텐츠를 편집할 수 없습니다." 배너가 잠시 사용자에 게 표시 됩니다. <br><br> -인덱스를 다시 작성 하는 동안에는 검색 인덱스를 사용할 수 없습니다. 이 기간 동안에는 검색 쿼리가 전체 결과를 반환 하지 않을 수 있습니다. <br><br> -기존 사이트가 보존 됩니다. |
|||||


## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 비즈니스용 Skype를 팀으로 마이그레이션 | 기존 비즈니스용 Skype 고객은 유럽의 Office 365 서비스로 마이그레이션하고 Office 365 서비스의 독일 지역에서 Microsoft 팀으로 전환 됩니다. | 비즈니스용 Skype 고객 | -사용자는 마이그레이션 날짜에 비즈니스용 Skype에 로그인 할 수 없습니다. 10 일 전 마이그레이션 이전에는 최종 사용자에 게 비즈니스용 Skype 클라이언트에서 대역내를 통해 팀으로 업그레이드할 예정입니다. 또한이 변경 내용은 10 일 후에 수행 되도록 관리 센터에도 게시 됩니다. <br><br> -정책 구성이 마이그레이션됩니다. <br><br> -사용자는 팀으로 마이그레이션되고 마이그레이션 후 비즈니스용 Skype를 더 이상 사용할 수 없게 됩니다. <br><br> -사용자에 게 팀 데스크톱 클라이언트가 설치 되어 있어야 합니다. 비즈니스용 Skype 인프라에서 정책에 따라 10 일 동안 설치가 진행 되지만,이 작업에 실패 하면 사용자는 여전히 클라이언트를 다운로드 하거나 지원 되는 브라우저에 연결 해야 합니다. <br><br> -연락처 및 모임이 팀으로 마이그레이션됩니다. <br><br> -사용자는 고객 DNS 항목이 완료 될 때까지 시간 서비스와 Office 365 서비스 간 전환 간에 비즈니스용 Skype에 로그인 할 수 없습니다. <br><br> -연락처 및 기존 모임은 계속 해 서 비즈니스용 Skype 모임으로 작동 합니다. |
|||||
        
## <a name="subscription"></a>구독

| 단계 | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| 승인 없이 고객을 마이그레이션할 수 없습니다. | Microsoft는 다음 두 가지 방법 중 하나를 사용 하 여 마이그레이션할 수 있는 권한을 얻게 되므로 Microsoft에서 Office 365 services 인스턴스에 데이터 및 서비스를 전환 하는 기능을 제공 합니다. <br> Microsoft 기반 마이그레이션으로 관리자 참여할. <br> 고객은 Microsoft Cloud 독일 테 넌 트에서 구독을 갱신 하는 경우는 2020 년 5 월 1 일 이후입니다. 이러한 고객에 게 매달 마이그레이션에 대 한 알림이 제공 되며, 30 일을 기다리면 고객에 게 ICM을 취소 하 고 직접 옵트인 할 수 있습니다. | 모든 Office 고객 | -테 넌 트가 마이그레이션을 위해 consented으로 표시 되 고 관리 센터에서 확인을 표시 합니다. <br><br> -응답은 클라우드 독일 메시지 센터 테 넌 트에 게시 됩니다. 서비스 구성은 Microsoft Cloud 독일 endpoints에서 계속 됩니다. <br><br> -마이그레이션 단계 상태에 대 한 업데이트를 메시지 센터에서 모니터링 합니다. |
| 구독이 전송 되 고 라이선스를 다시 할당 합니다. | 테 넌 트가 Office 365 서비스로 전환 된 후에는 전송 된 Microsoft Cloud 독일 구독에 대해 해당 Office 365 서비스 구독을 구입 합니다. Microsoft Cloud 독일 라이선스를 할당 받은 사용자에 게 Office 365 서비스 라이선스가 할당 됩니다. 레거시 Microsoft Cloud 독일 구독은 완료 시 Office 365 서비스 테 넌 트에서 제거 됩니다. | 모든 Office 고객 | -이 단계에서는 기존 구독에 대 한 변경 내용이 차단 됩니다 (예: 새 구독 구입 또는 사용자 수가 변경 되지 않음). <br><br> -라이선스 할당 변경 내용이 차단 됩니다. <br><br> -Microsoft Cloud 독일 subscription이 해당 Office 365 서비스 구독으로 마이그레이션됩니다. 해당 구독의 Office 365 서비스 제공은 Microsoft ( _제공 매핑_ 도 알려짐)에서 정의 됩니다. <br><br> -Office 365 서비스가 제공 하는 기능 (서비스 계획)의 수는 원래 Microsoft Cloud 독일 서비스에서 제공 하는 것 보다 클 수 있습니다. Office 365의 사용자 라이선스는 유사한 Microsoft 클라우드 독일 기능 (서비스 계획)에도 동일 하 게 할당 됩니다. 모든 사용자의 사용자 라이선스가 새 기능에 자동으로 할당 됩니다. 필요한 경우 관리자는 해당 라이선스를 사용 하지 않도록 설정 하기 위해 명시적으로 작업을 수행 해야 합니다. <br><br> -구독 마이그레이션이 완료 되 면 Office 365 서비스 및 독일 구독은 Office 365 관리 포털에 표시 되 고 독일 구독 상태는 _구축_ 으로 설정 됩니다. <br><br> -사용자에 게 새 Office 365 서비스 구독에 연결 된 라이선스를 다시 할당 합니다. 독일 구독 또는 SKU Guid에 대 한 종속성이 있는 고객 프로세스는 모두 끊어지고 Office 365 서비스 제공을 통해 수정 해야 합니다. <br><br> -Office 365 서비스의 새 구독은 새로운 용어 (월별/분기별/매년)를 사용 하 여 구매 되며, 고객은 Microsoft Cloud 독일 구독의 사용 되지 않은 잔액에 대해 적절 하지 않은 환불을 받게 됩니다. <br><br> -Partner Microsoft Cloud 독일 테 넌 트는 마이그레이션되지 않습니다. CSP 고객은 같은 파트너의 새 Office 365 서비스 테 넌 트 아래에서 Office 365 서비스로 마이그레이션됩니다. 고객 마이그레이션 후에는 파트너가 Office 365 서비스 테 넌 트에서이 고객만 관리할 수 있습니다. <br><br> -테 넌 트 관리자가 사용 하지 않도록 설정 하지 않는 한 추가 기능 (예: Microsoft Planner 및 Microsoft Flow)을 사용할 수 있습니다. 사용자 라이선스에 할당 된 서비스 계획을 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [사용자 라이선스를 할당 하는 동안 Microsoft 365 services에 대 한 액세스 비활성화](disable-access-to-services-while-assigning-user-licenses.md)를 참조 하세요.  |
|||||

## <a name="next-step"></a>다음 단계

[추가 사전 작업 수행](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>추가 정보

시작 하기:

- [Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동 하는 경우:

- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
