---
title: Microsoft 365 테스트 환경을 위한 암호 해시 동기화
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 및 로그인을 구성하고 보여 줍니다.'
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921507"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="475ea-103">Microsoft 365 테스트 환경을 위한 암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="475ea-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="475ea-104">*이 테스트 랩 가이드는 엔터프라이즈 및 엔터프라이즈용 Microsoft 365 둘 다에 사용할 Office 365 Enterprise 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="475ea-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="475ea-105">다수의 조직은 Azure AD Connect와 암호 해시 동기화를 사용하여 온-프레미스 AD DS(Active Directory Domain Services) 포리스트의 계정 집합을 Microsoft 365 구독의 Azure AD 테넌트의 계정 집합과 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="475ea-106">이 문서에서는 테스트 환경에 암호 해시 동기화를 추가하는 Microsoft 365 설명하여 이 구성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="475ea-108">이 테스트 환경을 설정하는 단계는 다음 세 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="475ea-109">1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기</span><span class="sxs-lookup"><span data-stu-id="475ea-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="475ea-110">2단계: 테스트 랩 도메인 만들기 및 등록</span><span class="sxs-lookup"><span data-stu-id="475ea-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="475ea-111">3단계: APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="475ea-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="475ea-112">엔터프라이즈용 테스트 랩 가이드 스택의 Microsoft 365 모든 문서에 대한 시각적 맵을 확인한 다음 엔터프라이즈 테스트 랩 Microsoft 365 스택에 대한 자세한 [설명을 참조하세요.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="475ea-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="475ea-113">1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기</span><span class="sxs-lookup"><span data-stu-id="475ea-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="475ea-114">에 대한 [시뮬레이트된 엔터프라이즈 기본 구성의 Microsoft 365.](simulated-ent-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="475ea-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="475ea-115">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-115">Your resulting configuration looks like this:</span></span>
  
![시뮬레이트된 엔터프라이즈 기본 구성](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="475ea-117">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="475ea-118">Microsoft 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="475ea-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="475ea-119">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network의 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="475ea-120">DC1은 AD DS 도메인에 대한 공용  <.> 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="475ea-121">2단계: 테스트 랩 도메인 만들기 및 등록</span><span class="sxs-lookup"><span data-stu-id="475ea-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="475ea-122">이 단계에서 공용 DNS 도메인을 추가한 다음 구독에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="475ea-123">먼저 공용 DNS 등록 공급자와 함께 현재 도메인 이름을 기반으로 하는 새 공용 DNS 도메인 이름을 만든 다음 구독에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="475ea-124">공용 도메인 에 **testlab.<*사용하는 것이 좋습니다.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="475ea-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="475ea-125">예를 들어 공용 도메인 이름이 **<span>contoso</span>.com이면** 공용 도메인 이름 **<span>testlab</span>.contoso.com.**</span><span class="sxs-lookup"><span data-stu-id="475ea-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="475ea-126">그런 다음 **>** 도메인 등록 <통해 공용 도메인을 Microsoft 365 평가판 또는 유료 구독에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="475ea-127">이 구성은 공용 도메인 도메인의 **testlab.<DNS *레코드를 추가하는 것으로 구성됩니다.* >**</span><span class="sxs-lookup"><span data-stu-id="475ea-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="475ea-128">자세한 내용은 [Add a domain to Microsoft 365.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="475ea-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="475ea-129">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-129">Your resulting configuration looks like this:</span></span>
  
![테스트 랩 도메인 이름 등록](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="475ea-131">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-131">This configuration consists of:</span></span>

- <span data-ttu-id="475ea-132">DNS Microsoft 365 E5 testlab.을 사용하여 평가판 또는 유료 < 등록된 공용 도메인> 구독입니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="475ea-133">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="475ea-134">공용 도메인 <testlab.>  방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="475ea-135">공용 DNS 레코드에서 지원도비니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="475ea-136">Microsoft 365 구독에 등록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="475ea-137">시뮬레이트된 인트라넷의 AD DS 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="475ea-138">3단계: APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="475ea-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="475ea-139">이 단계에서는 APP1에서 Azure AD 커넥트 도구를 설치하고 구성한 다음 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="475ea-140">먼저 APP1에 Azure AD 커넥트 설치하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="475ea-141">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="475ea-142">APP1의 바탕 화면에서 관리자 수준 Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행하여 Internet Explorer 강화 보안을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="475ea-143">작업 표시줄에서 를 **선택하고 Internet Explorer** 로 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="475ea-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="475ea-144">On the Microsoft Azure Active Directory 커넥트 page, select **Download**, and then select **Run**.</span><span class="sxs-lookup"><span data-stu-id="475ea-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="475ea-145">Azure AD 커넥트 시작 페이지에서 **동의를** 선택하고 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="475ea-146">**Express** 설정 익스프레스 설정 **사용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="475ea-147">Azure **AD 커넥트** 페이지에서 사용자 이름에 전역 관리자 계정 이름을 입력하고 **암호에** 암호를 **입력한** 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="475ea-148">AD **커넥트** 페이지의 사용자 이름에 **TESTLAB \\ User1을** 입력하고 **암호에** 암호를 **입력한** 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="475ea-149">구성 **준비 완료 페이지에서** 설치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="475ea-150">구성 **완료 페이지에서** 끝내기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="475ea-151">Internet Explorer에서 Microsoft 365 관리 센터([https://portal.microsoft.com](https://portal.microsoft.com))로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="475ea-152">왼쪽 탐색 창에서 사용자 및 활성 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="475ea-153">**User1** 이라는 계정을 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-153">Note the account named **User1**.</span></span> <span data-ttu-id="475ea-154">이 계정은 TESTLAB AD DS 도메인의 계정이며 디렉터리 동기화가 성공했다는 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="475ea-155">**User1 계정을 선택한** 다음 라이선스 및 **앱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="475ea-156">제품 **라이선스에서** 위치(필요한 경우)를 선택하고 Office 365 **E5** 라이선스를 사용하지 않도록 설정한 다음 Microsoft 365 E5 **라이선스를** 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="475ea-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="475ea-157">페이지 **아래쪽에서** 저장을 선택한 다음 닫기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="475ea-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="475ea-158">다음으로 User1 계정의 도메인 이름 사용자 이름을 **user1@testlab.< > 구독에** 로그인하는 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="475ea-159">APP1에서 로그아웃한 다음 다른 계정을 지정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="475ea-160">사용자 이름과 암호를 입력하라는 메시지가 표시될 때 도메인 **user1@testlab.< >** 사용자1 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="475ea-161">User1으로 성공적으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="475ea-162">User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 전역 관리자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="475ea-163">따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="475ea-164">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-164">Your resulting configuration looks like this:</span></span>

![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="475ea-166">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="475ea-167">Microsoft 365 E5 도메인 TESTLAB.Office 365 E5 평가판 또는 유료 구독을 등록하거나 < 도메인> 합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="475ea-168">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="475ea-169">Azure AD 커넥트 APP1에서 실행되어 TESTLAB AD DS 도메인을 사용자 구독의 Azure AD 테넌트와 Microsoft 365 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="475ea-170">TESTLAB AD DS 도메인의 User1 계정이 Azure AD 테넌트와 동기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="475ea-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="475ea-171">Next step</span></span>

<span data-ttu-id="475ea-172">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="475ea-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="475ea-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="475ea-173">See also</span></span>

[<span data-ttu-id="475ea-174">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="475ea-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="475ea-175">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="475ea-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="475ea-176">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="475ea-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)