---
title: 고급 eDiscovery 분석을 위해 Microsoft 제품이 아닌 365 콘텐츠 가져오기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: AeD로 분석할 수 있도록 Microsoft 365에 저장 되어 있지 않은 콘텐츠를 Azure blob에 가져오는 방법에 대 한 설명
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636955"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="ad8e4-103">고급 eDiscovery에 대 한 비 Microsoft 365 콘텐츠 가져오기 (클래식) 분석</span><span class="sxs-lookup"><span data-stu-id="ad8e4-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="ad8e4-104">고급 eDiscovery를 사용 하 여 분석을 수행 하는 데 필요한 모든 문서는 Microsoft 365에서 살고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="ad8e4-105">고급 eDiscovery의 타사 365 콘텐츠 가져오기 기능을 사용 하 여 PST 파일을 제외한 Microsoft 365에 없는 문서를 연결 된 Azure storage blob에 업로드 하 고 고급 eDiscovery로 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="ad8e4-106">이 절차에서는 Microsoft 이외의 365 문서를 분석을 위해 고급 eDiscovery로 가져오는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad8e4-p102">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ad8e4-109">Microsoft 제품이 아닌 365 콘텐츠에 대 한 고급 eDiscovery 데이터 저장소 추가 기능 구독을 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="ad8e4-110">이 기능은 고급 eDiscovery를 사용 하 여 분석 되는 콘텐츠에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="ad8e4-111">[비즈니스용 Microsoft 365에 대 한 추가 기능 구입 또는 편집](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) 의 단계를 따르고, 고급 eDiscovery 저장소 추가 기능을 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="ad8e4-112">Office 이외의 365 콘텐츠를 업로드 하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad8e4-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="ad8e4-113">이 절차에 설명 된 대로 Office 이외에 업로드 365 기능을 사용 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="ad8e4-114">고급 규정 준수 추가 기능 또는 E5 구독을 포함 하는 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="ad8e4-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="ad8e4-115">비 Office 365 콘텐츠가 업로드 되는 모든 custodians에는 고급 규정 준수 추가 기능 또는 E5 라이선스가 포함 된 E3이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="ad8e4-116">기존 eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="ad8e4-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="ad8e4-117">업로드 하기 위한 모든 파일은 custodian 당 하나의 폴더가 있고 폴더 이름이이 형식  *alias@domainname*  으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="ad8e4-118">*Alias@domainname* 사용자의 Office 365 별칭과 domain 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="ad8e4-119">모든  *alias@domainname*  폴더를 루트 폴더로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="ad8e4-120">루트 폴더에는  *alias@domainname*  폴더만 포함할 수 있으며 루트 폴더에는 느슨한 파일이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="ad8e4-121">EDiscovery 관리자 또는 eDiscovery 관리자 인 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="ad8e4-122">Office가 아닌 365 콘텐츠 폴더 구조에 대 한 액세스 권한이 있는 컴퓨터에 설치 된 [Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) 입니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="ad8e4-123">Office 이외의 365 콘텐츠를 고급 eDiscovery에 업로드</span><span class="sxs-lookup"><span data-stu-id="ad8e4-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="ad8e4-124">Ediscovery 관리자 또는 eDiscovery 관리자로 서 **ediscovery**를 열고 비 Office 365 데이터가 업로드 될 사례를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="ad8e4-125">사례를 만들어야 하는 경우 [에는 보안 및 &amp; 준수 센터에서 EDiscovery 사례 관리](ediscovery-cases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="ad8e4-126">**고급 eDiscovery로 전환을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="ad8e4-127">메뉴에서 **검토 집합** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="ad8e4-128">기존 검토 집합을 선택 하거나 **검토 설정 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="ad8e4-129">**검토 설정 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="ad8e4-130">비 Office 365 데이터 카드에서 **업로드 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="ad8e4-131">**업로드 파일** 을 선택 하 여 파일 업로드 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="ad8e4-132">첫 번째 탭은 **1입니다. 준비 단계**</span><span class="sxs-lookup"><span data-stu-id="ad8e4-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="ad8e4-133">**다음: 파일 업로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="ad8e4-134">**2. 파일 업로드** 탭 아직 완료 하지 않은 경우 AzCopy.exe 다운로드 한 다음 파일 위치에 대 한 경로를 제공 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="ad8e4-135">예를 들어 `C:\Upload`  AzCopy.exe 실행 하는 명령을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="ad8e4-136">`C:\Upload`를 사용 하면 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="ad8e4-137">명령 프롬프트 창을 열고 AzCopy.exe 명령을 실행 하 여 Azure로 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="ad8e4-138">모든 데이터를 로드 한 후에는 **다음: 프로세스 파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="ad8e4-139">다음 탭은 \*\*3입니다. \*\* 데이터를 포함 하는 custodians를 보게 되는 프로세스 파일과 가져올 데이터의 진행 상황도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="ad8e4-140">Azcopy 구문에 대 한 자세한 내용은 [Transfer data with a Windows Azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="ad8e4-141">고급 eDiscovery 처리에 대 한 자세한 내용은 [프로세스 모듈 실행 및 고급 ediscovery에서 데이터 로드 (클래식)](run-the-process-module-and-load-data-in-advanced-ediscovery.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ad8e4-142">사용자 마다 루트 폴더가 하나씩 있어야 하며 폴더 이름은 <b>alias@domainname</b>  형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="ad8e4-143">고급 eDiscovery에서 컨테이너를 성공적으로 처리 하면 더 이상 Azure의 SAS 저장소에 새 콘텐츠를 추가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="ad8e4-144">추가 콘텐츠를 수집 하 고 고급 eDiscovery 분석을 위해 사례에 추가 하려는 경우에는 **365 Office가 아닌 새 데이터** 컨테이너를 만들고이 절차를 반복 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="ad8e4-145">*폴더 명명 문제로 인해 컨테이너가 제대로 처리 되지* 않는 경우 문제를 해결 하는 경우에도이 문서의 절차에 따라 새 컨테이너를 만들고 다시 연결 하 고 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad8e4-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
