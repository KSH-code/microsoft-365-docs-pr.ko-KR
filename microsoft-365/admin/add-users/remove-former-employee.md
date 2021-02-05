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
description: '다음 검사 목록을 따라 Microsoft 365에서 직원을 제거하고 데이터를 보호합니다. '
ms.openlocfilehash: a875a8b7620067cdae46fcae3bb7ef8ce7d148fa
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114060"
---
# <a name="remove-or-delete-a-former-employee"></a>이전 직원 제거 또는 삭제

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end
  
## <a name="sign-out-now"></a>지금 로그아웃!

::: moniker range="o365-worldwide"

직원 제거에 대한 짧은 비디오를 시청합니다. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스와 Microsoft 365를 처음 사용하는 사용자를 위한 전체 교육 시리즈](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

직원이 로그인하지 못하게 방지:

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 사용자 이름 옆의 상자를 선택한 다음 암호 **재설정을 선택합니다.**
3. 새 암호를 입력한 다음 재설정을 **선택합니다.** (전송하지 않습니다.)
4. 사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 로그인 **시작을 선택합니다.** 

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 사용자를 선택한 다음 암호 **재설정을 선택합니다.**

3. 새 암호를 입력한 다음 재설정을 **선택합니다.** (전송하지 않습니다.)

4. 사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 로그인 **시작을 선택합니다.** 

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 사용자를 선택한 다음 암호 **재설정을 선택합니다.**

3. 새 암호를 입력한 다음 재설정을 **선택합니다.** (전송하지 않습니다.)

4. 사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 로그인 **시작을 선택합니다.** 

::: moniker-end

> [!NOTE]
> 전역 관리자로 로그인을 시작해야 합니다.

1시간 이내에 또는 현재 Microsoft 365 페이지를 떠났다가 다시 로그인하라는 메시지가 표시됩니다. 액세스 토큰은 1시간 동안 사용할 수 있으므로 타임라인은 해당 토큰에 남은 시간 및 현재 웹 페이지를 탐색하는지 여부에 따라 결정됩니다.
  
> [!IMPORTANT]
> 사용자가 웹에서 Outlook에 있는 경우 사서함을 클릭하기만 하면 즉시 시작되지 않을 수 있습니다. OneDrive와 같은 다른 타일을 선택하거나 브라우저를 새로 고치면 즉시 로그인이 시작됩니다.
  
PowerShell을 사용하여 사용자를 즉시 로그아웃하려면 [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) cmdlet을 참조하세요.
  
전자 메일에서 다른 사람을 제거하는 데 걸리는 시간에 대한 자세한 내용은 [직원의 전자 메일 세션 종료에 대해 알아야 할 사항](#what-you-need-to-know-about-terminating-an-employees-email-session)을 참조하세요.
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>직원을 제거하고 데이터를 보호하기 위한 모든 단계의 개요

"직원이 퇴사하는 경우 데이터를 보호하려면 어떻게 해야 하나요?"라는 질문을 자주 받습니다. 이 문서에서는 Microsoft 365에 대한 액세스를 차단하는 방법과 데이터 보안을 위해 취해야 하는 단계에 대해 설명합니다.
  
> [!NOTE]
> 전역 관리자인 경우 직원을 삭제하고 전자 메일을 전달하고 새로운 안내 환경을 사용하여 OneDrive 콘텐츠로 할 작업을 선택할 수 있습니다. 자세한 내용은 [전역 관리자: 사용자 삭제를 참조하세요.](remove-former-employee.md) 그러나 직원이 회사 데이터에 액세스할 수 있도록 여기에 나열된 추가 단계를 모두 완료하는 것이 좋습니다. 
  
간략한 개요는 다음과 같습니다. 각 단계는 이 문서에 자세히 설명되어 있습니다.
  
|||
|:-----|:-----|
|**단계** <br/> |**이렇게 하는 이유** <br/> |
|1. [이전 직원 사서함의 콘텐츠 저장](#save-the-contents-of-a-former-employees-mailbox) <br/> |이 기능은 직원의 작업을 인계할 사람이나 소송이 있는 경우 유용합니다.  <br/> |
|2. [이전 직원의 전자 메일을 다른 직원에게 전달 또는 공유 사서함으로 변환](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |이렇게 하면 이전 직원의 전자 메일 주소를 활성 상태로 유지할 수 있습니다. 이전 직원의 주소로 여전히 전자 메일을 보내는 고객 또는 파트너가 있는 경우 업무를 인수하는 사람에게 전자 메일이 전달됩니다.  <br/> |
|3. [이전 직원의 모바일 장치 초기화 및 차단](#wipe-and-block-a-former-employees-mobile-device) <br/> |휴대폰 또는 태블릿에서 비즈니스 데이터를 제거합니다.  <br/> |
|4. [Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data) 데이터에 대한 이전 직원의 액세스 차단<br/> |사용자가 이전 Microsoft 365 사서함 및 데이터에 액세스할 수 없습니다.  <br/><br/> **팁:** 사용자의 액세스를 차단하는 경우 라이선스 비용은 계속 지불하게 됩니다. 요금 지불을 중지하려면 구독에서 라이선스를 삭제합니다(5단계).  |
|5. [직원의 OneDrive 콘텐츠 이동](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |사용자의 라이선스만 제거하고 계정을 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  <br/><br/> 계정을 삭제하기 전에 OneDrive의 콘텐츠를 액세스하기 쉬운 다른 위치로 이동해야 합니다. 직원의 계정을 삭제하면 해당 OneDrive의 콘텐츠는 **30** 일 동안 보관됩니다. 그러나 이 기간 동안 사용자의 계정을 복원하고 OneDrive 콘텐츠에 대한 액세스 권한을 얻을 수 있습니다. 사용자의 계정을 복원하는 경우에는 30일이 지난 후에도 OneDrive 콘텐츠에 계속 액세스할 수 있습니다.  <br/> |
|5a. 사용자가 개인용 컴퓨터를 사용하여 OneDrive 및 SharePoint에 액세스하는 경우 어떻게 해야 하나요?  <br/> |회사에서 발급한 컴퓨터 대신 개인용 컴퓨터를 사용하여 OneDrive 및 SharePoint에서 파일을 다운로드하는 경우 저장한 파일을 지울 방법이 없습니다.  <br/><br/> 컴퓨터와 동기화된 모든 파일에 계속 액세스할 수 있습니다.  <br/> |
|6. [이전 직원의 Microsoft 365 라이선스](#remove-and-delete-the-microsoft-365-license-from-a-former-employee) 제거 및 삭제<br/> |라이선스를 제거하면 다른 사람에게 해당 라이선스를 할당할 수 있습니다. 또는 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않도록 라이선스를 삭제할 수 있습니다.  <br/><br/> 라이선스를 제거하거나 삭제하면 사용자의 이전 전자 메일, 연락처 및 일정이 **30일** 간 보존된 후 영구적으로 삭제됩니다. 라이선스를 제거하거나 삭제하되 계정은 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  <br/> |
|7. [이전 직원의 사용자 계정 삭제](#delete-a-former-employees-user-account)<br/> |그러면 관리 센터에서 계정이 제거됩니다. 깔끔하게 정리됩니다.  <br/> |

## <a name="save-the-contents-of-a-former-employees-mailbox"></a>이전 직원 사서함의 콘텐츠 저장

이전 직원 사서함의 콘텐츠를 저장하는 방법은 다음과 같은 두 가지가 있습니다.
  
1. Outlook 2013 또는 2016 버전에 이전 직원의 전자 메일 주소를 추가한 다음 데이터를 .pst 파일로 내보냅니다. 필요에 따라 다른 전자 메일 계정으로 데이터를 가져올 수 있습니다. 이 작업을 수행하는 방법을 알아보려면 [이전 사용자의 데이터 액세스 및 백업](get-access-to-and-back-up-a-former-user-s-data.md)을 참조하세요.

    또는

2. 사용자 계정을 삭제하기 전에 사서함에 대해 소송 보존 또는 원본 위치 유지를 적용합니다. 이 옵션은 첫 번째 옵션보다 훨씬 더 복잡하지만, Enterprise 요금제에 보관 및 법적 보존이 포함되어 있고 소송 가능성이 있으며 기술적으로 강력한 IT 부서가 있는 경우 수행할 가치가 있습니다.

    사서함을 "비활성 사서함"으로 변환한 후 관리자, 준수 관리자 또는 레코드 관리자는 Exchange Online의 In-Place eDiscovery 도구를 사용하여 콘텐츠에 액세스하고 검색할 수 있습니다.

    비활성 사서함은 전자 메일을 받을 수 없으며 조직의 공유 주소록 또는 기타 목록에 표시되지 않습니다.

    사서함을 보류하는 방법에 대한 자세한 내용은 Exchange Online에서 비활성 [사서함 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)

## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>이전 직원의 전자 메일을 다른 직원에게 전달 또는 공유 사서함으로 변환

이 단계에서는 이전 직원의 전자 메일 주소를 다른 직원에게 할당하거나 [사용자의 사서함을 공유 사서함](../email/convert-user-mailbox-to-shared-mailbox.md)으로 변환합니다.
  
- **사서함이 50GB보다 작은 한** 라이선스 비용을 지불할 필요가 없으므로 공유 사서함을 만드는 것이 비용이 덜 드는 방법입니다. 50GB 이상이면 사서함에 라이선스를 할당해야 합니다.
- 사서함을 공유 사서함으로 변환한 경우 이전 전자 메일을 모두 사용할 수 있습니다. 이렇게 하면 공간을 많이 차지할 수 있습니다.
- 전자 메일 전달을 설정한 경우 이제 이전 직원에게 전송되는  *새*  전자 메일만 현재 직원에게 전송됩니다.

 > [!IMPORTANT]
 > 전자 메일 전달 또는 공유 사서함을 설정하는 경우 마지막에 이전 직원의 계정을 삭제하지 않습니다. 전자 메일 전달 또는 공유 사서함의 기준 위치가 되는 기존 계정이 있어야 합니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 차단할 직원의 이름을 선택한 다음 메일 **탭을** 선택합니다.
3. 전자 **메일 전달 아래에서** 전자 메일 전달 **관리를 선택합니다.**
4. **이 사서함으로 전송된 모든 전자 메일을 전달** 을 켭니다. 전달 **주소 상자에** 전자 메일을 받을 현재 직원의 전자 메일 주소를 입력합니다.
5. **저장** 을 선택합니다.
6. 이전 직원의 계정을 삭제하지 않습니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 메일 설정을 차단하고 확장할 **직원을 선택합니다.**

3. 전자 메일 **전달 옆에서** 편집을 **선택합니다.**

4. **이 사서함으로 전송된 모든 전자 메일을 전달** 을 켭니다. **전달 주소** 상자에 전자 메일을 받게 될 현재 직원(또는 공유 사서함)의 전자 메일 주소를 입력합니다.
  
5. **저장** 을 선택합니다.

6. 이전 직원의 계정을 삭제하지 않습니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 메일 설정을 차단하고 확장할 **직원을 선택합니다.**

3. 전자 메일 **전달 옆에서** 편집을 **선택합니다.**

4. **이 사서함으로 전송된 모든 전자 메일을 전달** 을 켭니다. **전달 주소** 상자에 전자 메일을 받게 될 현재 직원(또는 공유 사서함)의 전자 메일 주소를 입력합니다.
  
5. **저장** 을 선택합니다.

6. 이전 직원의 계정을 삭제하지 않습니다.

::: moniker-end

## <a name="wipe-and-block-a-former-employees-mobile-device"></a>이전 직원의 모바일 장치 초기화 및 차단

이전 직원이 조직 전화가 있는 경우 Exchange 관리 센터를 사용하여 해당 장치를 지우고 차단하여 모든 조직 데이터가 장치에서 제거되고 더 이상 Office 365에 연결할 수 없습니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.
2. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다.
3. 사용자를 선택하고 모바일 **장치에서** 세부 정보 **보기를 선택합니다.**
4. 모바일 장치 **세부 정보** 페이지의 모바일 장치 아래에서 모바일 장치를 선택하고 데이터 지우기 장치를 선택한 다음 차단을 ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **선택합니다.**
5. **저장** 을 선택합니다.
   > [!TIP]
   > 사용자를 프레미스 Blackberry Enterprise Service에서 제거하거나 사용하지 않도록 설정해야 합니다. 또한 사용자에 대해 Blackberry 장치를 사용하지 않도록 설정해야 합니다. 사용자를 사용하지 않도록 설정하는 방법에 대한 구체적인 단계가 필요한 경우 Blackberry Business Cloud Services Administration Guide를 참조하세요.

## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Microsoft 365 데이터에 대한 이전 직원의 액세스 차단

 > [!IMPORTANT]
 > 계정을 차단하는 데 최대 24시간이 걸릴 수 있습니다. 사용자의 로그인 액세스를 즉시 차단해야 하는 경우 암호를 [](reset-passwords.md) 다시 설정한 다음 모든 장치에서 Microsoft 365 세션에서 로그인하는 일회성 이벤트를 시작해야 합니다. [지금 로그아웃!](#sign-out-now)을 참조하세요.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 차단할 직원의 이름을 선택하고 사용자 이름 아래에서 이 사용자 차단 **기호를 선택합니다.**
3. 사용자의 **로그인** 차단을 선택한 다음 저장을 **선택합니다.**

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택하고 로그인 **차단을 선택합니다.**

3. 사용자의 **로그인** 차단을 선택한 다음 저장을 **선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택하고 로그인 **차단을 선택합니다.**

3. 사용자의 **로그인** 차단을 선택한 다음 저장을 **선택합니다.**

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>전자 메일(Exchange Online)에 대한 이전 직원의 액세스 차단

Microsoft 365 구독의 일부로 전자 메일이 있는 경우 Exchange 관리 센터에 로그인하여 다음 단계에 따라 이전 직원이 전자 메일에 액세스하지 못하게 차단해야 합니다.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.
2. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다.
3. 사용자를 두 번 클릭하고 사서함 기능 **페이지로** 이동합니다. 모바일 **장치에서** 장치 사용 안 **Exchange ActiveSync** **장치용 OWA를** 사용하지 않도록 설정하고 메시지가 표시될 때 **모두 예로** 응답합니다.
4. 전자 **메일 연결에서** 사용 안 을 **선택하고** 메시지가 표시될 때 **예로** 응답합니다.

## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>이전 직원의 Microsoft 365 라이선스 제거 및 삭제

따라서 누군가 조직을 떠났다가 라이선스 비용을 계속 지불하지 않는 경우 Microsoft 365 라이선스를 제거한 다음 구독에서 라이선스를 삭제해야 합니다. 구독에서 라이선스를 삭제하지 않도록 선택하면 해당 라이선스를 다른 사용자에게 할당할 수 있습니다.
  
라이선스를 제거하면 해당 사용자의 모든 데이터가 30일간 보존됩니다. 데이터에 [액세스](get-access-to-and-back-up-a-former-user-s-data.md)하거나 해당 사용자가 복귀하면 계정을 [복원](restore-user.md)할 수 있습니다. 30일이 지난 후 모든 사용자 데이터(SharePoint Online에 저장된 문서 제외)는 Microsoft 365에서 영구적으로 삭제되고 복구할 수 없습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 차단할 직원의 이름을 선택한 다음 라이선스 및 앱 **탭을** 선택합니다.
3. 제거할 라이선스의 확인란 선택을 취소한 다음 변경 내용 **저장을 선택합니다.**

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택하고 제품 라이선스 옆에 있는 **편집을** **선택합니다.**

3. 제품 **라이선스** 페이지에서 제거할 라이선스를 해제한 다음 저장을 **선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원을 선택하고 제품 라이선스 옆에 있는 **편집을** **선택합니다.**

3. 제품 **라이선스** 페이지에서 제거할 라이선스를 해제한 다음 저장을 **선택합니다.**

::: moniker-end

**다른 사람을** 고용할 때까지 비용을 지불하는 라이선스 수를 줄이십시오. 다음 단계를 수행합니다.

::: moniker range="o365-worldwide"
1. 관리 센터에서 제품 청구  페이지로 이동하여 제품 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"></a> **탭을** 선택합니다.
2. 라이선스를 제거할 구독을 선택합니다.
3. 세부 정보 페이지에서 라이선스 **제거를 선택합니다.**
4. 라이선스 **제거** 창의 새 수량 아래에 있는  총 라이선스 상자에 이 구독에 대해 원하는 총 라이선스 수를 입력합니다. 예를 들어 라이선스가 25개 있는 경우 라이선스 중 하나를 제거하려면 24를 입력합니다.
5. **저장** 을 선택합니다.
::: moniker-end

::: moniker range="o365-germany"
1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.
2. 라이선스 **추가/제거를** 선택하여 라이선스를 삭제하여 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않습니다.
::: moniker-end

::: moniker range="o365-21vianet"
1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.
2. 라이선스 **추가/제거를** 선택하여 라이선스를 삭제하여 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않습니다.
::: moniker-end

비즈니스에 [다른](add-users.md) 사람을 추가하면 한 단계만 거치면 동시에 라이선스를 구입하라는 메시지가 표시될 것입니다.

비즈니스용 Microsoft 365의 사용자 라이선스를 관리하는 데 대한 자세한 내용은 [비즈니스용 Microsoft 365의](../manage/assign-licenses-to-users.md)사용자에게 라이선스 할당 및 비즈니스용 [Microsoft 365의](../manage/remove-licenses-from-users.md)사용자 라이선스 할당을 참조하세요.
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>삭제된 직원 계정이 비즈니스용 Skype에 영향을 미치는 방식

Office 365에서 사용자 라이선스를 제거하면 사용자와 연결된 PSTN 호출 번호가 해제됩니다. 이 PSTN 호출 번호를 다른 사용자에게 할당할 수 있습니다.
  
사용자가 큐 그룹에 속하는 경우 더 이상 통화 큐 에이전트의 실행 가능한 대상이 아닙니다. 따라서 통화 큐와 연결된 그룹에서도 사용자를 제거하는 것이 좋습니다.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>조직의 사용자에 대한 통화 전달 설정

종료된 직원의 전화 번호에 대해 통화 전달을 설정해야 하는 경우 통화 정책에 따라 수신 전화를 다른 사용자에게 전달하거나 동시에 다른 사용자에게 벨이 울리는 전달을 설정할 수 있습니다. 자세한 내용은 [Microsoft Teams의 통화 정책을 참조하세요.](https://docs.microsoft.com/microsoftteams/teams-calling-policy)
  
## <a name="delete-a-former-employees-user-account"></a>이전 직원의 사용자 계정 삭제

이전 직원의 모든 사용자 데이터에 액세스하여 저장한 후에는 이전 직원의 계정을 삭제할 수 있습니다.
  
전자 메일 전달을 설정했거나 공유 사서함으로 변환한 경우 계정을 삭제하지 마세요. 전달 또는 공유 사서함의 기준 위치가 되는 계정이 필요합니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 삭제할 직원의 이름을 선택합니다.
3. 사용자 이름 아래에서 사용자 삭제 **기호를 선택합니다.** 이 사용자에 대해 원하는 옵션을 선택한 다음 사용자 **삭제를 선택합니다.**

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 삭제할 직원의 이름을 선택합니다.

3. At the top of the page, select **Delete user.** 이 사용자에 대해 원하는 옵션을 선택한 다음 사용자 **삭제를 선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 삭제할 직원의 이름을 선택합니다.

3. At the top of the page, select **Delete user.** 이 사용자에 대해 원하는 옵션을 선택한 다음 사용자 **삭제를 선택합니다.**

::: moniker-end

사용자를 삭제하면 해당 계정은 약 30일간 비활성 상태가 됩니다. 이 기간에 계정을 복원하지 않으면 영구적으로 삭제됩니다.
  
### <a name="does-your-organization-use-active-directory"></a>조직에서 Active Directory를 사용하나요?

조직이 로컬 Active Directory 환경에서 사용자 계정을 Microsoft 365와 동기화하는 경우 로컬 Active Directory 서비스에서 해당 사용자 계정을 삭제하고 복원해야 합니다. Office 365에서는 해당 사용자 계정을 삭제하거나 복원할 수 없습니다.
  
Active Directory에서 사용자 계정을 삭제 및 복원하는 방법에 대한 자세한 내용은 사용자 계정 [삭제를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=841808)
  
Azure Active Directory를 사용하는 경우 [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet을 참조하세요.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>직원의 전자 메일 세션 종료에 대해 알아야 할 사항

다음은 전자 메일(Exchange)에서 직원을 제거하는 방법에 대한 정보입니다.
  
|||
|:-----|:-----|
|**실행할 수 있는 작업** <br/> |**방법** <br/> |
|세션(예: 웹용 Outlook, Outlook, Exchange Active Sync 등) 종료 및 새 세션 열기  <br/> |암호 재설정  <br/> |
|세션 종료 및 향후 세션에 대한 액세스 차단(모든 프로토콜에 대해)  <br/> |계정을 사용하지 않도록 설정합니다. 예를 들어(Exchange 관리 센터에서 또는 PowerShell 사용):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|특정 프로토콜(예: ActiveSync)에 대한 세션 종료  <br/> |프로토콜을 사용하지 않도록 설정합니다. 예를 들어(Exchange 관리 센터에서 또는 PowerShell 사용):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

위의 작업은 다음 세 곳에서 수행될 수 있습니다.
  
|||
|:-----|:-----|
|**여기에서 세션을 종료하는 경우** <br/> |**소요 시간** <br/> |
|Exchange 관리 센터에서 또는 PowerShell을 사용하는 경우  <br/> |30분 이내의 지연이 예상됨  <br/> |
|Azure Active Directory 관리 센터에서  <br/> |60분의 지연이 예상됨  <br/> |
|온-프레미스 환경에서  <br/> |3시간 이상의 지연이 예상됨  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>계정 종료에 대해 가장 빠른 응답을 받는 방법

 **가장 빠름**: Exchange 관리 센터(PowerShell 사용) 또는 Azure Active Directory 관리 센터를 사용합니다. 온-프레미스 환경에서 DirSync를 통해 변경 내용을 동기화하는 데 몇 시간이 걸릴 수 있습니다.
  
 **온 - 프레미스 및 Exchange Datacenter에 있는 사용자에게 가장 빠름**: Azure Active Directory 관리 센터/Exchange 관리 센터를 사용하여 세션을 종료하고 온 - 프레미스 환경에서도 변경합니다. 그렇지 않으면 Azure Active Directory 관리 센터/Exchange 관리 센터의 변경 사항이 DirSync에 의해 덮어 쓰여집니다.
  
## <a name="related-articles"></a>관련 문서

[사용자 복원](restore-user.md)
