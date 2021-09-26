---
title: 4단계 - 다른 직원에게 데이터 및 OneDrive 액세스 Outlook 부여
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 이 문서의 단계에 따라 다른 직원에게 이전 직원의 회사 및 OneDrive 액세스 권한을 Outlook.
ms.openlocfilehash: 4a502646e41bd3f06f5f8412aac3929b8fbad210
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774210"
---
# <a name="step-4---give-another-employee-access-to-onedrive-and-outlook-data"></a>4단계 - 다른 직원에게 데이터 및 OneDrive 액세스 Outlook 부여

직원이 조직을 떠나는 경우 해당 OneDrive 및 Outlook 데이터를 백업하고 다른 직원에게 부여할지 여부를 선택할 수 있습니다.
  
## <a name="access-a-former-users-onedrive-documents"></a>이전 사용자의 OneDrive 액세스

사용자의 라이선스를 제거하지만 계정을 삭제하지 않는 경우 사용자 라이선스의 콘텐츠에 대한 액세스 권한을 직접 부여할 수 OneDrive. 사용자 계정을 삭제하는 경우 기본적으로 30일 동안 이전 사용자의 계정 데이터에 액세스할 OneDrive 있습니다. [삭제된 사용자에 대한 OneDrive 설정하는 방법을 학습합니다.](/onedrive/set-retention) 이 시간 내에 [사용자](/office365/admin/add-users/restore-user) 계정을 복원하지 않는 경우 해당 OneDrive 삭제됩니다.

이전 사용자의 OneDrive 파일을 보존하려면 먼저 해당 사용자 OneDrive 액세스 권한을 부여한 다음 유지하려는 파일을 이동하십시오.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..  

2. 사용자를 선택합니다.

3. 오른쪽 창에서 를 **OneDrive.** 파일에 **액세스하려면 아래에서** **파일에 대한 링크 만들기 를 선택합니다.**

4. 파일 위치를 열 링크를 선택합니다. 파일을 컴퓨터에 다운로드하거나 이동  또는 복사를 선택하여 파일을 자신의 컴퓨터 또는 공유 라이브러리로 OneDrive 복사합니다. 

> [!NOTE]
> 한에 최대 500MB의 파일 및 폴더를 이동하거나 복사할 수 있습니다.<br/>
> 버전 기록이 있는 문서를 이동하거나 복사하면 최신 버전만 이동됩니다.  

또한 다른 사용자에게 이전 직원의 사용자 액세스 권한을 부여할 수도 OneDrive.

1. 전역 관리자 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">또는</a> 관리자로 관리 센터에 SharePoint 로그인합니다.

    관리 센터에 액세스할 수 있는 권한이 없다고 메시지가 표시된 경우 조직에 관리자 권한이 없습니다.

2. 왼쪽 창에서 관리  센터 를 \> **SharePoint.** (관리 센터의 목록을 보려면 **모두 표시** 를 선택해야 할 수도 있습니다.)

3. 클래식 SharePoint 관리 센터가 나타나면 페이지  맨 위에 있는 지금 열기 를 선택하여 SharePoint 관리 센터를 열 수 있습니다.

4. 왼쪽 창에서 추가 기능 **을 선택합니다.**

5. 사용자 **프로필에서** **열기 를 선택합니다.**

6. 사용자 **아래에서** 사용자 **프로필 관리를 선택합니다.**

7. 이전 직원의 이름을 입력하고 찾기 를 **선택합니다.**

8. 사용자를 마우스 오른쪽 단추로 클릭한 다음 사이트 모음 **소유자 관리를 클릭합니다.**

9. 사용자를 사이트 모음 **관리자에게 추가하고** 확인 을 **선택합니다.**

10. 이제 사용자는 해당 URL을 사용하여 이전 직원의 OneDrive 액세스할 OneDrive 있습니다. 

### <a name="revoke-admin-access-to-a-users-onedrive"></a>사용자의 사용자 액세스에 대한 관리자 액세스 OneDrive

사용자 계정의 콘텐츠에 대한 액세스 권한을 직접 부여할 OneDrive 더 이상 필요하지 않을 때 액세스를 제거할 수 있습니다.

1. 전역 관리자 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">또는</a> 관리자로 관리 센터에 SharePoint 로그인합니다.

    관리 센터에 액세스할 수 있는 권한이 없다고 메시지가 표시된 경우 조직에 관리자 권한이 없습니다.

2. 왼쪽 창에서 관리  센터 를 \> **SharePoint.** (관리 센터의 목록을 보려면 **모두 표시** 를 선택해야 할 수도 있습니다.)

3. 클래식 SharePoint 관리 센터가 나타나면 페이지  맨 위에 있는 지금 열기 를 선택하여 SharePoint 관리 센터를 열 수 있습니다.

4. 왼쪽 창에서 추가 기능 **을 선택합니다.**

5. 사용자 **프로필에서** **열기 를 선택합니다.**

6. 사용자 **아래에서** 사용자 **프로필 관리를 선택합니다.**

7. 사용자의 이름을 입력하고 찾기 를 **선택합니다.**

8. 사용자를 마우스 오른쪽 단추로 클릭한 다음 사이트 모음 **소유자 관리를 클릭합니다.**

9. 더 이상 사용자 데이터에 액세스할 필요가 없는 사용자를 제거하고 확인 을 **선택합니다.**

## <a name="access-the-outlook-data-of-a-former-user"></a>이전 Outlook 데이터 액세스

이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처를 저장하기 위해 정보를 Outlook 파일(.pst)로 내보낼 수 있습니다.
  
1. [이전 직원의](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) 전자 메일을 Outlook(사용자의 암호를 다시 [](reset-passwords.md)설정하는 경우 알고 있는 것으로만 설정할 수 있습니다.)

2. In Outlook, select **File**.

    ![이 리본 메뉴의 모양은 Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Open **&amp; Export** \> **Import/Export.**

    ![Import/Export 보기에서 명령을 실행합니다.](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. 파일로 **내보내기 를 선택하고** 다음 을 **선택합니다.**

    ![가져오기 및 내보내기 마법사의 파일 옵션으로 내보내기](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. 데이터 **Outlook 파일(.pst)을** 선택하고 다음 을 **선택합니다.**

6. 사서함 - Anne Weiler 또는 전자 메일 주소와 같은 이름 또는 전자 메일 주소를 선택하여 내보낼 계정을 anne@contoso.com. 메일, 일정, 연락처, 작업 및 메모를 포함하여 계정의 모든 것을 내보내는 경우 하위폴더 포함 **확인란이** 선택되어 있는지 확인란을 선택합니다.

    > [!NOTE]
    > 한 번씩 하나의 계정을 내보낼 수 있습니다. 여러 계정을 내보내는 경우 한 계정을 내보낼 때 다음 단계를 반복합니다.
  
    ![상위 Outlook 선택한 다음 하위 폴더 포함을 선택한 다음 데이터 파일 대화 상자를 내보낼 수 있습니다.](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. **다음** 을 선택합니다.

8. **찾아보기를** 선택하여 데이터 파일(.pst)Outlook 선택합니다. 파일  *이름 을 입력한* 다음 **확인을** 선택하여 계속합니다.

    > [!NOTE]
    > 내보내기 전에 사용한 경우 이전 폴더 위치와 파일 이름이 표시됩니다. 확인을 *선택하기* 전에 다른 파일 이름을 **입력합니다.**
  
9. 기존 Outlook 데이터 파일(.pst)로 내보내는 경우 **옵션** 에서 파일에 이미 있는 항목을 내보낼 때 수행할 작업을 지정합니다.

10. **완료** 를 선택합니다.

Outlook 새 Outlook 파일(.pst)을 만들거나 암호로 보호된 파일을 사용하는 경우를 아니면 내보내기 즉시 시작됩니다.
  
- 데이터 파일(.pst)Outlook 만드는 경우 선택적 암호를 사용하면 파일을 보호할 수 있습니다. 데이터 Outlook 만들기 대화 **상자가** 나타나면 암호  및 암호 확인  상자에 암호를 입력한 다음 확인 을 **선택합니다.**  데이터 **Outlook 암호** 대화 상자에서 암호를 입력하고 확인 을 **선택합니다.** 

- 암호로 보호된 기존 Outlook 데이터 파일(.pst)으로 내보내는 경우 Outlook **데이터** 파일 암호 대화 상자에 암호를 입력하고 확인 을 **선택합니다.**

2010년 8월 2일부로 전자 메일, 연락처 및 일정을 [.pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) Outlook 내보내거나 백업하는 Outlook 참조하세요.

  > [!NOTE]
  > 기본적으로 전자 메일은 12개월 동안 오프라인으로 사용할 수 있습니다. 필요한 경우 오프라인에서 사용 가능한 데이터를 [늘리는 방법을 참조합니다.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)

### <a name="give-another-user-access-to-a-former-users-email"></a>다른 사용자에게 이전 사용자의 전자 메일에 대한 액세스 권한을 부여합니다.

이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처에 대한 액세스 권한을 다른 직원에게 제공하기 위해 정보를 다른 직원의 Outlook 받은 편지함으로 가져와야 합니다.

> [!NOTE]
> 이전 사용자의 [사서함을](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) 공유 사서함으로 변환하거나 이전 직원의 전자 메일을 다른 직원에게 전달할 [수도 있습니다.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)

1. In Outlook, go to **File** \> **Open Export &amp; Import/Export.** \> 

    그러면 가져오기 및 내보내기 마법사가 시작됩니다.

2. 다른 **프로그램 또는 파일에서 가져오기 를 선택하고** 다음 을 **선택합니다.**

    ![가져오기 및 내보내기 마법사.](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. 데이터 **Outlook 파일(.pst)을 선택하고** 다음 을 **선택합니다.**

4. 가져올 .pst 파일을 검색합니다.

5. 옵션 **아래에서** 중복 항목을 처리하려는 방법을 선택합니다.

6. **다음** 을 선택합니다.

7. Outlook 데이터 파일(.pst)에 암호를 할당한 경우 암호를 입력한 다음 확인 을 **선택합니다.**

8. 항목 가져오기 옵션을 설정할 수 있습니다. 기본 설정은 일반적으로 변경할 필요가 없습니다.

9. **완료** 를 선택합니다.

> [!NOTE]
> 이 단계는 기존 사용자의 데이터 및 전자 메일 데이터에 액세스하는 OneDrive 동일하게 유지됩니다.

> [!TIP]
> Outlook 데이터 파일(.pst)에서 몇 가지 항목만 가져오거나 복원하려는 경우 Outlook 열 수 있습니다. 그런 다음 탐색 창에서 데이터 파일 폴더의 Outlook 기존 폴더로 Outlook 끌어 놓습니다.

## <a name="related-content"></a>관련 콘텐츠

[계정에서 관리자](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) 추가 및 OneDrive(문서)

[삭제된 데이터 OneDrive](/onedrive/restore-deleted-onedrive) 복원(문서)

[OneDrive 및](/onedrive/retention-and-deletion) 삭제(문서)

[OneDrive 파일 및 폴더 공유](https://support.microsoft.com/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07)
