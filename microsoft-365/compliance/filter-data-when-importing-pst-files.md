---
title: PST 파일을 가져올 때 데이터 필터링
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
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
description: PST 파일을 Office 365로 가져올 때 Office 365 가져오기 서비스의 지능형 가져오기 기능을 사용하여 데이터를 필터링하는 방법을 학습합니다.
ms.openlocfilehash: d511c1277104a27076116fafcb4b71bc851baaca
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817727"
---
# <a name="filter-data-when-importing-pst-files"></a><span data-ttu-id="2c8d4-103">PST 파일을 가져올 때 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="2c8d4-103">Filter data when importing PST files</span></span>

<span data-ttu-id="2c8d4-104">Office 365 가져오기 서비스의 새로운 지능형 가져오기 기능을 사용하여 실제로 대상 사서함으로 가져오는 PST 파일의 항목을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-104">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="2c8d4-105">작동 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-105">Here's how it works:</span></span>
  
- <span data-ttu-id="2c8d4-106">PST 가져오기 작업을 만들고 제출하면 PST 파일이 Microsoft 클라우드의 Azure 저장소 영역에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-106">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="2c8d4-107">Microsoft 365는 PST 파일에 포함된 사서함 항목의 연령 및 다양한 메시지 유형을 식별하여 안전하고 안전한 방식으로 PST 파일의 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-107">Microsoft 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="2c8d4-108">분석이 완료된 후 데이터를 가져올 준비가 된 경우 PST 파일의 모든 데이터를 있는 것으로 가져오거나 가져오는 데이터를 제어하는 필터를 설정하여 가져온 데이터를 트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-108">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="2c8d4-109">예를 들어 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-109">For example, you can choose to:</span></span>
    
  - <span data-ttu-id="2c8d4-110">특정 연령의 항목만 가져오기</span><span class="sxs-lookup"><span data-stu-id="2c8d4-110">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="2c8d4-111">선택한 메시지 유형을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-111">Import selected message types.</span></span>
    
  - <span data-ttu-id="2c8d4-112">특정 사람이 보내거나 받은 메시지를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-112">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="2c8d4-113">필터 설정을 구성한 후 Microsoft 365는 필터링 조건을 충족하는 데이터만 가져오기 작업에서 지정된 대상 사서함으로 가져오기합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-113">After you configure the filter settings, Microsoft 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="2c8d4-114">다음 그림에서는 지능형 가져오기 프로세스를 보여 주며, 수행하는 작업과 Office 365에서 수행하는 작업을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-114">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365의 지능형 가져오기 프로세스](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a><span data-ttu-id="2c8d4-116">PST 가져오기 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="2c8d4-116">Create a PST import job</span></span>

- <span data-ttu-id="2c8d4-117">이 항목의 단계에서는 네트워크 업로드 또는 드라이브 배송을 사용하여 Office 365 가져오기 서비스에서 PST 가져오기 작업을 만들었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-117">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="2c8d4-118">단계별 지침은 다음 항목 중 하나를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-118">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="2c8d4-119">네트워크 업로드를 사용하여 PST 파일을 Office 365로 가져오기</span><span class="sxs-lookup"><span data-stu-id="2c8d4-119">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="2c8d4-120">드라이브 배송을 사용하여 Office 365로 PST 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="2c8d4-120">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="2c8d4-121">& 네트워크 업로드를 사용하여 가져오기 작업을 만든 후 보안 및 준수 센터의 가져오기 페이지에서 가져오기 작업의 상태가 진행 중으로 설정됩니다. **즉,** Microsoft 365가 업로드한 PST 파일의 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-121">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Microsoft 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="2c8d4-122">새로 **고침을** ![ 클릭하여 ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 가져오기 작업의 상태를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-122">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="2c8d4-123">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-123">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="2c8d4-124">사서함으로 가져오는 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="2c8d4-124">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="2c8d4-125">PST 가져오기 작업을 만든 후 Office 365로 가져오기 전에 다음 단계에 따라 데이터를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-125">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="2c8d4-126">[https://protection.office.com/](https://protection.office.com/)으로 이동한 후 조직의 관리자 계정 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-126">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your organization.</span></span> 
    
2. <span data-ttu-id="2c8d4-127">정보 **거버넌스** \> **가져오기** \> **PST 파일을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-127">Click **Information governance** \> **Import** \> **Import PST files**.</span></span>
    
    <span data-ttu-id="2c8d4-128">조직의 가져오기 작업은 **PST** 파일 가져오기 페이지에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-128">The import jobs for your organization are listed on the **Import PST files** page.</span></span> <span data-ttu-id="2c8d4-129">상태 열의 **분석** 완료  값은 Microsoft 365에서 분석하여 가져올 준비가 된 가져오기 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-129">Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Microsoft 365 and are ready for you to import.</span></span> 
    
    ![분석 완료 상태는 Microsoft 365가 PST 파일의 데이터를 분석한 경우를 나타냅니다.](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="2c8d4-131">완료할 가져오기 작업을 **위해 Office 365로** 가져올 준비를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-131">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="2c8d4-132">PST 파일에 대한 정보 및 가져오기 작업에 대한 기타 정보가 포함된 플라이 아웃 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-132">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="2c8d4-133">**Office 365로 가져오기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-133">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="2c8d4-134">**데이터 필터링** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-134">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="2c8d4-135">데이터 사용 연령에 대한 정보를 포함하여 가져오기 작업의 PST 파일에 있는 데이터에 대한 데이터 인사이트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-135">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![데이터 필터링 페이지에 가져오기 작업용 PST 파일의 데이터 인사이트가 표시됩니다.](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="2c8d4-137">Microsoft 365로 가져온 데이터를 트리밍할지 여부에 따라 데이터를 필터링할지 여부에 따라 **다음** 중 하나를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-137">Based on whether or not you want to trim the data that's imported to Microsoft 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="2c8d4-138">a.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-138">a.</span></span> <span data-ttu-id="2c8d4-139">예, **가져오는** 데이터를 자르기 위해 가져오기 전에 필터링하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-139">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="2c8d4-140">**Office 365로** 데이터 가져오기 페이지는 Microsoft 365에서 수행한 분석의 자세한 데이터 인사이트와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-140">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Microsoft 365 performed.</span></span> 
    
    ![Microsoft 365는 PST 파일 분석에서 자세한 데이터 정보를 표시](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="2c8d4-142">이 페이지의 그래프에는 가져올 데이터의 양이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-142">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="2c8d4-143">PST 파일에 있는 각 메시지 유형에 대한 정보가 그래프에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-143">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="2c8d4-144">각 막대 위에 커서를 마우스로 대고 해당 메시지 유형에 대한 특정 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-144">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="2c8d4-145">PST 파일 분석에 따라 연령 값이 다른 드롭다운 목록도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-145">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="2c8d4-146">드롭다운 목록에서 연령을 선택하면 선택한 기간 동안 가져올 데이터의 수가 표시되어 그래프가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-146">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="2c8d4-147">b.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-147">b.</span></span> <span data-ttu-id="2c8d4-148">추가 필터를 구성하여 가져온 데이터의 양을 줄이려면 추가 필터링 옵션을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-148">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![더 많은 옵션 페이지에서 가져온 데이터를 자르도록 필터 구성](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="2c8d4-150">다음 필터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-150">You can configure these filters:</span></span>
    
      - <span data-ttu-id="2c8d4-151">**age** - 지정된 기간보다 더 새로운 항목만 가져올 수 있도록 연령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-151">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="2c8d4-152">Microsoft [](#more-information) 365에서 연령 필터의 연령 버킷을 결정하는 방법에 대한 설명은 추가 정보 섹션을 **참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-152">See the [More information](#more-information) section for a description about how Microsoft 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="2c8d4-153">**type** - 이 섹션에는 가져오기 작업의 PST 파일에서 찾은 모든 메시지 유형이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-153">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="2c8d4-154">제외할 메시지 유형 옆에 있는 확인란의 선택을 선택을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-154">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="2c8d4-155">다른 메시지 형식은 제외할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-155">Note that you can't exclude the Other message type.</span></span> <span data-ttu-id="2c8d4-156">기타 [범주에 포함된](#more-information) 사서함 항목 목록은 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-156">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="2c8d4-157">**사용자** - 특정 사용자가 보내거나 받은 메시지를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-157">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="2c8d4-158">보낸 사람: 필드, 받는 사람: 필드 또는 메시지의 Cc: 필드에 나타나는 사용자를 제외하려면 해당 받는 사람 유형 **옆에** 있는 사용자 제외를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-158">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="2c8d4-159">사용자의 전자 메일 주소(SMTP 주소)를 입력하고 새로 추가 아이콘을 클릭하여 해당 받는 사람 유형에 대해 제외된 사용자 목록에 추가한 다음 저장을 클릭하여 제외된 사용자 목록을  ![ 저장합니다. ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) </span><span class="sxs-lookup"><span data-stu-id="2c8d4-159">Type the email address (SMTP address) of the person, click **Add**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="2c8d4-160">Microsoft 365는 사용자 필터를 설정하여 얻을 수 있는 데이터 인사이트를 **표시하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-160">Microsoft 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="2c8d4-161">그러나 특정 사용자가 보내거나 받은 메시지를 제외하도록 이 필터를 설정하면 이러한 메시지는 실제 가져오기 프로세스 중에 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-161">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="2c8d4-162">c.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-162">c.</span></span> <span data-ttu-id="2c8d4-163">필터 **설정을** 저장하려면 추가 필터링 옵션 **플라이아웃** 페이지에서 적용을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-163">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="2c8d4-164">**Office 365로** 데이터 가져오기 페이지의 데이터 인사이트는 필터 설정에 따라 가져올 총 데이터 양을 포함하여 필터 설정에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-164">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="2c8d4-165">필터 설정에 대한 요약도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-165">Note that a summary of the filter settings is also shown.</span></span> <span data-ttu-id="2c8d4-166">필요한 경우 **필터** 옆에 있는 편집을 클릭하여 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-166">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![데이터 인사이트는 필터 설정에 따라 업데이트됩니다.](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="2c8d4-168">d.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-168">d.</span></span> <span data-ttu-id="2c8d4-169">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-169">Click **Next**.</span></span>
    
    <span data-ttu-id="2c8d4-170">필터 설정을 보여 주며 상태 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-170">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="2c8d4-171">다시, 필터 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-171">Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="2c8d4-172">e.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-172">e.</span></span> <span data-ttu-id="2c8d4-173">데이터 **가져오기를 클릭하여** 가져오기 시작</span><span class="sxs-lookup"><span data-stu-id="2c8d4-173">Click **Import data** to start the import .</span></span> <span data-ttu-id="2c8d4-174">가져올 총 데이터 양이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-174">Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="2c8d4-175">또는</span><span class="sxs-lookup"><span data-stu-id="2c8d4-175">Or</span></span>
    
    <span data-ttu-id="2c8d4-176">a.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-176">a.</span></span> <span data-ttu-id="2c8d4-177">**아니요를 클릭하고** PST 파일의 모든 데이터를 Office 365로 가져오기 위해 모든 데이터를 가져오고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-177">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="2c8d4-178">b.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-178">b.</span></span> <span data-ttu-id="2c8d4-179">Office **365로** 데이터 가져오기  페이지에서 데이터 가져오기를 클릭하여 가져오기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-179">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="2c8d4-180">가져올 총 데이터 양이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-180">Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="2c8d4-181">**PST 파일 가져오기 페이지에서** 새로 **고침을** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-181">On the **Import PST files** page, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="2c8d4-182">가져오기 작업의 상태가 상태 **열에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-182">The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="2c8d4-183">가져오기 작업을 클릭하여 각 PST 파일의 상태 및 구성한 필터 설정과 같은 자세한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-183">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="2c8d4-184">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2c8d4-184">More information</span></span>

- <span data-ttu-id="2c8d4-185">Microsoft 365는 연령 필터의 증분을 어떻게 결정하나요?</span><span class="sxs-lookup"><span data-stu-id="2c8d4-185">How does Microsoft 365 determine the increments for the age filter?</span></span> <span data-ttu-id="2c8d4-186">Microsoft 365는 PST 파일을 분석할 때 각 항목의 보내거나 받은 타임스탬프를 니다(항목에 보낸 타임스탬프와 받은 타임스탬프가 둘 다 있는 경우 가장 오래된 날짜가 선택된 경우).</span><span class="sxs-lookup"><span data-stu-id="2c8d4-186">When Microsoft 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="2c8d4-187">그런 다음 Microsoft 365는 해당 타임스탬프의 연도 값을 확인하여 현재 날짜와 비교하여 항목의 기간을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-187">Then Microsoft 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="2c8d4-188">이러한 연령은 연령 필터에 대한 드롭다운 목록의 값으로 **사용됩니다.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-188">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="2c8d4-189">예를 들어 PST 파일에 2016, 2015 및 2014의 메시지가 있는  경우 연령 필터의 값은 **1년,** **2년** 및 **3년입니다.**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-189">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="2c8d4-190">다음 표에는 기타 옵션 플라이아웃 페이지의 유형  필터에서 기타  범주에 포함된 메시지 유형이 나열되어 있습니다(이전 절차의 5b단계 참조). </span><span class="sxs-lookup"><span data-stu-id="2c8d4-190">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="2c8d4-191">현재는 OFFICE 365로 PSTS를 가져올 때 "기타" 범주의 항목을 제외할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c8d4-191">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="2c8d4-192">**메시지 클래스 ID**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-192">**Message class ID**</span></span>|<span data-ttu-id="2c8d4-193">**이 메시지 클래스를 사용하는 사서함 항목**</span><span class="sxs-lookup"><span data-stu-id="2c8d4-193">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="2c8d4-194">IPM. 활동</span><span class="sxs-lookup"><span data-stu-id="2c8d4-194">IPM.Activity</span></span>  <br/> |<span data-ttu-id="2c8d4-195">업무 일지 항목</span><span class="sxs-lookup"><span data-stu-id="2c8d4-195">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-196">IPM.Doc</span><span class="sxs-lookup"><span data-stu-id="2c8d4-196">IPM.Document</span></span>  <br/> |<span data-ttu-id="2c8d4-197">문서 및 파일(전자 메일 메시지에 첨부되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="2c8d4-197">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-198">IPM. 파일</span><span class="sxs-lookup"><span data-stu-id="2c8d4-198">IPM.File</span></span>  <br/> |<span data-ttu-id="2c8d4-199">(멘트와 IPM.Doc동일)</span><span class="sxs-lookup"><span data-stu-id="2c8d4-199">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-200">IPM. Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="2c8d4-200">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="2c8d4-201">인터넷에 대한 Exchange Server 게이트웨이인 Internet Mail Connect에서 보낸 보고서</span><span class="sxs-lookup"><span data-stu-id="2c8d4-201">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-202">IPM. 참고.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="2c8d4-202">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="2c8d4-203">팩스 메시지</span><span class="sxs-lookup"><span data-stu-id="2c8d4-203">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-204">IPM. Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c8d4-204">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="2c8d4-205">부재 중 메시지 자동 회신</span><span class="sxs-lookup"><span data-stu-id="2c8d4-205">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-206">IPM. Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c8d4-206">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="2c8d4-207">받은 편지함 규칙에서 보낸 답장</span><span class="sxs-lookup"><span data-stu-id="2c8d4-207">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-208">IPM. OLE. 클래스</span><span class="sxs-lookup"><span data-stu-id="2c8d4-208">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="2c8d4-209">재발하는 계열에 대한 예외</span><span class="sxs-lookup"><span data-stu-id="2c8d4-209">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-210">IPM. Recall.Report</span><span class="sxs-lookup"><span data-stu-id="2c8d4-210">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="2c8d4-211">메시지 회수 보고서</span><span class="sxs-lookup"><span data-stu-id="2c8d4-211">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-212">IPM. 원격</span><span class="sxs-lookup"><span data-stu-id="2c8d4-212">IPM.Remote</span></span>  <br/> |<span data-ttu-id="2c8d4-213">원격 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="2c8d4-213">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="2c8d4-214">IPM. 보고서</span><span class="sxs-lookup"><span data-stu-id="2c8d4-214">IPM.Report</span></span>  <br/> |<span data-ttu-id="2c8d4-215">항목 상황 보고서</span><span class="sxs-lookup"><span data-stu-id="2c8d4-215">Item status reports</span></span>  <br/> |
