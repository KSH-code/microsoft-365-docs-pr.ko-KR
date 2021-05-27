---
title: PST 파일을 가져올 때 데이터 필터링
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: PST 파일을 가져올 때 Office 365 가져오기 서비스의 지능형 가져오기 기능을 사용하여 데이터를 필터링하는 Office 365.
ms.openlocfilehash: fb978332f70495044a457147d29d8cdcf1194264
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684060"
---
# <a name="filter-data-when-importing-pst-files"></a><span data-ttu-id="77198-103">PST 파일을 가져올 때 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="77198-103">Filter data when importing PST files</span></span>

<span data-ttu-id="77198-104">Office 365 가져오기 서비스의 새로운 지능형 가져오기 기능을 사용하여 실제로 대상 사서함으로 가져오는 PST 파일의 항목을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-104">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="77198-105">작동 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-105">Here's how it works:</span></span>
  
- <span data-ttu-id="77198-106">PST 가져오기 작업을 만들고 제출하면 PST 파일이 Microsoft 클라우드의 Azure 저장소 영역에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-106">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
- <span data-ttu-id="77198-107">Microsoft 365 PST 파일에 포함된 다양한 메시지 유형과 사서함 항목의 사용 기한을 식별하여 안전하고 안전한 방식으로 PST 파일의 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-107">Microsoft 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
  
- <span data-ttu-id="77198-108">분석이 완료되어 데이터를 가져올 준비가 된 경우 PST 파일의 모든 데이터를 있는 것으로 가져오거나 가져올 데이터를 제어하는 필터를 설정하여 가져온 데이터를 자르는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-108">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="77198-109">예를 들어 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-109">For example, you can choose to:</span></span>
  
  - <span data-ttu-id="77198-110">특정 연령의 항목만 가져오기</span><span class="sxs-lookup"><span data-stu-id="77198-110">Import only items of a certain age.</span></span>
  
  - <span data-ttu-id="77198-111">선택한 메시지 유형 가져오기</span><span class="sxs-lookup"><span data-stu-id="77198-111">Import selected message types.</span></span>
  
  - <span data-ttu-id="77198-112">특정 사람이 보내거나 받은 메시지를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-112">Exclude messages sent or received by specific people.</span></span>
  
- <span data-ttu-id="77198-113">필터 설정을 구성한 Microsoft 365 필터링 조건을 충족하는 데이터만 가져오기 작업에서 지정된 대상 사서함으로만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-113">After you configure the filter settings, Microsoft 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
  
<span data-ttu-id="77198-114">다음 그림에서는 지능형 가져오기 프로세스를 보여 주며, 수행한 작업과 작업 및 사용자들이 수행한 작업을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="77198-114">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![2016의 지능형 가져오기 Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a><span data-ttu-id="77198-116">PST 가져오기 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="77198-116">Create a PST import job</span></span>

- <span data-ttu-id="77198-117">이 항목의 단계에서는 네트워크 업로드 또는 드라이브 배송을 사용하여 가져오기 Office 365 PST 가져오기 작업을 만들었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-117">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="77198-118">단계별 지침은 다음 항목 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77198-118">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="77198-119">네트워크 업로드를 사용하여 PST 파일을 Office 365로 가져오기</span><span class="sxs-lookup"><span data-stu-id="77198-119">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="77198-120">드라이브 배송을 사용하여 Office 365로 PST 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="77198-120">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="77198-121">네트워크 업로드를 사용하여 가져오기 작업을 만든 후 보안 & 준수 센터의 가져오기 페이지에서 가져오기 작업의 상태가 Analysis **in progress로** 설정됩니다. 즉, Microsoft 365 PST 파일에서 데이터를 분석하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-121">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Microsoft 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="77198-122">새로 **고침을** ![ 클릭하여 ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 가져오기 작업의 상태를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-122">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="77198-123">드라이브 배송 가져오기 작업의 경우 Microsoft Microsoft 365 직원이 하드 드라이브를 받고 PST 파일을 조직의 Azure 저장소 영역에 업로드한 후 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-123">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="77198-124">사서함으로 가져오는 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="77198-124">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="77198-125">PST 가져오기 작업을 만든 후 다음 단계에 따라 데이터를 가져오기 전에 데이터를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="77198-125">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="77198-126"><https://compliance.microsoft.com>으로 이동한 후 조직의 관리자 계정 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-126">Go to <https://compliance.microsoft.com> and sign in using the credentials for an administrator account in your organization.</span></span>
    
2. <span data-ttu-id="77198-127">규정 준수 센터의 왼쪽 Microsoft 365 정보 **거버넌스 가져오기 를** \> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77198-127">In the left pane of the Microsoft 365 compliance center, click **Information governance** \> **Import**.</span></span>
    
    <span data-ttu-id="77198-128">조직의 가져오기 작업이 가져오기 **탭에 나열됩니다.** 상태 **열의 분석** 완료 **값은** 사용자가 분석한 가져오기 Microsoft 365 가져오기 준비가 완료된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77198-128">The import jobs for your organization are listed on the **Import** tab. The **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Microsoft 365 and are ready for you to import.</span></span>
    
    ![분석 완료 상태는 Microsoft 365 PST 파일의 데이터를 분석한 경우를 나타냅니다.](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="77198-130">완료할 가져오기 작업을 선택하고 가져오기 를 **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="77198-130">Select the import job that you want to complete and click **Import to Office 365**.</span></span>
  
    <span data-ttu-id="77198-131">PST 파일에 대한 정보 및 가져오기 작업에 대한 기타 정보가 포함된 플라이 아웃 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-131">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>

4. <span data-ttu-id="77198-132">가져오기 **를 클릭하여 Office 365.**</span><span class="sxs-lookup"><span data-stu-id="77198-132">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="77198-133">**데이터 필터링** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-133">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="77198-134">이 문서에는 데이터 사용 기한에 대한 정보를 포함하여 가져오기 작업의 PST 파일에 있는 데이터에 대한 데이터 인사이트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-134">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![데이터 필터링 페이지에 가져오기 작업용 PST 파일의 데이터 인사이트가 표시됩니다.](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="77198-136">데이터 필터링으로 가져온 데이터를 트리밍할지 여부에 따라 Microsoft 365? 아래에서 **다음** 중 하나를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-136">Based on whether or not you want to trim the data that's imported to Microsoft 365, under **Do you want to filter your data?**, do one of the following:</span></span>
  
    <span data-ttu-id="77198-137">a.</span><span class="sxs-lookup"><span data-stu-id="77198-137">a.</span></span> <span data-ttu-id="77198-138">**가져오기** 전에 필터링을 클릭하여 가져오는 데이터를 자르고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77198-138">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
  
    <span data-ttu-id="77198-139">이 **페이지로** Office 365 가져오기 페이지는 수행한 분석의 자세한 데이터 Microsoft 365 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-139">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Microsoft 365 performed.</span></span> 
  
    ![Microsoft 365 PST 파일 분석에서 자세한 데이터 인사이트를 표시하는 방법](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="77198-141">이 페이지의 그래프에는 가져올 데이터의 양이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-141">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="77198-142">PST 파일에 있는 각 메시지 유형에 대한 정보가 그래프에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-142">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="77198-143">각 막대 위에 커서를 마우스로 대고 해당 메시지 유형에 대한 특정 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-143">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="77198-144">또한 PST 파일 분석에 따라 연령 값이 다른 드롭다운 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-144">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="77198-145">드롭다운 목록에서 기간을 선택하면 선택한 기간 동안 가져올 데이터의 수를 표시하기 위해 그래프가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-145">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
  
    <span data-ttu-id="77198-146">b.</span><span class="sxs-lookup"><span data-stu-id="77198-146">b.</span></span> <span data-ttu-id="77198-147">추가 필터를 구성하여 가져오는 데이터의 양을 줄이려면 추가 필터링 옵션 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77198-147">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
  
    ![가져오는 데이터를 자르도록 추가 옵션 페이지에서 필터 구성](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="77198-149">다음 필터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-149">You can configure these filters:</span></span>
  
      - <span data-ttu-id="77198-150">**Age** - 지정된 기간보다 더 새로운 항목만 가져올 수 있도록 연령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-150">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="77198-151">연령 [필터의](#more-information) 연령 버킷을 결정하는 Microsoft 365 자세한 내용은 추가 정보 **섹션을 참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="77198-151">See the [More information](#more-information) section for a description about how Microsoft 365 determines the age buckets for the **Age** filter.</span></span> 
  
      - <span data-ttu-id="77198-152">**Type** - 이 섹션에는 가져오기 작업의 PST 파일에서 찾은 모든 메시지 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-152">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="77198-153">제외할 메시지 유형 옆에 있는 상자의 선택을 선택을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-153">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="77198-154">기타 메시지 유형은 제외할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-154">You can't exclude the Other message type.</span></span> <span data-ttu-id="77198-155">기타 [범주에 포함된](#more-information) 사서함 항목 목록은 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77198-155">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span>
  
      - <span data-ttu-id="77198-156">**사용자** - 특정 사용자가 보내거나 받은 메시지를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-156">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="77198-157">보낸 사람: 필드, 받는 사람: 필드 또는 메시지의 Cc: 필드에  나타나는 사용자를 제외하려면 해당 받는 사람 유형 옆에 있는 사용자 제외를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-157">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="77198-158">사용자의 전자 메일 주소(SMTP 주소)를 입력하고 새로 추가 아이콘을 클릭하여 해당 받는 사람 유형에 대해 제외된 사용자 목록에 추가한 다음 저장을 클릭하여 제외된 사용자 목록을  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 저장합니다. </span><span class="sxs-lookup"><span data-stu-id="77198-158">Type the email address (SMTP address) of the person, click **Add**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
  
        > [!NOTE]
        > <span data-ttu-id="77198-159">Microsoft 365 사용자 필터 설정으로 인해 데이터 인사이트를 **표시하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-159">Microsoft 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="77198-160">그러나 특정 사용자가 보내거나 받은 메시지를 제외하도록 이 필터를 설정하면 실제 가져오기 프로세스 중에 해당 메시지가 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-160">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="77198-161">c.</span><span class="sxs-lookup"><span data-stu-id="77198-161">c.</span></span> <span data-ttu-id="77198-162">필터 **설정을** 저장하려면 **추가** 필터링 옵션 플라이아웃 페이지에서 적용을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-162">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
  
    <span data-ttu-id="77198-163">데이터 가져오기 페이지에서  Office 365 데이터 인사이트는 필터 설정에 따라 가져올 총 데이터 양을 포함하여 필터 설정에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-163">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="77198-164">필터 설정에 대한 요약도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-164">A summary of the filter settings is also shown.</span></span> <span data-ttu-id="77198-165">필요한 경우 **필터** 옆에 있는 편집을 클릭하여 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-165">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
  
    ![데이터 인사이트는 필터 설정에 따라 업데이트됩니다.](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="77198-167">d.</span><span class="sxs-lookup"><span data-stu-id="77198-167">d.</span></span> <span data-ttu-id="77198-168">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-168">Click **Next**.</span></span>
  
    <span data-ttu-id="77198-169">필터 설정을 표시하는 상태 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-169">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="77198-170">다시 한 번 필터 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77198-170">Again, you can edit any of the filter settings.</span></span>
  
    <span data-ttu-id="77198-171">e.</span><span class="sxs-lookup"><span data-stu-id="77198-171">e.</span></span> <span data-ttu-id="77198-172">데이터 **가져오기 를 클릭하여** 가져오기 시작</span><span class="sxs-lookup"><span data-stu-id="77198-172">Click **Import data** to start the import.</span></span> <span data-ttu-id="77198-173">가져올 데이터의 총 양이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-173">The total amount of data that will be imported is displayed.</span></span> 
  
    <span data-ttu-id="77198-174">또는</span><span class="sxs-lookup"><span data-stu-id="77198-174">Or</span></span>
  
    <span data-ttu-id="77198-175">a.</span><span class="sxs-lookup"><span data-stu-id="77198-175">a.</span></span> <span data-ttu-id="77198-176">**아니요,** PST 파일의 모든 데이터를 가져오기 위해 모든 데이터를 가져오고 Office 365 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="77198-176">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
  
    <span data-ttu-id="77198-177">b.</span><span class="sxs-lookup"><span data-stu-id="77198-177">b.</span></span> <span data-ttu-id="77198-178">데이터 **가져오기 Office 365** 가져오기 페이지에서 데이터 가져오기를 **클릭하여** 가져오기 시작을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-178">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="77198-179">가져올 데이터의 총 양이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-179">The total amount of data that will be imported is displayed.</span></span> 
  
6. <span data-ttu-id="77198-180">가져오기 **탭에서** 새로 **고침 을** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-180">On the **Import** tab, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="77198-181">가져오기 작업의 상태가 상태 **열에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77198-181">The status for the import job is displayed in the **Status** column.</span></span>
  
7. <span data-ttu-id="77198-182">작업 가져오기 를 클릭하여 각 PST 파일의 상태 및 구성한 필터 설정과 같은 자세한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-182">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

## <a name="more-information"></a><span data-ttu-id="77198-183">추가 정보</span><span class="sxs-lookup"><span data-stu-id="77198-183">More information</span></span>

- <span data-ttu-id="77198-184">연령 Microsoft 365 증분을 어떻게 결정하나요?</span><span class="sxs-lookup"><span data-stu-id="77198-184">How does Microsoft 365 determine the increments for the age filter?</span></span> <span data-ttu-id="77198-185">PST Microsoft 365 분석할 때 각 항목의 보내거나 받은 타임스탬프를 니다(항목에 보낸 타임스탬프와 받은 타임스탬프가 모두 있는 경우 가장 오래된 날짜가 선택된 경우).</span><span class="sxs-lookup"><span data-stu-id="77198-185">When Microsoft 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="77198-186">그런 Microsoft 365 타임스탬프의 연도 값을 확인하여 현재 날짜와 비교하여 항목의 사용 기간을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77198-186">Then Microsoft 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="77198-187">이러한 연령은 연령 필터에 대한 드롭다운 목록의 값으로 **사용됩니다.**</span><span class="sxs-lookup"><span data-stu-id="77198-187">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="77198-188">예를 들어 PST 파일에 2016, 2015 및 2014의 메시지가 있는  경우 연령 필터의 값은 **1년,** **2년** 및 **3년입니다.**</span><span class="sxs-lookup"><span data-stu-id="77198-188">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
  
- <span data-ttu-id="77198-189">다음 표에는 기타 옵션 플라이아웃 페이지의 유형  필터에서 기타  범주에 포함된 메시지 유형이 나열되어 있습니다(이전 절차의 5b단계 참조). </span><span class="sxs-lookup"><span data-stu-id="77198-189">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="77198-190">현재는 다른 항목으로 PSTS를 가져올 때 "기타" 범주의 항목을 제외할 Office 365.</span><span class="sxs-lookup"><span data-stu-id="77198-190">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
  
    |<span data-ttu-id="77198-191">**메시지 클래스 ID**</span><span class="sxs-lookup"><span data-stu-id="77198-191">**Message class ID**</span></span>|<span data-ttu-id="77198-192">**이 메시지 클래스를 사용하는 사서함 항목**</span><span class="sxs-lookup"><span data-stu-id="77198-192">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77198-193">IPM. 활동</span><span class="sxs-lookup"><span data-stu-id="77198-193">IPM.Activity</span></span>  <br/> |<span data-ttu-id="77198-194">업무 일지 항목</span><span class="sxs-lookup"><span data-stu-id="77198-194">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="77198-195">IPM.Doc</span><span class="sxs-lookup"><span data-stu-id="77198-195">IPM.Document</span></span>  <br/> |<span data-ttu-id="77198-196">문서 및 파일(전자 메일 메시지에 첨부되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="77198-196">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="77198-197">IPM. 파일</span><span class="sxs-lookup"><span data-stu-id="77198-197">IPM.File</span></span>  <br/> |<span data-ttu-id="77198-198">(멘트와 IPM.Doc동일)</span><span class="sxs-lookup"><span data-stu-id="77198-198">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="77198-199">IPM. 참고.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="77198-199">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="77198-200">인터넷에 대한 커넥트 게이트웨이인 인터넷 메일 서비스에서 Exchange Server 보고서</span><span class="sxs-lookup"><span data-stu-id="77198-200">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="77198-201">IPM. 참고.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="77198-201">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="77198-202">팩스 메시지</span><span class="sxs-lookup"><span data-stu-id="77198-202">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="77198-203">IPM. 참고.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="77198-203">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="77198-204">부재 중 메시지 자동 고치기</span><span class="sxs-lookup"><span data-stu-id="77198-204">Out-of-office autoreply messages</span></span>  <br/> |
    |<span data-ttu-id="77198-205">IPM. 참고.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="77198-205">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="77198-206">받은 편지함 규칙에서 보낸 답장</span><span class="sxs-lookup"><span data-stu-id="77198-206">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="77198-207">IPM. OLE. 클래스</span><span class="sxs-lookup"><span data-stu-id="77198-207">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="77198-208">Recurring 계열에 대한 예외</span><span class="sxs-lookup"><span data-stu-id="77198-208">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="77198-209">IPM. Recall.Report</span><span class="sxs-lookup"><span data-stu-id="77198-209">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="77198-210">메시지 회수 보고서</span><span class="sxs-lookup"><span data-stu-id="77198-210">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="77198-211">IPM. 원격</span><span class="sxs-lookup"><span data-stu-id="77198-211">IPM.Remote</span></span>  <br/> |<span data-ttu-id="77198-212">원격 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="77198-212">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="77198-213">IPM. 보고서</span><span class="sxs-lookup"><span data-stu-id="77198-213">IPM.Report</span></span>  <br/> |<span data-ttu-id="77198-214">항목 상황 보고서</span><span class="sxs-lookup"><span data-stu-id="77198-214">Item status reports</span></span>  <br/> |
