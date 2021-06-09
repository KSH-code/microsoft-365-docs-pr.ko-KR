---
title: eDiscovery 검색 결과를 내보낼 때 PST 파일의 크기 변경
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: eDiscovery 검색 결과를 내보낼 때 컴퓨터에 다운로드되는 PST 파일의 기본 크기를 변경할 수 있습니다.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942921"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="01a10-103">eDiscovery 검색 결과를 내보낼 때 PST 파일의 크기 변경</span><span class="sxs-lookup"><span data-stu-id="01a10-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="01a10-104">eDiscovery 내보내기 도구를 사용하여 다른 Microsoft eDiscovery 도구에서 eDiscovery 검색의 전자 메일 결과를 내보내는 경우 내보낼 수 있는 PST 파일의 기본 크기는 10GB입니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="01a10-105">이 기본 크기를 변경하려면 검색 결과를 내보내는 데 사용하는 Windows 레지스트리를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="01a10-106">이 작업을 하는 한 가지 이유는 PST 파일이 DVD, 컴팩트 디스크 또는 USB 드라이브와 같은 이동식 미디어에 맞을 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="01a10-107">eDiscovery 내보내기 도구는 보안 & 준수 센터, In-Place eDiscovery 및 Exchange Online Online의 eDiscovery 센터에서 콘텐츠 검색 도구를 사용할 때 검색 결과를 내보내는 SharePoint 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="01a10-108">eDiscovery 검색 결과를 내보낼 때 PST 파일의 크기를 변경하는 레지스트리 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="01a10-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="01a10-109">eDiscovery 검색 결과를 내보내는 데 사용할 컴퓨터에서 다음 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="01a10-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="01a10-110">eDiscovery 내보내기 도구가 열려 있는 경우 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="01a10-111">.reg의 파일 이름 접미사로 다음 텍스트를 Window 레지스트리 파일에 저장합니다. 예를 들어 PstExportSize.reg와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="01a10-112">위의 예제에서 값은  `PstSizeLimitInBytes` 1,073,741,824바이트 또는 약 1GB로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="01a10-113">다음은 설정에 대한 몇 가지 다른 샘플  `PstSizeLimitInBytes` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="01a10-114">**크기(약 GB)**</span><span class="sxs-lookup"><span data-stu-id="01a10-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="01a10-115">**크기(bytes)**</span><span class="sxs-lookup"><span data-stu-id="01a10-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="01a10-116">0.7GB(700MB)</span><span class="sxs-lookup"><span data-stu-id="01a10-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="01a10-117">751619277</span><span class="sxs-lookup"><span data-stu-id="01a10-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="01a10-118">2GB</span><span class="sxs-lookup"><span data-stu-id="01a10-118">2 GB</span></span>  <br/> |<span data-ttu-id="01a10-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="01a10-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="01a10-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="01a10-120">4 GB</span></span>  <br/> |<span data-ttu-id="01a10-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="01a10-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="01a10-122">8GB</span><span class="sxs-lookup"><span data-stu-id="01a10-122">8 GB</span></span>  <br/> |<span data-ttu-id="01a10-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="01a10-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="01a10-124">검색 결과를 내보낼 때 값을 원하는 최대 PST 파일 크기로 변경한 다음 `PstSizeLimitInBytes` 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="01a10-125">Windows 탐색기에서 이전 단계에서 만든 .reg 파일을 클릭하거나 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="01a10-126">사용자 액세스 제어 창에서 **예를** 클릭하여 레지스트리 편집기를 변경하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="01a10-127">계속할지 묻는 메시지가 표시될 때 예를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="01a10-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="01a10-128">레지스트리 편집기에는 설정이 레지스트리에 추가되었습니다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="01a10-129">3-6단계를 반복하여 레지스트리 설정 값을 변경할  `PstSizeLimitInBytes` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="01a10-130">eDiscovery 검색 결과를 내보낼 때 PST 파일의 기본 크기 변경에 대한 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="01a10-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="01a10-131">**기본 크기는 10GB인 이유는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="01a10-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="01a10-132">기본 크기인 10GB는 고객 의견을 기반으로 합니다. 10GB는 단일 PST에서 최적의 콘텐츠 양과 파일 손상 가능성이 가장 큰 균형입니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="01a10-133">**PST 파일의 기본 크기를 늘리거나 줄이세요?**</span><span class="sxs-lookup"><span data-stu-id="01a10-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="01a10-134">고객은 조직의 다른 위치로 물리적으로 발송할 수 있는 이동식 미디어에 검색 결과가 적합하게 크기 제한을 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="01a10-135">10GB보다 큰 PST 파일에 손상 문제가 있을 수 있기 때문에 기본 크기를 늘리지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="01a10-136">**어떤 컴퓨터에서 이 작업을 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="01a10-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="01a10-137">eDiscovery 내보내기 도구를 실행한 로컬 컴퓨터에서 레지스트리 설정을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="01a10-138">**이 설정을 변경한 후 컴퓨터를 다시 시작해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="01a10-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="01a10-139">아니요. 컴퓨터를 다시 시작하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="01a10-140">그러나 eDiscovery 내보내기 도구가 실행 중인 경우 이 설정을 변경한 후 도구를 닫고 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="01a10-141">**기존 레지스트리 키가 편집되거나 새 키가 만들어지나요?**</span><span class="sxs-lookup"><span data-stu-id="01a10-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="01a10-142">이 절차에서 만든 .reg 파일을 처음 실행할 때 새 레지스트리 키가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="01a10-143">그런 다음 .reg 편집 파일을 변경하고 다시 설정할 때마다 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="01a10-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
