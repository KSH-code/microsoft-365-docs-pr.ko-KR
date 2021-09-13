---
title: 사용자에 대한 디렉터리 동기화를 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: 이 문서에서는 PowerShell을 사용하여 사용자에 대한 디렉터리 동기화를 해제하는 Microsoft 365.
ms.openlocfilehash: 28e0a83bba1a63a7cd1d2f449b9bf3ba34e4862a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187827"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>사용자에 대한 디렉터리 동기화를 Microsoft 365
PowerShell을 사용하여 디렉터리 동기화를 해제하고 동기화된 사용자를 클라우드 전용으로 변환할 수 있습니다. 그러나 디렉터리 동기화를 문제 해결 단계로 해제하지 않는 것이 좋습니다. 디렉터리 동기화 문제 해결에 대한 도움이 필요한 경우 디렉터리 동기화 문제 해결 문서를 [Microsoft 365](fix-problems-with-directory-synchronization.md) 참조하세요. 
  
[필요한 경우](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 비즈니스 제품에 대한 지원에 문의합니다.
  
## <a name="turn-off-directory-synchronization"></a>디렉터리 동기화 끄기  
디렉터리 동기화를 끄기 위해 다음을 실행합니다.
  
1. 먼저 필요한 소프트웨어를 설치하고 Microsoft 365 연결합니다. 자세한 내용은 커넥트 모듈을 사용하여 Microsoft Azure Active Directory [모듈을 Windows PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
2. [Set-MsolDirSyncEnabled를](/previous-versions/azure/dn194097(v=azure.100)) 사용하여 디렉터리 동기화를 사용하지 않도록 설정할 수 있습니다. 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>이 명령을 사용하는 경우 디렉터리 동기화를 다시 켜기 전에 72시간을 기다려야 합니다.
>
