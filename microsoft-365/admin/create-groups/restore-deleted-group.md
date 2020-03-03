---
title: 삭제된 Office 365 그룹 복원
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Exchange 관리 센터를 사용 하 여 삭제 된 Office 365 그룹을 복원 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352439"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="0c73e-103">삭제된 Office 365 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="0c73e-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="0c73e-104">Office 365 그룹의 소유자 인 경우 다음 단계를 수행 하 여 직접 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="0c73e-105">삭제 된 [그룹 페이지](https://outlook.office.com/people/group/deleted)에서 **그룹** 노드 아래의 **그룹 관리** 옵션을 선택한 다음 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="0c73e-106">복원 하려는 그룹 옆에 있는 **복원** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="0c73e-107">삭제 된 그룹이 여기에 표시 되지 않으면 관리자에 게 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c73e-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="0c73e-108">Office 365 그룹을 복원 하려는 사용자 인 경우 관리자에 게 이러한 단계를 수행 하도록 요청 하거나 지원 센터에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c73e-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="0c73e-109">그룹을 삭제 한 경우에는 기본적으로 30 일간 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="0c73e-110">이 30 일의 기간은 여전히 그룹을 복원할 수 있기 때문에 "일시 삭제"로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="0c73e-111">30 일이 지나면 그룹 및 관련 내용이 영구적으로 삭제 되며 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="0c73e-112">"일시 삭제" 기간 동안 사용자가 사이트에 액세스 하려고 하면 404 _금지_ 된 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="0c73e-113">이 기간 후 사용자가 사이트에 액세스 하려고 하면 404 _찾을 수 없음_ 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="0c73e-114">그룹이 복원되면 다음 콘텐츠가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="0c73e-115">Azure AD (Active Directory) Office 365 그룹 개체, 속성 및 구성원</span><span class="sxs-lookup"><span data-stu-id="0c73e-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="0c73e-116">그룹의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="0c73e-117">Exchange Online 공유 받은 편지함 및 일정</span><span class="sxs-lookup"><span data-stu-id="0c73e-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="0c73e-118">SharePoint Online 팀 사이트 및 파일</span><span class="sxs-lookup"><span data-stu-id="0c73e-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="0c73e-119">OneNote 전자 필기장</span><span class="sxs-lookup"><span data-stu-id="0c73e-119">OneNote notebook</span></span>
    
- <span data-ttu-id="0c73e-120">Planner</span><span class="sxs-lookup"><span data-stu-id="0c73e-120">Planner</span></span>
    
- <span data-ttu-id="0c73e-121">Teams</span><span class="sxs-lookup"><span data-stu-id="0c73e-121">Teams</span></span>

- <span data-ttu-id="0c73e-122">Yammer 그룹 및 그룹 콘텐츠 (Yammer에서 Office 365 그룹을 만든 경우)</span><span class="sxs-lookup"><span data-stu-id="0c73e-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="0c73e-123">콘텐츠가 영구적으로 삭제되도록 보존 기간 30일을 기다릴 수 없는 경우 [Office 365그룹 영구적으로 삭제](#permanently-delete-an-office-365-group)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="0c73e-124">삭제 된 Office 365 그룹의 소유자도 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="0c73e-125">관리자 권한 없이 소유자 권한을 사용 하 여 office 365 그룹을 복원 하려면 [PowerShell을 사용 하 여 office 365 그룹 복원을](#restore-an-office-365-group-using-powershell)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c73e-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="0c73e-126">Exchange 관리 센터를 사용하여 Office 365 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="0c73e-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="0c73e-127">Office 365 전역 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="0c73e-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="0c73e-129">Exchange 관리 센터에서 **받는 사람**을 선택한 다음 **그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="0c73e-130">그룹이 활성 상태 인지 일시 삭제 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="0c73e-131">그룹이 영구적으로 삭제된 경우에는 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="0c73e-132">그룹이 일시 삭제 된 정확한 시간을 보려면 그룹을 선택 하 고 오른쪽 창에서 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="0c73e-133">복원할 그룹을 선택한 다음 복원 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![복원할 그룹을 선택한 다음 복원 아이콘을 선택 합니다.](../../media/restore-group.png)
  
5. <span data-ttu-id="0c73e-135">새로 고침 선택</span><span class="sxs-lookup"><span data-stu-id="0c73e-135">Select refresh</span></span> ![새로 고침 아이콘](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="0c73e-137">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-137">to update the information on the page.</span></span> <span data-ttu-id="0c73e-138">그룹이 활성으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-138">Your group will show as Active.</span></span> <span data-ttu-id="0c73e-139">그룹과 연결 된 양식 및 양식 데이터도 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="0c73e-140">PowerShell을 사용하여 Office 365그룹 복원</span><span class="sxs-lookup"><span data-stu-id="0c73e-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="0c73e-141">Office 365 전역 관리자 권한이 있거나 삭제 된 Office 365 그룹의 이전 소유자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c73e-142">PowerShell에서 Remove-msolgroup을 사용 하 여 그룹을 삭제 하는 경우 그룹이 영구적으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="0c73e-143">PowerShell을 사용하여 그룹을 삭제하는 경우 **Remove-AzureADMSGroup**을 사용하여 Office 365 그룹을 일시 삭제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="0c73e-144">이렇게 해야 필요한 경우 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="0c73e-145">Azure Active Directory PowerShell for Graph의 미리 보기 버전 설치</span><span class="sxs-lookup"><span data-stu-id="0c73e-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c73e-146">같은 컴퓨터에 preview와 GA 버전을 동시에 모두 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="0c73e-147">최상의 방법으로는 이전 AzureADPreview 또는 이전 AzureAD 버전을 제거 하 여 *항상* 최신 상태로 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="0c73e-148">검색 창에 Windows PowerShell을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="0c73e-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span><span class="sxs-lookup"><span data-stu-id="0c73e-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="0c73e-150">설치 된 모듈을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="0c73e-151">이전 버전의 AzureADPreview 또는 AzureAD를 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="0c73e-152">또는</span><span class="sxs-lookup"><span data-stu-id="0c73e-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="0c73e-153">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="0c73e-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="0c73e-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="0c73e-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="0c73e-155">삭제된 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="0c73e-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="0c73e-156">Previoius 섹션의 "Windows PowerShell 용 Azure Active Directory 모듈의 preview 버전 설치"에 설명 된 대로 **AzureADPreview** 모듈을 설치 했습니까?</span><span class="sxs-lookup"><span data-stu-id="0c73e-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="0c73e-157">위 단계가 작동하지 않는 가장 흔한 이유는 바로 최신 버전의 **미리 보기** 가 설치되어 있지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="0c73e-158">컴퓨터에서 Windows PowerShell 창을 엽니다(일반적인 Windows PowerShell 창이든 **관리자 권한으로 실행**을 선택하여 연 창이든 관계없습니다).</span><span class="sxs-lookup"><span data-stu-id="0c73e-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="0c73e-159">다음 명령을 실행 하 여 각 명령 다음에 **enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="0c73e-160">열리는 **계정에 로그인** 화면에서 관리자 계정 사용자 이름 및 암호를 입력 하 여 Azure AD 서비스에 연결 하 고 **로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="0c73e-161">다음 명령을 실행 하 여 조직의 일시 삭제 된 모든 Office 365 그룹을 30 일 동안 계속 해 서 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="0c73e-162">복원하려는 그룹(하나 또는 여러 개)의 개체 ID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="0c73e-163">이 목록에 찾으려는 그룹이 표시 되지 않으면 해당 그룹은 이미 영구적으로 제거 된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0c73e-164">삭제된 그룹과 같은 별칭 또는 SMTP 주소로 새 그룹이 만들어진 경우 삭제된 그룹을 복원할 수 있으려면 먼저 해당 새 그룹을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="0c73e-165">해당 그룹을 복원 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="0c73e-166">일반적으로이 프로세스는 몇 분 정도 걸리지만 몇 가지 드문 경우에도 완전히 복원 하는 데 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="0c73e-167">그룹이 복원되었는지 확인하려면 PowerShell에서 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="0c73e-p110">복원이 완료되고 나면 그룹이 Outlook 및 웹용 Outlook의 탐색 창에 다시 나타나야 합니다. 그룹 구성원이 SharePoint 및 Planner를 비롯한 복원된 모든 콘텐츠를 다시 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="0c73e-170">Office 365그룹 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="0c73e-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="0c73e-171">경우에 따라 30 일 일시 삭제 기간이 만료 될 때까지 기다리지 않고 그룹을 영구적으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="0c73e-172">이렇게 하려면 PowerShell을 시작하고 이 명령을 실행하여 그룹의 개체 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="0c73e-173">영구적으로 삭제 하려는 그룹 (또는 그룹)의 개체 ID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0c73e-174">그룹을 제거하면 그룹 및 해당 데이터가 영구적으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="0c73e-175">그룹을 제거하려면 PowerShell에서 이 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="0c73e-p112">그룹이 제거되었는지 확인하려면  *Get-AzureADMSDeletedGroup*  cmdlet을 다시 실행하여 그룹이 소프트 삭제된 그룹 목록에 더 이상 나타나지 않는지 확인합니다. 일부 경우 그룹 및 모든 해당 데이터가 영구적으로 삭제되는 데 24시간이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c73e-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="0c73e-178">Office 365 그룹에 대한 질문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="0c73e-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="0c73e-179">[Microsoft 기술 커뮤니티](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 를 방문 하 여 질문을 게시 하 고 Office 365 그룹에 대 한 대화에 참여 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c73e-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="0c73e-180">관련 문서</span><span class="sxs-lookup"><span data-stu-id="0c73e-180">Related articles</span></span>

[<span data-ttu-id="0c73e-181">PowerShell을 사용하여 Office 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="0c73e-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="0c73e-182">Remove-UnifiedGroup cmdlet을 사용하여 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="0c73e-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="0c73e-183">그룹에 연결된 팀 사이트 설정 관리</span><span class="sxs-lookup"><span data-stu-id="0c73e-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="0c73e-184">Outlook에서 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="0c73e-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
