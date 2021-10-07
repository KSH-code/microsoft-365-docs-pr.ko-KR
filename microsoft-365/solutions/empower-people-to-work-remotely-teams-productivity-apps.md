---
title: 5단계. 하이브리드 작업자 생산성 앱 및 서비스 배포
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 사용자가 Teams, Exchange, SharePoint 및 기타 Microsoft 365 서비스를 사용하여 생산성을 향상시킬 수 있도록 합니다.
ms.openlocfilehash: 36aa96b1355eec41060881da26f7e709a5058898
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190152"
---
# <a name="step-5-deploy-hybrid-worker-productivity-apps-and-services"></a>5단계. 하이브리드 작업자 생산성 앱 및 서비스 배포

생산성을 높이려면 사용자가 서로 통신하고 공동 작업을 해야 합니다. 사용자들은 만나고, 음성 및 텍스트로 채팅하 고, 새 콘텐츠를 만들고, 정보 및 파일을 공유 하고, 전자 메일을 교환하고, 일정 및 작업을 관리해야 합니다. Microsoft 365는 다음과 같은 모든 주요 기능에 대한 클라우드 기반 서비스를 제공합니다.

| IT 기능 | Microsoft 365 구성 요소 | 설명 |
|:-------|:-----|:-------|
| 전자 메일 서비스 | Exchange Online | Exchange Online 및 Outlook을 이용하여 전자 메일을 교환하고 일정, 연락처, 작업을 관리 |
| 조직 채팅, VOIP(Voice over IP), 팀 기반 공동 작업 | Microsoft Teams | 조직, 부서, 소규모 팀 및 개인을 위한 모임, 채팅 및 파일 저장을 위한 공통의 통신 허브와 떨어져 있는 동안 사람들이 계속 연결되도록 합니다. |
| 인트라 사이트, 문서 공동 작업 | SharePoint 및 OneDrive | 웹 브라우저 내에서 또는 Teams 내에서 파일을 저장하고 공동 작업합니다. |
| 데스크톱 및 모바일 장치 Office 응용 프로그램 | Microsoft 365 앱 | 새 콘텐츠를 만들거나 로컬 컴퓨터에 설치된 Word, PowerPoint, Excel 및 Outlook 버전으로 기존 콘텐츠를 공동 작업하고 지속적인 기능 및 보안 업데이트를 받을 수 있습니다. |
||||

![Teams, Outlook, SharePoint, OneDrive 및 Microsoft 365 앱을 사용해서 생산성 유지.](../media/empower-people-to-work-remotely/remote-workers-productivity-grid.png)

## <a name="keep-people-connected-with-microsoft-teams"></a>Microsoft Teams를 통해 사용자들이 연결된 상태를 유지

Teams를 사용하면 한 곳에서 채팅, 모임, 통화, 공동 작업을 모두 수행할 수 있습니다. Teams는 팀워크를 위한 허브로 현장 또는 원격 작업을 하는 데 필요한 모든 것을 통합하고 있기에 수백만 명의 사용자가 매일 Teams에서 작업을 수행합니다. 

자세한 지침은 [Microsoft Teams를 사용하여 원격 작업자 지원하기](/microsoftteams/support-remote-work-with-teams)를 참조하세요. 

하이브리드 작업에 Teams 사용에 대한 지침 및 데모는 [Microsoft Teams 웹캐스트를 사용하여 하이브리드 작업 사용](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)을 시청하세요.

### <a name="chat-and-conversations"></a>채팅 및 대화

채팅 및 스레드된 대화는 개별 1:1 채팅 및 그룹 채팅 그리고 대화에 대한 지원과 함께 Teams의 중심에 있습니다. 원격 직원은 그룹 채팅 혹은 1:1 메시지를 통해 정보, 의견, 그리고 개성을 공유할 수 있습니다.

### <a name="meetings-and-conferencing"></a>모임 및 회의 

Teams는 확실히 하이브리드 작업자들이(특히 최대 250명을 지원하는 모임) 연락을 유지하고 정보를 공유하는 데 도움이 됩니다.  Teams는 모임은 통해 조직의 내부 및 외부 사용자들과의 대화형 공동 작업 모임을 가능하게 해줍니다. 원격 작업자는 되풀이되는 프로젝트 검사점, 동료들과의 연락 유지, 브레인스토밍 세션, 고객과의 대화 촉진을 비롯한 일상적인 활동에 Teams 모임을 사용할 수 있습니다. 

### <a name="calling"></a>통화

Teams는 페더레이션을 사용하는 사용자들 및 심지어 다른 조직들 간에 직접 VoIP 통화를 지원 합니다. 이는 모임과 동일한 코덱을 사용하고 추가 PSTN 요금없이 세계적으로 탁월한 환경을 제공 합니다. 그러나 일부 사용는 현장 또는 원격으로 작업할 때 외부 전화를 받으려면 전용 전화 번호가 필요할 수도 있습니다. Teams는 이러한 사용자들이 전화를 걸고 받을 수 있도록 클라우드 전화 서비스를 신속하게 제공할 수 있습니다.

### <a name="apps-and-workflows"></a>앱 및 워크플로

Teams는 데스크톱, 웹 및 모바일 버전의 Teams에서 액세스할 수 있는 앱 및 워크플로를 위한 플랫폼을 제공합니다. Teams는 사용자를 참여시키고 생산성을 지원하며 일반적으로 사용되는 비즈니스 서비스를 Teams로 통합하기 위해 Microsoft 및 타사에서 게시한 수백 개의 앱을 제공합니다. 사용자 및 관리자 또한 낮은 코드의 전원 앱과 전원 자동화 개발 도구를 사용하여 Teams용 사용자 지정 앱 및 자동화된 워크플로를 만들 수 있습니다.

앱과 워크플로는 하이브리드 작업자들이 중요한 정보를 수집 및 공유하고, 반복적인 작업을 자동화하며 대화형 봇과 채팅을 할 수 있도록 하여 Teams에서 그들의 생산성을 더욱 향상시킬 수 있도록 해줍니다. 앱을 채널이나 Teams 앱 바에 고정하는 것은 사용자가 이 앱을 관련 공간에서 쉽게 액세스할 수 있도록 하는 좋은 방법이며 관리자는 앱을 고정하여 모든 사용자가 사용해야 할 앱의 인식성 및 채택성을 견인할 수 있습니다.

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a>Exchange Online 및 Outlook을 이용하여 전자 메일을 교환하고 일정, 연락처, 작업을 관리

Outlook을 사용하면 하이브리드 작업자는 연결 상태를 유지하고 전자 메일, 일정, 연락처, 작업 등을 모두 함께 계속해서 한 곳에서 구성할 수 있습니다. Outlook을 사용하면 관련 항목에 따라 하루를 순조롭게 진행하고 우선순위를 지정하는 데 도움이 됩니다. Outlook은 OneDrive에서 바로 첨부 파일을 공유하고, 팀 모임을 계획하고 모임에 참여하며, 일정을 보고 공유하고 다른 사용자에게 대리인 권한을 제공할 수 있도록 해줍니다. 직장 및 개인적 용무 모두의 측면에서 다음에 처리할 용무와 주의를 필요로 하는 사항을 아는 것은 하이브리드 작업자들이 중요한 사항에 집중할 수 있도록 하는 데 도움이 됩니다. Outlook은 하이브리드 작업자들이 그들의 시간 및 필요로 하는 사항을(예를 들어, 파일, 조직 내 사용자 등) 쉽게 관리하는 데 유용한 방법들을 제공합니다. 

최신 인증 및 조건부 액세스를 지원하는 조직의 전자 메일 및 메일 클라이언트를 보호하는 권장 ID와 정책은 [이 문서](../security/office-365-security/secure-email-recommended-policies.md)를 참조하세요.

## <a name="store-and-collaborate-on-files-with-sharepoint-and-onedrive"></a>SharePoint 및 OneDrive를 사용한 파일 저장 및 공동 작업

콘텐츠 공동 작업의 경우 하이브리드 작업자는 SharePoint 및 OneDrive 폴더를 클라우드의 중앙 위치로 사용하여 파일을 저장하고, 공동 작성하고, 통신하고 공동 작업을 수행할 수 있습니다. 원격 작업자는 웹 브라우저, Teams 그리고 Office 앱을 통해 어디에서나 안전하게 작업을 수행할 수 있습니다.

다음에서 문서를 SharePoint 또는 OneDrive로 마이그레이션해야 할 수 있습니다.

- [SharePoint Server Team 사이트](/sharepointmigration/sp-teams-sites-migration-guide)
- [MySites](/sharepointmigration/mysites-to-onedrive-migration-guide)
- [파일 공유](/sharepointmigration/fileshare-to-odsp-migration-guide)
- [Box](/sharepointmigration/box-to-onedrive-and-sharepoint-migration-guide)

SharePoint 및 OneDrive를 보호하기 위해 권장 ID 및 장치 액세스 정책에 대해 [이 문서](../security/office-365-security/sharepoint-file-access-policies.md)를 참조하세요.

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a>Microsoft 365 앱을 사용한 콘텐츠 만들기 및 공동 작업

Microsoft 365 앱은 언제 어디에서나 사용자들이 원활하게 함께 작업할 수 있도록 해주는 기업에 가장 생산적이고 안전한 Office 환경입니다. 원격 작업자는 동시에 여러 사용자와 한 문서에 대해 공동 작업을 하고, 실시간으로 편집 및 변경된 내용을 보고, 모든 노트북, PC 또는 모바일 장치를 통해 다른 사용자들과 공동 작성할 수 있습니다.

자세한 내용은 [Microsoft 365 앱용 배포 가이드](/deployoffice/deployment-guide-microsoft-365-apps)를 참조하세요.

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a>생산성 앱 및 서비스를 위한 관리자 기술 리소스

- [Microsoft Teams를 사용하여 원격 작업자 지원하기](/microsoftteams/support-remote-work-with-teams)
- [Microsoft Teams 웹캐스트를 사용하여 하이브리드 작업 사용](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)
- [Teams 고객 성공 키트 다운로드](https://www.microsoft.com/download/details.aspx?id=54244)
- [Teams의 채택을 촉진하기 위한 도구](/microsoftteams/adopt-tools-and-downloads) 
- [Microsoft Teams에 대한 변경 관리 전략 만들기](/MicrosoftTeams/change-management-strategy)
- [세 가지 보호 계층이 있는 Teams](configure-teams-three-tiers-protection.md)

## <a name="user-training-resources-for-productivity-apps-and-services"></a>생산성 앱과 서비스에 대한 사용자 교육 리소스

- [Office 및 Microsoft 365에 대한 사용자 교육](https://support.microsoft.com/office/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27)
- [웹용 Office 사용](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a>다음 단계

[![6단계: 사용자 교육 및 사용자 성공 모니터링.](../media/empower-people-to-work-remotely/remote-workers-step-grid-6.png)](empower-people-to-work-remotely-train-monitor-usage.md)

[6단계](empower-people-to-work-remotely-train-monitor-usage.md)로 계속하여 사용자를 교육하고 사용자의 성공을 모니터링합니다.