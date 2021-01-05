---
title: 단일 항목 오류 수정
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 대량 오류 수정 프로세스를 따를 필요 없이 Advanced eDiscovery의 검토 집합에서 문서의 처리 오류를 수정할 수 있습니다.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751585"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="57bf1-103">Advanced eDiscovery의 단일 항목 오류 수정</span><span class="sxs-lookup"><span data-stu-id="57bf1-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="57bf1-104">오류 수정을 통해 Advanced eDiscovery 사용자는 Advanced eDiscovery가 콘텐츠를 제대로 처리하지 못하게 하는 데이터 문제를 수정하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="57bf1-105">예를 들어 암호로 보호된 파일은 잠기거나 암호화되어 있기 때문에 처리될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="57bf1-106">이전에는 이 워크플로를 사용하여 대량으로 오류를 [수정해야만 합니다.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="57bf1-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="57bf1-107">그러나 경우에 따라 조사하고 있는 사례에 응답하는 파일이 없는 경우 여러 파일의 오류를 수정하는 것이 타당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="57bf1-108">또한 파일 메타데이터(예: 파일 위치 또는 액세스 권한이 있는 사용자)를 검토하여 응답성에 대한 선행 결정을 내리는 데 도움이 되기 전에 오류를 수정하는 것이 부적연할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="57bf1-109">단일 항목  오류 수정이라는 새로운 기능을 통해 eDiscovery 관리자는 처리 오류로 파일의 메타데이터를 보고 필요한 경우 검토 집합에서 직접 오류를 수정하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="57bf1-110">이 문서에서는 검토 집합에서 오류를 처리하여 파일을 식별, 무시 및 수정하는 방법에 대해 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="57bf1-111">오류가 있는 문서 식별</span><span class="sxs-lookup"><span data-stu-id="57bf1-111">Identify documents with errors</span></span>

<span data-ttu-id="57bf1-112">이제 검토 집합에서 오류를 처리하는 문서가 배너로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="57bf1-113">오류를 수정하거나 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="57bf1-114">다음 스크린샷은 암호로 보호된 검토 집합의 Word 문서에 대한 처리 오류 배너를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="57bf1-115">또한 처리 오류와 함께 문서의 파일 메타데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![처리 오류와 함께 문서에 대해 표시되는 배너](../media/SIERimage1.png)

<span data-ttu-id="57bf1-117">검토 집합에서 문서를 쿼리할 때 처리 상태  조건을 사용하여 처리 오류가 있는 문서를 검색할 [수도 있습니다.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="57bf1-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![처리 상태 조건을 사용하여 오류 문서 검색](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="57bf1-119">오류 무시</span><span class="sxs-lookup"><span data-stu-id="57bf1-119">Ignore errors</span></span>

<span data-ttu-id="57bf1-120">처리 오류 배너에서 **무시를** 클릭하여 처리 오류를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="57bf1-121">오류를 무시하면 대량 오류 수정 워크플로에서 [문서가 제거됩니다.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="57bf1-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="57bf1-122">오류가 무시되면 문서 배너의 색이 변경되고 처리 오류가 무시된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="57bf1-123">원하는 경우 되전을 클릭하여 오류를 무시할지 결정을 **되전할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="57bf1-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![처리 오류를 무시하려면 무시를 클릭합니다.](../media/SIERimage3.png)

<span data-ttu-id="57bf1-125">검토 집합에서 문서를 쿼리할 때 무시된 처리 오류 조건을  사용하여 처리 오류가 무시된 모든 문서를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![무시된 처리 오류 조건을 사용하여 무시된 오류 문서 검색](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="57bf1-127">오류로 문서 수정</span><span class="sxs-lookup"><span data-stu-id="57bf1-127">Remediate a document with errors</span></span>

<span data-ttu-id="57bf1-128">경우에 따라 암호 제거, 암호화된 파일 암호 해독 또는 손상된 문서 복구를 통해 문서의 처리 오류를 수정한 다음 수정된 문서를 검토 집합에 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="57bf1-129">이렇게 하면 오류 문서를 검토하고 검토 집합의 다른 문서와 함께 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="57bf1-130">단일 문서를 수정하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="57bf1-131">원본 **다운로드를** 클릭하여 파일 복사본을 로컬 컴퓨터에  >   다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![처리 오류와 함께 문서 다운로드](../media/SIERimage5.png)

2. <span data-ttu-id="57bf1-133">오프라인으로 파일의 오류를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="57bf1-134">암호 보호를 제거하려면 암호 해독 소프트웨어가 필요한 암호화된 파일의 경우 암호를 제공하고 파일을 저장하거나 암호 크래커를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="57bf1-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="57bf1-135">파일을 수정한 후 다음 단계로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="57bf1-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="57bf1-136">검토 집합에서 수정한 처리 오류가 있는 파일을 선택하고 **수정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="57bf1-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![처리 오류로 문서 배너에서 수정 클릭](../media/SIERimage6.png)


4. <span data-ttu-id="57bf1-138">**찾아보기를** 클릭하고 로컬 컴퓨터에서 수정된 파일의 위치로 이동한 다음 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![찾아보기를 클릭하고 로컬 컴퓨터에서 수정된 파일 선택](../media/SIERimage7.png)

    <span data-ttu-id="57bf1-140">수정된 파일을 선택한 후 검토 집합에 자동으로 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="57bf1-141">파일의 처리 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-141">You can track the processing status of the file.</span></span>

    ![업데이트 관리 프로세스의 상태가 표시됩니다.](../media/SIERimage8.png)

   <span data-ttu-id="57bf1-143">처리가 완료되면 수정된 문서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-143">After processing is completed, you can view the remediated document.</span></span>

    ![검토 집합에서 수정된 파일을 기본 형식으로 볼 수 있습니다.](../media/SIERimage9.png)

<span data-ttu-id="57bf1-145">문서가 수정되는 경우 발생하는 일에 대한 자세한 내용은 파일을 수정하면 [어떻게 될지 참조하세요.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)</span><span class="sxs-lookup"><span data-stu-id="57bf1-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="57bf1-146">수정된 문서 검색</span><span class="sxs-lookup"><span data-stu-id="57bf1-146">Search for remediated documents</span></span>

<span data-ttu-id="57bf1-147">키워드 조건을 사용하고 **IsFromErrorRemediation:true** 속성을  지정하여 수정된 검토 집합의 모든 문서를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="57bf1-148">이 속성은 검토 집합에서 문서를 내보낼 때 로드 파일 내보내기에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57bf1-148">This property is also available in the export load file when you export documents from a review set.</span></span>
