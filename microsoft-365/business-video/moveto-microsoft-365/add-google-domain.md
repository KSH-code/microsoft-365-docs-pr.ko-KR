---
title: Google Workspace 도메인 추가
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Google Workspace에서 비즈니스용 Microsoft 365로 도메인을 이동하는 방법을 배워야 합니다.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794750"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Microsoft 365에 Google Workspace 도메인 추가

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

비즈니스 전자 메일 주소를 계속 사용할 수 있도록 비즈니스용 Microsoft 365에 Google Workspace 도메인을 추가합니다.

## <a name="try-it"></a>사용해 보세요!

1. [Microsoft 365 관리 센터로 이동하세요.](https://admin.microsoft.com)
1. Microsoft 365 관리 센터의 왼쪽 nav에서 모두  **표시,** 설정 및 **도메인을 선택합니다.**
1. Choose **Add domain**, enter your domain name then select Use this **domain**. 
1. Choose, **Add a TXT record to the domains DNS records,** select **Continue,** and copy the TXT value. 
1. Go back to the [Google Admin Console,](https://admin.google.com)choose **Domains,** **Manage domains,** **View Details, Manage** **domain**, **DNS,** and then scroll down to **Custom resource records.** 
1. 레코드 종류 드롭다운을 열고 **TXT를** 선택한 다음 복사한 TXT 값을 붙여 넣은 다음 추가를 **선택합니다.** 

    업데이트는 일반적으로 몇 분 이내에 팩트에 걸리지만 최대 48시간이 걸릴 수 있습니다. 
1. Microsoft 365 관리 센터로 돌아가서 확인을 선택한 다음 **닫습니다.** 
1. 도메인을 사용자의 기본 전자 메일로 설정하려면 왼쪽 nav에서 사용자 활성 **사용자를**  >  **선택합니다.** 
1. 사용자를 선택하고 사용자 이름 **및** 전자 메일 관리, **편집,** 드롭다운에서 도메인 선택, 완료 **및** 변경 내용 **저장을 선택합니다.** 
1. 각 사용자에 대해 이 프로세스를 반복합니다. 

    완료되면 Office 앱을 설치하고 전자 메일 및 일정 항목을 Microsoft 365로 마이그레이션할 수 있습니다. 