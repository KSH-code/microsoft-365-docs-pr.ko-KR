---
title: 액세스 권한 받기 및 이전 사용자 데이터 백업
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: 직원이 조직을 떠날 때 직원의 파일 및 전자 메일을 보존하는 방법을 배워야 합니다.
ms.openlocfilehash: 17911e4a4551bba07d2c2ad034941bba737dcc1d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759993"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="3997d-103">액세스 권한 받기 및 이전 사용자 데이터 백업</span><span class="sxs-lookup"><span data-stu-id="3997d-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="3997d-104">직원이 조직을 떠나는 경우 해당 데이터(문서 및 전자 메일)에 액세스하여 해당 데이터를 검토하거나 백업하거나 새 직원에게 제공해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="3997d-105">이전 사용자의 OneDrive 문서 액세스</span><span class="sxs-lookup"><span data-stu-id="3997d-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="3997d-106">사용자의 라이선스를 제거하지만 계정을 삭제하지 않는 경우 사용자 OneDrive의 콘텐츠에 대한 액세스 권한을 직접 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="3997d-107">사용자 계정을 삭제하는 경우 기본적으로 30일 동안 이전 사용자의 OneDrive 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="3997d-108">[삭제된 사용자에 대한 OneDrive 보존을 설정하는 방법을 학습합니다.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="3997d-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="3997d-109">이 시간 내에 [사용자](/office365/admin/add-users/restore-user) 계정을 복원하지 않는 경우 해당 OneDrive 콘텐츠가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="3997d-110">이전 사용자의 OneDrive 파일을 보존하려면 먼저 OneDrive에 대한 액세스 권한을 부여한 다음 유지하려는 파일을 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="3997d-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3997d-111">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="3997d-112">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="3997d-113">관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="3997d-114">사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-114">Select a user.</span></span>

3. <span data-ttu-id="3997d-115">오른쪽 창에서 **OneDrive 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-115">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="3997d-116">파일에 **액세스하려면 아래에서** **파일에 대한 링크 만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-116">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="3997d-117">파일 위치를 열 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-117">Select the link to open the file location.</span></span> <span data-ttu-id="3997d-118">파일을 컴퓨터에 다운로드하거나 이동  또는 복사를 선택하여 파일을 자신의 OneDrive 또는 공유 라이브러리로 이동하거나 복사합니다. </span><span class="sxs-lookup"><span data-stu-id="3997d-118">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="3997d-119">한에 최대 500MB의 파일 및 폴더를 이동하거나 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-119">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="3997d-120">버전 기록이 있는 문서를 이동하거나 복사하면 최신 버전만 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-120">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="3997d-121">사용자의 OneDrive에 대한 관리자 액세스 해지</span><span class="sxs-lookup"><span data-stu-id="3997d-121">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="3997d-122">전역 관리자는 사용자 OneDrive의 콘텐츠에 대한 액세스 권한을 직접 부여할 수 있지만 더 이상 필요하지 않을 때 액세스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-122">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="3997d-123"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-123">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3997d-124"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-124">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3997d-125"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 의 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-125">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="3997d-126">왼쪽 창에서 관리 **센터** \> **SharePoint 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-126">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="3997d-127">(관리 센터의 목록을 보려면 **모두 표시** 를 선택해야 할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="3997d-127">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="3997d-128">클래식 SharePoint 관리 센터가 나타나면 페이지 맨 위에 있는 지금 열기 를 선택하여 SharePoint 관리 센터를 여십시오. </span><span class="sxs-lookup"><span data-stu-id="3997d-128">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="3997d-129">왼쪽 창에서 추가 기능 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-129">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="3997d-130">사용자 **프로필에서** **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-130">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="3997d-131">사용자 **아래에서** 사용자 **프로필 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-131">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="3997d-132">사용자의 이름을 입력하고 찾기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-132">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="3997d-133">사용자를 마우스 오른쪽 단추로 클릭한 다음 사이트 모음 **소유자 관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-133">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="3997d-134">더 이상 사용자 데이터에 액세스할 필요가 없는 사용자를 제거하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-134">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="3997d-135">이전 사용자의 Outlook 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="3997d-135">Access the Outlook data of a former user</span></span>

<span data-ttu-id="3997d-136">이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처를 저장하기 위해 정보를 Outlook 데이터 파일(.pst)로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-136">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="3997d-137">[Outlook에 이전 직원의](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) 전자 메일을 추가합니다(사용자의 암호를 다시 설정하는 경우 알고 있는 것으로만 설정할 수 있습니다.) [](reset-passwords.md)</span><span class="sxs-lookup"><span data-stu-id="3997d-137">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="3997d-138">Outlook에서 파일 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-138">In Outlook, select **File**.</span></span>
    
    ![Outlook 2016의 리본 메뉴 모양입니다.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="3997d-140">내보내기 **&amp; 가져오기/내보내기** \> **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-140">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Backstage 보기의 가져오기/내보내기 명령](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="3997d-142">파일로 **내보내기 를 선택하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-142">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![가져오기 및 내보내기 마법사의 파일로 내보내기 옵션](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="3997d-144">**Outlook 데이터 파일(.pst)을** 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-144">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="3997d-145">사서함 - Anne Weiler 또는 전자 메일 주소와 같은 이름 또는 전자 메일 주소를 선택하여 내보낼 계정을 anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3997d-145">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="3997d-146">메일, 일정, 연락처, 작업 및 메모를 포함하여 계정의 모든 것을 내보내는 경우 하위폴더 포함 **확인란이** 선택되어 있는지 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-146">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3997d-147">한 번씩 하나의 계정을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-147">You can export one account at a time.</span></span> <span data-ttu-id="3997d-148">여러 계정을 내보내는 경우 한 계정을 내보낼 때 다음 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-148">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![상위 폴더가 선택된 Outlook 데이터 파일 내보내기 대화 상자 및 하위 폴더 포함 선택](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="3997d-150">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-150">Select **Next**.</span></span>
    
8. <span data-ttu-id="3997d-151">**찾아보기를** 선택하여 Outlook 데이터 파일(.pst)을 저장할 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-151">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="3997d-152">파일  *이름 을 입력한* 다음 **확인을** 선택하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-152">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3997d-153">내보내기 전에 사용한 경우 이전 폴더 위치와 파일 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-153">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="3997d-154">확인을 *선택하기* 전에 다른 파일 이름을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-154">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="3997d-155">기존 Outlook 데이터 파일(.pst)로 내보내는 경우 **옵션** 에서 파일에 이미 있는 항목을 내보낼 때 수행할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-155">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="3997d-156">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="3997d-156">Select **Finish**.</span></span>
    
<span data-ttu-id="3997d-157">Outlook에서 새 Outlook 데이터 파일(.pst)을 만들거나 암호로 보호된 파일을 사용하는 경우를 아니면 내보내기 즉시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-157">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="3997d-158">Outlook 데이터 파일(.pst)을 만드는 경우 선택적 암호를 사용하여 파일을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-158">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="3997d-159">Outlook 데이터 **파일 만들기** 대화 상자가  나타나면 암호  및 암호 확인 상자에 암호를 입력한 다음 확인 을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="3997d-159">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="3997d-160">Outlook **데이터 파일 암호** 대화 상자에서 암호를 *입력하고* 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-160">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="3997d-161">암호로 보호된 기존 Outlook 데이터 파일(.pst)으로 내보내는 경우 **Outlook** 데이터 파일 암호 대화 상자에서 암호를 입력하고 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-161">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="3997d-162">Outlook 2010에서 Outlook [.pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) 파일로 전자 메일, 연락처 및 일정을 내보내거나 백업하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3997d-162">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="3997d-163">기본적으로 전자 메일은 12개월 동안 오프라인으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-163">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="3997d-164">필요한 경우 오프라인에서 사용 가능한 데이터를 [늘리는 방법을 참조합니다.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)</span><span class="sxs-lookup"><span data-stu-id="3997d-164">If required, see how to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="3997d-165">다른 사용자에게 이전 사용자의 전자 메일에 대한 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-165">Give another user access to a former user's email</span></span> 

<span data-ttu-id="3997d-166">이전 직원의 전자 메일 메시지, 일정, 작업 및 연락처에 대한 액세스 권한을 다른 직원에게 제공하기 위해 해당 정보를 다른 직원의 Outlook 받은 편지함으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-166">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="3997d-167">이전 사용자의 [사서함을](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) 공유 사서함으로 변환하거나 이전 직원의 전자 메일을 다른 직원에게 전달할 [수도 있습니다.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="3997d-167">You can also [convert the former user's mailbox to a shared mailbox](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="3997d-168">Outlook에서 파일  \> **열기 내보내기 &amp; 가져오기/내보내기** \> **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="3997d-168">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="3997d-169">그러면 가져오기 및 내보내기 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-169">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="3997d-170">다른 **프로그램 또는 파일에서 가져오기 를 선택하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-170">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![가져오기 및 내보내기 마법사](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="3997d-172">**Outlook 데이터 파일(.pst)을** 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-172">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="3997d-173">가져올 .pst 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-173">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="3997d-174">옵션 **아래에서** 중복 항목을 처리하려는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-174">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="3997d-175">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-175">Select **Next**.</span></span>
    
7. <span data-ttu-id="3997d-176">Outlook 데이터 파일(.pst)에 암호를 할당한 경우 암호를 입력한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3997d-176">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="3997d-177">항목 가져오기 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-177">Set the options for importing items.</span></span> <span data-ttu-id="3997d-178">기본 설정은 일반적으로 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-178">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="3997d-179">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="3997d-179">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="3997d-180">기존 사용자의 OneDrive 및 전자 메일 데이터에 액세스하는 단계는 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-180">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="3997d-181">Outlook 데이터 파일(.pst)에서 몇 가지 항목만 가져오거나 복원하려는 경우 Outlook 데이터 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-181">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="3997d-182">그런 다음 탐색 창에서 Outlook 데이터 파일 폴더의 항목을 기존 Outlook 폴더로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="3997d-182">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="3997d-183">관련 문서</span><span class="sxs-lookup"><span data-stu-id="3997d-183">Related articles</span></span>
[<span data-ttu-id="3997d-184">Office 365에서 이전 직원 제거</span><span class="sxs-lookup"><span data-stu-id="3997d-184">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="3997d-185">OneDrive 계정에서 관리자 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="3997d-185">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="3997d-186">삭제된 OneDrive 복원</span><span class="sxs-lookup"><span data-stu-id="3997d-186">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="3997d-187">OneDrive 보존 및 삭제</span><span class="sxs-lookup"><span data-stu-id="3997d-187">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
