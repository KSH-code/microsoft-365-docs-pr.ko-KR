---
title: 보존 레이블 및 DLP를 사용하여 SharePoint Online 파일 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: '요약: 다양한 정보 보호 수준을 통해 SharePoint Online 팀 사이트에 보존 레이블 및 DLP(데이터 손실 방지) 정책을 적용합니다.'
ms.openlocfilehash: ab9026fa4c00038abb166677277145c8129e33e2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081760"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="ab28f-103">보존 레이블 및 DLP를 사용하여 SharePoint Online 파일 보호</span><span class="sxs-lookup"><span data-stu-id="ab28f-103">Protect SharePoint Online files with retention labels and DLP</span></span>

<span data-ttu-id="ab28f-104">이 문서의 단계를 사용하여 초기, 중요 및 극비 SharePoint Online 팀 사이트에 대한 레이블 및 DLP 정책을 디자인하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-104">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="ab28f-105">이러한 3계층 보호에 대한 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab28f-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="ab28f-106">작동 방식</span><span class="sxs-lookup"><span data-stu-id="ab28f-106">How this works</span></span>

1. <span data-ttu-id="ab28f-107">원하는 보존 레이블을 만들고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="ab28f-108">게시하는데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="ab28f-109">원하는 SharePoint 사이트에서 문서 라이브러리 설정을 편집하여 원하는 보존 레이블을 라이브러리의 항목에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-109">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="ab28f-110">보존 레이블을 기반으로 작업을 수행하는 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="ab28f-111">사용자가 라이브러리에 문서를 추가하면 기본적으로 문서에 할당된 보존 레이블이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-111">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="ab28f-112">사용자는 필요한 경우 레이블을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-112">Users can change the label, if needed.</span></span> <span data-ttu-id="ab28f-113">사용자가 조직 외부에 문서를 공유하면 DLP는 레이블이 할당되었는지 확인하고 DLP 정책이 레이블과 일치하면 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="ab28f-114">DLP는 이러한 유형의 정책이 구성되어 있는 경우 신용 카드 번호로 파일을 보호하는 것과 같은 다른 정책 일치도 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="ab28f-115">SharePoint Online 사이트에 대한 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="ab28f-115">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="ab28f-116">SharePoint Online 팀 사이트에 보존 레이블을 만들고 할당하는 경우 다음 세 가지 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-116">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="ab28f-117">1단계: 보존 레이블 이름 결정</span><span class="sxs-lookup"><span data-stu-id="ab28f-117">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="ab28f-118">이 단계에서는 SharePoint Online 팀 사이트에 적용되는 네 가지 정보 보호 수준에 대한 보존 레이블의 이름을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="ab28f-119">다음 표에는 각 수준에 권장되는 이름이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="ab28f-120">**SharePoint Online 팀 사이트 보호 수준**</span><span class="sxs-lookup"><span data-stu-id="ab28f-120">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="ab28f-121">**레이블 이름**</span><span class="sxs-lookup"><span data-stu-id="ab28f-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab28f-122">초기 공용</span><span class="sxs-lookup"><span data-stu-id="ab28f-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="ab28f-123">내부 공용</span><span class="sxs-lookup"><span data-stu-id="ab28f-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="ab28f-124">초기 개인</span><span class="sxs-lookup"><span data-stu-id="ab28f-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="ab28f-125">개인</span><span class="sxs-lookup"><span data-stu-id="ab28f-125">Private</span></span>  <br/> |
|<span data-ttu-id="ab28f-126">중요</span><span class="sxs-lookup"><span data-stu-id="ab28f-126">Sensitive</span></span>  <br/> |<span data-ttu-id="ab28f-127">중요</span><span class="sxs-lookup"><span data-stu-id="ab28f-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="ab28f-128">극비</span><span class="sxs-lookup"><span data-stu-id="ab28f-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="ab28f-129">극비</span><span class="sxs-lookup"><span data-stu-id="ab28f-129">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="ab28f-130">2 단계: 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="ab28f-130">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="ab28f-131">이 단계에서는 서로 다른 수준의 정보 보호를 위해 결정한 레이블을 만들어 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="ab28f-132">보안 관리자 또는 회사 관리자 역할이 있는 계정으로 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="ab28f-133">브라우저의 **홈 - Microsoft 365 규정 준수** 탭에서 **분류 > 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="ab28f-134">**보존 레이블 > 레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="ab28f-135">**레이블 명칭 만들기** 창에서 레이블 이름과 관리자 및 사용자에 대한 설명을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="ab28f-136">**파일 계획 설명자** 창에서 필요에 따라 작성한 다음, **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ab28f-137">필요에 따라 **레이블 설정** 창에서 **보존**을 **켜기**로 설정하고 보존 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="ab28f-138">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="ab28f-139">**설정 검토** 창에서 **레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="ab28f-140">추가 레이블의 경우 **레이블 만들기**를 클릭한 다음, 필요에 따라 3~7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="ab28f-141">새 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-141">Publish your new labels</span></span>

<span data-ttu-id="ab28f-142">그리고 나서 다음의 단계를 사용하여 새 보존 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="ab28f-143">**레이블** 창에서 **레이블 보존**탭을 클릭한 다음 **레이블 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="ab28f-144">**게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="ab28f-145">**레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="ab28f-146">**완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="ab28f-147">**게시할 레이블 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="ab28f-148">**위치 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="ab28f-149">**정책 이름 지정** 창의 **이름**에서 레이블 집합 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ab28f-150">**설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="ab28f-151">3단계: SharePoint Online 사이트에 보존 레이블 적용하기</span><span class="sxs-lookup"><span data-stu-id="ab28f-151">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="ab28f-152">다음 단계에 따라 보존 레이블을 SharePoint Online 팀 사이트의 문서 폴더에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-152">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="ab28f-153">[Office 365 포털](https://www.office.com)에 로그인하고 **SharePoint** 앱을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-153">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="ab28f-154">브라우저의 새 **SharePoint** 탭에서 할당된 보존 레이블이 필요한 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-154">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="ab28f-155">브라우저의 새 SharePoint 사이트 탭에서 **문서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-155">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="ab28f-156">설정 아이콘을 클릭한 다음 **라이브러리 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-156">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="ab28f-157">**권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-157">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="ab28f-158">**설정 - 레이블 적용**에서 적절한 레이블을 선택하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-158">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="ab28f-159">SharePoint Online 사이트의 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-159">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="ab28f-160">2-8단계를 반복하여 추가 SharePoint Online 사이트에 보존 레이블을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-160">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="ab28f-161">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-161">Here is your resulting configuration.</span></span>
  
![SharePoint Online 팀 사이트의 4가지 유형에 대한 보존 레이블입니다.](../media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="ab28f-163">SharePoint Online 사이트에 대한 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="ab28f-163">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="ab28f-164">다음 단계를 사용하여 사용자가 조직 외부의 중요 SharePoint Online 팀 사이트에서 문서를 공유할 때 다른 사용자에게 알려주는 DLP 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-164">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="ab28f-165">보안 관리자 또는 회사 관리자 역할이 있는 계정으로 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="ab28f-166">브라우저의 새 **Microsoft 365 규정 준수** 탭에서 **정책 > 데이터 손실 방지**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-166">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="ab28f-167">**홈 > 데이터 손실 방지** 창에서 **정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-167">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="ab28f-168">**서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-168">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="ab28f-169">**정책 이름 지정** 창의 **이름**에서 중요 수준 DLP 정책의 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-169">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ab28f-170">**위치 선택** 창에서 **특정 위치 선택 허용**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-170">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="ab28f-171">위치 목록에서 **Exchange 전자 메일**, **OneDrive 계정** 및 **팀 채팅 및 채널 메시지** 를 사용하지 않도록 설정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-171">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ab28f-172">**보호할 콘텐츠 유형 사용자 지정** 창에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-172">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="ab28f-173">**보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **보존 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-173">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="ab28f-174">**보존 레이블** 창에서 **+추가**를 클릭하고, **중요** 레이블을 선택하고, **추가**를 클릭한 다음, **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-174">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="ab28f-175">**보호할 콘텐츠 유형 선택** 창에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-175">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="ab28f-176">**보호할 콘텐츠 유형 사용자 지정** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-176">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="ab28f-177">\*\*중요한 정보를 발견하면 \*\* 창에서 **팁 및 전자 메일 사용자 지정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-177">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="ab28f-178">**Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-178">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="ab28f-179">선택적으로 중요한 파일을 보호하기 위해 민감도 레이블을 사용하는지 여부에 따라 텍스트 상자에 다음 팁 중 하나를 입력하거나 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-179">In the text box, type or paste in one of the following tips, depending on if you are optionallyusing sensitivity labels to protect sensitive files:</span></span>
    
  - <span data-ttu-id="ab28f-p106">조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="ab28f-p107">극비 파일은 암호화를 통해 보호됩니다. IT 부서에서 사용 권한을 부여받은 외부 사용자만 극비 파일을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="ab28f-185">또는 조직 외부에 파일을 공유하는 방법을 사용자에게 지시하는 사용자 고유의 정책 팁을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-185">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="ab28f-186">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-186">Click **OK**.</span></span>
    
17. <span data-ttu-id="ab28f-187">**중요한 정보를 발견 시 어떠한 작업을 수행하시겠습니까?** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-187">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="ab28f-188">**정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-188">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="ab28f-189">**설정 검토 창**에서 **만들기**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-189">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="ab28f-190">결과적으로 중요 SharePoint Online 팀 사이트에 대한 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-190">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![중요 보존 레이블을 사용하는 격리된 SharePoint Online 팀 사이트의 DLP 정책](../media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="ab28f-192">그리고 나서 다음 단계를 사용하여 사용자가 조직 외부의 극비 SharePoint Online 팀 사이트에서 문서를 공유할 때 다른 사용자를 차단하는 DLP 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-192">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="ab28f-193">브라우저의 새 **Microsoft 365 규정 준수** 탭에서 **정책 > 데이터 손실 방지**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-193">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="ab28f-194">**데이터 손실 방지** 창에서 **정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-194">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="ab28f-195">**서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-195">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="ab28f-196">**정책 이름 지정** 창의 **이름**에서 이름에 극비 수준 DLP 정책의 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-196">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="ab28f-197">**위치 선택** 창에서 **특정 위치 선택 허용**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-197">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ab28f-198">위치 목록에서 **Exchange 전자 메일**, **OneDrive 계정** 및 **팀 채팅 및 채널 메시지** 를 사용하지 않도록 설정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-198">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="ab28f-199">**보호할 중요 정보의 유형 사용자 지정** 창에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-199">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="ab28f-200">**보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **보존 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-200">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="ab28f-201">**레이블** 창에서 **추가**를 클릭하고, **극비** 레이블을 선택하고, **추가**를 클릭한 다음, **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-201">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="ab28f-202">**보호할 콘텐츠 유형 선택** 창에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-202">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="ab28f-203">**Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-203">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="ab28f-204">\*\*중요한 정보를 발견하면 \*\* 창에서 **팁 및 전자 메일 사용자 지정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-204">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="ab28f-205">**Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-205">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="ab28f-206">텍스트 상자에 다음을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-206">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="ab28f-p108">조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="ab28f-210">또는 조직 외부의 파일을 공유하는 방법을 사용자에게 지시하는 사용자 고유의 정책 팁을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-210">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="ab28f-211">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-211">Click **OK**.</span></span>
    
17. <span data-ttu-id="ab28f-212">**중요한 정보를 발견 시 어떠한 작업을 수행하시겠습니까?** 창의 **한 번에 특정 양의 중요한 정보가 공유되는 경우 감지** 아래에서, **액세스 제한 또는 콘텐츠 암호화**를 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-212">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="ab28f-213">**정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-213">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="ab28f-214">**설정 검토 창**에서 **만들기**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-214">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="ab28f-215">결과적으로 극비 SharePoint Online 팀 사이트에 대한 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab28f-215">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![높은 수준의 기밀 보존 레이블을 사용하는 격리된 SharePoint Online 팀 사이트의 DLP 정책](../media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="ab28f-217">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ab28f-217">Next step</span></span>

[<span data-ttu-id="ab28f-218">민감도 레이블을 사용하여 SharePoint Online 파일 보호</span><span class="sxs-lookup"><span data-stu-id="ab28f-218">Protect SharePoint Online files with sensitivity labels</span></span>](protect-sharepoint-online-files-with-sensitivity-label.md)
    
## <a name="see-also"></a><span data-ttu-id="ab28f-219">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab28f-219">See Also</span></span>

[<span data-ttu-id="ab28f-220">정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침</span><span class="sxs-lookup"><span data-stu-id="ab28f-220">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="ab28f-221">클라우드 도입 및 하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="ab28f-221">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


