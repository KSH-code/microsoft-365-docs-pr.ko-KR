---
title: 보존 레이블 및 DLP를 사용하여 팀에서 파일을 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: '요약: 다양한 정보 보호 수준을 통해 팀 파일에 보존 레이블 및 DLP(데이터 손실 방지) 정책을 적용합니다.'
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083411"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="a6399-103">보존 레이블 및 DLP를 사용하여 팀에서 파일을 보호</span><span class="sxs-lookup"><span data-stu-id="a6399-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="a6399-104">이 문서의 단계를 사용하여 초기, 중요 및 극비 팀과 이에 해당하는 기본 SharePoint 사이트에 대한 보존 레이블과 DLP(데이터 손실 방지) 정책을 디자인하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="a6399-105">이러한 3계층 보호에 대한 자세한 내용은 [Microsoft Teams에서의 파일 보호](secure-files-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6399-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="a6399-106">작동 방식</span><span class="sxs-lookup"><span data-stu-id="a6399-106">How this works</span></span>

1. <span data-ttu-id="a6399-107">원하는 보존 레이블을 만들고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="a6399-108">게시하는데 최대 12시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="a6399-109">원하는 기본 SharePoint 사이트에서 문서 라이브러리 설정을 편집하여 원하는 보존 레이블을 라이브러리의 항목에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="a6399-110">보존 레이블을 기반으로 작업을 수행하는 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="a6399-111">사용자가 팀의 기본 SharePoint 사이트 라이브러리에 문서를 추가하면 기본적으로 문서에 할당된 보존 레이블이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="a6399-112">사용자는 필요한 경우 레이블을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-112">Users can change the label, if needed.</span></span> <span data-ttu-id="a6399-113">사용자가 조직 외부에 문서를 공유하면 DLP는 레이블이 할당되었는지 확인하고 DLP 정책이 레이블과 일치하면 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="a6399-114">DLP는 이러한 유형의 정책이 구성되어 있는 경우 신용 카드 번호로 파일을 보호하는 것과 같은 다른 정책 일치도 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="a6399-115">기본 SharePoint 사이트에 대한 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="a6399-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="a6399-116">기본 SharePoint 사이트에 보존 레이블을 만들고 할당하는 경우 다음 세 가지 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="a6399-117">1단계: 보존 레이블 이름 결정</span><span class="sxs-lookup"><span data-stu-id="a6399-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="a6399-118">이 단계에서는 기본 SharePoint 사이트에 적용되는 네 가지 정보 보호 수준에 대한 보존 레이블의 이름을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="a6399-119">다음 표에는 각 수준에 권장되는 이름이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="a6399-120">**기본 SharePoint 사이트 보호 수준**</span><span class="sxs-lookup"><span data-stu-id="a6399-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="a6399-121">**레이블 이름**</span><span class="sxs-lookup"><span data-stu-id="a6399-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6399-122">초기 공용</span><span class="sxs-lookup"><span data-stu-id="a6399-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="a6399-123">내부 공용</span><span class="sxs-lookup"><span data-stu-id="a6399-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="a6399-124">초기 개인</span><span class="sxs-lookup"><span data-stu-id="a6399-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="a6399-125">개인</span><span class="sxs-lookup"><span data-stu-id="a6399-125">Private</span></span>  <br/> |
|<span data-ttu-id="a6399-126">중요</span><span class="sxs-lookup"><span data-stu-id="a6399-126">Sensitive</span></span>  <br/> |<span data-ttu-id="a6399-127">중요</span><span class="sxs-lookup"><span data-stu-id="a6399-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="a6399-128">극비</span><span class="sxs-lookup"><span data-stu-id="a6399-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="a6399-129">극비</span><span class="sxs-lookup"><span data-stu-id="a6399-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="a6399-130">2단계: 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="a6399-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="a6399-131">이 단계에서는 서로 다른 수준의 정보 보호를 위해 결정한 레이블을 만들어 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="a6399-132">보안 관리자 또는 회사 관리자 역할이 있는 계정으로 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="a6399-133">브라우저의 **홈 - Microsoft 365 규정 준수** 탭에서 **분류 > 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="a6399-134">**보존 레이블 > 레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="a6399-135">**레이블 명칭 만들기** 창에서 레이블 이름과 관리자 및 사용자에 대한 설명을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="a6399-136">**파일 계획 설명자** 창에서 필요에 따라 작성한 다음, **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a6399-137">필요에 따라 **레이블 설정** 창에서 **보존**을 **켜기**로 설정하고 보존 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="a6399-138">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="a6399-139">**설정 검토** 창에서 **레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="a6399-140">추가 레이블의 경우 **레이블 만들기**를 클릭한 다음, 필요에 따라 이 절차의 3~7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="a6399-141">새 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-141">Publish your new labels</span></span>

<span data-ttu-id="a6399-142">그리고 나서 다음의 단계를 사용하여 새 보존 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="a6399-143">**레이블** 창에서 **레이블 보존**탭을 클릭한 다음 **레이블 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="a6399-144">**게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="a6399-145">**레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="a6399-146">**완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="a6399-147">**게시할 레이블 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="a6399-148">**위치 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="a6399-149">**정책 이름 지정** 창의 **이름**에서 레이블 집합 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a6399-150">**설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="a6399-151">3단계: 기본 SharePoint 사이트에 대한 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="a6399-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="a6399-152">다음 단계에 따라 보존 레이블을 기본 SharePoint 사이트의 문서 폴더에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="a6399-153">팀에서 **파일**을 클릭한 다음 **SharePoint에서 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="a6399-154">브라우저의 새 SharePoint 사이트 탭에서 **문서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="a6399-155">설정 아이콘을 클릭한 다음 **라이브러리 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="a6399-156">**권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="a6399-157">**설정 - 레이블 적용**에서 적절한 레이블을 선택하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="a6399-158">SharePoint 사이트의 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="a6399-159">1-6단계를 반복하여 추가 기본 SharePoint 사이트에 보존 레이블을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="a6399-160">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-160">Here is your resulting configuration.</span></span>
  
![기본 SharePoint 사이트의 4가지 유형에 대한 보존 레이블입니다.](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="a6399-162">기본 SharePoint 사이트에 대한 DLP 정책</span><span class="sxs-lookup"><span data-stu-id="a6399-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="a6399-163">다음 단계를 사용하여 사용자가 조직 외부의 중요 기본 SharePoint 사이트에서 문서를 공유할 때 다른 사용자에게 알려주는 DLP 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="a6399-164">보안 관리자 또는 회사 관리자 역할이 있는 계정으로 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="a6399-165">브라우저의 새 **Microsoft 365 규정 준수** 탭에서 **정책 > 데이터 손실 방지**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="a6399-166">**홈 > 데이터 손실 방지** 창에서 **정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="a6399-167">**서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="a6399-168">**정책 이름 지정** 창의 **이름**에서 중요 수준 DLP 정책의 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a6399-169">**위치 선택** 창에서 **특정 위치 선택 허용**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a6399-170">위치 목록에서 **Exchange 전자 메일**, **OneDrive 계정** 및 **팀 채팅 및 채널 메시지** 를 사용하지 않도록 설정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a6399-171">**보호할 콘텐츠 유형 사용자 지정** 창에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="a6399-172">**보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **보존 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="a6399-173">**보존 레이블** 창에서 **+추가**를 클릭하고, **중요** 레이블을 선택하고, **추가**를 클릭한 다음, **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="a6399-174">**보호할 콘텐츠 유형 선택** 창에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="a6399-175">**보호할 콘텐츠 유형 사용자 지정** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="a6399-176">\*\*중요한 정보를 발견하면 \*\* 창에서 **팁 및 전자 메일 사용자 지정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="a6399-177">**Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="a6399-178">텍스트 상자에서 다음과 팁 중 하나를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="a6399-p106">조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="a6399-p107">극비 파일은 암호화를 통해 보호됩니다. IT 부서에서 사용 권한을 부여받은 외부 사용자만 극비 파일을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="a6399-184">또는 조직 외부에 파일을 공유하는 방법을 사용자에게 지시하는 사용자 고유의 정책 팁을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="a6399-185">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="a6399-186">**중요한 정보를 발견 시 어떠한 작업을 수행하시겠습니까?** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="a6399-187">**정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="a6399-188">**설정 검토 창**에서 **만들기**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="a6399-189">결과적으로 중요한 팀에 대한 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![민감한 보존 레이블을 사용하는 중요한 팀에 대한 DLP 정책](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="a6399-191">다음 단계를 사용하여 사용자가 조직 외부의 중요 기본 SharePoint 사이트에서 문서를 공유할 때 사용자를 차단하는 DLP 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="a6399-192">브라우저의 새 **Microsoft 365 규정 준수** 탭에서 **정책 > 데이터 손실 방지**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="a6399-193">**데이터 손실 방지** 창에서 **정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="a6399-194">**서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="a6399-195">**정책 이름 지정** 창의 **이름**에서 이름에 극비 수준 DLP 정책의 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="a6399-196">**위치 선택** 창에서 **특정 위치 선택 허용**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a6399-197">위치 목록에서 **Exchange 전자 메일**, **OneDrive 계정** 및 **팀 채팅 및 채널 메시지** 를 사용하지 않도록 설정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a6399-198">**보호할 중요 정보의 유형 사용자 지정** 창에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="a6399-199">**보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **보존 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="a6399-200">**레이블** 창에서 **추가**를 클릭하고, **극비** 레이블을 선택하고, **추가**를 클릭한 다음, **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="a6399-201">**보호할 콘텐츠 유형 선택** 창에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="a6399-202">**Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="a6399-203">\*\*중요한 정보를 발견하면 \*\* 창에서 **팁 및 전자 메일 사용자 지정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="a6399-204">**Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="a6399-205">텍스트 상자에 다음을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="a6399-p108">조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="a6399-209">또는 조직 외부의 파일을 공유하는 방법을 사용자에게 지시하는 사용자 고유의 정책 팁을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="a6399-210">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="a6399-211">**중요한 정보를 발견 시 어떠한 작업을 수행하시겠습니까?** 창의 **한 번에 특정 양의 중요한 정보가 공유되는 경우 감지** 아래에서, **액세스 제한 또는 콘텐츠 암호화**를 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="a6399-212">**정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="a6399-213">**설정 검토 창**에서 **만들기**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="a6399-214">결과적으로 극비 팀에 대한 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6399-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![극비 보존 레이블을 사용하는 극비 팀에 대한 DLP 정책](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="a6399-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a6399-216">Next step</span></span>

[<span data-ttu-id="a6399-217">민감도 레이블을 사용하여 팀에서 파일 보호</span><span class="sxs-lookup"><span data-stu-id="a6399-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="a6399-218">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6399-218">See Also</span></span>

[<span data-ttu-id="a6399-219">Microsoft Teams에서의 파일 보호</span><span class="sxs-lookup"><span data-stu-id="a6399-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="a6399-220">클라우드 도입 및 하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="a6399-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


