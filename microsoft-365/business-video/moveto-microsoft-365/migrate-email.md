---
title: Google Workspace에서 비즈니스 전자 메일 및 일정 마이그레이션
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Google Workspace에서 비즈니스용 Microsoft 365로 전자 메일, 연락처 및 일정을 마이그레이션하는 방법을 학습합니다.
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928249"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="aae2d-103">Google Workspace에서 비즈니스 전자 메일 및 일정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="aae2d-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="aae2d-104">Google Workspace에서 Exchange Online으로 관리자가 실행한 마이그레이션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="aae2d-105">메일을 한 번 또는 단계적으로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="aae2d-106">다음 단계에서는 전자 메일 데이터를 한 번 마이그레이션하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="aae2d-107">자세한 내용은 [G Suite 마이그레이션 수행을 참조하세요.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="aae2d-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="aae2d-108">마이그레이션 프로세스는 마이그레이션하는 데이터의 양에 따라 몇 시간에서 며칠까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="aae2d-109">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="aae2d-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="aae2d-110">Google 서비스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="aae2d-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="aae2d-111">Chrome 브라우저를 사용하여 2016년 10월 1일부로 Google Workspace 관리 콘솔에 [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="aae2d-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="aae2d-112">새 탭 또는 창에서 서비스 계정 [페이지로](https://console.developers.google.com/iam-admin/serviceaccounts) 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="aae2d-113">프로젝트 **만들기를 선택하고** 프로젝트 이름을 지정하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="aae2d-114">서비스 **계정 만들기를 선택하고** 이름을 입력하고 만들기 및 완료를 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="aae2d-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="aae2d-115">작업 **메뉴를** 열고 편집을 선택한 다음 고유 ID를 메모합니다. </span><span class="sxs-lookup"><span data-stu-id="aae2d-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="aae2d-116">프로세스의 나중에 이 ID가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="aae2d-117">도메인 전체 **위임 표시 섹션을 여십시오.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="aae2d-118">**G Suite 도메인 전체** 위임 사용을 선택하고 동의 화면의 제품 이름을 입력한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="aae2d-119">제품 이름은 마이그레이션 프로세스에서 사용되지 않지만 대화 상자에 저장하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="aae2d-120">작업 **메뉴를** 다시 열고 **키 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="aae2d-121">Choose **JSON,** then **Create**.</span><span class="sxs-lookup"><span data-stu-id="aae2d-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="aae2d-122">개인 키는 장치의 다운로드 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="aae2d-123">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="aae2d-124">프로젝트에 대한 API 사용 사용</span><span class="sxs-lookup"><span data-stu-id="aae2d-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="aae2d-125">API [페이지로 이동합니다.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="aae2d-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="aae2d-126">검색 표시줄에 **Gmail API를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="aae2d-127">이 옵션을 선택하고 사용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="aae2d-128">Google 캘린더 API 및 연락처 API에 대해 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="aae2d-129">서비스 계정에 대한 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="aae2d-129">Grant access to the service account</span></span>

1. <span data-ttu-id="aae2d-130">Google Workspace 관리 콘솔로 돌아올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="aae2d-131">보안 **선택,** 아래로 스크롤 및 **API 컨트롤 열기.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="aae2d-132">아래로 스크롤하여 도메인 전체 **위임 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="aae2d-133">새로 **추가를** 선택하고 앞에서 메모한 클라이언트 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="aae2d-134">그런 다음 Google API에 대한 OAuth 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="aae2d-135">이러한 단계는 [5단계에서](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) aka.ms/GoogleWorkspaceMigration 사용할 수 있으며 다음 중 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="aae2d-136">Choose **Authorize**.</span><span class="sxs-lookup"><span data-stu-id="aae2d-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="aae2d-137">Microsoft 365로 전송하는 메일에 대한 하위 도메인 만들기</span><span class="sxs-lookup"><span data-stu-id="aae2d-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="aae2d-138">**Google Workspace 관리 콘솔로 돌아올 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="aae2d-139">도메인을 **선택하고** **도메인을 관리한** 다음 도메인 **별칭을 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="aae2d-140">같은 도메인 별칭을 `m365.contoso.com` 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="aae2d-141">그런 다음 **계속을 선택하고 도메인 소유권을 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="aae2d-142">도메인 확인은 일반적으로 몇 분 정도 걸리지만 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="aae2d-143">[Microsoft 365 관리 센터로 이동하세요.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aae2d-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="aae2d-144">Microsoft **365** 관리 센터의 왼쪽 nav에서 모두 표시,   **설정,** 도메인 및 도메인 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="aae2d-145">이전에 만든 하위 도메인을 입력한 다음 이 도메인 **사용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="aae2d-146">도메인을 연결하려면 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="aae2d-147">아래로 스크롤하여 MX 레코드, CNAME 레코드 및 TXT 레코드를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="aae2d-148">Google 관리 **콘솔로 돌아오기**</span><span class="sxs-lookup"><span data-stu-id="aae2d-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="aae2d-149">도메인을 **선택하고** 도메인 **관리,** **세부 정보 확인,** **도메인 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="aae2d-150">In the left nav, choose **DNS** and scroll down to **Custom resource records.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="aae2d-151">레코드 형식 드롭다운을 열고 **MX를** 선택하고 이전에 기록한 MX 레코드 정보를 입력하거나 복사하여 붙여넣은 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="aae2d-152">CNAME 레코드 및 TXT 레코드에 대한 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="aae2d-153">이러한 변경 내용을 적용하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="aae2d-154">**Microsoft 365** 관리 센터에서 벗어났다가 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="aae2d-155">이제 도메인이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="aae2d-156">Microsoft 365에서 전자 메일 별칭 만들기</span><span class="sxs-lookup"><span data-stu-id="aae2d-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="aae2d-157">마이그레이션을 시작하기 전에 새 하위omain을 사용하여 사용자에 대한 전자 메일 별칭을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="aae2d-158">다음 단계를 시작하려면 Microsoft  365 관리 센터의 도메인 추가 마법사에서 활성 사용자로 **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="aae2d-159">사용자를 선택한 다음 사용자 이름 **및 전자 메일을 관리합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="aae2d-160">도메인 **드롭다운에서** 이전에 만든 하위 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="aae2d-161">사용자 이름을 입력하고 **추가,** 변경 **내용** 저장 및 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="aae2d-162">각 사용자에 대해 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="aae2d-163">마이그레이션 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="aae2d-163">Start the migration process</span></span>

<span data-ttu-id="aae2d-164">완료되면 마이그레이션할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="aae2d-165">**Microsoft 365** 관리 센터의 왼쪽 네비게이트에서 관리 센터로 스크롤하여 **Exchange를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="aae2d-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="aae2d-166">Under **recipients,** choose **migration,** select **New,** **Migrate to Exchange Online,** choose **G Suite migration,** and then **Next.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="aae2d-167">마이그레이션할 사서함 목록이 있는 CSV 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="aae2d-168">파일이 다음 형식을 따르는지 확인</span><span class="sxs-lookup"><span data-stu-id="aae2d-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="aae2d-169">자세한 내용은 다음을 [aka.ms/GoogleWorkspaceMigration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)</span><span class="sxs-lookup"><span data-stu-id="aae2d-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="aae2d-170">Select **Choose File,** navigate to the CSV file, choose it, select **Open,** then **Next.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="aae2d-171">테스트에 사용할 관리자 전자 메일 주소를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="aae2d-172">Choose **File,** navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open,** then **Next.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="aae2d-173">새 마이그레이션 일괄 처리 이름 **필드에 이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="aae2d-174">대상 배달 도메인 필드에 만든  하위 도메인을 입력하고 **다음을** 선택한 다음 새로 **고를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="aae2d-175">정보가 저장되고 나면 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="aae2d-176">이제 마이그레이션 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="aae2d-177">마이그레이션하는 사용자의 수에 따라 시간이 지나면 새로 고침을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="aae2d-178">상태가 동기화된 것으로 변경된 후 **이** 마이그레이션 **일괄** 처리 완료,예를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="aae2d-179">프로세스가 완료되면 상태가 **완료로 변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="aae2d-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="aae2d-180">원하는 경우 마이그레이션에  대한 자세한 내용 보기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="aae2d-181">**닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-181">Select **Close**.</span></span> 
1. <span data-ttu-id="aae2d-182">Outlook을 열고 Google Workspace의 모든 전자 메일이 성공적으로 마이그레이션된지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="aae2d-183">일정 항목 및 연락처에 대해 이 작업을 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae2d-183">You can repeat this for calendar items and contacts as well.</span></span>