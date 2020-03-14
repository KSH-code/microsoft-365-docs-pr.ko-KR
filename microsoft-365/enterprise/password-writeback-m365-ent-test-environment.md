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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 쓰기 저장을 구성합니다.'
ms.openlocfilehash: 8ff6c8c7d2eae735a2572bae1c437502602cfd0b
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633086"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="df1c8-103">Microsoft 365 테스트 환경을 위한 암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="df1c8-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="df1c8-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="df1c8-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="df1c8-p101">암호 쓰기 저장은 Azure AD(Azure Active Directory)를 통해 자신의 암호를 업데이트하도록 허용합니다. 이는 로컬 AD DS(Active Directory Domain Services)에 복제됩니다. 암호 쓰기 저장을 사용하면 사용자가 원래 사용자 계정이 저장된 온-프레미스 AD DS를 통해 암호를 업데이트할 필요가 없습니다. 이는 온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don’t need to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="df1c8-108">이 문서에서는 암호 쓰기 저장에 대해 Microsoft 365 테스트 환경을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-108">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="df1c8-109">이러한 기능을 설정하는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-109">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="df1c8-110">암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-110">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="df1c8-111">테스트 랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-111">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="df1c8-113">[여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="df1c8-114">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="df1c8-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="df1c8-p102">먼저 [암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="df1c8-118">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-118">This configuration consists of:</span></span> 
  
- <span data-ttu-id="df1c8-119">Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="df1c8-119">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="df1c8-120">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-120">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="df1c8-121">Azure AD Connect는 Test Lab AD DS 도메인을 Microsoft 365 또는 Office 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="df1c8-122">2단계: 테스트랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="df1c8-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="df1c8-123">먼저 User 1 계정이 전역 관리자 역할을 가지도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="df1c8-124">[Microsoft 365 관리 센터](https://portal.microsoft.com)에서 글로벌 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="df1c8-125">**활성 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-125">Click **Active users**.</span></span>
 
3. <span data-ttu-id="df1c8-126">**활성 사용자** 페이지에서 **user1** 계정을 클릭하고,</span><span class="sxs-lookup"><span data-stu-id="df1c8-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="df1c8-127">**user1** 창에서 **역할** 옆의 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="df1c8-p103">user1의 **사용자 역할 편집** 창에서 **전역 관리자**를 클릭합니다. **저장**을 클릭한 다음 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-p103">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="df1c8-130">다음으로, 사용자 1 계정을 테스트 랩 AD DS 도메인의 다른 사용자를 대신하여 암호를 변경할 수 있는 보안 설정으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="df1c8-131">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="df1c8-132">APP1의 바탕 화면에서 **시작**을 클릭하고 **활성**을 입력한 후 **Active Directory 사용자 및 컴퓨터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="df1c8-p104">메뉴 모음에서 **보기**를 클릭합니다. **고급 기능**이 사용 안 함으로 되어 있으면 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-p104">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="df1c8-135">트리 창에서 도메인을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭한 다음 **보안** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="df1c8-136">**고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="df1c8-137">**사용 권한** 탭에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="df1c8-138">**보안 주체 선택**을 클릭하고 **User1**을 입력 한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="df1c8-139">**적용 대상**에서 **하위 항목 사용자 개체**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="df1c8-140">**사용 권한**에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="df1c8-141">암호 변경</span><span class="sxs-lookup"><span data-stu-id="df1c8-141">Change password</span></span>
    - <span data-ttu-id="df1c8-142">암호 다시 설정</span><span class="sxs-lookup"><span data-stu-id="df1c8-142">Reset password</span></span>

10. <span data-ttu-id="df1c8-143">**속성**에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="df1c8-144">lockoutTime 쓰기</span><span class="sxs-lookup"><span data-stu-id="df1c8-144">Write lockoutTime</span></span>
    - <span data-ttu-id="df1c8-145">pwdLastSet 쓰기</span><span class="sxs-lookup"><span data-stu-id="df1c8-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="df1c8-146">**확인**을 세 번 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="df1c8-147">**Active Directory 사용자 및 컴퓨터**를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="df1c8-148">다음으로 암호 쓰기 저장을 위해 APP1에서 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="df1c8-149">필요한 경우 TESTLAB\User1 계정으로 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="df1c8-150">APP1의 데스크톱에서 **Azure AD Connect**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="df1c8-151">**시작** 페이지에서 **구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="df1c8-152">**추가 작업** 페이에서 **동기화 옵션 사용자 지정**을 클릭한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="df1c8-153">**Azure AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-153">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="df1c8-154">**디렉터리 연결** 및 **도메인/OU 필터링** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="df1c8-155">**선택적 기능** 페이지에서 **암호 쓰기 저장**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-155">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="df1c8-156">**구성 준비** 페이지에서 **구성**을 클릭하고 프로세스가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="df1c8-157">구성이 완료되면 **종료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="df1c8-158">이제 시뮬레이션된 인트라넷의 가상 네트워크에 연결되지 않은 컴퓨터의 사용자에 대한 암호 쓰기 저장을 테스트할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="df1c8-159">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-159">Here is your resulting configuration:</span></span>

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="df1c8-161">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-161">This configuration consists of:</span></span>

- <span data-ttu-id="df1c8-162">Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독(DNS 도메인 Test Lab 포함).\<도메인 이름> 등록됨.</span><span class="sxs-lookup"><span data-stu-id="df1c8-162">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="df1c8-163">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-163">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="df1c8-164">Azure AD Connect는 Microsoft 365 또는 Office 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 테스트 랩 AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 or Office 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="df1c8-165">암호 쓰기 저장 기능은 사용자가 간소화된 인트라넷에 연결하지 않고도 Azure AD를 통해 암호를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="df1c8-166">프로덕션 환경에서 암호 업데이트를 구성하기 위한 정보 및 단계에 대해서는 ID 단계의 [암호 쓰기 저장 간소화](identity-add-user-accounts.md#identity-pw-writeback) 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df1c8-166">See the [Simplify password updates](identity-add-user-accounts.md#identity-pw-writeback) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="df1c8-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="df1c8-167">Next step</span></span>

<span data-ttu-id="df1c8-168">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="df1c8-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="df1c8-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df1c8-169">See also</span></span>

[<span data-ttu-id="df1c8-170">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="df1c8-170">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="df1c8-171">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="df1c8-171">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="df1c8-172">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="df1c8-172">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


