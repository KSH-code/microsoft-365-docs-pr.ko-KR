---
title: 추가 기능의 중앙 집중식 배포가 조직에 맞게 작동 하는지 확인
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 중앙 집중식 배포를 사용 하 여 Office 추가 기능을 배포할 수 있도록 테 넌 트 및 사용자가 요구 사항을 충족 하는지 확인 합니다.
ms.openlocfilehash: c89cb801a5b2fcad87227feaf4228b0dcabcf609
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464053"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="38d73-103">추가 기능의 중앙 집중식 배포가 조직에 맞게 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="38d73-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="38d73-104">중앙 집중식 배포는 대부분의 고객이 조직 내의 사용자 및 그룹에 Office 추가 기능을 배포 하는 데 권장 되 고 대부분의 기능을 많이 사용 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="38d73-105">관리자 인 경우이 지침을 사용 하 여 조직 및 사용자가 요구 사항을 충족 하는지 여부를 확인 하 고 중앙 집중식 배포를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="38d73-106">중앙 집중식 배포는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="38d73-107">전역 관리자는 추가 기능을 사용자에 게 직접 할당 하거나, 그룹을 통해 여러 사용자에 게 또는 조직의 모든 사람에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="38d73-108">관련 Office 응용 프로그램이 시작 되 면 추가 기능이 자동으로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="38d73-109">추가 기능이 추가 기능 명령을 지 원하는 경우 Office 응용 프로그램의 리본 메뉴에 추가 기능이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="38d73-110">관리자가 추가 기능을 해제 하거나 삭제 하거나, 사용자가 Azure Active Directory 또는 추가 기능이 할당 된 그룹에서 제거 되는 경우 사용자에 게 더 이상 추가 기능이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="38d73-111">중앙 집중식 배포는 세 가지 데스크톱 플랫폼 Windows, Mac 및 온라인 Office 앱을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="38d73-112">또한 중앙 집중식 배포는 iOS 및 Android를 지원 합니다 (Outlook 모바일 추가 기능만 해당).</span><span class="sxs-lookup"><span data-stu-id="38d73-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="38d73-113">모든 사용자의 클라이언트에 대해 추가 기능을 표시 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="38d73-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38d73-114">Requirements</span></span>

<span data-ttu-id="38d73-115">추가 기능의 중앙 집중식 배포에서는 사용자가 Microsoft 365 앱 for enterprise 또는 Microsoft 365 Business Premium을 사용 하 고 있으며, 조직 ID를 사용 하 여 Office에 로그인 하 고, Exchange Online 및 active Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise, or Microsoft 365 Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="38d73-116">구독 디렉터리는 내에 있거나 Azure Active Directory에 페더레이션 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="38d73-117">아래의 Office 및 Exchange에 대 한 특정 요구 사항을 보거나 [중앙 집중식 배포 호환성 검사](#centralized-deployment-compatibility-checker)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="38d73-118">중앙 집중식 배포는 다음을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="38d73-119">Office 2013에서 Word, Excel 또는 PowerPoint를 대상으로 하는 추가 기능</span><span class="sxs-lookup"><span data-stu-id="38d73-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="38d73-120">온-프레미스 디렉터리 서비스</span><span class="sxs-lookup"><span data-stu-id="38d73-120">An on-premises directory service</span></span>
- <span data-ttu-id="38d73-121">Exchange 온-프레미스 사서함에 대 한 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="38d73-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="38d73-122">SharePoint에 대한 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="38d73-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="38d73-123">팀 앱</span><span class="sxs-lookup"><span data-stu-id="38d73-123">Teams apps</span></span>
- <span data-ttu-id="38d73-124">COM(구성 요소 개체 모델) 또는 VSTO(Visual Studio Tools for Office) 추가 기능의 배포</span><span class="sxs-lookup"><span data-stu-id="38d73-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
- <span data-ttu-id="38d73-125">비즈니스를 위한 Microsoft 365 앱과 같은 Exchange를 포함 하지 않는 Microsoft 365 배포</span><span class="sxs-lookup"><span data-stu-id="38d73-125">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="38d73-126">Office 요구 사항</span><span class="sxs-lookup"><span data-stu-id="38d73-126">Office Requirements</span></span>

- <span data-ttu-id="38d73-127">Word, Excel 및 PowerPoint 추가 기능의 경우 사용자는 다음 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="38d73-128">Windows 장치에서 Microsoft 365 Apps for enterprise 또는 Microsoft 365 Business Premium의 버전 1704 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-128">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise, or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="38d73-129">Mac의 경우 버전 15.34 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="38d73-130">Outlook의 경우 사용자는 다음 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="38d73-131">Microsoft 365 Apps for enterprise 또는 Microsoft 365 Business Premium 버전 1701 이상</span><span class="sxs-lookup"><span data-stu-id="38d73-131">Version 1701 or later of Microsoft 365 Apps for enterprise, or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="38d73-132">Office Professional Plus 2019 또는 Office Standard 2019 버전 1808 이상</span><span class="sxs-lookup"><span data-stu-id="38d73-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="38d73-133">Office Professional Plus 2016 (MSI) 또는 Office Standard 2016 (MSI) 버전 16.0.4494.1000 이상\*</span><span class="sxs-lookup"><span data-stu-id="38d73-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="38d73-134">Office Professional Plus 2013 (MSI) 또는 Office Standard 2013 (MSI) 버전 15.0.4937.1000 이상\*</span><span class="sxs-lookup"><span data-stu-id="38d73-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="38d73-135">Office 2016 for Mac의 버전 16.0.9318.1000 이상</span><span class="sxs-lookup"><span data-stu-id="38d73-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="38d73-136">IOS 용 Outlook mobile 이상 버전 2.75.0</span><span class="sxs-lookup"><span data-stu-id="38d73-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="38d73-137">Android 용 Outlook mobile의 버전 2.2.145 이상</span><span class="sxs-lookup"><span data-stu-id="38d73-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="38d73-138">\* MSI 버전의 Outlook에는 "내 추가 기능" 섹션이 아닌 해당 Outlook 리본 메뉴에 관리자가 설치한 추가 기능이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="38d73-139">Microsoft 365 for enterprise 앱이 설치 되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="38d73-139">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="38d73-140">Microsoft 365 Apps for enterprise를 사용 하려면 사용자에 게 Microsoft 365 계정이 있고 라이선스가 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-140">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="38d73-141">자세한 내용은 [Overview For Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38d73-141">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="38d73-142">사용자가 office 용 Microsoft 365 앱이 설치 되어 있고 최근에 사용 중인 경우 microsoft 365 관리 센터에서 사용할 수 있는 Microsoft Office 정품 인증 보고서를 사용 하는 것이 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-142">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="38d73-143">이 보고서는 지난 7 일, 30 일, 90 일 또는 180 일 이내에 엔터프라이즈 용 Microsoft 365 앱을 정품 인증 한 모든 사용자의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-143">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="38d73-144">중앙 집중식 배포를 위해 Windows 또는 Mac에 대한 데스크톱 정품 인증은 보고서의 중요 열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-144">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="38d73-145">보고서를 Excel로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-145">You can export the report to Excel.</span></span> <span data-ttu-id="38d73-146">보고서에 대 한 자세한 내용은 [관리 센터의 microsoft 365 보고서-Microsoft Office 정품 인증](../activity-reports/microsoft-office-activations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38d73-146">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="38d73-147">정품 인증 보고서를 사용 하지 않으려는 경우 사용자에 게 컴퓨터에서 Word와 같은 Office 응용 프로그램을 열도록 요청 하 고 **파일** \> **계정을**선택 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-147">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="38d73-148">**제품 정보**에는 다음 이미지에 표시 된 것과 비슷한 **구독 제품** 및 microsoft 365 Business Premium **for enterprise**또는 microsoft 365이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-148">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**,or Microsoft 365 Business Premium, similar to what is shown in the following image.</span></span>

![Office 응용 프로그램의 제품 정보](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="38d73-150">Microsoft 365 for enterprise 용 앱에 대 한 도움말을 보려면 [microsoft 365 앱 for Enterprise 문제 해결 팁](https://go.microsoft.com/fwlink/p/?linkid=846339)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38d73-150">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="38d73-151">Exchange Online 요구 사항</span><span class="sxs-lookup"><span data-stu-id="38d73-151">Exchange Online requirements</span></span>

<span data-ttu-id="38d73-152">Microsoft Exchange는 조직 테넌트 내의 매니페스트에 추가 기능을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-152">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="38d73-153">추가 기능과 해당 추가 기능을 받는 사용자를 배포 하는 관리자는 OAuth 인증을 지 원하는 Exchange Online 버전에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-153">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="38d73-p109">조직의 Exchange 관리자에게 문의하여 사용 중인 구성을 확인합니다. 사용자당 OAuth 연결은 [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet을 사용하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-p109">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="38d73-156">중앙 집중식 배포 호환성 검사</span><span class="sxs-lookup"><span data-stu-id="38d73-156">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="38d73-157">중앙 집중식 배포 호환성 검사를 사용 하면 테 넌 트의 사용자가 Word, Excel 및 PowerPoint에 대해 중앙 집중식 배포를 사용 하도록 설정 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-157">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="38d73-158">Outlook 지원에는 호환성 검사가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-158">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="38d73-159">[여기](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)에서 호환성 검사를 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="38d73-159">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="38d73-160">호환성 검사 실행</span><span class="sxs-lookup"><span data-stu-id="38d73-160">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="38d73-161">관리자 권한 PowerShell.exe 창을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-161">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="38d73-162">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-162">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="38d73-163">**CompatabilityCheck** 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-163">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="38d73-164">이 명령은  *_Tenantdomain_* (예: *TailspinToysIncorporated microsoft </span> )을 입력 하 라는 메시지를 표시 합니다. com*) 및  *_TenantAdmin_* 자격 증명 (전역 관리자 자격 증명 사용)을 선택한 다음 동의를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-164">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="38d73-165">테넌트의 사용자 수에 따라 검사를 완료하는 데 몇 분 또는 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-165">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="38d73-166">도구 실행이 완료되면 쉼표로 구분된(.csv) 형식으로 출력 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-166">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="38d73-167">이 파일은 기본적으로에 지 해당 **system32** 에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-167">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="38d73-168">출력 파일에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-168">The output file contains the following information:</span></span>
  
- <span data-ttu-id="38d73-169">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="38d73-169">User Name</span></span>
    
- <span data-ttu-id="38d73-170">사용자 ID(사용자의 전자 메일 주소)</span><span class="sxs-lookup"><span data-stu-id="38d73-170">User ID (User's email address)</span></span>
    
- <span data-ttu-id="38d73-171">중앙 집중식 배포 준비 - 나머지 항목이 충족된 경우</span><span class="sxs-lookup"><span data-stu-id="38d73-171">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="38d73-172">Office 계획-사용이 허가 된 Office 계획</span><span class="sxs-lookup"><span data-stu-id="38d73-172">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="38d73-173">활성화된 Office - Office를 활성화한 경우</span><span class="sxs-lookup"><span data-stu-id="38d73-173">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="38d73-174">지원되는 사서함 - OAuth 지원 사서함을 사용 중인 경우</span><span class="sxs-lookup"><span data-stu-id="38d73-174">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="38d73-175">중앙 배포 PowerShell 모듈을 사용 하는 경우에는 다단계 인증이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-175">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="38d73-176">사용자 및 그룹 할당</span><span class="sxs-lookup"><span data-stu-id="38d73-176">User and group assignments</span></span>

<span data-ttu-id="38d73-177">중앙 집중식 배포 기능은 현재 Microsoft 365 그룹, 메일 그룹 및 보안 그룹과 같은 Azure Active Directory에서 지 원하는 대부분의 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-177">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38d73-178">비 메일 사용 가능 보안 그룹은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-178">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="38d73-179">중앙 집중식 배포에서는 개별 사용자, 그룹 및 테 넌 트의 모든 사용자에 대 한 할당을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-179">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="38d73-180">중앙 집중식 배포는 최상위 그룹 또는 부모 그룹이 없는 그룹의 사용자를 지원하지만, 중첩된 그룹 또는 부모 그룹이 있는 그룹의 사용자는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-180">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="38d73-p113">지민, 서연 및 영업부 그룹이 추가 기능에 할당된 다음 예제를 살펴봅니다. 서해안 영업부는 중첩된 그룹이므로 현준 및 배식은 추가 기능에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-p113">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![영업 부서 다이어그램](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="38d73-184">그룹이 중첩된 그룹을 포함하는지 확인</span><span class="sxs-lookup"><span data-stu-id="38d73-184">Find out if a group contains nested groups</span></span>

<span data-ttu-id="38d73-185">그룹이 중첩된 그룹을 포함하는지를 검색하는 가장 쉬운 방법은 Outlook 내에서 그룹 연락처 카드를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-185">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="38d73-186">전자 메일의 **대상** 필드에 그룹 이름을 입력 하 고 확인할 때 그룹 이름을 선택 하는 경우에는 사용자 또는 중첩 그룹이 포함 되는지 여부를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-186">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="38d73-187">아래 예에서 테스트 그룹에 대한 Outlook 연락처 카드의 **구성원** 탭에는 사용자는 표시되지 않고 하위 그룹 두 개만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-187">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Outlook 연락처 카드의 구성원 탭](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="38d73-p115">그룹이 어떤 그룹의 구성원인지 확인하기 위해 그룹을 확인하여 반대 쿼리를 수행할 수 있습니다. 아래 예에서 하위 그룹 1이 테스트 그룹의 구성원인 Outlook 연락처 카드의 **구성원 자격** 탭 아래에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-p115">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Outlook 연락처 카드의 멤버쉽 탭](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="38d73-p116">또는 Azure Active Directory Graph API를 사용하여 그룹 내의 그룹 목록을 찾기 위한 쿼리를 실행할 수 있습니다. 자세한 내용은 [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342)(그룹에 대한 작업 | Graph API 참조)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38d73-p116">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="38d73-194">Microsoft에 지원 요청</span><span class="sxs-lookup"><span data-stu-id="38d73-194">Contacting Microsoft for support</span></span>

<span data-ttu-id="38d73-195">중앙에서 배포 된 웹 (Word, Excel 등)에 Office 앱을 사용 하는 동안 추가 기능을 로드 하는 동안 문제가 발생 하는 경우 Microsoft 지원 서비스에 문의 해야 할 수 있습니다 ([방법 배우기](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="38d73-195">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="38d73-196">지원 티켓에서 Microsoft 365 환경에 대 한 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-196">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="38d73-197">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="38d73-197">**Platform**</span></span>|<span data-ttu-id="38d73-198">**디버그 정보**</span><span class="sxs-lookup"><span data-stu-id="38d73-198">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38d73-199">사무실</span><span class="sxs-lookup"><span data-stu-id="38d73-199">Office</span></span>  <br/> | <span data-ttu-id="38d73-200">Charles/Fiddler 로그</span><span class="sxs-lookup"><span data-stu-id="38d73-200">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="38d73-201">테넌트 ID( [방법 알아보기](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="38d73-201">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="38d73-202">관계.</span><span class="sxs-lookup"><span data-stu-id="38d73-202">CorrelationID.</span></span> <span data-ttu-id="38d73-203">Office 페이지 중 하나의 원본을 확인 하 고 상관 관계 ID 값을 확인 한 다음 지원에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="38d73-203">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="38d73-204">리치 클라이언트(Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="38d73-204">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="38d73-205">Charles/Fiddler 로그</span><span class="sxs-lookup"><span data-stu-id="38d73-205">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="38d73-206">클라이언트 응용 프로그램의 빌드 번호 ( **파일/계정의**스크린샷)</span><span class="sxs-lookup"><span data-stu-id="38d73-206">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
