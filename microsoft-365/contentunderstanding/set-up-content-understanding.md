---
title: SharePoint Syntex 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Project Cortex에서 콘텐츠 이해 설정
ms.openlocfilehash: 0d66076c93eb46ca11977cea12417c0816e0d11b
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367934"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="a622a-103">SharePoint Syntex 설정</span><span class="sxs-lookup"><span data-stu-id="a622a-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="a622a-104">관리자는 Microsoft 365 관리 센터를 사용하여 [Microsoft SharePoint Syntex](document-understanding-overview.md)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](document-understanding-overview.md).</span></span> 

<span data-ttu-id="a622a-105">시작하기 전에 다음을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-105">Consider the following before you start:</span></span>

- <span data-ttu-id="a622a-106">양식 처리를 활성화할 SharePoint 사이트는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="a622a-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="a622a-107">전부요, 일부인가요, 아니면 특정 사이트인가요?</span><span class="sxs-lookup"><span data-stu-id="a622a-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="a622a-108">기본 컨텐츠 센터의 이름을 무엇으로 지정하시겠어요?</span><span class="sxs-lookup"><span data-stu-id="a622a-108">What will you name of your default content center?</span></span>

<span data-ttu-id="a622a-109">Microsoft 365 관리 센터에서 초기 설정 후 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="a622a-110">이 기사의 내용은 Project Cortex 비공개 미리 보기에 대한 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="a622a-111">[Project Cortex](https://aka.ms/projectcortex)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a622a-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="a622a-112">설정하기 전에 사용자 환경에서 컨텐츠 이해도를 설정하고 구성하는 최선의 방법을 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="a622a-113">예를 들어 다음 이름을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="a622a-114">양식 처리를 실행하려는 SharePoint 사이트(모든 사이트, 일부 사이트 또는 선택한 사이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="a622a-115">컨텐츠 센터 및 주 사이트 관리자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="a622a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a622a-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="a622a-117">Microsoft 365 관리 센터에 액세스하고 콘텐츠 이해를 설정하려면 글로벌 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="a622a-118">관리자는 Microsoft 365 관리 센터의 콘텐츠 이해 관리 설정 전반에 걸쳐 설정 후 언제든지 선택한 설정을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="a622a-119">SharePoint Syntex를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="a622a-120">Microsoft365 관리 센터에서 **설정**을 선택하고 **파일 및 콘텐츠** 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="a622a-121">**파일 및 콘텐츠** 섹션에서 **콘텐츠 이해 자동화**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-121">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="a622a-122">**콘텐츠 이해 자동화** 페이지에서 **시작하기**를 클릭하여 설정 프로세스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-122">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![설치 시작](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="a622a-124">이미지 태그 지정 설정 페이지에서 [이미지 태그 지정](image-tagging.md)을 허용할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-124">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![이미지 태그 옵션의 스크린샷입니다.](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="a622a-126">**양식 처리 구성** 페이지에서 사용자가 특정 SharePoint 문서 라이브러리에 양식 처리 모델을 생성할 수 있도록 허용할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-126">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="a622a-127">사용 설정된 해당 Sharepoint 문서 라이브러리 리본에서 **양식 처리 모델을 만들기** 위한 문서 라이브러리 리본의 메뉴 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-127">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="a622a-128">**양식 처리 모델**을(를) 생성하기 위해 어떤 SharePoint 라이브러리에 표시할 것인지에 대해 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-128">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="a622a-129">**모든 SharePoint 라이브러리**를 조직의 모든 SharePoint 라이브러리에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-129">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="a622a-130">**선택한 사이트의 라이브러리만**. 그런 다음 사용할 수 있도록 만들 사이트를 선택하거나 최대 50개 사이트의 목록을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-130">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="a622a-131">\*\*사이트에서 SharePoint 라이브러리를 사용하지 않으려면 \*\* SharePoint 라이브러리가 없습니다(설치 후 이 라이브러리를 변경할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="a622a-131">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![양식 처리 구성](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="a622a-133">사이트가 포함된 후 사이트를 제거해도 해당 사이트의 라이브러리에 적용된 기존 모델이나 문서 이해 모델을 라이브러리에 적용하는 기능에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-133">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="a622a-p105">**콘텐츠 센터 생성** 페이지에서 사용자가 문서 이해 모델을 생성하고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 생성할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="a622a-p105">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models. </span></span></br>
    <span data-ttu-id="a622a-135">a.</span><span class="sxs-lookup"><span data-stu-id="a622a-135">a.</span></span> <span data-ttu-id="a622a-136">**사이트 이름**에 대해 콘텐츠 센터 사이트에 지정할 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="a622a-137">b.</span><span class="sxs-lookup"><span data-stu-id="a622a-137">b.</span></span> <span data-ttu-id="a622a-138">**사이트 주소**는 사이트 이름에 대해 선택한 항목에 따라 사이트의 URL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="a622a-139">변경하려는 경우 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-139">If you want to change it, click **Edit**.</span></span></br>

      ![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="a622a-141">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-141">Select **Next**.</span></span>

7. <span data-ttu-id="a622a-142">**검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="a622a-143">원하는 항목을 선택한 경우 **활성화**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="a622a-144">확인 페이지에서 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="a622a-145">**콘텐츠 이해 자동화** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="a622a-146">이 페이지에서 **관리**를 선택하여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="a622a-147">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="a622a-147">Assign licenses</span></span>

<span data-ttu-id="a622a-148">SharePoint Syntex를 구성한 후에는 SharePoint Syntex 기능을 사용할 사용자에게 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="a622a-149">라이선스를 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-149">To assign licenses:</span></span>

1. <span data-ttu-id="a622a-150">Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="a622a-151">라이선스를 부여할 사용자를 선택하고 **제품 라이선스 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="a622a-152">**추가 할당**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="a622a-153">**지능형 콘텐츠 서비스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="a622a-154">**앱**에서 **지능형 콘텐츠 서비스용 일반 데이터 서비스** 및 **지능형 콘텐츠 서비스**가 모두 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![SharePoint Syntex 라이선스는 Microsoft 365 관리 센터에서 사용할 수 있습니다.](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="a622a-156">**변경 사항 저장**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="a622a-157">AI Builder 크레딧</span><span class="sxs-lookup"><span data-stu-id="a622a-157">AI Builder credits</span></span>

<span data-ttu-id="a622a-158">조직에 SharePoint Syntex에 대한 SharePoint Syntex 라이선스가 300개 이상 있는 경우 100만 개의 AI Builder 크레딧이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="a622a-159">라이선스 수가 300개 미만인 경우 양식 처리를 사용하려면 AI Builder 크레딧을 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="a622a-160">[AI Builder 계산기](https://powerapps.microsoft.com/ai-builder-calculator)을(를) 사용하여 사용자에게 적합한 AI Builder 용량을 추정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="a622a-161">[파워 플랫폼 관리 센터](https://admin.powerplatform.microsoft.com/resources/capacity)로 이동하여 크레딧 및 사용량을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a622a-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a622a-162">See also</span></span>

<span data-ttu-id="a622a-163">[양식 처리 모델](https://docs.microsoft.com/ai-builder/form-processing-model-overview)을(를) 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a622a-163">[Overview of the form processing model](https://docs.microsoft.com/ai-builder/form-processing-model-overview)</span></span>

<span data-ttu-id="a622a-164">[단계별 절차는 다음과 같습니다. 문서 이해 모델(비디오)](https://www.youtube.com/watch?v=DymSHObD-bg)을(를) 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="a622a-164">[Step-by-Step: How to Build a Document Understanding Model (video)](https://www.youtube.com/watch?v=DymSHObD-bg)</span></span>

