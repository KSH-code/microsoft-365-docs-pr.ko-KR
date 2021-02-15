---
title: 사용자 복원
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 삭제된 사용자 계정 및 모든 관련 데이터를 복원하는 방법을 학습합니다.
ms.openlocfilehash: d14995c8ee2d62c1d722ef0bcc7577745a747082
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114000"
---
# <a name="restore-a-user"></a>사용자 복원

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end
   
사용자 계정을 삭제한 후 30일 이내에 복원할 경우 계정 및 모든 관련 데이터가 복원됩니다. 사용자는 같은 회사 또는 학교 계정으로 로그인할 수 있습니다. 해당 사서함이 완전히 복원됩니다. 특정 사용자 계정을 복원할 수 있는 기간이 얼마나 남았는지 확인해야 하는 경우 [Microsoft에 문의](../contact-support-for-business-products.md)하세요.
  
다음은 몇 가지 팁입니다.
  
- 계정에 할당할 수 있는 라이선스가 있는지 확인
    
- 회사에서 Active Directory를 사용할 경우, 사용자 계정 복원에 대한 자세한 내용은 [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308)(Office 365에서 삭제된 사용자 계정 문제를 해결하는 방법)를 참조하세요. 
    
## <a name="restore-one-or-more-user-accounts"></a>하나 이상의 사용자 계정 복원

다음 단계를 수행하려면 Microsoft 365 전역 관리자 또는 사용자 관리 관리자 되어야 합니다. 
  
 
::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 [센터로 이동한](https://go.microsoft.com/fwlink/p/?linkid=848041)다음  사용자가 \> **삭제된 사용자를 선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 [센터로 이동한](https://go.microsoft.com/fwlink/p/?linkid=850627)다음  사용자가 \> **삭제된 사용자를 선택합니다.**

::: moniker-end

2. 삭제된 **사용자** 페이지에서 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**
    
 
3. 프롬프트에 따라 암호를 설정한 다음 복원을 **선택합니다.**
    
4. 사용자가 복원된 경우 전자 메일 **보내기 및 닫기 를 선택합니다.** 이름 충돌이나 프록시 주소 충돌이 발생할 경우 해당 계정을 복원하는 방법에 대한 아래 지침을 참조하세요.
    
사용자를 복원한 후 암호가 변경되었다는 사실을 사용자에게 알리고 사용자를 후속으로 처리해야 합니다.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>사용자 이름 충돌이 있는 사용자 복원
<a name="RestoreUserNameConflict"> </a>

사용자 이름 충돌은 사용자 계정을 삭제하고 같은 사용자 또는 비슷한 이름의 다른 사용자에 대해 동일한 사용자 이름으로 새 사용자 계정을 만든 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다.
  
이 문제를 해결하려면 활성 사용자 계정을 복원하려는 계정으로 바꾸거나 동일한 사용자 이름을 갖는 2개의 계정이 존재하지 않도록 다른 사용자 이름을 복원하려는 계정에 할당합니다. 단계는 다음과 같습니다.
  

::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 [센터로 이동한](https://go.microsoft.com/fwlink/p/?linkid=848041)다음  사용자가 \> **삭제된 사용자를 선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 [센터로 이동한](https://go.microsoft.com/fwlink/p/?linkid=850627)다음  사용자가 \> **삭제된 사용자를 선택합니다.**

::: moniker-end

  
2. 삭제된 **사용자** 페이지에서 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**
    
    > [!NOTE]
    > 두 명 이상의 사용자를 복원하지 못한 경우 일부 사용자의 복원 작업이 실패했음을 알리는 오류 메시지가 나타납니다. 로그를 보고 복원되지 않은 사용자를 확인한 다음 실패한 계정을 한 번에 하나씩 복원합니다. 
  
3. 프롬프트에 따라 암호를 설정하고 복원을 **선택합니다.**
    
4. 메시지에서 계정을 복원하는 동안 문제가 발생했음을 알려 줍니다. 다음 중 하나를 수행합니다.
    
  - 복원을 취소하고 현재 활성 사용자의 이름을 바꿉니다. 그런 다음 복원을 다시 시도합니다.
    
  - 또는 사용자의 새 기본 전자 메일 주소를 입력하고 복원을 **선택합니다.**
    
5. 결과를 검토한 다음 **닫기** 를 선택합니다.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>프록시 주소 충돌이 있는 사용자 복원

프록시 주소 충돌은 프록시 주소가 포함된 사용자 계정을 삭제하고 동일한 프록시 주소를 다른 계정에 할당한 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다. 이 문제를 해결하려면 아래 단계를 따르세요.
  
이렇게하려면 [](about-admin-roles.md) Microsoft 365에서 관리자 권한이 있어야 합니다. 
  

::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

관리 [센터로 이동한](https://go.microsoft.com/fwlink/p/?linkid=848041)다음  사용자가 \> **삭제된 사용자를 선택합니다.**

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 [센터로 이동한](https://go.microsoft.com/fwlink/p/?linkid=850627)다음  사용자가 \> **삭제된 사용자를 선택합니다.**

::: moniker-end

2. **삭제된 사용자** 페이지에서 복원할 사용자를 선택하고 **복원** 을 선택합니다. 
    
3. 복원 **페이지에서** 지침에 따라 암호를 설정하고 복원을 **선택합니다.** 충돌하는 프록시 주소가 복원할 사용자에서 자동으로 제거됩니다.
    
4. 결과를 검토한 다음 **닫기** 를 선택합니다.

## <a name="related-articles"></a>관련 문서

[사용자 삭제](delete-a-user.md)
  
