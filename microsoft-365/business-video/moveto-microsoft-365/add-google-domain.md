---
title: Google Workspace 도메인 추가
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Google Workspace에서 비즈니스용 도메인으로 도메인을 Microsoft 365 방법을 배워야 합니다.
ms.openlocfilehash: b41fdf304d0f0b9680f87f40a4564573593d6e75
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204782"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Google Workspace 도메인을 추가하여 Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

비즈니스용 전자 메일 주소를 계속 Microsoft 365 수 있도록 비즈니스용 전자 메일에 Google Workspace 도메인을 추가합니다.

## <a name="try-it"></a>사용해 보세요!

1. 으로 [이동하여 Microsoft 365 관리 센터.](https://admin.microsoft.com)
1. 왼쪽 Microsoft 365 관리 센터 창에서 모든 설정   >    >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**도메인 표시를 선택합니다.**</a>
1. 도메인 **추가를** 선택하고 도메인 이름을 입력한 다음 이 **도메인 사용을 선택합니다.** 
1. **TXT** 레코드를 도메인 DNS 레코드에 추가를 선택하고 계속을 선택하고 TXT 값을 복사합니다. 
1. Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, View **Details**, **Manage domain**, **DNS**, and then scroll down to Custom **resource records**. 
1. 레코드 종류 드롭다운을 열고 **TXT를** 선택하고 복사한 TXT 값을 붙여 넣은 다음 추가 를 **선택합니다.** 

    일반적으로 업데이트는 몇 분 이내에 팩트가 사용되지만 최대 48시간이 걸릴 수 있습니다. 
1. 관리 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">센터로 돌아가서</a> **확인을** 선택한 다음 **닫습니다.** 
1. 도메인을 사용자의 기본 전자 메일로 설정하려면 왼쪽 nav에서 사용자 활성 **사용자를**  >  [**선택합니다.**](https://go.microsoft.com/fwlink/p/?linkid=834822) 
1. 사용자를 선택하고 사용자 이름 및 전자 **메일 관리,** **편집을** 선택하고 드롭다운에서 도메인을 선택한 다음 완료 **및** 변경 내용 **저장을 선택합니다.** 
1. 각 사용자에 대해 이 프로세스를 반복합니다. 

    완료되면 앱 앱을 설치하고 전자 메일 및 일정 Office 마이그레이션할 준비가 Microsoft 365. 