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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 도메인을 Microsoft 365에 연결하는 방법을 학습합니다.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794705"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>비즈니스용 Microsoft 365에 도메인 연결

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Microsoft 365를 설정하고 Google Workspace에서 전자 메일 데이터를 이동한 후 도메인을 Microsoft 365에 연결할 수 있습니다. 

먼저 Google에서 기존 DNS 레코드를 삭제해야 합니다. 그런 다음 Microsoft 365에서 새 DNS 레코드를 추가할 수 있습니다.

## <a name="try-it"></a>사용해 보세요!

1. 로그인하여 Google Workspace 관리 [콘솔의](https://admin.google.com)admin.google.com.
1. Select **Domains,** **Manage domains,** **View details,** Manage **domain,** then **DNS** in the left nav.
1. 아래로 스크롤하여 **가상** 레코드, **Google Workspace 열기,** **삭제** 선택, 다시 **삭제를** 선택합니다.
1. 아래로 스크롤하여 **사용자** 지정 리소스 레코드로 스크롤하고 이전에 Microsoft 365에 대해 만든 DNS 레코드를 포함하여 나타나는 기존 DNS 레코드를 삭제합니다.
1. [Microsoft 365 관리 센터로 이동하세요.](https://admin.microsoft.com)
1. In the left nav, choose, **Show all**, **Settings**, **Domains.**
1. 그런 다음 기본 도메인을 선택 합니다.
1. 설치 **계속을** 선택하고 도메인을 연결하려면 계속을 **선택합니다.**
1. 아래로 스크롤하여 Google에 복사해야 하는 DNS 레코드를 시청합니다.
1. **MX 레코드를** 열고 주소 또는 **값의 지점에서** 레코드를 복사합니다.
1. Google로 돌아가 사용자 지정 **리소스** 레코드 섹션에서 레코드 형식 드롭다운을 열고 **MX를 선택합니다.**
1. 데이터 **필드에** 복사한 레코드를 붙여 넣습니다.
1. 그런 다음 **추가** 를 선택합니다.
1. CNAME 및 TXT 레코드에 대한 프로세스를 반복하고 Google DNS 관리 페이지에 값을 추가합니다.
1. Microsoft 365 관리 센터로 돌아가서 계속을 **선택합니다.**

    도메인 설정이 완료되었습니다.