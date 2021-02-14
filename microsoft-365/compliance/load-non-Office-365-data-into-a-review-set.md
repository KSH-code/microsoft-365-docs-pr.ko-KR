---
title: 검토 집합에 비 Microsoft 365 데이터 로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery 사례에서 분석용 검토 집합으로 비 Microsoft 365 데이터를 가져오는 방법을 자세히 알아보는 방법을 참조합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad70207bdc015107a5aba074e2df06a42c0618b3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285864"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="be1c6-103">검토 집합에 비 Microsoft 365 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="be1c6-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="be1c6-104">Advanced eDiscovery에서 분석해야 하는 모든 문서가 Microsoft 365에 있는 것은 아니며,</span><span class="sxs-lookup"><span data-stu-id="be1c6-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="be1c6-105">Advanced eDiscovery의 비 Microsoft 365 데이터 가져오기 기능을 사용하면 Microsoft 365에 없는 문서를 검토 집합에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="be1c6-106">이 문서에서는 분석을 위해 Microsoft 365가 아닌 문서를 Advanced eDiscovery로 가져오는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="be1c6-107">비 Office 365 콘텐츠를 업로드하기 위해 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be1c6-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="be1c6-108">이 문서에 설명된 비 Microsoft 365 업로드 기능을 사용하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="be1c6-109">Microsoft 365가 아닌 콘텐츠를 연결하려는 모든 관리인에게 적절한 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="be1c6-110">자세한 내용은 [Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)시작을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be1c6-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="be1c6-111">기존 Advanced eDiscovery 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="be1c6-112">Microsoft 365가 아닌 데이터를 업로드하고 연결하려면 먼저 해당 사례에 정보를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="be1c6-113">Microsoft 365가 아닌 데이터는 Advanced eDiscovery에서 지원하는 파일 형식이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="be1c6-114">자세한 내용은 [Advanced eDiscovery의 지원되는 파일 형식을 참조하세요.](supported-filetypes-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="be1c6-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="be1c6-115">검토 집합에 업로드된 모든 파일은 폴더에 있어야 합니다. 폴더는 각 폴더가 특정 관할권과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="be1c6-116">이러한 폴더의 이름은 다음 이름 지정 *형식을* alias@domainname.</span><span class="sxs-lookup"><span data-stu-id="be1c6-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="be1c6-117">이 alias@domainname 사용자의 Microsoft 365 별칭 및 도메인이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="be1c6-118">루트 폴더의 모든 alias@domainname 폴더를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="be1c6-119">루트 폴더는 해당 폴더만 alias@domainname 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="be1c6-120">루트 폴더의 느슨한 파일은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="be1c6-121">업로드할 Microsoft 365가 아닌 데이터의 폴더 구조는 다음 예제와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="be1c6-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="be1c6-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="be1c6-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="be1c6-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="be1c6-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="be1c6-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="be1c6-125">여기서 abraham.mcmahon@contoso.com, jewell.gordon@contoso.com 및 staci.gonzalez@contoso.com 위치는 거래소의 SMTP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![비 Microsoft 365 데이터 업로드 폴더 구조](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="be1c6-127">eDiscovery 관리자 역할 그룹에 할당되어 eDiscovery 관리자로 추가된 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="be1c6-128">Microsoft 365가 아닌 콘텐츠 폴더 구조에 액세스할 수 있는 컴퓨터에 설치된 AzCopy v8.1 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="be1c6-129">AzCopy를 설치하려면 [Windows에서 AzCopy v8.1을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 전송을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="be1c6-130">**%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy인 기본 위치에 AzCopy를 설치해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="be1c6-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="be1c6-131">AzCopy v8.1을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="be1c6-132">Advanced eDiscovery에서 Microsoft 365가 아닌 데이터를 로드할 때 다른 버전의 AzCopy가 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="be1c6-133">Advanced eDiscovery에 Microsoft 365가 아닌 콘텐츠 업로드</span><span class="sxs-lookup"><span data-stu-id="be1c6-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="be1c6-134">eDiscovery 관리자 또는 eDiscovery 관리자로서 Advanced eDiscovery를 열고 Microsoft 365가 아닌 데이터가 업로드되는 경우로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="be1c6-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="be1c6-135">검토 **집합을 클릭한** 다음 검토 집합을 선택하여 비 Microsoft 365 데이터를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="be1c6-136">리뷰 집합이 없는 경우 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="be1c6-137">검토 집합에서 검토 집합 관리를 **클릭한** 다음 비 **Microsoft 365** 데이터 타일에서 업로드 보기를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="be1c6-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="be1c6-138">파일 **업로드를 클릭하여** 데이터 가져오기 마법사를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-138">Click **Upload files** to start the data import wizard.</span></span>

   ![파일 업로드](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="be1c6-140">마법사의 첫 번째 단계에서는 파일을 업로드할 보안 Microsoft 제공 Azure Storage 위치를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="be1c6-141">준비가 완료되면 **다음:** 파일 업로드 단추가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![비 Microsoft 365 가져오기: 준비](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="be1c6-143">다음을 **클릭합니다. 파일 업로드.**</span><span class="sxs-lookup"><span data-stu-id="be1c6-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="be1c6-144">파일 **업로드 페이지에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-144">On the **Upload files** page, do the following:</span></span>

   ![비 Microsoft 365 가져오기: 파일 업로드](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="be1c6-146">a.</span><span class="sxs-lookup"><span data-stu-id="be1c6-146">a.</span></span> <span data-ttu-id="be1c6-147">파일 **위치** 경로 상자에서 업로드할 Microsoft 365 이 아닌 데이터를 저장한 루트 폴더의 위치를 확인하거나 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="be1c6-148">예를 들어 시작하기 전에 섹션에 표시된 예제 파일의 위치에 **%USERPROFILE\Downloads\nonO365를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="be1c6-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="be1c6-149">올바른 위치를 제공하면 경로 아래에 상자에 표시된 AzCopy 명령이 제대로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="be1c6-150">b.</span><span class="sxs-lookup"><span data-stu-id="be1c6-150">b.</span></span> <span data-ttu-id="be1c6-151">**클립보드에 복사를 클릭하여** 상자에 표시되는 명령을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="be1c6-152">Windows 명령 프롬프트를 시작하고 이전 단계에서 복사한 명령을 붙여 넣은 다음 **Enter를** 눌러 AzCopy 명령을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="be1c6-153">명령을 시작하면 Microsoft 365가 아닌 파일이 4단계에서 준비된 Azure Storage 위치에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![비 Microsoft 365 가져오기: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="be1c6-155">앞서 언급했듯이 파일 업로드 페이지에 제공된 명령을 사용하려면 AzCopy v8.1을 **사용하여 성공적으로 실행해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="be1c6-156">제공된 AzCopy 명령이 실패하면 [Advanced eDiscovery에서 AzCopy 문제 해결을 참조합니다.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="be1c6-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="be1c6-157">보안 및 & 센터로 돌아가 **다음: 마법사에서** 파일 처리를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="be1c6-158">그러면 Azure Storage 위치에 업로드된 Microsoft가 아닌 다른 365 파일의 처리, 텍스트 추출 및 인덱싱이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="be1c6-159">검토 집합에 비 Microsoft  365 데이터  추가라는 작업을 확인하여 프로세스 파일 페이지 또는 작업 탭에서 파일 처리 진행률을 **추적합니다.**</span><span class="sxs-lookup"><span data-stu-id="be1c6-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="be1c6-160">작업이 완료되면 검토 집합에서 새 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![비 Microsoft 365 가져오기: 파일 처리](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="be1c6-162">처리가 완료되면 마법사를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1c6-162">After the processing is finished, you can close the wizard.</span></span>
