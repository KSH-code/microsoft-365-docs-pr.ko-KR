---
title: Microsoft 365 테스트 환경을 위한 암호 해시 동기화
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 및 로그인을 구성하고 보여 줍니다.'
ms.openlocfilehash: 3cee2b69ce34647627cb2b72f9e0f59a6fba17e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870293"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4f2a7-103">Microsoft 365 테스트 환경을 위한 암호 해시 동기화</span><span class="sxs-lookup"><span data-stu-id="4f2a7-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4f2a7-p101">많은 조직에서는 Azure AD Connect 및 암호 해시 동기화를 사용하여 온-프레미스 Windows Server AD(Active Directory) 포리스트의 계정 집합을 Office 365 및 EMS E5 구독의 Azure AD 테넌트에 있는 계정 집합과 동기화합니다. 이 문서에서는 암호 해시 동기화를 Microsoft 365 테스트 환경에 추가하여 다음과 같이 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p101">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Windows Server Active Directory (AD) forest to the set of accounts in the Azure AD tenant of their Office 365 and EMS E5 subscriptions. This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="4f2a7-107">이 테스트 환경의 2가지 주요 설정 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-107">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="4f2a7-108">Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-108">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="4f2a7-109">APP1에 Azure AD Connect를 설치 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-109">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="4f2a7-110">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="4f2a7-111">1단계: Microsoft 365 시뮬레이트된 엔터프라이즈 테스트 환경을 만들기</span><span class="sxs-lookup"><span data-stu-id="4f2a7-111">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="4f2a7-p102">[Microsoft 365의 시뮬레이이트된 엔터프라이즈 기반 구성](simulated-ent-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다. 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![시뮬레이트된 엔터프라이즈 기본 구성](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="4f2a7-115">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="4f2a7-116">Office 365 E5 및 EMS E5 평가판 또는 영구 구독</span><span class="sxs-lookup"><span data-stu-id="4f2a7-116">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="4f2a7-p103">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. DC1은 testlab.\<공용 도메인 이름> Windows Server AD 도메인에 대한 도메인 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network. DC1 is a domain controller for the testlab.\<your public domain name> Windows Server AD domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="4f2a7-119">2단계: 테스트 랩 도메인 만들기 및 등록</span><span class="sxs-lookup"><span data-stu-id="4f2a7-119">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="4f2a7-120">이 단계에서 공용 DNS 도메인을 추가하고 구독에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-120">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="4f2a7-p104">먼저, 공용 DNS 등록 공급자와 협력하여 공용 DNS 등록 공급자 현재 도메인 이름에 따라 새 공용 DNS 도메인 이름을 만든 후 Office 365 구독에 추가합니다. 이름 **testlab.**\<공용 도메인>을 사용하는 것이 좋습니다. 예를 들어, 공용 도메인 이름이 <span>**contoso</span>.com**이면 공용 도메인 이름 **<span>testlab</span>.contoso.com**을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your Office 365 subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is <span>**contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="4f2a7-p105">다음으로, 도메인 등록 프로세스를 진행하여 **testlab.**\<공용 도메인> 도메인을 Office 365 평가판 또는 영구 구독에 추가합니다. 이 과정에서 **testlab.**\<공용 도메인> 도메인에 DNS 레코드를 더 추가딥니다. 자세한 내용은 [Office 365에 사용자 및 도메인 추가](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p105">Next, you add the **testlab.**\<your public domain> domain to your Office 365 trial or permanent subscription by going through the domain registration process. This consists of adding additional DNS records to the **testlab.**\<your public domain> domain. For more information, see [Add users and domain to Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span> 

<span data-ttu-id="4f2a7-127">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-127">Here is your resulting configuration.</span></span>
  
![테스트 랩 도메인 이름 등록](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="4f2a7-129">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-129">This configuration consists of:</span></span>

- <span data-ttu-id="4f2a7-130">Office 365 E5 및 EMS E5 평가판 또는 DNS 도메인 testlab.\<공용 도메인 이름>이 등록된 영구 구독</span><span class="sxs-lookup"><span data-stu-id="4f2a7-130">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="4f2a7-131">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-131">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="4f2a7-132">testlab.\<공용 도메인 이름>에 대해 현재 다음 작업이 어떻게 진행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-132">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="4f2a7-133">공용 DNS 레코드에서 지원도비니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-133">Supported by public DNS records.</span></span>
- <span data-ttu-id="4f2a7-134">Office 365 및 EMS 구독에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-134">Registered in your Office 365 and EMS subscriptions.</span></span>
- <span data-ttu-id="4f2a7-135">시뮬레이트된 인트라넷의 Windows Server AD 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-135">The Windows Server AD domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="4f2a7-136">3단계: APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="4f2a7-136">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="4f2a7-137">이 단계에서는 APP1에서 Azure AD Connect 도구를 설치 및 구성한 후 잘 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-137">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="4f2a7-138">먼저 APP1에 Azure AD Connect 설치 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-138">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="4f2a7-139">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-139">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="4f2a7-140">APP1의 바탕 화면에서 관리자 수준 Windows PowerShell 명령 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-140">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="4f2a7-141">작업 표시줄에서 **Internet Explorer**를 클릭하고 [https://aka.ms/aadconnect](https://aka.ms/aadconnect)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-141">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="4f2a7-142">Microsoft Azure Active Directory Connect 페이지에서 **다운로드**를 클릭하고 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-142">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="4f2a7-143">**Azure AD Connect 시작** 페이지에서 **동의**를 클릭하고 **계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-143">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="4f2a7-144">**기본 설정** 페이지에서 **기본 설정 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-144">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="4f2a7-145">**Azure AD에 연결** 페이지에서 **사용자 이름**에 Office 365 전역 관리자 계정 이름을 입력하고 **암호**에 해당 암호를 입력한 후 \*\*다음 \*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-145">On the **Connect to Azure AD** page, type your Office 365 global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4f2a7-146">**AD DS에 연결** 페이지에서 **사용자 이름**에 **TESTLAB\\User1**을 입력하고 **암호**에 암호를 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-146">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="4f2a7-147">**구성 준비 완료** 페이지에서 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-147">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="4f2a7-148">**구성 완료** 페이지에서 **끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-148">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="4f2a7-149">Internet Explorer에서 Office 365 포털로 이동합니다([https://portal.office.com](https://portal.office.com)).</span><span class="sxs-lookup"><span data-stu-id="4f2a7-149">In Internet Explorer, go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)).</span></span>
    
12. <span data-ttu-id="4f2a7-150">기본 포털 페이지에서 **관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-150">From the main portal page, click **Admin**.</span></span>
    
13. <span data-ttu-id="4f2a7-151">왼쪽 탐색에서 **사용자 > 활성화된 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-151">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="4f2a7-p106">**User1** 계정을 확인합니다. 이 계정은 TESTLAB Windows Server AD 도메인에서 가져온 것이며 디렉터리 동기화가 진행되었다는 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p106">Note the account named **User1**. This account is from the TESTLAB Windows Server AD domain and is proof that directory synchronization has worked.</span></span>
    
14. <span data-ttu-id="4f2a7-p107">**User1** 계정을 클릭합니다. 제품 라이선스에 대해 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p107">Click the **User1** account. For product licenses, click **Edit**.</span></span>
    
15. <span data-ttu-id="4f2a7-p108">**제품 라이선스**에서 국가를 선택하고 **Office 365 Enterprise E5**에 대해 **해제** 컨트롤을 클릭합니다(**설정**으로 전환됨). **Enterprise Mobility + Security E5** 라이선스에 대해 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p108">In **Product licenses**, select your scountry, and then click the **Off** control for **Office 365 Enterprise E5** (switching it to **On**). Do the same for the **Enterprise Mobility + Security E5** license.</span></span> 

16. <span data-ttu-id="4f2a7-158">페이지 아래쪽에서 **저장**을 클릭하고 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-158">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="4f2a7-159">다음으로, user1 계정의 <strong>user1@testlab.</strong>\<사용자의 도메인 이름> 사용자 이름으로 Office 365 구독에 로그인하는 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-159">Next, you test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="4f2a7-160">APP1에서 Office 365로부터 로그아웃했다가 다른 계정을 지정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-160">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="4f2a7-p109">사용자 이름 및 암호를 지정하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<사용자의 도메인 이름> 및 User1 암호를 입력합니다. User1으로 잘 로그인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p109">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="4f2a7-p110">User1에 TESTLAB Windows Server AD 도메인에 대한 도메인 관리자 권한이 있더라도 Office 365 전역 관리자는 아닙니다. 따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p110">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="4f2a7-165">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-165">Here is your resulting configuration.</span></span>

![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="4f2a7-167">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-167">This configuration consists of:</span></span> 
  
- <span data-ttu-id="4f2a7-168">Office 365 E5 및 EMS E5 평가판 또는 DNS 도메인 TESTLAB.\<도메인 이름>이 등록된 영구 구독</span><span class="sxs-lookup"><span data-stu-id="4f2a7-168">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="4f2a7-p111">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. Azure AD Connect는 APP1에서 실행되며 30분 간격으로 TESTLAB Windows Server AD 도메인을 Office 365 및 EMS E5 구독의 Azure AD 테넌트와 정기적으로 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-p111">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>
- <span data-ttu-id="4f2a7-171">TESTLAB Windows Server AD 도메인의 User1 계정이 Azure AD 테넌트와 동기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-171">The User1 account in the TESTLAB  Windows Server AD domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="4f2a7-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4f2a7-172">Next step</span></span>

<span data-ttu-id="4f2a7-173">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4f2a7-173">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f2a7-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f2a7-174">See also</span></span>

[<span data-ttu-id="4f2a7-175">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="4f2a7-175">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4f2a7-176">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="4f2a7-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4f2a7-177">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="4f2a7-177">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


