---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 다단계 인증
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
description: Microsoft 365 Enterprise 테스트 환경에서 스마트 전화로 전송 되는 텍스트 메시지를 사용 하 여 다단계 인증을 구성 합니다.
ms.openlocfilehash: ea2041a463b224781df101251dab0f4d9f0e8753
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633196"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1300f-103">Microsoft 365 Enterprise 테스트 환경에 대 한 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="1300f-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1300f-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise와 Office 365 Enterprise 테스트 환경 모두에서 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="1300f-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1300f-105">Microsoft 365 또는 구독에 대해 Azure AD 테 넌 트를 사용 하는 모든 서비스 또는 응용 프로그램에 로그인 하기 위한 추가 보안 수준에 대 한 자세한 내용을 확인 하기 위해 사용자 이름 및 암호를 초과 하는 Azure multi-factor authentication을 사용 하도록 설정할 수 있습니다. 계정의.</span><span class="sxs-lookup"><span data-stu-id="1300f-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="1300f-106">다단계 인증을 사용 하는 경우 사용자는 전화 통화를 승인 하거나, 문자 메시지로 보낸 확인 코드를 입력 하거나, 암호를 올바르게 입력 한 후 스마트 전화에서 앱 암호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="1300f-107">사용자는 이 두 번째 인증 요소를 충족해야 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="1300f-108">이 문서에서는 특정 사용자 계정에 대해 텍스트 메시지 기반 인증을 사용 하 고 테스트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="1300f-109">Microsoft 365 Enterprise 테스트 환경에서는 계정에 대해 multi-factor authentication을 설정 하는 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="1300f-110">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="1300f-111">사용자 2 계정에 대해 multi-factor authentication을 사용 하도록 설정 하 고 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="1300f-112">조건부 액세스 정책을 사용 하 여 다단계 인증을 사용 하도록 설정 하 고 테스트 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="1300f-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="1300f-114">[여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-114">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1300f-115">1단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="1300f-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1300f-116">최소 요구 사항과 함께 경량 방식으로 multi-factor authentication을 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1300f-117">시뮬레이트된 엔터프라이즈에서 multi-factor authentication을 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="1300f-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1300f-118">다단계 인증을 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1300f-119">다단계 인증을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="1300f-120">2 단계: 사용자 2 계정에 대해 multi-factor authentication 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="1300f-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="1300f-121">사용자 2 계정에 대해 다단계 인증을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="1300f-122">별도의 브라우저 전용 인스턴스를 열고 Microsoft 365 관리 센터 ([https://portal.microsoft.com](https://portal.microsoft.com))로 이동한 후 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="1300f-123">왼쪽 탐색에서 **사용자 > 활성화된 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="1300f-124">활성 사용자 창에서 **다단계 인증**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="1300f-125">목록에서 **사용자 2** 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="1300f-126">**사용자 2** 섹션의 **빠른 단계**에서 **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="1300f-127">**다단계 인증 사용** 대화 상자에서 **다단계 인증 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="1300f-128">**업데이트 완료** 대화 상자에서 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="1300f-129">**Microsoft 365 관리 센터** 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 클릭 한 다음 **로그 아웃**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="1300f-130">브라우저 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-130">Close your browser instance.</span></span>
   
<span data-ttu-id="1300f-131">사용자 2 계정에 대 한 구성을 완료 하 여 유효성 검사에 텍스트 메시지를 사용 하 고 다음 단계를 사용 하 여 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="1300f-132">브라우저의 새 개인 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="1300f-133">Office 365 portal ([https://portal.office.com](https://portal.office.com))로 이동 하 여 사용자 2 계정 이름 및 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="1300f-134">로그인 한 후에는 계정을 설정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="1300f-135">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="1300f-136">**추가 보안 확인** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="1300f-137">국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="1300f-138">텍스트 메시지를 받을 스마트 폰의 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="1300f-139">**방법**에서 **문자 메시지로 코드 보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="1300f-140">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="1300f-141">스마트 폰에서 받은 문자 메시지의 확인 코드를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="1300f-142">**3 단계: 기존 응용 프로그램 유지** 페이지에서 사용자 2 계정에 대해 표시 된 앱 암호를 안전한 위치에 기록 하 고 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-142">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="1300f-143">사용자 2 계정으로 처음 로그인 하는 경우 암호를 변경 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="1300f-144">원래 암호와 새 암호를 두 번 입력 한 다음 **암호 업데이트 및 로그인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="1300f-145">새 암호를 안전한 위치에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="1300f-146">브라우저의 **Microsoft Office 홈** 탭에 사용자 2에 대 한 Office 포털이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="1300f-147">3 단계: 조건부 액세스 정책을 사용 하 여 다단계 인증을 사용 하도록 설정 및 테스트</span><span class="sxs-lookup"><span data-stu-id="1300f-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="1300f-148">*이 단계는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="1300f-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="1300f-149">이 단계에서는 그룹 및 조건부 액세스 정책을 사용 하 여 사용자 3 계정에 대해 multi-factor authentication을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="1300f-150">다음으로 MFAUsers 라는 새 그룹을 만들고 사용자 3 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="1300f-151">**Microsoft 365 관리 센터** 탭의 왼쪽 탐색 창에서 **그룹** 을 클릭 하 고 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="1300f-152">**그룹 추가를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="1300f-153">**그룹 유형 선택** 창에서 **보안**을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="1300f-154">**기본 설정** 창에서 **그룹 만들기**를 클릭 한 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="1300f-155">**그룹 추가 검토 및 완료** 창에서 **mfausers**를 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="1300f-156">그룹 목록에서 **Mfausers** 그룹을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="1300f-157">**Mfausers** 창에서 **구성원**을 클릭 하 고 **모두 보기 및 구성원 관리를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="1300f-158">**Mfausers** 창에서 **구성원 추가**를 클릭 하 고 **사용자 3** 계정을 선택한 다음 **저장 > 닫기를 클릭 > 닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="1300f-159">다음으로 MFAUsers 그룹의 구성원에 대해 다단계 인증을 요구 하는 조건부 액세스 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="1300f-160">브라우저의 새 탭에서으로 이동 [https://portal.azure.com](https://portal.azure.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="1300f-161">**Azure Active Directory > 보안 > 조건부 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="1300f-162">**조건부 액세스 – 정책** 창에서 **새 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="1300f-163">**새로 만들기** 창에서 **이름**에 **사용자 계정의 MFA** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="1300f-164">**할당** 섹션에서 **사용자 및 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="1300f-165">**사용자 및 그룹** 창의 **포함** 탭에서 사용자 및 그룹 **선택 > >** 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="1300f-166">**선택** 창에서 **mfausers** 그룹을 클릭 한 다음 **완료 > 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="1300f-167">**새** 창의 **액세스 제어** 섹션에서 **부여**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="1300f-168">**부여** 창에서 **다단계 인증 필요**를 클릭 한 다음 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="1300f-169">**새로 만들기** 창에서 **정책 사용** **을 클릭 하** 고 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="1300f-170">**Azure portal** 및 **Microsoft 365 관리 센터** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="1300f-171">이 정책을 테스트 하려면 로그 아웃 하 고 사용자 3 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="1300f-172">MFA를 구성 하 라는 메시지가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="1300f-173">이는 MFAUsers 정책이 적용 되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="1300f-174">프로덕션 환경에서 다단계 인증을 배포 하는 방법에 대 한 자세한 내용은 Identity 단계에서 [multi-factor Authentication 설정](identity-secure-user-sign-ins.md#identity-mfa) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1300f-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="1300f-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1300f-175">Next step</span></span>

<span data-ttu-id="1300f-176">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1300f-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1300f-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1300f-177">See also</span></span>

[<span data-ttu-id="1300f-178">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="1300f-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="1300f-179">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="1300f-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1300f-180">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="1300f-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1300f-181">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="1300f-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
