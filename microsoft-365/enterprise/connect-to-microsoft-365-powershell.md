---
title: PowerShell을 사용하여 Microsoft 365에 연결
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Microsoft 365용 PowerShell을 사용하여 Microsoft 365 테넌트에 연결하여 명령줄에서 관리 센터 작업을 수행합니다.
ms.openlocfilehash: 70d6aa1373daf2322319d21e385fc1498af3351e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782804"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="e5df1-103">PowerShell을 사용하여 Microsoft 365에 연결</span><span class="sxs-lookup"><span data-stu-id="e5df1-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="e5df1-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="e5df1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e5df1-105">Microsoft 365용 PowerShell을 사용하여 명령줄에서 Microsoft 365 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="e5df1-106">PowerShell에 연결하려면 필수 소프트웨어를 설치하고 Microsoft 365 조직에 연결하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="e5df1-107">Microsoft 365 및 관리자 계정, 그룹 및 라이선스에 연결하는 데 사용할 수 있는 두 가지 버전의 PowerShell 모듈이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="e5df1-108">Azure Active Directory PowerShell for Graph(cmdlet의 이름에 *AzureAD* 포함)</span><span class="sxs-lookup"><span data-stu-id="e5df1-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="e5df1-109">Windows PowerShell용 Microsoft Azure AD 모듈(cmdlet의 이름에 *Msol* 포함)</span><span class="sxs-lookup"><span data-stu-id="e5df1-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="e5df1-110">현재, Azure Active Directory PowerShell for Graph 모듈이 사용자, 그룹 및 라이선스 관리를 위한 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 완전히 대체하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="e5df1-111">어떤 경우에는, 두 버전을 모두 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="e5df1-112">동일한 컴퓨터에 두 버전을 안전하게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e5df1-113">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="e5df1-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="e5df1-114">**운영 체제**</span><span class="sxs-lookup"><span data-stu-id="e5df1-114">**Operating system**</span></span>

<span data-ttu-id="e5df1-p103">Windows 64비트 버전을 사용해야 합니다. Microsoft PowerShell용 Microsoft Azure Active Directory 모듈의 32비트 버전에 대한 지원은 2014년에 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="e5df1-117">다음 Windows 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="e5df1-118">Windows 10, Windows 8.1, Windows 8 또는 Windows 7 서비스팩 1(SP1)</span><span class="sxs-lookup"><span data-stu-id="e5df1-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="e5df1-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 또는 Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="e5df1-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="e5df1-120">Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 및 Windows Server 2008 R2 SP1의 경우, [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)을 다운로드하고 설치합니다. </span><span class="sxs-lookup"><span data-stu-id="e5df1-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="e5df1-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e5df1-121">**PowerShell**</span></span>

- <span data-ttu-id="e5df1-122">Azure Active Directory PowerShell for Graph 모듈의 경우 PowerShell 버전 5.1 이상을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="e5df1-p104">Windows PowerShell 모듈용 Microsoft Azure Active Directory 모듈의 경우 PowerShell 버전 5.1 이상, PowerShell 버전 6까지 사용해야 합니다. PowerShell 버전 7은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="e5df1-125">이러한 절차는 Microsoft 365 관리자 역할의 구성원인 사용자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="e5df1-126">자세한 내용은 [관리자 역할 정보](../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-126">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e5df1-127">그런 다음, Azure Active Directory PowerShell for Graph 모듈에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e5df1-128">Azure Active Directory PowerShell for Graph 모듈의 명령에는 cmdlet 이름에 *AzureAD* 가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="e5df1-129">[Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) 모듈 또는 [Azure PowerShell](/powershell/azure/install-az-ps)을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-129">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="e5df1-130">Azure Active Directory PowerShell for Graph 모듈에서 새 cmdlet을 필요로 하는 프로시저의 경우, 이러한 단계를 사용해서 모듈을 설치하고 Microsoft 365 구독에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="e5df1-131">Windows의 여러 버전에 대한 지원 정보는 [Azure Active Directory PowerShell for Graph 모듈](/powershell/azure/active-directory/install-adv2)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="e5df1-132">1단계: 필수 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="e5df1-132">Step 1: Install the required software</span></span>

<span data-ttu-id="e5df1-133">이러한 단계는 컴퓨터에서 한 번만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="e5df1-134">그러나 소프트웨어를 정기적으로 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="e5df1-135">관리자 권한의 Windows PowerShell 명령 프롬프트 창을 엽니다(관리자 권한으로 Windows PowerShell 실행).</span><span class="sxs-lookup"><span data-stu-id="e5df1-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="e5df1-136">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="e5df1-137">기본적으로 PowerShell 갤러리(PSGallery)는 **PowerShellGet** 을 위한 신뢰할 수 있는 리포지토리로 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-137">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="e5df1-138">PSGallery를 처음 사용하면 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-138">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="e5df1-139">설치를 계속하려면 **예** 또는 **모두 예** 로 대답하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5df1-139">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="e5df1-140">2단계: Microsoft 365 구독을 위해 Azure AD에 연결</span><span class="sxs-lookup"><span data-stu-id="e5df1-140">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="e5df1-p109">계정 이름 및 암호 또는 다단계 인증을 사용하여 Microsoft 365 구독용 Azure AD(Azure Active Directory)에 연결하려면, Windows PowerShell 명령 프롬프트에서 다음 명령 중 하나를 실행합니다(권한 상승할 필요는 없음.)</span><span class="sxs-lookup"><span data-stu-id="e5df1-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="e5df1-143">Office 365 클라우드</span><span class="sxs-lookup"><span data-stu-id="e5df1-143">Office 365 cloud</span></span> | <span data-ttu-id="e5df1-144">명령</span><span class="sxs-lookup"><span data-stu-id="e5df1-144">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="e5df1-145">Office 365 Worldwide(+GCC)</span><span class="sxs-lookup"><span data-stu-id="e5df1-145">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="e5df1-146">21 Vianet이 운영하는 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5df1-146">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="e5df1-147">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="e5df1-147">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="e5df1-148">Office 365 미국 국방부(DoD) 및 Office 365 미국 정부 GCC High</span><span class="sxs-lookup"><span data-stu-id="e5df1-148">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="e5df1-149">**계정에 로그인하세요** 대화 상자에서, Microsoft 365 회사 또는 학교 계정 사용자 이름 및 암호를 입력한 다음, **확인** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-149">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="e5df1-150">다단계 인증을 사용하는 경우 지침에 따라 확인 코드와 같은 추가 인증 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-150">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="e5df1-151">연결 후 [Azure Active Directory PowerShell for Graph 모듈](/powershell/module/azuread)의 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-151">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e5df1-152">Windows PowerShell용 Microsoft Azure Active Directory 모듈에 연결</span><span class="sxs-lookup"><span data-stu-id="e5df1-152">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="e5df1-153">Windows PowerShell용 Microsoft Azure Active Directory 모듈의 명령에는 cmdlet 이름에 *sol* 이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-153">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="e5df1-154">PowerShell 버전 7 이상은 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-154">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="e5df1-155">PowerShell 버전 7 이상의 경우 Azure Active Directory PowerShell for Graph 모듈 또는 Azure PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-155">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="e5df1-156">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-156">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="e5df1-157">Windows PowerShell에서 이러한 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-157">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="e5df1-158">1단계: 필수 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="e5df1-158">Step 1: Install the required software</span></span>

<span data-ttu-id="e5df1-159">이러한 단계는 컴퓨터에서 한 번만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-159">These steps are required only one time on your computer.</span></span> <span data-ttu-id="e5df1-160">그러나 소프트웨어를 정기적으로 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-160">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="e5df1-161">Windows 10을 사용하는 것이 아니라면 64비트 버전의 Microsoft Online Services 로그인 도우미를 설치합니다.[IT 전문가용 Microsoft Online Services 로그인 도우미 RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-161">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="e5df1-162">다음 단계에 따라 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-162">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="e5df1-163">관리자 권한의 Windows PowerShell 명령 프롬프트를 엽니다(관리자 권한으로 Windows PowerShell 실행).</span><span class="sxs-lookup"><span data-stu-id="e5df1-163">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="e5df1-164">**Install-Module MSOnline** 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-164">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="e5df1-165">NuGet 공급자를 설치할지 묻는 메시지가 표시되면 **Y** 를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-165">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="e5df1-166">PSGallery에서 모듈을 설치할지 묻는 메시지가 표시되면 **Y** 를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-166">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="e5df1-167">2단계: Microsoft 365 구독을 위해 Azure AD에 연결</span><span class="sxs-lookup"><span data-stu-id="e5df1-167">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="e5df1-p113">계정 이름 및 암호 또는 다단계 인증을 사용하여 Microsoft 365 구독용 Azure AD에 연결하려면, Windows PowerShell 명령 프롬프트에서 다음 명령 중 하나를 실행합니다(권한 상승할 필요는 없음.)</span><span class="sxs-lookup"><span data-stu-id="e5df1-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="e5df1-170">Office 365 클라우드</span><span class="sxs-lookup"><span data-stu-id="e5df1-170">Office 365 cloud</span></span> | <span data-ttu-id="e5df1-171">명령</span><span class="sxs-lookup"><span data-stu-id="e5df1-171">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="e5df1-172">Office 365 Worldwide(+GCC)</span><span class="sxs-lookup"><span data-stu-id="e5df1-172">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="e5df1-173">21 Vianet이 운영하는 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5df1-173">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="e5df1-174">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="e5df1-174">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="e5df1-175">Office 365 미국 국방부(DoD) 및 Office 365 미국 정부 GCC High</span><span class="sxs-lookup"><span data-stu-id="e5df1-175">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="e5df1-176">**계정에 로그인하세요** 대화 상자에서, Microsoft 365 회사 또는 학교 계정 사용자 이름 및 암호를 입력한 다음, **확인** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-176">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="e5df1-177">다단계 인증을 사용하는 경우 지침에 따라 확인 코드와 같은 추가 인증 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-177">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="e5df1-178">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="e5df1-178">How do you know it worked?</span></span>

<span data-ttu-id="e5df1-179">오류 메시지가 표시되지 않으면 성공적으로 연결된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-179">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="e5df1-180">빠르게 테스트하려면 **Get-MsolUser** 과 같은 Microsoft 365 cmdlet을 실행하고 결과를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-180">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="e5df1-181">오류 메시지가 표시되는 경우 다음 문제를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-181">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="e5df1-182">**가장 흔한 문제는 암호를 잘못 입력한 경우입니다**.</span><span class="sxs-lookup"><span data-stu-id="e5df1-182">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="e5df1-183">[2단계](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)를 다시 실행하고 사용자 이름과 암호를 입력할 때 신중하게 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-183">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="e5df1-184">**Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하려면 컴퓨터에 Microsoft .NET Framework 3.5.* x*가 있어야 합니다**. 컴퓨터에 최신 버전(예: 4 또는 4.5.* x*)이 설치되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-184">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="e5df1-185">이전 버전의 .NET Framework와 이전 버전과의 호환성을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-185">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="e5df1-186">자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-186">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="e5df1-187">Windows Server 2012 또는 Windows Server 2012 R2의 경우 [역할 및 기능 추가 마법사를 사용하여 .NET Framework 3.5를 사용 가능하도록 설정](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-187">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="e5df1-188">Windows 7 또는 Windows Server 2008 R2의 경우 [Windows PowerShell용 Azure Active Directory 모듈을 열 수 없음](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-188">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="e5df1-189">Windows 10, Windows 8.1 및 Windows 8의 경우, [Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치](/dotnet/framework/install/dotnet-35-windows-10)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-189">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="e5df1-190">**Windows PowerShell용 Microsoft Azure Active Directory 모듈 버전이 오래되었을 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e5df1-190">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="e5df1-191">확인하려면 Windows PowerShell용 Microsoft Azure Active Directory 모듈 또는 Microsoft 365용 PowerShell에서 다음 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-191">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="e5df1-192">반환된 버전 번호가 *1.0.8070.2* 보다 낮은 경우 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 제거한 후 위의 [1단계](#step-1-install-the-required-software)에서 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e5df1-192">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="e5df1-193">**연결 오류 메시지가 표시되면**, ["Connect-MsolService: 형식 예외가 발생함" 오류](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-193">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="e5df1-194">**"Get-Item: 경로를 찾을 수 없음" 오류 메시지가 표시되면**, 다음 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="e5df1-194">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="e5df1-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5df1-195">See also</span></span>

- [<span data-ttu-id="e5df1-196">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="e5df1-196">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e5df1-197">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="e5df1-197">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e5df1-198">단일 Windows PowerShell 창에서 모든 Office 365 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="e5df1-198">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
