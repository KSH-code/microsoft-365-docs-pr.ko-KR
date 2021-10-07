---
title: 랜섬웨어에 대한 전자 메일 규칙 만들기
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 랜섬웨어를 방지하기 위한 전자 메일 규칙을 만드는 방법을 배워야 합니다.
ms.openlocfilehash: f76d9883ef2d22803867da267f48760ec8894f99
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172746"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>랜섬웨어를 방지하기 위한 전자 메일 규칙 만들기

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 JavaScript, 배치 및 실행 파일과 같은 잠재적으로 위험한 파일이 랜섬웨어로부터 비즈니스를 열지 못하게 하여 비즈니스를 Outlook. 추가 파일 형식을 차단하거나 경고하는 규칙을 추가하여 이 보호 수준을 높이기 위해 다음 단계를 수행합니다.

## <a name="try-it"></a>사용해 보세요!

1. 의 관리 센터에서 [https://admin.microsoft.com](https://admin.microsoft.com) 관리 **Exchange** **를 선택하세요.**
1. 왼쪽 메뉴에서 메일 흐름 **을 선택합니다.**
1. 규칙 탭에서 더하기 기호(+) 옆의 화살표를 선택한 다음 새 규칙 만들기 **를 선택합니다.**
1. 새 **규칙 페이지에서** 규칙의 이름을 입력하고 아래쪽으로 스크롤한 다음 추가 옵션을 **선택합니다.**
1. 다음의 **경우 이 규칙 적용에서** **첨부 파일 을** 선택한 다음 다음 단어를 포함하는 파일 **확장명을 선택합니다.**
1. 단어 또는 구 지정 아래 상자에 규칙을 적용할 파일 확장명(예: 매크로를 포함할 수 있는 파일 확장명)을 입력합니다. 더하기(+) 기호를 사용하여 한 번씩 추가합니다.

    랜섬웨어로부터 보호를 읽어 파일 형식에 대해 자세히 [알아보십시오.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)

1. 아래로 스크롤하여 목록을 검토한 다음 확인 을 **선택합니다.**
1. 새 **규칙 페이지에서** 조건 추가 **를** 선택한 다음 다음으로 이동에서 **조건을 선택합니다.**
1. 선택할 수 있는 규칙 옵션이 많지만 이 예에서는 메시지를 받는 사람에게 **알리도록 선택합니다.**
1. 알림에 대한 메시지 텍스트를 입력하고 확인 을 **선택 합니다.**
1. 선택 사항: 새 규칙  **페이지에서** 예외 추가를 선택하고 신뢰할 수 있는 보낸 사람이 보낸 메시지 등 규칙에 대한 예외에 대한 세부 정보를 입력합니다.
1. 새 규칙 페이지에서 저장 **을** 선택하고 제공된 규칙 요약 정보를 검토합니다.