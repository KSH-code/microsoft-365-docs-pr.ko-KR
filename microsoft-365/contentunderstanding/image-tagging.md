---
title: SharePoint Syntex에서 이미지 태그 지정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: SharePoint Syntex에서 이미지 태그 지정에 대해 알아보기
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975868"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="723a4-103">SharePoint Syntex에서 이미지 태그 지정</span><span class="sxs-lookup"><span data-stu-id="723a4-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="723a4-104">(준비 중)</span><span class="sxs-lookup"><span data-stu-id="723a4-104">(Coming soon)</span></span>

<span data-ttu-id="723a4-105">SharePoint Syntex의 이미지 태그를 사용 하면 사용자가 이미지 태그를 검색 하여 이미지를 찾고, 이미지 태그에 따라 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="723a4-106">기본적으로 SharePoint 및 OneDrive에 대해 기본 이미지 태그 지정 기능이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="723a4-107">두 위치 중 하나에 업로드된 이미지는 자동으로 검색되며 가능한 경우 해당 태그가 37개의 기본 태그 목록에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="723a4-108">사용자는 이미지 태그 검색을 통해 이미지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="723a4-109">사용자가 이미지를 업로드하면 태그 지정 프로세스가 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="723a4-110">이미지를 편집하는 경우 태그 지정 프로세스를 다시 실행하여 태그를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="723a4-111">이미지 파일에 대한 사용 권한이 있는 사용자는 파일 정보 패널 또는 검색 결과 페이지에서 태그를 확인하고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="723a4-112">사용자가 이미지 태그를 편집한 후에는 해당 이미지가 편집되더라도 이미지에 자동 태그를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="723a4-113">태그 지정을 해제하면 이미지에 더 이상 자동으로 태그가 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="723a4-114">기존 태그는 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="723a4-115">이미지나 태그 기술이 업데이트 되면 세스템에서 생성된 태그가 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="723a4-116">이미지 태그 지정 구성</span><span class="sxs-lookup"><span data-stu-id="723a4-116">Configure image tagging</span></span>

<span data-ttu-id="723a4-117">[SharePoint Syntex](set-up-content-understanding.md)이후에는 Microsoft 365 관리 센터에서 이미지 태그를 구성 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="723a4-118">이미지 태그 지정 설정 또는 해제 방법</span><span class="sxs-lookup"><span data-stu-id="723a4-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="723a4-119">Microsoft 365 관리 센터에서 **설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="723a4-120">**조직 지식** 에서 **콘텐츠 이해 자동화** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="723a4-121">**관리** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-121">Click **Manage**.</span></span>

4. <span data-ttu-id="723a4-122">**이미지 태그 지정** 탭에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="723a4-123">**기본 태그 지정** 을 허용하거나 태그 지정 **해제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="723a4-124">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="723a4-124">Click **Save**.</span></span>

    ![이미지 태그 지정 컨트롤 스크린샷](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
