---
title: 추가 기능의 중앙 집중식 배포가 조직에 적합한지 확인
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 중앙 집중식 배포를 사용하여 추가 기능을 배포할 수 있도록 테넌트와 사용자가 요구 사항을 Office 확인합니다.
ms.openlocfilehash: 8f73deb1059097640946fcf7dad1ca97cb2831b1
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296722"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="1c7c1-103">추가 기능의 중앙 집중식 배포가 조직에 적합한지 확인</span><span class="sxs-lookup"><span data-stu-id="1c7c1-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="1c7c1-104">중앙 집중식 배포는 대부분의 고객이 조직 내의 사용자 및 그룹에 Office 추가 기능을 배포하는 데 권장되는 가장 다양한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="1c7c1-105">관리자인 경우 이 지침을 사용하여 조직 및 사용자가 중앙 집중식 배포를 사용할 수 있도록 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="1c7c1-106">중앙 집중식 배포는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="1c7c1-107">전역 관리자는 추가 기능을 사용자, 그룹을 통해 여러 사용자 또는 조직의 모든 사용자에게 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="1c7c1-108">관련 응용 Office 시작하면 추가 기능에서 자동으로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="1c7c1-109">추가 기능에서 추가 기능 명령을 지원하는 경우 추가 Office 응용 프로그램 내의 리본에 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="1c7c1-110">관리자가 추가 기능을 해제하거나 삭제하거나 사용자가 추가 기능을 Azure Active Directory 그룹에서 제거된 경우 더 이상 추가 기능을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="1c7c1-111">중앙 집중식 배포는 Mac 및 Windows 온라인 앱의 세 가지 데스크톱 Office 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="1c7c1-112">중앙 집중식 배포는 iOS 및 Android(모바일 Outlook 전용)도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="1c7c1-113">추가 기능을 모든 사용자의 클라이언트에 표시하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1c7c1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c7c1-114">Requirements</span></span>

<span data-ttu-id="1c7c1-115">추가 기능을 중앙 집중식으로 배포하려면 사용자가 Microsoft 365 Enterprise SKUS( E3/E5/F3 또는 Business SKUS: Business Basic, Business Standard, Business Premium(조직 ID를 사용하여 Office 로그인)를 사용하고 Exchange Online 및 활성 상태의 Exchange Online 사서함이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="1c7c1-116">구독 디렉터리가 에 있어야 합니다. 또는 구독 디렉터리에 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="1c7c1-117">아래에서 배포 및 Office 요구 Exchange 또는 중앙 집중식 배포 호환성 검사 를 사용할 [수 있습니다.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="1c7c1-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="1c7c1-118">중앙 집중식 배포는 다음을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="1c7c1-119">Office 2013에서 Word, Excel 또는 PowerPoint를 대상으로 하는 추가 기능</span><span class="sxs-lookup"><span data-stu-id="1c7c1-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="1c7c1-120">온-프레미스 디렉터리 서비스</span><span class="sxs-lookup"><span data-stu-id="1c7c1-120">An on-premises directory service</span></span>
- <span data-ttu-id="1c7c1-121">추가 기능 사서함에 Exchange 배포</span><span class="sxs-lookup"><span data-stu-id="1c7c1-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="1c7c1-122">SharePoint에 대한 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="1c7c1-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="1c7c1-123">Teams 앱</span><span class="sxs-lookup"><span data-stu-id="1c7c1-123">Teams apps</span></span>
- <span data-ttu-id="1c7c1-124">COM(구성 요소 개체 모델) 또는 Visual Studio Tools for Office(VSTO) 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="1c7c1-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="1c7c1-125">Microsoft 365 SKUS: Microsoft 365 앱 비즈니스용 Microsoft 365 앱 같은 Exchange Online 포함하지 않는 Microsoft 365 앱 배포 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="1c7c1-126">Office 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c7c1-126">Office Requirements</span></span>

- <span data-ttu-id="1c7c1-127">Word, Excel 및 PowerPoint 추가 기능의 경우 사용자가 다음 중 하나를 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="1c7c1-128">Windows SKUS 버전 1704 이상Microsoft 365 Enterprise E3/E5/F3 또는 Business SKUS: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="1c7c1-129">Mac 버전 15.34 이상.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="1c7c1-130">이 Outlook 사용자는 다음 중 하나를 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="1c7c1-131">버전 1701 이상Microsoft 365 Enterprise SKUS: E3/E5/F3 또는 Business SKUS: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="1c7c1-132">2019 또는 Office Professional Plus 2019 버전 Office Standard 버전 1808 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="1c7c1-133">MSI(버전 16.0.4494.1000 이상)Office Professional Plus 2016(MSI) 또는 Office Standard 2016(MSI)\*</span><span class="sxs-lookup"><span data-stu-id="1c7c1-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="1c7c1-134">MSI(Office Professional Plus 2013) 또는 Office Standard 2013(MSI) 버전 15.0.4937.1000 이상\*</span><span class="sxs-lookup"><span data-stu-id="1c7c1-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="1c7c1-135">버전 16.0.9318.1000 이상 Mac용 Office 2016</span><span class="sxs-lookup"><span data-stu-id="1c7c1-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="1c7c1-136">iOS용 모바일 Outlook 버전 2.75.0 이상</span><span class="sxs-lookup"><span data-stu-id="1c7c1-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="1c7c1-137">Android용 모바일 버전 2.2.145 Outlook 이상</span><span class="sxs-lookup"><span data-stu-id="1c7c1-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="1c7c1-138">\*MSI 버전의 Outlook "내 추가 기능" 섹션이 아니라 해당 Outlook 리본 메뉴에 관리자가 설치한 추가 기능을 보여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="1c7c1-139">Exchange Online 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c7c1-139">Exchange Online requirements</span></span>

<span data-ttu-id="1c7c1-140">Microsoft Exchange는 조직 테넌트 내의 매니페스트에 추가 기능을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="1c7c1-141">추가 기능을 배포하는 관리자와 이러한 추가 기능을 받는 사용자는 OAuth 인증을 지원하는 Exchange Online 버전에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="1c7c1-p106">조직의 Exchange 관리자에게 문의하여 사용 중인 구성을 확인합니다. 사용자당 OAuth 연결은 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet을 사용하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="1c7c1-144">중앙 집중식 배포 호환성 검사</span><span class="sxs-lookup"><span data-stu-id="1c7c1-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="1c7c1-145">중앙 집중식 배포 호환성 검사를 사용하여 테넌트의 사용자가 Word, 배포 및 배포에 대해 중앙 집중식 배포를 Excel PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="1c7c1-146">Outlook 지원에는 호환성 검사가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="1c7c1-147">[여기](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)에서 호환성 검사를 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="1c7c1-148">호환성 검사 실행</span><span class="sxs-lookup"><span data-stu-id="1c7c1-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="1c7c1-149">상승된 PowerShell.exe 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="1c7c1-150">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="1c7c1-151">**Invoke-CompatabilityCheck** 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="1c7c1-152">이 명령은  *_TenantDomain을_* 묻는 메시지를 표시합니다(예: *TailspinToysIncorporated.onmicrosoft). </span> com*) 및  *_TenantAdmin_* 자격 증명(전역 관리자 자격 증명 사용)을 입력한 다음 동의를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="1c7c1-153">테넌트의 사용자 수에 따라 검사를 완료하는 데 몇 분 또는 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="1c7c1-154">도구 실행이 완료되면 쉼표로 구분된(.csv) 형식으로 출력 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="1c7c1-155">파일은 기본적으로 **C:\windows\system32에** 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="1c7c1-156">출력 파일에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="1c7c1-157">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="1c7c1-157">User Name</span></span>
    
- <span data-ttu-id="1c7c1-158">사용자 ID(사용자의 전자 메일 주소)</span><span class="sxs-lookup"><span data-stu-id="1c7c1-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="1c7c1-159">중앙 집중식 배포 준비 - 나머지 항목이 충족된 경우</span><span class="sxs-lookup"><span data-stu-id="1c7c1-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="1c7c1-160">Office 계획 - 사용이 허가된 Office 계획</span><span class="sxs-lookup"><span data-stu-id="1c7c1-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="1c7c1-161">활성화된 Office - Office를 활성화한 경우</span><span class="sxs-lookup"><span data-stu-id="1c7c1-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="1c7c1-162">지원되는 사서함 - OAuth 지원 사서함을 사용 중인 경우</span><span class="sxs-lookup"><span data-stu-id="1c7c1-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="1c7c1-163">중앙 배포 PowerShell 모듈을 사용하는 경우 다단계 인증이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="1c7c1-164">사용자 및 그룹 할당</span><span class="sxs-lookup"><span data-stu-id="1c7c1-164">User and group assignments</span></span>

<span data-ttu-id="1c7c1-165">중앙 집중식 배포 기능은 현재 Azure Active Directory, 메일 그룹 및 보안 Azure Active Directory 그룹 등 대부분의 Microsoft 365 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c7c1-166">비 메일 사용 가능 보안 그룹은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="1c7c1-167">중앙 집중식 배포는 테넌트의 개별 사용자, 그룹 및 모든 사용자에게 할당을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="1c7c1-168">중앙 집중식 배포는 최상위 그룹 또는 부모 그룹이 없는 그룹의 사용자를 지원하지만, 중첩된 그룹 또는 부모 그룹이 있는 그룹의 사용자는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="1c7c1-p110">지민, 서연 및 영업부 그룹이 추가 기능에 할당된 다음 예제를 살펴봅니다. 서해안 영업부는 중첩된 그룹이므로 현준 및 배식은 추가 기능에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![영업 부서 다이어그램](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="1c7c1-172">그룹이 중첩된 그룹을 포함하는지 확인</span><span class="sxs-lookup"><span data-stu-id="1c7c1-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="1c7c1-173">그룹이 중첩된 그룹을 포함하는지를 검색하는 가장 쉬운 방법은 Outlook 내에서 그룹 연락처 카드를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="1c7c1-174">전자 메일의 To 필드에 그룹 이름을 입력한 다음 그룹 이름이 확인될 때 선택하면 그룹 이름이 사용자 또는 중첩된 그룹이 포함되어 있는 경우 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="1c7c1-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="1c7c1-175">아래 예에서 테스트 그룹에 대한 Outlook 연락처 카드의 **구성원** 탭에는 사용자는 표시되지 않고 하위 그룹 두 개만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![연락처 카드의 Outlook 탭](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="1c7c1-p112">그룹이 어떤 그룹의 구성원인지 확인하기 위해 그룹을 확인하여 반대 쿼리를 수행할 수 있습니다. 아래 예에서 하위 그룹 1이 테스트 그룹의 구성원인 Outlook 연락처 카드의 **구성원 자격** 탭 아래에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![연락처 카드의 Outlook 탭](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="1c7c1-p113">또는 Azure Active Directory Graph API를 사용하여 그룹 내의 그룹 목록을 찾기 위한 쿼리를 실행할 수 있습니다. 자세한 내용은 [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations)(그룹에 대한 작업 | Graph API 참조)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="1c7c1-182">Microsoft에 지원 요청</span><span class="sxs-lookup"><span data-stu-id="1c7c1-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="1c7c1-183">중앙에서 배포된 웹용 Office 앱(Word, Excel 등)을 사용하는 동안 추가 기능을 로드하는 데 문제가 발생하는 경우 Microsoft 지원에 문의해야 할 수 있습니다(방법[자세히).](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="1c7c1-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="1c7c1-184">지원 티켓의 Microsoft 365 환경에 대한 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="1c7c1-185">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="1c7c1-185">**Platform**</span></span>|<span data-ttu-id="1c7c1-186">**디버그 정보**</span><span class="sxs-lookup"><span data-stu-id="1c7c1-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1c7c1-187">Office</span><span class="sxs-lookup"><span data-stu-id="1c7c1-187">Office</span></span>  <br/> | <span data-ttu-id="1c7c1-188">Charles/Fiddler 로그</span><span class="sxs-lookup"><span data-stu-id="1c7c1-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="1c7c1-189">테넌트 ID( [방법 알아보기](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id))</span><span class="sxs-lookup"><span data-stu-id="1c7c1-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id))</span></span>  <br/>  <span data-ttu-id="1c7c1-190">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-190">CorrelationID.</span></span> <span data-ttu-id="1c7c1-191">사무실 페이지 중 하나의 원본을 보고 상관 관계 ID 값을 찾아서 지원에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7c1-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="1c7c1-192">리치 클라이언트(Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="1c7c1-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="1c7c1-193">Charles/Fiddler 로그</span><span class="sxs-lookup"><span data-stu-id="1c7c1-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="1c7c1-194">클라이언트 앱의 빌드 번호(파일/계정의 스크린샷으로 **가급적)**</span><span class="sxs-lookup"><span data-stu-id="1c7c1-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
