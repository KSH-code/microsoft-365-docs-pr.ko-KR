---
title: 전역 관리자 계정을 Microsoft 365 기업 테스트 환경에서 보호
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
description: Microsoft 365 기업 테스트 환경에서 전역 관리자 계정을 보호 하기 위해 다음이 단계를 사용 합니다.
ms.openlocfilehash: 4d444e217c5a232811701f6519c2eb3ebe86df70
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869742"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bbe48-103">전역 관리자 계정을 Microsoft 365 기업 테스트 환경에서 보호</span><span class="sxs-lookup"><span data-stu-id="bbe48-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bbe48-p101">관리자 계정 보안을 최대한 확인 하 여 조직에 대 한 디지털 공격을 방지할 수 있습니다. 이 문서에서는 전역 관리자 계정을 보호 하기 위해 Office 365 클라우드 응용 프로그램 보안 및 Azure AD 조건부 액세스 정책을 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="bbe48-106">전역 관리자 계정을 Microsoft 365 기업 테스트 환경에서 보호 하는 두 단계로 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="bbe48-107">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="bbe48-108">전용된 전역 관리자 계정을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-108">Protect your dedicated global administrator account.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="bbe48-110">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bbe48-111">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="bbe48-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bbe48-112">최소 요구 사항을 경량 방식으로 전역 관리자 계정 보호를 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="bbe48-113">시뮬레이션 된 엔터프라이즈에서 전역 관리자 계정 보호를 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe48-p102">인터넷에 연결 된 전역 관리자 계정 보호 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 필요 하지 않은 테스트 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공은 전역 관리자 계정 보호를 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="bbe48-116">2 단계: 클라우드 응용 프로그램 보안 및 조건부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="bbe48-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="bbe48-117">먼저, 전역 관리자 계정 활동을 모니터링 하 고 전역 관리자 계정의 전자 메일 주소로 경고를 보내도록 하는 Office 365 클라우드 응용 프로그램 보안 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="bbe48-118">Office 포털에 로그인 [http://portal.office.com](http://portal.office.com) 전역 관리자 계정을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-118">Sign in to the Office portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="bbe48-p103">**Admin** 타일을 클릭 합니다. **Office 관리 센터** 탭을 클릭 **관리 센터 > 보안 및 규정 준수**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="bbe48-121">왼쪽된 탐색 창의 클릭 **알림 > 고급 알림 관리**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="bbe48-122">**고급 알림 관리** 페이지에서 **Office 365 클라우드 응용 프로그램 보안 설정**를 클릭 한 다음 **Office 365 클라우드 응용 프로그램 보안으로 이동**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="bbe48-123">새 **대시보드** 탭을 클릭 **제어 > 정책**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="bbe48-124">**정책** 페이지에서 **정책 만들기**클릭 한 다음 **활동 정책**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="bbe48-125">**정책 이름** **관리 작업**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="bbe48-126">**정책 심각도**에서 **높음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="bbe48-127">**범주** **권한이 부여 된 계정**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="bbe48-128">**정책에 대 한 만들기 필터**에 **일치 하는 다음의 모든 활동**을에서 **관리 작업**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="bbe48-p104">**경고**에서 **전자 메일로 경고 보내기**를 클릭합니다. **받는 사람**에서 전역 관리자 계정의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="bbe48-131">페이지 하단에서 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="bbe48-132">**대시보드** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="bbe48-133">다음으로 전용된 전역 관리자 권한으로 새 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="bbe48-134">**Office 관리 센터** 탭에서 **현재 사용자** **사용자 추가**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="bbe48-135">**새 사용자** 페이지에서 **성**, **표시 이름**및 **사용자 이름**에 **DedicatedAdmin** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="bbe48-p105">**암호**를클릭하고 **나에 게 암호를 만들 수 있도록**를 클릭 한 다음 강력한 암호를 입력 합니다. 안전한 위치에 새이 계정의 암호를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="bbe48-138">**처음 로그인 할 때 자신의 암호를 변경 하는이 사용자를 확인 합니다.** 의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="bbe48-139">**역할**클릭 하 고 **전역 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="bbe48-140">**제품 라이선스**클릭 하 고 **엔터프라이즈 이동성 + 보안 e 5** 및 **Office 365 Enterprise E5 라이선스** 를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="bbe48-141">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-141">Click **Add**.</span></span>
8. <span data-ttu-id="bbe48-142">**사용자가 페이지를 추가**에서 **보내는 전자 메일에 암호를**지우고 **닫기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="bbe48-143">다음으로, GlobalAdmins 이라는 새 그룹을 만들고 DedicatedAdmin 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="bbe48-144">**Office 관리 센터** 탭의 왼쪽된 탐색 영역에서 그룹 아이콘을 클릭 하 고 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="bbe48-145">**그룹 추가**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="bbe48-146">**새 그룹** 페이지에서 **GlobalAdmins**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="bbe48-147">전역 관리자 계정을 **선택 소유자** 클릭을 클릭 하 고 다음을 클릭 **추가 > 닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="bbe48-148">그룹 목록에서 **GlobalAdmins** 그룹을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="bbe48-149">**GlobalAdmins** 페이지에서 **구성원에 대 한 편집**을 클릭 하 고 **구성원 추가**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="bbe48-150">목록에서 **DedicatedAdmin** 계정을 클릭 하 고 다음을 클릭 **저장 > 닫기 > 닫기 > 관리 센터**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="bbe48-151">다음으로, 전역 관리자 계정에 대 한 다단계 인증을 요구 하도록 하 고 로그인 위험 중간 또는 높은 경우 인증을 거부 하려면 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="bbe48-152">이 첫번째 정책 MFA 모든 전역 관리자 계정을 사용 하 여는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="bbe48-153">브라우저의 새 탭에서로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="bbe48-154">클릭 **Azure Active Directory > 조건부 액세스**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="bbe48-155">**조건부 액세스-정책** 블레이드 클릭 **기본 정책: admins (미리 보기)에 대 한 필요 MFA**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="bbe48-p106">**초기 계획 정책...** 블레이드 클릭 **즉시 정책을 사용 하 여 > 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="bbe48-158">이 두번째 정책 블록에 대 한 액세스 로그인 위험 중간 규모 또는 높은 경우 전역 관리자 계정 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="bbe48-159">**조건부 액세스-정책** 블레이드 **새 정책**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="bbe48-160">**새로운** 블레이드 **전역 관리자** **이름**에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="bbe48-161">**배정** 섹션에서 **사용자 및 그룹을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="bbe48-162">**사용자 및 그룹** 블레이드 **포함** 탭에서 클릭 **사용자 및 그룹 선택 > 사용자 및 그룹 > 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="bbe48-163">**선택** 블레이드 클릭은 **GlobalAdmins > 선택 > 완료**합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="bbe48-164">**배정** 섹션에서 **조건**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="bbe48-165">**조건** 블레이드에서 **로그인 위험**을 클릭, **구성**에 대 한 **예** 를 클릭 합니다., **높음** 및 **중간**규모를 클릭 하 고 **을 선택** 하 고 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="bbe48-166">**새로운** 블레이드의 **액세스 제어** 섹션에서 **권한 부여**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="bbe48-167">**부여** 블레이드에서 **블록 액세스**클릭 한 다음 **선택**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="bbe48-168">**새로운** 블레이드 **정책을 사용 하도록 설정**하는 것에 대 한 **에서** 클릭 하 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="bbe48-169">**Azure 포털** 및 **Office 관리 센터** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="bbe48-p107">첫번째 정책을 테스트 하려면 로그 아웃 하 고 DedicatedAdmin 계정을 사용 하 여 로그인 합니다. MFA 사용자 계정을 구성 하 라는 메시지가 나타납니다. 이 첫번째 정책이 적용 되는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="bbe48-173">정보 및 프로덕션 환경에서 전역 관리자 계정을 보호 하기 위해 링크에 대 한 Identity 단계에서 [암호로 보호 전역 관리자 계정](identity-designate-protect-admin-accounts.md) 단계를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="bbe48-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bbe48-174">Next step</span></span>

<span data-ttu-id="bbe48-175">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bbe48-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbe48-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbe48-176">See also</span></span>

[<span data-ttu-id="bbe48-177">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="bbe48-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="bbe48-178">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="bbe48-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="bbe48-179">Microsoft 365 엔터프라이즈 배포</span><span class="sxs-lookup"><span data-stu-id="bbe48-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bbe48-180">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="bbe48-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
