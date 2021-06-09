---
title: 엔터프라이즈 테스트 환경에 대한 사용자 Microsoft 365 라이선스 및 그룹 구성원 자동화
f1.keywords:
- NOCSH
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
description: 엔터프라이즈 테스트 환경에 대한 사용자 Microsoft 365 그룹 기반 라이선싱 및 동적 그룹 구성원을 구성합니다.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905371"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e9431-103">엔터프라이즈 테스트 환경에 대한 사용자 Microsoft 365 라이선스 및 그룹 구성원 자동화</span><span class="sxs-lookup"><span data-stu-id="e9431-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e9431-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="e9431-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e9431-105">그룹 기반 라이선스는 그룹 구성원 자격에 따라 사용자 계정에 대한 라이선스를 자동으로 할당하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="e9431-106">동적 그룹 구성원은 부서 또는 국가와 같은 사용자 계정 속성에 따라 그룹에 구성원을 **추가하거나** **제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="e9431-107">이 문서에서는 엔터프라이즈 테스트 환경의 사용자 환경에서 그룹 구성원을 추가 및 제거하는 방법을 Microsoft 365 단계에 대해 단계적으로 다단계합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="e9431-108">엔터프라이즈 테스트 환경에 대한 Microsoft 365 라이선스 및 동적 그룹 구성원 자격을 설정하는 단계는 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="e9431-109">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="e9431-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e9431-110">2단계: 동적 그룹 구성원 자격 및 자동 라이선싱 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="e9431-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e9431-112">엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="e9431-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e9431-113">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="e9431-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e9431-114">최소 요구 사항과 함께 간단한 방식으로만 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하려면 [Lightweight base configuration의](lightweight-base-configuration-microsoft-365-enterprise.md)지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e9431-115">시뮬레이트된 엔터프라이즈에서 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="e9431-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9431-116">자동화된 라이선스 및 그룹 멤버 자격을 테스트하는 데는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화를 포함하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e9431-117">여기서는 옵션으로 제공되어 자동화된 라이선싱 및 그룹 멤버 자격을 테스트하고 일반적인 조직을 나타내는 환경에서 실험해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="e9431-118">2단계: 동적 그룹 구성원 자격 및 자동 라이선싱 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="e9431-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="e9431-119">먼저 Sales라는 새 그룹을 만들고, 부서가 **Sales로** 설정된 사용자  계정이 Sales 그룹에 자동으로 가입하도록 동적 그룹 구성원 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="e9431-120">인터넷 브라우저의 개인 인스턴스에서 Microsoft 365 테스트 [](https://admin.microsoft.com) 랩 구독의 전역 관리자 계정을 사용하여 Microsoft 365 E5 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="e9431-121">브라우저의 별도 탭에서 의 Azure Portal로 [https://portal.azure.com](https://portal.azure.com) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="e9431-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="e9431-122">Azure Portal에서 **검색** 상자에 그룹을 입력한 다음 그룹을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="e9431-123">모든 **그룹 창에서** 새 그룹을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="e9431-124">그룹 **유형에서 를** **선택합니다Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="e9431-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="e9431-125">그룹 **이름에** Sales 를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="e9431-126">멤버 **자격 유형에서** 동적 **사용자 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="e9431-127">동적 **사용자 구성원 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="e9431-128">동적 구성원 **규칙 창에서 다음을** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="e9431-129">부서 **속성을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-129">Select the **department** property.</span></span>
   - <span data-ttu-id="e9431-130">**같음 연산자를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="e9431-131">값 **상자에** Sales 를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="e9431-132">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-132">Select **Save**.</span></span>
11. <span data-ttu-id="e9431-133">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-133">Select **Create**.</span></span>

<span data-ttu-id="e9431-134">그런 다음 구성원에게 라이선스 라이선스가 자동으로 할당될 수 있도록 Sales Microsoft 365 E5 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="e9431-135">Sales **그룹을 선택한** 다음 라이선스 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="e9431-136">라이선스 **할당 업데이트** 창에서 를 선택하고 **Microsoft 365 E5** 를 선택한 다음 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="e9431-137">브라우저에서 Azure Portal 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="e9431-138">다음으로, 사용자 4 계정에서 동적 그룹 구성원 자격 및 자동 라이선싱을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="e9431-139">브라우저의 **Microsoft Office 홈** 탭에서 관리자 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="e9431-140">관리 **Microsoft 365 탭에서** 활성 사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="e9431-141">활성 **사용자 페이지에서** 사용자 **4 계정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="e9431-142">사용자 **4 창에서** 제품 **라이선스에** 대해 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="e9431-143">제품 라이선스 **창에서** Microsoft 365 E5 라이선스를 사용하지 않도록 설정한 다음 저장 **닫기** **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="e9431-144">사용자 4 계정의 속성에서 제품 라이선스가 할당되지 않은지와 그룹 구성원 자격이 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="e9431-145">연락처 **정보에 대해** 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="e9431-146">연락처 **정보 편집 창에서** 연락처 **정보를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="e9431-147">부서 **상자에** 판매 를 **입력하고** 저장 **닫기 를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="e9431-148">몇 분 정도 기다렸다가 사용자  4 계정 창의 오른쪽 위에 있는 새로 고침 아이콘을 주기적으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="e9431-149">시간의 경우 다음이 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-149">In time, you should see the:</span></span>

- <span data-ttu-id="e9431-150">**Group memberships** 속성이 **Sales** 그룹으로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="e9431-151">**제품 라이선스 속성이** Microsoft 365 E5 **업데이트되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="e9431-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="e9431-152">다음 문서를 참조하여 프로덕션에서 동적 그룹 구성원 자격 및 자동 라이선싱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="e9431-153">그룹의 그룹 기반 라이선싱 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e9431-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="e9431-154">그룹의 동적 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e9431-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="e9431-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e9431-155">Next step</span></span>

<span data-ttu-id="e9431-156">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e9431-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9431-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9431-157">See also</span></span>

[<span data-ttu-id="e9431-158">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="e9431-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="e9431-159">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="e9431-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e9431-160">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="e9431-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e9431-161">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="e9431-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)