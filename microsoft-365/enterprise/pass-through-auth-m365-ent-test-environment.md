---
title: Microsoft 365 테스트 환경을 위한 통과 인증
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
ms.assetid: ''
description: '요약: Microsoft 365 테스트 환경을 위한 통과 인증을 구성합니다.'
ms.openlocfilehash: cdbb6927fb8ca0001e3089c7169ce9046208e8f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921531"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7174d-103">Microsoft 365 테스트 환경을 위한 통과 인증</span><span class="sxs-lookup"><span data-stu-id="7174d-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7174d-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 및 Office 365 Enterprise 테스트 환경에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="7174d-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7174d-105">Microsoft 클라우드 기반 서비스 및 응용 프로그램에 대한 인증을 위해 AD DS (Active Directory 도메인 서비스) 인프라를 직접 사용하려는 조직은 통과 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="7174d-106">이 문서에서는 통과 인증에 대해 Microsoft 365 테스트 환경을 구성하여 다음과 같은 결과를 얻는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="7174d-108">이 테스트 환경의 2가지 주요 설정 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="7174d-109">암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="7174d-110">통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7174d-112">[여기](../downloads/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-112">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7174d-113">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="7174d-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7174d-p102">[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="7174d-117">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="7174d-118">Microsoft 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="7174d-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="7174d-119">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="7174d-120">Azure AD Connect는 TESTLAB AD DS 도메인을 Microsoft 365 구독의 Azure AD 테넌트와 주기적으로 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="7174d-121">2단계: 통과 인증을 위해 APP1에서 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="7174d-122">이 단계에서는 통과 인증을 사용하도록 APP1에서 Azure AD Connect를 구성한 다음 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="7174d-123">APP1에 Azure AD Connect 설치</span><span class="sxs-lookup"><span data-stu-id="7174d-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="7174d-124">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="7174d-125">APP1의 데스크톱에서 Azure AD Connect를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="7174d-126">**시작** 페이지에서 **구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="7174d-127">추가 작업 페이지에서 **사용자 로그인 변경** 을 클릭한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="7174d-128">**Azure AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="7174d-129">**사용자 로그인** 페이지에서 **통과 인증** 를 클릭한 다음, **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="7174d-130">**구성 준비 완료** 페이지에서 **구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="7174d-131">**구성 완료** 페이지에서 **끝내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="7174d-p104">Azure Portal의 왼쪽 창에서 **Azure Active Directory > Azure AD Connect** 를 클릭합니다. **통과 인증** 기능이 **사용** 으로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="7174d-p105">**통과 인증** 을 클릭하세요. **통과 인증** 창에는 인증 에이전트가 설치된 서버가 나열됩니다. 목록에 APP1이 표시되었는지 확인해야 합니다. 그 다음 **통과 인증** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="7174d-138">다음으로, 구독에 로그인하는 기능을 테스트하고 구독을 <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="7174d-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="7174d-139">기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="7174d-140">APP1에서 로그아웃한 다음 다른 계정을 지정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="7174d-141">사용자 이름 및 암호를 입력하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="7174d-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="7174d-142">및 User1 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-142">and the User1 password.</span></span> <span data-ttu-id="7174d-143">User1으로 성공적으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="7174d-144">User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 전역 관리자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="7174d-145">따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="7174d-146">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-146">Here is your resulting configuration:</span></span>

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="7174d-148">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-148">This configuration consists of:</span></span>

- <span data-ttu-id="7174d-149">DNS 도메인 testlab이 있는 Microsoft 365 E5 평가판 또는 유료 구독\<your domain name></span><span class="sxs-lookup"><span data-stu-id="7174d-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="7174d-150">유료 구독.</span><span class="sxs-lookup"><span data-stu-id="7174d-150">registered.</span></span>
- <span data-ttu-id="7174d-p110">인터넷에 연결된 간소화된 조직 인트라넷으로, Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다. 인증 에이전트는 APP1에서 실행되어 Microsoft 365 구독의 Azure AD 테넌트의 통과 인증 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-p110">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="7174d-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7174d-153">Next step</span></span>

<span data-ttu-id="7174d-154">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7174d-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7174d-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7174d-155">See also</span></span>

[<span data-ttu-id="7174d-156">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="7174d-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7174d-157">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="7174d-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7174d-158">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="7174d-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)