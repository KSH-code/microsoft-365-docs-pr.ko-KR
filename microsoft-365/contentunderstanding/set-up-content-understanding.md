---
title: SharePoint Syntex 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex에서 콘텐츠 이해 설정
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294866"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="15c1a-103">SharePoint Syntex 설정</span><span class="sxs-lookup"><span data-stu-id="15c1a-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="15c1a-104">관리자는 Microsoft 365 관리 센터를 사용 하 여 설치 및 Microsoft SharePoint Syntex을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="15c1a-105">시작 하기 전에 다음 사항을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15c1a-105">Consider the following before you start:</span></span>

- <span data-ttu-id="15c1a-106">양식 처리를 사용 하도록 설정할 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="15c1a-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="15c1a-107">사이트를 모두 또는 선택 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="15c1a-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="15c1a-108">콘텐츠 센터의 이름과 기본 사이트 관리자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="15c1a-109">Microsoft 365 관리 센터의 초기 설치 후에 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="15c1a-110">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="15c1a-111">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="15c1a-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="15c1a-112">설치 전에 환경에서 콘텐츠 이해를 설정 하 고 구성 하는 최상의 방법을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="15c1a-113">예를 들어 다음 이름에 대 한 고려 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="15c1a-114">모든 해당, 일부 또는 선택한 사이트의 양식 처리를 사용 하도록 설정 하려는 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="15c1a-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="15c1a-115">콘텐츠 센터 및 기본 사이트 관리자의 이름</span><span class="sxs-lookup"><span data-stu-id="15c1a-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="15c1a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15c1a-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="15c1a-117">Microsoft 365 관리 센터에 액세스 하 고 콘텐츠 이해를 설정할 수 있으려면 전역 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="15c1a-118">관리자는 설치 후와 Microsoft 365 관리 센터의 콘텐츠를 이해 하는 콘텐츠에 따라 선택한 설정을 언제 든 지 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="15c1a-119">SharePoint Syntex를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="15c1a-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="15c1a-120">Microsoft 365 관리 센터에서 **설치**를 선택 하 고 **조직의 기술 자료** 섹션을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="15c1a-121">**조직의 기술 자료** 섹션에서 **콘텐츠 이해 자동화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![조직 기술 자료 설정 페이지](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="15c1a-123">**SharePoint Syntex 자동화** 페이지에서 **시작** 을 클릭 하 여 설정 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![설치 시작](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="15c1a-125">이미지 태그 설정 페이지에서 [이미지 태그](image-tagging.md)지정을 허용할 것인지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![이미지 태그 지정 옵션 스크린샷](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="15c1a-127">**양식 처리 구성** 페이지에서는 사용자가 AI Builder를 사용 하 여 특정 SharePoint 문서 라이브러리에서 양식 처리 모델을 만들 수 있도록 할 것인지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="15c1a-128">문서 라이브러리 리본 메뉴에서 사용 가능 하도록 설정 된 SharePoint 문서 라이브러리에 **양식 처리 모델을 만들려면** 이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="15c1a-129">**SharePoint 라이브러리에서 양식 처리 모델을 만드는 옵션을 표시 해야 하는**경우 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="15c1a-130">**모든 sharepoint 라이브러리** 를 조직의 모든 sharepoint 라이브러리에서 사용할 수 있도록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="15c1a-131">**선택한 사이트의 라이브러리 에서만**사용 가능 하도록 설정할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![양식 처리 구성](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="15c1a-133">SharePoint 문서 라이브러리에서이 설정을 사용 하도록 설정 해도 라이브러리에 적용 된 기존 모델이 나 라이브러리에 문서 이해 모델을 적용 하는 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="15c1a-134">**콘텐츠 센터 만들기** 페이지에서는 사용자가 문서 이해 모델을 만들고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="15c1a-135">a.</span><span class="sxs-lookup"><span data-stu-id="15c1a-135">a.</span></span> <span data-ttu-id="15c1a-136">**사이트 이름**에 콘텐츠 센터 사이트에 지정할 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="15c1a-137">b.</span><span class="sxs-lookup"><span data-stu-id="15c1a-137">b.</span></span> <span data-ttu-id="15c1a-138">사이트 **주소** 에는 사이트 이름으로 선택한 사항을 기반으로 하 여 사이트의 URL이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="15c1a-139">변경 하려면 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-139">If you want to change it, click **Edit**.</span></span></br>

      ![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="15c1a-141">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-141">Select **Next**.</span></span>

7. <span data-ttu-id="15c1a-142">**검토 및 마침** 페이지에서 선택한 설정을 확인 하 고 변경 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="15c1a-143">선택에 만족 하면 **활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="15c1a-144">확인 페이지에서 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="15c1a-145">**콘텐츠 자동화를 이해** 하는 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="15c1a-146">이 페이지에서 **관리** 를 선택 하 여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="15c1a-147">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="15c1a-147">Assign licenses</span></span>

<span data-ttu-id="15c1a-148">SharePoint Syntex를 구성한 후에는 양식 처리 및 문서 이해 기능을 사용할 사용자에 대 한 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="15c1a-149">라이선스를 할당 하려면:</span><span class="sxs-lookup"><span data-stu-id="15c1a-149">To assign licenses:</span></span>

1. <span data-ttu-id="15c1a-150">Microsoft 365 관리 센터의 **사용자**에서 **활성 사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="15c1a-151">라이선스를 부여할 사용자를 선택 하 고 **제품 라이선스 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="15c1a-152">**추가 할당**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="15c1a-153">**지능형 콘텐츠 서비스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="15c1a-154">**앱**에서 지능형 콘텐츠 서비스와 **지능형 콘텐츠** 서비스 **에 대 한 공통 데이터 서비스가** 모두 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Microsoft 365 관리 센터의 SharePoint Syntex 라이선스](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="15c1a-156">**변경 내용 저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="15c1a-157">AI 건축 제작진</span><span class="sxs-lookup"><span data-stu-id="15c1a-157">AI Builder credits</span></span>

<span data-ttu-id="15c1a-158">조직에 sharepoint Syntex에 대 한 SharePoint Syntex 라이선스가 300 개 이상 있는 경우 100만 AI Builder 크레딧이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="15c1a-159">라이선스 수가 300 개 미만이 면 양식 처리를 사용 하기 위해 AI 빌더 제작진을 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="15c1a-160">[Ai builder 계산기](https://powerapps.microsoft.com/ai-builder-calculator)로 적합 한 ai 작성기 용량을 추정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

1. <span data-ttu-id="15c1a-161">[Power Platform 관리 센터로](https://admin.powerplatform.microsoft.com/resources/capacity) 이동 하 여 크레딧 및 사용 현황을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15c1a-162">SharePoint 문서 라이브러리에서이 설정을 사용 하도록 설정 해도 라이브러리에 적용 된 기존 모델이 나 라이브러리에 문서 이해 모델을 적용할 수 있는 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-162">Enable this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
2. <span data-ttu-id="15c1a-163">**콘텐츠 센터 만들기** 페이지에서는 사용자가 문서 이해 모델을 만들고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-163">From the **Create Content Center** page, you can create a SharePoint content center site for which users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="15c1a-164">a.</span><span class="sxs-lookup"><span data-stu-id="15c1a-164">a.</span></span> <span data-ttu-id="15c1a-165">**사이트 이름**에 대해 콘텐츠 센터 사이트에 사용할 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-165">For **Site name**, type the name you want for the content center site.</span></span></br>
    <span data-ttu-id="15c1a-166">b.</span><span class="sxs-lookup"><span data-stu-id="15c1a-166">b.</span></span> <span data-ttu-id="15c1a-167">사이트 **주소** 는 사이트 이름을 기반으로 사이트의 URL을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-167">The **Site address** shows the URL for your site, based on the site name.</span></span></br>

    > [!NOTE] 
    > <span data-ttu-id="15c1a-168">지원 되는 언어를 선택할 수 있지만 콘텐츠 이해 모델은 영어에만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-168">While you can select any supported language, content understanding models can only be created for English.</span></span></br>

      ![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</br>

3. <span data-ttu-id="15c1a-170">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-170">Select **Next**.</span></span>

4. <span data-ttu-id="15c1a-171">**마침 및 검토** 페이지에서 선택한 설정을 확인 하 고 변경을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-171">On the **Finish and review** page, look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="15c1a-172">선택에 만족 하면 **활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-172">If you are satisfied with your selections, select **Activate**.</span></span>

5. <span data-ttu-id="15c1a-173">사용자가 양식 처리 기본 설정을 추가 하 고 콘텐츠 센터 사이트를 만들었기를 확인 하 여 **정품 인증 된 콘텐츠 이해** 됨 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-173">The **Content understanding activated** page displays, confirming the system added your form processing preferences and created the Content Center site.</span></span> <span data-ttu-id="15c1a-174">**완료**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-174">Select **Done**.</span></span>

6. <span data-ttu-id="15c1a-175">**콘텐츠 자동화를 이해** 하는 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-175">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="15c1a-176">이 페이지에서 **관리** 를 선택 하 여 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1a-176">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="15c1a-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15c1a-177">See also</span></span>

[<span data-ttu-id="15c1a-178">양식 처리 모델 개요</span><span class="sxs-lookup"><span data-stu-id="15c1a-178">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="15c1a-179">단계별: 문서 이해 모델을 작성 하는 방법 (비디오)</span><span class="sxs-lookup"><span data-stu-id="15c1a-179">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

