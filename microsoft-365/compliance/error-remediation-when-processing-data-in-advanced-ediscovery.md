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
description: 오류 수정을 사용하여 콘텐츠를 올바르게 처리하지 못하게 할 수 있는 Advanced eDiscovery의 데이터 문제를 수정하는 방법을 알아보겠습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6ef1076e44fca0d060d766fc85a435550c40059
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750801"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="2f577-103">데이터를 처리할 때 오류 수정</span><span class="sxs-lookup"><span data-stu-id="2f577-103">Error remediation when processing data</span></span>

<span data-ttu-id="2f577-104">오류 수정을 통해 eDiscovery 관리자는 Advanced eDiscovery가 콘텐츠를 제대로 처리하지 못하게 하는 데이터 문제를 수정하는 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="2f577-105">예를 들어 파일이 잠기거나 암호화되어 암호로 보호된 파일은 처리될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="2f577-106">eDiscovery 관리자는 오류 수정을 사용하여 이러한 오류가 있는 파일을 다운로드하고 암호 보호를 제거한 다음 수정된 파일을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="2f577-107">Advanced eDiscovery 사례에서 오류가 있는 파일을 수정하려면 다음 워크플로를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2f577-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="2f577-108">오류 처리 오류로 파일을 수정하는 오류 수정 세션 만들기</span><span class="sxs-lookup"><span data-stu-id="2f577-108">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="2f577-109">다음 절차 중 오류 수정 마법사가 닫히면 보기 드롭다운 메뉴에서 수정을 선택하여 처리 탭에서  오류 수정 세션으로  돌아올 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="2f577-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="2f577-110">Advanced  eDiscovery 사례의 처리 탭에 있는 보기  드롭다운 메뉴에서 오류를 선택한 다음 범위 드롭다운  메뉴에서 검토 집합 또는 전체 사례를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="2f577-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="2f577-111">이 섹션에는 특정 검토 집합의 사례 또는 오류에 대한 모든 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![오류 수정](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="2f577-113">오류 유형 또는 파일 형식 옆에 있는 라디오 단추를 클릭하여 수정하려는 오류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="2f577-114">다음 예제에서는 암호로 보호된 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="2f577-115">새 **오류 수정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="2f577-116">오류 수정 워크플로는 오류가 있는 파일이 Microsoft에서 제공한 Azure Storage 위치로 복사되어 수정을 위해 로컬 컴퓨터에 다운로드할 수 있는 준비 단계로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![오류 수정 준비](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="2f577-118">준비가 완료되면 다음: 파일 **다운로드를** 클릭하여 다운로드를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![파일 다운로드](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="2f577-120">파일을 다운로드하려면 다운로드할 **대상 경로를 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="2f577-121">파일을 다운로드할 로컬 컴퓨터의 상위 폴더 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="2f577-122">기본 경로인 %USERPROFILE%\Downloads\errors는 로그인한 사용자의 다운로드 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="2f577-123">원하는 경우 이 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-123">You can change this path if desired.</span></span> <span data-ttu-id="2f577-124">변경하는 경우 최상의 성능을 위해 로컬 파일 경로를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="2f577-125">원격 네트워크 경로를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-125">Don't use a remote network path.</span></span> <span data-ttu-id="2f577-126">예를 들어 **C:\Remediation 경로를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-126">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="2f577-127">부모 폴더의 경로는 자동으로 AzCopy 명령에 **추가됩니다(/Dest** 매개 변수의 값).</span><span class="sxs-lookup"><span data-stu-id="2f577-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="2f577-128">클립보드에 복사를 클릭하여 미리 정의한 **명령을 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="2f577-129">Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 Enter 를 **누르고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![오류 수정 준비](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="2f577-131">파일 다운로드 페이지에 제공된 명령을 사용하려면 AzCopy v8.1을 사용하여 성공적으로 **실행해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="2f577-132">또한 AzCopy v8.1을 사용하여 10단계에서 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="2f577-133">이 버전의 AzCopy를 설치하려면 [Windows에서 AzCopy v8.1을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 전송을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="2f577-134">제공된 AzCopy 명령이 실패하면 [Advanced eDiscovery에서 AzCopy 문제 해결을 참조합니다.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="2f577-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="2f577-135">선택한 파일은 5단계에서 지정한 위치로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="2f577-136">상위 폴더(예: **C:\Remediation)에** 다음과 같은 하위 폴더 구조가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="2f577-137">*하위폴더 1의* 이름은 1단계에서 선택한 범위에 따라 사례 또는 검토 집합의 ID로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="2f577-138">*하위 파일 2의* 이름이 다운로드한 파일의 파일 ID로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="2f577-139">다운로드한 파일은 하위 파일 *2에* 있으며 파일 ID로도 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="2f577-140">다음은 항목을 **C:\Remediation** 상위 폴더로 다운로드할 때 생성되는 폴더 경로 및 오류 파일 이름의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="2f577-141">여러 파일이 다운로드되는 경우 각 파일이 파일 ID로 이름이 지정된 하위 폴더로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2f577-142">9단계와 10단계에서 파일을 업로드할 때 수정된 파일은 동일한 파일 이름을 들이고 동일한 하위 폴더 구조에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="2f577-143">하위 파일 및 파일 이름은 수정된 파일을 원래 오류 파일과 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="2f577-144">폴더 구조 또는 파일 이름이 변경된 경우 다음 오류가 `Cannot apply Error Remediation to the current Workingset` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="2f577-145">문제를 방지하려면 수정된 파일을 동일한 상위 폴더 및 하위 폴더 구조에 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="2f577-146">파일을 다운로드한 후 적절한 도구로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="2f577-147">암호로 보호된 파일의 경우 사용할 수 있는 여러 암호 크래킹 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="2f577-148">파일의 암호를 알고 있는 경우 파일을 열고 암호 보호를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="2f577-149">Advanced eDiscovery 및 오류 수정 마법사로 돌아가 **다음: 파일 업로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="2f577-150">이제 파일을 업로드할 수 있는 다음 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-150">This moves to the next page where you can now upload the files.</span></span>

    ![파일 업로드](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="2f577-152">수정된 파일이 파일의 경로 텍스트 상자에 **있는** 상위 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="2f577-153">다시 말하면 부모 폴더는 파일을 다운로드할 때 만들어진 하위 폴더 구조와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="2f577-154">부모 폴더의 경로는 AzCopy 명령에 **자동으로 추가됩니다(/Source** 매개 변수의 값).</span><span class="sxs-lookup"><span data-stu-id="2f577-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="2f577-155">클립보드에 복사를 클릭하여 미리 정의한 **명령을 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="2f577-156">Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 Enter 를 **누르고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="2f577-157">파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-157">upload the files.</span></span>

    ![Azcopy에서 수정된 파일을 성공적으로 업로드한 결과](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="2f577-159">AzCopy 명령을 실행한 후 **다음: 파일 처리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f577-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="2f577-160">처리가 완료되면 검토 집합으로 이동하여 수정된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-160">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="2f577-161">컨테이너 파일의 오류 수정</span><span class="sxs-lookup"><span data-stu-id="2f577-161">Remediating errors in container files</span></span>

<span data-ttu-id="2f577-162">Advanced eDiscovery에서 컨테이너 파일(예: .zip 파일)의 내용을 추출할 수 없는 경우 컨테이너를 다운로드할 수 있으며 원본 컨테이너가 있는 폴더로 콘텐츠를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="2f577-163">확장된 파일은 원래 Advanced eDiscovery에 의해 확장된 것 같은 부모 컨테이너에 기인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="2f577-164">이 프로세스는 단일 파일을 대체 파일로 업로드하는 경우를 제외하고 위에 설명된 대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="2f577-165">수정된 파일을 업로드할 때 원본 컨테이너 파일을 포함하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2f577-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="2f577-166">추출된 텍스트를 업로드하여 오류 수정</span><span class="sxs-lookup"><span data-stu-id="2f577-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="2f577-167">Advanced eDiscovery에서 해석할 수 있는 네이티브 형식으로 파일을 수정하지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="2f577-168">그러나 원본 파일을 기본 파일의 원본 텍스트가 포함된 텍스트 파일(텍스트 오버레이라고 하는 프로세스)으로 바꿀 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="2f577-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="2f577-169">이렇게하려면 이 문서에 설명된 단계를 따르지만 원본 파일을 기본 형식으로 수정하는 대신 원본 파일에서 추출된 텍스트가 포함된 텍스트 파일을 만든 다음 .txt 접미사와 함께 추가된 원본 파일 이름을 사용하여 텍스트 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="2f577-170">예를 들어 파일 이름을 335850cc-6602-4af0-acfa-1d14d9128ca2.abc로 수정하는 동안 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="2f577-171">기본 응용 프로그램에서 파일을 열고 텍스트를 복사한 다음 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span><span class="sxs-lookup"><span data-stu-id="2f577-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="2f577-172">이렇게 하는 경우 수정된 텍스트 파일을 Advanced eDiscovery에 업로드하기 전에 로컬 컴퓨터의 수정된 파일 위치에서 원본 파일을 기본 형식으로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="2f577-173">파일이 수정되는 경우 발생하는 일</span><span class="sxs-lookup"><span data-stu-id="2f577-173">What happens when files are remediated</span></span>

<span data-ttu-id="2f577-174">수정된 파일이 업로드될 때 다음 필드를 제외한 원래 메타데이터가 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f577-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="2f577-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="2f577-175">ExtractedTextSize</span></span>
- <span data-ttu-id="2f577-176">HasText</span><span class="sxs-lookup"><span data-stu-id="2f577-176">HasText</span></span>
- <span data-ttu-id="2f577-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="2f577-177">IsErrorRemediate</span></span>
- <span data-ttu-id="2f577-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="2f577-178">LoadId</span></span>
- <span data-ttu-id="2f577-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="2f577-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="2f577-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="2f577-180">ProcessingStatus</span></span>
- <span data-ttu-id="2f577-181">텍스트</span><span class="sxs-lookup"><span data-stu-id="2f577-181">Text</span></span>
- <span data-ttu-id="2f577-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="2f577-182">WordCount</span></span>
- <span data-ttu-id="2f577-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="2f577-183">WorkingsetId</span></span>

<span data-ttu-id="2f577-184">Advanced eDiscovery의 모든 메타데이터 필드에 대한 정의는 문서 메타데이터 [필드를 참조합니다.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="2f577-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
