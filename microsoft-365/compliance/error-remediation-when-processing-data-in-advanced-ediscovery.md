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
description: 오류 수정을 사용 하 여 콘텐츠를 제대로 처리 하지 못할 수 있는 고급 eDiscovery의 데이터 문제를 해결 하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8ada53dd6339541fc39b37903a0f58fd4ad84c8c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035912"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="50ccc-103">데이터를 처리할 때 오류 수정</span><span class="sxs-lookup"><span data-stu-id="50ccc-103">Error remediation when processing data</span></span>

<span data-ttu-id="50ccc-104">오류 수정을 통해 eDiscovery 관리자는 고급 eDiscovery가 콘텐츠를 제대로 처리 하지 못하게 하는 데이터 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="50ccc-105">예를 들어 암호로 보호 된 파일은 파일을 잠그거나 암호화 한 후에 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="50ccc-106">오류 수정을 사용 하는 경우 eDiscovery 관리자는 이러한 오류와 함께 파일을 다운로드 하 고 암호 보호를 제거한 다음 재구성 된 파일을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="50ccc-107">다음 워크플로를 사용 하 여 고급 eDiscovery 사례에서 오류가 발생 한 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="50ccc-108">처리 오류가 있는 파일을 수정 하는 오류 업데이트 관리 세션 만들기</span><span class="sxs-lookup"><span data-stu-id="50ccc-108">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="50ccc-109">다음 절차 중에 오류 수정 마법사를 언제 든 지 닫을 경우, **보기** 드롭다운 메뉴에서 **Remediations** 을 선택 하 여 **처리** 탭에서 오류 수정 세션으로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="50ccc-110">고급 eDiscovery 사례의 **처리** 탭에 있는 **보기** 드롭다운 메뉴에서 **오류** 를 선택한 다음 **범위** 드롭다운 메뉴에서 검토 집합 또는 전체 사례를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="50ccc-111">이 섹션에는 특정 검토 집합의 케이스나 오류에 대 한 모든 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![오류 수정](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="50ccc-113">오류 유형 또는 파일 형식 옆의 라디오 단추를 클릭 하 여 수정할 오류를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="50ccc-114">다음 예제에서는 암호로 보호 된 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="50ccc-115">**새 오류 수정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="50ccc-116">오류 재구성 워크플로는 오류가 발생 한 파일을 Microsoft에서 제공한 Azure 저장소 위치로 복사 하 여 업데이트를 로컬 컴퓨터로 다운로드 하 여 수정할 수 있는 준비 단계로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![오류 수정 준비](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="50ccc-118">준비가 완료 되 면 **다음: 파일 다운로드** 를 클릭 하 여 다운로드를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![파일 다운로드](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="50ccc-120">파일을 다운로드 하려면 **다운로드 대상 경로**를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="50ccc-121">파일을 다운로드 하는 로컬 컴퓨터의 상위 폴더에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="50ccc-122">기본 경로인%USERPROFILE%\Downloads\errors는 로그인 한 사용자의 다운로드 폴더를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="50ccc-123">원하는 경우이 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-123">You can change this path if desired.</span></span> <span data-ttu-id="50ccc-124">이를 변경 하는 경우 최상의 성능을 위해 로컬 파일 경로를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="50ccc-125">원격 네트워크 경로를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="50ccc-125">Don't use a remote network path.</span></span> <span data-ttu-id="50ccc-126">예를 들어 **C:\remediation**경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-126">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="50ccc-127">부모 폴더에 대 한 경로는 AzCopy 명령에 자동으로 **/Tdest** 매개 변수 값으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="50ccc-128">**클립보드에 복사를**클릭 하 여 미리 정의 된 명령을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="50ccc-129">Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 **enter 키를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![오류 수정 준비](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="50ccc-131">**파일 다운로드** 페이지에 제공 된 명령을 정상적으로 사용 하려면 AzCopy v 8.1을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="50ccc-132">또한 10 단계에서 AzCopy v 8.1을 사용 하 여 파일을 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="50ccc-133">이 버전의 AzCopy을 설치 하려면 [Windows의 AzCopy v 8.1을 사용 하 여 데이터 전송을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50ccc-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="50ccc-134">제공 된 AzCopy 명령이 실패 하면 [Advanced eDiscovery에서 AzCopy 문제 해결](troubleshooting-azcopy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50ccc-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="50ccc-135">선택한 파일이 5 단계에서 지정한 위치로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="50ccc-136">상위 폴더 (예: **C:\remediation**)에서 다음 하위 폴더 구조가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="50ccc-137">*하위 폴더 1* 은 1 단계에서 선택한 범위에 따라 사례 또는 검토 집합의 ID를 사용 하 여 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="50ccc-138">*하위 폴더 2* 의 이름은 다운로드 한 파일의 파일 ID로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="50ccc-139">다운로드 된 파일은 *하위 폴더 2* 에 있으며 파일 ID로도 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="50ccc-140">다음은 항목을 **C:\remediation** 상위 폴더로 다운로드 했을 때 생성 되는 폴더 경로 및 오류 파일 이름의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="50ccc-141">여러 파일이 다운로드 되는 경우에는 파일 ID로 이름이 지정 된 하위 폴더로 각 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="50ccc-142">9 단계와 10 단계에서 파일을 업로드 하는 경우 재구성 된 파일의 파일 이름이 같고 동일한 하위 폴더 구조에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="50ccc-143">하위 폴더와 파일 이름은 재구성 된 파일과 원본 오류 파일을 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="50ccc-144">폴더 구조 또는 파일 이름이 변경 되 면 다음 오류가 `Cannot apply Error Remediation to the current Workingset`표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="50ccc-145">문제를 방지 하려면 재구성 된 파일을 동일한 상위 폴더 및 하위 폴더 구조에 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="50ccc-146">파일을 다운로드 한 후에는 적절 한 도구를 사용 하 여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="50ccc-147">암호로 보호 된 파일의 경우에는 여러 가지 암호 해독 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="50ccc-148">파일에 대 한 암호를 알고 있으면 열고 암호 보호 기능을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="50ccc-149">Advanced eDiscovery 및 오류 수정 마법사로 돌아간 후 **다음: 파일 업로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="50ccc-150">그러면 파일을 업로드할 수 있는 다음 페이지로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-150">This moves to the next page where you can now upload the files.</span></span>

    ![파일 업로드](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="50ccc-152">**파일 위치 경로** 텍스트 상자에서 재구성 된 파일이 있는 상위 폴더를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="50ccc-153">마찬가지로 부모 폴더에는 파일을 다운로드할 때 만든 하위 폴더 구조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="50ccc-154">상위 폴더의 경로는 AzCopy 명령 ( **/Source** 매개 변수 값)에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="50ccc-155">**클립보드에 복사를**클릭 하 여 미리 정의 된 명령을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="50ccc-156">Windows 명령 프롬프트를 열고 AzCopy 명령을 붙여 넣은 다음 **enter 키를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="50ccc-157">파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-157">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6-.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="50ccc-159">AzCopy 명령을 실행 한 후에 **다음: 프로세스 파일**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="50ccc-160">처리가 완료 되 면 검토 설정으로 이동 하 여 재구성 한 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-160">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="50ccc-161">컨테이너 파일의 수정 오류</span><span class="sxs-lookup"><span data-stu-id="50ccc-161">Remediating errors in container files</span></span>

<span data-ttu-id="50ccc-162">고급 eDiscovery로 컨테이너 파일의 내용 (예: .zip 파일)을 추출할 수 없는 경우 컨테이너를 다운로드 하 고 원래 컨테이너가 있는 동일한 폴더에 콘텐츠를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="50ccc-163">확장 된 파일은 처음에 고급 eDiscovery로 확장 된 것 처럼 부모 컨테이너에 대 한 특성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="50ccc-164">이 프로세스는 한 파일을 대체 파일로 업로드 하는 것을 제외 하 고 위에 설명 된 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="50ccc-165">재구성 한 파일을 업로드 하는 경우 원본 컨테이너 파일을 포함 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="50ccc-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="50ccc-166">추출 된 텍스트를 업로드 하 여 오류 수정</span><span class="sxs-lookup"><span data-stu-id="50ccc-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="50ccc-167">고급 eDiscovery에서 해석할 수 있는 기본 형식으로 파일을 수정 하는 것이 불가능할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="50ccc-168">하지만 원본 파일을 *텍스트 층*이라는 프로세스의 원본 텍스트가 포함 된 텍스트 파일로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="50ccc-169">이 작업을 수행 하려면이 문서에서 설명 하는 단계를 수행 하 되, 원본 파일을 기본 형식으로 수정 않고 원본 파일에서 추출한 텍스트를 포함 하는 텍스트 파일을 만든 다음 .txt 접미사로 추가 된 원래 파일 이름을 사용 하 여 텍스트 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="50ccc-170">예를 들어, 파일 이름 335850cc-6602-4af0-acfa-1d14d9128ca2를 사용 하 여 오류를 수정 하는 중에 파일이 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="50ccc-171">네이티브 응용 프로그램에서 파일을 열고 텍스트를 복사한 다음 335850cc-6602-4af0-acfa-1d14d9128ca2 라는 새 파일에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="50ccc-172">이 작업을 수행할 때는 재구성 된 텍스트 파일을 고급 eDiscovery로 업로드 하기 전에 로컬 컴퓨터의 재구성 된 파일 위치에서 원본 파일을 원시 형식으로 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="50ccc-173">파일을 수정 하는 경우 수행 되는 작업</span><span class="sxs-lookup"><span data-stu-id="50ccc-173">What happens when files are remediated</span></span>

<span data-ttu-id="50ccc-174">재구성 한 파일을 업로드 하면 다음 필드를 제외 하 고 원래 메타 데이터가 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ccc-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="50ccc-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="50ccc-175">ExtractedTextSize</span></span>
- <span data-ttu-id="50ccc-176">HasText</span><span class="sxs-lookup"><span data-stu-id="50ccc-176">HasText</span></span>
- <span data-ttu-id="50ccc-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="50ccc-177">IsErrorRemediate</span></span>
- <span data-ttu-id="50ccc-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="50ccc-178">LoadId</span></span>
- <span data-ttu-id="50ccc-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="50ccc-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="50ccc-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="50ccc-180">ProcessingStatus</span></span>
- <span data-ttu-id="50ccc-181">텍스트</span><span class="sxs-lookup"><span data-stu-id="50ccc-181">Text</span></span>
- <span data-ttu-id="50ccc-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="50ccc-182">WordCount</span></span>
- <span data-ttu-id="50ccc-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="50ccc-183">WorkingsetId</span></span>

<span data-ttu-id="50ccc-184">Advanced eDiscovery의 모든 메타 데이터 필드에 대 한 정의는 [문서 메타 데이터 필드](document-metadata-fields.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50ccc-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
