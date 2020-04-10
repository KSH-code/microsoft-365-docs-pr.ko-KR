---
title: Office 365 ATP에 대 한 안전한 링크, safelinks, 안전한 링크, 악성 링크 차단, office 365 ATP, 팀 세이프 링크, 사용자가 잘못 된 링크를 클릭 하지 못하도록 함, 악성 링크
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 이제 팀이 클릭 시에 안전한 링크에 액세스할 수 있습니다. Office 365 ATP에 대 한 구독을 갖고 있는 경우에는 채팅 1-설정 채팅, 그룹 간 또는 채널에서 탭을 사용 하는 경우에 관계 없이이 보안 기능을 사용 하도록 설정 하 고 사용할 수 있습니다.
ms.openlocfilehash: 49a49bd41e71daf0afc9e7a24e79898ff98ad798
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212548"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a>팀의 Office 365 안전한 링크

> [!IMPORTANT]
> 이 기능은 Microsoft 팀 기술 채택 프로그램의 고객을 위한 **공개 미리 보기** , 2020 년 2 월 28 일 (탭핑)에 있습니다. 이 메모는 팀에 대 한 안전한 링크를 보다 광범위 하 게 사용할 수 있는 경우 문서에서 제거 됩니다.

Microsoft 팀에서 작업을 관리 하기 위한 Office 365 클라우드 기반 응용 프로그램은 이미 Office 365의 안전한 첨부 파일을 사용 하지만, 이제 클릭 시에 안전한 링크에 액세스할 수 있게 됩니다. Office 365 ATP에 대 한 구독을 갖고 있는 경우에는 채팅 1-1 채팅, 그룹 간 또는 채널에서 탭을 사용 하 고 있는지 여부에 상관 없이이 안전 측정값을 사용 하도록 설정 하 고 사용할 수 있습니다.

작동 방식은 다음과 같습니다. 

1. 팀 응용 프로그램을 시작 하면 Office 365에서 사용자가 Office 365 ATP가 있는 조직에 속하고, 사용자가 Microsoft 팀에 대 한 보호를 사용 하는 활성 안전한 링크 정책의 일부 인지 확인 합니다.

2. 위의 사항에 해당 하는 경우에는 채팅, 그룹 채팅, 채널 및 해당 사용자에 대 한 탭에서을 클릭 했을 때 Url의 유효성이 검사 됩니다.

> [!NOTE]
> 안전한 링크는 게스트 사용자, 페더레이션 사용자, 테 넌 트 사용자가 보낸 링크의 사용자를 보호 합니다. 로그인 한 사용자가 팀에 대 한 안전한 링크를 사용 하는 경우 안전한 링크 보호가 적용 됩니다.
 
## <a name="what-will-users-experience"></a>사용자에 게 어떤 문제가 있나요? 

모든 보호 된 사용자는 위험한 Url에서 다음과 같은 환경을 갖게 됩니다. 

- 팀 대화, 그룹 채팅 또는 채널에서 링크를 클릭 한 경우 페이지가 기본 브라우저에 렌더링 됩니다. 고정 된 탭에서 링크를 클릭 하면 해당 탭 내의 팀 GUI에 페이지가 표시 되 고 보안을 위해 브라우저에서 여는 옵션이 사용 하지 않도록 설정 됩니다.

- 이 사용자는 URL의 사이트를 계속 사용할 수 없도록 차단 됩니다.

링크를 보낸 사용자가 Office 365 ATP에 의해 보호 되지 않는 경우에는 자신의 컴퓨터에서 URL을 클릭 하 여 문제가 있는 사이트를 확인할 수 있습니다. 따라서 Office 365 관리자는 보호 된 사용자의 사용 가능 여부를 확실히 알 수 있습니다.

![악성 링크를 보고 하 고 페이지로의 통과를 차단 하는 팀 페이지에 대 한 안전한 링크입니다.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

팀에서이 페이지의 *뒤로 이동* 단추를 클릭 하면 종료 됩니다 (또는 빈 페이지 사용자가 종료 될 수 있음). 그러나 링크를 다시 클릭 하면 해당 사이트의 신뢰도가 reassessment이 페이지도 나타납니다.

> [!NOTE]
>일부 Office 365 관리자는 차단 페이지의 **계속 해 서** 메시지를 사용 하도록 설정 합니다. 그러나 안전한 링크를 통해 사이트의 신뢰도를 측정 하 여 찾은 경우 더 이상 클릭 하지 않아야 합니다. 사용자가 안전 조치를 우회 하지 않는 것이 좋습니다. 계속을 사용 하도록 설정 하기 전에 다음 사항을 고려 하십시오. 

