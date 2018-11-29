---
title: Microsoft 365 테스트 환경을 위한 암호 재설정
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 재설정을 구성하고 테스트합니다.'
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870301"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c81c6-103">Microsoft 365 테스트 환경을 위한 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="c81c6-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c81c6-104">Azure AD SSPR(셀프 서비스 암호 재설정)을 사용하면 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="c81c6-105">이 문서에서는 Microsoft 365 테스트 환경에서 암호 재설정을 구성 및 테스트하는 방법을 두 단계로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="c81c6-106">암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-106">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="c81c6-107">사용자 2 계정에 대한 암호 재설정을 구성하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-107">Configure and test password reset for the User 2 account.</span></span>
    
![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c81c6-109">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c81c6-110">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="c81c6-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c81c6-p101">[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-p101">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="c81c6-114">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="c81c6-115">Office 365 E5 및 EMS E5 평가판 또는 영구 구독</span><span class="sxs-lookup"><span data-stu-id="c81c6-115">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="c81c6-116">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="c81c6-117">Azure AD Connect는 테스트 랩 Windows Server AD 도메인을 Office 365 및 EMS E5 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="c81c6-118">2단계: 암호 재설정 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="c81c6-118">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="c81c6-119">이 단계에서는 그룹 구성원 자격을 통해 Azure 테넌트에서 암호 재설정을 구성한 후 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-119">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="c81c6-120">먼저, 특정 Azure AD 그룹에서 계정에 대해 암호 재설정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-120">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="c81c6-121">브라우저의 비공개 인스턴스에서 [https://portal.azure.com](https://portal.azure.com)을 열고 전역 관리자 계정의 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-121">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="c81c6-122">Azure Portal에서 **Azure Active Directory > 그룹 > 새 그룹**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-122">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="c81c6-p102">**그룹 유형**을 **보안**으로, **그룹 이름**을 **PWReset**으로, **구성원 자격 유형**을 **할당됨**으로 설정합니다. **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="c81c6-125">목록에서 **PWReset** 그룹을 클릭한 후 **구성원**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-125">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="c81c6-p103">**구성원 추가**를 클릭하고 **사용자 2**를 클릭한 후 **선택**을 클릭합니다. **PWReset** 및 **그룹** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="c81c6-128">Azure Active Directory 페이지에서 **암호 재설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-128">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="c81c6-129">**속성** 페이지의 옵션 **셀프 서비스 암호 재설정이 사용하도록 설정됨**에서 **선택됨**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-129">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="c81c6-130">**그룹 선택**에서 **PWReset**을 선택한 후 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-130">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="c81c6-131">비공개 브라우저 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-131">Close the private browser instance.</span></span>

<span data-ttu-id="c81c6-132">다음으로, 사용자 2 계정에 대한 암호 재설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-132">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="c81c6-133">새 비공개 브라우저 인스턴스를 열고 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-133">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="c81c6-134">사용자 2 계정 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-134">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="c81c6-135">**Don’t lose access to your account**(계정에 대한 액세스 유지)에서 인증 전화를 휴대폰 번호로, 인증 이메일을 회사 또는 개인 이메일 계정으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-135">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="c81c6-136">둘 다 확인되면 **정상**을 클릭하고 브라우저의 비공개 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-136">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="c81c6-137">새 비공개 브라우저 인스턴스를 열고 [https://aka.ms/sspr](https://aka.ms/sspr)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-137">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="c81c6-138">사용자 2 계정 자격 증명으로 로그인하고 CAPTCHA의 문자를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-138">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="c81c6-p104">**확인 단계 1**에서 **Email my alternate email**(다른 이메일로 메일 보내기)를 클릭한 다음, **이메일**을 클릭합니다. 이메일을 받으면 확인 코드를 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="c81c6-p105">**Get back into your account(계정에 다시 접속)** 에서 사용자 2 계정에 대한 새 암호를 입력하고 **마침**을 클릭합니다. 사용자 2 계정의 변경된 암호를 적어 안전한 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="c81c6-p106">동일한 브라우저의 별도 탭에서 [https://portal.office.com](https://portal.office.com)으로 이동한 후 사용자 2 계정 이름과 해당 새 암호로 로그인합니다. **Office Home** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-p106">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="c81c6-145">프로덕션 환경에서 암호 재설정을 구성하기 위한 정보 및 단계에 대해서는 ID 단계의 [암호 재설정 간소화](identity-password-reset.md) 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c81c6-145">See the [Simplify password resets](identity-password-reset.md) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="c81c6-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c81c6-146">Next step</span></span>

<span data-ttu-id="c81c6-147">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c81c6-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c81c6-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c81c6-148">See also</span></span>

[<span data-ttu-id="c81c6-149">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="c81c6-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c81c6-150">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="c81c6-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c81c6-151">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="c81c6-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
