---
title: 엔터프라이즈 테스트 환경용 Microsoft 365의 전역 관리자 계정 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 다음 단계를 사용 하 여 엔터프라이즈 테스트 환경용 Microsoft 365의 전역 관리자 계정을 보호 합니다.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487639"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="802f8-103">엔터프라이즈 테스트 환경용 Microsoft 365의 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="802f8-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="802f8-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="802f8-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="802f8-105">관리자 계정이 최대한 안전한 지 확인 하 여 조직에서 디지털 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="802f8-106">이 문서에서는 Azure Active Directory (Azure AD) 조건부 액세스 정책을 사용 하 여 전역 관리자 계정을 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="802f8-107">엔터프라이즈 테스트 환경용 Microsoft 365에서 전역 관리자 계정 보호에는 다음 두 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="802f8-108">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="802f8-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="802f8-109">2 단계: 조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="802f8-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="802f8-111">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="802f8-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="802f8-112">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="802f8-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="802f8-113">최소 요구 사항에 따라 간단한 방식으로 전역 관리자 계정 보호를 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="802f8-114">시뮬레이트된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="802f8-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="802f8-115">전역 관리자 계정 보호를 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스)에 대 한 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="802f8-116">전역 관리자 계정 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서이를 시험해 볼 수 있도록 여기에 제공 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="802f8-117">2 단계: 조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="802f8-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="802f8-118">먼저 새 사용자 계정을 전용 전역 관리자로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="802f8-119">별도의 탭에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="802f8-120">**사용자**  >  **활성 사용자**를 선택한 다음 **사용자 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="802f8-121">**사용자 추가** 창의 **이름**, **표시 이름**및 **사용자 이름** 상자에 **DedicatedAdmin** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="802f8-122">**암호**를 선택 하 고 **암호 만들기**를 선택한 다음 강력한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="802f8-123">이 새 계정의 암호를 안전한 위치에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="802f8-124">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-124">Select **Next**.</span></span>
6. <span data-ttu-id="802f8-125">**제품 라이선스 할당** 창에서 **Microsoft 365 E5**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="802f8-126">**선택적 설정** 창에서 **역할**  >  **관리 센터 액세스**  >  **전역 관리자**  >  **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="802f8-127">**거의 완료** 된 창에서 **추가 완료**를 선택 하 고 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="802f8-128">그런 다음 GlobalAdmins 라는 새 그룹을 만들고 여기에 DedicatedAdmin 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="802f8-129">**Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 **그룹** 을 선택 하 고 **그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="802f8-130">**그룹 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="802f8-131">**그룹 유형 선택** 창에서 **보안**을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="802f8-132">**기본 설정** 창에서 **그룹 만들기**를 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="802f8-133">**검토 및 그룹 추가 완료** 창에서 **globaladmins**를 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="802f8-134">그룹 목록에서 **Globaladmins** 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="802f8-135">**Globaladmins** 창에서 **구성원**을 선택 하 고 **모두 보기 및 구성원 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="802f8-136">**Globaladmins** 창에서 **구성원 추가**를 선택 하 고 **DedicatedAdmin** 계정 및 전역 관리자 계정을 선택한 다음 닫기/닫기 **저장**을 선택  >  **Close**  >  **Close**합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="802f8-137">그런 다음 전역 관리자 계정에 대 한 다단계 인증을 요구 하 고 로그인 위험이 중간 또는 높은 경우 인증을 거부 하도록 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="802f8-138">이 첫 번째 정책에서는 모든 전역 관리자 계정에서 MFA를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="802f8-139">브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="802f8-140">**Azure Active Directory**  >  **보안**  >  **조건부 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="802f8-141">**조건부 액세스 – 정책** 창에서 **기본 정책: 관리자에 게 MFA 필요 (미리 보기)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="802f8-142">**기본 정책** 창에서 **정책 즉시 사용 > 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="802f8-143">이 두 번째 정책은 로그인 위험이 보통 또는 높음 인 경우 전역 관리자 계정 인증에 대 한 액세스를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="802f8-144">**조건부 액세스 – 정책** 창에서 **새 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="802f8-145">**새로 만들기** 창에서 **이름**에 **전역 관리자** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="802f8-146">**할당** 섹션에서 **사용자 및 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="802f8-147">**사용자 및 그룹** 창의 **포함** 탭에서 사용자 및 그룹 **선택**  >  **사용자 및 그룹**을 선택  >  합니다.**를 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="802f8-148">**선택** 창에서 **globaladmins** 그룹을 선택한 다음 **Select**  >  **완료**선택을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="802f8-149">**배정** 섹션에서 **조건을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="802f8-150">**조건** 창에서 **로그인 위험**을 선택 하 고, **구성**에 대해 **예** 를 선택 하 고, **높음** 및 **중간**을 선택한 다음 **선택** 및 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="802f8-151">**새** 창의 **액세스 제어** 섹션에서 **부여**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="802f8-152">**부여** 창에서 **액세스 차단**, **선택을**차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="802f8-153">**새로 만들기** 창에서 **정책 사용** **에 대해 설정을** 선택 하 고 **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="802f8-154">**Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="802f8-155">첫 번째 정책을 테스트 하려면 로그 아웃 하 고 DedicatedAdmin 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="802f8-156">MFA를 구성 하 라는 메시지가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="802f8-157">이는 첫 번째 정책을 적용 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="802f8-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="802f8-158">Next step</span></span>

<span data-ttu-id="802f8-159">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="802f8-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="802f8-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="802f8-160">See also</span></span>

[<span data-ttu-id="802f8-161">Id 로드맵</span><span class="sxs-lookup"><span data-stu-id="802f8-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="802f8-162">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="802f8-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="802f8-163">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="802f8-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="802f8-164">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="802f8-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
