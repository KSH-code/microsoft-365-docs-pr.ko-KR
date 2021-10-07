---
title: Google Workspace에서 비즈니스 전자 메일 및 일정 마이그레이션
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
description: Google Workspace에서 비즈니스용 전자 메일, 연락처 및 일정을 비즈니스용 Microsoft 365 방법을 학습합니다.
ms.openlocfilehash: a5ceccfde47b5084326aae9346b1c645cef7114a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163758"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Google Workspace에서 비즈니스 전자 메일 및 일정 마이그레이션

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

관리자가 실행한 마이그레이션을 사용하여 Google Workspace에서 Exchange Online 수 있습니다. 메일을 한 번만 마이그레이션하거나 단계적으로 마이그레이션할 수 있습니다. 다음 단계에서는 전자 메일 데이터를 한 번 마이그레이션하는 방법을 보여 제공합니다. 자세한 내용은 [Perform a G Suite migration을 참조하십시오.](/exchange/mailbox-migration/perform-g-suite-migration)

마이그레이션 프로세스는 마이그레이션하는 데이터의 양에 따라 몇 시간에서 며칠까지 걸릴 수 있습니다.

## <a name="try-it"></a>사용해 보세요!

### <a name="create-a-google-service-account"></a>Google 서비스 계정 만들기

1. Chrome 브라우저를 사용하여 에서 Google Workspace 관리 콘솔에 [admin.google.com.](https://admin.google.com) 
1. 새 탭 또는 창에서 서비스 계정 [페이지로](https://console.developers.google.com/iam-admin/serviceaccounts) 이동합니다. 
1. 프로젝트 **만들기를 선택하고** 프로젝트 이름을 지정한 다음 만들기 를 **선택합니다.** 
1. 서비스 **계정 만들기를 선택하고** 이름을 입력하고 **만들기,** 완료를 **선택합니다.** 
1. 작업 **메뉴를** 열고 편집 **을** 선택한 다음 고유 ID를 메모합니다. 프로세스 후반부에 이 ID가 필요합니다. 
1. 도메인 전체 **위임 표시 섹션을 여십시오.** 
1. G Suite 도메인 전체 위임 사용 **을** 선택하고 동의 화면의 제품 이름을 입력하고 저장 을 **선택합니다.** 

    > [!NOTE]
    > 제품 이름은 마이그레이션 프로세스에서 사용되지 않지만 대화 상자에 저장하는 데 필요합니다.     

1. 작업 **메뉴를** 다시 열고 **키 만들기 를 선택합니다.** 
1. **JSON을 선택한** 다음 를 **생성합니다.** 

     개인 키는 장치의 다운로드 폴더에 저장됩니다.
 
1. **닫기** 를 선택합니다. 

### <a name="enable-api-usage-for-the-project"></a>프로젝트에 대한 API 사용 사용

1. API [페이지로 이동합니다.](https://console.developers.google.com/apis/library) 
1. 검색 표시줄에 **Gmail API 를 입력합니다.**
1. 를 선택한 다음 사용 을 **선택합니다.**
1. Google 캘린더 API, 사용자 API 및 연락처 API에 대해 이 프로세스를 반복합니다. 

### <a name="grant-access-to-the-service-account"></a>서비스 계정에 대한 액세스 권한 부여

1. Google Workspace 관리 콘솔로 돌아오기. 
1. **보안,** 아래로 스크롤 및 API 컨트롤 **열기 를 선택합니다.** 
1. 아래로 스크롤하여 도메인 전체 위임 **관리를 선택합니다.**
1. 새 **추가를** 선택하고 앞에서 메모한 클라이언트 ID를 입력합니다.
1. 그런 다음 Google API에 대한 OAuth 범위를 입력합니다. 이러한 단계는 5단계에서 [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) 사용할 수 있으며 다음을 제공합니다.

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. 승인 **을 선택하세요.** 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>메일로 전송되는 메일에 대한 하위 도메인을 Microsoft 365

1. **Google Workspace** 관리 콘솔로 돌아오기.
1. 도메인, **도메인 관리,** 도메인 **별칭 추가를 선택합니다.**  
1. 같은 도메인 별칭을 `m365.contoso.com` 입력합니다.
1. 그런 다음 **계속을 선택하고 도메인 소유권 확인을 선택합니다.** 

    도메인 확인은 일반적으로 몇 분 정도 걸리지만 최대 48시간이 걸릴 수 있습니다.

1. 으로 [이동하여 Microsoft 365 관리 센터.](https://admin.microsoft.com)
1. 이 Microsoft 365 관리 센터 왼쪽 nav에서 모든 설정 도메인 표시를 선택한 다음 도메인 추가를  >    >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> **선택합니다.** 
1. 이전에 만든 하위 도메인을 입력한 다음 이 도메인 **사용을 선택합니다.** 
1. 도메인을 연결하려면 계속을 **선택합니다.** 
1. 아래로 스크롤하여 MX 레코드, CNAME 레코드 및 TXT 레코드를 기록합니다. 
1. Google 관리 **콘솔로 돌아오기**
1. 도메인을 **선택하고** **도메인 관리,** 세부 정보 **확인을** 선택한 다음 도메인 **관리를 선택합니다.** 
1. 왼쪽 nav에서 **DNS를** 선택하고 아래로 스크롤하여 사용자 지정 **리소스 레코드 를 스크롤합니다.** 
1. 레코드 유형 드롭다운을 열고 **MX를** 선택하고 이전에 언급한 MX 레코드 정보를 입력하거나 복사하여 붙여넣은 다음 추가 를 **선택합니다.** 
1. CNAME 레코드 및 TXT 레코드에 대한 프로세스를 반복합니다. 

    이러한 변경 내용을 적용하는 데 다소 시간이 걸릴 수 있습니다.  

1. 에서 벗어났다가 Microsoft 365 관리 센터 계속을 **선택합니다.** 

이제 도메인이 설정됩니다.  

### <a name="create-email-aliases-in-microsoft-365"></a>전자 메일 별칭을 Microsoft 365

마이그레이션을 시작하기 전에 새 하위omain을 사용하여 사용자에 대한 전자 메일 별칭을 만들어야 합니다. 

1. 다음 단계를 시작하려면 에서 도메인 추가 마법사에서 Microsoft 365 관리 센터 활성 사용자로 **이동을 선택합니다.**  
1. 사용자를 선택한 다음 사용자 이름 **및 전자 메일 관리 를 선택합니다.** 
1. 도메인 **드롭다운에서** 이전에 만든 하위 도메인을 선택합니다. 
1. 사용자 이름을 입력하고 **추가,** **변경** 내용 저장을 선택한 다음 창을 닫습니다. 

    각 사용자에 대해 이 프로세스를 반복합니다. 

### <a name="start-the-migration-process"></a>마이그레이션 프로세스 시작

완료되면 마이그레이션할 준비가 된 것입니다. 

1. In the left nav of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>, scroll down to **Admin centers**, and **select Exchange.** 
1. 받는 **사람 에서** 마이그레이션 **을 선택하고** 새로 추가, 마이그레이션으로 Exchange Online 를 선택하고 G Suite  **마이그레이션을** 선택한 후 다음 을 **선택합니다.**  
1. 마이그레이션할 사서함 목록이 있는 CSV 파일을 만들 수 있습니다. 파일이 다음 형식을 따르는지 확인 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      자세한 내용은 을 [aka.ms/GoogleWorkspaceMigration.](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac) 

1. Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**. 
1. 테스트에 사용할 관리자 전자 메일 주소를 검증합니다. 
1. 파일 **선택을** 선택하고, 앞에서 만든 JSON 파일(일반적으로 컴퓨터의 다운로드 폴더)으로 이동하고, 파일을 선택하고, **열기,** 다음을 **선택합니다.** 
1. 새 마이그레이션 일괄 처리 이름 필드에 이름을 **입력합니다.**
1. 대상 배달 도메인 필드에 만든 하위 도메인을 **입력하고** **다음,** 새로 고치기 **를 선택합니다.** 
1. 정보가 저장되고 나면 확인 을 **선택합니다.** 

    이제 마이그레이션 상태를 볼 수 있습니다. 

1. 마이그레이션하는 사용자의 수에 따라 시간이 지나면 새로 고침 을 **선택합니다.** 
1. 상태가 동기화로 변경된 후 이 마이그레이션 일괄 처리 완료 **,예** 를 **선택합니다.** 
1. 프로세스가 완료되면 상태가 **완료로 변경됩니다.** 
1. 원하는 경우 **세부** 정보 보기를 선택하여 마이그레이션에 대한 자세한 내용을 볼 수 있습니다. 
1. **닫기** 를 선택합니다. 
1. 웹 Outlook 열어 Google Workspace의 모든 전자 메일이 성공적으로 마이그레이션되어 있는지 확인할 수 있습니다.
일정 항목 및 연락처에 대해 이 작업을 반복할 수 있습니다.
