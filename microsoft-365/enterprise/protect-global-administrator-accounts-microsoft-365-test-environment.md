---
title: Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호
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
description: 다음 단계를 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정을 보호 합니다.
ms.openlocfilehash: 32e5983532c89c6ada106ed32d8ef3eabd5dc569
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801393"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c197e-103">Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="c197e-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c197e-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="c197e-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c197e-105">관리자 계정이 최대한 안전한 지 확인 하 여 조직에서 디지털 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="c197e-106">이 문서에서는 Azure Active Directory (Azure AD) 조건부 액세스 정책을 사용 하 여 전역 관리자 계정을 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="c197e-107">Microsoft 365 Enterprise 테스트 환경에서는 다음과 같은 두 가지 단계를 통해 전역 관리자 계정을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="c197e-108">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="c197e-109">전용 전역 관리자 계정을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-109">Protect your dedicated global administrator account.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c197e-111">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c197e-112">1단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="c197e-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c197e-113">최소 요구 사항에 따라 간단한 방법으로 전역 관리자 계정 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c197e-114">시뮬레이트된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c197e-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c197e-115">전역 관리자 계정 보호를 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스)에 대 한 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="c197e-116">전역 관리자 계정 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서이를 시험해 볼 수 있도록 여기에 제공 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="c197e-117">2 단계: 조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="c197e-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="c197e-118">먼저 새 사용자 계정을 전용 전역 관리자로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="c197e-119">별도의 탭에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="c197e-120">**활성 사용자 >** 사용자를 클릭 한 다음 **사용자 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="c197e-121">**사용자 추가** 창에서 **이름**, **표시 이름**및 **사용자 이름**에 **DedicatedAdmin** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="c197e-122">**암호**를 클릭 하 고 **암호 만들기**를 클릭 한 다음 강력한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="c197e-123">이 새 계정의 암호를 안전한 위치에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="c197e-124">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-124">Click **Next**.</span></span>
6. <span data-ttu-id="c197e-125">**제품 라이선스 할당** 창에서 **Microsoft 365 e5** 또는 **Office 365 E5**를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="c197e-126">**선택적 설정** 창에서 **역할**을 클릭 한 다음 **관리 센터 액세스** 및 **전역 관리자**를 선택 합니다. **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="c197e-127">**거의 완료** 된 창에서 **추가 완료**를 클릭 한 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="c197e-128">그런 다음 GlobalAdmins 라는 새 그룹을 만들고 여기에 DedicatedAdmin 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="c197e-129">**Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 **그룹** 을 클릭 하 고 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="c197e-130">**그룹 추가를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="c197e-131">**그룹 유형 선택** 창에서 **보안**을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="c197e-132">**기본 설정** 창에서 **그룹 만들기**를 클릭 한 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="c197e-133">**검토 및 그룹 추가 완료** 창에서 **globaladmins**를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="c197e-134">그룹 목록에서 **Globaladmins** 그룹을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="c197e-135">**Globaladmins** 창에서 **구성원**을 클릭 하 고 **모두 보기 및 구성원 관리를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="c197e-136">**Globaladmins** 창에서 **구성원 추가**를 클릭 하 고 **DedicatedAdmin** 계정 및 전역 관리자 계정을 선택한 다음 **저장 > 닫기 >** 닫기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="c197e-137">그런 다음 전역 관리자 계정에 대해 다단계 인증을 요구 하 고 로그인 위험이 중간 또는 높은 경우 인증을 거부 하도록 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="c197e-138">이 첫 번째 정책에서는 모든 전역 관리자 계정에서 MFA를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="c197e-139">브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="c197e-140">**Azure Active Directory > 보안 > 조건부 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="c197e-141">**조건부 액세스 – 정책** 창에서 **기본 정책: 관리자에 게 MFA 필요 (미리 보기)** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="c197e-142">**기본 정책** 창에서 **정책 즉시 사용 > 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="c197e-143">이 두 번째 정책은 로그인 위험이 보통 또는 높음 인 경우 전역 관리자 계정 인증에 대 한 액세스를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="c197e-144">**조건부 액세스 – 정책** 창에서 **새 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="c197e-145">**새로 만들기** 창에서 **이름**에 **전역 관리자** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="c197e-146">**할당** 섹션에서 **사용자 및 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="c197e-147">**사용자 및 그룹** 창의 **포함** 탭에서 사용자 및 그룹 **선택 > >** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="c197e-148">**선택** 창에서 **globaladmins** 그룹을 클릭 한 다음 **완료 > 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="c197e-149">**배정** 섹션에서 **조건을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="c197e-150">**조건** 창에서 **로그인 위험**을 클릭 하 고 **구성**에 대해 **예** 를 클릭 한 다음 **높음** 및 **중간**을 클릭 하 고 **선택** 및 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="c197e-151">**새** 창의 **액세스 제어** 섹션에서 **부여**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="c197e-152">**부여** 창에서 **액세스 차단**, **선택을**차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="c197e-153">**새로 만들기** 창에서 **정책 사용** **을 클릭 하** 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="c197e-154">**Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="c197e-155">첫 번째 정책을 테스트 하려면 로그 아웃 하 고 DedicatedAdmin 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="c197e-156">MFA를 구성 하 라는 메시지가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="c197e-157">이는 첫 번째 정책을 적용 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="c197e-158">프로덕션에서 전역 관리자 계정을 보호 하는 방법에 대 한 자세한 내용은 Identity 단계에서 [전역 관리자 계정 보호](identity-create-protect-global-admins.md#identity-global-admin) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c197e-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="c197e-159">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c197e-159">Next step</span></span>

<span data-ttu-id="c197e-160">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c197e-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c197e-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c197e-161">See also</span></span>

[<span data-ttu-id="c197e-162">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="c197e-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="c197e-163">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="c197e-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c197e-164">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="c197e-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c197e-165">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="c197e-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
