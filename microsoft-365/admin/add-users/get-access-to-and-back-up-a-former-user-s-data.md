---
title: 액세스 권한 받기 및 이전 사용자 데이터 백업
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: 사용자가 조직을 떠날 때 직원의 파일 및 전자 메일을 보존 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 11c946e5c242b05fea3a15b9427f36029c61082f
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142566"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="ed438-103">액세스 권한 받기 및 이전 사용자 데이터 백업</span><span class="sxs-lookup"><span data-stu-id="ed438-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="ed438-104">직원이 조직을 떠나는 경우 해당 데이터 (문서 및 전자 메일)에 액세스 하 고, 검토 하거나, 새 직원에 게 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="ed438-105">이전 사용자의 OneDrive 문서 액세스</span><span class="sxs-lookup"><span data-stu-id="ed438-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="ed438-106">사용자의 라이선스를 제거 하지만 계정을 삭제 하지 않으면 사용자의 OneDrive에 있는 콘텐츠에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="ed438-107">사용자 계정을 삭제 하면 기본적으로 30 일이 지나면 이전 사용자의 OneDrive 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-107">If you delete the user's account, you have 30 days by default to access the former user’s OneDrive data.</span></span> <span data-ttu-id="ed438-108">[삭제 된 사용자에 대 한 OneDrive 보존을 설정 하는 방법을 알아봅니다](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="ed438-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="ed438-109">이 시간 내에 [사용자 계정을 복원](/office365/admin/add-users/restore-user) 하지 않으면 OneDrive 콘텐츠가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="ed438-110">이전 사용자의 OneDrive 파일을 보존 하려면 먼저 자신에 게 OneDrive에 대 한 액세스 권한을 부여 하 고 보관할 파일을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ed438-111">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="ed438-112">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="ed438-113">사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-113">Select a user.</span></span>

3. <span data-ttu-id="ed438-114">오른쪽 창에서 **OneDrive**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-114">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="ed438-115">**파일에 대 한 액세스 권한**에서 **파일에 대 한 링크 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-115">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="ed438-116">링크를 선택 하 여 파일 위치를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-116">Select the link to open the file location.</span></span> <span data-ttu-id="ed438-117">파일을 컴퓨터에 다운로드 하거나, **이동** 하거나 **복사** 를 선택 하 여 자신의 OneDrive 또는 공유 라이브러리로 이동 하거나 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-117">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="ed438-118">파일 및 폴더를 한 번에 최대 500 MB까지 이동 하거나 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-118">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="ed438-119">버전 기록이 포함 된 문서를 이동 하거나 복사 하는 경우 최신 버전만 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-119">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ed438-120">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ed438-121">사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-121">Select a user.</span></span>

3. <span data-ttu-id="ed438-122">오른쪽 창에서 **OneDrive 설정을**확장 하 고 **액세스**옆에 있는 **파일 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-122">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="ed438-123">링크를 선택 하 여 파일 위치를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-123">Select the link to open the file location.</span></span> <span data-ttu-id="ed438-124">파일을 컴퓨터에 다운로드 하거나, **이동** 하거나 **복사** 를 선택 하 여 자신의 OneDrive 또는 공유 라이브러리로 이동 하거나 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-124">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="ed438-125">파일 및 폴더를 한 번에 최대 500 MB까지 이동 하거나 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-125">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="ed438-126">버전 기록이 포함 된 문서를 이동 하거나 복사 하는 경우 최신 버전만 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-126">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ed438-127">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="ed438-128">사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-128">Select a user.</span></span>

3. <span data-ttu-id="ed438-129">오른쪽 창에서 **OneDrive 설정을**확장 하 고 **액세스**옆에 있는 **파일 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-129">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="ed438-130">링크를 선택 하 여 파일 위치를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-130">Select the link to open the file location.</span></span> <span data-ttu-id="ed438-131">파일을 컴퓨터에 다운로드 하거나, **이동** 하거나 **복사** 를 선택 하 여 자신의 OneDrive 또는 공유 라이브러리로 이동 하거나 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-131">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="ed438-132">파일 및 폴더를 한 번에 최대 500 MB까지 이동 하거나 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-132">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="ed438-133">버전 기록이 포함 된 문서를 이동 하거나 복사 하는 경우 최신 버전만 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-133">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="ed438-134">사용자의 OneDrive에 대 한 관리자 액세스 권한 해지</span><span class="sxs-lookup"><span data-stu-id="ed438-134">Revoke admin access to a user’s OneDrive</span></span>

<span data-ttu-id="ed438-135">전역 관리자는 자신에 게 사용자의 OneDrive에 있는 콘텐츠에 대 한 액세스 권한을 부여할 수 있지만 더 이상 필요 하지 않은 경우에는 액세스 권한을 제거 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-135">As global admin, you can give yourself access to the content in a user’s OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ed438-136">전역 관리자 또는 SharePoint 관리자로 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a> 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-136">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="ed438-137">관리 센터에 액세스할 수 있는 권한이 없다는 메시지가 표시 되 면 조직에서 관리자 권한이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-137">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ed438-138">전역 관리자 또는 SharePoint 관리자로 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">관리 센터</a> 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="ed438-139">관리 센터에 액세스할 수 있는 권한이 없다는 메시지가 표시 되 면 조직에서 관리자 권한이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ed438-140">전역 관리자 또는 SharePoint 관리자로 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">관리 센터</a> 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="ed438-141">관리 센터에 액세스할 수 있는 권한이 없다는 메시지가 표시 되 면 조직에서 관리자 권한이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="ed438-142">왼쪽 창에서 **관리 센터** \> **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-142">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="ed438-143">(관리 센터의 목록을 보려면 **모두 표시**를 선택해야 할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="ed438-143">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="ed438-144">기존 SharePoint 관리 센터가 나타나는 경우 페이지 위쪽에 있는 **지금 열기**를 선택하여 새 SharePoint 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-144">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="ed438-145">왼쪽 창에서 **추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-145">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="ed438-146">**사용자 프로필**에서 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-146">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="ed438-147">**사람**에서 **사용자 프로필 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-147">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="ed438-148">사용자 이름을 입력 하 고 **찾기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-148">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="ed438-149">사용자를 마우스 오른쪽 단추로 클릭 한 다음 **사이트 모음 소유자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-149">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="ed438-150">사용자 데이터에 더 이상 액세스할 필요가 없는 사용자를 제거 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-150">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="ed438-151">이전 사용자의 Outlook 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="ed438-151">Access the Outlook data of a former user</span></span>

<span data-ttu-id="ed438-152">이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처를 저장 하려면 해당 정보를 Outlook 데이터 파일 (.pst)로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-152">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="ed438-153">Outlook에 [이전 직원의 전자 메일을 추가](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) 합니다 ( [사용자 암호를 다시 설정 하는](reset-passwords.md)경우에만 알고 있는 항목으로 설정할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="ed438-153">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="ed438-154">Outlook에서 **파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-154">In Outlook, select **File**.</span></span>
    
    ![리본 메뉴의 모양은 Outlook 2016에서 확인할 수 있습니다.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="ed438-156">내보내기 \> **가져오기/내보내기** \*\*열기 &amp; \*\* 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-156">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Backstage 보기의 가져오기/내보내기 명령](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="ed438-158">**파일로 내보내기를**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-158">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![가져오기/내보내기 마법사에서 파일로 내보내기 옵션](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="ed438-160">**Outlook 데이터 파일 (.pst)** 을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-160">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="ed438-161">이름 또는 전자 메일 주소 (예: 사서함-유가을 Weiler 또는 anne@contoso.com)를 선택 하 여 내보내려는 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-161">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="ed438-162">메일, 일정, 연락처, 작업 및 메모를 포함 하 여 계정의 모든 내용을 내보내려면 **하위 폴더 포함** 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-162">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ed438-163">한 번에 하나의 계정만 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-163">You can export one account at a time.</span></span> <span data-ttu-id="ed438-164">여러 계정을 내보내려는 경우 하나의 계정을 내보낸 후에는 이러한 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-164">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![폴더를 선택 하 고 하위 폴더를 포함 하는 Outlook 데이터 파일 내보내기 대화 상자](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="ed438-166">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-166">Select **Next**.</span></span>
    
8. <span data-ttu-id="ed438-167">**찾아보기를** 선택 하 여 Outlook 데이터 파일 (.pst)을 저장할 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-167">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="ed438-168">*파일 이름을*입력 한 다음 **확인** 을 선택 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-168">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ed438-169">이전에 export를 사용한 적이 있는 경우에는 위의 폴더 위치와 파일 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-169">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="ed438-170">**확인**을 선택 하기 전에 *다른 파일 이름을* 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-170">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="ed438-171">기존 Outlook 데이터 파일(.pst)로 내보내는 경우 **옵션**에서 파일에 이미 있는 항목을 내보낼 때 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-171">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="ed438-172">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="ed438-172">Select **Finish**.</span></span>
    
<span data-ttu-id="ed438-173">새 Outlook 데이터 파일 (.pst)을 만들거나 암호로 보호 된 파일을 사용 하는 경우가 아니면 outlook이 즉시 내보내기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-173">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="ed438-174">Outlook 데이터 파일 (.pst)을 만드는 경우 선택적 암호를 통해 파일을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-174">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="ed438-175">**Outlook 데이터 파일 만들기** 대화 상자가 나타나면 암호 및 **암호 확인** 상자에 *암호* 를 입력 **하 고** **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-175">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="ed438-176">**Outlook 데이터 파일 암호** 대화 상자에서 *암호*를 입력 한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-176">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="ed438-177">암호로 보호 되는 기존 Outlook 데이터 파일 (.pst)로 내보내는 경우 **Outlook 데이터 파일 암호** 대화 상자에 *암호*를 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-177">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="ed438-178">Outlook 2010에서 [전자 메일, 연락처 및 일정을 outlook .pst 파일로 내보내거나 백업](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed438-178">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="ed438-179">기본적으로 12 개월 동안 전자 메일을 오프 라인으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-179">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="ed438-180">필요한 경우 [오프 라인에서 사용할 수 있는 데이터를 늘리는](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed438-180">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="ed438-181">다른 사용자에 게 이전 사용자의 전자 메일에 대 한 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="ed438-181">Give another user access to a former user's email</span></span> 

<span data-ttu-id="ed438-182">다른 직원에 게 이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처에 대 한 액세스 권한을 부여 하려면 해당 정보를 다른 직원의 Outlook 받은 편지 함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-182">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="ed438-183">또한 [이전 사용자의 사서함을 공유 사서함으로 변환](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) 하거나 [이전 직원의 전자 메일을 다른 직원에 게 전달할](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-183">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="ed438-184">Outlook에서 **가져오기/내보내기** \*\* &amp; 내보내기\*\* \> **파일로** \> 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-184">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="ed438-185">그러면 가져오기 및 내보내기 마법사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-185">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="ed438-186">**다른 프로그램 또는 파일에서 가져오기를**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-186">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![가져오기 및 내보내기 마법사](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="ed438-188">**Outlook 데이터 파일 (.pst)** 을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-188">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="ed438-189">가져올 .pst 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-189">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="ed438-190">**옵션**에서 중복 항목을 처리할 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-190">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="ed438-191">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-191">Select **Next**.</span></span>
    
7. <span data-ttu-id="ed438-192">암호를 Outlook 데이터 파일 (.pst)에 할당 한 경우 암호를 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-192">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="ed438-193">항목 가져오기에 대 한 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-193">Set the options for importing items.</span></span> <span data-ttu-id="ed438-194">기본 설정은 대개 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-194">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="ed438-195">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="ed438-195">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="ed438-196">이 단계는 기존 사용자의 OneDrive 및 전자 메일 데이터에 액세스 하는 경우에도 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-196">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="ed438-197">Outlook 데이터 파일 (.pst)에서 항목을 몇 개 가져오거나 복원 하려는 경우 Outlook 데이터 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-197">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="ed438-198">그런 다음 탐색 창에서 Outlook 데이터 파일 폴더의 항목을 기존 Outlook 폴더로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ed438-198">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="ed438-199">관련 문서</span><span class="sxs-lookup"><span data-stu-id="ed438-199">Related articles</span></span>
[<span data-ttu-id="ed438-200">Office 365에서 이전 직원 제거</span><span class="sxs-lookup"><span data-stu-id="ed438-200">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="ed438-201">OneDrive 계정에서 관리자 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="ed438-201">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="ed438-202">삭제 된 OneDrive 복원</span><span class="sxs-lookup"><span data-stu-id="ed438-202">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="ed438-203">OneDrive 보존 및 삭제</span><span class="sxs-lookup"><span data-stu-id="ed438-203">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
