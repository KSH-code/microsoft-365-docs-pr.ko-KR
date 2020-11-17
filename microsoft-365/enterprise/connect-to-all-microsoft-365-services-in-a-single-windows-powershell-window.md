---
title: 단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: '요약: 단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결합니다.'
ms.openlocfilehash: 4128e360a3664d3a61559139bc4e6e346418fa61
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087030"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="77f15-103">단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="77f15-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="77f15-104">PowerShell을 사용하여 Microsoft 365를 관리하는 경우 여러 PowerShell 세션을 동시에 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="77f15-105">사용자 계정, SharePoint Online, Exchange Online, 비즈니스용 Skype 온라인, Microsoft Teams, 보안 &amp; 준수 센터를 관리하는 PowerShell 창이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="77f15-106">서비스 관리 창 간에 데이터를 교환할 수 없기 때문에 최적의 Microsoft 365 관리 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="77f15-107">이 문서에서는 Microsoft 365 계정, 비즈니스용 Skype 온라인, Exchange Online, SharePoint Online, Microsoft Teams, 보안 &amp; 준수 센터를 관리하는 데 사용할 수 있는 PowerShell의 단일 인스턴스를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="77f15-108">현재 이 문서에는 전 세계(+GCC) 클라우드에 연결하는 명령만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="77f15-109">노트에서는 Microsoft 365 클라우드에 연결하는 방법에 대한 문서 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="77f15-110">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="77f15-110">Before you begin</span></span>

<span data-ttu-id="77f15-111">단일 PowerShell 인스턴스에서 모든 Microsoft 365를 관리하려면 먼저 다음 필수 구성 요소를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="77f15-112">사용하는 Microsoft 365 회사 또는 학교 계정은 Microsoft 365 관리자 역할의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="77f15-113">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="77f15-114">이러한 Microsoft 365 PowerShell 요구 사항은 모든 Microsoft 365 서비스 요구 사항이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="77f15-115">다음 64비트 Windows 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="77f15-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="77f15-116">Windows 10</span></span>
    
  - <span data-ttu-id="77f15-117">Windows 8.1 또는 Windows 8</span><span class="sxs-lookup"><span data-stu-id="77f15-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="77f15-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="77f15-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="77f15-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="77f15-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="77f15-120">Windows Server 2012 R2 또는 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="77f15-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="77f15-121">Windows 7 SP1(서비스 팩 1)\*</span><span class="sxs-lookup"><span data-stu-id="77f15-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="77f15-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="77f15-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="77f15-123">\*Microsoft .NET Framework 4.5.*x* 및 Windows Management Framework 3.0 또는 4.0을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="77f15-124">자세한 내용은 [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).</span></span>
    
    <span data-ttu-id="77f15-125">비즈니스용 Skype 온라인과 하나의 Microsoft 365 모듈 요구 사항 때문에 64비트 버전의 Windows를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="77f15-126">Azure Active Directory(Azure AD), Exchange 온라인, SharePoint 온라인, 비즈니스용 Skype 온라인 및 Teams에 필요한 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="77f15-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="77f15-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="77f15-128">SharePoint Online 관리 셸</span><span class="sxs-lookup"><span data-stu-id="77f15-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="77f15-129">비즈니스용 Skype Online PowerShell 모듈</span><span class="sxs-lookup"><span data-stu-id="77f15-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="77f15-130">Exchange 온라인 PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="77f15-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="77f15-131">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="77f15-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="77f15-132">비즈니스용 Skype 온라인과 보안 &amp; 준수 센터에 대해 서명된 스크립트를 실행하기 위해 PowerShell을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="77f15-133">관리자 권한이 있는 PowerShell 세션에서 다음 명령을 실행 합니다 (**관리자 권한으로 실행** PowerShellPowerShell 세션).</span><span class="sxs-lookup"><span data-stu-id="77f15-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="77f15-134">Exchange Online PowerShell V2 모듈과 함께 Exchange Online 및 보안 &amp; 준수 센터</span><span class="sxs-lookup"><span data-stu-id="77f15-134">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="77f15-135">이 문서에서는 Exchange Online PowerShell V2 모듈을 사용하여 Exchange Online 및 보안 &amp; 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-135">The procedures in this article use the Exchange Online PowerShell V2 module to connect to both Exchange Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="77f15-136">그러나 현재 *동일한 PowerShell 창* 에서 둘 다 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-136">But currently you can't connect to both *in the same PowerShell window*.</span></span> <span data-ttu-id="77f15-137">여러 Microsoft 365 서비스에 대해 PowerShell 창을 구성할 때 하나 또는 다른 하나에 연결하도록 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-137">So you have to choose to connect to one or the other when you configure a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="77f15-138">암호만 사용하는 경우 연결 단계</span><span class="sxs-lookup"><span data-stu-id="77f15-138">Connection steps when using just a password</span></span>

<span data-ttu-id="77f15-139">로그인에 암호만 사용하는 경우 단일 PowerShell 창에서 모든 서비스에 연결하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-139">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="77f15-140">Windows PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-140">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="77f15-141">이 명령을 실행하여 Microsoft 365 회사 또는 학교 계정 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-141">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="77f15-142">이 명령을 실행하여 Azure Active Directory PowerShell for Grap 모듈을 사용해 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-142">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="77f15-143">또는, Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하고 있는 경우, 이 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-143">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="77f15-144">PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-144">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="77f15-145">PowerShell에서 이 cmdlet을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-145">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="77f15-146">SharePoint 온라인에 연결 하려면 이 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-146">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="77f15-147">도메인에 대한 조직 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-147">Specify the organization name for your domain.</span></span> <span data-ttu-id="77f15-148">예를 들어 "litwareinc\.onmicrosoft.com"의 경우 조직 이름 값은 "litwareinc"입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-148">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="77f15-149">비즈니스용 Skype 온라인에 연결하려면 다음 명령어를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-149">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="77f15-150">처음에 연결할 때 `WSMan NetworkDelayms` 값을 늘린다는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-150">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="77f15-151">이 경고는 무시하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-151">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="77f15-152">Skype for Business Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-152">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="77f15-153">최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-153">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="77f15-154">이 명령을 실행하여 Exchange 온라인에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-154">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="77f15-155">전 세계 외의 Microsoft 365 클라우드용 Exchange 온라인에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-155">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   <span data-ttu-id="77f15-156">또는 이러한 명령을 실행하여 보안 &amp; 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-156">Alternatively, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="77f15-157">전 세계 이외의 Microsoft 365 클라우드에 대한 보안 &amp; 준수 센터에 연결하려면 [보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-157">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="77f15-158">다음 명령을 실행하여 Teams PowerShell에 연결하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-158">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="77f15-159">*전 세계* 이외의 Microsoft Teams 클라우드에 연결하려면 [연결-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f15-159">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="77f15-160">Azure Active Directory PowerShell for Grap 모듈</span><span class="sxs-lookup"><span data-stu-id="77f15-160">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="77f15-161">다음은 Azure Active Directory PowerShell for Graph 모듈을 사용하는 경우 단일 블록에서 *보안 &amp; 준수 센터를 제외한* 모든 서비스에 대한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-161">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="77f15-162">도메인 호스트의 이름을 지정하고 한 번에 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-162">Specify the name of your domain host and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="77f15-163">다음은Azure Active Directory PowerShell for Graph 모듈을 사용하는 경우 단일 블록에서 보안 *Exchange Online을 제외한* 모든 서비스에 대한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-163">Here are the commands for all the services *except Exchange Online* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="77f15-164">로그인을 위해 도메인 호스트 이름 및 UPN을 지정하고 한 번에 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-164">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="77f15-165">Windows PowerShell용 Microsoft Azure Active Directory 모듈</span><span class="sxs-lookup"><span data-stu-id="77f15-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="77f15-166">다음은 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하는 경우 단일 블록에서 *보안 &amp; 준수 센터를 제외한* 모든 서비스에 대한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-166">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="77f15-167">도메인 호스트의 이름을 지정하고 한 번에 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-167">Specify the name of your domain host and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="77f15-168">다음은 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하는 경우 단일 블록에서 *Exchange Online을 제외한* 모든 서비스에 대한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-168">Here are the commands for all the services *except Exchange Online* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="77f15-169">로그인을 위해 도메인 호스트 이름 및 UPN을 지정하고 한 번에 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-169">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="77f15-170">다단계 인증을 사용하는 경우 연결 단계</span><span class="sxs-lookup"><span data-stu-id="77f15-170">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="77f15-171">Graph 모듈용 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="77f15-171">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="77f15-172">다음은 Azure Active Directory PowerShell for Graph 모듈을 사용하는 다단계 인증과 함께 *보안 &amp; 준수 센터를 제외하고* 여러 Microsoft 365 서비스에 연결하는 단일 블록의 모든 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="77f15-173">다음은 Azure Active Directory PowerShell for Graph 모듈을 사용하는 다단계 인증과 함께 *Exchange Online을 제외하고* 여러 Microsoft 365 서비스에 연결하는 단일 블록의 모든 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-173">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication when you use the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="77f15-174">Windows PowerShell용 Microsoft Azure Active Directory 모듈</span><span class="sxs-lookup"><span data-stu-id="77f15-174">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="77f15-175">다음은 Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하는 다단계 인증과 함께 *보안 &amp; 준수 센터를 제외하고* 여러 Microsoft 365 서비스에 연결하는 단일 블록의 모든 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-175">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="77f15-176">다음은 Windows PowerShell용 Microsoft Azure Active Directory 모듈과 함께 다단계 인증을 사용하는 *Exchange Online을 제외하고* 여러 Microsoft 365 서비스에 연결하는 단일 블록의 모든 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-176">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="77f15-177">PowerShell 창 닫기</span><span class="sxs-lookup"><span data-stu-id="77f15-177">Close the PowerShell window</span></span>

<span data-ttu-id="77f15-178">PowerShell 창을 닫으려면 이 명령을 실행하여 비즈니스용 Skype 온라인, SharePoint Online 및 Teams에 대한 활성 세션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="77f15-178">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="77f15-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77f15-179">See also</span></span>

- [<span data-ttu-id="77f15-180">PowerShell로 Microsoft 365에 연결</span><span class="sxs-lookup"><span data-stu-id="77f15-180">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="77f15-181">PowerShell로 SharePoint 온라인 관리</span><span class="sxs-lookup"><span data-stu-id="77f15-181">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="77f15-182">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="77f15-182">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
