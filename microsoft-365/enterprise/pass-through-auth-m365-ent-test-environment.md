---
title: Microsoft 365 테스트 환경을 위한 통과 인증
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 통과 인증을 구성합니다.'
ms.openlocfilehash: b92700d28a758842d3754bb2b359181b9ee59d2e
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553357"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a2e4a-103">Microsoft 365 테스트 환경을 위한 통과 인증</span><span class="sxs-lookup"><span data-stu-id="a2e4a-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a2e4a-104">Microsoft 클라우드 기반 서비스 및 응용 프로그램에 대한 인증을 위해 AD DS (Active Directory 도메인 서비스) 인프라를 직접 사용하려는 조직은 통과 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-104">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="a2e4a-105">이 문서에서는 통과 인증에 대해 Microsoft 365 테스트 환경을 구성하여 다음과 같은 결과를 얻는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-105">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="a2e4a-107">이 테스트 환경의 2가지 주요 설정 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-107">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="a2e4a-108">암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="a2e4a-109">통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-109">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a2e4a-111">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a2e4a-112">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="a2e4a-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a2e4a-p102">[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="a2e4a-116">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="a2e4a-117">Office 365 E5 및 EMS E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="a2e4a-117">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a2e4a-118">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="a2e4a-119">Azure AD Connect는 테스트 랩 AD DS 도메인을 Office 365 및 EMS E5 구독의 Azure AD 테넌트와 주기적으로 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="a2e4a-120">2단계: 통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-120">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="a2e4a-121">이 단계에서는 통과 인증을 사용하도록 APP1에서 Azure AD Connect를 구성한 다음 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-121">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="a2e4a-122">APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="a2e4a-122">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="a2e4a-123">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="a2e4a-124">APP1의 데스크톱에서 Azure AD Connect를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="a2e4a-125">**시작** 페이지에서 **구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-125">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="a2e4a-126">추가 작업 페이지에서 **사용자 로그인 변경**을 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-126">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="a2e4a-127">**Azure AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="a2e4a-128">**사용자 로그인** 페이지에서 **통과 인증**를 클릭한 다음, **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-128">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="a2e4a-129">**구성 준비 완료** 페이지에서 **구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-129">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="a2e4a-130">**구성 완료** 페이지에서 **끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-130">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="a2e4a-p104">Azure Portal의 왼쪽 창에서 **Azure Active Directory > Azure AD Connect**를 클릭합니다. **통과 인증** 기능이 **사용**으로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="a2e4a-p105">**통과 인증**을 클릭하세요. **통과 인증** 창에는 인증 에이전트가 설치된 서버가 나열됩니다. 목록에 APP1이 표시되었는지 확인해야 합니다. 그 다음 **통과 인증** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="a2e4a-137">다음으로, user1 계정의 <strong>user1@testlab.</strong>\<사용자의 공용 도메인> 사용자 이름으로 Office 365 구독에 로그인하는 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-137">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="a2e4a-138">APP1에서 Office 365로부터 로그아웃했다가 다른 계정을 지정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-138">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="a2e4a-139">사용자 이름 및 암호를 지정하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<사용자의 공용 도메인> 및 User1 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-139">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="a2e4a-140">User1으로 성공적으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-140">You should successfully sign in as User1.</span></span>

<span data-ttu-id="a2e4a-141">User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 Office 365 전역 관리자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-141">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not an Office 365 global administrator.</span></span> <span data-ttu-id="a2e4a-142">따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-142">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="a2e4a-143">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-143">Here is your resulting configuration:</span></span>

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="a2e4a-145">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-145">This configuration consists of:</span></span>

- <span data-ttu-id="a2e4a-146">Office 365 E5 및 EMS E5 평가판 또는 DNS 도메인 TESTLAB.\<도메인 이름>이 등록된 유료 구독.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-146">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="a2e4a-p108">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 인증 에이전트는 APP1에서 실행되어 Office 365 및 EMS E5 구독의 Azure AD 테넌트로부터의 통과 인증 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="next-step"></a><span data-ttu-id="a2e4a-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2e4a-149">Next step</span></span>

<span data-ttu-id="a2e4a-150">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a2e4a-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2e4a-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2e4a-151">See also</span></span>

[<span data-ttu-id="a2e4a-152">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="a2e4a-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a2e4a-153">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="a2e4a-153">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a2e4a-154">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="a2e4a-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


