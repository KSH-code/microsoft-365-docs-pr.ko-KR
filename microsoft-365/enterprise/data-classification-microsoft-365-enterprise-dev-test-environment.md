---
title: Microsoft 365 기업에 대 한 데이터 분류 테스트 환경
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 만들고 Microsoft 365 기업 테스트 환경에서 문서에 Office 365 레이블을 사용 합니다.
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870333"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="084ed-103">Microsoft 365 기업에 대 한 데이터 분류 테스트 환경</span><span class="sxs-lookup"><span data-stu-id="084ed-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="084ed-104">이 문서의 지침을과 함께 Microsoft 365 기업 테스트 환경에서 Office 365 레이블을 사용 하 여 데이터 분류를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-104">With the instructions in this article, you configure data classification using Office 365 labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="084ed-106">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="084ed-107">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="084ed-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="084ed-108">최소 요구 사항을 경량 방식으로 Office 365 레이블을 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="084ed-109">Office 365 레이블 시뮬레이션 된 엔터프라이즈에서 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="084ed-p101">Office 365 레이블 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="084ed-112">2단계: Office 365 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="084ed-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="084ed-113">이 단계에서는 다양 한 수준의 SharePoint Online 문서 폴더에 대 한 보안에 대 한 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-113">In this phase, you create the labels for the different levels of security for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="084ed-p102">필요한 경우 인터넷 브라우저의 개인 인스턴스를 사용 하 고 전역 관리자 계정 사용 하 여 Office 365 포털에 로그인 합니다. 도움말을 보려면 [Office 365에 로그인 할 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="084ed-p102">If needed, use a private instance of your Internet browser and sign in to the Office 365 portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="084ed-116">**Microsoft Office 홈** 탭에서 **관리** 타일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="084ed-117">브라우저의 새 **Office 관리 센터** 탭에서 **관리 센터 > 보안 및 준수**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="084ed-118">브라우저의 새 **홈 - 보안 및 준수** 탭에서 **분류 > 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-118">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="084ed-119">**홈 > 레이블** 창에서 **레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-119">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="084ed-120">**레이블 이름 지정** 창에서 **내부 공용**을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-120">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="084ed-121">**레이블 설정** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-121">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="084ed-122">**설정 검토** 창에서 **이 레이블 만들기**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-122">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="084ed-123">추가 레이블에 5-8단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-123">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="084ed-124">개인</span><span class="sxs-lookup"><span data-stu-id="084ed-124">Private</span></span>
    
  - <span data-ttu-id="084ed-125">중요</span><span class="sxs-lookup"><span data-stu-id="084ed-125">Sensitive</span></span>
    
  - <span data-ttu-id="084ed-126">극비</span><span class="sxs-lookup"><span data-stu-id="084ed-126">Highly Confidential</span></span>
    
10. <span data-ttu-id="084ed-127">\*\*홈 > 레이블 \*\* 창에서 **레이블 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-127">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="084ed-128">**게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-128">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="084ed-129">**레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-129">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="084ed-130">**완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-130">Click **Done**.</span></span>
    
14. <span data-ttu-id="084ed-131">**게시할 레이블 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-131">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="084ed-132">**위치 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-132">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="084ed-133">**정책 이름 지정** 창에서 **이름**에 **예제 조직**을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-133">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="084ed-134">**설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-134">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="084ed-135">메모를 게시할 수 있는 레이블에 대 한 몇 분정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-135">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-labels-to-documents"></a><span data-ttu-id="084ed-136">3 단계: Office 365 레이블을 문서에 적용</span><span class="sxs-lookup"><span data-stu-id="084ed-136">Phase 3: Apply Office 365 labels to documents</span></span>

<span data-ttu-id="084ed-137">이 단계에서 SharePoint Online 사이트의 문서 폴더의 파일에 대 한 기본 레이블 동작 찾아 수동으로 레이블 문서를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-137">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="084ed-138">먼저, 민감한 수준 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-138">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="084ed-p103">로컬 컴퓨터에서 브라우저를 사용하여 전역 관리자 계정으로 Office 365 포털에 로그인합니다. 도움을 받으려면 [Office 365에 로그인하는 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="084ed-p103">Using a browser on your local computer, sign in to the Office 365 portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="084ed-141">타일 목록에서 **SharePoint**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-141">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="084ed-142">브라우저에서 새 **SharePoint** 탭에서 **사이트 만들기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-142">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="084ed-143">**사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-143">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="084ed-144">**팀 사이트 이름** **SensitiveFiles**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-144">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="084ed-145">**팀 사이트 설명** **중요 한 파일에 대 한 SharePoint 사이트**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-145">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="084ed-146">**개인 정보 설정**에서 **개인 - 구성원만 이 사이트에 액세스할 수 있음**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-146">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="084ed-147">**누구를 추가하시겠습니까?** 창에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-147">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="084ed-148">다음으로 중요 한 레이블에 대 한 SensitiveFiles 팀 사이트의 문서 폴더를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-148">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="084ed-149">브라우저의 **SensitiveFiles** 탭에서 **문서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-149">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="084ed-150">설정 아이콘을 클릭한 다음 **라이브러리 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-150">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="084ed-151">**권한 및 관리** 아래에서 **Apply label to items in this library(이 라이브러리의 항목에 레이블 적용)** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-151">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="084ed-152">**레이블 설정 적용**드롭다운 목록 상자에서 **중요 한** 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="084ed-153">다음으로 SensitiveFiles 사이트에 새 문서를 작성 하 고 해당 레이블을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-153">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="084ed-154">문서 폴더에서 클릭 **새로 만들기 > Word 문서**합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="084ed-p104">다음은 새 문서에 일부 텍스트를 입력 합니다. 텍스트를 저장할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-p104">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="084ed-157">메뉴 모음에서 **공유 문서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="084ed-158">**Document.docx** 파일 이름 옆에 있는 Word 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-158">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="084ed-159">**속성** 섹션 **적용 레이블**아래에서 오른쪽 창에서 문서 자동으로 적용 하는 **중요 한** 레이블 길었던는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-159">In the right-hand pane, in the **Properties** section, under **Apply label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="084ed-160">**모든 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="084ed-161">**Document.docx** 창의 **적용 레이블** **매우 기밀** 레이블 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-161">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="084ed-162">정보 및 프로덕션 환경에서 Office 365 레이블에 대 한 링크에 대 한 **정보 보호** 단계에서 [사용자 환경에 대 한 구성 분류](data-classification-microsoft-365-enterprise-dev-test-environment.md) 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="084ed-162">See the [Configure classification for your environment](data-classification-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to Office 365 labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="084ed-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="084ed-163">Next step</span></span>

<span data-ttu-id="084ed-164">추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능 및 기능 테스트 환경에서 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="084ed-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="084ed-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="084ed-165">See also</span></span>

[<span data-ttu-id="084ed-166">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="084ed-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="084ed-167">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="084ed-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="084ed-168">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="084ed-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 