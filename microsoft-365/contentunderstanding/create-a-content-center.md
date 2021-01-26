---
title: Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 콘텐츠 센터 만드는 방법 알아보기
ms.openlocfilehash: 4377cbfbda8572fe9e08a079a05146961105298b
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976534"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="59c91-103">Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기</span><span class="sxs-lookup"><span data-stu-id="59c91-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="59c91-104">문서 이해 모델을 만들고 관리하려면 먼저 콘텐츠 센터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="59c91-105">콘텐츠 센터는 모델 만들기 인터페이스이자 게시된 모델에 적용된 문서 라이브러리에 대한 정보를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![문서 라이브러리 선택](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="59c91-107">[설정](set-up-content-understanding.md) 중에 기본 콘텐츠 센터가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="59c91-108">SharePoint 관리자는 필요한 경우 추가 센터를 만들도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="59c91-109">모든 모델 활동을 롤업하는 환경이라면 단일 콘텐츠 센터로도 괜찮지만 모델에 따라 요구사항과 사용 권한이 다를 경우 조직 내에 여러 부서를 위한 추가 센터가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="59c91-110">SharePoint 관리자는 관리 센터 사이트 프로비전 창에서 [다른 SharePoint 사이트를 만드는 것](https://docs.microsoft.com/sharepoint/create-site-collection)과 같이 콘텐츠 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="59c91-111">새 콘텐츠 센터를 만들려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-111">To create a new content center:</span></span>

1. <span data-ttu-id="59c91-112">Microsoft 365 관리 센터에서 SharePoint 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="59c91-113">SharePoint 관리 센터의 **사이트** 에서 **활성 사이트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="59c91-114">**활성 사이트** 페이지에서 **만들기** 를 클릭하고 **다른 옵션** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="59c91-115">**서식 파일 선택** 메뉴에서 **콘텐츠 센터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="59c91-116">새 사이트의 경우 **사이트 이름**, **주 관리자** 및 **언어** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="59c91-117">사용 가능한 모든 언어로 콘텐츠 센터 사이트를 렌더링하도록 선택할 수 있지만 현재 모델은 영문 파일에 대해서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="59c91-118">또한 사이트 형식처럼 사이트가 만들어진 이후에 기본 언어 편집은 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="59c91-119">**마침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-119">Select **Finished**.</span></span>
 
<span data-ttu-id="59c91-120">콘텐츠 센터 사이트를 만든 후에는 SharePoint 관리 센터의 **활성 사이트** 페이지에 표시되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="59c91-121">추가 사용자에게 액세스 부여</span><span class="sxs-lookup"><span data-stu-id="59c91-121">Give access to additional users</span></span>
 
<span data-ttu-id="59c91-122">사이트를 만든 후에는 다른 사용자에게 표준 [SharePoint 사이트 사용 권한 모델](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)을 통해 사이트에 액세스를 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c91-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="59c91-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59c91-123">See Also</span></span>
[<span data-ttu-id="59c91-124">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="59c91-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="59c91-125">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="59c91-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="59c91-126">콘텐츠 센터 만들기</span><span class="sxs-lookup"><span data-stu-id="59c91-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="59c91-127">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="59c91-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="59c91-128">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="59c91-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="59c91-129">모델 적용</span><span class="sxs-lookup"><span data-stu-id="59c91-129">Apply a model</span></span>](apply-a-model.md)    
