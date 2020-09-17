---
title: Microsoft 365의 공동 작업 관리 개요
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 그룹, 팀, SharePoint 및 Yammer에서 관련 기능을 제어 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b217dc089eb150d01eed9cd720b2caa290d54bf1
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950715"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Microsoft 365의 공동 작업 관리 개요

Microsoft 365에는 조직에 필요한 거 버 넌 스 기능을 구현 하기 위한 다양 한 도구가 포함 되어 있습니다. 이 문서에서는 IT 전문가를 대상으로 거 버 넌 스에 대 한 요구 사항을 확인 하 고 조직의 프로필을 기반으로이를 충족 하는 방법을 안내 합니다.

## <a name="what-are-microsoft-365-groups"></a>Microsoft 365 그룹 이란?

현재 조직은 다양 한 도구 집합을 사용 하 고 있음을 알 수 있습니다. 팀 채팅, 전자 메일 보내기, 엔터프라이즈 소셜를 통해 연결 되는 전체 조직 등을 사용 하는 개발자 팀이 있습니다. 여러 공동 작업 도구는 모든 그룹이 고유 하 고 고유한 기능 요구 사항 및 작업 스타일을 가지 므로 사용 됩니다. 일부 사용자는 전자 메일만 사용 하 고, 일부는 온라인 채팅에 살고 있습니다. 

사용자가 제공 하는 도구가 요구 사항에 맞지 않는 경우에는 해당 시나리오를 지 원하는 즐겨 사용 하는 소비자 앱을 다운로드 하 게 됩니다. 이 프로세스를 사용 하면 사용자가 작업을 빠르게 시작할 수 있지만, 여러 로그인을 사용 하는 조직 전체에서 사용자 환경이 원활 하 게 진행 되거나, 공유가 어려움을 야기 하 고, 콘텐츠를 볼 수 있는 단일 장소는 없습니다. 이 개념을 "섀도 IT" 이라고 하며 조직에 심각한 위험을 초래 합니다. 이를 통해 사용자 액세스를 일관 되 게 관리 하 고, 보안을 보장 하며, 서비스 규정 준수 요구 사항을 줄일 수 있습니다.

Microsoft 365 그룹, 팀, Yammer 등의 서비스를 통해 사용자에 게 도움을 주며, 공동 작업에 필요한 도구를 제공 하 여 섀도 복사본의 위험을 줄일 수 있습니다. Microsoft 365 그룹에서는 공동 작업을 수행 하려는 사용자 집합을 선택 하 고, 해당 사용자가 공유할 리소스 모음을 쉽게 설정할 수 있습니다. 그룹에 구성원을 추가 하면 그룹에서 제공 하는 모든 자산에 필요한 사용 권한이 자동으로 부여 됩니다. 팀과 Yammer 모두 Microsoft 365 그룹을 사용 하 여 해당 구성원 자격을 관리 합니다.

![Microsoft 365 그룹 및 관련 서비스를 보여 주는 다이어그램](../media/microsoft-365-groups-hub-spoke.png)

Microsoft 365 그룹에는 조직의 그룹을 관리 하는 데 도움이 되는 만료 정책, 명명 규칙 및 차단 된 단어 정책이 포함 된 다양 한 관리 방식 컨트롤이 포함 되어 있습니다. 자세한 내용은 [microsoft 365 그룹 및 Microsoft 팀에 대 한 조직 및 수명 주기 거 버 넌 스 계획](plan-organization-lifecycle-governance.md) 을 참조 하세요.

## <a name="technical-architecture"></a>기술 아키텍처

Microsoft 365에서 지 원하는 주요 통신 방법에는 다음 세 가지가 있습니다.

- Outlook: 공유 그룹 받은 편지함 및 일정을 사용 하 여 전자 메일 공동 작업
- Microsoft 팀: 다양 한 주제에 대 한 비공식적인 실시간 대화를 포함할 수 있는 지속적인 채팅 기반 작업 영역으로, 특정 하위 그룹으로 구성 됩니다.
- Yammer: 공동 작업용 엔터프라이즈 소셜 환경

> [!NOTE]
> SharePoint, Planner 또는 Stream과 같은 다른 팀 작업 응용 프로그램을 통해 새 그룹을 만들면 Outlook 받은 편지함 및 팀에 연결 하는 기능을 사용 하 여 그룹을 만들 수 있습니다.

그룹을 만든 위치에 따라 다음과 같은 특정 리소스가 자동으로 프로 비전 됩니다.
- [받은 편지함](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -그룹 구성원 간의 전자 메일 대화에 사용 됩니다. 이 받은 편지함에는 전자 메일 주소가 있으며, 기존 메일 그룹과 같이 그룹 외부에 있는 사람이 나 조직 외부의 메시지를 수락 하도록 설정할 수 있습니다.
 - [일정](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) -그룹과 관련 된 이벤트 예약
- [SharePoint 팀 사이트](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) -그룹에 관련 된 정보, 링크 및 콘텐츠를 위한 중앙 리포지토리입니다.
- [OneNote 전자 필기장](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) -아이디어, 리서치 및 정보를 수집 합니다.
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) -그룹 구성원 간에 프로젝트 작업을 할당 하 고 관리 하기 위한 것입니다.
- [Yammer 그룹](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) -대화 및 공유 정보를 저장할 수 있는 일반적인 장소입니다.
- 팀-Microsoft 365의 채팅 기반 작업 영역
- Stream-비디오 스트리밍 서비스

> [!NOTE]
> Yammer 또는 팀을 통해 새 Office 365 그룹을 만드는 경우 해당 사용자 간의 기본 통신은 해당 클라이언트에서 발생 하므로 Outlook 또는 주소록에 그룹이 표시 되지 않습니다. Yammer 그룹은 팀에 연결할 수 없습니다.

## <a name="collaboration-options"></a>공동 작업 옵션

공동 작업을 수행 하 고 Microsoft 365 내의 대화를 나눌 수 있는 위치가 여러 위치입니다. 대화를 시작 하는 위치를 이해 하면 통신 전략을 정의 하는 데 도움이 될 수 있습니다.

![팀, Yammer 및 Outlook을 사용 하는 경우를 보여 주는 다이어그램](../media/inner-loop-outer-loop.png)

- 팀: 채팅 기반 작업 영역 (고속 공동 작업) – 내부 루프
  - 매일 근무 하는 사람들과 공동 작업을 하도록 작성
  - 단일 환경에서 사용자에 게 간편 하 게 정보 저장
  - 탭, 연결선 및 인공 지능 추가
  - 실시간 채팅, 오디오/비디오 회의, 녹음 된 모임

- Yammer: 조직 전체에서 연결 (엔터프라이즈 소셜)-외부 루프
  - 일반적인 관심사 또는 전문 지식을 공유 하지만 일상적인 공동 작업을 수행 하는 데 필요 하지 않은 회사 간 업무 그룹의 커뮤니티
  - 리더십 연결, 학습 커뮤니티, 역할 기반 커뮤니티

- 사서함 및 일정 (전자 메일 기반 공동 작업)
  - 사용자 그룹의 대상 지정 통신에 사용
  - 다른 그룹 구성원이 있는 모임에 대 한 공유 일정
 
모든 그룹은 사용자가 콘텐츠를 공유 하 고 사용자 지정 된 페이지 및 작성자 뉴스를 만들 수 있는 연결 SharePoint 팀 사이트를 가져옵니다. [기존 SharePoint 팀 사이트를 새 Microsoft 365 그룹에 연결할](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)수도 있습니다.

## <a name="illustrations"></a>그림

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>IT 설계자용 Microsoft 365의 Microsoft Teams 및 관련 생산성 서비스
Microsoft Teams로 시장을 선도하는 Microsoft 365 생산성 서비스의 논리적 아키텍처입니다.

|**항목**|**설명**|
|:-----|:-----|
|[![Teams 논리 아키텍처 포스터의 축소판 그림 이미지](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>2019년 4월에 업데이트됨   |Microsoft는 생산성 서비스 제품군을 제공하여 데이터 관리, 보안 및 규정 준수 기능이 포함된 공동 작업 환경을 제공합니다. <br/> <br/>이 일러스트레이션 시리즈는 엔터프라이즈 설계자를 위해 Microsoft Teams로 시장을 선도하는 생산성 서비스의 논리 아키텍처를 보여줍니다.|


### <a name="groups-in-microsoft-365-for-it-architects"></a>IT 설계자용 Microsoft 365의 그룹
IT 설계자가 Microsoft 365의 그룹에 대해 알아야 하는 점

|**항목**|**설명**|
|:-----|:-----|
|[![그룹 인포그래픽용 축소판 이미지](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 2019년 6월에 업데이트됨|이러한 일러스트레이션은 다양한 그룹의 종류, 그룹을 만들고 관리하는 방법, 몇 가지 관리 권장 사항에 대해 자세한 설명을 제공합니다.|

## <a name="conference-sessions"></a>회의 세션

이러한 회의 세션을 시청 하 여 Microsoft 365 그룹 및 팀의 거 버 넌 스에 대 한 자세한 내용을 알아보세요.

**기초적인**

Microsoft 365 그룹의 주요 사항 및 새로운 혁신 기능에 대 한 자세한 내용은 확장성, 효율적인 사용 및 채택을 위한 모범 사례 및 셀프 서비스에 대 한 정보를 포함 합니다.

- [Microsoft 365 그룹 도입](https://www.youtube.com/watch?v=dAamBF1gb7M)

**거버넌스**

그룹 만료 수명 주기, 이름 지정 정책, 분류 레이블, 외부 게스트와의 공동 작업, 그룹 만들기 권한 관리 등을 설정 하는 방법에 대해 알아봅니다.

- [공동 작업을 변환 하 고 Office 365 그룹으로 섀도 사용](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**고객 예**

전체 공동 작업 플랫폼을 제공 하기 위해 Microsoft 365 그룹, SharePoint, 팀 및 Yammer가 함께 작동 하는 방식에 대 한 배후의 예를 참조 하세요.

- [Office 365 그룹, SharePoint, 팀 및 Yammer를 사용 하 여 공동 작업 찾기](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
