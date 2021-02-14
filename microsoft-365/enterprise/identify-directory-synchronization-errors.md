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
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="1734d-103">Microsoft 365에서 디렉터리 동기화 오류 보기</span><span class="sxs-lookup"><span data-stu-id="1734d-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="1734d-104">Microsoft 365 관리 센터에서 디렉터리 동기화 오류를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1734d-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1734d-105">User 개체 오류만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1734d-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="1734d-106">PowerShell에서 오류를 확인하려면 [DirSyncProvisioningErrors를](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)사용하여 개체 식별을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1734d-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1734d-107">Microsoft 365 관리 센터에서 디렉터리 동기화 오류 보기</span><span class="sxs-lookup"><span data-stu-id="1734d-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1734d-108">Microsoft 365 관리 센터에서 오류를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="1734d-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="1734d-109">전역 관리자 계정으로 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1734d-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="1734d-110">홈 **페이지에** 사용자 관리 **카드가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1734d-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![Microsoft 365 관리 센터의 사용자 관리 카드](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="1734d-112">카드에서 Azure  **AD Connect에서** 동기화 오류를 선택하고 **디렉터리** 동기화 오류 페이지에서 오류를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1734d-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![디렉터리 동기화 오류 페이지의 예](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="1734d-114">오류에 대한 정보와 수정 방법에 대한 팁과 함께 세부 정보 창을 표시하는 오류를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="1734d-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![디렉터리 동기화 오류의 세부 정보 예](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="1734d-116">확인한 후 [Microsoft 365의](fix-problems-with-directory-synchronization.md) 디렉터리 동기화 문제를 해결하여 식별된 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="1734d-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>

