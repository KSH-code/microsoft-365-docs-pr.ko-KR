---
title: 간단한 기본 구성
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 이 테스트 랩 가이드를 사용하여 Microsoft 365 Enterprise 테스트를 위한 간단한 테스트 환경을 만듭니다.
ms.openlocfilehash: 7a4800d374416a1e197536bc1a867d3fbc4b1243
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818756"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="00c0c-103">간단한 기본 구성</span><span class="sxs-lookup"><span data-stu-id="00c0c-103">The lightweight base configuration</span></span>

<span data-ttu-id="00c0c-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise와 Office 365 Enterprise 테스트 환경 모두에서 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="00c0c-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="00c0c-105">이 문서에서는 Microsoft 365 E5 구독 및 Windows 10 Enterprise를 실행하는 컴퓨터에서 간소화된 환경을 만드는 방법에 대한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![간단한 Microsoft 365 Enterprise 테스트 환경](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="00c0c-107">결과로 나타난 환경을 사용하여 [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)의 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="00c0c-109">Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인하려면 [Microsoft 365 Enterprise 테스트 랩 가이드 스택](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="00c0c-109">Click [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="00c0c-110">1단계: Office 365 E5 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="00c0c-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="00c0c-111">Office 365 E5 평가판 구독으로 시작하여 Microsoft 365 E5 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="00c0c-112">Office 365 E5 평가판 구독을 시작하려면 먼저 가상의 회사 이름 및 새 Microsoft 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="00c0c-113">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required.</span><span class="sxs-lookup"><span data-stu-id="00c0c-113">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required.</span></span> <span data-ttu-id="00c0c-114">Record your fictitious company name here:</span><span class="sxs-lookup"><span data-stu-id="00c0c-114">Record your fictitious company name here:</span></span> ![선](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="00c0c-116">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address.</span><span class="sxs-lookup"><span data-stu-id="00c0c-116">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address.</span></span> <span data-ttu-id="00c0c-117">You will use this account to sign up for Office 365.</span><span class="sxs-lookup"><span data-stu-id="00c0c-117">You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="00c0c-118">여기에 새 계정의 이름과 성을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-118">Record the first and last name of your new account here:</span></span> ![선](../media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="00c0c-120">여기서 새 전자 메일 계정 주소를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-120">Record the new email account address here:</span></span> ![선](../media/Common-Images/TableLine.png)<span data-ttu-id="00c0c-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="00c0c-122">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="00c0c-123">Office 365 E5 평가판 구독 등록</span><span class="sxs-lookup"><span data-stu-id="00c0c-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="00c0c-124">컴퓨터에서 인터넷 브라우저를 열고 [https://aka.ms/e5trial](https://aka.ms/e5trial)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="00c0c-125">**Office 365 E5를 선택해 주셔서 감사합니다** 페이지에서 1단계의 새 이메일 계정 주소를 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="00c0c-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="00c0c-126">추적 구독 프로세스의 2단계에서 요청된 정보를 입력한 다음 확인을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="00c0c-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="00c0c-127">3단계에서 조직 이름과 구독의 글로벌 관리자가 될 계정 이름을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="00c0c-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="00c0c-128">4단계에서 여기에 로그인 페이지를 기록합니다(선택 후 복사).</span><span class="sxs-lookup"><span data-stu-id="00c0c-128">For step 4, record the sign-in page here (select and copy):</span></span> ![Line](../media/Common-Images/TableLine.png) 
6. <span data-ttu-id="00c0c-130">여기에 사용자 ID를 기록합니다. ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="00c0c-130">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="00c0c-131">입력한 암호를 안전한 위치에 기록해둡니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="00c0c-132">이 값은 **전역 관리자 이름**으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-132">This value will be referred to as the **global administrator name**.</span></span>
8. <span data-ttu-id="00c0c-133">**설정으로 이동**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="00c0c-134">Office 365 E5 설정에서 **전자 메일 및 로그인에 대해 *조직*.onmicrosoft.com 계속 사용**을 클릭한 다음 **종료 및 나중에 계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="00c0c-135">Microsoft 365 관리 센터가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="00c0c-136">우리는 사용자의 Office 365의 평가판 구독을 생성하여 테스트 환경에 사용자가 현재 보유하고 있는 유료 구독과 별도의 Azure AD 테넌트를 보유하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="00c0c-137">이러한 분리는 프로덕션 구독에 영향을 주지 않고 테스트 테넌트의 사용자 및 그룹을 추가 및 제거할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="00c0c-138">2단계: Office 365 평가판 구독 구성</span><span class="sxs-lookup"><span data-stu-id="00c0c-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="00c0c-139">이 단계에서는 추가 사용자로 구독을 구성하고 Office 365 E5 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-139">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="00c0c-140">[Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)의 지침을 사용하여 컴퓨터에서 그래프 모듈용 Azure Active Directory PowerShell을 사용하여 구독에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="00c0c-141">**Windows PowerShell 자격 증명 요청** 대화 상자에서 전역 관리자 이름(예: jdoe@contosotoycompany.onmicrosoft.com)과 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-141">In the **Windows PowerShell Credential Request** dialog box, type the global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="00c0c-142">조직 이름(예 : contosotoycompany), 위치에 대한 2 자리 국가 코드, 공통 계정 암호를 입력 한 다음 PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="00c0c-143">여기서 공통 암호를 사용하는 것은 테스트 환경을 위한 구성을 쉽게 하고 자동화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="00c0c-144">물론 프로덕션 구독에서는 공통 암호를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="00c0c-145">나중에 참조할 수 있도록 주요 정보 기록</span><span class="sxs-lookup"><span data-stu-id="00c0c-145">Record key information for future reference</span></span>

<span data-ttu-id="00c0c-146">이 문서를 인쇄하여 30일 동안의 Office 365 평가판 구독 기간 동안 환경에 필요한 특정 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="00c0c-147">추가 30일 동안 평가판 구독을 쉽게 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="00c0c-148">영구 테스트 환경의 경우 별도의 Azure AD 테넌트와 소수의 라이선스를 사용해서 유료 구독을 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="00c0c-149">다음 값을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-149">Record these values:</span></span>
  
- <span data-ttu-id="00c0c-150">전역 관리자 이름:</span><span class="sxs-lookup"><span data-stu-id="00c0c-150">global administrator name:</span></span> ![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="00c0c-152">.onmicrosoft.com (1단계의 스텝 6)</span><span class="sxs-lookup"><span data-stu-id="00c0c-152">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="00c0c-153">이 계정의 암호도 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="00c0c-154">평가판 구독 조직 이름: </span><span class="sxs-lookup"><span data-stu-id="00c0c-154">Your trial subscription organization name:</span></span> ![Line](../media/Common-Images/TableLine.png) <span data-ttu-id="00c0c-156">(1단계의 스텝 4)</span><span class="sxs-lookup"><span data-stu-id="00c0c-156">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="00c0c-157">사용자 2, 사용자 3, 사용자 4, 사용자 5에 대한 계정을 나열하려면 Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="00c0c-158">여기에 계정 이름을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="00c0c-159">사용자 2 계정 이름: user2@</span><span class="sxs-lookup"><span data-stu-id="00c0c-159">User 2 account name: user2@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="00c0c-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="00c0c-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="00c0c-162">사용자 3 계정 이름: user3@</span><span class="sxs-lookup"><span data-stu-id="00c0c-162">User 3 account name: user3@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="00c0c-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="00c0c-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="00c0c-165">사용자 4 계정 이름: user4@</span><span class="sxs-lookup"><span data-stu-id="00c0c-165">User 4 account name: user4@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="00c0c-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="00c0c-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="00c0c-168">사용자 5 계정 이름: user5@</span><span class="sxs-lookup"><span data-stu-id="00c0c-168">User 5 account name: user5@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="00c0c-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="00c0c-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="00c0c-171">해당 계정의 공통 암호도 안전한 위치에 적어둡니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="00c0c-172">Office 365 테스트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="00c0c-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="00c0c-173">Office 365 테스트 환경만을 필요로 하는 경우 여기에서 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="00c0c-174">Office 365 및 Microsoft 365 모두에 적용되는 추가 테스트 랩 가이드는 [Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00c0c-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="00c0c-175">3단계: Microsoft 365 E5 평가판 구독 추가.</span><span class="sxs-lookup"><span data-stu-id="00c0c-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="00c0c-176">이 단계에서는 Microsoft 365 E5 평가판 구독을 등록하고 Office 365 E5 평가판 구독과 동일한 조직에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="00c0c-177">우선, Microsoft 365 E5 평가판 구독을 추가하고 전역 관리자 계정에 새로운 Microsoft 365 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="00c0c-178">인터넷 브라우저의 개인 인스턴스를 사용하고 전역 관리자 계정 자격 증명으로 [https://admin.microsoft.com](https://admin.microsoft.com)의 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="00c0c-179">**Microsoft 365 관리 센터** 페이지에 있는 왼쪽 탐색 영역에서 **대금 청구 > 서비스 구매**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="00c0c-180">**구입 서비스** 페이지에서 **Microsoft 365 E5**를 클릭한 다음 **무료 평가판 받기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="00c0c-181">**Microsoft 365 E5 평가판** 페이지에서 텍스트 또는 전화를 받도록 선택한 다음, 전화 번호를 입력하고, **문자 받기** 또는 **전화 받기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="00c0c-182">인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-182">Perform the verification.</span></span>

5. <span data-ttu-id="00c0c-183">**주문 확인** 페이지에서 **지금 평가판 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="00c0c-184">**주문 접수** 페이지에서 **계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="00c0c-185">Microsoft 365 관리 센터에서 **사용자> 활성 사용자**를 클릭하십시오.</span><span class="sxs-lookup"><span data-stu-id="00c0c-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="00c0c-186">**활성 사용자**에서 관리자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="00c0c-187">**라이선스와 앱**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="00c0c-188">Office 365 Enterprise E5의 라이센스를 비활성화하고 Microsoft 365 E5의 라이센스를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="00c0c-189">**변경 내용 저장**을 클릭한 다음 사용자 계정 정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="00c0c-190">다음, 다른 모든 계정 (사용자 2, 사용자 3, 사용자 4 및 사용자 5)에 대해 이전 절차의 8단계에서 11단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="00c0c-191">Microsoft 365 E5 평가판 구독은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="00c0c-192">영구 테스트 환경의 경우 소수의 라이선스를 사용해서 이 평가판 구독을 유료 구독으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="00c0c-193">이제 테스트 환경에는 다음이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="00c0c-194">Microsoft 365 E5 평가판 구독.</span><span class="sxs-lookup"><span data-stu-id="00c0c-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="00c0c-195">모든 해당 사용자 계정(전역 관리자만 또는 5개의 사용자 계정 모두)이 Microsoft 365 E5를 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="00c0c-196">다음에서는 구성 결과, Microsoft 365 E5를 추가하는 계정, Office 365 및 EMS(Enterprise Security + Management)를 포함하는 계정을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Microsoft 365 Enterprise 테스트 환경 3단계](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="00c0c-198">4단계: Windows 10 Enterprise 컴퓨터 만들기</span><span class="sxs-lookup"><span data-stu-id="00c0c-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="00c0c-199">이 단계에서는 Windows 10 Enterprise를 실행하는 독립 실행형 컴퓨터를 실제 컴퓨터, 가상 머신 또는 Azure Virtual Machine으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="00c0c-200">실제 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="00c0c-200">Physical computer</span></span>

<span data-ttu-id="00c0c-201">Obtain a personal computer and install Windows 10 Enterprise on it.</span><span class="sxs-lookup"><span data-stu-id="00c0c-201">Obtain a personal computer and install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="00c0c-202">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="00c0c-202">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="00c0c-203">가상 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="00c0c-203">Virtual machine</span></span>

<span data-ttu-id="00c0c-204">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it.</span><span class="sxs-lookup"><span data-stu-id="00c0c-204">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="00c0c-205">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="00c0c-205">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="00c0c-206">Azure의 가상 머신</span><span class="sxs-lookup"><span data-stu-id="00c0c-206">Virtual machine in Azure</span></span>

<span data-ttu-id="00c0c-207">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="00c0c-207">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise.</span></span> <span data-ttu-id="00c0c-208">Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image.</span><span class="sxs-lookup"><span data-stu-id="00c0c-208">Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image.</span></span> <span data-ttu-id="00c0c-209">For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="00c0c-209">For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="00c0c-210">The following command sets use the latest version of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00c0c-210">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="00c0c-211">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="00c0c-211">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="00c0c-212">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span><span class="sxs-lookup"><span data-stu-id="00c0c-212">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="00c0c-213">If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span><span class="sxs-lookup"><span data-stu-id="00c0c-213">If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="00c0c-214">먼저 Microsoft PowerShell 프롬프트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="00c0c-215">다음 명령을 사용하여 Azure 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="00c0c-216">다음 명령을 사용하여 구독 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="00c0c-217">Set your Azure subscription.</span><span class="sxs-lookup"><span data-stu-id="00c0c-217">Set your Azure subscription.</span></span> <span data-ttu-id="00c0c-218">Replace everything within the quotes, including the \< and > characters, with the correct name.</span><span class="sxs-lookup"><span data-stu-id="00c0c-218">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="00c0c-219">Next, create a new resource group.</span><span class="sxs-lookup"><span data-stu-id="00c0c-219">Next, create a new resource group.</span></span> <span data-ttu-id="00c0c-220">To determine a unique resource group name, use this command to list your existing resource groups.</span><span class="sxs-lookup"><span data-stu-id="00c0c-220">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="00c0c-221">Create your new resource group with these commands.</span><span class="sxs-lookup"><span data-stu-id="00c0c-221">Create your new resource group with these commands.</span></span> <span data-ttu-id="00c0c-222">Replace everything within the quotes, including the \< and > characters, with the correct names.</span><span class="sxs-lookup"><span data-stu-id="00c0c-222">Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="00c0c-223">Next, you create a new virtual network and the WIN10 virtual machine with these commands.</span><span class="sxs-lookup"><span data-stu-id="00c0c-223">Next, you create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="00c0c-224">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span><span class="sxs-lookup"><span data-stu-id="00c0c-224">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="00c0c-225">5단계: Azure AD에 Windows 10 컴퓨터 가입</span><span class="sxs-lookup"><span data-stu-id="00c0c-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="00c0c-226">Windows 10 Enterprise가 있는 실제 또는 가상 머신을 만든 후에 로컬 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00c0c-227">Azure에 있는 가상 머신에는 [다음 지침](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)에 따라 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="00c0c-228">다음으로, WIN10 컴퓨터를 Microsoft 365 E5 구독의 Azure AD 테넌트에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="00c0c-229">WIN10 컴퓨터의 데스크톱에서 **시작 > 설정 > 계정 > 회사 또는 학교 액세스 > 연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="00c0c-230">**회사 또는 학교 계정 설정** 대화 상자에서 **Azure Active Directory에 이 장치 가입**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="00c0c-231">**회사 또는 학교 계정**에서 Microsoft 365 E5 구독의 전역 관리자 계정 이름을 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="00c0c-232">**암호 입력**에 전역 관리자 계정의 암호를 입력하고 **로그인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="00c0c-233">사용자의 조직이 맞는지 묻는 메시지가 표시되면 **가입**을 클릭하고 **완료**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="00c0c-234">설정 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-234">Close the settings window.</span></span>
    
<span data-ttu-id="00c0c-235">다음으로 WIN10 컴퓨터에 엔터프라이즈용 Microsoft 365 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-235">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="00c0c-236">Microsoft Edge 브라우저를 열고 글로벌 관리자 계정 자격 증명으로 Office 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="00c0c-237">도움을 받으려면 [Office 365에 로그인하는 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00c0c-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="00c0c-238">**Microsoft Office 홈** 탭에서 **Office 설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="00c0c-239">수행할 작업을 묻는 메시지가 표시되면 **실행**을 클릭하고 **사용자 계정 컨트롤**에 대해 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="00c0c-240">Wait for Office to complete its installation.</span><span class="sxs-lookup"><span data-stu-id="00c0c-240">Wait for Office to complete its installation.</span></span> <span data-ttu-id="00c0c-241">When you see **You're all set!**, click **Close** twice.</span><span class="sxs-lookup"><span data-stu-id="00c0c-241">When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="00c0c-242">결과 환경은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-242">Here is your resulting environment.</span></span>

![Microsoft 365 Enterprise 테스트 환경 5단계](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="00c0c-244">여기에는 다음과 같은 WIN10 컴퓨터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="00c0c-245">Microsoft 365 E5 구독의 Azure AD 테넌트에 가입했습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="00c0c-246">Microsoft Intune(EMS)에서 Azure AD 장치로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="00c0c-247">엔터프라이즈용 Microsoft 365 앱이 설치되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-247">Has Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="00c0c-248">이제 [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)의 추가 기능을 사용해볼 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="00c0c-249">다음 단계</span><span class="sxs-lookup"><span data-stu-id="00c0c-249">Next steps</span></span>

<span data-ttu-id="00c0c-250">다음과 같은 추가 테스트 랩 가이드 집합에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="00c0c-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="00c0c-251">ID</span><span class="sxs-lookup"><span data-stu-id="00c0c-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="00c0c-252">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="00c0c-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="00c0c-253">정보 보호</span><span class="sxs-lookup"><span data-stu-id="00c0c-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="00c0c-254">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00c0c-254">See also</span></span>

[<span data-ttu-id="00c0c-255">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="00c0c-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="00c0c-256">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="00c0c-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="00c0c-257">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="00c0c-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
