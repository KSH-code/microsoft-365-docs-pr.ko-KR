---
title: Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 다음 단계를 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정을 보호 합니다.
ms.openlocfilehash: 89985f99f5471aab87189e78035062add2c6bad9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673334"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a8723-103">Microsoft 365 Enterprise 테스트 환경에서 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="a8723-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a8723-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="a8723-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a8723-105">관리자 계정이 최대한 안전한 지 확인 하 여 조직에서 디지털 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="a8723-106">이 문서에서는 Azure Active Directory (Azure AD) 조건부 액세스 정책을 사용 하 여 전역 관리자 계정을 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="a8723-107">Microsoft 365 Enterprise 테스트 환경에서는 다음과 같은 두 가지 단계를 통해 전역 관리자 계정을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="a8723-108">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="a8723-109">전용 전역 관리자 계정을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-109">Protect your dedicated global administrator account.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a8723-111">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a8723-112">1 단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="a8723-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a8723-113">최소 요구 사항에 따라 간단한 방법으로 전역 관리자 계정 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a8723-114">시뮬레이트된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a8723-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="a8723-115">전역 관리자 계정 보호를 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스)에 대 한 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="a8723-116">전역 관리자 계정 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서이를 시험해 볼 수 있도록 여기에 제공 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="a8723-117">2 단계: 조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="a8723-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="a8723-118">먼저 새 사용자 계정을 전용 전역 관리자로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="a8723-119">별도의 탭에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="a8723-120">**활성 사용자**에서 **사용자 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="a8723-121">**새 사용자** 페이지에서 **이름**, **표시 이름**및 **사용자 이름**에 **DedicatedAdmin** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="a8723-122">**암호**를 클릭 하 고 **암호 만들기**를 클릭 한 다음 강력한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="a8723-123">이 새 계정의 암호를 안전한 위치에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="a8723-124">**이 사용자가 처음 로그인 할 때 암호를 변경 하도록**합니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="a8723-125">**역할**을 클릭 하 고 **전역 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="a8723-126">**제품 라이선스**를 클릭 하 고 **Enterprise Mobility + Security e5** 및 **Office 365 enterprise E5 라이선스** 를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-126">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="a8723-127">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-127">Click **Add**.</span></span>
9. <span data-ttu-id="a8723-128">**사용자 추가 됨 페이지**에서 **전자 메일로 암호 보내기를**선택 취소 하 고 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="a8723-129">그런 다음 GlobalAdmins 라는 새 그룹을 만들고 여기에 DedicatedAdmin 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="a8723-130">**Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 그룹 아이콘을 클릭 한 다음 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="a8723-131">**그룹 추가를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="a8723-132">**새 그룹** 페이지에서 **globaladmins**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="a8723-133">**소유자 선택을** 클릭 하 고 전역 관리자 계정을 클릭 한 다음 **추가 > 닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="a8723-134">그룹 목록에서 **Globaladmins** 그룹을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="a8723-135">**Globaladmins** 페이지에서 **구성원에 대해 편집**을 클릭 한 다음 **구성원 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="a8723-136">목록에서 **DedicatedAdmin** 계정을 클릭 한 다음 **저장 > 닫기를 클릭 하 > > 관리 센터를 닫습니다**.</span><span class="sxs-lookup"><span data-stu-id="a8723-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="a8723-137">그런 다음 전역 관리자 계정에 대해 다단계 인증을 요구 하 고 로그인 위험이 중간 또는 높은 경우 인증을 거부 하도록 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="a8723-138">이 첫 번째 정책에서는 모든 전역 관리자 계정에서 MFA를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="a8723-139">브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a8723-140">**Azure Active Directory > 조건부 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="a8723-141">**조건부 액세스 – 정책** 블레이드에서 **기본 정책: 관리자에 게 MFA 필요 (미리 보기)** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="a8723-142">**기본 정책 ...**</span><span class="sxs-lookup"><span data-stu-id="a8723-142">On the **Baseline policies…**</span></span> <span data-ttu-id="a8723-143">블레이드에 **정책 즉시 사용 > 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="a8723-144">이 두 번째 정책은 로그인 위험이 보통 또는 높음 인 경우 전역 관리자 계정 인증에 대 한 액세스를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="a8723-145">**조건부 액세스 – 정책** 블레이드에서 **새 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="a8723-146">**새** 블레이드에서 **이름**에 **전역 관리자** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="a8723-147">**할당** 섹션에서 **사용자 및 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="a8723-148">**사용자 및** 그룹 블레이드에서 **포함** 탭에서 사용자 및 그룹 **선택 > >** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="a8723-149">**Select** 블레이드에서 **globaladmins >** 클릭 하 여 > 완료를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="a8723-150">**배정** 섹션에서 **조건을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="a8723-151">**조건** 블레이드에서 **로그인 위험**을 클릭 하 고, **구성**에 대해 **예** 를 클릭 하 고, **높음** 및 **중간**을 차례로 클릭 한 다음 **선택** 및 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="a8723-152">**새** 블레이드의 **액세스 제어** 섹션에서 **부여**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="a8723-153">**허용** 블레이드에서 **액세스 차단을**클릭 한 다음 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="a8723-154">**새** 블레이드에서 **정책을 사용 하도록 설정을**클릭 하 고 **만들기** **를 클릭** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="a8723-155">**Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="a8723-156">첫 번째 정책을 테스트 하려면 로그 아웃 하 고 DedicatedAdmin 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="a8723-157">사용자 계정에서 MFA를 구성 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="a8723-158">이는 첫 번째 정책을 적용 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="a8723-159">프로덕션에서 전역 관리자 계정을 보호 하는 방법에 대 한 자세한 내용은 Identity 단계에서 [전역 관리자 계정 보호](identity-create-protect-global-admins.md#identity-global-admin) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8723-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a8723-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a8723-160">Next step</span></span>

<span data-ttu-id="a8723-161">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a8723-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8723-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8723-162">See also</span></span>

[<span data-ttu-id="a8723-163">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="a8723-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a8723-164">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="a8723-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a8723-165">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="a8723-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a8723-166">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="a8723-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
