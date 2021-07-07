---
title: 테스트 작업 설정
description: 테스트 작업 설정
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322950"
---
# <a name="step-4-the-tasks-tab"></a><span data-ttu-id="011d3-103">4단계: 작업 탭</span><span class="sxs-lookup"><span data-stu-id="011d3-103">Step 4: The tasks tab</span></span>

<span data-ttu-id="011d3-104">작업 탭에서 업로드한 zip 폴더의 이진 탭에 있는 테스트 스크립트의 경로를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-104">On the tasks tab, you are expected to provide the paths to your test scripts which are in the zip folder you uploaded under the binaries tab.</span></span>

  - <span data-ttu-id="011d3-105">**Out of Box Test Scripts:** 설치, 시작, 닫기 및 제거 스크립트에 대한 상대 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-105">**Out of Box Test Scripts:** Type in the relative paths to your install, launch, close and uninstall scripts.</span></span> <span data-ttu-id="011d3-106">설치 스크립트에 대한 추가 설정을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-106">You also have the option to select additional settings for the install script.</span></span>
  - <span data-ttu-id="011d3-107">**기능 테스트 스크립트:** 업로드된 각 기능 테스트 스크립트에 대한 상대 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-107">**Functional Test Scripts:** Type in the relative path to each functional test script uploaded.</span></span> <span data-ttu-id="011d3-108">단추를 사용하여 추가 기능 테스트 스크립트를 추가할 수 ```Add Script``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-108">Additional functional test scripts can be added using the ```Add Script``` button.</span></span> <span data-ttu-id="011d3-109">최소 하나의 (1) 스크립트가 필요하며 최대 8개의 기능 테스트 스크립트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-109">You need a minimum of one (1) script and can add up to eight (8) functional test scripts.</span></span> 
  
    <span data-ttu-id="011d3-110">스크립트는 업로드 순서대로 실행되고 특정 스크립트에서 오류가 발생하면 후속 스크립트 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-110">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>
    <span data-ttu-id="011d3-111">또한 제공된 각 스크립트에 대해 추가 설정을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-111">You also have the option of selecting additional settings for each script provided.</span></span>

## <a name="set-script-path"></a><span data-ttu-id="011d3-112">스크립트 경로 설정</span><span class="sxs-lookup"><span data-stu-id="011d3-112">Set script path</span></span>

![테스트 작업의 이미지](Media/testtask.png)

<span data-ttu-id="011d3-114">폴더 구조에 상대 경로를 제공하는 방법의 샘플은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-114">Sample of how to provide the relative path on a folder structure is below:</span></span>

<span data-ttu-id="011d3-115">_**Zip_file_uploaded**_</span><span class="sxs-lookup"><span data-stu-id="011d3-115">_**Zip_file_uploaded**_</span></span>
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="011d3-116">**ScriptX.ps1** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-116">**ScriptX.ps1** would have.</span></span> <span data-ttu-id="011d3-117">_ScriptX.ps1_ 경로로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-117">_ScriptX.ps1_ as the relative path.</span></span>
  - <span data-ttu-id="011d3-118">**Script.ps1** _폴더1/script.ps1_ 경로로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="011d3-118">**Script.ps1** would have _folder1/script.ps1_ as the relative path.</span></span>


## <a name="next-steps"></a><span data-ttu-id="011d3-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="011d3-119">Next steps</span></span>

<span data-ttu-id="011d3-120">다음 문서에서 테스트 옵션 탭의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="011d3-120">View details of the Test Options tab in the next article</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="011d3-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="011d3-121">Next step</span></span>](testoptions.md)
