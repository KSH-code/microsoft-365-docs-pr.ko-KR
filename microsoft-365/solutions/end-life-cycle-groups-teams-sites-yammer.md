---
title: 그룹, 팀 및 Yammer의 수명 주기 옵션 끝
ms.reviewer: mmclean
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
description: 그룹, 팀 및 Yammer에 대 한 수명 주기 옵션의 끝입니다.
ms.openlocfilehash: 31383287f3288cbab68d6e249f98210dec62af2f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681713"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>그룹, 팀 및 Yammer의 수명 주기 옵션 끝

Microsoft 365 그룹 및 Microsoft 팀은 다양 한 연결 서비스를 사용 하 여 작업 합니다. 그룹 또는 팀을 삭제 하면 연결 된 서비스에 있는 대부분의 정보도 삭제 됩니다. 이 문서에서는 삭제 전에 그룹 또는 팀에서 정보를 보존 하기 위한 옵션에 대해 설명 합니다.

더 이상 필요 하지 않은 그룹 또는 팀에 대 한 일반적인 방법은 파일을 팀에서 이동 하 여 저장소 또는 보관으로 작동 하는 SharePoint 문서 라이브러리와 같은 다른 위치에 저장 하는 것입니다. 이 방법은 파일 및 폴더 내에서 정보가 저장 되는 레거시 작업 스타일을 기반으로 하며, 전자 메일을 통해 통신이 수행 됩니다.

다음 표에서는 그룹 및 팀에 연결 된 서비스와 각 사용자에 게 있는 주요 콘텐츠 유형에 대해 간략히 설명 합니다.

|서비스|콘텐츠 형식|
|:------|:---------------|
|Teams|채널 대화, 채널의 파일|
|Forms|설문 조사 구조 및 결과|
|OneNote|노트북과|
|Outlook|메일 및 일정|
|Planner|프로젝트 상태 및 작업 정보|
|전원 자동화|Workflows|
|Power BI|데이터, 보고서 및 대시보드|
|웹의 프로젝트|프로젝트 계획|
|로드맵|로드맵|
|SharePoint|파일, 목록, 팀 채널 위 키 데이터|
|Stream|동영상|
|Yammer|Conversations|

그룹 또는 팀을 삭제 하는 경우 관련 리소스 대부분이 모두 삭제 됩니다. Stream의 비디오를 포함 하는 일부 예외는 그대로 유지 되며이를 업로드/녹화 한 사용자가 계속 소유 하며 전원 자동화의 흐름에 따라 진행 됩니다. Web의 Project에 있는 프로젝트 및 로드맵 데이터는 CD에 유지 되며 따로 복원할 수 있습니다.

그룹 및 팀은 일시 삭제 상태 이며 30 일 동안 유지 되며 언제 든 지 복원할 수 있습니다. 그러나 30 일 후와 서비스 및 콘텐츠와 같은 관련 리소스는 Microsoft 365 환경에서 완전히 제거 됩니다. 보존 정책에 의해 보호 되는 콘텐츠는 eDiscovery 검색을 통해 계속 사용할 수 있습니다.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>그룹 연결 서비스에 대 한 수명 주기 고려 사항 종료

그룹 또는 팀을 삭제할 때는 팀과 그룹 소유자 및 IT 관리자가 고려해 야 하는 세 가지 주요 영역이 있습니다.

**콘텐츠**

팀이 더 이상 작동 하지 않거나 존재 하지 않는 한 콘텐츠를 보존 해야 합니까? Microsoft 365의 보존 기능을 사용 하는 것이 충분 한지, 아니면 보존을 제공 하지 않는 앱 및 서비스의 콘텐츠 중 일부 입니까? 레코드 관리를 위해 콘텐츠를 보존 해야 하거나, 보관을 목적으로 하거나, 나중에 사용 하거나 참조용으로 사용할 수 있습니다.

잠재적인 데이터 손실을 방지 하기 위해 팀이 보관 되거나 삭제 되기 전에 이러한 질문에 대 한 요구 사항을 충족 해야 합니다.

**서비스**

다양 한 앱 및 서비스의 콘텐츠 위쪽에 현재 작업 중인 양식을 유지 해야 하는지 여부 예를 들어 Power BI 보고서에 계속 액세스할 수 있어야 하 고, 시각적 요약 보기에서 양식 결과를 사용할 수 있어야 하는 경우에는 SharePoint에 연결 되거나 포함 된 외부에 있는 목록 인지를 확인 합니다.

콘텐츠를 간단 하 게 내보낼 수 있는 것 처럼 기본 그룹을 삭제 하기 전에 이러한 사항을 고려해 야 합니다.

**게스트**

게스트를 팀에 초대 하면 워크플로에서 해당 사용자를 팀에 추가 하기 전에 호스트 조직의 Azure Active Directory에 해당 id를 만듭니다. 팀이 삭제 되 면 게스트가 Azure Active Directory에서 제거 되는 것이 아니며 여전히 Microsoft 팀 환경에 존재 합니다. 게스트가 공유 되지 않은 그룹, 사이트, 팀 또는 콘텐츠에 액세스할 수는 없지만 채팅, 음성 및 화상 통화, 앱 사용 등의 Microsoft 팀 내에서 기능을 활용할 수 있습니다.

팀 또는 그룹 소유자는 외부 사용자를 Azure Active Directory에서 게스트로 초대 하 여 팀에 추가 하 고 팀에서 제거할 수 있습니다. 그러나 팀 소유자는 Azure Active Directory에서 게스트를 제거할 수 없으며,이는 전역 관리자 또는 사용자 관리자만 수행 해야 합니다.

따라서 게스트 검토를 수행 하 고 팀 삭제 시에 게스트를 Azure Active Directory에서 제거 해야 하는지 여부를 이해 하는 것이 중요 합니다. 다른 하나 이상의 팀 구성원 이거나 다른 Microsoft 365 또는 Azure 서비스를 사용 하는 경우와 같이 게스트가 디렉터리에 남아 있는 경우에는 유효한 경우가 있을 수 있습니다.

## <a name="teams"></a>Teams

팀 관련 콘텐츠는 주로 대화 형태입니다.

기본 Microsoft 팀의 기능을 사용 하 여 채널의 대화를 복사 하거나 이동할 수는 없습니다. 그러나 Graph API를 사용 하 여 내보낼 수는 있습니다.

또한 보존 정책이 팀에 적용 되는 경우에는 해당 대화가 유지 되 고 eDiscovery 검색을 통해 사용 가능 합니다. EDiscovery 검색에 있는 항목을 내보낼 수는 있지만 원래 원본의 컨텍스트 또는 구조는 그대로 유지 되며 개별 메시지 일 뿐입니다.

### <a name="archiving-a-team"></a>팀 보관

[팀 보관](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) 의 이점은 사용자가 비활성 상태인 경우에도 여전히 채널 대화를 찾아보고 파일을 열 수 있도록 하기 위해 팀에 게 모든 권한을 제공 하는 것입니다. 또한 프로젝트 확장의 경우와 같이 작업을 계속 해야 하는 경우에는 팀이 unarchived 될 수 있습니다.

팀이 소유자에 의해 보관 되 면 팀 내의 콘텐츠에 대 한 구성원 및 관련 SharePoint 사이트 모두에 대해 읽기 전용으로 설정 됩니다. 이 작업의 목적은 채널의 대화가 파일 및 wiki와 같은 SharePoint 기반 콘텐츠와 함께 기존 상태에 보존 되도록 하기 위한 것입니다.

SharePoint 사이트에서는 변경 내용이 표시 되지 않지만 Microsoft 365 그룹의 SharePoint 기반 권한 그룹이 사이트 방문자 수준으로 설정 된 경우에는 어떠한 파일 또는 목록도 변경할 수 없습니다. 여기에는 SharePoint 사이트 내의 사이트 자산 라이브러리에 저장 되므로 팀의 OneNote 전자 필기장이 포함 됩니다.

팀이 보관 된 경우 기본 Microsoft 365 그룹에 여전히 만료 정책이 적용 되며 (설정 된 경우) 소유자는 계속 해 서 팀을 갱신 해야 합니다.

팀의 채널 대화 및 SharePoint 사이트 내용은 읽기 전용으로 설정 되어 있지만 관련 된 다른 서비스에는 적용 되지 않습니다.

- Planner 버킷 및 작업은 여전히 생성, 수정 및 삭제할 수 있습니다.
- 양식에서 계속 전송 가능
- Outlook 사서함은 여전히 전자 메일을 받을 수 있습니다.
- Power BI 대시보드, 보고서 및 데이터를 계속 수정할 수 있음
- 프로젝트 및 로드맵은 여전히 웹의 Project에서 편집할 수 있습니다.
- Stream에서 동영상을 계속 업로드, 수정 및 삭제할 수 있습니다.
- 절전 팀의 채널에 메시지를 게시 해야 하는 경우에도 전원 자동화의 흐름을 계속 만들고 수정 하 고 삭제할 수 있으며,이 작업은 실패 합니다.

## <a name="forms"></a>Forms

양식은 개별 계정에서 그룹으로 이동할 수 있지만, 그룹 간 이동 하거나 복사할 수는 없습니다. 팀을 삭제할 때 양식에 사용할 수 있는 옵션에는 세 가지가 있습니다.

**양식 복제**

양식을 [서식 파일로 공유](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)하 여 다른 사용자가 자신의 계정이 나 그룹에 복사할 수 있습니다. 결과 전송의 데이터는 보존 되지 않습니다. 질문 및 설정 등의 양식 구조만

**결과를 스프레드시트로 내보내기**

양식 응답의 데이터를 보존 해야 하는 경우에는 [결과를 Excel 스프레드시트로 내보내서](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)이를 달성할 수 있습니다. 이렇게 하면 질문과 응답이 데이터로 내보내기 되며 폼에서 만든 그래프가 포함 되지 않습니다.


**양식 삭제**

그룹을 삭제 하면 연결 된 양식이 모두 삭제 되지만 그룹 구성원은 그룹의 소유자가 아니므로 [직접 삭제할](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) 수 있지만,이는 추가 이점을 제공 하지 않는 수동 단계입니다.

## <a name="onenote"></a>OneNote

그룹에 포함 된 OneNote 전자 필기장은 연결 된 SharePoint 사이트 내의 사이트 자산 라이브러리에 저장 됩니다. 전자 필기장 파일은 여러 개별 파일에 분산 될 수 있지만 독립적으로 복사 하 고 열 수 없습니다. 대신 onenote 전자 필기장의 내용은 OneNote 2016을 사용 하 여 이동 하거나 내보내야 합니다.

**페이지 및 섹션을 다른 전자 필기장으로 이동**

[페이지 또는 섹션을 개별적으로 다른 전자 필기장으로 이동](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) 하면 소유자가 데이터를 정리 하 고 유지 해야 하는 작업만 수행할 수 있습니다.

**전체 전자 필기장을 패키지로 내보내기**

기존 구조를 사용 하 여 전체 전자 필기장을 보존 해야 하는 경우에는 해당 파일을 [OneNote 패키지 파일로 내보낸](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) 다음 새 위치로 가져올 수 있습니다. 또는이 메서드를 사용 하 여 기존 다중 파일 구조가 아닌 단일 파일에 콘텐츠를 보존 하는 방법으로 사용할 수 있습니다.

**PDF로 인쇄**

전자 필기장의 일부 콘텐츠를 참조 나 레코드로 보존 해야 하는 경우에는 개별 페이지를 [PDF로 인쇄 하 고 다른 위치에 저장할](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)수 있습니다.

## <a name="mailbox-and-calendar"></a>사서함 및 일정

팀 채널 내에서 많은 대화가 수행 되었을 수 있지만 그룹 연결 사서함을 사용 하는 경우는 흔하지 않습니다. 사서함에 직접 전자 메일로 전송 된 전자 메일만 저장 되 고 채널로 직접 보내진 전자 메일은 포함 되지 않습니다.

사서함에 저장 된 전자 메일이 단순히 모임, Planner 작업 업데이트 및 기타 앱 이나 시스템 생성 메시지에 대 한 알림을 받을 수 있는 경우도 있습니다. 콘텐츠를 유지할지 또는 삭제할지를 결정 하기 위해 사서함 내용을 검토 해야 합니다.

보존 정책이 Exchange에 적용 되는 경우 전자 메일 및 일정 항목은 보관 되며 eDiscovery 검색을 통해 사용할 수 있습니다.

**메일 및 일정 내보내기**

팀 또는 그룹 구성원은 [사서함 및 일정의 내용을 Outlook 데이터/개인 저장소 (PST) 파일로 내보낼](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)수 있습니다. 이 파일은 다른 곳에 저장 하거나 기타 사서함으로 가져올 수 있습니다. PST 파일의 내용을 Outlook에서 열지 않고 검색할 수 없는 경우에는 이전을 사용 하지 않는 것이 좋지만 시간이 지남에 따라 파일 자체가 손상 될 수도 있습니다.

**IT가 수행한 콘텐츠 마이그레이션**

관리자는 타사 도구를 사용 하 여 사용자 개입 없이도 사서함 간에 전자 메일 및 일정 내용을 마이그레이션할 수 있습니다. 잠재적인 저장 위치 중 하나는 그룹 사서함 콘텐츠의 "보관"으로 사용 하기 위해 단순히 만들어지는 공유 사서함 일 수 있습니다.

## <a name="planner"></a>Planner

각 그룹 또는 팀에 여러 요금제가 있을 수 있습니다. 오프 보 딩 프로세스를 수행 하는 동안 각 계획의 내용이 유지 되는지 여부를 확인 하는 것이 중요 합니다. 다른 제품과 마찬가지로 Planner에는 보드 콘텐츠를 몇 가지 방법으로 사용할 수 있습니다.

**계획을 스프레드시트로 내보내기**

레코드 보존 용도의 계획 복사본을 유지 해야 하는 경우에는 [계획을 Excel 스프레드시트로 내보내는](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)것이 가장 간단한 방법입니다. 이 작업은 스프레드시트에서 계획을 가져올 수 있는 옵션이 없기 때문에 단방향 동작입니다.

> [!IMPORTANT]
> 계획을 Excel로 내보내면 계획 내에서 대부분의 정보를 가져올 수 있지만 메모, 링크 또는 파일은 포함 되지 않습니다.

**다른 요금제로 작업 복사 및 이동**

이는 솔루션 처럼 보이지만, 계획에 연결 된 그룹을 삭제 하는 경우에는 각 작업을 동일한 그룹 내의 [계획 간에 복사 하거나 이동할](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) 수 있습니다.

**전체 계획 복사**

[전체 요금제를 복사할](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)수도 있습니다. 그러나이는 기존 그룹이 나 같은 그룹 내 에서도 사용할 수 없습니다. 요금제를 복사 하면 새 그룹이 만들어집니다. 또한 전체 계획을 복사 하는 경우에는 메모, 할당, 링크, 첨부 파일 또는 날짜가 포함 되지 않습니다.

## <a name="power-automate"></a>전원 자동화

전원 자동화로 만들어지고 그룹 또는 팀과 연결 된 흐름은 그룹에 속하지 않고, 대신 작성자가 소유 하며 다른 사용자 및 그룹과 공유 합니다. 따라서 그룹 또는 팀이 삭제 되어도 영향을 받지 않습니다.

**흐름 소유권 변경**

워크플로가 계속 해 서 작동 해야 하는 경우 모든 소유자는 다른 사용자 또는 Microsoft 365 그룹을 소유자로만 추가할 수 있습니다.

**흐름 내보내기**

작업을 계속할 필요가 없지만 나중에 사용할 수 있도록 워크플로를 보존 해야 하는 경우에는 [파일로 내보낸](https://flow.microsoft.com/blog/import-export-bap-packages/) 후 나중에 다시 가져올 수도 있습니다.

## <a name="power-bi"></a>Power BI

Power BI 데이터 및 작업 영역은 그룹 및 팀에서 독립적으로 작동할 수 있으며 다른 작업을 통해 다양 한 offboarded 방법을 제공 합니다.

**다른 작업 영역에 보고서 복사**

그룹 또는 팀의 수명 이후에 보고서를 해당 기능 상태로 유지 해야 하는 경우에는 [기존 작업 영역에서 POWER BI 내의 다른 작업 영역으로 복사할](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports)수 있습니다.

**대시보드 또는 보고서에서 데이터 내보내기**

또는 보고서가 더 이상 활성화 되지 않아도 되 고 데이터를 보존 해야 하는 경우 [Excel로 내보낼](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)수 있습니다.

## <a name="project"></a>Project

웹에서 프로젝트에 만든 프로젝트와 로드맵는 Microsoft 365 그룹과 연결 하 고 Power BI와 유사한 오프 보 딩에 대 한 접근 방식을 제공할 수 있습니다.

**프로젝트를 다른 그룹에 할당**

프로젝트를 그룹 또는 팀의 수명 보다 더 많은 기능 상태로 유지 해야 하는 경우 Dynamics 365 관리 센터를 사용 하 여 [다른 Microsoft 365 그룹에 할당할](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) 수 있습니다.

**프로젝트 또는 로드맵에서 데이터 내보내기**

Dynamics 365 관리 센터를 사용 하 여 프로젝트의 [사용자 데이터](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) 를 스프레드시트로 내보내거나 PowerShell 스크립트를 사용 하는 경우 데이터를 프로젝트 파일 (으로 내보낼 수 있습니다. MPP) 및 XML 파일 형식을 지정 합니다.

## <a name="sharepoint"></a>SharePoint
팀 채널의 모든 파일은 연결 된 그룹의 SharePoint 사이트에 있는 문서 라이브러리에 저장 됩니다. 문서 이외의 콘텐츠 (예: 목록 또는 페이지)가 SharePoint에 있는 경우도 있습니다.
파일은 일반적으로 SharePoint 사이트 내의 세 가지 기본 위치에 저장 됩니다.

- 페이지-사이트 페이지 라이브러리
- 페이지에 사용 되는 이미지-사이트 자산 라이브러리
- 채널의 파일-문서 라이브러리
- Wiki 페이지-팀 위 키 데이터 라이브러리

사이트에 하위 사이트가 하나 이상 중첩 되어 있으면 각 하위 사이트에 대해 오프 보 딩 프로세스를 반복 해야 합니다. 팀에 개인 채널이 포함 된 경우 각 채널 마다 별도의 SharePoint 사이트가 있습니다.

그룹 또는 팀에서 파일을 제거 하는 경우 그룹 또는 팀의 구성원이 아닌 사용자 (조직 내부 또는 외부)와 공유 될 수 있는 것으로 간주 하 고 이러한 작업에 대 한 임박한 변경 사항을 알리는 것이 유용할 수 있습니다.

**파일 다운로드**

위에 언급 된 라이브러리 중 하나에서 SharePoint 내에 저장 한 파일의 경우 [로컬 컴퓨터로 다운로드할](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)수 있습니다.

**파일 이동**

또한 파일을 다른 사이트의 라이브러리와 같이 SharePoint 내의 다른 위치로 이동할 수 있습니다.
참고할 https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**목록 내보내기** SharePoint 목록에 저장 된 데이터를 [Excel 스프레드시트로 내보낸](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)다음 다른 사이트의 목록으로 다시 가져올 수 있습니다.

또는 타사 도구를 사용 하 여 기능, 목록 보기, 서식 및 기타 특성을 유지 하기 위해 사이트 간에 목록을 마이그레이션할 수 있습니다.

**"Export" wiki 파일**

팀 채널 내의 위 키 내용은 연결 된 SharePoint 사이트의 전용 라이브러리에 있는 HTML 형식의 파일에 저장 됩니다. 이러한 파일은 쉽게 내보내고 다른 채널 wiki로 가져올 수 없으며, HTML 파일로 변환 하 여 웹 페이지로 열 수 있습니다.

## <a name="microsoft-stream"></a>Microsoft Stream

전원 자동화와 마찬가지로 그룹 또는 팀에 연결 된 Stream의 비디오는 실제로 그룹이 소유 하지 않으며, 그룹을 삭제 해도 삭제 되지 않습니다. Stream의 비디오는 사용자 또는 그룹을 소유자로 추가 하더라도 비디오를 업로드 하거나 만든 사람이 소유 합니다. 이는 팀 채널에 기록 된 모임의 경우에도 해당 됩니다. 녹음을 시작한 사용자가 소유 합니다.

**다른 소유자 추가**

비디오가 그룹 삭제에 관계 없이 Stream에 유지 되 면 원래 소유자는 [다른 사용자 및 그룹과 비디오를 소유자로 추가](https://docs.microsoft.com/stream/portal-edit-video)하 여이를 공유할 수 있습니다.

**비디오 다운로드**

비디오를 스트림에서 보존할 필요가 없거나 레코드 관리 시스템과 같은 대체 위치에 저장 해야 하는 시나리오에서는 소유자가 [로컬로 다운로드](https://docs.microsoft.com/stream/portal-download-video) 될 수 있습니다.

## <a name="yammer"></a>Yammer

Microsoft 팀의 대화와 달리 Yammer는 대화를 이동 하거나 내보내기 하기 위한 사용자 및 관리자 옵션을 제공 합니다.

**다른 그룹 또는 커뮤니티에 대화 이동**

대화를 소유자 또는 관리자 뿐만 아니라 모든 사용자가 다른 Yammer 그룹으로 이동할 수 있습니다. 이 기능은 [새로운 yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) 인터페이스 뿐 아니라 [클래식 yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)에서도 가능 합니다.

**네트워크 데이터 내보내기**

Yammer 네트워크 관리자는 [네트워크 데이터 내보내기를](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)수행할 수 있지만 이렇게 하면 전체 네트워크에 대 한 모든 대화가 내보내기 됩니다. 결과 내보내기에는 그룹 ID가 나열 되므로이를 기반으로 대화를 필터링 할 수 있습니다.
