---
title: 테스트 패키지 지침
description: 테스트 패키지에 대한 지침 검토
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323046"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="95dcb-103">테스트 패키지 지침</span><span class="sxs-lookup"><span data-stu-id="95dcb-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="95dcb-104">1. 스크립트 참조</span><span class="sxs-lookup"><span data-stu-id="95dcb-104">1.   Script referencing</span></span>

<span data-ttu-id="95dcb-105">포털에 .zip 파일을 업로드할 때 해당 파일의 모든 콘텐츠의zip을 루트 폴더로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="95dcb-106">이 초기의 unzip 작업을 수행하기 위해 코드를 작성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="95dcb-107">업로드된 zip 파일을 .zip 경로를 사용하여 파일 내의 모든 파일을 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="95dcb-108">아래 예제에서는 작업 탭의 입력 필드에서 이진/스크립트를 참조하는 방법을 보여 주겠습니다. 텍스트는 인용 부호 없이 **스크립트** 경로 필드에 파란색으로 **입력해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="95dcb-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="95dcb-109">파일을 업로드하기 전에 zip 파일 내의 콘텐츠를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="95dcb-110">폴더를 압축할 때 로컬 컴퓨터는 zip 파일 아래에 주 폴더를 만드는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="95dcb-111">이 경우 참조는 아래 굵게 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="95dcb-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="95dcb-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="95dcb-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="95dcb-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="95dcb-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="95dcb-114">Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="95dcb-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="95dcb-115">다른 경우 zip 파일에 파일 또는 콘텐츠가 바로 아래에 있을 수 있습니다. 즉, 2nd 수준 폴더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="95dcb-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="95dcb-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="95dcb-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="95dcb-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="95dcb-118">Script.ps1 – **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="95dcb-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="95dcb-119">2. 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="95dcb-119">2.   Script execution</span></span>

<span data-ttu-id="95dcb-120">**Out-of-Box 테스트:** 응용 프로그램 패키지에는 응용 프로그램 및 해당 종속성에 대한 무인 설치, 시작 및 닫기 작업을 실행하는 세 개 이상의 PowerShell 스크립트가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="95dcb-121">각 스크립트는 자체 필수 필수 설정 확인, 성공 확인, 자체 후 정리(필요한 경우)를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="95dcb-122">**기능 테스트:** 응용 프로그램 패키지에는 하나 이상의 PowerShell 스크립트가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="95dcb-123">두 개 이상의 스크립트가 제공되는 경우 스크립트는 업로드 시퀀스에서 실행되고 특정 스크립트의 오류는 후속 스크립트의 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="95dcb-124">스크립트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="95dcb-124">Script requirements</span></span>

<span data-ttu-id="95dcb-125">• PowerShell 버전 5.1+</span><span class="sxs-lookup"><span data-stu-id="95dcb-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="95dcb-126">• 무인 실행</span><span class="sxs-lookup"><span data-stu-id="95dcb-126">•   Unattended execution</span></span>    

<span data-ttu-id="95dcb-127">• 오류 반환 코드</span><span class="sxs-lookup"><span data-stu-id="95dcb-127">•   Error return code</span></span>               

<span data-ttu-id="95dcb-128">• 성공 확인</span><span class="sxs-lookup"><span data-stu-id="95dcb-128">•   Validate success</span></span>            

<span data-ttu-id="95dcb-129">• 특정 로그 폴더 스크립트에 로깅</span><span class="sxs-lookup"><span data-stu-id="95dcb-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="95dcb-130">테스트 파이프라인에서 성공적으로 실행하기 위해 각 스크립트는 완전히 무인으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="95dcb-131">스크립트가 성공적으로 완료될 때 "0"을 반환하고 실행 중에 오류가 발생하면 0이 아닌 오류 코드를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="95dcb-132">각 스크립트는 성공적으로 실행된지 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="95dcb-133">예:</span><span class="sxs-lookup"><span data-stu-id="95dcb-133">E.g.</span></span> <span data-ttu-id="95dcb-134">설치 스크립트는 설치 관리자 이진 파일 실행이 완료된 후 설치가 성공적이라 적절한 신뢰도로 실행이 완료된 후 시스템에 특정 바이너리 및/또는 레지스트리 키가 존재하는지 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="95dcb-135">이는 테스트 실행 중에 오류가 발생하는 위치(예: 응용 프로그램을 성공적으로 설치할 수 없거나 실행할 수 없는 경우)를 제대로 진단하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="95dcb-136">**다음을 방지합니다.** 스크립트를 다시 시작해야 하는 경우 스크립트를 업로드하는 동안 다시 시작해야 하는 경우 스크립트를 다시 시작하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="95dcb-137">3. 로그 컬렉션</span><span class="sxs-lookup"><span data-stu-id="95dcb-137">3.   Log collection</span></span>

<span data-ttu-id="95dcb-138">각 스크립트는 이라는 폴더에 생성되는 모든 로그를 출력해야 ```logs``` 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="95dcb-139">이름이 인 디렉터리의 모든 폴더가 복사된 후 ```logs``` 페이지에서 다운로드할 수 ```Test Results``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="95dcb-140">예를 들어 설치 **스크립트(App/scripts/install** 디렉터리에 위치할 수 있습니다.)는 로그를 **로그/install.log에** 출력할 수 있습니다. 즉, 최종 로그가 에 위치하도록 합니다. **Apps/scripts/install/logs/install.log**</span><span class="sxs-lookup"><span data-stu-id="95dcb-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="95dcb-141">시스템은 다른 폴더 내의 다른 파일과 함께 파일을 선택하고 ```install.log``` ```logs``` 다운로드를 위해 데이터를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="95dcb-142">4. 응용 프로그램 이진</span><span class="sxs-lookup"><span data-stu-id="95dcb-142">4.   Application binaries</span></span>

<span data-ttu-id="95dcb-143">모든 이진 파일 및 종속성은 단일 zip 파일에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="95dcb-144">여기에는 응용 프로그램 설치에 필요한 모든 것(예: 응용 프로그램 설치 관리자)이 포함되어야 합니다. 응용 프로그램이 .NET Core/Standard 또는 .NET Framework 프레임워크에 종속된 경우 파일에 포함되어 제공된 스크립트에서 올바르게 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="95dcb-145">업로드한 zip 파일에 이름에 공백이나 특수 문자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dcb-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="95dcb-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="95dcb-146">Next steps</span></span>

<span data-ttu-id="95dcb-147">FAQ(질문과 대답)를 보기 위해 다음 **문서로 진행합니다.**</span><span class="sxs-lookup"><span data-stu-id="95dcb-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="95dcb-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="95dcb-148">Next step</span></span>](faq.md)
