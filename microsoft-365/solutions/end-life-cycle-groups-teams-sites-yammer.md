---
title: 그룹, 팀 및 팀에 대한 수명 주기 종료 옵션 Yammer
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
recommendations: false
description: 그룹, 팀 및 팀에 대한 수명 주기 종료 옵션 Yammer.
ms.openlocfilehash: fccdf838b7ebec6a1ab1fae2f709824bfbd3b6d1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192252"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>그룹, 팀 및 팀에 대한 수명 주기 종료 옵션 Yammer

Microsoft 365 그룹 및 Microsoft Teams 연결된 여러 서비스에서 작업합니다. 그룹 또는 팀이 삭제되면 연결된 서비스의 대부분의 정보도 삭제됩니다. 이 문서에서는 그룹 또는 팀에서 정보를 지우기 전에 정보를 보존하는 옵션에 대해 설명합니다.

더 이상 필요 없는 그룹 또는 팀의 일반적인 관행은 파일을 팀 밖으로 이동하여 파일 라이브러리와 같은 다른 위치에 SharePoint 것입니다. 이 방법은 정보가 파일 및 폴더에 저장되고 전자 메일을 통해 통신이 수행되는 레거시 작업 스타일을 기반으로 합니다.

다음 표에서는 그룹 및 팀과 연결된 서비스와 각 그룹에서 찾을 수 있는 주요 콘텐츠 유형에 대해 간략하게 설명합니다.

|서비스|콘텐츠 형식|
|:------|:---------------|
|Teams|채널 대화, 채널의 파일|
|Forms|설문 조사 구조 및 결과|
|OneNote|전자 필기장|
|Outlook|메일 및 일정|
|Planner|Project 및 작업 정보 표시|
|Power Automate|Workflows|
|Power BI|데이터, 보고서 및 대시보드|
|Project 웹에서 사용|Project 계획|
|로드맵|로드맵|
|SharePoint|파일, 목록, Teams 채널 위키 데이터|
|Stream|비디오|
|Yammer|Conversations|

그룹 또는 팀을 삭제할 때 대부분의 관련 자원도 삭제됩니다. 예외는 다음과 같습니다.

- Stream의 비디오는 그대로 유지 및 업로드/녹화한 사람이 소유합니다.
- 흐름은 Power Automate 그대로 유지되어 만든 사람이 소유합니다.
- Project 웹 Project 및 로드맵 데이터는 CDS에 유지되고 별도로 복원할 수 있습니다.

그룹 및 팀은 30일 동안 소프트 삭제 상태로 유지되고, 수시로 복원할 수 있습니다. 그러나 30일이 지난 후 서비스 및 콘텐츠와 같은 모든 관련 리소스는 해당 환경에서 Microsoft 365 제거됩니다. 보존 정책으로 보호되는 모든 콘텐츠는 eDiscovery 검색을 통해 계속 사용할 수 있습니다.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>그룹 연결 서비스에 대한 수명 주기 고려 사항 종료

팀과 그룹 소유자 및 IT 관리자가 그룹 또는 팀을 삭제하는 경우 고려해야 하는 세 가지 주요 영역이 있습니다.

**콘텐츠**

팀이 더 이상 존재하지 않는 경우 콘텐츠를 보존해야 하나요? 앱의 보존 기능에 Microsoft 365 또는 보존을 제공하지 않는 앱 및 서비스의 일부 콘텐츠인가요? 레코드 관리, 보관 또는 향후 사용 및 참조를 위해 콘텐츠를 보존해야 합니까?

잠재적인 데이터 손실을 방지하려면 팀을 보관하거나 삭제하기 전에 이러한 질문을 해야 합니다.

**서비스**

콘텐츠가 현재 작업 양식에 유지해야 하나요? 예를 들어 보고서에 Power BI 계속 액세스할 수 있도록 해야 합니까? 양식 결과를 시각적 요약 보기에서 사용할 수 있도록 해야 합니까? 목록의 목록이 SharePoint 또는 포함된 목록이 있습니까?

콘텐츠를 내보내는 것만으로는 충분하지 않을 수 있기 때문에 이러한 질문을 먼저 요청해야 합니다.

**게스트**

게스트가 팀에 초대되면 게스트 계정을 팀에 추가하기 전에 호스트 조직의 Azure Active Directory 생성됩니다. 팀이 삭제되면 게스트가 팀에서 Azure Active Directory. 게스트는 공유되지 않은 그룹, 사이트, 팀 또는 콘텐츠에 액세스할 수 없는 경우 채팅, 음성 및 화상 통화 시작, 앱 사용과 같은 Microsoft Teams 기능도 사용할 수 있습니다.

팀 또는 그룹 소유자는 조직 외부의 사람을 팀에 추가하여 조직 외부의 Azure Active Directory 초대할 수 있습니다. 그러나 팀 소유자는 게스트를 팀에서 제거할 수 Azure Active Directory. 계정 삭제는 전역 관리자 또는 사용자 관리자만 수행할 수 있습니다.

게스트 검토를 수행하고 게스트를 팀 삭제 시 게스트를 제거해야 Azure Active Directory 중요합니다. 게스트가 디렉터리에 남아 있는 경우(예: 다른 팀의 구성원이 되거나 다른 팀 또는 Azure 서비스 사용)Microsoft 365 있습니다.

## <a name="teams"></a>Teams

Teams 콘텐츠는 주로 대화 형식입니다.

채널의 대화는 기본 채널 기능을 사용하여 복사하거나 Microsoft Teams 없습니다. 그러나 이 API를 사용하여 내보낼 Graph 있습니다.

또한 보존 정책이 Teams eDiscovery 검색을 통해 대화가 보존되고 사용할 수 있습니다. 고급 eDiscovery를 사용하면 채팅 대화를 다시 Teams [수 있습니다.](/microsoft-365/compliance/conversation-review-sets)


### <a name="archiving-a-team"></a>팀 보관

팀을 [](/microsoftteams/archive-or-delete-a-team) 보관하면 팀이 있는 팀에 대한 모든 권한을 부여할 수 있습니다. 사용자는 활성 상태인 경우에도 채널 대화를 찾아보고 파일을 열 수 있습니다. 또한 프로젝트가 확장된 경우와 같은 작업을 계속해야 하는 경우 팀을 미지원할 수 있습니다.

팀이 소유자가 보관하는 경우 팀 내의 콘텐츠 및 선택한 경우 연결된 팀 사이트 모두에 대한 구성원에 대해 SharePoint 설정됩니다. 이 작업의 목표는 채널의 대화가 파일 및 위키와 같은 SharePoint 콘텐츠와 함께 기존 상태로 유지되도록 하는 것입니다.

사이트 SharePoint 변경 내용이 없습니다. 그러나 SharePoint 그룹의 사용 권한이 사이트 방문자로 설정되어 있기 때문에 파일이나 Microsoft 365 변경할 수 **없습니다.** 여기에는 OneNote 사이트 내의 사이트 자산 라이브러리에 저장되는 팀용 SharePoint 포함됩니다.

팀이 보관된 경우 Microsoft 365 그룹은 만료 정책(설정된 경우)을 계속 적용하며, 따라서 소유자는 팀을 계속 갱신해야 합니다.

팀의 채널 대화 및 SharePoint 콘텐츠가 읽기 전용으로 설정되어 있는 동안에는 다른 연결된 서비스에도 동일하게 적용되지 않습니다.

- Planner 버킷 및 작업은 여전히 생성, 수정 및 삭제할 수 있습니다.
- 양식은 계속 제출을 받을 수 있습니다.
- 사서함 Outlook 여전히 전자 메일을 받을 수 있습니다.
- Power BI 대시보드에서 보고서 및 데이터를 계속 수정할 수 있습니다.
- 프로젝트 및 로드맵은 웹용 Project 편집할 수 있습니다.
- Stream에서 비디오를 업로드, 수정 및 삭제할 수 있습니다.
- 흐름을 Power Automate, 수정, 삭제 및 계속 실행할 수 있습니다. 그러나 보관된 팀의 채널에 메시지를 게시해야 하는 경우 실패합니다.

## <a name="forms"></a>Forms

폼을 개별 계정에서 그룹으로 이동할 수 있는 경우 한 그룹에서 다른 그룹으로 양식을 이동하거나 복사할 수 없습니다. 팀이 삭제될 때 양식에 사용할 수 있는 세 가지 옵션이 있습니다.

**양식 복제**

양식을 서식 [파일로 공유하여](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)다른 사용자가 자신의 계정이나 그룹에 복사할 수 있습니다. 결과 제출의 데이터는 보존되지 않습니다. 질문 및 설정과 같은 양식 구조만

**결과를 스프레드시트로 내보내기**

양식 응답 데이터를 보존해야 하는 경우 결과를 Excel 스프레드시트로 내보낼 [수 있습니다.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) 이렇게 하면 질문과 응답만 데이터로 내보내지며 양식에서 만든 그래프는 포함하지 않습니다.

**양식 삭제**

그룹을 삭제하면 연결된 양식도 삭제되는 반면, 그룹 구성원은 그룹 소유자가 될 필요 없이 양식을 직접 삭제할 수 있습니다. [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) 그러나 이 단계는 추가 혜택을 제공하지 않는 수동 단계입니다.

## <a name="onenote"></a>OneNote

그룹에 OneNote 전자 필기장은 연결된 사이트 내의 사이트 자산 라이브러리에 SharePoint 저장됩니다. 전자 필기장 파일은 여러 개별 파일에 분산될 수 있는 경우도 있는 반면, 전자 필기장 파일은 독립적으로 복사하고 열 수 없습니다. 대신 전자 필기장의 내용을 OneNote 이동하거나 내보내야 OneNote 2016.

**페이지 및 섹션을 다른 전자 필기장으로 이동**

[페이지나 섹션을](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) 다른 전자 필기장으로 개별적으로 이동하면 소유자가 데이터를 정리하고 보존해야 하는 부분만 사용할 수 있습니다.

**전체 전자 필기장을 패키지로 내보내기**

전체 전자 필기장을 기존 구조로 유지해야 하는 [](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) 경우 전자 필기장을 OneNote 파일로 내보낼 수 있으며 새 위치로 가져올 수 있습니다. 대신 기존 다중 파일 구조 대신 단일 파일에 콘텐츠를 보존하는 방법으로 사용할 수 있습니다.

**PDF로 인쇄**

전자 필기장의 일부 내용을 참조나 레코드로만 보존해야 하는 시나리오에서는 개별 페이지를 PDF로 인쇄하여 다른 위치에 저장할 [수 있습니다.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>사서함 및 일정

팀 채널 내에서 많은 대화가 수행될 수 있는 경우에도 그룹 관련 사서함을 사용하는 것은 많지 않습니다. 사서함에는 직접 전자 메일로 전송된 전자 메일만 저장하고 채널로 직접 전송된 전자 메일은 포함하지 않습니다.

경우에 따라 사서함에 저장된 전자 메일은 모임 알림, Planner 작업 업데이트 및 기타 앱 또는 시스템 생성 메시지일 수 있습니다. 사서함의 내용을 검토하여 콘텐츠를 보존할지 또는 삭제할지 결정해야 합니다.

전자 메일에 보존 정책이 Exchange 전자 메일 및 일정 항목은 eDiscovery 검색을 통해 보존되고 사용할 수 있습니다.

**메일 및 일정 내보내기**

팀 또는 그룹 구성원은 사서함 및 일정의 내용을 [PST(Outlook /Personal Storage) 파일로 내보낼 수 있습니다.](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) 그런 다음 이 파일을 다른 위치에 저장하거나 콘텐츠를 다른 사서함으로 가져올 수 있습니다. PST 파일의 콘텐츠는 PST 파일에서 열지 않고 검색할 수 Outlook 시간이 경과하면 파일 자체가 손상될 수 있습니다.

**IT에서 수행한 콘텐츠 마이그레이션**

관리자는 타사 도구를 사용하여 사용자 개입 없이 사서함 간에 전자 메일 및 일정 콘텐츠를 마이그레이션할 수 있습니다. 하나의 잠재적인 저장소 위치는 그룹 사서함 콘텐츠의 "보관함"으로만 사용할 수 있는 공유 사서함일 수 있습니다.

## <a name="planner"></a>Planner

각 그룹 또는 팀에는 여러 계획이 있을 수 있습니다. 오프 보류 프로세스 중에 각 계획에 대한 보존 요구 사항을 충족하는 것이 중요합니다. 다른 서비스와 마찬가지로 Planner의 오프보드 콘텐츠에 대한 몇 가지 접근 방식이 있습니다.

**스프레드시트로 계획 내보내기**

레코드 유지를 위해 계획의 복사본만 보관해야 하는 경우 가장 간단한 방법은 계획을 Excel [것입니다.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) 이는 단방형 작업입니다. 스프레드시트에서 계획을 가져올 수 있는 옵션은 없습니다.

> [!IMPORTANT]
> 계획에 Excel 내보낼 경우 계획 내에서 대부분의 정보가 사용되지만 설명, 링크 또는 파일은 포함하지 않습니다.

**다른 계획으로 작업 복사 및 이동**

작업을 다른 계획으로 복사하거나 이동하는 작업은 솔루션처럼 보이나 개별 작업은 같은 그룹 내의 계획 간에만 복사하거나 [이동할](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) 수 있습니다. 계획과 연결된 그룹이 삭제되는 경우 데이터가 백업되지 않습니다.

**전체 계획 복사**

전체 계획을 복사할 [수도 있습니다.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) 기존 그룹에는 복사를 할 수 없습니다. 계획을 복사하면 새 그룹이 생성됩니다. 또한 전체 계획을 복사할 때 설명, 배정, 링크, 첨부 파일 또는 날짜는 포함하지 않습니다.

## <a name="power-automate"></a>Power Automate

그룹에서 Power Automate 또는 팀과 연결된 흐름은 그룹에 속하지 않습니다. 작성자가 소유하며 다른 사용자 및 그룹과만 공유됩니다. 따라서 그룹 또는 팀이 삭제된 경우 영향을 받지 않습니다.

**흐름의 소유권 변경**

흐름이 계속 작동해야 하는 경우 모든 소유자는 다른 사용자 또는 Microsoft 365 그룹을 소유자로 추가할 수 있습니다.

**흐름 내보내기**

흐름이 계속 작동할 필요는 없지만 나중에 사용할 수 있는 보존해야 하는 [](https://flow.microsoft.com/blog/import-export-bap-packages/) 경우 파일로 내보낼 수 있으며 나중에 다시 가져올 수 있습니다.

## <a name="power-bi"></a>Power BI

Power BI 및 작업 영역은 그룹 및 팀과 독립적으로 작동할 수 있으며 다른 워크로드와 마찬가지로 오프보드되는 다양한 방법을 제공합니다.

**다른 작업 영역으로 보고서 복사**

그룹 또는 팀이 삭제되면 보고서가 필요한 경우 기존 작업 영역의 보고서를 기존 작업 영역의 다른 작업 영역으로 복사할 [Power BI.](/power-bi/connect-data/service-datasets-copy-reports)

**대시보드 또는 보고서에서 데이터 내보내기**

대신 보고서를 더 이상 활성 상태일 필요는 없지만 데이터를 보존해야 하는 경우 에서 으로 [내보낼 수 Excel.](/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

웹용 Project 프로젝트 및 로드맵은 Microsoft 365 그룹과 연결되어 있으며 오프보드(off-boarding)와 유사한 Power BI.

**프로젝트를 다른 그룹에 할당**

프로젝트가 그룹 또는 팀의 수명 이후 기능 상태로 유지해야 하는 경우 다른 Microsoft 365 그룹에 할당할 [수 있습니다.](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) 이는 Dynamics 365 관리 센터를 사용하여 수행될 수 있습니다.

**프로젝트 또는 로드맵에서 데이터 내보내기**

Dynamics 365 관리 센터를 사용하여 프로젝트에서 스프레드시트로 사용자 데이터를 내보낼 수 있습니다. [](/project-for-the-web/export-user-data-from-project-for-the-web) 데이터를 파일()로 내보낼 Project 있습니다. PowerShell을 사용하여 MPP) 및 XML 파일 형식을 사용할 수 있습니다.

## <a name="sharepoint"></a>SharePoint

팀 채널의 모든 파일은 연결된 그룹의 SharePoint 사이트에 저장됩니다. 경우에 따라 목록이나 페이지와 같은 문서가 SharePoint 콘텐츠가 존재할 수 있습니다.

파일은 일반적으로 사이트 내의 세 가지 기본 위치에 SharePoint 저장됩니다.

- 페이지 - 사이트 페이지 라이브러리
- 페이지에 사용되는 이미지 - 사이트 자산 라이브러리
- 채널의 파일 - 문서 라이브러리
- Wiki 페이지 - Teams 데이터 라이브러리

사이트에 하나 이상의 하위 사이트가 있는 경우 각 하위 사이트에 대해 오프 보드 프로세스를 반복해야 합니다. 팀에 비공개 채널이 포함되어 있는 경우 각 채널에 대해 별도의 SharePoint 사이트가 있습니다.

그룹 또는 팀에서 파일을 제거할 때 그룹 또는 팀의 구성원이 아닌 사용자와 공유할 수 있는 것으로 고려해야 합니다. 임박한 변경 내용을 전달할 수 있습니다.

**파일 다운로드**

위에서 SharePoint 라이브러리 중 하나에 저장된 파일은 로컬 컴퓨터로 [다운로드할 수 있습니다.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**파일 이동**

또한 다른 사이트의 라이브러리와 같은 SharePoint 내의 다른 위치로 [파일을 이동할 수 있습니다.](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)

**목록 내보내기**

SharePoint 저장된 데이터는 Excel 스프레드시트로 내보낼 수 있으며 다른 사이트의 목록으로 다시 가져올 수 있습니다. [](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

또는 타사 도구를 사용하여 기능, 목록 보기, 서식 및 기타 특성을 유지 관리하기 위해 사이트 간에 목록을 마이그레이션할 수 있습니다.

**위키 파일 "내보내기"**

팀 채널 내의 위키 콘텐츠는 HTML 형식의 파일에 연결된 사이트 전용 라이브러리에 SharePoint 저장됩니다. 다른 채널 위키로 쉽게 내보내고 가져올 수 없지만 HTML 파일로 변환하고 웹 페이지로 열 수 있습니다.

## <a name="microsoft-stream"></a>Microsoft Stream

이 Power Automate 마찬가지로 그룹 또는 팀과 연결된 Stream의 비디오는 실제로 그룹 소유가 아니며 그룹이 삭제될 때 삭제되지 않습니다. Stream의 비디오는 사용자 또는 그룹을 소유자로 추가하는 경우에도 비디오를 업로드하거나 만든 사람이 소유합니다. Teams 채널에 기록된 모임은 녹음/녹화를 시작한 사람이 소유합니다.

**다른 소유자 추가**

그룹이 삭제될 때 비디오가 Stream에 유지될 수 있기 때문에 원래 소유자는 다른 사용자 및 그룹과 비디오를 공유하고 소유자로 추가할 [수도 있습니다.](/stream/portal-edit-video)

**비디오 다운로드**

비디오를 Stream에 유지할 필요가 없는 경우 또는 레코드 관리 시스템과 같은 대체 위치에 저장해야 하는 시나리오에서는 소유자가 로컬로 다운로드할 [수 있습니다.](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Microsoft Teams 대화와 Yammer 이동하거나 내보내기 위한 사용자 및 관리자 옵션을 모두 제공합니다.

**다른 그룹 또는 커뮤니티로 대화 이동**

대화는 소유자나 관리자만이 Yammer 다른 사용자 그룹으로 이동할 수 있습니다. 이는 클래식 인터페이스와 [](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) 새로운 Yammer [인터페이스에서 모두](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) Yammer 있습니다.

**네트워크 데이터 내보내기**

Yammer 네트워크 관리자가 네트워크 [데이터를 내보낼 수 있습니다.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) 그러나 이렇게 하면 전체 네트워크의 모든 대화가 내보내됩니다. 결과 내보내기에는 그룹 ID가 나열됩니다. 이 ID에 따라 대화를 필터링할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[이전 직원 제거 및 보안 데이터](/microsoft-365/admin/add-users/remove-former-employee)
