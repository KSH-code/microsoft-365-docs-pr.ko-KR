---
title: Microsoft 365 환경 다단계 인증을 위한 데이터 관리
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
description: 엔터프라이즈 테스트 환경의 휴대폰에서 스마트폰으로 전송된 문자 메시지를 사용하여 Microsoft 365 다단계 인증을 구성합니다.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923759"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3bcbd-103">엔터프라이즈 테스트 환경에 대한 Microsoft 365 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="3bcbd-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3bcbd-104">*이 테스트 랩 가이드는 엔터프라이즈 및 엔터프라이즈용 Microsoft 365 둘 다에 사용할 Office 365 Enterprise 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="3bcbd-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="3bcbd-105">구독에 대해 Azure AD 테넌트를 사용하는 서비스 또는 응용 프로그램에 Microsoft 365 로그인하기 위한 추가 보안 수준을 위해 계정 확인을 위해 사용자 이름과 암호 이상이 필요한 Azure AD 다단계 인증을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="3bcbd-106">다단계 인증을 사용하는 경우 사용자는 전화 통화를 확인하거나, 문자 메시지로 전송된 확인 코드를 입력하거나, 암호를 올바르게 입력한 후 스마트폰의 앱으로 인증을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="3bcbd-107">두 번째 인증 요소가 충족된 후에만 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="3bcbd-108">이 문서에서는 특정 사용자 계정에 대해 텍스트 메시지 기반 인증을 사용하도록 설정하고 테스트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="3bcbd-109">엔터프라이즈 테스트 환경에 대한 Microsoft 365 계정에 대해 다단계 인증을 설정하려면 다음 두 단계와 세 번째 선택적 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="3bcbd-110">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="3bcbd-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="3bcbd-111">2단계: 사용자 2 계정에 대해 다단계 인증 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="3bcbd-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="3bcbd-112">3단계: 조건부 액세스 정책을 사용하여 다단계 인증 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="3bcbd-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3bcbd-114">엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="3bcbd-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3bcbd-115">1단계: 엔터프라이즈 테스트 Microsoft 365 사용자 환경 구축</span><span class="sxs-lookup"><span data-stu-id="3bcbd-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3bcbd-116">최소 요구 사항으로 간단한 방식으로 다단계 인증을 테스트하려는 경우 간단한 기본 구성의 [지침을 따릅니다.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="3bcbd-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3bcbd-117">시뮬레이트된 엔터프라이즈에서 다단계 인증을 테스트하려는 경우 [통과 인증의 지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="3bcbd-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bcbd-118">다단계 인증을 테스트하는 데는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화를 포함하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3bcbd-119">여기서는 다단계 인증을 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="3bcbd-120">2단계: 사용자 2 계정에 대해 다단계 인증 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="3bcbd-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="3bcbd-121">다음 단계를 사용하여 사용자 2 계정에 대해 다단계 인증을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="3bcbd-122">별도의 개인 브라우저 인스턴스를 열고 Microsoft 365 관리 센터()로 이동한 다음 전역 관리자 계정으로 [https://portal.microsoft.com](https://portal.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="3bcbd-123">왼쪽 탐색에서 사용자 활성  >  **사용자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="3bcbd-124">활성 사용자 창에서 다단계 인증 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="3bcbd-125">목록에서 사용자 **2 계정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="3bcbd-126">사용자 **2 섹션의** 빠른 **단계에서** 사용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="3bcbd-127">다단계  인증 사용 대화 상자에서 다단계 인증 **사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="3bcbd-128">업데이트 **성공 대화** 상자에서 닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="3bcbd-129">관리 **Microsoft 365** 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 선택한 다음 **로그인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="3bcbd-130">브라우저 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-130">Close your browser instance.</span></span>
   
<span data-ttu-id="3bcbd-131">유효성 검사에 문자 메시지를 사용하려면 사용자 2 계정의 구성을 완료하고 다음 단계를 사용하여 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="3bcbd-132">브라우저의 새 개인 인스턴스를 여는 경우.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="3bcbd-133">Microsoft 365 [관리 센터로](https://admin.microsoft.com) 이동하고 사용자 2 계정 이름 및 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="3bcbd-134">로그인한 후 자세한 정보를 위해 계정을 설정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="3bcbd-135">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="3bcbd-136">추가 **보안 확인 페이지에서 다음을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="3bcbd-137">국가 또는 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="3bcbd-138">문자 메시지를 받을 스마트폰의 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="3bcbd-139">**메서드에서** 문자 **메시지로 코드 보내기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="3bcbd-140">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="3bcbd-141">스마트폰에 수신된 문자 메시지의 확인 코드를 입력한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="3bcbd-142">**3단계: 기존 응용 프로그램 유지 페이지에서** 완료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="3bcbd-143">사용자 2 계정으로 처음 로그인한 경우 암호를 변경하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="3bcbd-144">원래 암호와 새 암호를 두 번 입력한 다음 암호 업데이트를 선택하고 **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="3bcbd-145">새 암호를 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="3bcbd-146">브라우저의 Office 탭에 사용자 2용 Microsoft Office  포털이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="3bcbd-147">3단계: 조건부 액세스 정책을 사용하여 다단계 인증 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="3bcbd-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="3bcbd-148">*이 단계는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="3bcbd-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="3bcbd-149">이 단계에서는 그룹 및 조건부 액세스 정책을 사용하여 사용자 3 계정에 대해 다단계 인증을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="3bcbd-150">그런 다음 MFAUsers라는 새 그룹을 만들고 사용자 3 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="3bcbd-151">관리 **Microsoft 365 탭의** 왼쪽 탐색  창에서 그룹을 선택한 다음 그룹을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="3bcbd-152">그룹 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="3bcbd-153">그룹 **유형 선택 창에서** 보안 을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="3bcbd-154">기본 **설정** 창에서 그룹 만들기를 선택한 다음 닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="3bcbd-155">검토 및 그룹 **추가 완료 창에서** **MFAUsers를 입력하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="3bcbd-156">그룹 목록에서 **MFAUsers 그룹을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="3bcbd-157">**MFAUsers 창에서** 구성원 을 선택한 다음 모두 보기 및 구성원 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="3bcbd-158">**MFAUsers 창에서** 구성원 **추가를** 선택하고 사용자 **3** 계정을 선택한 다음 저장 **닫기**  >  **닫기 를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="3bcbd-159">그런 다음 MFAUsers 그룹의 구성원에 대해 다단계 인증을 요구하는 조건부 액세스 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="3bcbd-160">브라우저의 새 탭에서 로 [https://portal.azure.com](https://portal.azure.com) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="3bcbd-161">보안 **Azure Active Directory**  >    >  **액세스 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="3bcbd-162">조건부 **액세스 - 정책** 창에서 새 정책을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="3bcbd-163">새 **창의** 이름 상자에 사용자 계정에 **대한 MFA를** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="3bcbd-164">할당 **섹션에서** 사용자 및 **그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="3bcbd-165">사용자 **및** 그룹 포함 창의 포함 **탭에서** 사용자 및 그룹 사용자 및 **그룹**  >  **선택 을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="3bcbd-166">선택 **창에서** **MFAUsers** 그룹을 선택한 다음 완료 **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="3bcbd-167">새 **창의 액세스** 제어 **섹션에서** 부여를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="3bcbd-168">부여 **창에서** 다단계 인증 **필요를** 선택한 다음 **선택을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="3bcbd-169">새로 만들기 **창에서** 정책 사용에 **대해** **을** 선택하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="3bcbd-170">Azure **Portal을** 닫고 관리 **Microsoft 365 탭을 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="3bcbd-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="3bcbd-171">해당 정책을 테스트하려면 사용자 3 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="3bcbd-172">MFA를 구성하라는 메시지가 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="3bcbd-173">이는 MFAUsers 정책이 적용되고 있는 것을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="3bcbd-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="3bcbd-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3bcbd-174">Next step</span></span>

<span data-ttu-id="3bcbd-175">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3bcbd-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bcbd-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bcbd-176">See also</span></span>

[<span data-ttu-id="3bcbd-177">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="3bcbd-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3bcbd-178">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="3bcbd-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3bcbd-179">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="3bcbd-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3bcbd-180">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="3bcbd-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)