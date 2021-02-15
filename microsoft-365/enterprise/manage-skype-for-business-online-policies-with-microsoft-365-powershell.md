---
title: PowerShell을 사용하여 온라인 비즈니스 정책용 Skype 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: '요약: PowerShell을 사용하여 정책을 사용하여 비즈니스용 Skype Online 사용자 계정 속성을 관리합니다.'
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477044"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="abb83-103">PowerShell을 사용하여 온라인 비즈니스 정책용 Skype 관리</span><span class="sxs-lookup"><span data-stu-id="abb83-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="abb83-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="abb83-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="abb83-105">비즈니스용 Skype Online에 대한 사용자 계정의 여러 속성을 관리하려면 Microsoft 365용 PowerShell을 사용하여 정책의 속성으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="abb83-106">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="abb83-106">Before you begin</span></span>

<span data-ttu-id="abb83-107">다음 지침을 사용하여 명령을 실행하기 위한 설정(이미 완료한 단계 건너뛰기)을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="abb83-108">Skype for Business Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="abb83-109">최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="abb83-110">Teams [PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="abb83-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="abb83-111">Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   <span data-ttu-id="abb83-112">메시지가 표시될 때 비즈니스용 Skype Online 관리자 계정 이름과 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="abb83-113">사용자 계정 정책 관리</span><span class="sxs-lookup"><span data-stu-id="abb83-113">Manage user account policies</span></span>

<span data-ttu-id="abb83-114">많은 비즈니스용 Skype Online 사용자 계정 속성은 정책을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="abb83-115">정책은 단순히 한 개 이상의 사용자에게 적용할 수 있는 설정 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="abb83-116">정책이 구성된 방법을 살펴보기 위해 FederationAndPICDefault 정책에 대해 다음 예제 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="abb83-117">그러면 다음을 통해 다시 돌아와야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="abb83-118">이 예에서 이 정책 내의 값은 페더링 사용자와 통신할 때 사용할 수 있는 작업을 결정하거나 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="abb83-119">예를 들어 사용자가 조직 외부의 사용자와 통신할 수 있도록 EnableOutsideAccess 속성을 True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="abb83-120">이 속성은 Microsoft 365 관리 센터에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="abb83-121">대신 선택한 다른 선택에 따라 속성이 자동으로 True 또는 False로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="abb83-122">관심 있는 다른 두 속성은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="abb83-123">**EnableFederationAccess는** 사용자가 페더전된 도메인의 사용자와 통신할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="abb83-124">**EnablePublicCloudAccess는** 사용자가 사용자와 통신할 수 있는지 여부를 Windows Live 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="abb83-125">따라서 사용자 계정(예: **Set-CsUser -EnableFederationAccess 또는 Set-CsUser -EnableFederationAccess)**$True.</span><span class="sxs-lookup"><span data-stu-id="abb83-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="abb83-126">대신 원하는 속성 값이 미리 구성된 외부 액세스 정책을 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="abb83-127">사용자가 페더인 사용자 및 Windows Live 사용자와 통신할 수 있게 하려는 경우 해당 사용자 계정에 이러한 유형의 통신을 허용하는 정책이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="abb83-128">조직 외부의 사용자와 통신할 수 있는지 여부를 확인하려는 경우 다음을해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="abb83-129">해당 사용자에게 할당된 외부 액세스 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="abb83-130">해당 정책에서 허용되거나 허용되지 않는 기능을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="abb83-131">예를 들어 다음 명령을 사용하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="abb83-132">이 명령은 사용자에게 할당된 정책을 찾은 다음 해당 정책 내에서 활성화되거나 사용하지 않도록 설정된 기능을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="abb83-133">PowerShell을 사용하여 비즈니스용 Skype Online 정책을 관리하기 위해 다음에 대한 cmdlet을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abb83-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="abb83-134">[클라이언트 정책](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="abb83-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="abb83-135">[회의 정책](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="abb83-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="abb83-136">[모바일 정책](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="abb83-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="abb83-137">[온라인 음성메일 정책](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="abb83-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="abb83-138">[음성 라우팅 정책](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="abb83-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="abb83-139">비즈니스용 Skype Online 다이얼 플랜은 이름을 제외한 모든 측면에서 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="abb83-140">Office Communications Server 및 Exchange와의 호환성을 제공하기 위해 "전화 걸기 정책" 대신 "다이얼 플랜"을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="abb83-141">예를 들어 사용 가능한 모든 음성 정책을 확인한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="abb83-142">이 경우 사용 가능한 모든 음성 정책의 목록이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="abb83-143">그러나 일부 정책은 모든 사용자에게 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="abb83-144">이는 라이선싱 및 지리적 위치와 관련된 다양한 제한 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="abb83-145">(소위["사용](https://msdn.microsoft.com/library/azure/dn194136.aspx)위치") 특정 사용자에게 할당할 수 있는 외부 액세스 정책 및 회의 정책을 알고 싶은 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-145">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="abb83-146">ApplicableTo 매개 변수는 반환되는 데이터를 지정된 사용자에게 할당할 수 있는 정책(예: Alex Darrow)으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-146">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow).</span></span> <span data-ttu-id="abb83-147">라이선스 및 사용 위치 제한에 따라 사용 가능한 모든 정책의 하위 집합을 나타내는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-147">Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="abb83-148">경우에 따라 정책 속성은 Microsoft 365에서 사용되지 않는 반면 다른 정책 속성은 Microsoft 지원 담당자만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="abb83-149">비즈니스용 Skype Online에서는 일종의 정책을 통해 사용자를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="abb83-150">유효한 정책 관련 속성이 비어 있는 경우 이는 해당 사용자가 사용자 지정 정책을 특별히 할당하지 않는 한 사용자에게 자동으로 적용되는 정책인 글로벌 정책에 의해 관리되고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="abb83-151">사용자 계정에 대한 클라이언트 정책이 나열되지 않는 경우 전역 정책에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="abb83-152">다음 명령을 사용하여 전역 클라이언트 정책을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb83-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="abb83-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abb83-153">See also</span></span>

[<span data-ttu-id="abb83-154">PowerShell을 통해 비즈니스용 Skype Oline 관리</span><span class="sxs-lookup"><span data-stu-id="abb83-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="abb83-155">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="abb83-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="abb83-156">Microsoft 365 용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="abb83-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

