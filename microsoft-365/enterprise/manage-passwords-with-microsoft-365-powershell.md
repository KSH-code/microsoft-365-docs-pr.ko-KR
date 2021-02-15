---
title: PowerShell을 사용하여 암호 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: PowerShell을 사용하여 암호를 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073215"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="fac61-103">PowerShell을 사용하여 암호 관리</span><span class="sxs-lookup"><span data-stu-id="fac61-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="fac61-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="fac61-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fac61-105">Microsoft 365 관리 센터 대신 Microsoft 365용 PowerShell을 사용하여 Microsoft 365에서 암호를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="fac61-106">이 문서의 명령 블록에 변수 값을 지정해야 하는 경우 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="fac61-107">명령 블록을 클립보드에 복사하여 메모장이나 PowerShell ISE(통합 스크립트 환경)에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="fac61-108">변수 값을 입력하고 "<" 및 ">" 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="fac61-109">PowerShell 창 또는 PowerShell ISE에서 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fac61-110">Graph 모듈용 Azure Active Directory PowerShell 사용하기</span><span class="sxs-lookup"><span data-stu-id="fac61-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="fac61-111">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="fac61-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="fac61-112">암호 설정</span><span class="sxs-lookup"><span data-stu-id="fac61-112">Set a password</span></span>

<span data-ttu-id="fac61-113">다음 명령을 사용하여 사용자 계정의 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="fac61-114">사용자가 강제로 암호를 변경하도록 강제</span><span class="sxs-lookup"><span data-stu-id="fac61-114">Force a user to change their password</span></span>

<span data-ttu-id="fac61-115">다음 명령을 사용하여 암호를 설정하고 사용자가 새 암호를 변경하도록 강제합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="fac61-116">다음 명령을 사용하여 암호를 설정하고 사용자가 다음에 로그인할 때 새 암호를 변경하도록 강제합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fac61-117">Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기</span><span class="sxs-lookup"><span data-stu-id="fac61-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fac61-118">먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="fac61-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="fac61-119">암호 설정</span><span class="sxs-lookup"><span data-stu-id="fac61-119">Set a password</span></span>

<span data-ttu-id="fac61-120">다음 명령을 사용하여 사용자 계정의 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="fac61-121">사용자가 강제로 암호를 변경하도록 강제</span><span class="sxs-lookup"><span data-stu-id="fac61-121">Force a user to change their password</span></span>

<span data-ttu-id="fac61-122">다음 명령을 사용하여 사용자가 암호를 강제로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="fac61-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fac61-123">See also</span></span>

[<span data-ttu-id="fac61-124">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="fac61-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fac61-125">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="fac61-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fac61-126">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="fac61-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

