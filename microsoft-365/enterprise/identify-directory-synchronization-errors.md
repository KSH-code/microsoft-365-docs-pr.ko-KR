---
title: Microsoft 365에서 디렉터리 동기화 오류 보기
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
description: Microsoft 365 관리 센터에서 디렉터리 동기화 오류 및 가능한 수정 내용을 보는 방법을 알아보십시오.
ms.openlocfilehash: 5103b1f8a8f0514ca30fd71b94dee2530f0b082f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692761"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Microsoft 365에서 디렉터리 동기화 오류 보기

Microsoft 365 관리 센터에서 디렉터리 동기화 오류를 볼 수 있습니다. User 개체 오류만 표시됩니다. PowerShell에서 오류를 확인하려면 [DirSyncProvisioningErrors를](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)사용하여 개체 식별을 참조합니다.

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 디렉터리 동기화 오류 보기

Microsoft 365 관리 센터에서 오류를 표시하려면
  
1. 전역 관리자 계정으로 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다. 
    
2. 홈 **페이지에** 사용자 관리 **카드가** 표시됩니다. 
    
    ![Microsoft 365 관리 센터의 사용자 관리 카드](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. 카드에서 Azure  **AD Connect에서** 동기화 오류를 선택하고 **디렉터리** 동기화 오류 페이지에서 오류를 확인합니다.   
    
    ![디렉터리 동기화 오류 페이지의 예](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. 오류에 대한 정보와 수정 방법에 대한 팁과 함께 세부 정보 창을 표시하는 오류를 선택하십시오.

   ![디렉터리 동기화 오류의 세부 정보 예](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
확인한 후 [Microsoft 365의](fix-problems-with-directory-synchronization.md) 디렉터리 동기화 문제를 해결하여 식별된 문제를 해결합니다.

