---
title: Microsoft 365 테스트 환경을 위한 암호 재설정
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 재설정을 구성하고 테스트합니다.'
ms.openlocfilehash: 13169824866e91c1a09d412a875d2f4ce4391fa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339385"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="81c88-103">Microsoft 365 테스트 환경을 위한 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="81c88-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="81c88-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="81c88-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="81c88-105">Azure AD(Azure Active Directory) SSPR(셀프 서비스 암호 재설정)을 사용하면 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="81c88-106">이 문서에서는 테스트 환경에서 암호 재설정을 구성하고 테스트하는 Microsoft 365 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="81c88-107">SSPR 설정에는 다음 세 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="81c88-108">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="81c88-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="81c88-109">2단계: 암호 쓰기 저장을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="81c88-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="81c88-110">3단계: 암호 재설정 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="81c88-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="81c88-112">엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="81c88-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="81c88-113">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="81c88-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="81c88-114">먼저 암호 해시 [동기화의 지침을 따릅니다.](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="81c88-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="81c88-115">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-115">Your resulting configuration looks like this:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="81c88-117">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="81c88-118">Microsoft 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="81c88-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="81c88-119">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="81c88-120">Azure AD Connect는 TESTLAB AD DS(Active Directory Domain Services) 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="81c88-121">2단계: 암호 쓰기 저장을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="81c88-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="81c88-122">[암호 쓰기 저장 테스트 랩 가이드의 2단계](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)에 있는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="81c88-123">암호 쓰기 저장을 사용하려면 암호를 재설정할 수 있도록 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="81c88-124">3단계: 암호 재설정 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="81c88-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="81c88-125">이 단계에서는 그룹 구성원 자격을 통해 Azure AD 테넌트에서 암호 재설정을 구성한 다음 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="81c88-126">먼저, 특정 Azure AD 그룹에서 계정에 대해 암호 재설정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="81c88-127">브라우저의 비공개 인스턴스에서 [https://portal.azure.com](https://portal.azure.com)을 열고 전역 관리자 계정의 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="81c88-128">Azure Portal에서 그룹 **Azure Active Directory**  >    >  **그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="81c88-129">**그룹 유형** 을 **보안** 으로, **그룹 이름** 을 **PWReset** 으로, **구성원 자격 유형** 을 **할당됨** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="81c88-130">구성원을 **선택하고** 사용자 **3을 찾아 선택하고** 선택 을 선택한 다음 만들기를  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="81c88-131">**그룹** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="81c88-132">왼쪽 Azure Active Directory 창에서 암호 **재설정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="81c88-133">**암호 재설정 속성** 창의 옵션 **셀프 서비스 암호 재설정이 사용하도록 설정됨** 에서 **선택됨** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="81c88-134">그룹 **선택을 선택하고** **PWReset** 그룹을 선택한 다음 **저장을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="81c88-135">비공개 브라우저 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-135">Close the private browser instance.</span></span>

<span data-ttu-id="81c88-136">다음으로 사용자 3 계정에 대한 암호 재설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="81c88-137">새 비공개 브라우저 인스턴스를 열고 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="81c88-138">사용자 3 계정 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="81c88-139">필요한 **추가 정보에서** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="81c88-140">**계정에 대한 액세스 유지** 에서 인증 전화를 휴대폰 번호로, 인증 이메일을 회사 또는 개인 이메일 계정으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="81c88-141">두 가지를 모두 확인한 후 **양호한** 모양을 선택한 다음 브라우저의 개인 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="81c88-142">새 개인 브라우저 인스턴스에서 로 [https://aka.ms/sspr](https://aka.ms/sspr) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="81c88-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="81c88-143">사용자 3 계정 이름을 입력하고 CAPTCHA의 문자를 입력한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="81c88-144">확인 **1단계에서** 내 대체 전자 **메일 전자 메일을** 선택한 다음 전자 메일을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="81c88-145">전자 메일을 받으면 확인 코드를 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="81c88-146">계정으로 **돌아가기에서** 사용자 3 계정에 대한 새 암호를 입력하고 마친 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="81c88-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="81c88-147">사용자 3 계정의 변경된 암호를 적어놓고 안전한 장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="81c88-148">동일한 브라우저의 별도 탭에서 [https://admin.microsoft.com](https://admin.microsoft.com)으로 이동한 후 사용자 3 계정 이름과 해당 새 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-148">In a separate tab of the same browser, go to [https://admin.microsoft.com](https://admin.microsoft.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="81c88-149">**Microsoft Office 홈** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="81c88-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="81c88-150">Next step</span></span>

<span data-ttu-id="81c88-151">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="81c88-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="81c88-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81c88-152">See also</span></span>

[<span data-ttu-id="81c88-153">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="81c88-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="81c88-154">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="81c88-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="81c88-155">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="81c88-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)