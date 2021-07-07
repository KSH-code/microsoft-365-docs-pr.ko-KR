---
title: 업로드 응용 프로그램 이진
description: M365용 테스트 기준을 사용하여 시작하는 방법
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323166"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="19043-103">3단계: 업로드, 종속성 및 스크립트 확인</span><span class="sxs-lookup"><span data-stu-id="19043-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="19043-104">이 탭에서 테스트 제품군을 실행하는 데 사용되는 이진, 종속성 및 스크립트가 포함된 단일 zip 패키지를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="19043-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="19043-105">업로드 zip 파일</span><span class="sxs-lookup"><span data-stu-id="19043-105">Upload package zip file</span></span>

![업로드 이진](Media/AddBinaries.png)

  - <span data-ttu-id="19043-107">업로드된 종속성에는 응용 프로그램 또는 테스트 사례를 실행하기 위해 액세스할 테스트 프레임워크, 스크립팅 엔진 또는 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19043-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="19043-108">예를 들어 Selenium 및 webdriver 설치 관리자를 업로드하여 브라우저 기반 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19043-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="19043-109">스크립트 활동이 모듈식으로 유지되도록 하는 것이 가장 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="19043-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="19043-110">스크립트는 ```Install``` 설치 작업만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="19043-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="19043-111">스크립트는 ```Launch``` 응용 프로그램만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="19043-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="19043-112">스크립트는 ```Close``` 응용 프로그램만 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="19043-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="19043-113">선택적 ```Uninstall``` 스크립트는 응용 프로그램만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="19043-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="19043-114">**현재 포털에서는 PowerShell 스크립트만 지원됩니다.**</span><span class="sxs-lookup"><span data-stu-id="19043-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="19043-115">다음 단계</span><span class="sxs-lookup"><span data-stu-id="19043-115">Next steps</span></span> 

<span data-ttu-id="19043-116">다음 문서로 이동하여 4단계: 테스트 작업 **설정으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="19043-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="19043-117">돌아 가</span><span class="sxs-lookup"><span data-stu-id="19043-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="19043-118">다음 단계</span><span class="sxs-lookup"><span data-stu-id="19043-118">Next step</span></span>](testtask.md)

