---
title: 단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
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
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307628"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="96878-103">단일 PowerShell 창에서 모든 Microsoft 365 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="96878-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="96878-104">PowerShell을 사용하여 Microsoft 365를 관리하는 경우 사용자 계정, SharePoint 온라인, Exchange 온라인, 비즈니스용 Skype 온라인, Microsoft Teams 및 보안 &amp; 규정 준수 관리에 해당하는 서로 다른 PowerShell 창에서 여러 PowerShell 세션을 동시에 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96878-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="96878-105">서비스 관리 창 간에 데이터를 교환할 수 없기 때문에 최적의 Microsoft 365 관리 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96878-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="96878-106">이 항목에서는 Microsoft 365 계정, 비즈니스용 Skype 온라인, Exchange 온라인, SharePoint 온라인, Microsoft Teams 및 보안 &amp; 준수 센터를 관리하는 데 사용할 수 있는 PowerShell의 단일 인스턴스를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="96878-107">현재 이 문서에는 전 세계(+GCC) 클라우드에 연결하는 명령만 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96878-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="96878-108">노트에서는 Microsoft 365 클라우드에 연결하는 방법에 대한 정보가 포함된 문서 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="96878-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="96878-109">Before you begin</span></span>

<span data-ttu-id="96878-110">단일 PowerShell 인스턴스에서 모든 Microsoft 365를 관리하려면 먼저 다음 필수 구성 요소를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="96878-111">이러한 절차에 사용하는 Microsoft 365회사 또는 학교 계정은 Microsoft 365 관리자 역할의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="96878-112">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="96878-113">이러한 Microsoft 365 PowerShell 요구 사항은 모든 Microsoft 365 서비스 요구 사항이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96878-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="96878-114">다음 64비트 Windows 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96878-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="96878-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="96878-115">Windows 10</span></span>
    
  - <span data-ttu-id="96878-116">Windows 8.1 또는 Windows 8</span><span class="sxs-lookup"><span data-stu-id="96878-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="96878-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="96878-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="96878-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="96878-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="96878-119">Windows Server 2012 R2 또는 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="96878-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="96878-120">Windows 7 SP1(서비스 팩 1)\*</span><span class="sxs-lookup"><span data-stu-id="96878-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="96878-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="96878-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="96878-122">\* Microsoft .NET Framework 4.5. *x*를 설치한 다음 Windows Management Framework 3.0 또는 Windows Management Framework 4.0을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="96878-123">자세한 내용은 [.NET Framework 설치](https://go.microsoft.com/fwlink/p/?LinkId=257868) 및 [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) 혹은 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="96878-124">비즈니스용 Skype 온라인과 하나의 Microsoft 365 모듈 요구 사항 때문에 64비트 버전의 Windows를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="96878-125">Azure Active Directory(Azure AD), Exchange 온라인, SharePoint 온라인, 비즈니스용 Skype 온라인 및 Teams에 필요한 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="96878-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="96878-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="96878-127">SharePoint Online 관리 셸</span><span class="sxs-lookup"><span data-stu-id="96878-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="96878-128">비즈니스용 Skype Online PowerShell 모듈</span><span class="sxs-lookup"><span data-stu-id="96878-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="96878-129">Exchange 온라인 PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="96878-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="96878-130">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="96878-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="96878-131">비즈니스용 Skype 온라인과 보안 &amp; 규정 준수 센터에 대해 서명된 스크립트를 실행하기 위해 PowerShell을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="96878-132">이렇게 하려면 다음 명령어를 상위 PowerShell 세션에서 실행하세요(**관리자 권한으로 실행**을 선택하여 연 PowerShell).</span><span class="sxs-lookup"><span data-stu-id="96878-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="96878-133">암호만 사용하는 경우 연결 단계</span><span class="sxs-lookup"><span data-stu-id="96878-133">Connection steps when using just a password</span></span>

<span data-ttu-id="96878-134">로그인에 암호만 사용 하는 경우 단일 PowerShell 창에서 모든 서비스에 연결 하기 위한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96878-134">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="96878-135">Windows PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96878-135">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="96878-136">이 명령을 실행하여 Microsoft 365 회사 또는 학교 계정 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-136">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="96878-137">이 명령을 실행하여 Graph 모듈인 Azure Active Directory PowerShell을 사용해 Azure AD에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-137">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="96878-138">또는 PowerShell 모듈용 Microsoft Azure Active Directory 모듈을 사용하는 경우라면 이 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-138">Alternately, if you are using the Microsoft Azure Active Directory Module for PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="96878-139">PowerShell Core는 PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol**이 있는 cmdlet을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96878-139">PowerShell Core does not support the Microsoft Azure Active Directory Module for PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="96878-140">이러한 cmdlet을 계속 사용하려면 PowerShell에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-140">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="96878-141">SharePoint 온라인에 연결 하려면 이 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-141">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="96878-142">도메인에 대한 조직 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-142">Specify the organization name for your domain.</span></span> <span data-ttu-id="96878-143">예를 들어 "litwareinc.onmicrosoft.com"의 경우 조직 이름 값은 "litwareinc"입니다.</span><span class="sxs-lookup"><span data-stu-id="96878-143">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="96878-144">비즈니스용 Skype 온라인에 연결하려면 다음 명령어를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-144">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="96878-145">`WSMan NetworkDelayms`값 증가에 대한 경고는 처음 연결 시 보여지지만 무시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-145">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="96878-146">이 명령을 실행하여 Exchange 온라인에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-146">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="96878-147">전 세계 외의 Microsoft 365 클라우드에 Exchange 온라인에 연결하려면 **-ExchangeEnvironmentName** 매개 변수를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-147">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="96878-148">자세한 내용은 [연결-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-148">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="96878-149">다음 명령을 실행하여 Teams PowerShell에 연결하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-149">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="96878-150">전 세계 이외의 Microsoft Teams 클라우드에 연결하려면 [연결-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-150">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="96878-151">다음 명령을 실행하여 보안 &amp; 준수 센터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-151">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="96878-152">전 세계 이외의 Microsoft 365 클라우드에 대한 보안 &amp; 준수 센터에 연결하려면 [PowerShell 보안 준수 센터에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-152">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="96878-153">다음은 Graph 모듈에 Azure Active Directory PowerShell을 사용하는 경우 단일 블록의 모든 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="96878-153">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="96878-154">도메인 호스트의 이름을 지정하고 한 번에 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-154">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="96878-155">또는, PowerShell 모듈에 Microsoft Azure Active Directory 모듈을 사용할 때 단일 블록에 있는 모든 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96878-155">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span> <span data-ttu-id="96878-156">도메인 호스트의 이름을 지정하고 한 번에 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="96878-157">PowerShell 창을 닫을 준비가 되면 다음 명령을 실행하여 비즈니스용 Skype 온라인, SharePoint 온라인, 보안 &amp; 규정 준수 센터 및 Teams에 대한 활성 세션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-157">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="96878-158">다단계 인증을 사용 하는 경우 연결 단계</span><span class="sxs-lookup"><span data-stu-id="96878-158">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="96878-159">단일 창에서 그래프 모듈에 Azure Active Directory PowerShell에 다단계 인증을 사용하는 Azure AD, SharePoint 온라인, 비즈니스용 Skype, Exchange 온라인 및 Teams에 연결하기 위해 사용하는 단일 블록의 모든 명령어입니다.</span><span class="sxs-lookup"><span data-stu-id="96878-159">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="96878-160">사용자 계정의 UPN(사용자 계정 이름) 이름과 도메인 호스트 이름을 지정하 고 한 번에 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96878-160">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="96878-161">또는 다음은 PowerShell 모듈용 Microsoft Azure Active Directory 모듈을 사용하는 경우의 모든 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="96878-161">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="96878-162">보안 &amp; 준수 센터에 대한 자세한 내용은 다단계 인증을 사용하여 [다단계 인증을 사용하는 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96878-162">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="96878-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96878-163">See also</span></span>

- [<span data-ttu-id="96878-164">PowerShell로 Microsoft 365에 연결</span><span class="sxs-lookup"><span data-stu-id="96878-164">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="96878-165">PowerShell로 SharePoint 온라인 관리</span><span class="sxs-lookup"><span data-stu-id="96878-165">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="96878-166">PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="96878-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
