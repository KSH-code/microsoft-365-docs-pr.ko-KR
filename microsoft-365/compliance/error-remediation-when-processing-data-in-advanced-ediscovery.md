---
title: 데이터를 처리할 때 오류 수정
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
description: 오류 수정을 사용하여 콘텐츠의 적절한 처리를 Advanced eDiscovery 데이터 문제를 수정하는 방법을 알아보겠습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 891e8292fca629669a48684e95f522c08838d3aa
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226662"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="5f2f9-103">데이터를 처리할 때 오류 수정</span><span class="sxs-lookup"><span data-stu-id="5f2f9-103">Error remediation when processing data</span></span>

<span data-ttu-id="5f2f9-104">오류 수정을 통해 eDiscovery 관리자는 콘텐츠가 제대로 처리되지 않도록 하는 데이터 문제를 Advanced eDiscovery 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="5f2f9-105">예를 들어 암호로 보호된 파일은 잠기거나 암호화된 파일을 처리하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="5f2f9-106">eDiscovery 관리자는 오류 수정을 사용하여 이러한 오류가 있는 파일을 다운로드하고 암호 보호를 제거한 다음 수정된 파일을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="5f2f9-107">다음 워크플로를 사용하여 오류가 있는 파일을 Advanced eDiscovery 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="5f2f9-108">오류 수정 세션을 만들어 처리 오류로 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-108">Create an error remediation session to remediate files with processing errors</span></span>

> [!NOTE]
> <span data-ttu-id="5f2f9-109">다음 절차 중에 오류 수정 마법사가 닫히면 보기 드롭다운 메뉴에서 수정을 선택하여 처리 탭에서  오류 수정 세션으로  돌아올 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="5f2f9-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="5f2f9-110">Advanced eDiscovery  사례의 처리 탭에서 보기 드롭다운 메뉴에서  오류를 선택한 다음 범위 드롭다운 메뉴에서 검토 집합 또는 전체 사례를 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="5f2f9-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="5f2f9-111">이 섹션에는 특정 검토 집합의 사례 또는 오류가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![오류 수정](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="5f2f9-113">오류 유형 또는 파일 형식 옆에 있는 라디오 단추를 클릭하여 수정하려는 오류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="5f2f9-114">다음 예제에서는 암호로 보호된 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="5f2f9-115">새 **오류 수정 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f2f9-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="5f2f9-116">오류 수정 워크플로는 오류가 있는 파일을 로컬 컴퓨터에 다운로드하여 수정하기 위해 Microsoft에서 제공하는 Azure Storage 위치에 복사하는 준비 단계로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![오류 수정 준비](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="5f2f9-118">준비가 완료되면 다음: 파일 **다운로드를** 클릭하여 다운로드를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![파일 다운로드](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="5f2f9-120">파일을 다운로드하려면 **다운로드 대상 경로** 를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="5f2f9-121">이는 로컬 컴퓨터의 상위 폴더에 대한 경로로, 파일이 이곳으로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="5f2f9-122">기본 경로인 %USERPROFILE%\Downloads\errors는 로그인한 사용자의 다운로드 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="5f2f9-123">원하는 경우 이 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-123">You can change this path if desired.</span></span> <span data-ttu-id="5f2f9-124">변경하는 경우 최상의 성능을 위해 로컬 파일 경로를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="5f2f9-125">원격 네트워크 경로를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-125">Don't use a remote network path.</span></span> <span data-ttu-id="5f2f9-126">예를 들어 **C:\Remediation 경로를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5f2f9-126">For example, you could use the path **C:\Remediation**.</span></span>

   <span data-ttu-id="5f2f9-127">부모 폴더의 경로는 자동으로 AzCopy 명령에 **/Dest** 매개 변수 값으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="5f2f9-128">**클립보드로 복사** 를 클릭하여 미리 정의된 명령을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="5f2f9-129">명령 프롬프트를 Windows 열고 AzCopy 명령을 붙여 넣은 다음 **Enter 를 누를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5f2f9-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>

    ![오류 수정 준비](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="5f2f9-131">파일 다운로드 페이지에 제공된 명령을 사용하려면 AzCopy v8.1을 **사용해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="5f2f9-132">또한 AzCopy v8.1을 사용하여 10단계에서 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="5f2f9-133">이 버전의 AzCopy를 설치하려면 에서 [AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 Windows.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="5f2f9-134">제공된 AzCopy 명령이 실패하면 에서 [AzCopy 문제 해결을 Advanced eDiscovery.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="5f2f9-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="5f2f9-135">선택한 파일이 5단계에서 지정한 위치로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="5f2f9-136">상위 폴더(예: **C:\Remediation**)에 다음 하위 폴더 구조가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="5f2f9-137">*Subfolder 1* 은 1단계에서 선택한 범위에 따라 사례 또는 검토 집합의 ID로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="5f2f9-138">*Subfolder 2* 는 다운로드한 파일의 파일 ID로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="5f2f9-139">다운로드한 파일은 *Subfolder 2* 에 있으며 파일 ID로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="5f2f9-140">다음은 항목을 **C:\Remediation** 부모 폴더로 다운로드할 때 생성되는 폴더 경로 및 오류 파일 이름의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="5f2f9-141">여러 파일이 다운로드되는 경우 각 파일이 파일 ID로 이름이 지정되는 하위 폴더로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5f2f9-142">9단계와 10단계에서 파일을 업로드할 때 수정된 파일은 동일한 파일 이름을 사용하며 동일한 하위 폴더 구조에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="5f2f9-143">하위 및 파일 이름은 수정된 파일을 원래 오류 파일과 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="5f2f9-144">폴더 구조 또는 파일 이름이 변경된 경우 다음 오류가 `Cannot apply Error Remediation to the current Workingset` 발생합니다. .</span><span class="sxs-lookup"><span data-stu-id="5f2f9-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="5f2f9-145">문제를 방지하려면 수정된 파일을 동일한 상위 폴더 및 하위 폴더 구조에 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="5f2f9-146">파일을 다운로드한 후 적절한 도구로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="5f2f9-147">암호로 보호된 파일의 경우 사용할 수 있는 몇 가지 암호 크래킹 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="5f2f9-148">파일의 암호를 알고 있는 경우 파일을 열고 암호 보호를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="5f2f9-149">파일 Advanced eDiscovery 수정 마법사로 돌아가 다음: 파일 업로드 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f2f9-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="5f2f9-150">이렇게 하면 파일을 업로드할 수 있는 다음 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-150">This moves to the next page where you can now upload the files.</span></span>

    ![업로드 파일](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="5f2f9-152">**파일 위치 경로** 텍스트 상자에서 수정된 파일이 있는 상위 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="5f2f9-153">다시 말하면 부모 폴더의 하위 폴더 구조는 파일을 다운로드할 때 만들어진 동일한 하위 폴더 구조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="5f2f9-154">부모 폴더의 경로는 자동으로 AzCopy 명령에 /Source 매개 변수 **값으로 추가됩니다.**</span><span class="sxs-lookup"><span data-stu-id="5f2f9-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="5f2f9-155">**클립보드로 복사** 를 클릭하여 미리 정의된 명령을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="5f2f9-156">명령 프롬프트를 Windows 열고 AzCopy 명령을 붙여 넣은 다음 **Enter 를 누를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5f2f9-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="5f2f9-157">파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-157">upload the files.</span></span>

    ![Azcopy에서 수정된 파일을 성공적으로 업로드한 결과](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="5f2f9-159">AzCopy 명령을 실행한 후 **다음: 파일 처리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f2f9-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="5f2f9-160">처리가 완료되면 집합을 검토하여 수정된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-160">When processing is complete, you can go to review set and view the remediated files.</span></span>

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="5f2f9-161">컨테이너 파일의 오류 수정</span><span class="sxs-lookup"><span data-stu-id="5f2f9-161">Remediating errors in container files</span></span>

<span data-ttu-id="5f2f9-162">.zip 파일과 같은 컨테이너 파일의 내용을 추출할 수 없는 Advanced eDiscovery 경우 컨테이너를 다운로드할 수 있으며 원본 컨테이너가 있는 동일한 폴더로 콘텐츠를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="5f2f9-163">확장된 파일은 원래 부모 컨테이너에 의해 확장된 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="5f2f9-164">이 프로세스는 단일 파일을 대체 파일로 업로드하는 경우를 제외하고 위에 설명된 대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="5f2f9-165">수정된 파일을 업로드할 때 원본 컨테이너 파일을 포함하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="5f2f9-166">추출된 텍스트를 업로드하여 오류 수정</span><span class="sxs-lookup"><span data-stu-id="5f2f9-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="5f2f9-167">경우에 따라 파일을 해석할 수 있는 기본 형식으로 파일을 Advanced eDiscovery 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="5f2f9-168">그러나 원본 파일을 기본 파일의 원본 텍스트(텍스트 오버레이라고 하는 프로세스)가 포함된 텍스트 파일로 *바꿀 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="5f2f9-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="5f2f9-169">이렇게하려면 이 문서에 설명된 단계를 따르지만 원본 파일을 기본 형식으로 수정하는 대신 원본 파일에서 추출된 텍스트가 포함된 텍스트 파일을 만든 다음 원본 접미사와 함께 추가된 원본 파일 이름을 사용하여 텍스트 파일을 .txt 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="5f2f9-170">예를 들어 파일 이름 335850cc-6602-4af0-acfa-1d14d9128ca2.abc를 통해 오류를 수정하는 동안 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="5f2f9-171">기본 응용 프로그램에서 파일을 열고 텍스트를 복사한 다음 이름이 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="5f2f9-172">이렇게 하는 경우 수정된 텍스트 파일을 로컬 컴퓨터의 수정된 파일 위치에서 기본 형식으로 제거한 후 수정된 텍스트 파일을 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="5f2f9-173">파일이 수정되는 경우 발생하는 일</span><span class="sxs-lookup"><span data-stu-id="5f2f9-173">What happens when files are remediated</span></span>

<span data-ttu-id="5f2f9-174">수정된 파일이 업로드될 때 다음 필드를 제외하고 원래 메타데이터가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2f9-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span>

- <span data-ttu-id="5f2f9-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="5f2f9-175">ExtractedTextSize</span></span>
- <span data-ttu-id="5f2f9-176">HasText</span><span class="sxs-lookup"><span data-stu-id="5f2f9-176">HasText</span></span>
- <span data-ttu-id="5f2f9-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="5f2f9-177">IsErrorRemediate</span></span>
- <span data-ttu-id="5f2f9-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="5f2f9-178">LoadId</span></span>
- <span data-ttu-id="5f2f9-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="5f2f9-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="5f2f9-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="5f2f9-180">ProcessingStatus</span></span>
- <span data-ttu-id="5f2f9-181">텍스트</span><span class="sxs-lookup"><span data-stu-id="5f2f9-181">Text</span></span>
- <span data-ttu-id="5f2f9-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="5f2f9-182">WordCount</span></span>
- <span data-ttu-id="5f2f9-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="5f2f9-183">WorkingsetId</span></span>

<span data-ttu-id="5f2f9-184">모든 메타데이터 필드에 대한 정의는 Advanced eDiscovery 메타데이터 필드 [를 참조합니다.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="5f2f9-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields-in-advanced-ediscovery.md).</span></span>