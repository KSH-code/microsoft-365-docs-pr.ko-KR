---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 데이터 분류
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 Enterprise 테스트 환경의 문서에 대해 Office 365 보존 레이블을 만들고 사용 합니다.
ms.openlocfilehash: 6534eff67e9c91423eb6f81415cb3ef2e965dcc1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067995"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="711e6-103">Microsoft 365 Enterprise 테스트 환경에 대 한 데이터 분류</span><span class="sxs-lookup"><span data-stu-id="711e6-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="711e6-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise와 Office 365 Enterprise 테스트 환경 모두에서 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="711e6-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="711e6-105">이 문서의 지침을 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 Office 365 보존 레이블을 사용 하 여 데이터 분류를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="711e6-107">[여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="711e6-108">1단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="711e6-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="711e6-109">최소 요구 사항을 사용 하 여 간단한 방법으로 Office 365 보존 레이블을 구성 하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="711e6-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="711e6-110">시뮬레이트된 엔터프라이즈에서 Office 365 보존 레이블을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="711e6-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="711e6-111">Office 365 보존 레이블 테스트를 수행 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트에 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="711e6-112">이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="711e6-113">2 단계: Office 365 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="711e6-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="711e6-114">이 단계에서는 SharePoint Online 문서 폴더에 대 한 여러 보존 수준에 대 한 보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="711e6-115">전역 관리자 계정을 사용 하 여 [Microsoft 365 보안 센터](https://security.microsoft.com/homepage) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="711e6-116">브라우저의 **집-Microsoft 365 보안** 탭에서 **분류 > 보존 레이블**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="711e6-117">**레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="711e6-118">**레이블 이름** 지정 창에서 **레이블 이름**에 **내부 공용** 을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="711e6-119">**파일 계획 설명자** 창에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="711e6-120">필요한 경우 **레이블 설정** 창에서 **보존** 을 **On**으로 설정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="711e6-121">**설정 검토** 창에서 **레이블 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="711e6-122">아래 이름의 추가 레이블에 대해 3~7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="711e6-123">개인</span><span class="sxs-lookup"><span data-stu-id="711e6-123">Private</span></span>
    
  - <span data-ttu-id="711e6-124">중요</span><span class="sxs-lookup"><span data-stu-id="711e6-124">Sensitive</span></span>
    
  - <span data-ttu-id="711e6-125">극비</span><span class="sxs-lookup"><span data-stu-id="711e6-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="711e6-126">**보존 레이블** 창에서 **레이블 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="711e6-127">**게시할 레이블 선택** 창에서 **게시할 레이블 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="711e6-128">**레이블 선택** 창에서 **추가** 를 클릭 하 고 네 개의 레이블을 모두 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="711e6-129">**추가**를 클릭 한 다음 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="711e6-130">**게시할 레이블 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="711e6-131">**위치 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="711e6-132">**정책 이름 지정** 창에서 **이름**에 **예제 조직**을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="711e6-133">**설정 검토** 창에서 **레이블 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="711e6-134">보존 레이블을 게시 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="711e6-135">3 단계: 문서에 Office 365 보존 레이블을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="711e6-136">이 단계에서는 SharePoint Online 사이트의 문서 폴더에 있는 파일에 대 한 기본 보존 레이블 동작을 검색 하 고 문서의 보존 레이블을 수동으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="711e6-137">먼저 중요 한 수준의 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="711e6-138">브라우저의 개인 인스턴스를 사용 하 여 전역 관리자 계정을 사용 하 여 [Office 365 포털](https://portal.office.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="711e6-139">타일 목록에서 **SharePoint**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="711e6-140">브라우저의 새 **SharePoint** 탭에서 **사이트 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="711e6-141">**사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="711e6-142">**팀 사이트 이름**에 **SensitiveFiles**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="711e6-143">**팀 사이트 설명**에서 **중요 한 파일에 대 한 SharePoint 사이트**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="711e6-144">**개인 정보 설정**에서 **비공개 – 구성원만 이 사이트에 액세스할 수 있습니다.** 를 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="711e6-145">**어떤 사용자를 추가** 하 시겠습니까? 창에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="711e6-146">그런 다음 SensitiveFiles 팀 사이트의 문서 폴더를 구성 하 여 중요 한 보존 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="711e6-147">브라우저의 **SensitiveFiles** 탭에서 **문서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="711e6-148">설정 아이콘을 클릭한 다음 **라이브러리 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="711e6-149">**사용 권한 및 관리**에서 **이 목록 또는 라이브러리의 항목에 레이블 적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="711e6-150">이 옵션이 나타나지 않으면 보존 레이블이 아직 게시 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="711e6-151">나중에이 단계를 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="711e6-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="711e6-152">**설정-레이블 적용**에서 드롭다운 상자에서 **중요** 를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="711e6-153">다음으로, SensitiveFiles 사이트에서 새 문서를 만들고 해당 보존 레이블을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="711e6-154">문서 폴더에서 **Word 문서 > 새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="711e6-155">빈 문서에 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-155">Type some text in the blank document.</span></span> <span data-ttu-id="711e6-156">텍스트가 저장 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="711e6-157">메뉴 모음에서 **공유 문서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="711e6-158">**문서 .docx** 파일 이름 옆에 있는 줄임표를 클릭 한 다음 **세부 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="711e6-159">오른쪽 창의 **속성** 섹션에 있는 **보존 레이블 적용**에서 문서에 **중요 한** 보존 레이블이 자동으로 적용 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="711e6-160">**모두 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="711e6-161">**문서 .docx** 창의 **보존 레이블 적용**에서 **높은 기밀** 레이블을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="711e6-162">프로덕션 환경에서 Office 365 보존 레이블을 배포 하는 방법에 대 한 자세한 내용과 정보는 **정보 보호** 단계에서 작업 [환경의 분류 구성](infoprotect-configure-classification.md) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="711e6-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="711e6-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="711e6-163">Next step</span></span>

<span data-ttu-id="711e6-164">테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="711e6-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="711e6-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="711e6-165">See also</span></span>

[<span data-ttu-id="711e6-166">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="711e6-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="711e6-167">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="711e6-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="711e6-168">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="711e6-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
