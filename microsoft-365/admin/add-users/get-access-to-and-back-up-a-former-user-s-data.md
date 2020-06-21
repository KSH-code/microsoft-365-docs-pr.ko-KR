---
title: 액세스 권한 받기 및 이전 사용자 데이터 백업
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: 사용자가 조직을 떠날 때 직원의 파일 및 전자 메일을 보존 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 32f64efb30acb5438e5add8bcb897200951e6362
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780616"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>액세스 권한 받기 및 이전 사용자 데이터 백업


직원이 조직을 떠나는 경우 해당 데이터 (문서 및 전자 메일)에 액세스 하 고, 검토 하거나, 새 직원에 게 제공 하는 것이 좋습니다.
  
    
## <a name="access-a-former-users-onedrive-documents"></a>이전 사용자의 OneDrive 문서 액세스

사용자의 라이선스를 제거 하지만 계정을 삭제 하지 않으면 사용자의 OneDrive에 있는 콘텐츠에 대 한 액세스 권한을 부여할 수 있습니다. 사용자 계정을 삭제 하면 기본적으로 30 일이 지나면 이전 사용자의 OneDrive 데이터에 액세스할 수 있습니다. [삭제 된 사용자에 대 한 OneDrive 보존을 설정 하는 방법을 알아봅니다](/onedrive/set-retention). 이 시간 내에 [사용자 계정을 복원](/office365/admin/add-users/restore-user) 하지 않으면 OneDrive 콘텐츠가 삭제 됩니다. 

이전 사용자의 OneDrive 파일을 보존 하려면 먼저 자신에 게 OneDrive에 대 한 액세스 권한을 부여 하 고 보관할 파일을 이동 합니다. 

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.  
    
2. 사용자를 선택 합니다.

3. 오른쪽 창에서 **OneDrive**를 선택 합니다. **파일에 대 한 액세스 권한**에서 **파일에 대 한 링크 만들기**를 선택 합니다.

4. 링크를 선택 하 여 파일 위치를 엽니다. 파일을 컴퓨터에 다운로드 하거나, **이동** 하거나 **복사** 를 선택 하 여 자신의 OneDrive 또는 공유 라이브러리로 이동 하거나 복사 합니다. 

> [!NOTE]
> 파일 및 폴더를 한 번에 최대 500 MB까지 이동 하거나 복사할 수 있습니다.<br/>
> 버전 기록이 포함 된 문서를 이동 하거나 복사 하는 경우 최신 버전만 이동 됩니다.  

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.  

2. 사용자를 선택 합니다.

3. 오른쪽 창에서 **OneDrive 설정을**확장 하 고 **액세스**옆에 있는 **파일 액세스**를 선택 합니다.

4. 링크를 선택 하 여 파일 위치를 엽니다. 파일을 컴퓨터에 다운로드 하거나, **이동** 하거나 **복사** 를 선택 하 여 자신의 OneDrive 또는 공유 라이브러리로 이동 하거나 복사 합니다. 

> [!NOTE]
> 파일 및 폴더를 한 번에 최대 500 MB까지 이동 하거나 복사할 수 있습니다.<br/>
> 버전 기록이 포함 된 문서를 이동 하거나 복사 하는 경우 최신 버전만 이동 됩니다.  

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다. 

2. 사용자를 선택 합니다.

3. 오른쪽 창에서 **OneDrive 설정을**확장 하 고 **액세스**옆에 있는 **파일 액세스**를 선택 합니다.

4. 링크를 선택 하 여 파일 위치를 엽니다. 파일을 컴퓨터에 다운로드 하거나, **이동** 하거나 **복사** 를 선택 하 여 자신의 OneDrive 또는 공유 라이브러리로 이동 하거나 복사 합니다.  

> [!NOTE]
> 파일 및 폴더를 한 번에 최대 500 MB까지 이동 하거나 복사할 수 있습니다.<br/>
> 버전 기록이 포함 된 문서를 이동 하거나 복사 하는 경우 최신 버전만 이동 됩니다.  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>사용자의 OneDrive에 대 한 관리자 액세스 권한 해지

전역 관리자는 자신에 게 사용자의 OneDrive에 있는 콘텐츠에 대 한 액세스 권한을 부여할 수 있지만 더 이상 필요 하지 않은 경우에는 액세스 권한을 제거 해야 할 수 있습니다. 

::: moniker range="o365-worldwide"

1. 전역 관리자 또는 SharePoint 관리자로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a> 에 로그인 합니다. 

    관리 센터에 액세스할 수 있는 권한이 없다는 메시지가 표시 되 면 조직에서 관리자 권한이 없는 것입니다.

::: moniker-end

::: moniker range="o365-germany"

1. 전역 관리자 또는 SharePoint 관리자로 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a> 에 로그인 합니다.

    관리 센터에 액세스할 수 있는 권한이 없다는 메시지가 표시 되 면 조직에서 관리자 권한이 없는 것입니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 전역 관리자 또는 SharePoint 관리자로 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a> 에 로그인 합니다.

    관리 센터에 액세스할 수 있는 권한이 없다는 메시지가 표시 되 면 조직에서 관리자 권한이 없는 것입니다.

::: moniker-end

2. 왼쪽 창에서 **관리 센터** \> **SharePoint**를 선택 합니다. (관리 센터의 목록을 보려면 **모두 표시**를 선택해야 할 수도 있습니다.)

3. 클래식 SharePoint 관리 센터가 나타나면 페이지 맨 위에 있는 **지금 열기** 를 선택 하 여 SharePoint 관리 센터를 엽니다.

4. 왼쪽 창에서 **추가 기능**을 선택 합니다.

5. **사용자 프로필**에서 **열기**를 선택 합니다.

6. **사람**에서 **사용자 프로필 관리**를 선택 합니다.

7. 사용자 이름을 입력 하 고 **찾기**를 선택 합니다.

8. 사용자를 마우스 오른쪽 단추로 클릭 한 다음 **사이트 모음 소유자 관리**를 선택 합니다.

9. 사용자 데이터에 더 이상 액세스할 필요가 없는 사용자를 제거 하 고 **확인**을 선택 합니다.

    
## <a name="access-the-outlook-data-of-a-former-user"></a>이전 사용자의 Outlook 데이터 액세스

이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처를 저장 하려면 해당 정보를 Outlook 데이터 파일 (.pst)로 내보냅니다.
  
1. Outlook에 [이전 직원의 전자 메일을 추가](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) 합니다 ( [사용자 암호를 다시 설정 하는](reset-passwords.md)경우에만 알고 있는 항목으로 설정할 수 있음).
    
2. Outlook에서 **파일**을 선택 합니다.
    
    ![리본 메뉴의 모양은 Outlook 2016에서 확인할 수 있습니다.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. ** &amp; 내보내기** \> **가져오기/내보내기**열기를 선택 합니다.
    
    ![Backstage 보기의 가져오기/내보내기 명령](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. **파일로 내보내기를**선택 하 고 **다음**을 선택 합니다.
    
    ![가져오기/내보내기 마법사에서 파일로 내보내기 옵션](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. **Outlook 데이터 파일 (.pst)** 을 선택 하 고 **다음**을 선택 합니다.
    
6. 이름 또는 전자 메일 주소 (예: 사서함-유가을 Weiler 또는 anne@contoso.com)를 선택 하 여 내보내려는 계정을 선택 합니다. 메일, 일정, 연락처, 작업 및 메모를 포함 하 여 계정의 모든 내용을 내보내려면 **하위 폴더 포함** 확인란이 선택 되어 있는지 확인 합니다. 
    
    > [!NOTE]
    > 한 번에 하나의 계정만 내보낼 수 있습니다. 여러 계정을 내보내려는 경우 하나의 계정을 내보낸 후에는 이러한 단계를 반복 합니다. 
  
    ![폴더를 선택 하 고 하위 폴더를 포함 하는 Outlook 데이터 파일 내보내기 대화 상자](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. **다음**을 선택합니다.
    
8. **찾아보기를** 선택 하 여 Outlook 데이터 파일 (.pst)을 저장할 위치를 선택 합니다. *파일 이름을*입력 한 다음 **확인** 을 선택 하 여 계속 합니다. 
    
    > [!NOTE]
    > 이전에 export를 사용한 적이 있는 경우에는 위의 폴더 위치와 파일 이름이 표시 됩니다. **확인**을 선택 하기 전에 *다른 파일 이름을* 입력 합니다. 
  
9. 기존 Outlook 데이터 파일(.pst)로 내보내는 경우 **옵션**에서 파일에 이미 있는 항목을 내보낼 때 수행할 작업을 지정합니다.
    
10. Select **Finish**.
    
새 Outlook 데이터 파일 (.pst)을 만들거나 암호로 보호 된 파일을 사용 하는 경우가 아니면 outlook이 즉시 내보내기를 시작 합니다.
  
   - Outlook 데이터 파일 (.pst)을 만드는 경우 선택적 암호를 통해 파일을 보호할 수 있습니다. **Outlook 데이터 파일 만들기** 대화 상자가 나타나면 암호 및 **암호 확인** 상자에 *암호* 를 입력 **하 고** **확인**을 선택 합니다. **Outlook 데이터 파일 암호** 대화 상자에서 *암호*를 입력 한 다음 **확인**을 선택 합니다.
    
  - 암호로 보호 되는 기존 Outlook 데이터 파일 (.pst)로 내보내는 경우 **Outlook 데이터 파일 암호** 대화 상자에 *암호*를 입력 하 고 **확인**을 선택 합니다.
    
Outlook 2010에서 [전자 메일, 연락처 및 일정을 outlook .pst 파일로 내보내거나 백업](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) 하는 방법을 참조 하세요. 
  
  
  > [!NOTE]
  > 기본적으로 12 개월 동안 전자 메일을 오프 라인으로 사용할 수 있습니다. 필요한 경우 [오프 라인에서 사용할 수 있는 데이터를 늘리는](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)방법을 참조 하세요.
 
## <a name="give-another-user-access-to-a-former-users-email"></a>다른 사용자에 게 이전 사용자의 전자 메일에 대 한 액세스 권한 부여 

다른 직원에 게 이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처에 대 한 액세스 권한을 부여 하려면 해당 정보를 다른 직원의 Outlook 받은 편지 함으로 가져옵니다.

> [!NOTE]
> 또한 [이전 사용자의 사서함을 공유 사서함으로 변환](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) 하거나 [이전 직원의 전자 메일을 다른 직원에 게 전달할](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)수 있습니다.

  
1. Outlook에서 **File** \> ** &amp; ** \> **가져오기/내보내기**내보내기 파일로 이동 합니다.
    
    그러면 가져오기 및 내보내기 마법사가 시작 됩니다.
    
2. **다른 프로그램 또는 파일에서 가져오기를**선택 하 고 **다음**을 선택 합니다.
    
    ![가져오기 및 내보내기 마법사](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. **Outlook 데이터 파일 (.pst)** 을 선택 하 고 **다음**을 선택 합니다.
    
4. 가져올 .pst 파일을 찾습니다.
    
5. **옵션**에서 중복 항목을 처리할 방법을 선택 합니다.
    
6. **다음**을 선택합니다.
    
7. 암호를 Outlook 데이터 파일 (.pst)에 할당 한 경우 암호를 입력 하 고 **확인**을 선택 합니다.
    
8. 항목 가져오기에 대 한 옵션을 설정 합니다. 기본 설정은 대개 변경할 필요가 없습니다.
    
9. Select **Finish**.

> [!NOTE]
> 이 단계는 기존 사용자의 OneDrive 및 전자 메일 데이터에 액세스 하는 경우에도 동일 하 게 유지 됩니다.
    
> [!TIP]
> Outlook 데이터 파일 (.pst)에서 항목을 몇 개 가져오거나 복원 하려는 경우 Outlook 데이터 파일을 열 수 있습니다. 그런 다음 탐색 창에서 Outlook 데이터 파일 폴더의 항목을 기존 Outlook 폴더로 끌어 놓습니다. 
  
  
## <a name="related-articles"></a>관련 문서
[Office 365에서 이전 직원 제거](remove-former-employee.md)

[OneDrive 계정에서 관리자 추가 및 제거](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[삭제 된 OneDrive 복원](/onedrive/restore-deleted-onedrive)
  
[OneDrive 보존 및 삭제](/onedrive/retention-and-deletion)
  
