---
title: PowerShell을 비즈니스용 Skype 온라인 정책을 사용자 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: '요약: PowerShell을 사용하여 Microsoft 365 Online 정책을 사용하여 사용자 비즈니스용 Skype 할당합니다.'
ms.openlocfilehash: d7f369e96f3db95c741e6d4f2178eaf9032ab0bb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288086"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="53561-103">PowerShell을 비즈니스용 Skype 온라인 정책을 사용자 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="53561-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="53561-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="53561-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="53561-105">PowerShell을 사용하여 Microsoft 365 온라인 정책을 사용하여 사용자당 통신 설정을 효율적으로 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="53561-106">PowerShell 명령 실행 준비</span><span class="sxs-lookup"><span data-stu-id="53561-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="53561-107">다음 지침을 사용하여 명령을 실행하기 위한 설정(이미 완료한 단계 건너뛰기)을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="53561-108">Skype for Business Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="53561-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="53561-109">최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="53561-110">[Teams PowerShell 모듈](/microsoftteams/teams-powershell-install)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="53561-111">Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="53561-112">메시지가 표시될 때 비즈니스용 Skype 계정 이름과 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="53561-113">사용자 계정에 대한 외부 통신 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="53561-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="53561-114">사용자 계정에서 외부 통신 설정을 변경하려는 경우를 가정해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-114">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="53561-115">예를 들어 Alex가 페더임 사용자와 통신할 수 있도록 허용할 수 있지만(EnableFederationAccess가 True와 같음) Windows Live 사용자와는 통신하지 않을 수 있습니다(EnablePublicCloudAccess는 False임).</span><span class="sxs-lookup"><span data-stu-id="53561-115">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="53561-116">이를 위해 다음 두 가지 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-116">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="53561-117">기준을 충족하는 외부 액세스 정책을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="53561-118">해당 외부 액세스 정책을 Alex에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="53561-119">Alex를 할당할 외부 액세스 정책을 결정하는 방법</span><span class="sxs-lookup"><span data-stu-id="53561-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="53561-120">다음 명령은 EnableFederationAccess가 True로 설정되고 EnablePublicCloudAccess가 False로 설정된 모든 외부 액세스 정책을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="53561-121">ExternalAccessPolicy의 사용자 지정 인스턴스를 만들지 않은 경우 이 명령은 조건(FederationOnly)을 충족하는 정책 하나를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="53561-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="53561-123">Alex에게 할당할 정책을 알고 있습니다. [이제 Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet을 사용하여 해당 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-123">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet.</span></span> <span data-ttu-id="53561-124">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-124">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="53561-125">정책을 할당하는 것은 매우 간단합니다. 단순히 사용자의 ID와 할당할 정책의 이름을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53561-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="53561-126">또한 정책 및 정책 할당과 관련되어 사용자 계정 작업을 한 번만 수행하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-126">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="53561-127">페더레이션 파트너 및 Windows Live 사용자와 통신할 수 있는 모든 사용자의 목록이 필요한 경우를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-127">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="53561-128">여기서 해당 사용자에게는 외부 사용자 액세스 정책 FederationAndPICDefault가 이미 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-128">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="53561-129">따라서 하나의 간단한 명령을 실행하여 모든 사용자 목록을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-129">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="53561-130">해당 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-130">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="53561-131">이처럼 ExternalAccessPolicy 속성이 FederationAndPICDefault로 설정된 모든 사용자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="53561-131">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="53561-132">화면에 나타나는 정보의 양을 제한하기 위해 Select-Object cmdlet을 사용하여 각 사용자의 표시 이름만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-132">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="53561-133">모든 사용자 계정이 동일한 정책을 사용하도록 구성하기 위해 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="53561-134">이 명령은 Get-CsOnlineUser 사용하여 Lync를 사용하도록 설정된 모든 사용자 컬렉션을 반환한 다음 해당 모든 정보를 Grant-CsExternalAccessPolicy에 전송하여 컬렉션의 모든 사용자에게 FederationAndPICDefault 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="53561-135">추가 예로 이전에 FederationAndPICDefault 정책에 Alex를 할당했다가 이제 글로벌 외부 액세스 정책을 통해 Alex를 관리하고자 했던 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="53561-136">전역 정책은 명시적으로 누구에게도 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="53561-137">대신 해당 사용자에게 사용자당 정책이 할당되지 않은 경우 지정된 사용자에 대해 글로벌 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="53561-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="53561-138">따라서 글로벌 정책에 의해 Alex를 관리하려면 이전에 할당된 사용자 정책의 할당을 해지해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="53561-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="53561-139">예제 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="53561-140">이 명령은 Alex에게 할당된 외부 액세스 정책의 이름을 null 값($Null)으로 $Null.</span><span class="sxs-lookup"><span data-stu-id="53561-140">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="53561-141">Null은 "nothing"을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-141">Null means "nothing".</span></span> <span data-ttu-id="53561-142">즉, Alex에게 외부 액세스 정책이 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-142">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="53561-143">사용자에게 외부 액세스 정책이 할당되지 않은 경우 해당 사용자는 전역 정책에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="53561-143">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="53561-144">많은 수의 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="53561-144">Managing large numbers of users</span></span>

<span data-ttu-id="53561-145">많은 수의 사용자(1,000명 이상)를 관리하려면 [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet을 사용하여 스크립트 블록을 통해 명령을 일괄 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>  <span data-ttu-id="53561-146">이전 예제에서는 cmdlet이 실행될 때마다 호출을 설정한 다음 결과를 다시 보내기 전에 대기해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="53561-147">스크립트 블록을 사용하는 경우 cmdlet을 원격으로 실행할 수 있으며 완료되면 데이터를 다시 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53561-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span>

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="53561-148">이 경우 클라이언트 정책이 없는 사용자는 한에 500명까지 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="53561-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="53561-149">클라이언트 정책 "ClientPolicyNoIMURL" 및 외부 액세스 정책 "FederationAndPicDefault"를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="53561-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="53561-150">결과는 50개 그룹으로 일괄 처리된 다음 각 일괄 처리 50개가 원격 컴퓨터로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="53561-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53561-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53561-151">See also</span></span>

[<span data-ttu-id="53561-152">PowerShell을 통해 비즈니스용 Skype Oline 관리</span><span class="sxs-lookup"><span data-stu-id="53561-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="53561-153">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="53561-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="53561-154">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="53561-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)