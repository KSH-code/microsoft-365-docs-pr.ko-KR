---
title: 1단계 - 직원이 로그인하지 못하게 Microsoft 365
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 이전 직원의 로그인을 차단하고 Microsoft 365 차단합니다.
ms.openlocfilehash: 326188e0000d3c59eb411222d3e3c47177b383ed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161693"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>1단계 - 이전 직원이 로그인하지 못하게 방지하고 Microsoft 365 액세스 차단

사용자의 로그인 액세스를 즉시 차단해야 하는 경우 암호를 다시 설정해야 합니다. 이 단계에서는 사용자의 로그인을 강제로 Microsoft 365.

> [!NOTE]
> 다른 관리자에 대한 로그인을 시작하려면 전역 관리자로 설정해야 합니다. 관리자가 아닌 사용자의 경우 사용자 관리자 또는 헬프데스크 관리자 사용자를 사용하여 이 작업을 수행할 수 있습니다. [관리자 역할에 대해 자세히 알아보시고](about-admin-roles.md)

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..
2. 사용자 이름 옆의 상자를 선택한 다음 암호 다시 설정을 **선택합니다.**
3. 새 암호를 입력한 다음 다시 설정을 **선택합니다.** (보내지 않습니다.)
4. 사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 모든 세션에서 **서명을 선택합니다.** 

1시간 이내에 또는 현재 Microsoft 365 페이지에서 나면 다시 로그인하라는 메시지가 표시됩니다. 액세스 토큰은 한 시간 동안 양호하기 때문에 시간 표시 막대는 해당 토큰에 남아 있는 시간 및 현재 웹 페이지를 탐색하는지 여부에 따라 결정됩니다.
  
> [!IMPORTANT]
> 사용자가 사서함에 있는 웹용 Outlook 사서함을 클릭하는 것만이 즉시 시작되지 않을 수 있습니다. 다른 타일(예: OneDrive)을 선택하거나 브라우저를 새로 고치자마자 로그인이 시작됩니다.
  
PowerShell을 사용하여 사용자를 즉시 로그인하기 위해 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet을 참조하세요.
  
전자 메일에서 다른 사람을 제거하는 데 걸리는 시간에 대한 자세한 내용은 [직원의 전자 메일 세션 종료에 대해 알아야 할 사항](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)을 참조하세요.

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>이전 직원의 서비스 액세스 Microsoft 365 차단

> [!IMPORTANT]
 > 계정을 차단하는 데 최대 24시간이 걸릴 수 있습니다. 사용자의 로그인 액세스를 즉시 차단해야 하는 경우 위의 단계를 수행하고 암호를 다시 설정하세요.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..
2. 차단할 직원의 이름을 선택하고 사용자 이름에서 이 사용자 차단의 **기호를 선택합니다.**
3. 사용자가 로그인할 수 **없습니다.를** 선택한 다음 저장 을 **선택합니다.**

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>전자 메일(Exchange Online)에 대한 이전 직원의 액세스 차단

Microsoft 365 구독의 일부로 전자 메일이 있는 경우 Exchange 관리 센터에 로그인하고 다음 단계에 따라 이전 직원이 전자 메일에 액세스하지 못하게 차단합니다.
  
1. <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange 관리 센터</a>로 이동합니다.
2. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다.
3. 목록에서 사용자 사서함을 선택한 다음  세부 정보 창(오른쪽)에서 전자 메일 앱의 전자 메일 **앱 설정** 관리를 **선택합니다.** 모든 **옵션에** 대해 슬라이더를 해제합니다. **모바일(Exchange ActiveSync)** **,** 웹용 Outlook , Outlook **데스크톱(MAPI)**, Exchange 웹 **서비스,** **POP3** 및 **IMAP**.
4. **저장** 을 선택합니다.

## <a name="related-content"></a>관련 콘텐츠

[Exchange 관리 센터의 Exchange Online](/exchange/exchange-admin-center)

[사용자 복원](restore-user.md)
