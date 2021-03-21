---
title: '디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: .local 도메인) 준비'
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
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Microsoft 365 테넌트와 동기화하기 전에 라우팅할 수 없는 도메인이 사내 사용자 계정과 연결되어 있는 경우 어떻게 해야 할지 알아보고,
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927399"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="3e8d2-103">디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: .local 도메인) 준비</span><span class="sxs-lookup"><span data-stu-id="3e8d2-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="3e8d2-104">Microsoft 365와 사내 디렉터리를 동기화하는 경우 Azure AD(Azure Active Directory)에 확인된 도메인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3e8d2-105">사내 AD DS(Active Directory 도메인 서비스) 도메인과 연결된 UPNS(사용자 계정 이름)만 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="3e8d2-106">그러나 ".local"(예: billa@contoso.local)와 같은 라우팅할 수 없는 도메인을 포함하는 UPN은 .onmicrosoft.com 도메인(예: billa@contoso.onmicrosoft.com)에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="3e8d2-107">AD DS에서 사용자 계정에 대해 현재 ".local" 도메인을 사용하는 경우 Microsoft 365 도메인과 제대로 동기화하려면 확인된 도메인(예: billa@contoso.com)을 사용하도록 도메인을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="3e8d2-108">".local" 도메인만 있는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="3e8d2-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="3e8d2-109">Azure AD Connect를 사용하여 AD DS를 Microsoft 365 테넌트의 Azure AD 테넌트와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="3e8d2-110">자세한 내용은 [Azure AD에 On-premises ID 통합을 참조하세요.](/azure/architecture/reference-architectures/identity/azure-ad)</span><span class="sxs-lookup"><span data-stu-id="3e8d2-110">For more information, see [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="3e8d2-111">Azure AD Connect는 사용자의 UPN 및 암호를 동기화하여 사용자가 사내에서 사용하는 자격 증명과 동일한 자격 증명으로 로그인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="3e8d2-112">그러나 Azure AD Connect는 사용자를 Microsoft 365에서 확인한 도메인과만 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="3e8d2-113">즉, Microsoft 365 ID는 Azure AD에서 관리하기 때문에 도메인도 Azure AD에서 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="3e8d2-114">즉, 도메인은 유효한 인터넷 도메인(예: .com, .org, .net, .us)으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="3e8d2-115">내부 AD DS에서 라우팅할 수 없는 도메인(예: ".local")만 사용하는 경우 Microsoft 365 테넌트에 대해 확인된 도메인과 일치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="3e8d2-116">온-프레미스 AD DS에서 기본 도메인을 변경하거나 하나 이상의 UPN 접미사를 추가하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="3e8d2-117">기본 도메인 변경</span><span class="sxs-lookup"><span data-stu-id="3e8d2-117">Change your primary domain</span></span>

<span data-ttu-id="3e8d2-118">Microsoft 365에서 확인한 도메인으로 기본 도메인을 변경합니다(예: contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="3e8d2-119">그런 다음 contoso.local 도메인이 있는 모든 사용자가 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="3e8d2-120">그러나 이 프로세스는 매우 관련이 있으며, 다음 섹션에서는 보다 쉬운 해결 방법도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="3e8d2-121">UPN 접미사 추가 및 사용자 업데이트</span><span class="sxs-lookup"><span data-stu-id="3e8d2-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="3e8d2-122">AD DS에 새 UPN 접미사 또는 접미사를 Microsoft 365에서 확인한 도메인과 일치하게 등록하면 ".local" 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="3e8d2-123">예를 들어 새 접미사 등록 후 사용자 계정이 새 도메인 이름으로 대체하도록 사용자 UPNS를 업데이트하여 사용자 계정이 billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="3e8d2-124">확인된 도메인을 사용하기 위해 UPNS를 업데이트한 후, Microsoft 365와 사내 AD DS를 동기화할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="3e8d2-125">1단계: 새 UPN 접미사 추가\*\*</span><span class="sxs-lookup"><span data-stu-id="3e8d2-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="3e8d2-126">AD DS 도메인 컨트롤러의 서버 관리자에서 **도구** \> **Active Directory 도메인 및 트러스트 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="3e8d2-127">**또는 사용자가 없는 경우 Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="3e8d2-128">**Windows 키 + R을 눌러** 실행 대화 상자를 **연** 다음 Domain.msc에 입력한 다음 확인 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Active Directory 도메인 및 트러스트를 선택하십시오.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="3e8d2-130">Active **Directory 도메인 및 트러스트** 창에서 Active Directory 도메인 및 **트러스트** 를 마우스 오른쪽 단추로 클릭한 다음 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Active Directory 도메인 및 트러스트를 마우스 오른쪽 단추로 클릭하고 속성을 선택](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="3e8d2-132">**UPN 접미사** 탭의 대체 **UPN** 접미사 상자에 새 UPN 접미사 또는 접미사를  입력한 다음 적용 추가를 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![새 UPN 접미사 추가](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="3e8d2-134">**접미사** 추가가 완료되면 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="3e8d2-135">2단계: 기존 사용자의 UPN 접미사 변경</span><span class="sxs-lookup"><span data-stu-id="3e8d2-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="3e8d2-136">AD DS 도메인 컨트롤러의 서버 관리자에서 **도구** Active Directory 사용자 및 \> **컴퓨터를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="3e8d2-137">**또는 사용자가 없는 경우 Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="3e8d2-138">**Windows 키 + R을** 눌러 실행 대화 상자를 **연** 다음 Dsa.msc에 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="3e8d2-139">사용자를 선택하고 마우스 오른쪽 단추로 클릭한 다음 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="3e8d2-140">계정 **탭의** UPN 접미사 드롭다운 목록에서 새 UPN 접미사, 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e8d2-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![사용자에 대한 새 UPN 접미사 추가](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="3e8d2-142">모든 사용자에 대해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="3e8d2-143">PowerShell을 사용하여 모든 사용자의 UPN 접미사 변경</span><span class="sxs-lookup"><span data-stu-id="3e8d2-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="3e8d2-144">업데이트할 사용자 계정이 많은 경우 PowerShell을 사용하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="3e8d2-145">다음 예제에서는 [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) 및 [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) cmdlet을 사용하여 모든 contoso.local 접미사는 AD DS에서 contoso.com 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-145">The following example uses the cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) and [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="3e8d2-146">예를 들어 다음 PowerShell 명령을 실행하여 모든 contoso.local 접미사를 업데이트하여 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="3e8d2-147">AD [DS에서](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) Windows PowerShell 자세한 내용은 Active Directory Windows PowerShell 모듈을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e8d2-147">See [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) to learn more about using Windows PowerShell in AD DS.</span></span>