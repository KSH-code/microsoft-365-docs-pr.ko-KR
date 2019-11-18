---
title: 단일 항목 오류 수정
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
description: 고급 eDiscovery의 검토 집합에 포함 된 문서에서 대량 오류 업데이트 관리 프로세스를 수행 하지 않고도 처리 오류를 해결할 수 있습니다.
ms.openlocfilehash: 922c0e4b0ab30bae6507fac7e97080a5951ea750
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38687121"
---
# <a name="single-item-error-remediation"></a><span data-ttu-id="d0d9f-103">단일 항목 오류 수정</span><span class="sxs-lookup"><span data-stu-id="d0d9f-103">Single item error remediation</span></span>

<span data-ttu-id="d0d9f-104">오류 수정을 통해 고급 eDiscovery 사용자는 고급 eDiscovery가 콘텐츠를 제대로 처리 하지 못하게 하는 데이터 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="d0d9f-105">예를 들어 암호로 보호 된 파일은 잠겨 있거나 암호화 되어 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="d0d9f-106">이전에는 [이 워크플로](error-remediation-when-processing-data-in-advanced-ediscovery.md)를 사용 하 여 대량 으로만 오류를 수정할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d0d9f-107">그러나 조사 중인 사례에 대응 되는 파일이 있는지 확실 하지 않은 경우에는 여러 파일의 오류를 수정 하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="d0d9f-108">또한 파일 위치 또는 액세스 권한이 있는 파일 메타 데이터를 검토 하 여 응답성에 대 한 사전 결정을 내리는 데 도움이 되도록 오류를 수정 하는 것은 바람직하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="d0d9f-109">*단일 항목 오류 수정* 프로그램 이라는 새로운 기능을 통해 eDiscovery 관리자는 처리 오류가 발생 한 파일의 메타 데이터를 볼 수 있으며, 필요한 경우 검토 집합에서 오류를 직접 수정 하는 기능이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="d0d9f-110">이 문서에서는 검토 집합에서 처리 오류가 발생 한 파일을 식별, 무시 및 수정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="d0d9f-111">오류가 있는 문서 확인</span><span class="sxs-lookup"><span data-stu-id="d0d9f-111">Identify documents with errors</span></span>

<span data-ttu-id="d0d9f-112">검토 집합에서 처리 오류가 발생 한 문서가 배너를 통해 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="d0d9f-113">오류를 수정 하거나 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="d0d9f-114">다음 스크린샷은 검토 중에 암호로 보호 된 Word 문서에 대 한 처리 오류 배너를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="d0d9f-115">또한 처리 오류가 있는 문서의 파일 메타 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![처리 오류가 있는 문서에 대해 표시 되는 배너](media/SIERimage1.png)

<span data-ttu-id="d0d9f-117">[검토 집합에서 문서를 쿼리할](review-set-search.md)때 **처리 상태** 조건을 사용 하 여 처리 오류가 있는 문서를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![처리 상태 조건을 사용 하 여 오류 문서 검색](media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="d0d9f-119">오류 무시</span><span class="sxs-lookup"><span data-stu-id="d0d9f-119">Ignore errors</span></span>

<span data-ttu-id="d0d9f-120">처리 오류 배너에서 **건너뛰기를** 클릭 하 여 처리 오류를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="d0d9f-121">오류를 무시 하면 문서가 [대량 오류 수정 워크플로](error-remediation-when-processing-data-in-advanced-ediscovery.md)에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d0d9f-122">오류가 무시 되 면 문서 배너가 색이 변경 되 고 처리 오류가 무시 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="d0d9f-123">언제 든 지 **되돌리기를**클릭 하 여 오류를 무시 하도록 결정을 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![처리 오류를 무시 하려면 Ignore를 클릭 합니다.](media/SIERimage3.png)

<span data-ttu-id="d0d9f-125">검토 집합에서 문서를 쿼리할 때 *처리 오류 무시* 조건을 사용 하 여 처리 오류가 발생 한 모든 문서를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![무시 된 오류 문서를 검색 하는 데 필요한 문제 처리 오류 조건을 사용 합니다.](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="d0d9f-127">오류가 있는 문서 수정</span><span class="sxs-lookup"><span data-stu-id="d0d9f-127">Remediate a document with errors</span></span>

<span data-ttu-id="d0d9f-128">경우에 따라 문서에서 암호를 제거 하 고 암호화 된 파일의 암호를 해독 하거나 손상 된 문서를 복구 하는 방법으로 처리 오류를 수정 하 고 검토 집합에 재구성 된 문서를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="d0d9f-129">이를 통해 오류 문서를 검토 하 고 검토 집합의 다른 문서와 함께 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="d0d9f-130">단일 문서를 수정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="d0d9f-131">**원본 다운로드** **다운로드** > 를 클릭 하 여 로컬 컴퓨터에 파일의 복사본을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![처리 오류와 함께 문서 다운로드](media/SIERimage5.png)

2. <span data-ttu-id="d0d9f-133">오프 라인 파일에서 오류를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="d0d9f-134">암호화 된 파일의 경우 암호 보호를 제거 하려면 암호를 입력 하 고 파일을 저장 하거나 암호 해독을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="d0d9f-135">파일을 수정 했으면 다음 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="d0d9f-136">검토 집합에서 재구성 한 처리 오류가 있는 파일을 선택 하 고 **수정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![처리 오류가 있는 문서의 배너에서 업데이트를 클릭 합니다.](media/SIERimage6.png)


4. <span data-ttu-id="d0d9f-138">**찾아보기를**클릭 하 고 로컬 컴퓨터에서 재구성 된 파일 위치로 이동한 다음 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![찾아보기를 클릭 하 고 로컬 컴퓨터에서 재구성 한 파일을 선택 합니다.](media/SIERimage7.png)

    <span data-ttu-id="d0d9f-140">재구성 된 파일을 선택 하면 해당 파일이 검토 집합에 자동으로 업로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="d0d9f-141">파일의 처리 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-141">You can track the processing status of the file.</span></span>

    ![업데이트 관리 프로세스의 상태가 표시 됩니다.](media/SIERimage8.png)

   <span data-ttu-id="d0d9f-143">처리가 완료 되 면 재구성 된 문서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-143">After processing is completed, you can view the remediated document.</span></span>

    ![재구성 한 파일을 검토 집합의 기본 형식으로 볼 수 있습니다.](media/SIERimage9.png)

<span data-ttu-id="d0d9f-145">문서를 수정 하는 경우 수행 되는 작업에 대 한 자세한 내용은 파일을 수정 [했을 때 수행 되는 작업](error-remediation.md#what-happens-when-files-are-remediated)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="d0d9f-146">재구성 한 문서 검색</span><span class="sxs-lookup"><span data-stu-id="d0d9f-146">Search for remediated documents</span></span>

<span data-ttu-id="d0d9f-147">**키워드** 조건을 사용 하 고 값 쌍: **Isfromerrorremediation: true**속성을 지정 하 여 검토 집합에서 재구성 된 모든 문서를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="d0d9f-148">이 속성은 문서를 검토 집합에서 내보낼 때 내보내기 로드 파일 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d9f-148">This property is also available in the export load file when you export documents from a review set.</span></span>
