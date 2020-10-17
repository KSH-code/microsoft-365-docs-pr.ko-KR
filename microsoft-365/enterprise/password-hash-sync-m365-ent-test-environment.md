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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487461"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="2b94e-103">Microsoft 365 테스트 환경을 위한 암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="2b94e-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="2b94e-104">*이 테스트 랩 가이드는 enterprise 및 Office 365 Enterprise 테스트 환경용 Microsoft 365에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="2b94e-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2b94e-105">다수의 조직은 Azure AD Connect와 암호 해시 동기화를 사용하여 온-프레미스 AD DS(Active Directory Domain Services) 포리스트의 계정 집합을 Microsoft 365 구독의 Azure AD 테넌트의 계정 집합과 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="2b94e-106">이 문서에서는이 구성을 통해 Microsoft 365 테스트 환경에 암호 해시 동기화를 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="2b94e-108">이 테스트 환경에 대 한 설정에는 다음 세 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="2b94e-109">1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기</span><span class="sxs-lookup"><span data-stu-id="2b94e-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="2b94e-110">2단계: 테스트 랩 도메인 만들기 및 등록</span><span class="sxs-lookup"><span data-stu-id="2b94e-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="2b94e-111">3단계: APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="2b94e-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="2b94e-112">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b94e-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="2b94e-113">1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기</span><span class="sxs-lookup"><span data-stu-id="2b94e-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="2b94e-114">[Microsoft 365에 대해 시뮬레이트된 엔터프라이즈 기반 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="2b94e-115">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-115">Your resulting configuration looks like this:</span></span>
  
![시뮬레이트된 엔터프라이즈 기본 구성](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="2b94e-117">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="2b94e-118">Microsoft 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="2b94e-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="2b94e-119">인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 DC1, APP1 및 CLIENT1 가상 머신으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="2b94e-120">DC1은 testlab의 도메인 컨트롤러입니다. *공용 도메인 이름을* <AD DS domain> 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="2b94e-121">2단계: 테스트 랩 도메인 만들기 및 등록</span><span class="sxs-lookup"><span data-stu-id="2b94e-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="2b94e-122">이 단계에서 공용 DNS 도메인을 추가 하 고 구독에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="2b94e-123">먼저 공용 DNS 등록 공급자와 함께 사용 하 여 현재 도메인 이름을 기반으로 하는 새 공용 DNS 도메인 이름을 만든 다음 구독에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="2b94e-124">Testlab 이름을 사용 하는 것이 좋습니다 ( \*\* *공용 도메인* > <합니다.\*\*</span><span class="sxs-lookup"><span data-stu-id="2b94e-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="2b94e-125">예를 들어 공용 도메인 이름이 \*\* <span>contoso</span>.com**인 경우 공용 도메인 이름: \*\* <span>testlab</span>** 를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="2b94e-126">다음으로, testlab을 추가 합니다. 도메인 등록 프로세스를 진행 하 여 Microsoft 365 평가판 또는 유료 구독에 대 한 \*\* *공용 도메인* > 도메인 <합니다.\*\*</span><span class="sxs-lookup"><span data-stu-id="2b94e-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="2b94e-127">이는 testlab에 DNS 레코드를 추가 하는 것으로, \*\* *공용 도메인* > 도메인 <합니다.\*\*</span><span class="sxs-lookup"><span data-stu-id="2b94e-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="2b94e-128">자세한 내용은 [365 Microsoft에 도메인 추가](../admin/setup/add-domain.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b94e-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="2b94e-129">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-129">Your resulting configuration looks like this:</span></span>
  
![테스트 랩 도메인 이름 등록](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="2b94e-131">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-131">This configuration consists of:</span></span>

- <span data-ttu-id="2b94e-132">DNS 도메인 testlab을 사용한 Microsoft 365 E5 평가판 또는 유료 구독 <등록 된> *공용 도메인 이름* 입니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="2b94e-133">인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="2b94e-134">Testlab이 <> 현재 *공용 도메인 이름* 입니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="2b94e-135">공용 DNS 레코드에서 지원도비니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="2b94e-136">Microsoft 365 구독에 등록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="2b94e-137">시뮬레이트된 인트라넷의 AD DS 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="2b94e-138">3단계: APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="2b94e-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="2b94e-139">이 단계에서는 APP1에서 Azure AD Connect 도구를 설치 및 구성 하 고, 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="2b94e-140">먼저 APP1에서 Azure AD Connect를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="2b94e-141">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="2b94e-142">APP1의 바탕 화면에서 관리자 수준 Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행하여 Internet Explorer 강화 보안을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="2b94e-143">작업 표시줄에서 **Internet Explorer** 를 선택 하 고로 이동 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="2b94e-144">Microsoft Azure Active Directory 연결 페이지에서 **다운로드**를 선택 하 고 **실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="2b94e-145">**AZURE AD Connect 시작** 페이지에서 **동의 함**을 선택 하 고 **계속**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="2b94e-146">**빠른 설정** 페이지에서 **빠른 설정 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="2b94e-147">**AZURE AD에 연결** 페이지에서 **사용자 이름** 에 전역 관리자 계정 이름을 입력 하 고 **암호**에 암호를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="2b94e-148">**AD DS에 연결** 페이지에서 **사용자 이름** 에 **testlab \\ User1** 을 입력 하 고 **암호**에 암호를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="2b94e-149">**구성 준비 완료** 페이지에서 **설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="2b94e-150">**구성 완료** 페이지에서 **끝내기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="2b94e-151">Internet Explorer에서 Microsoft 365 관리 센터([https://portal.microsoft.com](https://portal.microsoft.com))로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="2b94e-152">왼쪽 탐색 창에서 **사용자 > 활성 사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="2b94e-153">**User1**이라는 계정을 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-153">Note the account named **User1**.</span></span> <span data-ttu-id="2b94e-154">이 계정은 TESTLAB AD DS 도메인의 계정이며 디렉터리 동기화가 성공했다는 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="2b94e-155">**User1** 계정을 선택한 다음 **라이선스 및 앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="2b94e-156">**제품 라이선스**에서 사용자의 위치를 선택 하 고 (필요한 경우) **Office 365 e5** 라이선스를 사용 하지 않도록 설정한 다음 **Microsoft 365 e5** 라이선스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="2b94e-157">페이지 아래쪽에서 **저장** 을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="2b94e-158">다음으로, user1@testlab 사용 하 여 구독에 로그인 하는 기능을 테스트 \*\*합니다. <사용자의 *도메인 이름* > \*\* user1 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="2b94e-159">APP1에서 로그아웃한 다음 다른 계정을 지정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="2b94e-160">사용자 이름 및 암호를 입력 하 라는 메시지가 표시 되 면 user1@testlab를 지정 하 고 \*\* *도메인 이름* > \*\* 및 user1 암호를 <합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="2b94e-161">User1으로 성공적으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="2b94e-162">User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 전역 관리자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="2b94e-163">따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="2b94e-164">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-164">Your resulting configuration looks like this:</span></span>

![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="2b94e-166">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="2b94e-167">DNS 도메인 TESTLAB을 사용한 Microsoft 365 E5 또는 Office 365 E5 평가판 또는 유료 구독 <등록 된 *도메인 이름*> 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="2b94e-168">인터넷에 연결 된 간소화 된 조직 인트라넷-Azure virtual network의 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 컴퓨터로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="2b94e-169">Azure AD Connect는 APP1에서 실행 되며, 주기적으로 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테 넌 트와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="2b94e-170">TESTLAB AD DS 도메인의 User1 계정이 Azure AD 테넌트와 동기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="2b94e-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2b94e-171">Next step</span></span>

<span data-ttu-id="2b94e-172">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2b94e-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b94e-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b94e-173">See also</span></span>

[<span data-ttu-id="2b94e-174">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="2b94e-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2b94e-175">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="2b94e-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2b94e-176">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b94e-176">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
