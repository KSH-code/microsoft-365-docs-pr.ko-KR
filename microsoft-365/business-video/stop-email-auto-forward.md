---
title: 전자 메일 자동 전달 중지
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- AdminTemplateSet
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 소유 정보 도용을 방지하기 위한 메일 흐름 규칙을 만들어 자동 전달 전자 메일을 중지하는 방법을 학습합니다.
ms.openlocfilehash: 5c13e43f29b6d49b13daf4eb0aa6e3d6fd8275ae
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188787"
---
# <a name="stop-email-auto-forward"></a>전자 메일 자동 전달 중지

## <a name="watch-stop-auto-forwarding-emails"></a>감시: 전자 메일 자동 전달 중지

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

해커가 사용자의 사서함에 액세스할 수 있는 경우 사용자의 전자 메일을 외부 주소로 자동 전달하고 소유 정보를 도용할 수 있습니다. 메일 흐름 규칙을 만들어 이를 중지할 수 있습니다.

## <a name="try-it"></a>사용해 보세요!

1. 에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>, **메일** Exchange 를 선택하고 규칙 탭에서 더하기 기호를 선택하고 새 규칙 만들기 **를 선택합니다.**  
1. 추가 **옵션 을 선택합니다.** 새 규칙의 이름을 지정합니다.
1. 그런 다음 이 규칙을 적용하기 위한 드롭다운을 **열고** 보낸 사람 **을** 선택한 다음 외부 내부 **입니다.**
1. 조직 **내부 를 선택한** 다음 확인 **을 선택합니다.**
1. 조건 **추가를 선택하고** 드롭다운을 열고 메시지 속성 **을 선택한** 다음 메시지 유형 **을 포함합니다.**
1. 메시지 유형 **선택 드롭다운을** 열고 자동 **전달,** 확인을 **선택합니다.**
1. 다음 **작업을 합니다.** 드롭다운을 열고 메시지 **차단을** 선택한 다음 메시지를 **거부하고 설명을 포함합니다.**
1. 설명에 대한 메시지 텍스트를 입력한 다음 확인 을 **선택합니다.**
1. 아래쪽으로 스크롤하고 저장 을 **선택합니다.**

    규칙이 만들어지며 해커는 더 이상 메시지를 자동 전달할 수 없습니다.

## <a name="related-content"></a>관련 콘텐츠

[사용자의 다른 전자 메일 별칭 추가](../admin/email/add-another-email-alias-for-a-user.md)(문서)\
[Microsoft 365에서 전자 메일 전달 구성](../admin/email/configure-email-forwarding.md)(문서)\
[비즈니스 관리자를 위한 전자](/exchange/troubleshoot/email-delivery/email-delivery-issues) 메일 Office 365 문제 찾기 및 해결(문서)