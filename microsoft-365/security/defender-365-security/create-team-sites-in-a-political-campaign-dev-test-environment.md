---
title: 팀 사이트 만들기 - 정치적 캠페인 개발/테스트 환경
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: '요약: 정치적 캠페인 개발/테스트 환경에서 공용, 개인, 중요 및 극비 SharePoint Online 팀 사이트를 만듭니다.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4f680cfb30de5b6904e5fa489cca368550195b4f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073343"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="ab2f3-103">정치적 캠페인 개발/테스트 환경에서 팀 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="ab2f3-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ab2f3-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="ab2f3-104">**Applies to**</span></span>

- [<span data-ttu-id="ab2f3-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="ab2f3-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- 
 <span data-ttu-id="ab2f3-106">**요약:** 정치적 캠페인 개발/테스트 환경에서 공용, 개인, 중요 및 극비 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
   
<span data-ttu-id="ab2f3-p101">이 문서의 지침을 사용하여 [정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 솔루션에 대한 4가지 다른 유형의 SharePoint Online 팀 사이트가 포함된 개발/테스트 환경을 만듭니다. 이러한 사이트는 **SharePoint 및 비즈니스용 OneDrive** 제목의 항목 10에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="ab2f3-109">1단계: 정치적 캠페인 개발/테스트 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="ab2f3-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="ab2f3-110">먼저 [정치적 캠페인 개발/테스트 환경에 대한 사용자 및 그룹 구성](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)의 지침에 따라 구독, 사용자 및 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="ab2f3-111">2 단계: 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="ab2f3-111">Phase 2: Create labels</span></span>

<span data-ttu-id="ab2f3-112">이 단계에서는 SharePoint Online 팀 사이트에 있는 문서 폴더의 다양한 보안 수준에 대한 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="ab2f3-113">필요한 경우 평가판 구독의 전역 관리자 계정 자격 증명으로 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-113">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="ab2f3-114">도움을 받으려면 [Microsoft 365에 로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ab2f3-115">**Microsoft Office 홈** 탭에서 **관리** 타일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-115">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>

3. <span data-ttu-id="ab2f3-116">브라우저의 새 **Microsoft 365 관리 센터** 탭에서 **관리 센터 > 보안 및 준수** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-116">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>

4. <span data-ttu-id="ab2f3-117">브라우저의 새 **홈 - 보안 및 준수** 탭에서 **분류 > 레이블** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-117">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>

5. <span data-ttu-id="ab2f3-118">**홈 > 레이블** 창에서 **레이블 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-118">From the **Home > Labels** pane, click **Create a label**.</span></span>

6. <span data-ttu-id="ab2f3-119">**레이블 이름 지정** 창에서 **내부** 를 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-119">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>

7. <span data-ttu-id="ab2f3-120">**레이블 설정** 창에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-120">On the **Label settings** pane, click **Next**.</span></span>

8. <span data-ttu-id="ab2f3-121">**설정 검토** 창에서 **이 레이블 만들기**, **닫기** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-121">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

9. <span data-ttu-id="ab2f3-122">추가 레이블에 5-8단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-122">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="ab2f3-123">개인</span><span class="sxs-lookup"><span data-stu-id="ab2f3-123">Private</span></span>
   - <span data-ttu-id="ab2f3-124">중요</span><span class="sxs-lookup"><span data-stu-id="ab2f3-124">Sensitive</span></span>
   - <span data-ttu-id="ab2f3-125">극비</span><span class="sxs-lookup"><span data-stu-id="ab2f3-125">Highly Confidential</span></span>

10. <span data-ttu-id="ab2f3-126">**홈 > 레이블** 창에서 **레이블 게시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>

11. <span data-ttu-id="ab2f3-127">**게시할 레이블 선택** 창에서 **게시할 레이블 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

12. <span data-ttu-id="ab2f3-128">**레이블 선택** 창에서 **추가** 를 클릭하고 네 개의 레이블을 모두 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

13. <span data-ttu-id="ab2f3-129">**완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-129">Click **Done**.</span></span>

14. <span data-ttu-id="ab2f3-130">**게시할 레이블 선택** 창에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-130">On the **Choose labels to publish** pane, click **Next**.</span></span>

15. <span data-ttu-id="ab2f3-131">**위치 선택** 창에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-131">On the **Choose locations** pane, click **Next**.</span></span>

16. <span data-ttu-id="ab2f3-132">**정책 이름 지정** 창에서 **이름** 에 **캠페인** 을 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-132">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

17. <span data-ttu-id="ab2f3-133">**설정 검토** 창에서 **레이블 게시**, **닫기** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="ab2f3-134">3단계: SharePoint Online 팀 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="ab2f3-134">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="ab2f3-135">이 단계에서는 네 가지 유형의 SharePoint Online 팀 사이트에 해당하는 정치적 캠페인을 위한 SharePoint Online 팀 사이트를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-135">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="ab2f3-136">캠페인 수준의 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="ab2f3-136">Campaign wide team site</span></span>

<span data-ttu-id="ab2f3-137">초기 공용 SharePoint Online 팀 사이트를 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-137">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="ab2f3-138">필요한 경우 로컬 컴퓨터에서 브라우저를 사용하여 전역 관리자 계정으로 관리 센터(<https://admin.microsoft.com>)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-138">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ab2f3-139">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-139">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ab2f3-140">브라우저의 새 **SharePoint** 탭에서 **+ 사이트 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-140">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ab2f3-141">**사이트 만들기** 페이지에서 **팀 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-141">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ab2f3-142">**사이트 이름** 에 **캠페인 수준** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-142">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="ab2f3-143">**팀 사이트 설명** 에서 **전체 캠페인에 대한 SharePoint 사이트** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-143">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="ab2f3-144">**개인 정보 설정** 에서 **공개 – 조직의 모든 사용자가 이 사이트에 액세스할 수 있습니다.** 를 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-144">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ab2f3-145">**어떤 사람을 추가하시겠습니까?** 창에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="ab2f3-146">그런 다음, 내부 레이블에 대한 캠페인 수준 팀 사이트의 문서 폴더를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-146">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="ab2f3-147">브라우저의 **캠페인 수준 - 홈** 탭에서 **문서** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-147">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ab2f3-148">설정 아이콘을 클릭한 다음, **라이브러리 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-148">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ab2f3-149">**권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ab2f3-150">**설정 - 레이블 적용** 에서 **내부** 를 선택하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-150">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="ab2f3-151">캠페인 프로젝트 1 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="ab2f3-151">Campaign project 1 team site</span></span>

<span data-ttu-id="ab2f3-152">캠페인 내에서 프로젝트에 대한 초기 개인 SharePoint Online 팀 사이트를 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-152">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="ab2f3-153">필요한 경우 로컬 컴퓨터에서 브라우저를 사용하여 전역 관리자 계정으로 관리 센터(<https://admin.microsoft.com>)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-153">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ab2f3-154">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-154">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ab2f3-155">브라우저의 새 **SharePoint** 탭에서 **+ 사이트 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-155">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ab2f3-156">**사이트 만들기** 페이지에서 **팀 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-156">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ab2f3-157">**사이트 이름** 에 **캠페인 프로젝트 1** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-157">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="ab2f3-158">**팀 사이트 설명** 에 **캠페인 프로젝트 1에 대한 SharePoint 사이트** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-158">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="ab2f3-159">**개인 정보 설정** 에서 **비공개 – 구성원만 이 사이트에 액세스할 수 있습니다.** 를 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-159">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ab2f3-160">**어떤 사람을 추가하시겠습니까?** 창에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-160">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="ab2f3-161">그런 다음, 비공개 레이블에 대한 캠페인 프로젝트 1 팀 사이트의 문서 폴더를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-161">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="ab2f3-162">브라우저의 **캠페인 프로젝트 1 - 홈** 탭에서 **문서** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-162">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ab2f3-163">설정 아이콘을 클릭한 다음, **라이브러리 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-163">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ab2f3-164">**권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ab2f3-165">**설정 - 레이블 적용** 에서 **개인** 을 선택하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-165">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="ab2f3-166">캠페인 마케팅 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="ab2f3-166">Campaign marketing team site</span></span>

<span data-ttu-id="ab2f3-167">캠페인 마케팅 리소스에 대해 격리된 중요 수준 SharePoint Online 팀 사이트를 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-167">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="ab2f3-168">로컬 컴퓨터에서 브라우저를 사용하여 전역 관리자 계정으로 관리 센터(<https://admin.microsoft.com>)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-168">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ab2f3-169">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-169">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ab2f3-170">브라우저의 새 **SharePoint** 탭에서 **+ 사이트 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-170">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ab2f3-171">**사이트 만들기** 페이지에서 **팀 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-171">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ab2f3-172">**팀 사이트 이름** 에 **캠페인 마케팅** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-172">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="ab2f3-173">**팀 사이트 설명** 에 **캠페인 마케팅에 대한 SharePoint 사이트(중요)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-173">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="ab2f3-174">**개인 정보 설정** 에서 **비공개 – 구성원만 이 사이트에 액세스할 수 있습니다.** 를 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-174">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ab2f3-175">**어떤 사람을 추가하시겠습니까?** 창에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-175">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="ab2f3-176">브라우저의 새 **캠페인 마케팅** 탭에 있는 도구 모음에서 설정 아이콘을 클릭한 다음, **사이트 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-176">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="ab2f3-177">**사이트 권한** 창에서 **고급 권한 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-177">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="ab2f3-178">브라우저의 새 **권한** 탭에서 **액세스 요청 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-178">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="ab2f3-179">**액세스 요청 설정** 대화 상자에서 **구성원이 사이트와 개별 파일 및 폴더를 공유할 수 있도록 허용합니다.** 및 **구성원이 다른 사용자들을 사이트 구성원 그룹에 초대할 수 있도록 허용합니다.** 확인란의 선택을 취소하고 **모든 액세스 요청 보내기** 에 **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** 을 입력하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-179">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="ab2f3-180">목록에서 **캠페인 마케팅 구성원** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-180">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="ab2f3-181">**사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-181">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="ab2f3-182">**공유** 대화 상자에 **선임 및 전략적 직원** 를 입력하고 선택한 후 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-182">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="ab2f3-183">**분석 직원** 그룹과 **Regular1** 사용자 계정에 대해 14 및 15 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-183">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="ab2f3-184">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-184">Click the back button on your browser.</span></span>

18. <span data-ttu-id="ab2f3-185">목록에서 **캠페인 마케팅 소유자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-185">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="ab2f3-186">**사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-186">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="ab2f3-187">**공유** 대화 상자에서 **IT 직원** 를 입력하고 선택한 후 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-187">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="ab2f3-188">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-188">Click the back button on your browser.</span></span>

22. <span data-ttu-id="ab2f3-189">브라우저에서 **사용자 및 그룹** 탭을 닫고 브라우저에서 **캠페인 마케팅 - 홈** 탭을 클릭한 다음, **사이트 권한** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-189">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="ab2f3-190">권한 구성의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-190">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="ab2f3-191">**캠페인 마케팅 - 구성원** SharePoint 그룹에는 **선임 및 전략적 직원** 그룹(Candidate, ChiefOfStaff 및 Strategic1 사용자 계정 포함), **마케팅 캠페인** 그룹(전역 관리자 사용자 계정 포함) 그룹, **분석 직원** 그룹(DataScientist1 사용자 계정을 포함) 및 **Regular1** 사용자 계정만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-191">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="ab2f3-192">**캠페인 마케팅 - 소유자** SharePoint 그룹에는 **IT 직원** 그룹(ITAdmin1 및 ITAdmin2 사용자 계정만 포함) 그룹만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-192">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="ab2f3-193">**캠페인 마케팅 - 방문자** SharePoint 그룹에는 그룹 또는 사용자 계정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-193">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="ab2f3-194">구성원은 사이트 수준 권한을 수정할 수 없습니다(이 작업은 **캠페인 마케팅 - 소유자** 그룹의 구성원만 수행할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="ab2f3-194">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="ab2f3-195">다른 사용자 계정은 사이트 또는 해당 리소스에 액세스할 수 없지만, 해당 사이트에 대한 액세스는 요청할 수 있으며, 이 사이트에서 ITAdmin1 사용자 계정 사서함으로 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-195">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="ab2f3-196">그런 다음, 중요 레이블에 대한 캠페인 마케팅 팀 사이트의 문서 폴더를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-196">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="ab2f3-197">브라우저의 **캠페인 마케팅 - 홈** 탭에서 **문서** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-197">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ab2f3-198">설정 아이콘을 클릭한 다음, **라이브러리 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-198">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ab2f3-199">**권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ab2f3-200">**설정 - 레이블 적용** 에서 **중요** 를 선택하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-200">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="ab2f3-p103">그런 다음, SharePoint Online 팀 사이트의 문서를 조직 외부의 중요 레이블과 공유할 때 사용자에게 알리는 DLP(데이터 손실 방지) 정책을 구성합니다. 이 DLP 정책은 캠페인 마케팅 사이트의 리소스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="ab2f3-203">브라우저의 **Microsoft Office 홈** 탭에서 **보안 및 준수 센터** 타일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-203">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="ab2f3-204">브라우저의 새 **보안 및 준수** 탭에서 **데이터 손실 방지 > 정책** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-204">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="ab2f3-205">**데이터 손실 방지** 창에서 **+ 정책 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-205">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="ab2f3-206">**서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-206">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="ab2f3-207">**정책 이름 지정** 창의 **이름** 에서 **중요 레이블 SharePoint Online 팀 사이트** 를 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-207">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="ab2f3-208">**위치 선택** 창에서 **특정 위치 선택 허용** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-208">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="ab2f3-209">위치 목록에서 **Exchange 전자 메일** 및 **OneDrive 계정** 위치를 사용하지 않도록 설정하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-209">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="ab2f3-210">**보호할 중요 정보의 유형 사용자 지정** 창에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-210">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="ab2f3-211">**보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **레이블** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-211">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="ab2f3-212">**레이블** 창에서 **+ 추가** 를 클릭하고, **중요** 레이블을 선택하고, **추가** 를 클릭한 다음, **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-212">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="ab2f3-213">**보호할 콘텐츠 유형 선택** 창에서 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-213">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="ab2f3-214">**Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-214">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="ab2f3-215">**중요한 정보를 발견하면** 창에서 **팁 및 전자 메일 사용자 지정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-215">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="ab2f3-216">**Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-216">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="ab2f3-217">텍스트 상자에 다음을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-217">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="ab2f3-p104">조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="ab2f3-221">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-221">Click **OK**.</span></span>

17. <span data-ttu-id="ab2f3-222">**중요한 정보를 감지하는 경우 어떻게 하시겠어요?** 창에서 **사용자의 공유를 차단하고 공유 콘텐츠에 대한 액세스를 제한** 확인란의 선택을 취소하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-222">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="ab2f3-223">**정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-223">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="ab2f3-224">**설정 검토 창** 에서 **만들기**, **닫기** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-224">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="ab2f3-225">캠페인 전략 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="ab2f3-225">Campaign strategy team site</span></span>

<span data-ttu-id="ab2f3-226">캠페인 전략 리소스에 대해 격리된 극비 수준의 SharePoint Online 팀 사이트를 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-226">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="ab2f3-227">필요한 경우 로컬 컴퓨터에서 브라우저를 사용하여 전역 관리자 계정으로 관리 센터(<https://admin.microsoft.com>)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-227">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="ab2f3-228">타일 목록에서 **SharePoint** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-228">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="ab2f3-229">브라우저의 새 **SharePoint** 탭에서 **+ 사이트 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-229">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="ab2f3-230">**사이트 만들기** 페이지에서 **팀 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-230">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="ab2f3-231">**팀 사이트 이름** 에 **캠페인 전략** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-231">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="ab2f3-232">**팀 사이트 설명** 에 **캠페인 전략에 대한 SharePoint 사이트(극비)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-232">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="ab2f3-233">**개인 정보 설정** 에서 **비공개 – 구성원만 이 사이트에 액세스할 수 있습니다.** 를 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-233">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="ab2f3-234">**어떤 사람을 추가하시겠습니까?** 창에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-234">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="ab2f3-235">브라우저의 새 **캠페인 전략** 탭에 있는 도구 모음에서 설정 아이콘을 클릭한 다음, **사이트 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-235">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="ab2f3-236">**사이트 권한** 창에서 **고급 권한 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-236">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="ab2f3-237">브라우저의 새 **권한** 탭에서 **액세스 요청 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-237">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="ab2f3-238">**액세스 요청 설정** 대화 상자에서 **구성원이 사이트와 개별 파일 및 폴더를 공유할 수 있도록 허용합니다.** 및 **구성원이 다른 사용자들을 사이트 구성원 그룹에 초대할 수 있도록 허용합니다.** 확인란의 선택을 취소하고(3개 확인란이 모두 선택 취소됨) **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-238">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="ab2f3-239">목록에서 **캠페인 전략 구성원** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-239">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="ab2f3-240">**사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-240">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="ab2f3-241">**공유** 대화 상자에 **선임 및 전략적 직원** 를 입력하고 선택한 후 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-241">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="ab2f3-242">목록에서 **캠페인 전략 소유자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-242">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="ab2f3-243">**사용자 및 그룹** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-243">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="ab2f3-244">**공유** 대화 상자에서 **IT 직원** 를 입력하고 선택한 후 **공유** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-244">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="ab2f3-245">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-245">Click the back button on your browser.</span></span>

20. <span data-ttu-id="ab2f3-246">브라우저에서 **사용자 및 그룹** 탭을 닫고 브라우저에서 **캠페인 전략 - 홈** 탭을 클릭한 다음, **사이트 권한** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-246">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="ab2f3-247">권한 구성의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-247">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="ab2f3-248">**캠페인 전략 - 구성원** SharePoint 그룹에는 **선임 및 전략적 직원** 그룹(Candidate, ChiefOfStaff 및 Strategic1 사용자 계정만 포함) 및 **캠페인 전략** 그룹(전역 관리자 사용자 계정만 포함)만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-248">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="ab2f3-249">**캠페인 전략 - 소유자** SharePoint 그룹에는 **IT 직원** 그룹(ITAdmin1 및 ITAdmin2 사용자 계정만 포함) 그룹만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-249">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="ab2f3-250">**캠페인 전략 - 방문자** SharePoint 그룹에는 그룹 또는 사용자 계정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-250">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="ab2f3-251">구성원은 사이트 수준 권한을 수정할 수 없습니다(이 작업은 **캠페인 전략 - 소유자** 그룹의 구성원만 수행할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="ab2f3-251">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="ab2f3-p105">다른 사용자 계정은 사이트 또는 해당 리소스에 액세스하거나 사이트에 대한 액세스를 요청할 수 없습니다. 사이트에 대한 추가 권한은 전역 관리자 또는 **캠페인 전략 - 소유자** 그룹의 구성원이 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="ab2f3-254">그런 다음, 극비 레이블에 대한 캠페인 전략 팀 사이트의 문서 폴더를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-254">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="ab2f3-255">브라우저의 **캠페인 전략 - 홈** 탭에서 **문서** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-255">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="ab2f3-256">설정 아이콘을 클릭한 다음, **라이브러리 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-256">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="ab2f3-257">**권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-257">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="ab2f3-258">**설정 - 레이블 적용** 에서 **극비** 를 선택하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-258">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="ab2f3-p106">그런 다음, SharePoint Online 팀 사이트의 문서를 조직 외부의 극비 레이블과 공유할 때 사용자를 차단하는 DLP 정책을 구성합니다. 이 DLP 정책은 캠페인 전략 사이트의 리소스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="ab2f3-261">필요한 경우 로컬 컴퓨터에서 브라우저를 사용하여 보안 관리자 또는 회사 관리자 역할이 있는 계정으로 관리 센터(<https://admin.microsoft.com>)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-261">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="ab2f3-262">브라우저의 **Microsoft Office 홈** 탭에서 **보안 및 준수 센터** 타일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-262">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="ab2f3-263">브라우저의 새 **보안 및 준수** 탭에서 **데이터 손실 방지 > 정책** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-263">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="ab2f3-264">**데이터 손실 방지** 창에서 **+ 정책 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-264">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="ab2f3-265">**서식 파일로 시작하거나 사용자 지정 정책 만들기** 창에서 **사용자 지정**, **다음** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-265">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="ab2f3-266">**정책 이름 지정** 창의 **이름** 에서 **극비 레이블 SharePoint Online 팀 사이트** 를 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-266">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="ab2f3-267">**위치 선택** 창에서 **특정 위치 선택 허용** 을 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-267">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="ab2f3-268">위치 목록에서 **Exchange 전자 메일** 및 **OneDrive 계정** 위치를 사용하지 않도록 설정하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-268">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="ab2f3-269">**보호할 중요 정보의 유형 사용자 지정** 창에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-269">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="ab2f3-270">**보호할 콘텐츠 유형 선택** 창의 드롭다운 상자에서 **추가**, **레이블** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-270">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="ab2f3-271">**레이블** 창에서 **+ 추가** 를 클릭하고, **극비** 레이블을 선택하고, **추가** 를 클릭한 다음, **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-271">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="ab2f3-272">**보호할 콘텐츠 유형 선택** 창에서 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-272">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="ab2f3-273">**Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-273">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="ab2f3-274">**중요한 정보를 발견하면** 창에서 **팁 및 전자 메일 사용자 지정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-274">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="ab2f3-275">**Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-275">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="ab2f3-276">텍스트 상자에 다음을 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-276">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="ab2f3-p107">조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. 파일, 문서 보호, 암호 설정을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="ab2f3-280">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-280">Click **OK**.</span></span>

18. <span data-ttu-id="ab2f3-281">**중요한 정보를 감지하는 경우 어떻게 하시겠어요?** 창에서 **재정의하려면 비즈니스 사유 필요** 를 선택하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-281">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="ab2f3-282">**정책을 켤까요 아니면 먼저 테스트를 수행할까요?** 창에서 **예, 지금 켜겠습니다.** 를 클릭하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-282">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="ab2f3-283">**설정 검토 창** 에서 **만들기**, **닫기** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-283">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="ab2f3-284">[Microsoft 365 관리 센터에서 Azure RMS 활성화](/information-protection/deploy-use/activate-office365)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-284">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="ab2f3-285">다음으로, 아래 단계에 따라 보호 및 권한에 대한 새 범위 지정 정책 및 하위 레이블을 사용하여 Azure Information Protection을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-285">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="ab2f3-286">보안 관리자 또는 회사 관리자 역할이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-286">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="ab2f3-287">도움을 받으려면 [Office 365에 로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-287">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ab2f3-288">브라우저의 별도 탭에서 Azure Portal(<https://portal.azure.com>)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-288">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="ab2f3-289">검색 창에서 **정보** 를 입력하고 **Azure Information Protection** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-289">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="ab2f3-290">**레이블** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-290">Click **Labels**.</span></span>

5. <span data-ttu-id="ab2f3-291">**기밀** 레이블을 마우스 오른쪽 단추로 클릭하고 **하위 레이블 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-291">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="ab2f3-292">**이름** 에 **CampaignStrategy** 를 입력하고 **설명** 에 **캠페인 전략 팀 사이트의 문서에 대한 레이블** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-292">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="ab2f3-293">**이 레이블을 포함하는 문서 및 전자 메일에 대한 권한 설정** 에서 **보호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-293">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="ab2f3-294">**보호** 섹션에서 **Azure(클라우드 키)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-294">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="ab2f3-295">**보호** 블레이드의 **보호 설정** 아래에서 **+ 권한 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-295">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="ab2f3-296">**권한 추가** 블레이드의 **사용자 및 그룹 지정** 아래에서 **+ 디렉터리 찾아보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-296">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="ab2f3-297">**AAD 사용자 및 그룹** 창에서 **선임 및 전략적 직원** 을 선택하고 **선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-297">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="ab2f3-298">**미리 설정된 또는 설정된 사용자 지정에서 권한 선택** 에서 **사용자 지정** 을 클릭한 다음 **권한 보기**, **콘텐츠 편집**, **저장**, **회신** 및 **모두 회신** 확인란을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-298">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="ab2f3-299">**확인** 를 두 번 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-299">Click **OK** twice.</span></span>

14. <span data-ttu-id="ab2f3-300">**하위 레이블** 블레이드에서 **저장** 을 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-300">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="ab2f3-301">**Azure Information Protection** 블레이드에서 **정책 > + 새 정책 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-301">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="ab2f3-302">**정책 이름** 에 **CampaignStrategy** 를 입력하고 **설명** 에 **캠페인 전략 팀 사이트의 문서** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-302">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="ab2f3-303">**이 정책을 가져올 사용자 또는 그룹을 선택합니다 > 사용자/그룹** 을 클릭한 후 **선임 및 전략적 직원** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-303">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="ab2f3-304">**선택 \> 확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-304">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="ab2f3-p109">**레이블 추가 또는 제거** 를 클릭합니다. **정책: 레이블 추가 또는 제거** 창에서 **캠페인 전략** 을 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="ab2f3-307">**저장** 을 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-307">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="ab2f3-308">이제 이러한 네 가지 사이트에서 문서를 만들고 다양한 사용자 계정으로 해당 문서에 대한 액세스를 테스트할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-308">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="ab2f3-309">Azure Information Protection 및 이 새로운 레이블을 사용하여 문서를 보호하려면 테스트 컴퓨터에 [Azure Information Protection 클라이언트를 설치](/information-protection/rms-client/install-client-app)하고, 관리 센터에서 Office를 설치한 다음, Microsoft Word에서 평가판 구독의 **선임 및 전략적 직원** 그룹에 속한 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2f3-309">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab2f3-310">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab2f3-310">See Also</span></span>

[<span data-ttu-id="ab2f3-311">정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침</span><span class="sxs-lookup"><span data-stu-id="ab2f3-311">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="ab2f3-312">정치적 캠페인 개발/테스트 환경에 대해 그룹 및 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="ab2f3-312">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="ab2f3-313">클라우드 도입 TLG(테스트 랩 가이드)</span><span class="sxs-lookup"><span data-stu-id="ab2f3-313">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="ab2f3-314">Microsoft 365 솔루션 및 아키텍처 센터</span><span class="sxs-lookup"><span data-stu-id="ab2f3-314">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)