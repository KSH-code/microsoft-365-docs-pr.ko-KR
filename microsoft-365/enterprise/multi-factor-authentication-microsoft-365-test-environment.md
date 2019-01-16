---
title: 다단계 인증 Microsoft 365 기업에 대 한 테스트 환경
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
description: Microsoft 365 기업 테스트 환경에서 스마트폰으로 전송 하는 텍스트 메시지를 사용 하 여 다단계 인증을 구성 합니다.
ms.openlocfilehash: 353f09253794670e8107e084acb3a01cd309fd60
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869721"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d544d-103">다단계 인증 Microsoft 365 기업에 대 한 테스트 환경</span><span class="sxs-lookup"><span data-stu-id="d544d-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d544d-p101">추가 된 Office 365 또는 모든 서비스 또는 조직에 대 한 Azure AD 테 넌 트를 사용 하는 응용 프로그램에 로그인 하는 것에 대 한 보안 수준을 대 한 사용자 이름 및 암호 확인 하기 위해 단순한 필요 Azure 다단계 인증을 사용할 수 있습니다는 계정입니다. 다단계 인증을 사용 하면 사용자가 전화 통화, 텍스트 메시지를 열고 전송 확인 코드를 입력 하거나 올바르게 자신의 암호를 입력 한 후 스마트 전화 앱 암호를 지정 해야 합니다. 이 두번째 인증 요소를 충족 된 후에에 로그인 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-p101">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account. With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords. They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="d544d-107">이 문서에서는 설정 하 고 특정 계정에 대 한 텍스트 메시지 기반 인증을 테스트 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="d544d-108">Microsoft 365 기업 테스트 환경에서 계정에 대 한 다단계 인증을 설정 하는 두 단계로 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="d544d-109">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="d544d-110">사용 하도록 설정 하 고 사용자 2 계정에 대 한 다단계 인증을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d544d-112">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d544d-113">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="d544d-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d544d-114">최소 요구 사항을 경량 방식으로 다단계 인증을 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d544d-115">시뮬레이션 된 엔터프라이즈에서 다단계 인증을 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d544d-p102">다단계 인증을 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공은 다단계 인증을 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-p102">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="d544d-118">2 단계: 사용 하도록 설정 하 고 사용자 2 계정에 대 한 다단계 인증 테스트</span><span class="sxs-lookup"><span data-stu-id="d544d-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="d544d-119">다음이 단계를 사용 하 여 사용자 2 계정에 대 한 다단계 인증을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="d544d-120">브라우저의 개인 별도 인스턴스를 열고, Office 포털으로 이동 ([https://office.com](https://office.com)), 전역 관리자 계정을 사용 하 여 다음에 서명 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="d544d-121">기본 포털 페이지에서 **관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="d544d-122">왼쪽 탐색에서 **사용자 > 활성화된 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="d544d-123">현재 사용자가 창에서 클릭 **더 > 다단계 인증 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="d544d-124">목록에서 **사용자 2** 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="d544d-125">**사용자 2** 섹션에서 **빠른 단계** **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="d544d-126">**다단계 인증을 사용 하도록 설정 하는 방법에 대 한** 대화 상자에서 **다단계 인증 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="d544d-127">**성공적으로 업데이트 하는** 대화 상자에서 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="d544d-128">**Microsoft Office 홈** 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 클릭 하 고 **로그 아웃**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="d544d-129">브라우저 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-129">Close your browser instance.</span></span>
   
<span data-ttu-id="d544d-130">유효성 검사에 대 한 텍스트 메시지를 사용 하 고 이러한 단계를 테스트 하는 사용자 2 계정에 대 한 구성을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="d544d-131">브라우저의 개인 새 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="d544d-132">Office 포털에 이동 ([https://office.com](https://office.com))와 사용자 2 계정 사용 하 여 로그인 (@ user2\<조직 이름 >. onmicrosoft.com) 및 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="d544d-p103">로그인 한 후 자세한 정보에 대 한 계정을 설정 하 라는 메시지가 표시 됩니다. **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-p103">After signing in, you are prompted to set up the account for more information. Click **Next**.</span></span>
    
4. <span data-ttu-id="d544d-135">**추가 보안 확인** 페이지 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="d544d-136">국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="d544d-137">텍스트 메시지를 받을 스마트 전화의 전화번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="d544d-138">**메서드**를 **보내기 나에 게 텍스트 메시지를 여는 코드를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="d544d-139">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="d544d-140">스마트 전화기에서 받은 텍스트 메시지에서 확인 코드를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="d544d-141">**3 단계: 기존 응용 프로그램을 유지** 페이지를 안전한 위치에 2 사용자 계정에 대 한 표시 된 앱 암호를 기록 하 고 다음 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="d544d-p104">이것은 처음으로 하는 경우 귀하가 사용자 2 계정을 사용 하 여 메시지가 표시 되는 암호를 변경 해야 합니다. 원래 암호와 새 암호를을 두번 입력 하 고 **암호를 업데이트 하 고 로그인**을 클릭 합니다. 안전한 위치에 새 암호를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="d544d-145">사용자 2에 대 한 Office 포털 브라우저의 **Microsoft Office Home** 탭에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="d544d-146">정보 및 프로덕션 환경에서 다단계 인증을 배포에 대 한 링크에 대 한 Identity 단계에서 [다단계 인증을 설정](identity-multi-factor-authentication.md) 하는 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d544d-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="d544d-147">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d544d-147">Next step</span></span>

<span data-ttu-id="d544d-148">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d544d-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d544d-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d544d-149">See also</span></span>

[<span data-ttu-id="d544d-150">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="d544d-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="d544d-151">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="d544d-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d544d-152">Microsoft 365 엔터프라이즈 배포</span><span class="sxs-lookup"><span data-stu-id="d544d-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d544d-153">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="d544d-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
