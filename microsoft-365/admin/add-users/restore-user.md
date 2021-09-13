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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 사용자 계정을 삭제한 후 30일 이내에 계정 및 모든 데이터를 복원할 수 있으며 사용자는 동일한 계정으로 로그인할 수 있습니다.
ms.openlocfilehash: e37f913bcc6a54bdcc1e0f52168fe1aab0c8afdd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185171"
---
# <a name="restore-a-user"></a>사용자 복원
   
사용자 계정을 삭제한 후 30일 이내에 복원할 경우 계정 및 모든 관련 데이터가 복원됩니다. 사용자는 같은 회사 또는 학교 계정으로 로그인할 수 있습니다. 해당 사서함이 완전히 복원됩니다. 특정 사용자 계정을 복원할 수 있는 기간이 얼마나 남았는지 확인해야 하는 경우 [Microsoft에 문의](../../business-video/get-help-support.md)하세요.
  
다음은 몇 가지 팁입니다.
  
- 계정에 할당할 수 있는 라이선스가 있는지 확인
    
- 비즈니스에서 Active Directory를 사용하는 경우 사용자 계정 복원에 대한 자세한 내용은 에서 삭제된 사용자 계정 문제를 해결하는 [Office 365.](/office365/troubleshoot/active-directory/restore-deleted-user-accounts) 
    
## <a name="restore-one-or-more-user-accounts"></a>하나 이상의 사용자 계정 복원

이러한 단계를 수행하려면 Microsoft 365 관리자 또는 사용자 관리 관리자로 설정해야 합니다. 

1. 관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.

2. 삭제된 **사용자 페이지에서** 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**
    
3. 프롬프트에 따라 암호를 설정한 다음 복원을 **선택합니다.**
    
4. 사용자가 복원되면 전자 메일 **보내기 및 닫기 를 선택합니다.** 이름 충돌이나 프록시 주소 충돌이 발생할 경우 해당 계정을 복원하는 방법에 대한 아래 지침을 참조하세요.
    
사용자를 복원한 후 암호가 변경되었다는 사실을 사용자에게 알리고 추가 정보를 제공해야 합니다.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>사용자 이름 충돌이 있는 사용자 복원

사용자 이름 충돌은 사용자 계정을 삭제하고 같은 사용자 또는 비슷한 이름의 다른 사용자에 대해 동일한 사용자 이름으로 새 사용자 계정을 만든 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다.
  
이 문제를 해결하려면 활성 사용자 계정을 복원하려는 계정으로 바꾸거나 동일한 사용자 이름을 갖는 2개의 계정이 존재하지 않도록 다른 사용자 이름을 복원하려는 계정에 할당합니다. 단계는 다음과 같습니다.

1. 관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.
  
2. 삭제된 **사용자 페이지에서** 복원할 사용자의 이름을 선택하고 복원을 **선택합니다.**
    
    > [!NOTE]
    > 두 명 이상의 사용자를 복원하지 못한 경우 일부 사용자의 복원 작업이 실패했음을 알리는 오류 메시지가 나타납니다. 로그를 보고 복원되지 않은 사용자를 확인한 다음 실패한 계정을 한 번에 하나씩 복원합니다. 
  
3. 프롬프트에 따라 암호를 설정하고 복원을 **선택합니다.**
    
4. 메시지에서 계정을 복원하는 동안 문제가 발생했음을 알려 줍니다. 다음 중 하나를 수행합니다.
    
  - 복원을 취소하고 현재 활성 사용자의 이름을 바꿉니다. 그런 다음 복원을 다시 시도합니다.
    
  - 또는 사용자의 새 기본 전자 메일 주소를 입력하고 복원을 **선택합니다.**
    
5. 결과를 검토한 다음 **닫기** 를 선택합니다.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>프록시 주소 충돌이 있는 사용자 복원

프록시 주소 충돌은 프록시 주소가 포함된 사용자 계정을 삭제하고 동일한 프록시 주소를 다른 계정에 할당한 후 삭제된 계정을 복원하려고 하는 경우에 발생합니다. 이 문제를 해결하려면 아래 단계를 따르세요.
  
이렇게하려면 [](about-admin-roles.md) 관리자 권한이 Microsoft 365 있어야 합니다. 

1. 관리 센터에서 사용자 **삭제된 사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">페이지로</a> 이동합니다.

2. **삭제된 사용자** 페이지에서 복원할 사용자를 선택하고 **복원** 을 선택합니다. 
    
3. 복원 **페이지에서** 지침에 따라 암호를 설정하고 복원을 **선택합니다.** 충돌하는 프록시 주소가 복원할 사용자에서 자동으로 제거됩니다.
    
4. 결과를 검토한 다음 **닫기** 를 선택합니다.

## <a name="related-content"></a>관련 콘텐츠

[사용자](delete-a-user.md) 삭제(문서)\
[관리자 역할](assign-admin-roles.md) 할당(비디오)\
[사용자에게 라이선스](../manage/assign-licenses-to-users.md) 할당(문서)
