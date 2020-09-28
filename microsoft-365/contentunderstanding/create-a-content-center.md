---
title: Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 콘텐츠 센터를 만드는 방법을 알아봅니다.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295435"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="b10b8-103">Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기</span><span class="sxs-lookup"><span data-stu-id="b10b8-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="b10b8-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="b10b8-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="b10b8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="b10b8-106">문서 모델을 이해 하 고 관리 하려면 먼저 콘텐츠 센터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="b10b8-107">콘텐츠 센터는 모델 만들기 인터페이스 이며, 적용 된 문서 라이브러리에 대 한 정보도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![문서 라이브러리 선택](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="b10b8-109">[설치](set-up-content-understanding.md)하는 동안 초기 콘텐츠 센터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="b10b8-110">그러나 SharePoint 관리자는 필요에 따라 추가 센터를 만들도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="b10b8-111">모든 모델 활동의 롤업을 사용할 환경에서 단일 콘텐츠 센터가 발생할 수 있는 경우 조직 내에 여러 부서에 대 한 추가 센터가 있을 수 있으며, 이러한 모델에 대 한 요구 사항과 요구 사항이 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="b10b8-112">SharePoint 관리자는 사이트 서식 파일을 사용 하 여 [다른 sharepoint 사이트를 만드는](https://docs.microsoft.com/sharepoint/create-site-collection) 것 처럼 콘텐츠 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="b10b8-113">새 콘텐츠 센터를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-113">To create a new content center:</span></span>

1. <span data-ttu-id="b10b8-114">Microsoft 365 관리 센터에서 SharePoint 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="b10b8-115">SharePoint 관리 센터의 **사이트**아래에서 **활성 사이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="b10b8-116">**활성 사이트** 페이지에서 **만들기**를 클릭 한 다음 **기타 옵션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="b10b8-117">**서식 파일 선택** 메뉴에서 **콘텐츠 센터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="b10b8-118">새 사이트의 경우 **사이트 이름**, **기본 관리자**및 **언어**를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="b10b8-119">필요한 경우 콘텐츠 센터 사이트를 선택 하 여 사용 가능한 언어로 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="b10b8-120">영어 파일에 대해서만 현재 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="b10b8-121">**마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="b10b8-122">추가 사용자에 게 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="b10b8-122">Give access to additional users</span></span>
 
<span data-ttu-id="b10b8-123">사이트를 만든 후에는 다른 사용자에 게 표준 [SharePoint 사이트 사용 권한 모델](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)을 통해 사이트에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b10b8-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="b10b8-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b10b8-124">See Also</span></span>
[<span data-ttu-id="b10b8-125">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="b10b8-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="b10b8-126">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="b10b8-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="b10b8-127">[콘텐츠 센터 만들기](create-a-content-center.md) 
 [문서 이해 개요](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b10b8-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="b10b8-128">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="b10b8-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="b10b8-129">모델 적용</span><span class="sxs-lookup"><span data-stu-id="b10b8-129">Apply a model</span></span>](apply-a-model.md)    
