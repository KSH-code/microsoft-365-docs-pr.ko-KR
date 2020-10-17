---
title: 엔터프라이즈 테스트 환경에 대 한 Microsoft 365 (multi-factor authentication)
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
- seo-marvel-apr2020
description: 엔터프라이즈 테스트 환경용 Microsoft 365에서 스마트 전화로 전송 되는 텍스트 메시지를 사용 하 여 다단계 인증을 구성 합니다.
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487143"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="95f3d-103">엔터프라이즈 테스트 환경용 Microsoft 365에 대 한 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="95f3d-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="95f3d-104">*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="95f3d-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="95f3d-105">Microsoft 365 또는 구독에 대해 Azure AD 테 넌 트를 사용 하는 모든 서비스 또는 응용 프로그램에 로그인 하기 위한 추가 보안 수준에 대 한 자세한 내용은 계정을 확인 하기 위해 사용자 이름 및 암호 뿐 아니라 Azure multi-factor authentication을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="95f3d-106">다단계 인증을 사용 하는 경우 사용자는 전화 통화를 승인 하거나, 문자 메시지로 보낸 확인 코드를 입력 하거나, 암호를 올바르게 입력 한 후 스마트 전화에서 앱을 사용 하 여 인증을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="95f3d-107">두 번째 인증 요소가 충족 된 후에만 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="95f3d-108">이 문서에서는 특정 사용자 계정에 대해 텍스트 메시지 기반 인증을 사용 하 고 테스트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="95f3d-109">엔터프라이즈 테스트 환경에 대해 Microsoft 365의 계정에 대 한 multi-factor authentication을 설정 하는 작업은 다음 두 단계와 세 번째 선택적 단계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="95f3d-110">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="95f3d-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="95f3d-111">2 단계: 사용자 2 계정에 대해 multi-factor authentication 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="95f3d-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="95f3d-112">3 단계: 조건부 액세스 정책을 사용 하 여 다단계 인증을 사용 하도록 설정 및 테스트</span><span class="sxs-lookup"><span data-stu-id="95f3d-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="95f3d-114">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="95f3d-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="95f3d-115">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="95f3d-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="95f3d-116">최소 요구 사항과 함께 경량 방식으로 multi-factor authentication을 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="95f3d-117">시뮬레이트된 엔터프라이즈에서 multi-factor authentication을 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="95f3d-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="95f3d-118">다단계 인증을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="95f3d-119">다단계 인증을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="95f3d-120">2 단계: 사용자 2 계정에 대해 multi-factor authentication 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="95f3d-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="95f3d-121">사용자 2 계정에 대해 다단계 인증을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="95f3d-122">별도의 브라우저 전용 인스턴스를 열고 Microsoft 365 관리 센터 ()로 이동한 [https://portal.microsoft.com](https://portal.microsoft.com) 후 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="95f3d-123">왼쪽 탐색 영역에서 **사용자**  >  **활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="95f3d-124">활성 사용자 창에서 **다단계 인증**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="95f3d-125">목록에서 **사용자 2** 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="95f3d-126">**사용자 2** 섹션의 **빠른 단계**에서 **사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="95f3d-127">**다단계 인증 사용** 대화 상자에서 **다단계 인증 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="95f3d-128">**업데이트 완료** 대화 상자에서 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="95f3d-129">**Microsoft 365 관리 센터** 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 선택 하 고 **로그 아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="95f3d-130">브라우저 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-130">Close your browser instance.</span></span>
   
<span data-ttu-id="95f3d-131">사용자 2 계정에 대 한 구성을 완료 하 여 유효성 검사에 텍스트 메시지를 사용 하 고 다음 단계를 사용 하 여 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="95f3d-132">브라우저의 새 개인 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="95f3d-133">[Microsoft 365 관리 센터로](https://admin.microsoft.com) 이동 하 여 사용자 2 계정 이름 및 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="95f3d-134">로그인 한 후에는 계정을 설정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="95f3d-135">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="95f3d-136">**추가 보안 확인** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="95f3d-137">국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="95f3d-138">텍스트 메시지를 받을 스마트 폰의 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="95f3d-139">**방법**에서 **문자 메시지로 코드 보내기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="95f3d-140">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="95f3d-141">스마트 폰에서 받은 문자 메시지의 확인 코드를 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="95f3d-142">**3 단계: 기존 응용 프로그램 유지** 페이지에서 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="95f3d-143">사용자 2 계정으로 처음 로그인 하는 경우 암호를 변경 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="95f3d-144">원래 암호와 새 암호를 두 번 입력 한 다음 **암호 업데이트 및 로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="95f3d-145">새 암호를 안전한 위치에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="95f3d-146">브라우저의 **Microsoft Office 홈** 탭에 사용자 2에 대 한 Office 포털이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="95f3d-147">3 단계: 조건부 액세스 정책을 사용 하 여 다단계 인증을 사용 하도록 설정 및 테스트</span><span class="sxs-lookup"><span data-stu-id="95f3d-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="95f3d-148">*이 단계는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="95f3d-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="95f3d-149">이 단계에서는 그룹 및 조건부 액세스 정책을 사용 하 여 사용자 3 계정에 대해 multi-factor authentication을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="95f3d-150">다음으로 MFAUsers 라는 새 그룹을 만들고 사용자 3 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="95f3d-151">**Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 **그룹** 을 선택 하 고 **그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="95f3d-152">**그룹 추가를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="95f3d-153">**그룹 유형 선택** 창에서 **보안**을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="95f3d-154">**기본 설정** 창에서 **그룹 만들기**를 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="95f3d-155">**그룹 추가 검토 및 완료** 창에서 **mfausers**를 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="95f3d-156">그룹 목록에서 **Mfausers** 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="95f3d-157">**Mfausers** 창에서 **구성원**을 선택 하 고 **모두 보기 및 구성원 관리를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="95f3d-158">**Mfausers** 창에서 **구성원 추가**를 선택 하 고 **사용자 3** 계정을 선택한 다음 닫기, 닫기 **저장**을 선택  >  **Close**  >  **Close**합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="95f3d-159">다음으로 MFAUsers 그룹의 구성원에 대해 다단계 인증을 요구 하는 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="95f3d-160">브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com) 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="95f3d-161">**Azure Active Directory**  >  **보안**  >  **조건부 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="95f3d-162">**조건부 액세스 – 정책** 창에서 **새 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="95f3d-163">**새로 만들기** 창의 **이름** 상자에 **사용자 계정의 MFA** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="95f3d-164">**할당** 섹션에서 **사용자 및 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="95f3d-165">**사용자 및 그룹** 창의 **포함** 탭에서 사용자 및 그룹 **선택**  >  **사용자 및 그룹**을 선택  >  합니다.**를 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="95f3d-166">**선택** 창에서 **mfausers** 그룹을 선택한 다음 **Select**  >  **완료**선택을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="95f3d-167">**새** 창의 **액세스 제어** 섹션에서 **부여**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="95f3d-168">**부여** 창에서 **다단계 인증 필요**를 선택한 다음 **선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="95f3d-169">**새로 만들기** 창에서 **정책 사용** **에 대해 설정을** 선택 하 고 **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="95f3d-170">**Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="95f3d-171">이 정책을 테스트 하려면 로그 아웃 하 고 사용자 3 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="95f3d-172">MFA를 구성 하 라는 메시지가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="95f3d-173">이는 MFAUsers 정책이 적용 되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="95f3d-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="95f3d-174">Next step</span></span>

<span data-ttu-id="95f3d-175">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="95f3d-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="95f3d-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95f3d-176">See also</span></span>

[<span data-ttu-id="95f3d-177">Id 로드맵</span><span class="sxs-lookup"><span data-stu-id="95f3d-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="95f3d-178">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="95f3d-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="95f3d-179">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="95f3d-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="95f3d-180">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95f3d-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
