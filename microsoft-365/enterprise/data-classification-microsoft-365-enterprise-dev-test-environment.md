---
title: 엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 데이터 분류
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
description: 이 테스트 랩 가이드를 사용 하 여 엔터프라이즈 테스트 환경용 Microsoft 365의 문서에 보존 레이블을 만들고 사용 합니다.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487735"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="24334-103">엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 데이터 분류</span><span class="sxs-lookup"><span data-stu-id="24334-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="24334-104">*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="24334-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="24334-105">이 문서에서는 엔터프라이즈 테스트 환경용 Microsoft 365의 보존 레이블을 사용 하 여 데이터 분류를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="24334-106">테스트 환경에서 데이터를 분류 하려면 다음 세 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="24334-107">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="24334-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="24334-108">2 단계: 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="24334-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="24334-109">3 단계: 문서에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="24334-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="24334-111">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="24334-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="24334-112">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="24334-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="24334-113">최소 요구 사항에 따라 간단한 방법으로 보존 레이블을 구성 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="24334-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="24334-114">시뮬레이트된 엔터프라이즈에서 보존 레이블을 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="24334-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="24334-115">테스트 보존 레이블에서는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24334-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="24334-116">자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에서 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24334-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="24334-117">2 단계: 보존 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="24334-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="24334-118">이 단계에서는 SharePoint Online 문서 폴더에 대해 서로 다른 보존 수준에 대 한 보존 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="24334-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="24334-119">전역 관리자 계정을 사용 하 여 [Microsoft 365 보안 센터](https://security.microsoft.com/homepage) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="24334-120">브라우저의 **집-Microsoft 365 보안** 탭에서 **분류**  >  **보존 레이블을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="24334-121">**레이블 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="24334-122">**레이블 이름** 지정 창에서 **레이블 이름**에 **내부 공용** 을 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="24334-123">**파일 계획 설명자** 창에서 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="24334-124">필요한 경우 **레이블 설정** 창에서 **보존** 을 **On**으로 설정 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="24334-125">**설정 검토** 창에서 **레이블 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="24334-126">아래 이름의 추가 레이블에 대해 3~7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="24334-127">개인</span><span class="sxs-lookup"><span data-stu-id="24334-127">Private</span></span>
  - <span data-ttu-id="24334-128">중요</span><span class="sxs-lookup"><span data-stu-id="24334-128">Sensitive</span></span>
  - <span data-ttu-id="24334-129">극비</span><span class="sxs-lookup"><span data-stu-id="24334-129">Highly Confidential</span></span>
1. <span data-ttu-id="24334-130">**보존 레이블** 창에서 **레이블 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="24334-131">**게시할 레이블 선택** 창에서 **게시할 레이블 선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="24334-132">**레이블 선택** 창에서 **추가** 를 선택 하 고 네 개의 레이블을 모두 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="24334-133">**추가**를 선택한 다음 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="24334-134">**게시할 레이블 선택** 창에서 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="24334-135">**위치 선택** 창에서 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="24334-136">**정책 이름** 설정 창에서 **이름**에 **예제 조직을** 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="24334-137">**설정 검토** 창에서 **레이블 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="24334-138">보존 레이블을 게시 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24334-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="24334-139">3 단계: 문서에 보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="24334-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="24334-140">이 단계에서는 SharePoint Online 사이트의 문서 폴더에 있는 파일에 대 한 기본 보존 레이블 동작을 검색 하 고 문서의 보존 레이블을 수동으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="24334-141">먼저 중요 한 수준의 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="24334-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="24334-142">브라우저의 개인 인스턴스를 사용 하 여 전역 관리자 계정을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="24334-143">타일 목록에서 **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="24334-144">브라우저의 새 **SharePoint** 탭에서 **사이트 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="24334-145">**사이트 만들기** 페이지에서 **팀 사이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="24334-146">**팀 사이트 이름** 상자에 **SensitiveFiles**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="24334-147">**팀 사이트 설명** 상자에 **중요 한 파일에 대 한 SharePoint 사이트**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="24334-148">**개인 정보 설정**에서 **비공개-구성원만이 사이트에 액세스할 수 있습니다**.를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="24334-149">**어떤 사용자를 추가** 하 시겠습니까? 창에서 **마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="24334-150">그런 다음 SensitiveFiles 팀 사이트의 문서 폴더를 구성 하 여 중요 한 보존 레이블을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="24334-151">브라우저의 **SensitiveFiles** 탭에서 **문서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="24334-152">**설정** 아이콘을 선택한 다음 **라이브러리 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="24334-153">**사용 권한 및 관리**에서 **이 목록 또는 라이브러리의 항목에 레이블 적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="24334-154">이 옵션이 표시 되지 않으면 보존 레이블이 아직 게시 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24334-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="24334-155">나중에이 단계를 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="24334-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="24334-156">**설정-레이블 적용**에서 드롭다운 상자에서 **중요** 를 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="24334-157">다음으로, SensitiveFiles 사이트에서 새 문서를 만들고 해당 보존 레이블을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="24334-158">문서 폴더에서 **새**  >  **Word 문서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="24334-159">빈 문서에 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-159">Enter some text in the blank document.</span></span> <span data-ttu-id="24334-160">텍스트가 저장 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="24334-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="24334-161">메뉴 모음에서 **공유 문서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="24334-162">**Document.docx** 파일 이름 옆에 있는 세로 줄임표 (...)를 선택 하 고 **세부 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="24334-163">오른쪽 창의 **속성** 섹션에 있는 **보존 레이블 적용**에서 문서에 **중요 한** 보존 레이블이 자동으로 적용 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="24334-164">**모두 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="24334-165">**Document.docx** 창의 **보존 레이블 적용**에서 **높은 기밀** 레이블을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24334-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="24334-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="24334-166">Next step</span></span>

<span data-ttu-id="24334-167">테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="24334-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="24334-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24334-168">See also</span></span>

[<span data-ttu-id="24334-169">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="24334-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="24334-170">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="24334-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="24334-171">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24334-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
