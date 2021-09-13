---
title: Microsoft 365에 도메인 연결
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 도메인을 도메인에 연결하는 방법을 Microsoft 365.
ms.openlocfilehash: 377bb0444582f8efe15583fa522eceb9d675e474
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211272"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>커넥트 도메인을 비즈니스용 Microsoft 365 수 있도록 설정

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Google Workspace에서 전자 메일 Microsoft 365 설정하고 이동한 후 도메인을 도메인에 연결할 수 Microsoft 365. 

먼저 Google에서 기존 DNS 레코드를 삭제해야 합니다. 그런 다음 새 DNS 레코드를 Google에서 추가할 수 Microsoft 365.

## <a name="try-it"></a>사용해 보세요!

1. 에서 Google Workspace 관리 콘솔에 [admin.google.com.](https://admin.google.com)
1. 도메인, **도메인 관리,** **세부** 정보 **보기,** 도메인 관리, 왼쪽 nav에서 **DNS를** 선택합니다. 
1. 아래로 스크롤하여 **가상** 레코드, **Google Workspace를** 열고 **삭제를** 선택한 다음 다시 **삭제를** 선택합니다.
1. 아래로 스크롤하여 **사용자** 지정 리소스 레코드로 이동하여 이전에 사용자 지정 리소스 레코드에 대해 이전에 만들 수 있는 DNS 레코드를 포함하여 나타나는 기존 DNS 레코드를 Microsoft 365.
1. 으로 [이동하여 Microsoft 365 관리 센터.](https://admin.microsoft.com)
1. 왼쪽 네비게이트에서 모든 도메인 표시를  >    >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**설정.**</a>
1. 그런 다음 기본 도메인을 선택 합니다.
1. 설치 **계속 을** 선택한 다음 도메인을 연결하려면 계속을 **선택합니다.**
1. 아래로 스크롤하여 Google에 복사해야 하는 DNS 레코드를 시청합니다.
1. **MX 레코드를** 열고 주소 또는 값 **에서** 레코드를 복사합니다.
1. Google로 돌아가 사용자 지정 **리소스** 레코드 섹션에서 레코드 유형 드롭다운을 열고 **MX 를 선택합니다.**
1. 데이터 **필드에** 복사한 레코드를 붙여 넣습니다.
1. 그런 다음 **추가** 를 선택합니다.
1. CNAME 및 TXT 레코드에 대한 프로세스를 반복하고 Google DNS 관리 페이지에 값을 추가합니다.
1. 를 Microsoft 365 관리 센터 계속을 **선택합니다.**

    도메인 설정이 완료되었습니다.