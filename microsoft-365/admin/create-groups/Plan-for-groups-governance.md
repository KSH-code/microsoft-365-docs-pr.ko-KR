---
title: 그룹 거 버 넌 스 계획
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Microsoft 365 그룹 거 버 넌 스를 계획 하는 방법을 알아봅니다.
ms.openlocfilehash: c37f88cbd3f41f22c1effdd7ba482033012aff01
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351842"
---
# <a name="plan-for-governance-in-groups"></a>그룹의 거 버 넌 스 계획

Microsoft 365 그룹에는 조직에 필요한 거 버 넌 스 기능을 구현 하기 위한 다양 한 도구가 포함 되어 있습니다. 이 문서에서는 IT 전문가를 대상으로 거 버 넌 스에 대 한 요구 사항을 확인 하 고 조직의 프로필을 기반으로이를 충족 하는 방법을 안내 합니다.

## <a name="why-microsoft-365-groups"></a>왜 Microsoft 365 그룹이 있나요?
![이미지 desc](../../media/01.png)

현재 조직은 다양 한 도구 집합을 사용 하 고 있음을 알 수 있습니다. 팀 채팅, 전자 메일 보내기, 엔터프라이즈 소셜를 통해 연결 되는 전체 조직 등을 사용 하는 개발자 팀이 있습니다. 여러 공동 작업 도구는 모든 그룹이 고유 하 고 고유한 기능 요구 사항과 작업 스타일을 가지 므로 사용 됩니다. 일부 사용자는 전자 메일만 사용 하 고, 일부는 온라인 채팅에 살고 있습니다. 

사용자가 제공 하는 도구가 요구 사항에 맞지 않는 경우에는 해당 시나리오를 지 원하는 즐겨 사용 하는 소비자 앱을 다운로드 하 게 됩니다. 이 프로세스를 사용 하면 사용자가 작업을 빠르게 시작할 수 있지만, 여러 로그인을 사용 하는 조직 전체에서 사용자 환경이 원활 하 게 진행 되거나, 공유가 어려움을 야기 하 고, 콘텐츠를 볼 수 있는 단일 장소는 없습니다. 이 개념을 "섀도 IT" 이라고 하며 조직에 심각한 위험을 초래 합니다. 이를 통해 사용자 액세스를 일관 되 게 관리 하 고, 보안을 보장 하며, 서비스 규정 준수 요구 사항을 줄일 수 있습니다.

Microsoft 365 그룹은 사용자에 게 도움을 주며, 공동 작업을 수행 하는 데 필요한 여러 도구를 한 단계로 제공 하 여 섀도 위험을 줄여줍니다. Microsoft 365 그룹에서는 공동 작업을 수행 하려는 사용자 집합을 선택 하 고, 해당 사용자가 공유할 리소스 모음을 쉽게 설정할 수 있습니다. 리소스에 사용 권한을 수동으로 할당 하는 것은 그룹에 구성원을 추가 하는 것이 그룹에서 제공 하는 모든 자산에 필요한 사용 권한을 자동으로 부여 하는 것 보다 더 이상입니다.

## <a name="technical-architecture"></a>기술 아키텍처

Microsoft 365 그룹에서 지 원하는 주요 통신 방법에는 세 가지가 있습니다. 이러한 환경 내에서 그룹을 만들고 Microsoft 365에서 사용할 수 있습니다.
- Outlook: 공유 그룹 받은 편지함 및 일정을 사용 하 여 전자 메일 공동 작업
- Microsoft 팀: 다양 한 주제에 대 한 비공식적인 실시간 대화를 포함할 수 있는 지속적인 채팅 기반 작업 영역으로, 특정 하위 그룹으로 구성 됩니다.
- Yammer: 공동 작업용 엔터프라이즈 소셜 환경

> [!NOTE]
> SharePoint, Planner 또는 Stream과 같은 다른 팀 작업 응용 프로그램을 통해 새 그룹을 만들면 Outlook 받은 편지함 및 Microsoft 팀에 연결 하는 기능을 사용 하 여 그룹을 만들 수 있습니다.

그룹을 만든 위치에 따라 다음과 같은 특정 리소스가 자동으로 프로 비전 됩니다.
- [받은 편지함](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -그룹 구성원 간의 전자 메일 대화에 사용 됩니다. 이 받은 편지함에는 전자 메일 주소가 있으며, 기존 메일 그룹과 같이 그룹 외부에 있는 사람이 나 조직 외부의 메시지를 수락 하도록 설정할 수 있습니다.
 - [일정](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) -그룹과 관련 된 이벤트 예약
- [SharePoint 팀 사이트](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) -그룹에 관련 된 정보, 링크 및 콘텐츠를 위한 중앙 리포지토리입니다.
- [SharePoint 문서 라이브러리](https://support.microsoft.com/en-us/office/share-group-files-in-outlook-749bc73b-90c9-4760-9b6f-9aa1cf01b403) -그룹이 파일을 저장 하 고 공유할 수 있는 중앙 위치입니다.
- [OneNote 전자 필기장](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) -아이디어, 리서치 및 정보를 수집 합니다.
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) -그룹 구성원 간에 프로젝트 작업을 할당 하 고 관리 하기 위한 것입니다.
- [Yammer 그룹](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) -대화 및 공유 정보를 저장할 수 있는 일반적인 장소입니다.
- Microsoft 팀-Microsoft 365의 채팅 기반 작업 영역

각 그룹에 대해 만들어지는 리소스에 대 한 자세한 내용은 [Microsoft 365 그룹에 대 한](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)자세한 정보를 참조 하세요.

> [!NOTE]
> Yammer 또는 팀을 통해 새 Microsoft 365 그룹을 만들 때 해당 사용자 간의 기본 통신은 해당 클라이언트에서 발생 하므로 Outlook 또는 주소록에 그룹이 표시 되지 않습니다. Yammer 그룹은 Microsoft 팀에 연결할 수 없습니다.

## <a name="where-to-start-a-conversation"></a>대화를 시작 하는 위치
Microsoft 365 내에 대화를 할 수 있는 위치가 여러 개 있습니다. 대화를 시작 하는 위치를 이해 하면 조직에서 통신 전략을 정의 하는 데 도움이 될 수 있습니다.

![이미지 desc](../../media/03.png)

- 팀: 채팅 기반 작업 영역 (고속 공동 작업) – 내부 루프
   - 매일 근무 하는 사람들과 공동 작업을 하도록 작성
  - 단일 환경에서 사용자에 게 간편 하 게 정보 저장
  - 탭, 연결선 및 인공 지능 추가
  - 실시간 채팅, 오디오/비디오 회의, 녹음 된 모임

- Yammer: 조직 전체에서 연결 (엔터프라이즈 소셜)-외부 루프
  - 일반적인 관심사 또는 전문 지식을 공유 하지만 일상적인 공동 작업을 수행 하는 데 필요 하지 않은 회사 간 업무 그룹의 커뮤니티
  - 리더십 연결, 학습 커뮤니티, 역할 기반 커뮤니티

- Outlook 그룹: 최신 DL (전자 메일 기반 공동 작업)
  - 대상 정보 교환에 대 한 장소
  - Dl을 Microsoft 365 Groups로 업그레이드 하 고 [업그레이드 해야 하는 이유는 무엇 인가요?](https://support.microsoft.com/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint-모든 Microsoft 365 그룹에 대 한 핵심 콘텐츠 공동 작업 환경
  - 모든 그룹은 연결 된 SharePoint 팀 사이트를 가져옵니다.
  - 콘텐츠 공유, 사용자 지정 된 페이지 및 만든이 뉴스 만들기
  - 기존 SharePoint 팀 사이트를 새 Microsoft 365 그룹에 [연결](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>확장에서의 Microsoft 365 관리 및 관리

Microsoft 365 그룹에는 조직에 필요한 거 버 넌 스 기능을 구현 하기 위한 다양 한 도구가 포함 되어 있습니다. 다음 섹션에서는 이러한 기능에 대해 설명 하 고 최상의 방법을 권장 하며, 거 버 넌 스에 대 한 요구 사항을 확인 하 고 문제를 충족 하는 방법을 문의할 수 있는 지침을 제공 합니다.

**이 섹션의 항목은**다음과 같습니다.
- [Microsoft 365 그룹을 만들 수 있는 사용자 제어](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [그룹 일시 삭제 및 복원](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [그룹 명명 정책](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [그룹 만료 정책](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [그룹 게스트 액세스](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [정보 보호 & 그룹 정책](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [기존 공동 작업 도구 업그레이드](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [그룹 보고](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>Microsoft 365 그룹을 만들 수 있는 사용자 제어
최종 사용자가 Outlook, SharePoint, 팀 및 기타 환경을 비롯 한 여러 최종 지점에서 그룹을 만들 수 있습니다.

![이미지 desc](../../media/04.png)
> [!Tip]
>- 그룹 소유자에 게 적용할 수 있는 셀프 서비스를 강력 하 게 고려 합니다.
>- 그룹을 요청 하는 방법을 문서화 하 고 전달 합니다.
>- 클라우드 여행 중에 그룹을 만들 수 있는 사용자를 다시 검토 합니다.
>- 동적 구성원 자격을 사용 하 여 그룹 만들기를 제어 하는 보안 그룹 구성원을 구성 하는 것이 좋습니다.
>- 동적 멤버 자격을 통해 관리할 수 있는 그룹 시나리오를 평가 하 고 rest를 위해 셀프 서비스를 허용 합니다.

그룹에는 공개, led 및 제어의 세 가지 기본 프로 비전 모델이 있습니다. 다음 표에서는 각 모델의 장점을 설명 합니다.

| 모델          | 장점                                                   |
| -------------- | ------------------------------------------------------------ |
| Open (기본값) | 사용자는 필요에 따라 자체 그룹을 만들어 기다리지 않고 직접 만들 수 있습니다. |
| IT-led         | 사용자가 여기에서 그룹을 요청 합니다. 이 가이드는 사용자의 요구에 가장 적합 한 공동 작업 도구를 선택 하는 데 도움이 될 수 있습니다. |
| 의해     | 그룹 만들기는 특정 사용자, 팀 또는 서비스로 제한 됩니다. 자세한 내용은 [Microsoft 365 그룹을 만들 수 있는 사용자 관리](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)를 참조 하세요. |

조직에는 그룹을 만들 수 있는 사용자에 게 엄격한 제어를 구현 하기 위한 특정 요구 사항이 있을 수 있습니다. 다음 표를 사용 하 여 조직에 적합 한 프로 비전 모델을 결정할 수 있습니다.

|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>조직 요구 사항에 맞는 프로 비전 모델</li><li>조직에서 관리자에 게 그룹 만들기를 제한 해야 하나요?</li><li>조직에서 그룹 만들기를 보안 그룹 구성원으로 제한 해야 하나요?</li><li>조직에서 부서와 같은 사용자 특성에 따라 동적으로 일부 그룹을 만들어야 합니까?</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>그룹 및 팀 만들기에 대 한 조직의 요구 사항을 문서화 합니다.</li><li>이러한 요구 사항을 그룹 롤아웃의 일부로 구현할 계획입니다.</li><li>사용자에 게 예상 되는 동작을 알리기 위해 정책 전달 및 게시</li><li>해당 하는 경우 동적 멤버 자격 구현 계획</li></ul>|

> [!Important]
> 그룹 및 팀 만들기를 제한 하면 서비스 작동을 위해 그룹을 만들어야 하는 Microsoft 365 서비스가 많으므로 사용자 생산성이 저하 될 수 있습니다. 자세한 내용은 [Microsoft 365 그룹을 만드는 이유를 제어 하는 이유](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups) 를 참조 하세요.

#### <a name="resources"></a>*리소스*
- [Microsoft 365 그룹을 만들 수 있는 사용자 관리](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [개체 특성에 따라 동적으로 그룹 채우기](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [Outlook 용 Microsoft 365 그룹의 기본 설정을 공용 또는 개인으로 변경 하는 방법](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [보안 그룹과 팀 멤버 자격 동기화](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>그룹 일시 삭제 및 복원
Microsoft 365 그룹을 삭제 한 경우에는 기본적으로 30 일 동안 보존 됩니다. 이 30일의 기간을 "일시 삭제"라고 하며 이 기간 동안 그룹을 복원할 수 있습니다. 30일이 지나면 그룹 및 관련 콘텐츠가 영구적으로 삭제되며 복원할 수 없습니다.

> [!Tip]
>- 복원 프로세스를 사용자에 게 알립니다.
>- 헬프데스크 팀을 교육 합니다.
>- PowerShell 스크립트를 사용 하 여 삭제할 예정 된 그룹을 추적 합니다.

|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>장기 저장소에 특정 자산이 보관 되어야 하나요?</li><li>조직에 대 한 특정 보존 요구 사항이 있습니까?</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>사용자에 게 예상 되는 동작을 알리기 위해 삭제 및 복원 정책 전달 및 게시 </li><li> 조직 요구 사항을 문서화 하 여 삭제 된 그룹을 모니터링 합니다.</li><li>그룹 구축의 일부로 이러한 요구 사항을 구현할 계획입니다.</li></ul>|

> [!Important]
>"소프트 삭제" 기간 동안 사용자가 사이트에 액세스를 시도하는 경우 403 금지 메시지가 표시됩니다. 이 기간 이후에 사용자가 사이트에 액세스하려고 하면 404 찾을 수 없음 메시지가 표시됩니다.

#### <a name="resources"></a>*리소스*
- [삭제 된 Microsoft 365 그룹 복원](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [Azure Active Directory에서 삭제 된 Microsoft 365 그룹 복원](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Remove-UnifiedGroup cmdlet을 사용하여 그룹 삭제](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>그룹 명명 정책
명명 정책을 통해 그룹, 구성원, 지리적 위치 또는 그룹을 만든 사용자의 기능을 식별 하는 데 도움이 될 수 있습니다. 또한 명명 정책은 주소록의 그룹을 분류 하는 데 도움이 됩니다. 정책을 사용 하 여 그룹 이름 및 별칭에 특정 단어를 사용 하지 못하도록 차단할 수 있습니다.

> [!Tip]
> - 짧은 문자열을 접미사로 사용 합니다.
> - 값과 함께 특성을 사용 합니다.
> - 창의적인 작업이 너무 많으면 총 이름 길이는 최대 264 자입니다.
> - 조직의 특정 차단 된 단어를 업로드 하 여 사용을 제한 합니다.


|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>조직에 그룹에 대 한 특정 명명 규칙이 필요 합니까?</li><li>조직에서 모든 작업의 명명 규칙을 요구 하나요?</li><li>조직에 사용자의 사용을 차단 하려는 특정 단어가 있습니까?</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>조직의 명명 그룹에 대 한 요구 사항을 문서화 합니다. </li><li> 그룹 구축의 일부로 이러한 요구 사항을 구현할 계획입니다.</li><li> 사용자에 게 알리기 위해 명명 정책 및 표준을 전달 하 고 게시 합니다.</li></ul>|

> [!Important]
>명명 정책은 모든 그룹 작업 (예: Outlook, Microsoft 팀, SharePoint, Planner, Yammer 등)에 걸쳐 만들어지는 그룹에 적용 됩니다. 그룹 이름과 그룹 별칭에 모두 적용 됩니다. 사용자가 그룹을 만들 때와 기존 그룹에 대 한 그룹 이름 또는 별칭을 편집한 경우에 적용 됩니다.

#### <a name="resources"></a>*리소스*
- [Microsoft 365 그룹 명명 정책](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Azure Active Directory에서 Microsoft 365 그룹에 대 한 명명 정책 적용](https://go.microsoft.com/fwlink/?linkid=868340)
- [그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
- [그룹 이름 지정을 위한 미리 보기 기능](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>그룹 만료 정책
관리자는 만료 기간을 지정할 수 있으며 해당 기간 끝에 도달 하 고 갱신 되지 않은 그룹은 삭제 됩니다. 만료 기간은 그룹을 만들 때 또는 마지막으로 갱신 된 날짜에 시작 됩니다. 그룹 소유자는 만료 되기 전에 자동으로 전자 메일을 보내 다른 만료 간격으로 그룹을 갱신할 수 있습니다. 활성 그룹은 자동으로 갱신 됩니다.

그룹 만료로 설정 하는 경우:
- 그룹 소유자에 게는 만료 됨에 따라 그룹 갱신을 알리는 알림이 표시 됩니다.
- 갱신 되지 않은 그룹은 삭제 됩니다.
- 삭제 된 그룹은 그룹 소유자 또는 관리자가 30 일 이내에 복원할 수 있습니다.

> [!Tip]
> - 초기에 특정 그룹을 사용한 파일럿
> - Microsoft 365 관리 센터의 활동 보고서를 기반으로 비활성 그룹을 선택 합니다.
> - 갱신 프로세스를 그룹 소유자에 게 전달 합니다.
> - 지원 센터 팀에 등록 합니다.
> - 그룹에 여러 소유자가 있고 고아 그룹에 대해 전자 메일을 구성 해야 합니다.


|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>조직에서 팀의 만료 날짜를 지정해야 하나요?</li><li>고아 그룹을 처리 하기 위한 전략을 결정 합니다.</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>조직의 그룹 만료, 데이터 보존 및 보관에 대 한 요구 사항을 문서화 합니다.</li><li>그룹 구축의 일부로 이러한 요구 사항을 구현할 계획입니다.</li><li>단일 소유자가 있거나 소유자가 낮은 그룹에 대해 보고할 사용자 지정 작업을 구현할 계획을 세워야 합니다. </li></ul>|

> [!Important]
>만료 정책을 변경 하면 서비스에서 각 그룹의 만료 날짜를 다시 계산 합니다. 항상 그룹을 만든 날짜부터 계산을 시작 하 고 새 만료 정책을 적용 합니다.

#### <a name="resources"></a>*리소스*
- [Microsoft 365 그룹 만료 정책](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [Microsoft 365 그룹에 대 한 만료 정책 구성](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>그룹 게스트 액세스
관리자는 전체 조직에 대 한 Microsoft 365 그룹 또는 개별 Microsoft 365 그룹에 대 한 게스트 액세스를 허용할지 여부를 제어할 수 있습니다. 또한 그룹에 게스트를 추가하는 사람을 제어할 수 있습니다.
>[!Tip]
>- 테 넌 트 수준에서 게스트 액세스를 사용 하도록 설정 합니다. 필요한 경우 특정 그룹을 차단 합니다.
>- Guest 도메인 허용/차단, 게스트 inviter 역할, 액세스 검토, 사용 약관을 사용 하 여 제어 합니다.
>- 감사 로그를 통해 게스트 사용자 활동을 추적 합니다.

|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>그룹 단위로 팀에 게스트를 추가 하는 기능을 제한 해야 하나요?</li><li> 조직에서 법적 또는 규정 준수 요구 사항에 관련 된 고 지 사항을 제공 해야 하나요?</li><li>조직에서 사용자를 추가 하 고 제거 하는 관리를 줄일 필요가 있습니까?</li><li>조직에서 게스트/외부 액세스에 대 한 감사 제어를 기대 하나요?</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>보존 기간 및 발생 빈도를 포함 하 여 특정 분류 그룹에 대 한 게스트/외부 액세스에 대 한 문서 요구 사항</li><li>사용 약관 및 액세스 검토를 필요로 하는 그룹에 대 한 문서 조직의 요구 사항 </li><li>검토를 수행 하 여 내부 및 게스트 사용자에 대 한 그룹 구성원 자격을 효율적으로 관리 합니다.</li></ul>|


#### <a name="resources"></a>*리소스*
- [조직 외부의 사용자와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [Microsoft 365 그룹에서 게스트 액세스 관리](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Microsoft 365 그룹의 게스트 액세스](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Azure AD 액세스 검토](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Azure Active Directory 사용 약관 기능](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google Federation](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>정보 보호 & 그룹 정책
Microsoft 365 그룹은 Microsoft 365의 고급 보안 및 규정 준수 기능을 기반으로 구축 되 고 분류, 감사 및 보고, 준수 콘텐츠 검색, 전자 검색, 법적 보유 및 보존 정책을 지원 합니다.
>[!Tip]
>- 조직의 요구 사항에 맞게 분류, 사용 지침 및 레이블을 구성 합니다.
>- 보존 정책은 레이블과 독립적으로 정의할 수 있습니다.
>- 감사 그룹 활동: 만들기, 삭제 등
>- 분류를 기반으로 그룹 개인 정보 및 게스트 액세스를 관리 합니다.

|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>조직에 모든 사용자에 게 전달 해야 하는 특정 사용 요구 사항이 있습니까?</li><li>조직에서 모든 콘텐츠의 분류가 필요 합니까?</li><li>조직에서 특정 기간 동안 콘텐츠를 보존 해야 하나요?</li><li>조직에서 특정 데이터 보존 정책을 그룹에 적용 해야 하는지 여부</li><li>조직은 콘텐츠를 보존 하기 위해 비활성 그룹을 보관 해야 할 것으로 예상 됩니까?</li><li>그룹 작성자가 팀에 조직별 분류를 할당할 수 있어야 합니까?</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>그룹에 대 한 조직의 사용 지침 문서화</li><li>조직의 분류 요구 사항을 문서화 합니다.</li><li>민감도, 보존, 게스트 액세스 등 분류에 따라 적용할 정책을 결정 합니다.</li><li>조직의 민감도 레이블과 연결 하려는 보호 설정을 정의 합니다.</li><li>레이블이 표시 되는 사용자 및 그룹을 제어 하는 레이블 정책을 정의 합니다.</li><li>[그룹 민감도 레이블 미리 보기](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) 를 구성 하 고 조직에서 그룹 분류를 시작 합니다.</li><li>이러한 요구 사항을 그룹 롤아웃의 일부로 구현할 계획입니다.</li></ul>|


#### <a name="resources"></a>*리소스*
- [Microsoft 365 Groups 링크 사용 지침](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [조직의 Office 그룹에 대 한 분류 만들기](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [그룹 설정 구성](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [보존 정책 개요](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [민감도 레이블 개요](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)
- [레이블 개요](https://docs.microsoft.com/microsoft-365/compliance/labels)
- [감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
- [원본 위치 유지 만들기 또는 제거](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [보존 정책 만들기](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [보안 & 준수 센터에서 콘텐츠 검색 실행](https://docs.microsoft.com/microsoft-365/compliance/content-search)
- [Windows PowerShell을 사용하여 보존 레이블 대량 생성 및 게시](https://docs.microsoft.com/microsoft-365/compliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>기존 공동 작업 도구 업그레이드
수년간 조직이 메일 그룹에 의존 하 여 회사 내부 및 외부의 사용자 그룹에 대 한 공동 작업을 수행 했습니다. 그러나 이제 Outlook의 Microsoft 365 그룹은 보다 강력한 공동 작업 솔루션을 제공 합니다. 또한 해당 사이트를 modernize 하려면 Microsoft 365 그룹을 기존 SharePoint 사이트에 연결할 수 있어야 합니다.

>[!Tip]
>- Exchange 관리 센터를 통해 또는 PowerShell cmdlet을 사용 하 여 모든 적합 한 메일 그룹을 초 단위로 쉽게 업그레이드 합니다.
>- 기존 SharePoint 팀 사이트를 새 Microsoft 365 그룹에 연결 합니다.

|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>조직에 업그레이드에 [적합 하지](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) 않은 메일 그룹이 있습니까?<li>가장 잘 마이그레이션되는 메일 그룹의 유형을 결정 합니다.</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>Microsoft 365 그룹으로 업그레이드할 수 있는 메일 그룹을 식별 합니다.</li><li>기존 SharePoint 팀 사이트를 분석 하 여 그룹으로 연결할 준비가 된 사이트를 확인 합니다.</li><li>회사의 다른 팀에 게 사용자의 메일 그룹 업그레이드를 알리는 것을 허용 하 고, 성공적인 작업을 위해 수행한 단계를 확인 하세요.</li></ul>|


#### <a name="resources"></a>*리소스*
- [Outlook에서 그룹으로의 DL (배포 목록) 업그레이드](https://aka.ms/whyupgradedls)
- Exchange 관리 센터를 통해 또는 [PowerShell 스크립트](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists) 를 통해 한 번 클릭으로 업그레이드
- [Microsoft 365 그룹으로 메일 그룹 마이그레이션-관리자 도움말](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [기존 SharePoint 사이트를 Microsoft 365 그룹에 연결:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [스캐너 데이터 분석 및 사용](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint Modernization 스캐너](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (GitHub에 있는 도구)

### <a name="groups-reporting"></a><a name="groups-reporting"></a>그룹 보고
Microsoft 365 보고서 대시보드에는 조직의 Microsoft 제품 전체에 대 한 활동 개요가 표시 됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다.
> [!TIP]
>- 그룹 보고서를 사용 하 여 조직의 Microsoft 365 그룹 활동에 대 한 정보를 파악 하 고 만들고 사용 중인 그룹의 수를 확인할 수 있습니다.
>-Microsoft 365 Groups report는 지난 7 일, 30 일, 90 일 또는 180 일 동안의 추세를 볼 수 있습니다.
>- 그룹 사서함 대화, 그룹 사이트/파일 활동, 외부 구성원 수를 포함 한 그룹 구성원에 대 한 세부 정보 간의 그룹 활동을 모니터링 합니다.
>- 사용 사례를 배우고 내부적으로 amplify 활성 그룹의 그룹 소유자에 게 도달할 수 있도록 주기적으로 모니터링 합니다.
>- 추가 통찰력을 위해 Power BI 콘텐츠 팩을 활용 합니다.


|         |         |         |
|---------|---------|---------|
|![이미지 desc](../../media/decision_point.png)|의사 결정 지점|<ul><li>조직에서 Microsoft 365 그룹 사용을 이해 하려면 일반 보고서가 필요 합니까?<li>조직에 외부 구성원이 있는 모든 그룹에 대 한 보고가 필요 합니까?</li></ul>|
|![이미지 desc](../../media/next_steps.png)|다음 단계|<ul><li>정기적으로 그룹을 검토 하는 조직의 요구 사항 활동 보고서를 문서화 합니다.</li></ul>|


#### <a name="resources"></a>*리소스*
- [관리 센터의 Microsoft 365 보고서](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Office 365 채택 콘텐츠 팩](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD 콘텐츠 팩](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph 그룹 활동 API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Microsoft 365 Groups Report (통합 그룹)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Azure Active Directory 포털에서 활동 보고서 감사](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph-델타 쿼리를 사용 하 여 변경 내용 추적](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>클라우드 도입을 기반으로 시작

Microsoft 365 그룹은 조직에서 요구할 수 있는 다양 한 거 버 넌 스 기능 집합을 제공 합니다. 모범 사례를 이해 하 고 적절 한 질문에 따라 거 버 넌 스에 대 한 요구 사항을 확인 하 고이를 충족 하는 방법에 대 한 지침은 다음 조직 프로필을 고려 하세요.

**다음과 같은 조직 프로필을 고려해 야 합니다.**
- 소규모 기업
- 중간 규모 기업
- 규제 또는 기업

### <a name="small-business"></a>소규모 기업
비즈니스 Essentials 및 Business Premium 요금제를 포함 하는 최소 Exchange Online 및 SharePoint Online 라이선스 및 Enterprise E1, E3 및 E5 요금제가 Azure Active Directory Premium license와 함께 Microsoft 365을 배포한 조직을 고려 합니다.

| 단계 | 설명 |
| --------------- | ------------------------------------------------------------ |
| 지침 |<ul><li>셀프 서비스 프로 비전 모델을 고려해 보십시오.</li><li> Outlook & SharePoint 사이트의 그룹은 [기본적으로 비공개로](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395)되어 있습니다.</li><li> 그룹은 기존 Dl (메일 그룹)을 일대일로 또는 PowerShell을 통해 대량으로 업그레이드 하 여 만들 수 있습니다. [배포 목록을 Microsoft 365 그룹으로 업그레이드를](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)참조 하세요.</li><li> 게스트 액세스를 사용 하도록 설정 하 되 허용/차단 게스트 도메인을 제어 합니다.</li><li> 그룹 보고를 사용 하 여 사용자가 그룹을 사용 하는 방법을 통찰력을 얻습니다.</li><li> 공동 작업을 위해 모든 사용자가 단일 팀의 일부가 되는 방식으로 조직 차원의 팀 Microsoft 팀 팀을 만드는 것이 좋습니다. </li></ul>|
| 다음 단계      |<ul><li>[JSON 스키마 참조](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)에 정의 된 작업을 사용 하 여 컨트롤에 대 한 기본 디자인을 정의 하는 [사이트 디자인 및 사이트 스크립트](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) 를 사용 하는 것이 좋습니다.</li><li>[그룹 보고](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)를 검토 합니다.</li><li>전체 그룹 및 비활성/활성 그룹을 추적 합니다.</li><li>사용 되는 Exchange 및 SharePoint 저장소를 모두 추적 합니다.</li><li>그룹 사서함 대화, 그룹 사이트/파일 활동 등을 통해 그룹 활동을 봅니다.</li></ul> |

### <a name="medium-sized-business"></a>중간 규모 기업
위의 권장 사항 외에, Azure Active Directory Premium P1 라이선스가 포함 된 Enterprise E3/E5 이상으로 Microsoft 365을 배포한 중간 규모의 비즈니스에 대해서는 다음 사항을 고려 하세요.

| 단계 | 설명 |
| --------------- | ------------------------------------------------------------ |
| 지침 |<ul><li>오픈 또는 IT-led 프로 비전 모델을 결정 합니다.</li><li> 부서와 같은 Azure AD 특성을 기반으로 [동적 멤버 자격 규칙](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) 에 연결 되는 특정 그룹을 만들 수 있습니다.</li><li> 조직 내에서 분류를 정의 합니다 (예: 고도의 기밀, 기밀 (기본값), 일반).</li><li>  보존 및 민감도와 같은 분류에 따라 정책을 정의 합니다.</li><li> SharePoint는 모든 Microsoft 365 그룹에 대 한 콘텐츠 서비스입니다. 세 가지 보호 계층 (기준, 중요 및 고도의 기밀) [에 대 한 SharePoint Online 사이트를](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) 디자인 하 고 배포 하는 방법을 고려 합니다. 이러한 3계층 보호에 대한 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)를 참조하세요.</li><li> 공용 및 개인 그룹은 기본적으로 GAL에 나열 됩니다. Microsoft 팀 외부에서 만들어진 GAL 전용 그룹에 표시할 그룹을 결정 합니다.  [Remove-unifiedgroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) cmdlet의 "HiddenFromAddressListsEnabled" 또는 "HidefromExchangeClients"를 사용 하 여 특정 그룹을 숨깁니다.</li></ul> |
| 다음 단계      |<ul><li>그룹을 효과적으로 유지 하는 데 도움이 되는 모범 사례를 사용자에 게 교육 하 고 내부 콘텐츠 정책에 대해 교육 하기 위한 [사용 지침](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) 을 정의 합니다. 예를 들어 분류, 정책 및 절차에 대해 설명 합니다. </li><li>그룹을 갱신 하거나 삭제 하는 만료 정책에 해당 그룹의 수명 주기 기간을 정의 합니다.</li><li>다음 사용자 지정 작업을 만들어 분류에 따라 정책을 구현 하는 것이 좋습니다.</li><li>개인 정보를 비공개로 설정 합니다.</li><li>외부 구성원/공유를 사용 하지 않도록 설정 합니다. </li><li>[소유자가 없는](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)그룹을 그룹 구성원에 게 알리기 위한 전자 메일</li><li>소유권 정책 적용 (최소 2 명의 소유자)</li><li> 분류를 기반으로 그룹에 대 한 보존 정책을 정의 합니다. </li><li>보존 정책 개요</li><li>Powershell을 사용 하 여 분류 및 [new-retentioncompliancepolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps)을 사용 하 여 그룹 식별</li><li>[JSON 스키마 참조](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)에 정의 된 작업을 사용 하 여 컨트롤을 정의 하려면 사이트 디자인 및 사이트 스크립트를 사용 하는 것이 좋습니다.</li><li>사이트 디자인 및 Microsoft 흐름 [을 사용 하 여 간단한 사이트 디렉터리를 작성 하는](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) 것이 좋습니다. 이 사이트 디자인을 사용 하 여 사이트를 만들 때마다 사이트의 세부 정보를 캡처하여 목록에 씁니다. </li></ul>|

### <a name="regulated-or-enterprise"></a>규제 또는 기업
위의 권장 사항 외에, Azure Active Directory Premium P1/P2 라이선스를 사용 하 여 최소한 엔터프라이즈 E3/E5를 사용 하 여 Office 365을 배포한 정부, 금융 서비스 또는 의료과 같은 고도로 규제 또는 대규모 입력 환경에 대해 다음을 고려해 야 합니다.

| 단계 | 설명 |
| --------------- | ------------------------------------------------------------ |
| 지침 |<ul><li> 분류를 기반으로 하 여 그룹과 연결 된 SharePoint 사이트의 데이터 거 버 넌 스에 대 한 정책을 정의 합니다.</li><li>[레이블 및 DLP를 사용 하 여 SharePoint Online 파일을 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)합니다.</li><li>[Azure Information Protection을 사용 하 여 SharePoint Online 파일을 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)합니다.</li><li> 사용자의 기본 설정 데이터 위치 ([다중 지역](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365))에 연결 된 지역으로 프로 비전 된 그룹 사이트입니다.</li><li> 외부 구성원이 있는 그룹에 대 한 구성원 자격 검토 ([액세스 검토](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview))</li><li>액세스를 받기 전에 직원 또는 게스트 사용자에 게 법적 또는 규정 준수 요구 사항에 대 한 관련 부인 여부를 확인 합니다. ([사용 약관](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou))</li><li>[외부 사용자도 포함 하는 특정 분류](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561)를 사용 하 여 Microsoft 365 그룹을 식별 하 고 보고 합니다.</li><li>그룹을 만들 때 [remove-unifiedgroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) Cmdlet (HiddenGroup 스위치 사용)을 사용 하 여 멤버 자격을 숨겨야 하는 보안 그룹을 만들어야 합니다.</li><li>[암호를 사용 하 여 콘텐츠에](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) 대 한 액세스를 제한 하 고 특정 Microsoft 365 그룹에 게시 하 여 조직의 [민감도 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 정의 합니다.</li><li>기밀 레이블을 사용 하 여 windows를 실행 하는 장치에 대 한 중요 한 콘텐츠가 [Windows Information Protection과의 민감도](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)를 유지 하지 않도록 합니다. |
| 다음 단계      | <ul><li> 사이트 디자인 및 사이트 스크립트를 사용 하 여 새 사이트를 만들 때 수행 되는 기본 [작업](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) 을 정의 합니다. 예를 들어 [외부 공유 설정을 구성](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) 하거나 [Microsoft Flow를 트리거하여 Azure 함수를 호출 하](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) 여 기본적으로 지원 되지 않는 구성을 적용 합니다. </li><li> [레이블과 DLP를 사용 하 여 SharePoint Online 파일](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) 을 Microsoft 365 그룹과 연결 된 사이트로 보호 하기 위한 요구 사항을 문서화 합니다.</li><li>Microsoft 365 그룹에 연결 된 [SharePoint Online 사이트 및 파일을 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-sharepoint-online-sites-and-files) 하기 위한 조직 요구 사항을 문서화 합니다. </li><li>콘텐츠를 보호 하기 위해 특정 사용자 또는 그룹에 [민감도 레이블을](hhttps://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 게시 하기 위한 조직 요구 사항을 문서화 합니다.</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>그룹 관리 기능 계획 검사 목록

Azure Active Directory를 통해 여러 그룹 관련 컨트롤을 관리할 수 있습니다. 그룹 설정 구성에 대 한 자세한 내용은 [그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)을 참조 하십시오.

다음 표를 사용 하 여 조직 요구 사항을 배포 하는 데 필요한 기능을 확인할 수 있습니다. 이를 통해 미리 계획을 수립할 수 있도록 필요한 라이선스를 결정 하는 데 도움이 됩니다.

| **기능**      | **세부 정보**                                    | **Azure AD Premium 라이선스 필요** | **결정 사항** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| 그룹 명명 정책 | 접두사-접미사 기반, 사용자 지정 차단 된 단어를 사용 합니다. | P1                                    |      TBD     |
| 그룹 분류 | 팀에 분류를 할당 합니다. | P1                                    |   TBD        |
| 그룹 게스트 액세스 | 게스트가 그룹에 추가 되는 것을 허용 하거나 차단 합니다. | 아니요                                    |  TBD        |
| 그룹 만들기 | 팀 만들기를 관리자로 제한 합니다. | 아니요                                    |   TBD        |
| 그룹 만들기 | 팀 만들기를 보안 그룹 구성원으로 제한 합니다. | P1                                    |     TBD      |
| 그룹 사용 지침 | 모든 그룹 만들기 끝점에 표시 되는 그룹 사용 지침 링크를 설정 합니다. | P1                                    |   TBD        |
| 숨겨진 멤버 자격 | 그룹의 구성원이 아닌 사용자 로부터 Microsoft 365 그룹의 구성원 숨기기 | 아니요                                    |   TBD        |
| 만료 정책 | 만료 정책을 설정 하 여 Microsoft 365 그룹의 수명 주기를 관리 합니다. | P1                                    |  TBD        |
| 그룹 활동 보고서 | 조직의 Microsoft 365 그룹 활동에 대 한 통찰력을 얻고 만들고 사용 중인 Microsoft 365 그룹의 수를 확인 합니다. | 아니요                                    |    TBD       |
| 보존 정책 | 보안 & 준수 센터에서 Microsoft 365 그룹에 대 한 보존 정책을 설정 하 여 특정 기간에 대 한 데이터를 보존 하거나 삭제 합니다. **참고:** 이 기능을 사용 하려면 Office 365 Enterprise e 3 이상에 대 한 라이선스가 필요 합니다. | 아니요                                    |    TBD       |
| 데이터 손실 방지 정책 | Microsoft 365 그룹 연결 사이트에서 중요 한 정보를 식별 하 고 실수로 공유 되지 않도록 합니다. **참고:** 이 기능을 사용 하려면 Office 365 Enterprise e 3 이상에 대 한 라이선스가 필요 합니다. | 아니요                                    |     TBD      |
| 보관 및 복원 | 더 이상 활성 상태가 아닌 팀을 보관 하지만 참조용으로 유지 하거나 나중에 다시 활성화 하려는 경우 | 아니요                                    |   TBD        |
| 액세스 검토 | 내부 및 게스트 사용자를 위해 그룹 구성원을 효율적으로 관리 하기 위해 검토 수행 | P2                                    |   TBD       |
| 사용 약관 | 조직에서 최종 사용자에 게 정보를 제공 하는 데 사용할 수 있는 간단한 방법입니다. 이 프레젠테이션은 사용자가 법적 또는 규정 준수 요구 사항에 대 한 관련 부인를 볼 수 있도록 합니다. | P1                                    |         TBD  |

