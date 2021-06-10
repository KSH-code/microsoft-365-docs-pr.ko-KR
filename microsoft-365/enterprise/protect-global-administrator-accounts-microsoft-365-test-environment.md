---
title: 엔터프라이즈 테스트 환경에 Microsoft 365 전역 관리자 계정 보호
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
description: 다음 단계에 따라 엔터프라이즈 테스트 환경에 대한 Microsoft 365 전역 관리자 계정을 보호합니다.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918885"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="20a94-103">엔터프라이즈 테스트 환경에 Microsoft 365 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="20a94-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="20a94-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="20a94-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="20a94-105">관리자 계정이 최대한 안전하게 유지될 수 있도록 하여 조직에 대한 디지털 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="20a94-106">이 문서에서는 Azure AD(Azure Active Directory 조건부 액세스 정책을 사용하여 전역 관리자 계정을 보호하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="20a94-107">엔터프라이즈 테스트 환경에 대한 Microsoft 365 전역 관리자 계정을 보호하는 데는 다음 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="20a94-108">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="20a94-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="20a94-109">2단계: 조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="20a94-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="20a94-111">엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="20a94-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="20a94-112">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="20a94-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="20a94-113">최소 요구 사항과 경량 방식으로 전역 관리자 계정 보호를 테스트하려면 Lightweight [base configuration의 지침을 따릅니다.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="20a94-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="20a94-114">시뮬레이트된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트하려면 [통과 인증의 지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="20a94-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="20a94-115">전역 관리자 계정 보호를 테스트할 때에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스)에 대한 디렉터리 동기화를 포함하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="20a94-116">전역 관리자 계정 보호를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 여기에 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="20a94-117">2단계: 조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="20a94-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="20a94-118">먼저 새 사용자 계정을 전용 전역 관리자로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="20a94-119">별도 탭에서 관리 Microsoft 365 [를 를 니다.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="20a94-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="20a94-120">사용자 **활성 사용자를**  >  **선택한** 다음 사용자 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="20a94-121">사용자 **추가 창의** **이름,** 표시 이름 및 사용자 이름 상자에 **DedicatedAdmin을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="20a94-122">암호를 **선택하고** **암호** 만들기를 선택한 다음 강력한 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="20a94-123">이 새 계정의 암호를 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="20a94-124">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-124">Select **Next**.</span></span>
6. <span data-ttu-id="20a94-125">제품 **라이선스 할당** 창에서 Microsoft 365 E5 를 선택하고 다음 **을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="20a94-126">선택적 **설정 창에서** 역할 **관리** 센터  >  **액세스 전역**  >  **관리자 다음 을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="20a94-127">**You're almost done(거의 완료)** 창에서 Finish adding (을) **선택하고** Close(닫기)를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="20a94-128">그런 다음 GlobalAdmins라는 새 그룹을 만들고 DedicatedAdmin 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="20a94-129">관리 **Microsoft 365 탭의** 왼쪽 탐색  창에서 그룹을 선택한 다음 그룹을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="20a94-130">그룹 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="20a94-131">그룹 **유형 선택 창에서** 보안 을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="20a94-132">기본 **설정** 창에서 그룹 만들기를 선택한 다음 닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="20a94-133">검토 및 그룹 **추가 완료 창에서** **GlobalAdmins** 를 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="20a94-134">그룹 목록에서 **GlobalAdmins 그룹을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="20a94-135">**GlobalAdmins 창에서** 구성원 을 선택한 다음 모두 보기 및 구성원 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="20a94-136">**GlobalAdmins** 창에서 구성원 **추가를** 선택하고 **DedicatedAdmin** 계정 및 전역 관리자 계정을 선택한 다음 저장   >  **닫기 닫기 를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="20a94-137">다음으로, 전역 관리자 계정에 대해 다단계 인증을 요구하고 로그인 위험이 중간 또는 높음인 경우 인증을 거부하는 조건부 액세스 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="20a94-138">이 첫 번째 정책을 사용하려면 모든 전역 관리자 계정이 MFA를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="20a94-139">브라우저의 새 탭에서 로 [https://portal.azure.com](https://portal.azure.com) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="20a94-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="20a94-140">보안 **Azure Active Directory**  >    >  **액세스 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="20a94-141">조건부 **액세스 - 정책** 창에서 기준 **정책: 관리자에 대해 MFA 필요(미리 보기)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="20a94-142">기본 정책 **창에서** 저장 즉시 정책 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="20a94-143">이 두 번째 정책은 로그인 위험이 중간 또는 높음일 때 전역 관리자 계정 인증에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="20a94-144">조건부 **액세스 - 정책** 창에서 새 정책을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="20a94-145">새 **창의** 이름에 **전역 관리자를** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="20a94-146">할당 **섹션에서** 사용자 및 **그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="20a94-147">사용자 **및** 그룹 포함 창의 포함 **탭에서** 사용자 및 그룹 사용자 및 **그룹**  >  **선택 을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="20a94-148">선택 **창에서** **GlobalAdmins** 그룹을 선택한 다음 완료 **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="20a94-149">배정 **섹션에서** 조건을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="20a94-150">조건 **창에서** 로그인 위험 을 선택하고 구성에 대해  **예를** 선택하고 높음 및 보통을 선택한 다음 선택 **및** 완료를 **선택합니다.**   </span><span class="sxs-lookup"><span data-stu-id="20a94-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="20a94-151">새 **창의 액세스** 제어 **섹션에서** 부여를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="20a94-152">부여 **창에서** 액세스 차단을 **선택하고** 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="20a94-153">새로 만들기 **창에서** 정책 사용에 **대해** **을** 선택하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="20a94-154">Azure **Portal을** 닫고 관리 **Microsoft 365 탭을 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="20a94-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="20a94-155">첫 번째 정책을 테스트하려면 전용Admin 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="20a94-156">MFA를 구성하라는 메시지가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="20a94-157">이는 첫 번째 정책이 적용되고 있는 것을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="20a94-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="20a94-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="20a94-158">Next step</span></span>

<span data-ttu-id="20a94-159">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20a94-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="20a94-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20a94-160">See also</span></span>

[<span data-ttu-id="20a94-161">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="20a94-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="20a94-162">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="20a94-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="20a94-163">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="20a94-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="20a94-164">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="20a94-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)