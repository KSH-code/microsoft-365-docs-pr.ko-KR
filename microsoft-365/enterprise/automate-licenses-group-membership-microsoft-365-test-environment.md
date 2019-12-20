---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 라이선싱 및 그룹 구성원을 자동화 합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 Enterprise 테스트 환경에서 그룹 기반 라이선싱 및 동적 그룹 구성원을 구성 합니다.
ms.openlocfilehash: facff7eb556299c0312fa7488a35a96151bb1882
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802123"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="53710-103">Microsoft 365 Enterprise 테스트 환경에 대 한 라이선싱 및 그룹 구성원을 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="53710-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="53710-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="53710-105">그룹 기반 라이선스는 그룹 구성원을 기반으로 사용자 계정에 대 한 라이선스를 자동으로 할당 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="53710-106">동적 그룹 구성원 자격은 사용자 계정 속성 (예: 부서 또는 국가)을 기반으로 그룹에 구성원을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="53710-107">이 문서에서는 Microsoft 365 Enterprise 테스트 환경 모두에 대 한 데모를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="53710-108">Microsoft 365 Enterprise 테스트 환경에서 자동 라이선싱 및 동적 그룹 멤버 자격을 설정 하는 두 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53710-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="53710-109">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53710-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="53710-110">동적 그룹 구성원 자격 및 자동 라이선스를 구성 하 고 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="53710-112">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53710-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="53710-113">1단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="53710-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="53710-114">최소 요구 사항에 따라 간단한 방법으로 자동 라이선싱 및 그룹 구성원을 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="53710-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="53710-115">시뮬레이트된 엔터프라이즈에서 자동화 된 라이선싱 및 그룹 구성원을 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="53710-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="53710-116">자동 라이선싱 및 그룹 구성원을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53710-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="53710-117">이 기능은 자동 라이선스 및 그룹 구성원을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53710-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="53710-118">2 단계: 동적 그룹 구성원 자격 및 자동 라이선스 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="53710-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="53710-119">먼저 새 Sales 그룹을 만들고 부서가 Sales로 설정 된 사용자 계정이 Sales 그룹에 자동으로 추가 되도록 동적 그룹 구성원 규칙을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="53710-120">인터넷 브라우저의 개인 인스턴스를 사용 하 여 Microsoft 365 E5 테스트 랩 구독의 전역 관리자 [https://portal.office.com](https://portal.office.com) 계정으로 Office 365 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="53710-121">브라우저의 별도 탭에서 Azure portal ()로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="53710-122">Azure portal에서 검색 상자에 **그룹** 을 입력 하 고 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="53710-123">**모든 그룹** 창에서 **새 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="53710-124">**그룹 유형에**서 **Office 365**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="53710-125">**그룹 이름**에 **Sales**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="53710-126">**멤버 자격 유형에**서 **동적 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="53710-127">**동적 사용자 구성원**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="53710-128">**동적 멤버 자격 규칙** 창에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="53710-129">**부서** 속성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-129">Select the **department** property.</span></span>
   - <span data-ttu-id="53710-130">**같음** 연산자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="53710-131">**값**에 **Sales** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="53710-132">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-132">Click **Save**.</span></span>
11. <span data-ttu-id="53710-133">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-133">Click **Create**.</span></span>

<span data-ttu-id="53710-134">다음으로, 구성원에 게 Microsoft 365 E5 라이선스가 자동으로 할당 되도록 Sales 그룹을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="53710-135">**Sales** 그룹을 클릭 한 다음 **라이선스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="53710-136">**라이선스 할당 업데이트** 창에서 **Microsoft 365 E5**를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="53710-137">브라우저에서 Azure Portal 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="53710-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="53710-138">다음으로, 사용자 4 계정에서 동적 그룹 구성원 자격 및 자동 라이선싱을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="53710-139">브라우저의 **Microsoft Office 홈** 탭에서 **관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="53710-140">**Microsoft 365 관리 센터** 탭에서 **활성 사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="53710-141">**활성 사용자** 페이지에서 **사용자 4** 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="53710-142">**사용자 4** 창에서 **제품 라이선스**에 대 한 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="53710-143">**제품 라이선스** 창에서 **Microsoft 365 E5** 라이선스를 사용 하지 않도록 설정 하 고 **닫기 > 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="53710-144">사용자 4 계정의 속성에서 제품 라이선스가 할당 되어 있지 않으며 그룹 구성원 자격이 없음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="53710-145">**연락처 정보**에 대해 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="53710-146">**연락처 정보 편집** 창에서 **연락처 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="53710-147">**부서** 필드에 **Sales**를 입력 하 고 **닫기를 > 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="53710-148">몇 분 정도 기다린 다음 사용자 4 계정 창의 오른쪽 위에 있는 새로 고침 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53710-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="53710-149">다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53710-149">In time you should see the:</span></span>

- <span data-ttu-id="53710-150">**Sales** 그룹으로 업데이트 된 **그룹 멤버 자격** 속성</span><span class="sxs-lookup"><span data-stu-id="53710-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="53710-151">**Microsoft 365 E5** 라이선스로 **제품 라이선스** 속성을 업데이트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53710-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="53710-152">프로덕션 환경에서 동적 그룹 구성원 자격 및 자동 라이선싱을 배포 하는 방법에 대 한 자세한 내용과 링크는 Identity 단계에서 다음 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53710-152">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="53710-153">자동 라이선싱 설정</span><span class="sxs-lookup"><span data-stu-id="53710-153">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="53710-154">동적 그룹 구성원 설정</span><span class="sxs-lookup"><span data-stu-id="53710-154">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="53710-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="53710-155">Next step</span></span>

<span data-ttu-id="53710-156">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="53710-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="53710-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53710-157">See also</span></span>

[<span data-ttu-id="53710-158">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="53710-158">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="53710-159">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="53710-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="53710-160">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="53710-160">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="53710-161">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="53710-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
