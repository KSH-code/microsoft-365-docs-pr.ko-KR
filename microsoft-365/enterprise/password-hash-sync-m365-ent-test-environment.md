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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 및 로그인을 구성하고 보여 줍니다.'
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819391"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ccf49-103">Microsoft 365 테스트 환경을 위한 암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="ccf49-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ccf49-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise와 Office 365 Enterprise 테스트 환경 모두에서 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="ccf49-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ccf49-105">다수의 조직은 Azure AD Connect와 암호 해시 동기화를 사용하여 온-프레미스 AD DS(Active Directory Domain Services) 포리스트의 계정 집합을 Microsoft 365 구독의 Azure AD 테넌트의 계정 집합과 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="ccf49-106">이 문서에서는 Microsoft 365 테스트 환경에 암호 해시 동기화를 추가하여 다음과 같은 구성을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="ccf49-108">이 테스트 환경의 2가지 주요 설정 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="ccf49-109">Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="ccf49-110">APP1에 Azure AD Connect를 설치 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="ccf49-111">Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인하려면 [Microsoft 365 Enterprise 테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="ccf49-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="ccf49-112">1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기</span><span class="sxs-lookup"><span data-stu-id="ccf49-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="ccf49-p102">[Microsoft 365의 시뮬레이이트된 엔터프라이즈 기반 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다. 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![시뮬레이트된 엔터프라이즈 기본 구성](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="ccf49-116">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="ccf49-117">Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독.</span><span class="sxs-lookup"><span data-stu-id="ccf49-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="ccf49-118">인터넷에 연결된 간소화된 조직 인트라넷: Azure 가상 네트워크에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="ccf49-119">DC1은 testlab.\<your public domain name> AD DS 도메인의</span><span class="sxs-lookup"><span data-stu-id="ccf49-119">DC1 is a domain controller for the testlab.\<your public domain name></span></span> <span data-ttu-id="ccf49-120">도메인 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-120">AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="ccf49-121">2단계: 테스트 랩 도메인 만들기 및 등록</span><span class="sxs-lookup"><span data-stu-id="ccf49-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="ccf49-122">이 단계에서 공용 DNS 도메인을 추가하고 구독에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-122">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="ccf49-123">먼저 공용 DNS 등록 공급자와 협력하여 현재 도메인 이름을 기반으로 하는 새 공용 DNS 도메인 이름을 만든 다음 구독에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-123">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="ccf49-124">**testlab.**\<your public domain> 이름을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-124">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="ccf49-125">예를 들어, 공용 도메인 이름이 **<span>contoso</span>.com**인 경우 공용 도메인 이름 **<span>testlab</span>.contoso.com**을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="ccf49-126">그런 다음 도메인 등록 프로세스를 통해 **테스트랩**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="ccf49-126">Next, you add the **testlab.**\<your public domain></span></span> <span data-ttu-id="ccf49-127">도메인을 Microsoft 365 또는 Office 365 평가판 또는 유료 구독에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-127">domain to your Microsoft 365 or Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="ccf49-128">이 프로세스는 추가 DNS 레코드를 **testlab.**\<your public domain> 도메인에 추가하는 것으로</span><span class="sxs-lookup"><span data-stu-id="ccf49-128">This consists of adding additional DNS records to the **testlab.**\<your public domain></span></span> <span data-ttu-id="ccf49-129">구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-129">domain.</span></span> <span data-ttu-id="ccf49-130">자세한 내용은 [Office 365에 도메인 추가](https://docs.microsoft.com/office365/admin/setup/add-domain)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccf49-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span></span> 

<span data-ttu-id="ccf49-131">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-131">Here is your resulting configuration.</span></span>
  
![테스트 랩 도메인 이름 등록](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="ccf49-133">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-133">This configuration consists of:</span></span>

- <span data-ttu-id="ccf49-134">DNS 도메인 testlab.\<your public domain name>이 등록된 Microsoft 365 E5 또는 Office 365 E5 평가판 또는 </span><span class="sxs-lookup"><span data-stu-id="ccf49-134">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name></span></span> <span data-ttu-id="ccf49-135">유료 구독.</span><span class="sxs-lookup"><span data-stu-id="ccf49-135">registered.</span></span>
- <span data-ttu-id="ccf49-136">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-136">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="ccf49-137">testlab.\<your public domain name>은</span><span class="sxs-lookup"><span data-stu-id="ccf49-137">Notice how the testlab.\<your public domain name></span></span> <span data-ttu-id="ccf49-138">현재:</span><span class="sxs-lookup"><span data-stu-id="ccf49-138">is now:</span></span>

- <span data-ttu-id="ccf49-139">공용 DNS 레코드에서 지원도비니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-139">Supported by public DNS records.</span></span>
- <span data-ttu-id="ccf49-140">Microsoft 365 구독에 등록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-140">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="ccf49-141">시뮬레이트된 인트라넷의 AD DS 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-141">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="ccf49-142">3단계: APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="ccf49-142">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="ccf49-143">이 단계에서는 APP1에서 Azure AD Connect 도구를 설치 및 구성한 후 잘 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-143">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="ccf49-144">먼저 APP1에 Azure AD Connect 설치 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-144">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="ccf49-145">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-145">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="ccf49-146">APP1의 바탕 화면에서 관리자 수준 Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행하여 Internet Explorer 강화 보안을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-146">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="ccf49-147">작업 표시줄에서 **Internet Explorer**를 클릭하고 [https://aka.ms/aadconnect](https://aka.ms/aadconnect)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-147">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="ccf49-148">Microsoft Azure Active Directory Connect 페이지에서 **다운로드**를 클릭하고 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-148">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="ccf49-149">**Azure AD Connect 시작** 페이지에서 **동의**를 클릭하고 **계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-149">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="ccf49-150">**기본 설정** 페이지에서 **기본 설정 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-150">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="ccf49-151">**Azure AD에 연결** 페이지에서 **사용자 이름**에 전역 관리자 계정 이름을 입력하고 **암호**에 해당 암호를 입력한 후 \*\*다음 \*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-151">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ccf49-152">**AD DS에 연결** 페이지에서 **사용자 이름**에 **TESTLAB\\User1**을 입력하고 **암호**에 암호를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-152">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="ccf49-153">**구성 준비 완료** 페이지에서 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-153">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="ccf49-154">**구성 완료** 페이지에서 **끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-154">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="ccf49-155">Internet Explorer에서 Microsoft 365 관리 센터([https://portal.microsoft.com](https://portal.microsoft.com))로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-155">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="ccf49-156">왼쪽 탐색에서 **사용자 > 활성화된 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-156">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="ccf49-157">**User1**이라는 계정을 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-157">Note the account named **User1**.</span></span> <span data-ttu-id="ccf49-158">이 계정은 TESTLAB AD DS 도메인의 계정이며 디렉터리 동기화가 성공했다는 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-158">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="ccf49-159">**User1** 계정을 클릭한 다음 **라이선스 및 앱**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-159">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="ccf49-160">**제품 라이선스**에서 위치를 선택하고 (필요한 경우) **Office 365 E5** 라이선스를 해제 하고 **Microsoft 365 E5** 라이선스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-160">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="ccf49-161">페이지 아래쪽에서 **저장**을 클릭하고 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-161">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="ccf49-162">다음으로, User1 계정의 <strong>user1@testlab.</strong>\<your domain name> 사용자 이름으로 구독에 로그인하는</span><span class="sxs-lookup"><span data-stu-id="ccf49-162">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="ccf49-163">기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-163">user name of the User1 account.</span></span>

1. <span data-ttu-id="ccf49-164">APP1에서 로그아웃한 다음 다른 계정을 지정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-164">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="ccf49-165">사용자 이름 및 암호를 입력하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="ccf49-165">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="ccf49-166">및 User1 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-166">and the User1 password.</span></span> <span data-ttu-id="ccf49-167">User1으로 성공적으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-167">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="ccf49-168">User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 전역 관리자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-168">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="ccf49-169">따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-169">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="ccf49-170">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-170">Here is your resulting configuration.</span></span>

![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="ccf49-172">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-172">This configuration consists of:</span></span> 
  
- <span data-ttu-id="ccf49-173">DNS 도메인 TESTLAB.\<your domain name>이 등록된 Microsoft 365 E5 또는 Office 365 E5 평가판 또는 </span><span class="sxs-lookup"><span data-stu-id="ccf49-173">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="ccf49-174">유료 구독.</span><span class="sxs-lookup"><span data-stu-id="ccf49-174">registered.</span></span>
- <span data-ttu-id="ccf49-175">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-175">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="ccf49-176">Azure AD Connect는 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 주기적으로 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-176">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="ccf49-177">TESTLAB AD DS 도메인의 User1 계정이 Azure AD 테넌트와 동기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-177">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="ccf49-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ccf49-178">Next step</span></span>

<span data-ttu-id="ccf49-179">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ccf49-179">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccf49-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccf49-180">See also</span></span>

[<span data-ttu-id="ccf49-181">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="ccf49-181">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ccf49-182">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="ccf49-182">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ccf49-183">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="ccf49-183">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


