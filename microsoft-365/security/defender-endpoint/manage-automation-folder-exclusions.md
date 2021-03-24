---
title: 자동화 폴더 제외 관리
description: 자동화 폴더 제외를 추가하여 자동화된 조사에서 제외된 파일을 제어합니다.
keywords: 관리, 자동화, 제외, 차단, 정리, 악의적
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fb398f1acbea4bd8f388c072f9706f9b2ca25175
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070196"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="6d1eb-104">자동화 폴더 제외 관리</span><span class="sxs-lookup"><span data-stu-id="6d1eb-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6d1eb-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="6d1eb-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6d1eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="6d1eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d1eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6d1eb-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6d1eb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6d1eb-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="6d1eb-110">자동화 폴더 제외를 사용하면 자동화된 조사에서 건너뛸 폴더를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="6d1eb-111">건너뛴 폴더에 대한 다음 특성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="6d1eb-112">폴더</span><span class="sxs-lookup"><span data-stu-id="6d1eb-112">Folders</span></span> 
- <span data-ttu-id="6d1eb-113">파일의 확장명</span><span class="sxs-lookup"><span data-stu-id="6d1eb-113">Extensions of the files</span></span>
- <span data-ttu-id="6d1eb-114">파일 이름</span><span class="sxs-lookup"><span data-stu-id="6d1eb-114">File names</span></span>


<span data-ttu-id="6d1eb-115">**폴더**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-115">**Folders**</span></span><br>
<span data-ttu-id="6d1eb-116">건너뛴 폴더와 해당 하위 폴더를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="6d1eb-117">현재는 디렉터리에서 파일을 제외하는 방법으로 와일드카드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="6d1eb-118">**Extensions**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-118">**Extensions**</span></span><br>
<span data-ttu-id="6d1eb-119">특정 디렉터리에서 제외할 확장을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="6d1eb-120">확장은 공격자가 제외된 폴더를 사용하여 악용을 숨기는 것을 방지하는 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="6d1eb-121">확장명은 무시할 파일을 명시적으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="6d1eb-122">**파일 이름**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-122">**File names**</span></span><br>
<span data-ttu-id="6d1eb-123">특정 디렉터리에서 제외할 파일 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="6d1eb-124">이 이름은 공격자가 제외된 폴더를 사용하여 악용을 숨기지 못하게 하는 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="6d1eb-125">이름은 무시할 파일을 명시적으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="6d1eb-126">자동화 폴더 제외 추가</span><span class="sxs-lookup"><span data-stu-id="6d1eb-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="6d1eb-127">탐색 창에서 설정 **자동화**  >  **폴더 제외를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="6d1eb-128">새 **폴더 제외 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="6d1eb-129">폴더 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-129">Enter the folder details:</span></span>

    - <span data-ttu-id="6d1eb-130">폴더</span><span class="sxs-lookup"><span data-stu-id="6d1eb-130">Folder</span></span>
    - <span data-ttu-id="6d1eb-131">Extensions</span><span class="sxs-lookup"><span data-stu-id="6d1eb-131">Extensions</span></span>
    - <span data-ttu-id="6d1eb-132">파일 이름</span><span class="sxs-lookup"><span data-stu-id="6d1eb-132">File names</span></span>
    - <span data-ttu-id="6d1eb-133">설명</span><span class="sxs-lookup"><span data-stu-id="6d1eb-133">Description</span></span>
    

4. <span data-ttu-id="6d1eb-134">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="6d1eb-135">제외된 파일을 수집하거나 검사하기 위해 라이브 응답 명령은 오류와 함께 실패합니다. "파일이 제외됩니다."</span><span class="sxs-lookup"><span data-stu-id="6d1eb-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="6d1eb-136">또한 자동화된 조사는 제외된 항목을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="6d1eb-137">자동화 폴더 제외 편집</span><span class="sxs-lookup"><span data-stu-id="6d1eb-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="6d1eb-138">탐색 창에서 설정 **자동화**  >  **폴더 제외를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="6d1eb-139">폴더 **제외에서** 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1eb-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="6d1eb-140">규칙의 세부 정보를 업데이트하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="6d1eb-141">자동화 폴더 제외 제거</span><span class="sxs-lookup"><span data-stu-id="6d1eb-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="6d1eb-142">탐색 창에서 설정 **자동화**  >  **폴더 제외를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="6d1eb-143">제외 **제거를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d1eb-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="6d1eb-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6d1eb-144">Related topics</span></span>
- [<span data-ttu-id="6d1eb-145">자동화 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="6d1eb-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="6d1eb-146">자동화 파일 업로드 관리</span><span class="sxs-lookup"><span data-stu-id="6d1eb-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
