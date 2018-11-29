---
title: Microsoft 365 기업 테스트 환경에 대 한 라이선스 및 그룹 구성원 자격을 자동화 합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 기업 테스트 환경에서 라이선스 그룹 기반 및 동적 그룹 구성원 자격을 구성 합니다.
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870107"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4a250-103">Microsoft 365 기업 테스트 환경에 대 한 라이선스 및 그룹 구성원 자격을 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4a250-p101">자동으로 라이선스 그룹 기반 할당 하거나 그룹 구성원 자격을 기준으로 사용자 계정에 대 한 라이선스를 제거 합니다. 동적 그룹 구성원 자격을 추가 또는 부서 또는 국가/지역 등의 사용자 계정 속성을 기준으로 그룹에 구성원을 제거 합니다. 이 문서에서는 Microsoft 365 기업 테스트 환경에서 모두의 데모를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="4a250-107">Microsoft 365 기업 테스트 환경에서 자동 라이선스 및 동적 그룹 구성원 자격을 설정 하는 두 단계로 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="4a250-108">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="4a250-109">구성 하 고 동적 그룹 멤버 자격 및 자동 라이선스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4a250-111">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4a250-112">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="4a250-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4a250-113">최소 요구 사항을 경량 방식으로 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4a250-114">시뮬레이션 된 엔터프라이즈에서 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a250-p102">라이선스 하는 자동화 된 테스트 하 고 그룹 멤버 자격을 원하지 않는 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공는 자동화 된 라이선스 및 그룹 구성원 자격을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="4a250-117">2 단계: 구성 및 테스트 동적 그룹 멤버 자격 및 자동 라이선스</span><span class="sxs-lookup"><span data-stu-id="4a250-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="4a250-118">첫째, 새 Sales 그룹을 만들고 Sales 그룹에 사용자 계정을 매출으로 설정 하는 부서와 함께 자동으로 추가 되도록 동적 그룹 멤버 자격 규칙을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="4a250-119">Office 365 포털에 로그인 인터넷 브라우저의 전용 인스턴스를 사용 하 여 [https://portal.office.com](https://portal.office.com) Office 365 E5 평가판 구독의 전역 관리자 계정을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="4a250-120">브라우저의 개별 탭에 있는 포털로 이동 하 여 Azure에서 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="4a250-121">Azure Portal에서 **Azure Active Directory > 사용자 및 그룹 > 모든 그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="4a250-122">**모든 그룹** 블레이드에서 **새 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="4a250-123">**그룹 종류** **Office 365**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="4a250-124">**그룹 이름** **판매**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="4a250-125">**멤버 자격 형식** **동적 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="4a250-126">**동적 쿼리 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="4a250-127">**사용자를 추가할 위치**에서 **부서**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="4a250-128">다음 필드에서 **같음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="4a250-129">다음 필드에서 **Sales**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="4a250-130">**쿼리 추가**를 클릭한 다음, **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="4a250-131">**그룹** 및 **그룹 모든 그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="4a250-132">다음으로, Office 365 e 5 및 Enterprise 이동성 + 보안 E5 라이선스 구성원은 자동으로 할당 되도록 Sales 그룹을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="4a250-133">Azure Active Directory에 대 한 **개요** 블레이드, 클릭 **라이선스 > 모든 제품**합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="4a250-134">목록에서 **Enterprise Mobility + Security E5** 및 **Office 365 Enterprise E5**를 선택하고 **할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="4a250-135">**라이선스를 할당** 블레이드 **사용자 및 그룹을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="4a250-136">그룹 목록에서 **Sales** 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="4a250-137">**선택**을 클릭하고 **할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="4a250-138">브라우저에서 Azure Portal 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="4a250-139">다음으로, 동적 그룹 멤버 자격 및 사용자 4 계정에 자동 라이선스 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="4a250-140">브라우저에서 **Microsoft Office 홈** 탭에서 **관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="4a250-141">**Office 관리 센터** 탭에서 **활성 사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="4a250-142">**현재 사용자** 페이지에서 **사용자 4** 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="4a250-143">**사용자 4** 창에서 **제품 라이선스**에 대 한 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="4a250-144">**제품 라이선스** 창에는 **엔터프라이즈 이동성 + 보안 e 5를** 설정 하 고 **Office 365 Enterprise e 5** 라이선스를 해제 하 고 다음을 클릭 **저장 > 닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="4a250-145">4 사용자 계정 속성에 없는 제품 라이선스를 할당 하 고는 없는 그룹 구성원 자격을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="4a250-146">**연락처 정보**에 대 한 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="4a250-147">**연락처 편집 정보** 창에서 **연락처 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="4a250-148">**부서** 필드에서 **Sales**를 입력 하 고 클릭 **저장 > 닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="4a250-149">몇분 기다린 다음 업그레이드를 주기적으로 사용자 4 계정 창의 오른쪽 위에서에서 새로고침 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="4a250-150">시간에 표시 되어야는:</span><span class="sxs-lookup"><span data-stu-id="4a250-150">In time you should see the:</span></span>

- <span data-ttu-id="4a250-151">**그룹 구성원 자격** 속성 **Sales** 그룹을 사용 하 여 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="4a250-152">**제품 라이선스** 속성 **Enterprise 이동성 + 보안 e 5** 및 **Office 365 Enterprise E5** 라이선스를 사용 하 여 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="4a250-153">정보 및 동적 그룹 멤버 자격 및 프로덕션 환경에서 자동 라이선스 배포에 대 한 링크에 대 한 Identity 단계에서 다음이 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a250-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="4a250-154">자동 라이선싱 설정</span><span class="sxs-lookup"><span data-stu-id="4a250-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="4a250-155">동적 그룹 구성원 설정</span><span class="sxs-lookup"><span data-stu-id="4a250-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="4a250-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4a250-156">Next step</span></span>

<span data-ttu-id="4a250-157">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4a250-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a250-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a250-158">See also</span></span>

[<span data-ttu-id="4a250-159">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="4a250-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="4a250-160">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="4a250-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4a250-161">Microsoft 365 엔터프라이즈 배포</span><span class="sxs-lookup"><span data-stu-id="4a250-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4a250-162">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="4a250-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
