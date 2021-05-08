---
title: 7단계 - 이전 직원의 사용자 계정 삭제
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
description: 다음 단계에 따라 이전 직원의 사용자 계정을 삭제합니다.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244237"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>7단계 - 이전 직원의 사용자 계정 삭제

이전 직원의 모든 사용자 데이터에 액세스하여 저장한 후에는 이전 직원의 계정을 삭제할 수 있습니다.

> [!IMPORTANT]
> 전자 메일 전달을 설정했거나 공유 사서함으로 변환한 경우 계정을 삭제하지 마세요. 전달 또는 공유 사서함의 기준 위치가 되는 계정이 필요합니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.
2. 삭제할 직원의 이름을 선택합니다.
3. 사용자 이름에서 사용자 **삭제 를 선택합니다.** 이 사용자에 대해 원하는 옵션을 선택한 다음 사용자 삭제 **를 선택합니다.** 이 사용자의 전자 메일 및 OneDrive 다른 사용자에게 이미 액세스 권한을 부여한 경우 여기에서 다시 할 수 없습니다.

사용자를 삭제하면 해당 계정은 약 30일간 비활성 상태가 됩니다. 이 기간에 계정을 복원하지 않으면 영구적으로 삭제됩니다.
  
## <a name="does-your-organization-use-active-directory"></a>조직에서 Active Directory를 사용하나요?

조직에서 사용자 계정을 로컬 Active Directory Microsoft 365 사용자 계정을 동기화하는 경우 로컬 Active Directory 서비스에서 해당 사용자 계정을 삭제하고 복원해야 합니다. Office 365에서는 해당 사용자 계정을 삭제하거나 복원할 수 없습니다.

Active Directory에서 사용자 계정을 삭제 및 복원하는 방법에 대한 자세한 내용은 사용자 계정 [삭제를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))
  
사용 중이면 Azure Active Directory [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet을 참조합니다.
  
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
