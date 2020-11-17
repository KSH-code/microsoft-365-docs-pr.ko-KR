---
title: SharePoint Syntex 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Project Cortex에서 콘텐츠 이해 설정
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087574"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="6efb1-103">SharePoint Syntex 설정</span><span class="sxs-lookup"><span data-stu-id="6efb1-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="6efb1-104">관리자는 Microsoft 365 관리 센터를 사용하여 [Microsoft SharePoint Syntex](index.md)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="6efb1-105">시작하기 전에 다음을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-105">Consider the following before you start:</span></span>

- <span data-ttu-id="6efb1-p101">Which SharePoint sites will you enable form processing? All of them, some, or select sites?</span><span class="sxs-lookup"><span data-stu-id="6efb1-p101">Which SharePoint sites will you enable form processing? All of them, some, or select sites?</span></span>
- <span data-ttu-id="6efb1-108">기본 컨텐츠 센터의 이름을 무엇으로 지정하시겠어요?</span><span class="sxs-lookup"><span data-stu-id="6efb1-108">What will you name of your default content center?</span></span>

<span data-ttu-id="6efb1-109">Microsoft 365 관리 센터에서 초기 설정 후 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="6efb1-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:</span><span class="sxs-lookup"><span data-stu-id="6efb1-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="6efb1-112">양식 처리를 실행하려는 SharePoint 사이트(모든 사이트, 일부 사이트 또는 선택한 사이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-112">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="6efb1-113">컨텐츠 센터 및 주 사이트 관리자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-113">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="6efb1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6efb1-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="6efb1-115">Microsoft 365 관리 센터에 액세스하고 콘텐츠 이해를 설정하려면 글로벌 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="6efb1-116">관리자는 Microsoft 365 관리 센터의 콘텐츠 이해 관리 설정 전반에 걸쳐 설정 후 언제든지 선택한 설정을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="6efb1-117">SharePoint Syntex를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="6efb1-118">Microsoft365 관리 센터에서 **설정** 을 선택하고 **파일 및 콘텐츠** 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="6efb1-119">**파일 및 콘텐츠** 섹션에서 **콘텐츠 이해 자동화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="6efb1-120">**콘텐츠 이해 자동화** 페이지에서 **시작하기** 를 클릭하여 설정 프로세스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6efb1-121">![설치 시작](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="6efb1-121">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="6efb1-p103">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span><span class="sxs-lookup"><span data-stu-id="6efb1-p103">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="6efb1-124">**양식 처리 모델** 을(를) 생성하기 위해 어떤 SharePoint 라이브러리에 표시할 것인지에 대해 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="6efb1-125">**모든 SharePoint 라이브러리** 를 조직의 모든 SharePoint 라이브러리에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-125">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="6efb1-126">**선택한 사이트의 라이브러리만**. 그런 다음 사용할 수 있도록 만들 사이트를 선택하거나 최대 50개 사이트의 목록을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-126">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="6efb1-127">**사이트에서 SharePoint 라이브러리를 사용하지 않으려면** SharePoint 라이브러리가 없습니다(설치 후 이 라이브러리를 변경할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="6efb1-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6efb1-128">![양식 처리 구성](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="6efb1-128">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="6efb1-129">사이트가 포함된 후 사이트를 제거해도 해당 사이트의 라이브러리에 적용된 기존 모델이나 문서 이해 모델을 라이브러리에 적용하는 기능에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="6efb1-130">**콘텐츠 센터 생성** 페이지에서 사용자가 문서 이해 모델을 생성하고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-130">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="6efb1-131">**사이트 이름** 에 대해 콘텐츠 센터 사이트에 지정할 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-131">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="6efb1-p104">The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="6efb1-p104">The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="6efb1-134">![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="6efb1-134">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="6efb1-135">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-135">Select **Next**.</span></span>

6. <span data-ttu-id="6efb1-p105">On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.</span><span class="sxs-lookup"><span data-stu-id="6efb1-p105">On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="6efb1-138">확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-138">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="6efb1-p106">You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings.</span><span class="sxs-lookup"><span data-stu-id="6efb1-p106">You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="6efb1-141">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6efb1-141">Assign licenses</span></span>

<span data-ttu-id="6efb1-142">SharePoint Syntex를 구성한 후에는 SharePoint Syntex 기능을 사용할 사용자에게 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-142">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="6efb1-143">라이선스를 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-143">To assign licenses:</span></span>

1. <span data-ttu-id="6efb1-144">Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-144">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="6efb1-145">라이선스를 부여할 사용자를 선택하고 **제품 라이선스 관리** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-145">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="6efb1-146">**추가 할당** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-146">Select **Assign more**.</span></span>

4. <span data-ttu-id="6efb1-p107">Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span><span class="sxs-lookup"><span data-stu-id="6efb1-p107">Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6efb1-149">![Microsoft 365 관리 센터의 SharePoint Syntex 라이선스](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="6efb1-149">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="6efb1-150">**변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-150">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="6efb1-151">AI Builder 크레딧</span><span class="sxs-lookup"><span data-stu-id="6efb1-151">AI Builder credits</span></span>

<span data-ttu-id="6efb1-p108">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span><span class="sxs-lookup"><span data-stu-id="6efb1-p108">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="6efb1-154">[AI Builder 계산기](https://powerapps.microsoft.com/ai-builder-calculator)을(를) 사용하여 사용자에게 적합한 AI Builder 용량을 추정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-154">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="6efb1-155">[파워 플랫폼 관리 센터](https://admin.powerplatform.microsoft.com/resources/capacity)로 이동하여 크레딧 및 사용량을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-155">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="6efb1-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6efb1-156">See also</span></span>

<span data-ttu-id="6efb1-157">[양식 처리 모델](https://docs.microsoft.com/ai-builder/form-processing-model-overview)을(를) 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6efb1-157">[Overview of the form processing model](https://docs.microsoft.com/ai-builder/form-processing-model-overview)</span></span>

<span data-ttu-id="6efb1-158">[단계별 절차는 다음과 같습니다. 문서 이해 모델(비디오)](https://www.youtube.com/watch?v=DymSHObD-bg)을(를) 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="6efb1-158">[Step-by-Step: How to Build a Document Understanding Model (video)](https://www.youtube.com/watch?v=DymSHObD-bg)</span></span>

