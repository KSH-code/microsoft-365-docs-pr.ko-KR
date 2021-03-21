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
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921483"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6c57d-103">Microsoft 365 테스트 환경을 위한 암호 쓰기 저장</span><span class="sxs-lookup"><span data-stu-id="6c57d-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6c57d-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="6c57d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6c57d-105">사용자는 암호 쓰기 저장을 사용하여 Azure AD(Azure Active Directory)를 통해 암호를 업데이트한 다음 로컬 AD DS(Active Directory 도메인 서비스)로 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="6c57d-106">암호 쓰기 저장을 사용하는 경우 사용자는 원래 사용자 계정이 저장되어 있는 사내 AD DS를 통해 암호를 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="6c57d-107">이렇게 하면 원격 액세스 연결이 없는 로밍 또는 원격 사용자가 자신의 On-프레미스 네트워크에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="6c57d-108">이 문서에서는 암호 쓰기 저장을 위해 Microsoft 365 테스트 환경을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="6c57d-109">암호 쓰기 저장을 위해 테스트 환경을 구성하는 단계는 다음 두 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="6c57d-110">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="6c57d-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="6c57d-111">2단계: 테스트랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6c57d-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6c57d-113">엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365 테스트](../downloads/Microsoft365EnterpriseTLGStack.pdf)랩 가이드 스택으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="6c57d-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6c57d-114">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="6c57d-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6c57d-115">먼저 암호 해시 [동기화의 지침을 따릅니다.](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="6c57d-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="6c57d-116">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-116">Your resulting configuration looks like this:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="6c57d-118">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="6c57d-119">Microsoft 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="6c57d-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="6c57d-120">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6c57d-121">Azure AD Connect는 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="6c57d-122">2단계: 테스트랩 AD DS 도메인에 대한 암호 쓰기 저장을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6c57d-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="6c57d-123">먼저 User 1 계정이 전역 관리자 역할을 가지도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="6c57d-124">[Microsoft 365 관리 센터](https://portal.microsoft.com)에서 글로벌 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="6c57d-125">활성 **사용자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="6c57d-126">활성 **사용자 페이지에서** **user1 계정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="6c57d-127">**user1 창에서** 역할 **옆의** **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="6c57d-128">**user1의 사용자 역할 편집** 창에서 전역 관리자를 선택하고 저장을 선택한 다음 닫기  **를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="6c57d-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="6c57d-129">다음으로, 사용자 1 계정을 테스트 랩 AD DS 도메인의 다른 사용자를 대신하여 암호를 변경할 수 있는 보안 설정으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="6c57d-130">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="6c57d-131">APP1의 바탕 화면에서 시작 **,** **활성** 을 입력하고 Active Directory 사용자 및 컴퓨터를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="6c57d-132">메뉴 표시줄에서 보기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="6c57d-133">고급 **기능을** 사용하도록 설정하지 않은 경우 해당 기능을 선택하여 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="6c57d-134">트리 창에서 도메인을 선택하고 보유(또는 마우스 오른쪽 단추 클릭)한 다음 **속성** 을 선택한 다음 보안 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="6c57d-135">고급 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="6c57d-136">사용 권한 **탭에서** 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="6c57d-137">보안 **주체 선택을** 선택하고 **User1 을 입력한** 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="6c57d-138">**적용 대상** 에서 **하위 항목 사용자 개체** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="6c57d-139">**사용 권한** 에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="6c57d-140">**암호 변경**</span><span class="sxs-lookup"><span data-stu-id="6c57d-140">**Change password**</span></span>
    - <span data-ttu-id="6c57d-141">**암호 다시 설정**</span><span class="sxs-lookup"><span data-stu-id="6c57d-141">**Reset password**</span></span>

10. <span data-ttu-id="6c57d-142">**속성** 에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="6c57d-143">**lockoutTime 쓰기**</span><span class="sxs-lookup"><span data-stu-id="6c57d-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="6c57d-144">**pwdLastSet 쓰기**</span><span class="sxs-lookup"><span data-stu-id="6c57d-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="6c57d-145">**확인을** 세 번 선택하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="6c57d-146">**Active Directory 사용자 및 컴퓨터** 를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="6c57d-147">다음으로 암호 쓰기 저장을 위해 APP1에서 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="6c57d-148">필요한 경우 TESTLAB\User1 계정으로 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="6c57d-149">APP1의 데스크톱에서 **Azure AD Connect** 를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="6c57d-150">시작 **페이지에서 구성을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="6c57d-151">추가 **작업 페이지에서** 동기화 옵션 사용자 지정을 **선택하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="6c57d-152">Azure **AD에 연결 페이지에서** 전역 관리자 계정 자격 증명을 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="6c57d-153">Connect **directories** and **Domain/OU filtering** 페이지에서 Next(다음)를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="6c57d-154">선택적 **기능 페이지에서** 암호 쓰기 **저장을** 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="6c57d-155">구성 **준비 완료 페이지에서**  구성을 선택하고 프로세스가 완료될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="6c57d-156">구성이 완료되면 **끝내기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c57d-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="6c57d-157">이제 시뮬레이트된 인트라넷의 가상 네트워크에 연결되지 않은 컴퓨터에서 사용자에 대한 암호 쓰기 저장을 테스트할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="6c57d-158">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-158">Your resulting configuration looks like this:</span></span>

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="6c57d-160">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-160">This configuration consists of:</span></span>

- <span data-ttu-id="6c57d-161">DNS 도메인 TESTLAB이 있는 Microsoft 365 E5 평가판 또는 유료 구독\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="6c57d-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="6c57d-162">유료 구독.</span><span class="sxs-lookup"><span data-stu-id="6c57d-162">registered.</span></span>
- <span data-ttu-id="6c57d-163">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6c57d-164">Azure AD Connect는 Microsoft 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 TESTLAB AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="6c57d-165">암호 쓰기 저장 기능은 사용자가 간소화된 인트라넷에 연결하지 않고도 Azure AD를 통해 암호를 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="6c57d-166">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6c57d-166">Next step</span></span>

<span data-ttu-id="6c57d-167">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6c57d-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c57d-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c57d-168">See also</span></span>

[<span data-ttu-id="6c57d-169">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="6c57d-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6c57d-170">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="6c57d-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6c57d-171">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="6c57d-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)