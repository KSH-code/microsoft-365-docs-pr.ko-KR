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
description: 이전 직원의 로그인을 차단하고 Microsoft 365 차단합니다.
ms.openlocfilehash: 84852e9bccb1d4370db07492baf7ccaed7f6db3d
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698907"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>1단계 - 이전 직원이 로그인하지 못하게 방지하고 Microsoft 365 액세스 차단

사용자의 로그인 액세스를 즉시 차단해야 하는 경우 암호를 다시 설정해야 합니다. 이 단계에서는 사용자의 로그인을 강제로 Microsoft 365.

> [!NOTE]
> 다른 관리자에 대한 로그인을 시작하려면 전역 관리자로 설정해야 합니다. 관리자가 아닌 사용자의 경우 사용자 관리자 또는 헬프데스크 관리자 사용자를 사용하여 이 작업을 수행할 수 있습니다.
> 관리자 역할에 대한 관리자 <a href="https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles">역할에 대해 자세히 알아보시고</a>

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 사용자 이름 옆의 상자를 선택한 다음 암호 다시 설정을 **선택합니다.**
3. 새 암호를 입력한 다음 다시 설정을 **선택합니다.** (보내지 않습니다.)
4. 사용자의 이름을 선택하여 속성 창으로 이동하고 계정 탭에서 로그인 시작 **을 선택합니다.** 

1시간 이내에 또는 현재 Microsoft 365 페이지에서 나면 다시 로그인하라는 메시지가 표시됩니다. 액세스 토큰은 한 시간 동안 양호하기 때문에 시간 표시 막대는 해당 토큰에 남아 있는 시간 및 현재 웹 페이지를 탐색하는지 여부에 따라 결정됩니다.
  
> [!IMPORTANT]
> 사용자가 웹에서 Outlook 있는 경우 사서함을 클릭하기만 하면 즉시 시작되지 않을 수 있습니다. 다른 타일(예: OneDrive)을 선택하거나 브라우저를 새로 고치자마자 로그인이 시작됩니다.
  
PowerShell을 사용하여 사용자를 즉시 로그인하기 위해 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet을 참조하세요.
  
전자 메일에서 다른 사람을 제거하는 데 걸리는 시간에 대한 자세한 내용은 [직원의 전자 메일 세션 종료에 대해 알아야 할 사항](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)을 참조하세요.

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>이전 직원의 서비스 액세스 Microsoft 365 차단

> [!IMPORTANT]
 > 계정을 차단하는 데 최대 24시간이 걸릴 수 있습니다. 사용자의 로그인 액세스를 즉시 차단해야 하는 경우 위의 단계를 수행하고 암호를 다시 설정하세요.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 차단할 직원의 이름을 선택하고 사용자 이름에서 이 사용자 차단의 **기호를 선택합니다.**
3. 사용자가 로그인할 수 **없습니다.를** 선택한 다음 저장 을 **선택합니다.**

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>전자 메일(Exchange Online)에 대한 이전 직원의 액세스 차단

Microsoft 365 구독의 일부로 전자 메일이 있는 경우 Exchange 관리 센터에 로그인하고 다음 단계에 따라 이전 직원이 전자 메일에 액세스하지 못하게 차단합니다.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.
2. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다.
3. 사용자를 두 번 클릭하고 사서함 기능 **페이지로** 이동합니다. 모바일 **장치에서** 장치 사용 안 **Exchange ActiveSync** 및 **장치용 OWA** 사용 안 을 선택하고 메시지가 표시될 때 모두 예를 선택합니다. 
4. 전자 **메일 연결에서** 사용 **안** 을 선택하고 메시지가 **표시될** 때 예를 선택합니다.
