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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈용 Microsoft 365를 테스트하기 위한 간단한 테스트 환경을 만들 수 있습니다.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487391"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="0b217-103">간단한 기본 구성</span><span class="sxs-lookup"><span data-stu-id="0b217-103">The lightweight base configuration</span></span>

<span data-ttu-id="0b217-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 및 Office 365 Enterprise 테스트 환경에 모두 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="0b217-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="0b217-105">이 문서에서는 Microsoft 365 E5 구독 및 Windows 10 Enterprise를 실행하는 컴퓨터를 사용하여 간소화된 환경을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![간단한 Microsoft 365 Enterprise 테스트 환경](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="0b217-107">간단한 테스트 환경을 만드는 데는 다음 다섯 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="0b217-108">1단계: Microsoft 365 E5 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="0b217-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="0b217-109">2단계: Office 365 평가판 구독 구성</span><span class="sxs-lookup"><span data-stu-id="0b217-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="0b217-110">3단계: Microsoft 365 E5 평가판 구독 추가.</span><span class="sxs-lookup"><span data-stu-id="0b217-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="0b217-111">4단계: Windows 10 Enterprise 컴퓨터 만들기</span><span class="sxs-lookup"><span data-stu-id="0b217-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="0b217-112">5단계: Azure AD에 Windows 10 컴퓨터 가입</span><span class="sxs-lookup"><span data-stu-id="0b217-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="0b217-113">결과 환경을 사용하여 [엔터프라이즈용 Microsoft 365의 기능을 테스트합니다.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="0b217-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="0b217-115">엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b217-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="0b217-116">이 문서를 인쇄하여 30일 동안의 Office 365 평가판 구독 기간 동안 환경에 필요한 특정 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="0b217-117">추가 30일 동안 평가판 구독을 쉽게 연장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="0b217-118">영구 테스트 환경의 경우 별도의 Azure AD 테넌트와 소수의 라이선스를 사용해서 유료 구독을 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="0b217-119">1단계: Microsoft 365 E5 구독 만들기</span><span class="sxs-lookup"><span data-stu-id="0b217-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="0b217-120">Microsoft 365 E5 평가판 구독으로 시작한 다음 Microsoft 365 E5 구독을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="0b217-121">테스트 환경에 현재 있는 유료 구독과 별개의 Azure AD 테넌트가 있도록 Office 365의 평가판 구독을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="0b217-122">이러한 분리는 프로덕션 구독에 영향을 주지 않고 테스트 테넌트에서 사용자 및 그룹을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="0b217-123">Microsoft 365 E5 평가판 구독을 시작하려면 먼저 가상의 회사 이름 및 새 Microsoft 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="0b217-p103">회사 이름으로 Microsoft 샘플 콘텐츠에 사용되는 가상의 회사인 Contoso의 변형을 사용하는 것이 좋지만 필수는 아닙니다. 여기에 가상의 회사 이름을 기록하세요.</span><span class="sxs-lookup"><span data-stu-id="0b217-p103">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![선](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="0b217-p104">새 Microsoft 계정을 등록하려면으로 [https://outlook.com](https://outlook.com)으로 이동한 후 새 전자 메일 계정 및 주소를 사용하여 계정을 만듭니다. 이 계정을 사용하여 Office 365에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-p104">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="0b217-129">여기에 새 계정의 이름과 성을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-129">Record the first and last name of your new account here:</span></span> ![선](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="0b217-131">여기서 새 전자 메일 계정 주소를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-131">Record the new email account address here:</span></span> ![선](../media/Common-Images/TableLine.png)<span data-ttu-id="0b217-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="0b217-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="0b217-134">Office 365 E5 평가판 구독 등록</span><span class="sxs-lookup"><span data-stu-id="0b217-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="0b217-135">브라우저에서 [https://aka.ms/e5trial](https://aka.ms/e5trial) .</span><span class="sxs-lookup"><span data-stu-id="0b217-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="0b217-136">**Office 365 E5** 페이지를 선택해 주셔서 감사합니다. 1단계에서 새 전자 메일 계정 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="0b217-137">내보라 구독 프로세스의 2단계에서 요청된 정보를 입력한 다음 확인을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="0b217-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="0b217-138">3단계에서 조직 이름을 입력한 다음 구독의 전역 관리자가 될 계정 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="0b217-139">4단계에서 여기에 로그인 페이지를 기록합니다(선택 후 복사).</span><span class="sxs-lookup"><span data-stu-id="0b217-139">For step 4, record the sign-in page here (select and copy):</span></span> ![Line](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="0b217-141">여기에 사용자 ID를 기록합니다. ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0b217-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="0b217-142">입력한 암호를 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="0b217-143">이 값은 **전역 관리자 이름** 으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="0b217-144">설치로 **이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="0b217-145">In Office 365 E5 Setup, select **Continue using your *organization*.onmicrosoft.com for email and signing in,** and then select **Exit and continue later.**</span><span class="sxs-lookup"><span data-stu-id="0b217-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="0b217-146">Microsoft 365 관리 센터가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="0b217-147">2단계: Office 365 평가판 구독 구성</span><span class="sxs-lookup"><span data-stu-id="0b217-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="0b217-148">이 단계에서는 추가 사용자로 구독을 구성하고 Office 365 E5 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="0b217-149">컴퓨터에서 Azure Active Directory PowerShell for Graph 모듈을 사용하여 구독에 연결하려면 [PowerShell을 사용하여 Microsoft 365에 연결의](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="0b217-150">Windows PowerShell **자격** 증명 요청 대화 상자에 전역 관리자 이름(예: jdoe@contosotoycompany.onmicrosoft.com) 및 암호를 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="0b217-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="0b217-151">조직 이름(예: *contosotoycompany),* 위치에 대한 2자 국가 코드, 공통 계정 암호를 입력한 다음 PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="0b217-152">여기서 공통 암호를 사용하는 것은 테스트 환경을 위한 구성을 쉽게 하고 자동화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="0b217-153">물론 프로덕션 구독에서는 공통 암호를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="0b217-154">나중에 참조할 수 있도록 주요 정보 기록</span><span class="sxs-lookup"><span data-stu-id="0b217-154">Record key information for future reference</span></span>

<span data-ttu-id="0b217-155">이러한 값을 아직 기록하지 않은 경우 지금 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="0b217-156">전역 관리자 이름:</span><span class="sxs-lookup"><span data-stu-id="0b217-156">Global administrator name:</span></span> ![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="0b217-158">.onmicrosoft.com (1단계의 스텝 6)</span><span class="sxs-lookup"><span data-stu-id="0b217-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="0b217-159">이 계정의 암호도 안전한 위치에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="0b217-160">평가판 구독 조직 이름: </span><span class="sxs-lookup"><span data-stu-id="0b217-160">Your trial subscription organization name:</span></span> ![Line](../media/Common-Images/TableLine.png) <span data-ttu-id="0b217-162">(1단계의 스텝 4)</span><span class="sxs-lookup"><span data-stu-id="0b217-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="0b217-163">사용자 2, 사용자 3, 사용자 4, 사용자 5에 대한 계정을 나열하려면 Windows PowerShell 프롬프트에 대한 Microsoft Azure Active Directory 모듈에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="0b217-164">여기에 계정 이름을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="0b217-165">사용자 2 계정 이름: user2@</span><span class="sxs-lookup"><span data-stu-id="0b217-165">User 2 account name: user2@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="0b217-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0b217-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="0b217-168">사용자 3 계정 이름: user3@</span><span class="sxs-lookup"><span data-stu-id="0b217-168">User 3 account name: user3@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="0b217-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0b217-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="0b217-171">사용자 4 계정 이름: user4@</span><span class="sxs-lookup"><span data-stu-id="0b217-171">User 4 account name: user4@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="0b217-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0b217-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="0b217-174">사용자 5 계정 이름: user5@</span><span class="sxs-lookup"><span data-stu-id="0b217-174">User 5 account name: user5@</span></span>![Line](../media/Common-Images/TableLine.png)<span data-ttu-id="0b217-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0b217-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="0b217-177">해당 계정의 공통 암호도 안전한 위치에 적어둡니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="0b217-178">Office 365 테스트 환경 사용</span><span class="sxs-lookup"><span data-stu-id="0b217-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="0b217-179">Office 365 테스트 환경만 필요한 경우 이 문서의 나머지 내용을 읽을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="0b217-180">Office 365와 Microsoft 365에 모두 적용되는 추가 테스트 랩 가이드는 [엔터프라이즈용 Microsoft 365 테스트 랩 가이드를 참조하세요.](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="0b217-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="0b217-181">3단계: Microsoft 365 E5 평가판 구독 추가.</span><span class="sxs-lookup"><span data-stu-id="0b217-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="0b217-182">이 단계에서는 Microsoft 365 E5 평가판 구독을 등록하고 Office 365 E5 평가판 구독과 동일한 조직에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="0b217-183">우선, Microsoft 365 E5 평가판 구독을 추가하고 전역 관리자 계정에 새로운 Microsoft 365 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="0b217-184">인터넷 브라우저 개인 창에서 전역 관리자 계정 자격 증명을 사용하여 Microsoft 365 관리 센터에 [https://admin.microsoft.com](https://admin.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="0b217-185">Microsoft **365** 관리 센터 페이지의 왼쪽 탐색에서 청구 서비스 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="0b217-186">서비스 **구매 페이지에서** **Microsoft 365 E5를** 선택한 다음 평가판 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="0b217-187">Microsoft **365 E5 평가판** 페이지에서 문자 메시지 또는 전화 통화를 받고 전화 번호를  입력한 다음 문자 메시지 또는 전화 받기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="0b217-188">인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-188">Perform the verification.</span></span>

5. <span data-ttu-id="0b217-189">주문 **확인 페이지에서** 지금 **시도를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="0b217-190">주문 **확인 페이지에서** 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="0b217-191">Microsoft 365 관리 센터에서 활성 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="0b217-192">활성 **사용자에서** 관리자 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="0b217-193">라이선스 **및 앱을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="0b217-194">Office 365 Enterprise E5의 라이센스를 비활성화하고 Microsoft 365 E5의 라이센스를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="0b217-195">변경 **내용 저장을** 선택한 다음 사용자 계정 정보 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="0b217-196">다음, 다른 모든 계정 (사용자 2, 사용자 3, 사용자 4 및 사용자 5)에 대해 이전 절차의 8단계에서 11단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b217-197">Microsoft 365 E5 평가판 구독 기간은 30일입니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="0b217-198">영구 테스트 환경의 경우 소수의 라이선스를 사용해서 이 평가판 구독을 유료 구독으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="0b217-199">이제 테스트 환경에는 다음이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="0b217-200">Microsoft 365 E5 평가판 구독.</span><span class="sxs-lookup"><span data-stu-id="0b217-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="0b217-201">모든 해당 사용자 계정(전역 관리자만 또는 5개의 사용자 계정 모두)이 Microsoft 365 E5를 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="0b217-202">결과로 Microsoft 365 E5를 추가하는 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Microsoft 365 Enterprise 테스트 환경 3단계](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="0b217-204">4단계: Windows 10 Enterprise 컴퓨터 만들기</span><span class="sxs-lookup"><span data-stu-id="0b217-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="0b217-205">이 단계에서는 Windows 10 Enterprise를 실행하는 독립 실행형 컴퓨터를 실제 컴퓨터, 가상 머신 또는 Azure Virtual Machine으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="0b217-206">실제 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="0b217-206">Physical computer</span></span>

<span data-ttu-id="0b217-207">개인 컴퓨터에 Windows 10 Enterprise를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="0b217-208">여기에서 Windows 10 Enterprise 평가판을 다운로드할 수 [있습니다.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)</span><span class="sxs-lookup"><span data-stu-id="0b217-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="0b217-209">가상 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="0b217-209">Virtual machine</span></span>

<span data-ttu-id="0b217-210">선택한 하이퍼바이너를 사용하여 가상 머신을 만든 다음 Windows 10 Enterprise를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="0b217-211">여기에서 Windows 10 Enterprise 평가판을 다운로드할 수 [있습니다.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)</span><span class="sxs-lookup"><span data-stu-id="0b217-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="0b217-212">Azure의 가상 머신</span><span class="sxs-lookup"><span data-stu-id="0b217-212">Virtual machine in Azure</span></span>

<span data-ttu-id="0b217-p111">Microsoft Azure에서 Windows 10 가상 머신을 만들려면 Windows 10 Enterprise에 대한 이미지에 액세스할 수 있는 ***Visual Studio 기반 구독이 있어야 합니다***. 다른 유형의 Azure 구독(예: 평가판 및 유료 구독)으로는 이 이미지에 액세스할 수 없습니다. 최신 정보를 보려면 [개발/테스트 시나리오에 Azure의 Windows 클라이언트 사용](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b217-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b217-216">다음 명령 집합은 최신 버전의 Azure PowerShell을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="0b217-217">[Azure PowerShell cmdlet으로 시작](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b217-217">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="0b217-218">이러한 명령 집합은 WIN10이라는 Windows 10 Enterprise 가상 컴퓨터와 리소스 그룹, 저장소 계정 및 가상 네트워크를 비롯한 모든 필수 인프라를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="0b217-219">Azure 인프라 서비스에 이미 익숙한 경우 현재 배포된 인프라에 맞게 이러한 지침을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="0b217-220">먼저 Microsoft PowerShell 프롬프트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="0b217-221">이 명령을 사용하여 Azure 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="0b217-222">이 명령을 사용하여 구독 이름을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="0b217-223">Azure 구독을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-223">Set your Azure subscription.</span></span> <span data-ttu-id="0b217-224">문자를 포함하여 인용 부호 안에 있는 모든 것을 올바른 \< and > 이름으로 바칭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="0b217-225">다음으로 새 리소스 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-225">Next, create a new resource group.</span></span> <span data-ttu-id="0b217-226">고유한 리소스 그룹 이름을 확인하려면 이 명령을 사용하여 기존 리소스 그룹을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="0b217-227">이러한 명령을 사용하여 새 리소스 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="0b217-228">문자를 포함하여 인용 부호 안에 있는 모든 것을 올바른 \< and > 이름으로 바칭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="0b217-229">다음으로, 다음 명령을 사용하여 새 가상 네트워크 및 WIN10 가상 머신을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="0b217-230">메시지가 표시될 때 WIN10에 대한 로컬 관리자 계정의 이름과 암호를 제공하고 안전한 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="0b217-231">5단계: Azure AD에 Windows 10 컴퓨터 가입</span><span class="sxs-lookup"><span data-stu-id="0b217-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="0b217-232">Windows 10 Enterprise가 있는 실제 또는 가상 머신을 만든 후에 로컬 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b217-233">Azure의 가상 컴퓨터의 경우 다음  [지침을](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) 사용하여 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-233">For a virtual machine in Azure, use  [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="0b217-234">다음으로, WIN10 컴퓨터를 Microsoft 365 E5 구독의 Azure AD 테넌트에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="0b217-235">WIN10 컴퓨터의 바탕 화면에서 시작 > 설정 > 계정에 > 또는 학교 액세스 > **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="0b217-236">직장 또는 **학교 계정** 설정 대화 상자에서 이 디바이스를 Azure **Active Directory에 가입을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="0b217-237">직장 **또는 학교 계정에서** Microsoft 365 E5 구독의 전역 관리자 계정 이름을 입력하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="0b217-238">암호를 **입력하고** 전역 관리자 계정의 암호를 입력한 다음 **로그인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="0b217-239">조직이 올바른지 확인하라는 메시지가 표시될 때 **참가를** 선택한 다음 완료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="0b217-240">설정 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-240">Close the settings window.</span></span>
    
<span data-ttu-id="0b217-241">다음으로 WIN10 컴퓨터에 엔터프라이즈용 Microsoft 365 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="0b217-242">Microsoft Edge 브라우저를 열고 전역 관리자 계정 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="0b217-243">On the **Microsoft Office Home** tab, select **Install Office**.</span><span class="sxs-lookup"><span data-stu-id="0b217-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="0b217-244">실행할 작업을 묻는 메시지가 표시될 때 실행을 선택한 다음 사용자 계정 컨트롤에 **대해 예를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b217-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="0b217-245">Office 설치가 완료될 때까지 기다렸다가</span><span class="sxs-lookup"><span data-stu-id="0b217-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="0b217-246">모두 **설정되어** 있는 경우 닫기 두 **번** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="0b217-247">결과 환경은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-247">Your resulting environment looks like this:</span></span>

![Microsoft 365 Enterprise 테스트 환경 5단계](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="0b217-249">여기에는 다음과 같은 WIN10 컴퓨터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="0b217-250">Microsoft 365 E5 구독의 Azure AD 테넌트에 가입했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="0b217-251">Microsoft Intune(EMS)에서 Azure AD 장치로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="0b217-252">엔터프라이즈용 Microsoft 365 앱이 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="0b217-253">이제 엔터프라이즈용 [Microsoft 365의](https://www.microsoft.com/microsoft-365/enterprise)추가 기능을 실험할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0b217-254">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0b217-254">Next steps</span></span>

<span data-ttu-id="0b217-255">다음과 같은 추가 테스트 랩 가이드 집합에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0b217-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="0b217-256">ID</span><span class="sxs-lookup"><span data-stu-id="0b217-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="0b217-257">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="0b217-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="0b217-258">정보 보호</span><span class="sxs-lookup"><span data-stu-id="0b217-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="0b217-259">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b217-259">See also</span></span>

[<span data-ttu-id="0b217-260">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="0b217-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0b217-261">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="0b217-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0b217-262">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="0b217-262">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
