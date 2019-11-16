---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 데이터 분류
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 Enterprise 테스트 환경의 문서에 대해 Office 365 보존 레이블을 만들고 사용 합니다.
ms.openlocfilehash: e0186bcfc786356b34aff45b1b1e67f54dd40001
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672664"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3d8e5-103">Microsoft 365 Enterprise 테스트 환경에 대 한 데이터 분류</span><span class="sxs-lookup"><span data-stu-id="3d8e5-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3d8e5-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 및 Office 365 Enterprise 테스트 환경 둘 다에 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="3d8e5-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="3d8e5-105">이 문서의 지침을 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 Office 365 보존 레이블을 사용 하 여 데이터 분류를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="3d8e5-107">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3d8e5-108">1 단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="3d8e5-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3d8e5-109">최소 요구 사항을 사용 하 여 간단한 방법으로 Office 365 보존 레이블을 구성 하려면 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3d8e5-110">시뮬레이트된 엔터프라이즈에서 Office 365 보존 레이블을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d8e5-111">Office 365 보존 레이블 테스트에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3d8e5-112">이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="3d8e5-113">2 단계: Office 365 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="3d8e5-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="3d8e5-114">이 단계에서는 SharePoint Online 문서 폴더에 대 한 여러 보존 수준에 대 한 보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="3d8e5-115">전역 관리자 계정을 사용하여 [Microsoft 365 규정 준수 포털](https://compliance.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-115">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="3d8e5-116">브라우저의 **홈 - Microsoft 365 규정 준수** 탭에서 **분류 > 레이블**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-116">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="3d8e5-117">**보존 레이블 > 레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-117">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="3d8e5-118">**레이블 이름 지정** 창에서 **레이블 이름 지정**에 **내부 공용**을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-118">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="3d8e5-119">**파일 플랜 설명자** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-119">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="3d8e5-120">필요에 따라 **레이블 설정** 창에서 **보존**을 **켜기**로 설정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-120">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="3d8e5-121">**설정 검토** 창에서 **레이블 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-121">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="3d8e5-122">아래 이름의 추가 레이블에 대해 3~7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="3d8e5-123">개인</span><span class="sxs-lookup"><span data-stu-id="3d8e5-123">Private</span></span>
    
  - <span data-ttu-id="3d8e5-124">중요</span><span class="sxs-lookup"><span data-stu-id="3d8e5-124">Sensitive</span></span>
    
  - <span data-ttu-id="3d8e5-125">극비</span><span class="sxs-lookup"><span data-stu-id="3d8e5-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="3d8e5-126">\*\*홈 > 레이블 \*\* 창에서 **레이블 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="3d8e5-127">**게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="3d8e5-128">**레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="3d8e5-129">**완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-129">Click **Done**.</span></span>
    
13. <span data-ttu-id="3d8e5-130">**게시할 레이블 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="3d8e5-131">**위치 선택** 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="3d8e5-132">**정책 이름 지정** 창에서 **이름**에 **예제 조직**을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="3d8e5-133">**설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="3d8e5-134">보존 레이블을 게시 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="3d8e5-135">3 단계: 문서에 Office 365 보존 레이블을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="3d8e5-136">이 단계에서는 SharePoint Online 사이트의 문서 폴더에 있는 파일에 대 한 기본 보존 레이블 동작을 검색 하 고 문서의 보존 레이블을 수동으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="3d8e5-137">먼저 중요 한 수준의 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="3d8e5-138">로컬 컴퓨터에서 브라우저를 사용하여 전역 관리자 계정으로 [Office 365 포털](https://portal.office.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-138">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="3d8e5-139">타일 목록에서 **SharePoint**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="3d8e5-140">브라우저의 새 **SharePoint** 탭에서 **사이트 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="3d8e5-141">**사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="3d8e5-142">**팀 사이트 이름**에 **SensitiveFiles**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="3d8e5-143">**팀 사이트 설명**에서 **중요 한 파일에 대 한 SharePoint 사이트**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="3d8e5-144">**개인 정보 설정**에서 **개인 - 구성원만 이 사이트에 액세스할 수 있음**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3d8e5-145">**누구를 추가하시겠습니까?** 창에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="3d8e5-146">그런 다음 SensitiveFiles 팀 사이트의 문서 폴더를 구성 하 여 중요 한 보존 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="3d8e5-147">브라우저의 **SensitiveFiles** 탭에서 **문서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="3d8e5-148">설정 아이콘을 클릭한 다음 **라이브러리 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="3d8e5-149">**권한 및 관리** 아래에서 **이 라이브러리의 항목에 레이블 적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="3d8e5-150">**설정-레이블 적용**에서 드롭다운 상자에서 **중요** 를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-150">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="3d8e5-151">다음으로, SensitiveFiles 사이트에서 새 문서를 만들고 해당 보존 레이블을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-151">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="3d8e5-152">문서 폴더에서 **Word 문서 > 새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-152">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="3d8e5-153">빈 문서에 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-153">Type some text in the blank document.</span></span> <span data-ttu-id="3d8e5-154">텍스트가 저장 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-154">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="3d8e5-155">메뉴 모음에서 **공유 문서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-155">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="3d8e5-156">**문서 .docx** 파일 이름 옆에 있는 Word 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-156">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="3d8e5-157">오른쪽 창의 **속성** 섹션에 있는 **보존 레이블 적용**에서 문서에 **중요 한** 레이블이 자동으로 적용 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-157">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="3d8e5-158">**모두 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-158">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="3d8e5-159">**문서 .docx** 창의 **레이블 적용**에서 **높은 기밀** 레이블을 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-159">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="3d8e5-160">프로덕션 환경에서 Office 365 보존 레이블을 배포 하는 방법에 대 한 자세한 내용과 정보는 **정보 보호** 단계에서 작업 [환경의 분류 구성](infoprotect-configure-classification.md) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-160">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="3d8e5-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3d8e5-161">Next step</span></span>

<span data-ttu-id="3d8e5-162">테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e5-162">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d8e5-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d8e5-163">See also</span></span>

[<span data-ttu-id="3d8e5-164">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="3d8e5-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3d8e5-165">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="3d8e5-165">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3d8e5-166">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="3d8e5-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 