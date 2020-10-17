---
title: Microsoft 365 테스트 환경을 위한 암호 쓰기 저장
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: '요약: Microsoft 365 테스트 환경을 위한 암호 쓰기 저장을 구성합니다.'
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487131"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="22bff-103">Microsoft 365 테스트 환경을 위한 암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="22bff-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="22bff-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="22bff-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="22bff-p101">사용자는 암호 쓰기 저장을 사용 하 여 Azure Active Directory (Azure AD)를 통해 암호를 업데이트할 수 있으며, 그러면 로컬 AD DS (Active Directory 도메인 서비스)에 복제 됩니다. 암호 쓰기 저장을 사용 하는 경우 사용자는 원래 사용자 계정이 저장 되는 온-프레미스 AD DS를 통해 암호를 업데이트할 필요가 없습니다. 이는 온-프레미스 네트워크에 대 한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에 게 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-p101">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="22bff-108">이 문서에서는 암호 쓰기 저장을 위해 Microsoft 365 테스트 환경을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="22bff-109">암호 쓰기 저장을 위한 테스트 환경을 구성 하는 작업은 다음 두 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="22bff-110">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="22bff-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="22bff-111">2단계: 테스트랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="22bff-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="22bff-113">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="22bff-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="22bff-114">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="22bff-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="22bff-p102">먼저 [암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md)의 지침을 따릅니다. 구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Your resulting configuration looks like this:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="22bff-118">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="22bff-119">Microsoft 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="22bff-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="22bff-120">인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="22bff-121">Azure AD Connect는 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="22bff-122">2단계: 테스트랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="22bff-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="22bff-123">먼저 User 1 계정이 전역 관리자 역할을 가지도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="22bff-124">[Microsoft 365 관리 센터](https://portal.microsoft.com)에서 글로벌 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="22bff-125">**활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="22bff-126">**활성 사용자** 페이지에서 **user1** 계정을 선택 하 고,</span><span class="sxs-lookup"><span data-stu-id="22bff-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="22bff-127">**User1** 창에서 **역할**옆에 있는 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="22bff-128">User1에 대 한 **사용자 역할 편집** 창에서 **전역 관리자**를 선택 하 고 **저장**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="22bff-129">다음으로, 사용자 1 계정을 테스트 랩 AD DS 도메인의 다른 사용자를 대신하여 암호를 변경할 수 있는 보안 설정으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="22bff-130">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="22bff-131">APP1의 바탕 화면에서 **시작**을 선택 하 고 **활성**을 입력 한 후 **active Directory 사용자 및 컴퓨터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="22bff-132">메뉴 모음에서 **보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="22bff-133">**고급 기능이** 설정 되어 있지 않은 경우이를 선택 하 여 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="22bff-134">트리 창에서 도메인을 선택 하 고 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 **보안** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="22bff-135">**고급**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="22bff-136">**사용 권한** 탭에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="22bff-137">**보안 주체 선택을**선택 하 고 **User1**을 입력 한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="22bff-138">**적용 대상**에서 **하위 항목 사용자 개체**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="22bff-139">**사용 권한**에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="22bff-140">**암호 변경**</span><span class="sxs-lookup"><span data-stu-id="22bff-140">**Change password**</span></span>
    - <span data-ttu-id="22bff-141">**암호 다시 설정**</span><span class="sxs-lookup"><span data-stu-id="22bff-141">**Reset password**</span></span>

10. <span data-ttu-id="22bff-142">**속성**에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="22bff-143">**lockoutTime 쓰기**</span><span class="sxs-lookup"><span data-stu-id="22bff-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="22bff-144">**pwdLastSet 쓰기**</span><span class="sxs-lookup"><span data-stu-id="22bff-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="22bff-145">**확인** 을 세 번 선택 하 여 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="22bff-146">**Active Directory 사용자 및 컴퓨터**를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="22bff-147">다음으로 암호 쓰기 저장을 위해 APP1에서 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="22bff-148">필요한 경우 TESTLAB\User1 계정으로 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="22bff-149">APP1의 데스크톱에서 **Azure AD Connect**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="22bff-150">**시작 페이지**에서 **구성을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="22bff-151">**추가 작업** 페이지에서 **동기화 옵션 사용자 지정**을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="22bff-152">**AZURE AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="22bff-153">**디렉터리 연결** 및 **도메인/OU 필터링** 페이지에서 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="22bff-154">**선택적 기능** 페이지에서 **암호 쓰기 저장**을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="22bff-155">**구성 준비 완료** 페이지에서 **구성을** 선택 하 고 프로세스가 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="22bff-156">구성 완료가 표시 되 면 **끝내기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="22bff-157">이제 시뮬레이트된 인트라넷의 가상 네트워크에 연결 되지 않은 컴퓨터의 사용자에 대 한 암호 쓰기 저장을 테스트할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="22bff-158">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-158">Your resulting configuration looks like this:</span></span>

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="22bff-160">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-160">This configuration consists of:</span></span>

- <span data-ttu-id="22bff-161">DNS 도메인 TESTLAB과 함께 Microsoft 365 E5 평가판 또는 유료 구독입니다.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="22bff-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="22bff-162">유료 구독.</span><span class="sxs-lookup"><span data-stu-id="22bff-162">registered.</span></span>
- <span data-ttu-id="22bff-163">인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="22bff-164">Azure AD Connect는 Microsoft 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 TESTLAB AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="22bff-165">암호 쓰기 저장 기능은 사용자가 간소화된 인트라넷에 연결하지 않고도 Azure AD를 통해 암호를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="22bff-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="22bff-166">Next step</span></span>

<span data-ttu-id="22bff-167">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="22bff-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="22bff-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22bff-168">See also</span></span>

[<span data-ttu-id="22bff-169">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="22bff-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="22bff-170">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="22bff-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="22bff-171">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22bff-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


