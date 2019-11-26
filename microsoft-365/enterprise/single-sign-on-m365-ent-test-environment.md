---
title: Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: '요약: Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On을 구성하고 테스트합니다.'
ms.openlocfilehash: f263ab507e392c1172d28b5d6ef111d8d9f40682
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202239"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="12a72-103">Microsoft 365 테스트 환경을 위한 Azure AD Seamless Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="12a72-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="12a72-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise와 Office 365 Enterprise 테스트 환경 모두에서 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="12a72-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="12a72-p101">Azure AD Seamless SSO(Single Sign-On)는 조직 네트워크에 연결된 PC 또는 장치에서 사용하는 사용자를 자동으로 로그인합니다. Azure AD Seamless SSO는 추가 온-프레미스 구성 요소를 요구하지 않고 클라우드 기반 응용 프로그램에 쉽게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="12a72-107">이 문서에서는 Azure AD Seamless SSO에 대해 Microsoft 365 테스트 환경을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="12a72-108">이러한 기능을 설정하는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="12a72-109">암호 해시 동기화로 시뮬레이트된 Microsoft 365 엔터프라이즈 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="12a72-110">APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="12a72-112">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="12a72-113">1단계: Microsoft 365 테스트 환경을 위한 암호 해시 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="12a72-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="12a72-p102">[Microsoft 365에 대한 암호 해시 동기화](password-hash-sync-m365-ent-test-environment.md) 지침을 따릅니다. 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![암호 해시 동기화 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="12a72-117">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="12a72-118">Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독</span><span class="sxs-lookup"><span data-stu-id="12a72-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="12a72-119">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="12a72-120">Azure AD Connect는 테스트 랩 AD DS(Active Directory 도메인 서비스) 도메인을 Microsoft 365 또는 Office 365 구독의 Azure AD 테넌트와 주기적으로 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="12a72-121">2단계: APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect 구성</span><span class="sxs-lookup"><span data-stu-id="12a72-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="12a72-122">이 단계에서는 APP1에서 Azure AD Seamless SSO에 대한 Azure AD Connect를 구성한 다음, 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="12a72-123">APP1에서 Azure AD Connect 구성</span><span class="sxs-lookup"><span data-stu-id="12a72-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="12a72-124">[Azure Portal](https://portal.azure.com)에서 전역 관리자 계정으로 로그인한 후 TESTLAB\User1 계정을 사용하여 APP1에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="12a72-125">APP1의 데스크톱에서 Azure AD Connect를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="12a72-126">**시작** 페이지에서 **구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="12a72-127">**추가 작업** 페이지에서 **사용자 로그인 변경**을 클릭한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="12a72-128">**Azure AD에 연결** 페이지에서 전역 관리자 계정 자격 증명을 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="12a72-129">**사용자 로그인** 페이지에서 **Single Sign-On 사용**을 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="12a72-130">**Single Sign-On 사용** 페이지에서 **자격 증명 입력**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="12a72-p103">**Windows 보안** 대화 상자에 **user1** 및 user1 계정의 암호를 입력하고 **확인**을 클릭합니다. **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="12a72-133">**구성 준비 완료** 페이지에서 **구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="12a72-134">**구성 완료** 페이지에서 **끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="12a72-p104">Azure Portal의 왼쪽 창에서 **Azure Active Directory > Azure AD Connect**를 클릭합니다. **Seamless Single Sign-On** 기능이 **사용**으로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="12a72-137">다음으로, user1 계정의 <strong>user1@testlab.</strong>\<사용자의 공용 도메인> 사용자 이름으로 구독에 로그인하는 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-137">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="12a72-138">APP1의 Internet Explorer에서 설정 아이콘을 클릭하고 **인터넷 옵션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="12a72-139">**인터넷 옵션**에서 **보안** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="12a72-140">**로컬 인트라넷**을 클릭하고 **사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="12a72-141">**로컬 인트라넷**에서 **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="12a72-142">**영역에 이 웹 사이트 추가**에서 **https<span>://</span>autologon.microsoftazuread sso.com**을 입력하고 **추가 > 닫기 > 확인 > 확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="12a72-143">로그아웃했다가 다른 계정을 지정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-143">Sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="12a72-144">로그인하라는 메시지가 표시되면 <strong>user1@testlab.</strong>\<공용 도메인> 이름을 지정한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="12a72-145">암호를 묻는 창이 뜨지 않고 User1로 성공적으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="12a72-146">이는 Azure AD Seamless SSO가 제대로 작동하고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="12a72-147">User1에 TESTLAB AD DS 도메인에 대한 도메인 관리자 권한이 있더라도 Azure AD 전역 관리자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD and Office 365.</span></span> <span data-ttu-id="12a72-148">따라서 **관리자** 아이콘이 옵션으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="12a72-149">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-149">Here is your resulting configuration:</span></span>

![통과 인증 테스트 환경으로 시뮬레이트된 엔터프라이즈](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="12a72-151">이 구성은 다음으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-151">This configuration consists of:</span></span>

- <span data-ttu-id="12a72-152">Microsoft 365 E5, Office 365 E5 평가판 또는 유료 구독(DNS 도메인 Test Lab 포함).\<도메인 이름> 등록됨.</span><span class="sxs-lookup"><span data-stu-id="12a72-152">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="12a72-153">인터넷에 연결된 간소화된 조직 인트라넷: Azure Virtual Network 서브넷에 있는 DC1, APP1 및 CLIENT1 가상 머신으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="12a72-154">Azure AD Connect는 Microsoft 365 또는 Office 365 구독의 Azure AD 테넌트에 있는 계정 및 그룹 목록을 테스트 랩 AD DS 도메인과 동기화하기 위해 APP1에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="12a72-155">Azure AD Seamless SSO는 시뮬레이트된 인트라넷의 컴퓨터가 사용자 계정 암호를 지정하지 않아도 Microsoft 365 클라우드 리소스에 로그온할 수 있도록 하기 위해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="12a72-156">프로덕션 환경에서 Azure AD Seamless SSO를 구성하기 위한 정보 및 단계에 대해서는 ID 단계의 [사용자 로그인 간소화](identity-secure-your-passwords.md#identity-sso) 단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12a72-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="12a72-157">다음 단계</span><span class="sxs-lookup"><span data-stu-id="12a72-157">Next step</span></span>

<span data-ttu-id="12a72-158">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="12a72-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="12a72-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12a72-159">See also</span></span>

[<span data-ttu-id="12a72-160">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="12a72-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="12a72-161">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="12a72-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="12a72-162">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="12a72-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


