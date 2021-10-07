---
title: 목록에서 디렉터리 동기화 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: 디렉터리 동기화 오류 및 가능한 수정 내용을 보기 위한 방법을 Microsoft 365 관리 센터.
ms.openlocfilehash: 2b832cff65aad0ae7327f440a565e12c7cba66f4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197380"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>목록에서 디렉터리 동기화 Microsoft 365

에서 디렉터리 동기화 오류를 볼 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">수 Microsoft 365 관리 센터.</a> User 개체 오류만 표시됩니다. PowerShell에서 오류를 확인하려면 [DirSyncProvisioningErrors로 개체 식별을 참조합니다.](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>서버의 디렉터리 동기화 오류를 Microsoft 365 관리 센터

오류 메시지에서 오류를 Microsoft 365 관리 센터.
  
1. 전역 관리자 [Microsoft 365 관리 센터](https://admin.microsoft.com) 로그인합니다. 
    
2. 홈 **페이지에** 사용자 관리 **카드가** 표시됩니다. 
    
    ![사용자 관리 카드의 Microsoft 365 관리 센터.](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. 카드에서 Azure  **AD에서** 동기화 오류를 커넥트 디렉터리 동기화 오류 페이지에서 오류를 **확인합니다.**   
    
    ![디렉터리 동기화 오류 페이지의 예입니다.](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. 오류를 선택하고 오류에 대한 정보와 수정 방법에 대한 팁이 있는 세부 정보 창을 표시합니다.

   ![디렉터리 동기화 오류의 세부 정보 예제입니다.](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
확인한 후 [확인된](fix-problems-with-directory-synchronization.md) 문제를 해결하기 위해 디렉터리 Microsoft 365 수정을 참조합니다.