---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정 삭제
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: 이 문서에서는 PowerShell에서 서로 다른 모듈을 사용 하 여 Microsoft 365 사용자 계정을 삭제 하는 방법을 알아봅니다.
ms.openlocfilehash: 0c13b57c13fb3d01d648438a5d6973fea8b9db67
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235445"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="be017-103">PowerShell을 사용 하 여 Microsoft 365 사용자 계정 삭제</span><span class="sxs-lookup"><span data-stu-id="be017-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="be017-104">Microsoft 365 용 PowerShell을 사용 하 여 사용자 계정을 삭제 및 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be017-104">You can use PowerShell for Microsoft 365 to delete and restore a user account.</span></span>

>[!Note]
><span data-ttu-id="be017-105">Microsoft 365 관리 센터를 사용 하 여 [사용자 계정을 복원 하는 방법에 대해 알아봅니다](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) .</span><span class="sxs-lookup"><span data-stu-id="be017-105">[Learn how to restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="be017-106">추가 리소스 목록은 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be017-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="be017-107">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="be017-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="be017-108">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="be017-109">연결한 후 다음 구문을 사용하여 개별 사용자 계정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-109">After you have connected, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="be017-110">이 예제에서는 사용자 계정 fabricec@litwareinc.com을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-110">This example removes the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="be017-111">**AzureADUser** cmdlet의 **-ObjectID** 매개 변수는 사용자 보안 주체 이름이 라고도 하는 계정의 로그인 이름 또는 계정의 개체 ID를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-111">The **-ObjectID** parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="be017-112">사용자 이름을 기준으로 계정 이름을 표시하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="be017-113">이 예제에서는 Caleb Sills라는 사용자의 계정 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-113">This example displays the account name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="be017-114">사용자 표시 이름을 기준으로 계정을 제거하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="be017-115">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="be017-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="be017-p102">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하여 사용자 계정을 삭제할 경우에 계정은 영구 삭제되지 않습니다. 30일 이내에 삭제한 사용자 계정은 복원할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="be017-p102">When you delete a user account with the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted. You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="be017-118">먼저 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="be017-119">사용자 계정을 삭제 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="be017-120">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol**이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be017-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="be017-121">이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="be017-122">BelindaN@litwareinc.com 사용자 계정을 삭제 하는이 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="be017-122">This example deletes the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="be017-123">30 일 유예 기간 동안 삭제 된 사용자 계정을 복원 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="be017-124">삭제 된 계정 BelindaN@litwareinc.com을 복원 하는이 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="be017-124">This example restores the deleted account BelindaN@litwareinc.com.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 <span data-ttu-id="be017-125">**참고:**</span><span class="sxs-lookup"><span data-stu-id="be017-125">**Notes:**</span></span>
  
- <span data-ttu-id="be017-126">복원할 수 있는 삭제된 사용자 목록을 보려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-126">To see the list of deleted users that can be restored, run the following command:</span></span>
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- <span data-ttu-id="be017-127">사용자 계정의 원본 사용자 계정 이름이 다른 계정에서 사용된 경우에, 사용자 계정을 복원할 때 다른 사용자 계정 이름을 지정하려면 _UserPrincipalName_ 대신에 _NewUserPrincipalName_ 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be017-127">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="be017-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be017-128">See also</span></span>

[<span data-ttu-id="be017-129">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="be017-129">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="be017-130">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="be017-130">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="be017-131">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="be017-131">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
