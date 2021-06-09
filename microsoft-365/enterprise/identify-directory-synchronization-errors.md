---
title: 목록에서 디렉터리 동기화 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
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
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Microsoft 365 관리 센터에서 디렉터리 동기화 오류 및 가능한 수정 Microsoft 365 방법을 알아보십시오.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907507"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>목록에서 디렉터리 동기화 Microsoft 365

사이트 관리 센터에서 디렉터리 동기화 오류를 볼 Microsoft 365 있습니다. User 개체 오류만 표시됩니다. PowerShell에서 오류를 확인하려면 [DirSyncProvisioningErrors로 개체 식별을 참조합니다.](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 디렉터리 동기화 오류 보기

관리 센터에서 오류를 Microsoft 365:
  
1. 전역 관리자 [계정으로](https://admin.microsoft.com) Microsoft 365 관리 센터에 로그인합니다. 
    
2. 홈 **페이지에** 사용자 관리 **카드가** 표시됩니다. 
    
    ![Microsoft 365 관리 센터의 사용자 관리 카드](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. 카드에서 Azure  **AD에서** 동기화 오류를 커넥트 디렉터리 동기화 오류 페이지에서 오류를 **확인합니다.**   
    
    ![디렉터리 동기화 오류 페이지의 예](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. 오류를 선택하고 오류에 대한 정보와 수정 방법에 대한 팁이 있는 세부 정보 창을 표시합니다.

   ![디렉터리 동기화 오류의 세부 정보 예](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
확인한 후 [확인된](fix-problems-with-directory-synchronization.md) 문제를 해결하기 위해 디렉터리 Microsoft 365 수정을 참조합니다.