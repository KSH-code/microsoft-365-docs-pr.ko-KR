---
title: 콘텐츠 센터 만들기 (미리 보기)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 콘텐츠 센터를 만드는 방법을 알아봅니다.
ms.openlocfilehash: ced47f8029079910479dd9aa5c43b39870a56aea
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537570"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="ce915-103">콘텐츠 센터 만들기 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="ce915-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="ce915-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="ce915-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="ce915-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="ce915-106">문서 모델을 이해 하 고 관리 하려면 먼저 콘텐츠 센터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="ce915-107">콘텐츠 센터는 모델 만들기 인터페이스 이며, 적용 된 문서 라이브러리에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![문서 라이브러리 선택](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="ce915-109">초기 콘텐츠 센터는 [설치](set-up-content-understanding.md)중에 만들어지며 SharePoint 관리자는 필요에 따라 추가 항목을 만들도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="ce915-110">모든 모델 활동의 롤업을 보려는 환경에는 단일 콘텐츠 센터가 있을 수 있지만, 조직 내의 여러 부서에 해당 모델에 대 한 요구 사항을 서로 다르게 설정 해야 하는 경우에는 추가 기능을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="ce915-111">SharePoint 관리자는 사이트 서식 파일을 통해 [다른 sharepoint 사이트를 만드는](https://docs.microsoft.com/sharepoint/create-site-collection) 것 처럼 콘텐츠 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="ce915-112">새 콘텐츠 센터를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-112">To create a new content center:</span></span>

1. <span data-ttu-id="ce915-113">Microsoft 365 관리 센터에서 SharePoint 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="ce915-114">SharePoint 관리 센터의 **사이트**아래에서 **활성 사이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="ce915-115">**활성 사이트** 페이지에서 **만들기**를 클릭 한 다음 **기타 옵션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="ce915-116">**서식 파일 선택** 메뉴에서 **콘텐츠 센터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="ce915-117">새 사이트의 경우 **사이트 이름**, **기본 관리자**및 **언어**를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="ce915-118">사용할 수 있는 언어로 렌더링할 콘텐츠 센터 사이트를 선택할 수 있지만 현재 모델은 영어 파일에 대해서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="ce915-119">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="ce915-120">추가 사용자에 게 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="ce915-120">Give access to additional users</span></span>
 
<span data-ttu-id="ce915-121">사이트를 만든 후에는 다른 사용자에 게 표준 [SharePoint 사이트 사용 권한 모델](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)을 통해 사이트에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce915-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="ce915-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce915-122">See Also</span></span>
[<span data-ttu-id="ce915-123">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="ce915-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="ce915-124">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="ce915-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="ce915-125">[콘텐츠 센터 만들기](create-a-content-center.md) 
 [문서 이해 개요](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ce915-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="ce915-126">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="ce915-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="ce915-127">모델 적용</span><span class="sxs-lookup"><span data-stu-id="ce915-127">Apply a model</span></span>](apply-a-model.md)    




