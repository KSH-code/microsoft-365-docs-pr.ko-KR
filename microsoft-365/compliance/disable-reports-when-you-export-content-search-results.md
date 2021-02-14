---
title: 콘텐츠 검색 결과를 내보낼 때 보고서를 사용하지 않도록 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: 보안 및 준수 센터에서 콘텐츠 검색 결과를 내보낼 때 보고서를 사용하지 않도록 설정하려면 로컬 컴퓨터의 Windows 레지스트리를 & 수 있습니다.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817857"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="e7c44-103">콘텐츠 검색 결과를 내보낼 때 보고서를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e7c44-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="e7c44-104">eDiscovery 내보내기 도구를 사용하여 보안 & 준수 센터에서 콘텐츠 검색 결과를 내보내면 내보낼 콘텐츠에 대한 추가 정보가 포함된 두 개의 보고서가 자동으로 만들어지며 내보내기됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="e7c44-105">이러한 보고서는 Results.csv 파일 및 Manifest.xml 파일입니다(보고서에 대한 자세한 설명은 이 항목의 내보내기 보고서 사용 안 에 대한 질문과 대답 참조). [](#frequently-asked-questions-about-disabling-export-reports)</span><span class="sxs-lookup"><span data-stu-id="e7c44-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="e7c44-106">이러한 파일은 매우 크기 때문에 다운로드 시간을 절약하고 이러한 파일을 내보내지 못하게 하여 디스크 공간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="e7c44-107">검색 결과를 내보내는 데 사용하는 컴퓨터에서 Windows 레지스트리를 변경하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="e7c44-108">나중에 보고서를 포함하려는 경우 레지스트리 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="e7c44-109">내보내기 보고서를 사용하지 않도록 설정하는 레지스트리 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="e7c44-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="e7c44-110">콘텐츠 검색 결과를 내보내는 데 사용할 컴퓨터에서 다음 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7c44-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="e7c44-111">eDiscovery 내보내기 도구가 열려 있는 경우 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="e7c44-112">사용하지 않도록 설정할 내보내기 보고서에 따라 다음 단계 중 하나 또는 둘 다를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="e7c44-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="e7c44-113">**Results.csv**</span></span>
    
      <span data-ttu-id="e7c44-114">.reg의 파일 이름 접미사로 다음 텍스트를 Windows 레지스트리 파일에 저장합니다. 예를 들어 DisableResultsCsv.reg와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="e7c44-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="e7c44-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="e7c44-116">.reg의 파일 이름 접미사로 다음 텍스트를 Windows 레지스트리 파일에 저장합니다. 예를 들어 DisableManifestXml.reg와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="e7c44-117">Windows 탐색기에서 이전 단계에서 만든 .reg 파일을 클릭하거나 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="e7c44-118">사용자 액세스 제어 창에서 **예를** 클릭하여 레지스트리 편집기를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="e7c44-119">계속할지 묻는 메시지가 표시될 때 **예를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7c44-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="e7c44-120">레지스트리 편집기에는 설정이 레지스트리에 추가되었습니다.는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="e7c44-121">레지스트리 설정을 편집하여 내보내기 보고서를 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e7c44-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="e7c44-122">이전 절차에서 .reg 파일을 만들어 Results.csv 및 Manifest.xml 보고서를 사용하지 않도록 설정한 경우 해당 파일을 편집하여 보고서가 검색 결과로 내보내지 않도록 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="e7c44-123">다시 콘텐츠 검색 결과를 내보내는 데 사용할 컴퓨터에서 다음 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7c44-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="e7c44-124">eDiscovery 내보내기 도구가 열려 있는 경우 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="e7c44-125">이전 절차에서 만든 .reg 편집 파일 중 하나 또는 둘 다를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="e7c44-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="e7c44-126">**Results.csv**</span></span>
    
        <span data-ttu-id="e7c44-127">메모장에서 DisableResultsCsv.reg 파일을 열고 값을 변경한 다음  `False`  `True` 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="e7c44-128">예를 들어 파일을 편집한 후 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="e7c44-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="e7c44-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="e7c44-130">메모장에서 DisableManifestXml.reg 파일을 열고 값을 변경한 다음  `False`  `True` 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="e7c44-131">예를 들어 파일을 편집한 후 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="e7c44-132">Windows 탐색기에서 이전 단계에서 편집한 .reg 파일을 클릭하거나 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="e7c44-133">사용자 액세스 제어 창에서 **예를** 클릭하여 레지스트리 편집기를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="e7c44-134">계속할지 묻는 메시지가 표시될 때 **예를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7c44-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="e7c44-135">레지스트리 편집기에는 설정이 레지스트리에 추가되었습니다.는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="e7c44-136">내보내기 보고서를 사용 안 하게 하는 경우와 관련한 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="e7c44-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="e7c44-137">**보고서 및 Results.csv 보고서는 Manifest.xml 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="e7c44-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="e7c44-138">파일 Results.csv Manifest.xml 파일에는 내보낼 콘텐츠에 대한 추가 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="e7c44-139">**Results.csv** 검색 결과로 다운로드하는 각 항목에 대한 정보가 포함된 Excel 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="e7c44-140">전자 메일의 경우 결과 로그에는 다음을 비롯한 각 메시지에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="e7c44-141">원본 사서함에 있는 메시지의 위치 (포함 여부는 주 메시지는 보관 사서함 또는).</span><span class="sxs-lookup"><span data-stu-id="e7c44-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="e7c44-142">메시지가 전송된 날짜</span><span class="sxs-lookup"><span data-stu-id="e7c44-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="e7c44-143">메시지의 제목 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="e7c44-144">보낸 사람 및 메시지 받는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="e7c44-145">검색 결과를 내보낼 때 중복 제거를 사용하도록 설정한 경우 메시지가 중복 메시지인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="e7c44-146">중복 메시지의 경우 상위 **ItemId** 열에 해당 메시지를 중복 메시지로 식별하는 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="e7c44-147">**Parent ItemId** 열의 값은 내보낼 메시지의 **Item DocumentId** 열 값과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="e7c44-148">SharePoint 및 비즈니스용 OneDrive 사이트의 문서에 대해 결과 로그에는 다음을 비롯한 각 문서에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="e7c44-149">문서에 대 한 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="e7c44-150">문서가 있는 사이트 모음의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="e7c44-151">문서를 마지막으로 수정한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="e7c44-152">이름 (에 있는 제목 열 결과 로그에서) 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="e7c44-153">**Manifest.xml** 검색 결과에 포함된 각 항목에 대한 정보가 포함된 매니페스트 파일(XML 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="e7c44-154">이 보고서의 정보는 Results.csv 보고서와 동일하지만 EDRM(전자 검색 참조 모델)에서 지정한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="e7c44-155">EDRM에 대한 자세한 내용은 을(를) [https://www.edrm.net](https://www.edrm.net) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7c44-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="e7c44-156">**언제 이러한 보고서를 내보내지 않도록 설정해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e7c44-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="e7c44-157">특정 요구에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-157">It depends on your specific needs.</span></span> <span data-ttu-id="e7c44-158">많은 조직에서는 검색 결과에 대한 추가 정보가 필요하지 않습니다. 이러한 보고서는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="e7c44-159">**어떤 컴퓨터에서 이 작업을 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e7c44-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="e7c44-160">eDiscovery 내보내기 도구를 실행한 로컬 컴퓨터에서 레지스트리 설정을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="e7c44-161">**이 설정을 변경한 후 컴퓨터를 다시 시작해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e7c44-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="e7c44-162">아니요. 컴퓨터를 다시 시작할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="e7c44-163">그러나 eDiscovery 내보내기 도구가 실행 중인 경우 레지스트리 설정을 변경한 후 해당 도구를 닫은 다음 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="e7c44-164">**기존 레지스트리 키가 편집되거나 새 키가 만들어지나요?**</span><span class="sxs-lookup"><span data-stu-id="e7c44-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="e7c44-165">이 항목의 절차에서 만든 .reg 파일을 처음 실행할 때 새 레지스트리 키가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="e7c44-166">그런 다음 .reg 편집 파일을 변경하고 다시 실행할 때마다 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c44-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
