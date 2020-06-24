---
title: 이전 직원 제거
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: '다음 검사 목록을 따라 Microsoft 365에서 직원을 제거 하 고 데이터를 보호 합니다. '
ms.openlocfilehash: 51fd26835cd74fa8403437397d37395fcf1c7301
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844861"
---
# <a name="remove-a-former-employee"></a>이전 직원 제거

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end
  
## <a name="sign-out-now"></a>지금 로그아웃!

::: moniker range="o365-worldwide"

직원을 제거 하는 방법에 대 한 간단한 동영상을 시청 하세요. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

직원이 로그인 하지 못하도록 하려면 다음을 수행 합니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 사용자 이름 옆의 상자를 선택 하 고 **암호 다시 설정을**선택 합니다.

3. 새 암호를 입력 하 고 **재설정**을 선택 합니다. (여기로 보내지 않습니다.)
    
4. 사용자 이름을 선택 하 여 해당 속성 창으로 이동 하 고 **OneDrive** 탭에서 **로그 아웃 시작**을 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 사용자를 선택 하 고 **암호 다시 설정을**선택 합니다.

3. 새 암호를 입력 하 고 **재설정**을 선택 합니다. (여기로 보내지 않습니다.)

4. 사용자를 다시 선택 하 고 **OneDrive 설정을**확장 한 후 **로그 아웃**옆에 있는 **시작** 을 선택 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 사용자를 선택 하 고 **암호 다시 설정을**선택 합니다.

3. 새 암호를 입력 하 고 **재설정**을 선택 합니다. (여기로 보내지 않습니다.)

4. 사용자를 다시 선택 하 고 **OneDrive 설정을**확장 한 후 **로그 아웃**옆에 있는 **시작** 을 선택 합니다.

::: moniker-end

    
한 시간 이내에 또는 현재 Microsoft 365 페이지에서 나간 후에 다시 로그인 하 라는 메시지가 표시 됩니다. (액세스 토큰은 한 시간 동안 유효 하므로 타임 라인은 해당 토큰에 남은 시간과 현재 웹 페이지에서 벗어나 이동 하는지 여부에 따라 달라 집니다.)
  
 **주의 사항**: 사용자가 웹용 Outlook에 있는 경우 사서함 주위를 클릭하는 것만으로는 즉시 로그아웃되지 않을 수 있습니다. OneDrive와 같은 다른 타일을 선택 하거나 브라우저를 새로 고치면 로그 아웃이 시작 됩니다. 
  
PowerShell을 사용하여 사용자를 즉시 로그아웃하려면 [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) cmdlet을 참조하세요. 
  
전자 메일에서 다른 사람을 제거하는 데 걸리는 시간에 대한 자세한 내용은 [직원의 전자 메일 세션 종료에 대해 알아야 할 사항](#what-you-need-to-know-about-terminating-an-employees-email-session)을 참조하세요.
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>직원을 제거하고 데이터를 보호하기 위한 모든 단계의 개요
<a name="bkmk_now"> </a>

"직원이 퇴사하는 경우 데이터를 보호하려면 어떻게 해야 하나요?"라는 질문을 자주 받습니다. 이 문서에서는 Microsoft 365에 대 한 액세스를 차단 하는 방법과 데이터를 보호 하기 위해 수행 해야 하는 단계에 대해 설명 합니다.
  
> [!NOTE]
> 전역 관리자는 직원을 삭제 하 고, 전자 메일을 전달 하 고, 새로운 안내가 제공 되는 환경을 사용 하 여 OneDrive 콘텐츠로 수행할 작업을 선택할 수 있습니다. 자세한 내용은 [전역 관리자: 사용자 삭제](remove-former-employee.md)를 참조 하세요. 그러나 직원에 게 회사 데이터에 대 한 액세스 권한이 없는지 확인 하려면 여기에 나열 된 추가 단계를 모두 완료 하는 것이 좋습니다. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**단계** <br/> |**이렇게 하는 이유** <br/> |
|1. [이전 직원 사서함의 콘텐츠 저장](#save-the-contents-of-a-former-employees-mailbox) <br/> |해당 직원의 업무를 인수하는 사람에게 또는 소송이 발생하는 경우 유용합니다.  <br/> |
|2. [이전 직원의 전자 메일을 다른 직원에게 전달 또는 공유 사서함으로 변환](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [이전 직원의 모바일 장치 초기화 및 차단](#wipe-and-block-a-former-employees-mobile-device) <br/> |휴대폰 또는 태블릿에서 비즈니스 데이터를 제거합니다.  <br/> |
|4. [Microsoft 365 데이터에 대 한 이전 직원의 액세스 차단](#block-a-former-employees-access-to-microsoft-365-data)<br/> |이를 통해 사용자가 이전 Microsoft 365 사서함 및 데이터에 액세스 하지 못합니다.  <br/><br/> **팁**: 사용자의 액세스를 차단 해도 해당 라이선스에 대 한 비용을 지불 하 고 있습니다. 라이선스 비용 지불을 중지하려면 구독에서 라이선스를 삭제(5단계)해야 합니다.           |
|5. [직원의 OneDrive 콘텐츠 이동](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |사용자의 라이선스만 제거하고 계정을 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |회사에서 발급한 컴퓨터 대신 개인용 컴퓨터를 사용하여 OneDrive 및 SharePoint에서 파일을 다운로드하는 경우 저장한 파일을 지울 방법이 없습니다.  <br/><br/> 컴퓨터와 동기화된 모든 파일에 계속 액세스할 수 있습니다.  <br/> |
|6. [이전 직원의 Microsoft 365 라이선스 제거 및 삭제](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [이전 직원의 사용자 계정 삭제](#delete-a-former-employees-user-account)<br/> |이렇게 하면 관리 센터에서 계정이 제거 됩니다. 깔끔하게 정리됩니다.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>이전 직원 사서함의 콘텐츠 저장
<a name="bkmk_preserve"> </a>

이전 직원 사서함의 콘텐츠를 저장하는 방법은 다음과 같은 두 가지가 있습니다.
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    또는
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    사서함을 "비활성 사서함"으로 전환하면 관리자, 준수 관리자 또는 레코드 관리자가 Exchange Online의 원본 위치 eDiscovery 도구를 사용하여 콘텐츠에 액세스하고 콘텐츠를 검색할 수 있습니다.
    
    비활성 사서함은 전자 메일을 받을 수 없으며 조직의 공유 주소록 또는 기타 목록에 표시되지 않습니다.
    
    사서함에 보존을 적용 하는 방법에 대 한 자세한 내용은 [Exchange Online에서 비활성 사서함 관리](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)를 참조 하세요.
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>이전 직원의 전자 메일을 다른 직원에게 전달 또는 공유 사서함으로 변환
<a name="bkmk_forward"> </a>

이 단계에서는 이전 직원의 전자 메일 주소를 다른 직원에게 할당하거나 [사용자의 사서함을 공유 사서함](../email/convert-user-mailbox-to-shared-mailbox.md)으로 변환합니다. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- 전자 메일 전달을 설정한 경우 이제 이전 직원에게 전송되는  *새*  전자 메일만 현재 직원에게 전송됩니다. 
    
- 전자 메일을 전달하려면 이전 직원의 계정에 라이선스가 있어야 합니다.
    
 > [!IMPORTANT] 
 > 전자 메일 전달 또는 공유 사서함을 설정 하는 경우 끝에서 이전 직원의 계정을 삭제 하지 마세요. 전자 메일 전달 또는 공유 사서함의 기준 위치가 되는 기존 계정이 있어야 합니다. 

::: moniker range="o365-worldwide"  

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원의 이름을 선택 하 고 **메일** 탭을 선택 합니다.

3. **전자 메일 전달**에서 **전자 메일 전달 관리**를 선택 합니다.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. **저장**을 선택합니다. 
    
6. 이전 직원의 계정을 삭제하지 않습니다.
 
::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단 하려는 직원을 선택 하 고 **메일 설정을**확장 합니다.

3. **전자 메일 전달**옆에 있는 **편집**을 선택 합니다.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. **저장**을 선택합니다. 
    
6. 이전 직원의 계정을 삭제하지 않습니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단 하려는 직원을 선택 하 고 **메일 설정을**확장 합니다.

3. **전자 메일 전달**옆에 있는 **편집**을 선택 합니다.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. **저장**을 선택합니다. 
    
6. 이전 직원의 계정을 삭제하지 않습니다.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>이전 직원의 모바일 장치 초기화 및 차단
<a name="bkmk_mobile"> </a>

이전 직원이 조직 휴대폰을 보유했던 경우 해당 장치에서 모든 조직 데이터가 제거되고 해당 장치가 더 이상 Office 365에 연결될 수 없도록 Exchange 관리 센터를 사용하여 해당 장치를 초기화 및 차단할 수 있습니다.
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.

3. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다. 
    
4. 사용자를 선택 하 고 **모바일 장치**에서 **세부 정보 보기**를 선택 합니다. 
    
5. 모바일 장치 **세부 정보** 페이지의 **모바일**장치에서 모바일 장치를 선택 하 고 **데이터** ![ 지우기 장치 지우기를 선택한 ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) 다음 **차단을**선택 합니다. 
    
6. **저장**을 선택합니다. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Microsoft 365 데이터에 대 한 이전 직원의 액세스 차단
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > 계정 차단이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다. 사용자의 로그인 액세스를 즉시 방지 해야 하는 경우 [암호를 다시 설정한](reset-passwords.md) 다음 모든 장치에서 Microsoft 365 세션에서 로그 아웃 하는 일회성 이벤트를 시작 해야 합니다. [지금 로그아웃!](#sign-out-now)을 참조하세요.
 

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원의 이름을 선택 하 고 사용자 이름 아래에 **이 사용자 차단**에 대 한 기호를 선택 합니다.

3. **사용자가 로그인**하지 못하도록 차단을 선택한 다음 **저장**을 선택 합니다. 

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택한 다음 **로그인 차단을**선택 합니다.

3. **사용자가 로그인**하지 못하도록 차단을 선택한 다음 **저장**을 선택 합니다. 

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택한 다음 **로그인 차단을**선택 합니다.

3. **사용자가 로그인**하지 못하도록 차단을 선택한 다음 **저장**을 선택 합니다. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>전자 메일(Exchange Online)에 대한 이전 직원의 액세스 차단
<a name="bkmk_block_email"> </a>

Microsoft 365 구독의 일부로 전자 메일이 있는 경우 다음 단계를 수행 하 여 이전 직원이 전자 메일에 액세스 하지 못하도록 차단 하려면 Exchange 관리 센터에 로그인 해야 합니다.
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.
     
2. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다. 
    
3. 사용자를 두 번 클릭 하 고 **사서함 기능** 페이지로 이동 합니다. **모바일 장치**에서 **Exchange ActiveSync 사용 안 함** 및 **장치용 OWA 사용 안** 함을 **선택 하 고** 메시지가 표시 되 면 둘 다에 대해 응답 합니다. 
    
4. **전자 메일 연결**에서 메시지가 표시 되 면 **사용 안 함** 및 대답이 **예** 를 선택 합니다. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>이전 직원의 Microsoft 365 라이선스 제거 및 삭제
<a name="bkmk_remove"> </a>

누군가가 조직에서 나간 후에 라이선스 비용을 계속 지불 하지 않으려면 Microsoft 365 라이선스를 제거한 다음 구독에서 삭제 해야 합니다. 구독에서 라이선스를 삭제하지 않도록 선택하면 해당 라이선스를 다른 사용자에게 할당할 수 있습니다.
  
라이선스를 제거하면 해당 사용자의 모든 데이터가 30일간 보존됩니다. 데이터에 [액세스](get-access-to-and-back-up-a-former-user-s-data.md)하거나 해당 사용자가 복귀하면 계정을 [복원](restore-user.md)할 수 있습니다. 30 일 후에는 사용자의 모든 데이터 (SharePoint Online에 저장 된 문서를 제외)가 Microsoft 365에서 영구적으로 삭제 되며 복구할 수 없습니다. 

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원의 이름을 선택 하 고 **라이선스 및 앱** 탭을 선택 합니다.

4. 제거할 라이선스에 대 한 확인란의 선택을 취소 한 다음 **변경 내용 저장**을 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택 하 고 **제품 라이선스**옆에 있는 **편집**을 선택 합니다.

3. **제품 라이선스** 페이지에서 제거 하려는 라이선스를 설정/해제 하 고 **저장**을 선택 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택 하 고 **제품 라이선스**옆에 있는 **편집**을 선택 합니다.

3. **제품 라이선스** 페이지에서 제거 하려는 라이선스를 설정/해제 하 고 **저장**을 선택 합니다.

::: moniker-end


다른 사람을 고용할 때까지 **비용을 지불하는 라이선스 수를 줄이려면** 다음을 수행합니다. 

::: moniker range="o365-worldwide"



1. 관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요.


::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.

::: moniker-end
    
2. 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이센스 비용을 지불 하지 않을 수 있습니다.

비즈니스에 다른 사람을 [추가](add-users.md) 하면 동시에 라이선스를 구입 하 라는 메시지가 표시 되며 한 단계만 진행 됩니다.
    
비즈니스용 Microsoft 365에 대 한 사용자 라이선스를 관리 하는 방법에 대 한 자세한 내용은 microsoft 365의 사용자 [에 게 라이선스 할당](../manage/assign-licenses-to-users.md)및 [비즈니스용 microsoft 365의 사용자](../manage/remove-licenses-from-users.md)에 대 한 라이선스 제거를 참조 하세요.
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>삭제된 직원 계정이 비즈니스용 Skype에 영향을 미치는 방식
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>이전 직원의 사용자 계정 삭제
<a name="bkmk_delete"> </a>

이전 직원의 모든 사용자 데이터에 액세스하여 저장한 후에는 이전 직원의 계정을 삭제할 수 있습니다.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 삭제할 직원의 이름을 선택 합니다.

3. 사용자 이름 아래에서 **사용자 삭제**에 대 한 기호를 선택 합니다. 이 사용자에 대해 원하는 옵션을 선택 하 고 **사용자 삭제**를 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 삭제할 직원의 이름을 선택 합니다.

3. 페이지 맨 위에서 **사용자 삭제**를 선택 합니다. 이 사용자에 대해 원하는 옵션을 선택 하 고 **사용자 삭제**를 선택 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 삭제할 직원의 이름을 선택 합니다.

3. 페이지 맨 위에서 **사용자 삭제**를 선택 합니다. 이 사용자에 대해 원하는 옵션을 선택 하 고 **사용자 삭제**를 선택 합니다.

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>조직에서 Active Directory를 사용하나요?

조직에서 로컬 Active Directory 환경에서 사용자 계정을 Microsoft 365와 동기화 하는 경우 로컬 Active Directory 서비스에서 해당 사용자 계정을 삭제 하 고 복원 해야 합니다. Office 365에서는 해당 사용자 계정을 삭제하거나 복원할 수 없습니다.
  
자세한 내용은 [사용자 계정 삭제](https://go.microsoft.com/fwlink/?linkid=841808)문서를 참조 하십시오.
  
Azure Active Directory를 사용하는 경우 [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet을 참조하세요. 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>직원의 전자 메일 세션 종료에 대해 알아야 할 사항
<a name="bkmk_session"> </a>

다음은 전자 메일(Exchange)에서 직원을 제거하는 방법에 대한 정보입니다.
  
|||
|:-----|:-----|
|**실행할 수 있는 작업** <br/> |**방법** <br/> |
|세션(예: 웹용 Outlook, Outlook, Exchange Active Sync 등) 종료 및 새 세션 열기  <br/> |암호 재설정  <br/> |
|세션 종료 및 향후 세션에 대한 액세스 차단(모든 프로토콜에 대해)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|특정 프로토콜(예: ActiveSync)에 대한 세션 종료  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
위 작업은 다음 세 위치에서 수행할 수 있습니다.
  
|||
|:-----|:-----|
|**여기에서 세션을 종료하는 경우** <br/> |**소요 시간** <br/> |
|Exchange 관리 센터에서 또는 PowerShell을 사용하는 경우  <br/> |30분 이내의 지연이 예상됨  <br/> |
|Azure Active Directory 관리 센터에서  <br/> |60분의 지연이 예상됨  <br/> |
|온-프레미스 환경에서  <br/> |3시간 이상의 지연이 예상됨  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>계정 종료에 대해 가장 빠른 응답을 받는 방법

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>관련 문서

[사용자 복원](restore-user.md)
  
