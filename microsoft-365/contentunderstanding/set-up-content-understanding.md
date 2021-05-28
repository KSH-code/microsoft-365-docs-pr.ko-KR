---
title: SharePoint Syntex 설정
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Project Cortex에서 콘텐츠 이해 설정
ms.openlocfilehash: 7589003505aafb480872b14a09c383cfbe0dff40
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683556"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="fcfa5-103">SharePoint Syntex 설정</span><span class="sxs-lookup"><span data-stu-id="fcfa5-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="fcfa5-104">관리자는 Microsoft 365 관리 센터를 사용하여 [Microsoft SharePoint Syntex](index.md)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="fcfa5-105">시작하기 전에 다음을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-105">Consider the following before you start:</span></span>

- <span data-ttu-id="fcfa5-106">양식 처리를 사용하도록 설정할 SharePoint 사이트는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="fcfa5-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="fcfa5-107">전부요, 일부인가요, 아니면 특정 사이트인가요?</span><span class="sxs-lookup"><span data-stu-id="fcfa5-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="fcfa5-108">기본 콘텐츠 센터의 이름을 무엇으로 지정하시겠어요?</span><span class="sxs-lookup"><span data-stu-id="fcfa5-108">What will you name your default content center?</span></span>

<span data-ttu-id="fcfa5-109">Microsoft 365 관리 센터에서 초기 설정 후 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="fcfa5-p102">설정하기 전에 사용자 환경에서 컨텐츠 이해도를 설정하고 구성하는 최선의 방법을 계획해야 합니다. 예를 들어 다음과 같은 결정을 내려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="fcfa5-112">양식 처리를 사용하도록 설정할 SharePoint 사이트(모든 사이트, 일부 사이트 또는 선택한 사이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="fcfa5-113">이름 및 관리자 또는 콘텐츠 센터</span><span class="sxs-lookup"><span data-stu-id="fcfa5-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="fcfa5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fcfa5-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="fcfa5-115">Microsoft 365 관리 센터에 액세스하고 SharePoint Syntex를 설정하려면 글로벌 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="fcfa5-116">관리자는 Microsoft 365 관리 센터의 콘텐츠 이해 관리 설정 전반에 걸쳐 설정 후 언제든지 선택한 설정을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

<span data-ttu-id="fcfa5-117">사용자 지정 Power Platform 환경을 사용하고자 계획한다면 이 환경에서 *Project Cortex용 AI Builder* 앱을 [설치하고](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) [AI Builder 크레딧](/power-platform/admin/capacity-add-on)을 할당해야 양식 처리 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-117">If you plan to use a custom Power Platform environment, you must [install the *AI Builder for Project Cortex* app in this environment](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) and [allocate AI Builder credits](/power-platform/admin/capacity-add-on) to it before you can create form processing models.</span></span>

### <a name="licensing"></a><span data-ttu-id="fcfa5-118">라이선싱</span><span class="sxs-lookup"><span data-stu-id="fcfa5-118">Licensing</span></span>

<span data-ttu-id="fcfa5-119">SharePoint Syntex를 사용하려면 조직에 SharePoint Syntex 구독이 있어야 합니다. 각 사용자에게 다음 라이선스가 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-119">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="fcfa5-120">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="fcfa5-120">SharePoint Syntex</span></span>
- <span data-ttu-id="fcfa5-121">SharePoint Syntex - SPO 유형</span><span class="sxs-lookup"><span data-stu-id="fcfa5-121">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="fcfa5-122">SharePoint Syntex용 일반 데이터 서비스</span><span class="sxs-lookup"><span data-stu-id="fcfa5-122">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="fcfa5-123">향후 날짜에 SharePoint Syntex 구독을 취소하거나 평가판이 만료되면 사용자는 더 이상 문서 이해 또는 양식 처리 모델을 만들거나 실행할 수 없으며 콘텐츠 센터 서식 파일을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-123">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="fcfa5-124">또한 용어 저장소 보고서, SKOS 분류법 가져오기 및 내용 유형 푸시는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-124">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="fcfa5-125">내용이 삭제되지 않으며 사이트 사용 권한도 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-125">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="fcfa5-126">AI Builder 크레딧</span><span class="sxs-lookup"><span data-stu-id="fcfa5-126">AI Builder credits</span></span>

<span data-ttu-id="fcfa5-127">조직에 SharePoint Syntex에 대한 SharePoint Syntex 라이선스가 300개 이상 있는 경우 100만 개의 AI Builder 크레딧이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-127">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="fcfa5-128">라이선스 수가 300개 미만인 경우 양식 처리를 사용하려면 AI Builder 크레딧을 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-128">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="fcfa5-129">[AI Builder 계산기](https://powerapps.microsoft.com/ai-builder-calculator)을(를) 사용하여 사용자에게 적합한 AI Builder 용량을 추정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-129">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="fcfa5-130">사용자 지정 Power Platform 환경을 사용하려면 [해당 환경에 크레딧을 할당](/power-platform/admin/capacity-add-on)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-130">If you plan to use a custom Power Platform environment, you must [allocate credits to that environment](/power-platform/admin/capacity-add-on).</span></span>

<span data-ttu-id="fcfa5-131">[Power Platform 관리 센터](https://admin.powerplatform.microsoft.com/resources/capacity)로 이동하여 크레딧 및 사용량을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-131">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="fcfa5-132">SharePoint Syntex를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-132">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="fcfa5-133">Microsoft365 관리 센터에서 **설정** 을 선택하고 **파일 및 콘텐츠** 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-133">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="fcfa5-134">**파일 및 콘텐츠** 섹션에서 **콘텐츠 이해 자동화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-134">In the **Files and content** section, select **Automate content understanding**.</span></span> <span data-ttu-id="fcfa5-135">현재 AI Builder 크레딧의 상태는 **한눈에 보기** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-135">Note that your current AI Builder credit availability is shown in the **At a glance** section.</span></span><br/>

3. <span data-ttu-id="fcfa5-136">**콘텐츠 이해 자동화** 페이지에서 **시작하기** 를 클릭하여 설정 프로세스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-136">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span> <br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fcfa5-137">![설치 시작](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="fcfa5-137">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="fcfa5-138">**양식 처리 구성** 페이지에서 사용자가 특정 SharePoint 문서 라이브러리에 양식 처리 모델을 생성할 수 있도록 허용할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-138">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="fcfa5-139">사용 설정된 해당 Sharepoint 문서 라이브러리 리본에서 **양식 처리 모델을 만들기** 위한 문서 라이브러리 리본의 메뉴 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-139">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="fcfa5-140">**양식 처리 모델** 을(를) 생성하기 위해 어떤 SharePoint 라이브러리에 표시할 것인지에 대해 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-140">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="fcfa5-141">**모든 SharePoint 라이브러리** 를 조직의 모든 SharePoint 라이브러리에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-141">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="fcfa5-142">**선택한 SharePoint 사이트의 라이브러리** 를 선택한 다음, 사용 가능한 사이트를 선택하거나 최대 50개 사이트의 목록을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-142">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="fcfa5-143">**사이트에서 SharePoint 라이브러리를 사용하지 않으려면** SharePoint 라이브러리가 없습니다(설치 후 이 라이브러리를 변경할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fcfa5-143">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fcfa5-144">![양식 처리 사이트 옵션 구성](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="fcfa5-144">![Configure form processing site options](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="fcfa5-145">사이트가 포함된 후 사이트를 제거해도 해당 사이트의 라이브러리에 적용된 기존 모델이나 문서 이해 모델을 라이브러리에 적용하는 기능에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-145">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
    <span data-ttu-id="fcfa5-146">여러 Power Platform 환경을 구성한 경우 양식 처리에 사용할 환경을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-146">If you have multiple Power Platform environments configured, you can choose which one you want to use with for form processing.</span></span> <span data-ttu-id="fcfa5-147">(환경이 하나뿐인 경우 이 옵션이 나타나지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="fcfa5-147">(This option will not appear if you only have one environment.)</span></span>

    ![양식 처리 Power Platform 옵션 구성](../media/content-understanding/setup-power-platform-env.png)

    <span data-ttu-id="fcfa5-149">**Power Platform 환경** 의 경우 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-149">For **Power Platform environment**, you can select:</span></span>
    - <span data-ttu-id="fcfa5-150">**기본 환경 설정을 사용하여** 기본 Power Platform 환경을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-150">**Use the default environment** to use your default Power Platform environment.</span></span>
    - <span data-ttu-id="fcfa5-151">**사용자 지정 환경을 사용하여** 사용자 지정 환경을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-151">**Use a custom environment** to use a custom environment.</span></span> <span data-ttu-id="fcfa5-152">목록에서 사용할 환경을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-152">Choose the environment that you want to use from the list.</span></span> <span data-ttu-id="fcfa5-153">([사용자 지정 환경의 요구 사항을 참조하세요](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).</span><span class="sxs-lookup"><span data-stu-id="fcfa5-153">([See the requirements for a custom environment](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).</span></span>

    <span data-ttu-id="fcfa5-154">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-154">Click **Next**.</span></span>

5. <span data-ttu-id="fcfa5-155">**콘텐츠 센터 생성** 페이지에서 사용자가 문서 이해 모델을 생성하고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-155">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="fcfa5-156">**사이트 이름** 에 대해 콘텐츠 센터 사이트에 지정할 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-156">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="fcfa5-157">**사이트 주소** 는 사이트 이름에 대해 선택한 항목에 따라 사이트의 URL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-157">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="fcfa5-158">변경하려는 경우 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-158">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="fcfa5-159">![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="fcfa5-159">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="fcfa5-160">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-160">Select **Next**.</span></span>

6. <span data-ttu-id="fcfa5-161">**검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-161">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="fcfa5-162">원하는 항목을 선택한 경우 **활성화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-162">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="fcfa5-163">확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-163">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="fcfa5-164">**콘텐츠 이해 자동화** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-164">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="fcfa5-165">이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-165">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="fcfa5-166">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="fcfa5-166">Assign licenses</span></span>

<span data-ttu-id="fcfa5-167">SharePoint Syntex를 구성한 후에는 SharePoint Syntex 기능을 사용할 사용자에게 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-167">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="fcfa5-168">라이선스를 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-168">To assign licenses:</span></span>

1. <span data-ttu-id="fcfa5-169">Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-169">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="fcfa5-170">라이선스를 부여할 사용자를 선택하고 **제품 라이선스 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-170">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="fcfa5-171">드롭다운 메뉴에서 **앱** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-171">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="fcfa5-172">**SharePoint Syntex용 앱 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-172">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="fcfa5-173">**앱** 에서 **SharePoint Syntex용 일반 데이터 서비스**, **SharePoint Syntex** 및 **SharePoint Syntex - SPO 유형** 이 모두 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-173">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fcfa5-174">![Microsoft 365 관리 센터의 SharePoint Syntex 라이선스](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="fcfa5-174">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="fcfa5-175">**변경 사항 저장** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-175">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcfa5-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcfa5-176">See also</span></span>

<span data-ttu-id="fcfa5-177">[양식 처리 모델](/ai-builder/form-processing-model-overview)을(를) 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfa5-177">[Overview of the form processing model](/ai-builder/form-processing-model-overview)</span></span>

<span data-ttu-id="fcfa5-178">[단계별 절차는 다음과 같습니다. 문서 이해 모델(비디오)](https://www.youtube.com/watch?v=DymSHObD-bg)을(를) 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="fcfa5-178">[Step-by-Step: How to Build a Document Understanding Model (video)](https://www.youtube.com/watch?v=DymSHObD-bg)</span></span>

[<span data-ttu-id="fcfa5-179">Power Platform 관리 센터에서 환경 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="fcfa5-179">Create and manage environments in the Power Platform admin center</span></span>](/power-platform/admin/create-environment)
