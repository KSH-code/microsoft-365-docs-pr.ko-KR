---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 다단계 인증
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 Enterprise 테스트 환경에서 스마트 전화로 전송 되는 텍스트 메시지를 사용 하 여 다단계 인증을 구성 합니다.
ms.openlocfilehash: ab346934ea639e819e4e45dd6560093629ee9cde
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353180"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f8d2f-103">Microsoft 365 Enterprise 테스트 환경에 대 한 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="f8d2f-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f8d2f-104">Office 365 또는 조직의 Azure AD 테 넌 트를 사용 하는 모든 서비스 또는 응용 프로그램에 로그인 하기 위한 추가 보안 수준에 대 한 자세한 내용을 확인 하기 위해 사용자 이름 및 암호를 초과 하는 azure multi-factor authentication을 사용 하도록 설정할 수 있습니다. 계정의.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="f8d2f-105">다단계 인증을 사용 하는 경우 사용자는 전화 통화를 승인 하거나, 문자 메시지로 보낸 확인 코드를 입력 하거나, 암호를 올바르게 입력 한 후 스마트 전화에서 앱 암호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="f8d2f-106">사용자는 이 두 번째 인증 요소를 충족해야 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="f8d2f-107">이 문서에서는 특정 계정에 대해 텍스트 메시지 기반 인증을 사용 하도록 설정 하 고 테스트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="f8d2f-108">Microsoft 365 Enterprise 테스트 환경에서는 계정에 대해 multi-factor authentication을 설정 하는 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="f8d2f-109">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="f8d2f-110">사용자 2 계정에 대해 multi-factor authentication을 사용 하도록 설정 하 고 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f8d2f-112">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f8d2f-113">1 단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="f8d2f-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f8d2f-114">최소 요구 사항과 함께 경량 방식으로 multi-factor authentication을 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f8d2f-115">시뮬레이트된 엔터프라이즈에서 multi-factor authentication을 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8d2f-116">다단계 인증을 테스트 하는 경우에는 AD DS (Active directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f8d2f-117">다단계 인증을 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="f8d2f-118">2 단계: 사용자 2 계정에 대해 multi-factor authentication 사용 및 테스트</span><span class="sxs-lookup"><span data-stu-id="f8d2f-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="f8d2f-119">사용자 2 계정에 대해 다단계 인증을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="f8d2f-120">별도의 브라우저 전용 인스턴스를 열고 Microsoft 365 관리 센터 ([https://portal.microsoft.com](https://portal.microsoft.com))로 이동한 후 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-120">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="f8d2f-121">왼쪽 탐색에서 **사용자 > 활성화된 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-121">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="f8d2f-122">활성 사용자 창에서 **더 > 다단계 인증 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-122">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
4. <span data-ttu-id="f8d2f-123">목록에서 **사용자 2** 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-123">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="f8d2f-124">**사용자 2** 섹션의 **빠른 단계**에서 **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-124">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="f8d2f-125">**다단계 인증 사용** 대화 상자에서 **다단계 인증 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-125">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="f8d2f-126">**업데이트 완료** 대화 상자에서 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-126">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="f8d2f-127">**Microsoft 365 관리 센터** 탭의 오른쪽 위에 있는 사용자 계정 아이콘을 클릭 한 다음 **로그 아웃**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-127">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="f8d2f-128">브라우저 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-128">Close your browser instance.</span></span>
   
<span data-ttu-id="f8d2f-129">사용자 2 계정에 대 한 구성을 완료 하 여 유효성 검사에 텍스트 메시지를 사용 하 고 다음 단계를 사용 하 여 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-129">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="f8d2f-130">브라우저의 새 개인 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-130">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="f8d2f-131">Office 365 portal ([https://portal.office.com](https://portal.office.com))로 이동 하 여 사용자 2 계정 이름 및 암호를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-131">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="f8d2f-132">로그인 한 후에는 계정을 설정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-132">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="f8d2f-133">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-133">Click **Next**.</span></span>
    
4. <span data-ttu-id="f8d2f-134">**추가 보안 확인** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-134">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="f8d2f-135">국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-135">Select your country or region.</span></span>
    
   - <span data-ttu-id="f8d2f-136">텍스트 메시지를 받을 스마트 폰의 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-136">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="f8d2f-137">**방법**에서 **문자 메시지로 코드 보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-137">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="f8d2f-138">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-138">Click **Next**.</span></span>
    
6. <span data-ttu-id="f8d2f-139">스마트 폰에서 받은 문자 메시지의 확인 코드를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-139">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="f8d2f-140">**3 단계: 기존 응용 프로그램 유지** 페이지에서 사용자 2 계정에 대해 표시 된 앱 암호를 안전한 위치에 기록 하 고 **완료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-140">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="f8d2f-141">사용자 2 계정으로 처음 로그인 하는 경우 암호를 변경 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-141">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="f8d2f-142">원래 암호와 새 암호를 두 번 입력 한 다음 **암호 업데이트 및 로그인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-142">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="f8d2f-143">새 암호를 안전한 위치에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-143">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="f8d2f-144">브라우저의 **Microsoft office 홈** 탭에 사용자 2에 대 한 Office 포털이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-144">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="f8d2f-145">프로덕션 환경에서 다단계 인증을 배포 하는 방법에 대 한 자세한 내용은 Identity 단계에서 [multi-factor authentication 설정](identity-multi-factor-authentication.md#identity-mfa) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-145">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="f8d2f-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f8d2f-146">Next step</span></span>

<span data-ttu-id="f8d2f-147">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f8d2f-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8d2f-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8d2f-148">See also</span></span>

[<span data-ttu-id="f8d2f-149">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="f8d2f-149">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f8d2f-150">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="f8d2f-150">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f8d2f-151">Microsoft 365 엔터프라이즈 배포</span><span class="sxs-lookup"><span data-stu-id="f8d2f-151">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f8d2f-152">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="f8d2f-152">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
