---
title: 통신 준수를 통해 채널 신호 검색
description: 통신 규정 준수를 통해 채널 신호를 검색하는 방법을 자세히 알아보하세요.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 9bbc79b82933c0e1586acbd08fa4e5792f949863
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335710"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>통신 준수를 통해 채널 신호 검색

통신 준수 정책을 사용하면 다음 통신 플랫폼 중 하나 이상에서 그룹으로 또는 독립 실행형 원본으로 메시지를 검색하도록 선택할 수 있습니다. 이러한 플랫폼에서 캡처된 통신은 사용자가 조직을 떠나 사서함이 삭제된 경우에도 기본적으로 각 정책에 대해 7년 동안 유지됩니다.

## <a name="microsoft-teams"></a>Microsoft Teams

공개 및 개인 Microsoft Teams 채팅 채널과 개별 채팅 모두에서 채팅 통신을 검사할 수 있습니다. 사용자가 선택된 Microsoft Teams 통신 준수 정책에 할당되면 사용자에 대한 채팅 통신이 사용자가 구성원으로 있는 모든 Microsoft Teams 자동으로 모니터링됩니다. Microsoft Teams 정책 서식 파일은 미리 정의된 정책 템플릿에 대해 자동으로 포함되며 사용자 지정 정책 템플릿에서 기본적으로 선택됩니다. Teams 준수 정책 조건과 일치하는 채팅을 처리하는 데 최대 48시간이 걸릴 수 있습니다.

개인 채팅 및 비공개 채널의 경우 통신 준수 정책은 최신 첨부 파일 검색을 지원합니다. 최신 첨부 파일은 OneDrive [](/onedrive/plan-onedrive-enterprise#modern-attachments) 메시지에 SharePoint [](/sharepoint/dev/solution-guidance/modern-experience-customizations) 사이트에서 Teams 파일입니다. 자동 처리를 위해 이러한 첨부 파일에서 텍스트가 자동으로 추출되고 활성 통신 준수 정책 조건 및 분류자와 일치하는 잠재적인 일치가 가능합니다. 최신 첨부 파일 검색 및 처리에 필요한 추가 구성은 없습니다. 정책 조건과 일치하는 첨부 파일에만 텍스트가 추출됩니다. 첨부 파일에 정책 일치도 있는 경우에도 정책이 일치하는 메시지의 첨부 파일에 대해 텍스트가 추출되지 않습니다.

다음 파일 형식에 대해 최신 첨부 파일 검색이 지원됩니다.

- Microsoft Word(.docx)
- Microsoft Excel(.xlsx)
- Microsoft PowerPoint(.pptx)
- 텍스트(.txt)
- Portable Document Format(.pdf)

최신 첨부 파일에 대한 추출된 텍스트는 정책에  대한 보류 중인 알림 대시보드의 관련 메시지에 포함됩니다. 첨부 파일에 대해 추출된 텍스트의 이름은 첨부 파일 이름(및 형식 확장명) 및 확장명 .txt 지정됩니다. 예를 들어ContosoBusinessPlan.docx첨부 파일에 대해 추출된 텍스트는  정책의 보류 ContosoBusinessPlan.docx.txt대시보드에 표시됩니다. 

추출된 첨부 파일 텍스트를 선택하여 *원본,* 일반 텍스트 또는 주석 보기에서 세부 정보를 볼 *수* 있습니다. 검토한 후 명령 표시줄 컨트롤을 사용하여 첨부 파일 텍스트를 확인하거나 조치를 취할 수 있습니다. 또한 통신 준수 검토 프로세스 외부에서 검토를 위해 첨부 파일을 다운로드할 수도 있습니다.

다음 그룹 관리 구성을 사용하여 그룹의 개별 사용자 채팅 및 채널 통신을 Teams.

- **채팅 Teams:** 개별 사용자를 할당하거나 [](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) 메일 그룹을 통신 준수 정책에 할당합니다. 이 설정은 일 대 일 또는 일 대 다 사용자/채팅 관계에 해당합니다.
- **채널 Teams:** 특정 Microsoft Teams 포함된 모든 Microsoft 365 채널 또는 사용자 그룹을 통신 준수 정책에 할당합니다. 다른 Microsoft Teams 채널 또는 Microsoft 365 그룹에 동일한 사용자를 추가하는 경우, 반드시 커뮤니케이션 규정 준수 정책에 이러한 새 채널 및 그룹을 추가해야 합니다. 채널의 구성원이 정책 내에서 감독된 사용자인  경우 인바운드 방향이 정책에서 구성된 경우 채널 내에서 전송된 모든 메시지는 명시적으로 감독되지 않는 채널의 사용자라도 검토 및 잠재적인 정책 일치가 적용될 수 있습니다. 예를 들어 사용자 A는 채널의 소유자 또는 구성원입니다. 사용자 B와 사용자 C는 동일한 채널의 구성원으로, 사용자 A만 감독하는 공격적인 언어 정책과 일치하는 언어를 사용하게 됩니다. 사용자 B와 사용자 C는 공격적인 언어 정책에서 직접 감독되지 않는 경우에도 채널 내의 대화에 대한 정책 일치를 생성합니다. Teams 포함된 채널 외부에 있는 사용자 B와 사용자 C 간의 대화에는 사용자 A를 포함하는 공격적인 언어 정책이 사용되지 않습니다. 채널의 다른 구성원이 명시적으로 감독되는 경우 채널 구성원을 감독에서 제외하기 위해 해당 통신 준수 정책에서 인바운드 통신 방향 설정을 해제합니다. 
- **하이브리드 Teams** 환경과의 채팅 통신의 경우: 통신 규정 준수는 Exchange 배포 또는 외부 전자 메일 공급자가 하이브리드 전자 메일 환경을 사용하도록 설정한 조직의 사용자에 대해 채팅 메시지를 모니터링할 Microsoft Teams. 모니터링할 사서함이 있는 사용자에 대한 메일 그룹을 만들어야 합니다. 통신 준수 정책을 만들 때 이 메일 그룹을  정책 마법사에서 감독된 사용자 및 그룹 선택으로 할당합니다. 클라우드 기반 저장소를 사용하도록 설정하기 위한 요구 사항 및 제한 사항에 대한 자세한 내용은 Teams 사용자에 대한 Teams 채팅 데이터 검색을 [참조하세요.](search-cloud-based-mailboxes-for-on-premises-users.md)

## <a name="exchange-email"></a>Exchange 전자 메일

Exchange Online 또는 Microsoft 365 구독의 일부로 Office 365 사서함은 모두 메시지 검색을 사용할 수 있습니다. Exchange 준수 정책 조건과 일치하는 전자 메일 메시지 및 첨부 파일을 처리하는 데 최대 24시간이 걸릴 수 있습니다. 커뮤니케이션 규정 준수를 위해 지원되는 첨부 파일 형식은 [Exchange 메일 흐름 규칙 콘텐츠 검사에 대해 지원되는 파일 형식](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)과 동일해야 합니다.

## <a name="yammer"></a>Yammer

커뮤니티의 개인 메시지 및 공개 대화 및 Yammer 첨부 파일을 검색할 수 있습니다. 사용자가 정의된 채널로 Yammer 포함된 통신 준수 정책에 사용자를 추가하면 사용자가 구성원으로 있는 Yammer 모든 커뮤니티의 통신이 검사 프로세스에 포함됩니다. Yammer 준수 정책 조건과 일치하는 채팅 및 첨부 파일을 처리하는 데 최대 24시간이 걸릴 수 있습니다. 

Yammer 통신 및 [](/yammer/configure-your-yammer-network/overview-native-mode) 첨부 파일을 모니터링하려면 통신 준수 정책의 기본 Yammer 있어야 합니다. 기본 모드에서는 모든 Yammer 사용자가 Azure Active Directory(AAD)에 있으며 모든 그룹은 Office 365 그룹으로 설정되고 모든 파일은 SharePoint Online에 저장됩니다.

## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

비즈니스용 Skype 온라인의 채팅 통신 및 관련 첨부 파일을 감독할 수 있습니다. 커뮤니케이션 규정 준수 정책 조건과 일치하는 비즈니스용 Skype Online 채팅을 처리하는 데에는 최대 24시간이 걸릴 수 있습니다. 감독되는 채팅 대화는 온라인 에서 저장한 이전 [비즈니스용 Skype 있습니다.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  

다음 그룹 관리 구성을 사용하여 온라인에서 사용자 채팅 통신을 비즈니스용 Skype 있습니다.

- **비즈니스용 Skype 온라인 채팅** 통신의 경우: 개별 사용자를 [](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) 할당하거나 통신 준수 정책에 메일 그룹을 할당합니다. 이 설정은 일 대 일 또는 일 대 다 사용자/채팅 관계에 해당합니다.

## <a name="third-party-sources"></a>타사 원본

[Instant Bloomberg,](archive-instant-bloomberg-data.md) [Slack Microsoft 365](archive-slack-data.md) [Zoom,](archive-zoommeetings-data.md)SMS 및 기타 여러 타사 소스에서 조직에서 사서함으로 가져온 데이터에 대한 통신을 검색할 수 있습니다. 통신 규정 준수에서 지원되는 커넥터의 전체 목록은 타사 데이터 [보관을 참조하세요.](archiving-third-party-data.md)

통신 준수 정책에 커넥터를 할당하려면 Microsoft 365 조직에 대해 타사 커넥터를 구성해야 합니다. 통신 **준수 정책** 마법사의 타사 원본 섹션에는 현재 구성된 타사 커넥터만 표시됩니다.
