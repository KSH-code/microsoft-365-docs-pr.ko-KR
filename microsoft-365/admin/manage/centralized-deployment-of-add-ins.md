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
ms.openlocfilehash: db5a9669464a9c4cb150dee119d8c0bcc2dc9833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399815"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="47e34-103">추가 기능의 중앙 집중식 배포가 조직에 맞게 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="47e34-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="47e34-104">중앙 집중식 배포는 대부분의 고객이 조직 내의 사용자 및 그룹에 Office 추가 기능을 배포 하는 데 권장 되 고 대부분의 기능을 많이 사용 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="47e34-105">관리자 인 경우이 지침을 사용 하 여 테 넌 트 및 사용자가 요구 사항을 충족 하는지 확인 하 여 중앙 집중식 배포를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="47e34-106">중앙 집중식 배포는 Windows, Mac, iOS, Android 및 온라인 Office 앱을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-106">Centralized Deployment supports Windows, Mac, iOS, Android and Online Office apps.</span></span>
<span data-ttu-id="47e34-107">모든 사용자에 대해 클라이언트에 대해 추가 기능을 표시 하는 데 최대 12 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-107">It can take up to 12 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="47e34-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47e34-108">Requirements</span></span>

<span data-ttu-id="47e34-109">추가 기능의 중앙 집중식 배포에서는 사용자가 Microsoft 365 앱 for enterprise (및 조직 ID를 사용 하 여 Office에 로그인)를 사용 하 고 있으며 Exchange Online 및 active Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-109">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="47e34-110">구독 디렉터리는 내에 있거나 Azure Active Directory에 페더레이션 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-110">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="47e34-111">아래의 Office 및 Exchange에 대 한 특정 요구 사항을 보거나 [중앙 집중식 배포 호환성 검사](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-111">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="47e34-112">중앙 집중식 배포는 다음을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-112">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="47e34-113">Office 2013에서 Word, Excel 또는 PowerPoint를 대상으로 하는 추가 기능</span><span class="sxs-lookup"><span data-stu-id="47e34-113">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="47e34-114">온-프레미스 디렉터리 서비스</span><span class="sxs-lookup"><span data-stu-id="47e34-114">An on-premises directory service</span></span>
    
- <span data-ttu-id="47e34-115">SharePoint에 대한 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="47e34-115">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="47e34-116">팀 앱</span><span class="sxs-lookup"><span data-stu-id="47e34-116">Teams apps</span></span>
   
- <span data-ttu-id="47e34-117">COM(구성 요소 개체 모델) 또는 VSTO(Visual Studio Tools for Office) 추가 기능의 배포</span><span class="sxs-lookup"><span data-stu-id="47e34-117">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="47e34-118">비즈니스를 위한 Microsoft 365 앱과 같은 Exchange를 포함 하지 않는 Microsoft 365 배포</span><span class="sxs-lookup"><span data-stu-id="47e34-118">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="47e34-119">Office 요구 사항</span><span class="sxs-lookup"><span data-stu-id="47e34-119">Office Requirements</span></span>

- <span data-ttu-id="47e34-120">Word, Excel 및 PowerPoint 추가 기능의 경우 사용자는 다음 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-120">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="47e34-121">Windows 장치에서 Microsoft 365 앱 for enterprise 버전 1704 이상에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-121">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="47e34-122">Mac의 경우 버전 15.34 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-122">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="47e34-123">Outlook의 경우 사용자는 다음 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-123">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="47e34-124">Enterprise 용 Microsoft 365 앱 버전 1701 이상</span><span class="sxs-lookup"><span data-stu-id="47e34-124">Version 1701 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="47e34-125">Office Professional Plus 2019 또는 Office Standard 2019 버전 1808 이상</span><span class="sxs-lookup"><span data-stu-id="47e34-125">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="47e34-126">Office Professional Plus 2016 (MSI) 또는 Office Standard 2016 (MSI) 버전 16.0.4494.1000 이상\*</span><span class="sxs-lookup"><span data-stu-id="47e34-126">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="47e34-127">Office Professional Plus 2013 (MSI) 또는 Office Standard 2013 (MSI) 버전 15.0.4937.1000 이상\*</span><span class="sxs-lookup"><span data-stu-id="47e34-127">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="47e34-128">Office 2016 for Mac의 버전 16.0.9318.1000 이상</span><span class="sxs-lookup"><span data-stu-id="47e34-128">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="47e34-129">IOS 용 Outlook mobile 이상 버전 2.75.0</span><span class="sxs-lookup"><span data-stu-id="47e34-129">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="47e34-130">Android 용 Outlook mobile의 버전 2.2.145 이상</span><span class="sxs-lookup"><span data-stu-id="47e34-130">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="47e34-131">\* MSI 버전의 Outlook에는 "내 추가 기능" 섹션이 아닌 해당 Outlook 리본 메뉴에 관리자가 설치한 추가 기능이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-131">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="47e34-132">Microsoft 365 for enterprise 앱이 설치 되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="47e34-132">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="47e34-133">Microsoft 365 Apps for enterprise를 사용 하려면 사용자에 게 Microsoft 365 계정이 있고 라이선스가 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-133">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="47e34-134">자세한 내용은 [Overview For Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47e34-134">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="47e34-135">사용자가 office 용 Microsoft 365 앱이 설치 되어 있고 최근에 사용 중인 경우 microsoft 365 관리 센터에서 사용할 수 있는 Microsoft Office 정품 인증 보고서를 사용 하는 것이 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-135">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="47e34-136">이 보고서는 지난 7 일, 30 일, 90 일 또는 180 일 이내에 엔터프라이즈 용 Microsoft 365 앱을 정품 인증 한 모든 사용자의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-136">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="47e34-137">중앙 집중식 배포를 위해 Windows 또는 Mac에 대한 데스크톱 정품 인증은 보고서의 중요 열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-137">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="47e34-138">보고서를 Excel로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-138">You can export the report to Excel.</span></span> <span data-ttu-id="47e34-139">보고서에 대 한 자세한 내용은 [관리 센터의 microsoft 365 보고서-Microsoft Office 정품 인증](../activity-reports/microsoft-office-activations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47e34-139">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="47e34-140">정품 인증 보고서를 사용 하지 않으려는 경우 사용자에 게 컴퓨터에서 Word와 같은 Office 응용 프로그램을 열도록 요청 하 고 **파일** \> **계정을**선택 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-140">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="47e34-141">다음 이미지에 표시 된 것 처럼 **제품 정보**아래에는 **구독 제품** 및 **Microsoft 365 for enterprise**가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-141">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**, as shown in the following image.</span></span>

![Office 응용 프로그램의 제품 정보](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="47e34-143">Microsoft 365 for enterprise 용 앱에 대 한 도움말을 보려면 [microsoft 365 앱 for Enterprise 문제 해결 팁](https://go.microsoft.com/fwlink/p/?linkid=846339)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="47e34-143">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="47e34-144">Exchange Online 요구 사항</span><span class="sxs-lookup"><span data-stu-id="47e34-144">Exchange Online requirements</span></span>

<span data-ttu-id="47e34-145">Microsoft Exchange는 조직 테넌트 내의 매니페스트에 추가 기능을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-145">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="47e34-146">추가 기능과 해당 추가 기능을 받는 사용자를 배포 하는 관리자는 OAuth 인증을 지 원하는 Exchange Online 버전에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-146">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="47e34-p107">조직의 Exchange 관리자에게 문의하여 사용 중인 구성을 확인합니다. 사용자당 OAuth 연결은 [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet을 사용하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-p107">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="47e34-149">중앙 집중식 배포 호환성 검사</span><span class="sxs-lookup"><span data-stu-id="47e34-149">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="47e34-150">중앙 집중식 배포 호환성 검사를 사용 하면 테 넌 트의 사용자가 Word, Excel 및 PowerPoint에 대해 중앙 집중식 배포를 사용 하도록 설정 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-150">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="47e34-151">Outlook 지원에는 호환성 검사가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-151">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="47e34-152">[여기](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)에서 호환성 검사를 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="47e34-152">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="47e34-153">호환성 검사 실행</span><span class="sxs-lookup"><span data-stu-id="47e34-153">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="47e34-154">관리자 권한 PowerShell 창을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-154">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="47e34-155">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-155">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="47e34-156">**CompatabilityCheck** 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-156">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="47e34-157">여기에는 *_Tenantdomain_* 을 묻는 메시지가 표시 됩니다 (예: *TailspinToysIncorporated. </span> com*) 및 *_TenantAdmin_* 자격 증명 (전역 관리자 자격 증명 사용)을 선택한 다음 동의를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-157">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="47e34-158">테넌트의 사용자 수에 따라 검사를 완료하는 데 몇 분 또는 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-158">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="47e34-159">도구 실행이 완료되면 쉼표로 구분된(.csv) 형식으로 출력 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-159">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="47e34-160">이 파일은 기본적으로에 지 해당 **system32** 에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-160">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="47e34-161">출력 파일에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-161">The output file contains the following information:</span></span>
  
- <span data-ttu-id="47e34-162">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="47e34-162">User Name</span></span>
    
- <span data-ttu-id="47e34-163">사용자 ID(사용자의 전자 메일 주소)</span><span class="sxs-lookup"><span data-stu-id="47e34-163">User ID (User's email address)</span></span>
    
- <span data-ttu-id="47e34-164">중앙 집중식 배포 준비 - 나머지 항목이 충족된 경우</span><span class="sxs-lookup"><span data-stu-id="47e34-164">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="47e34-165">Office 계획-사용이 허가 된 Office 계획</span><span class="sxs-lookup"><span data-stu-id="47e34-165">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="47e34-166">활성화된 Office - Office를 활성화한 경우</span><span class="sxs-lookup"><span data-stu-id="47e34-166">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="47e34-167">지원되는 사서함 - OAuth 지원 사서함을 사용 중인 경우</span><span class="sxs-lookup"><span data-stu-id="47e34-167">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="47e34-168">사용자 및 그룹 할당</span><span class="sxs-lookup"><span data-stu-id="47e34-168">User and group assignments</span></span>

<span data-ttu-id="47e34-169">중앙 집중식 배포 기능은 현재 Microsoft 365 그룹, 메일 그룹 및 보안 그룹과 같은 Azure Active Directory에서 지 원하는 대부분의 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-169">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47e34-170">비 메일 사용 가능 보안 그룹은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-170">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="47e34-171">중앙 집중식 배포에서는 개별 사용자, 그룹 및 테 넌 트의 모든 사용자에 대 한 할당을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-171">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="47e34-172">중앙 집중식 배포는 최상위 그룹 또는 부모 그룹이 없는 그룹의 사용자를 지원하지만, 중첩된 그룹 또는 부모 그룹이 있는 그룹의 사용자는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-172">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="47e34-p111">지민, 서연 및 영업부 그룹이 추가 기능에 할당된 다음 예제를 살펴봅니다. 서해안 영업부는 중첩된 그룹이므로 현준 및 배식은 추가 기능에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![영업 부서 다이어그램](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="47e34-176">그룹이 중첩된 그룹을 포함하는지 확인</span><span class="sxs-lookup"><span data-stu-id="47e34-176">Find out if a group contains nested groups</span></span>

<span data-ttu-id="47e34-177">그룹이 중첩된 그룹을 포함하는지를 검색하는 가장 쉬운 방법은 Outlook 내에서 그룹 연락처 카드를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-177">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="47e34-178">전자 메일의 **대상** 필드에 그룹 이름을 입력 하 고 확인할 때 그룹 이름을 선택 하는 경우에는 사용자 또는 중첩 그룹이 포함 되는지 여부를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-178">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="47e34-179">아래 예에서 테스트 그룹에 대한 Outlook 연락처 카드의 **구성원** 탭에는 사용자는 표시되지 않고 하위 그룹 두 개만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-179">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Outlook 연락처 카드의 구성원 탭](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="47e34-p113">그룹이 어떤 그룹의 구성원인지 확인하기 위해 그룹을 확인하여 반대 쿼리를 수행할 수 있습니다. 아래 예에서 하위 그룹 1이 테스트 그룹의 구성원인 Outlook 연락처 카드의 **구성원 자격** 탭 아래에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Outlook 연락처 카드의 멤버쉽 탭](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="47e34-p114">또는 Azure Active Directory Graph API를 사용하여 그룹 내의 그룹 목록을 찾기 위한 쿼리를 실행할 수 있습니다. 자세한 내용은 [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342)(그룹에 대한 작업 | Graph API 참조)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47e34-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="47e34-186">Microsoft에 지원 요청</span><span class="sxs-lookup"><span data-stu-id="47e34-186">Contacting Microsoft for support</span></span>

<span data-ttu-id="47e34-187">중앙에서 배포 된 웹 (Word, Excel 등)에 Office 앱을 사용 하는 동안 추가 기능을 로드 하는 동안 문제가 발생 하는 경우 Microsoft 지원 서비스에 문의 해야 할 수 있습니다 ([방법 배우기](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="47e34-187">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="47e34-188">지원 티켓에서 Microsoft 365 환경에 대 한 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-188">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="47e34-189">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="47e34-189">**Platform**</span></span>|<span data-ttu-id="47e34-190">**디버그 정보**</span><span class="sxs-lookup"><span data-stu-id="47e34-190">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="47e34-191">사무실</span><span class="sxs-lookup"><span data-stu-id="47e34-191">Office</span></span>  <br/> | <span data-ttu-id="47e34-192">Charles/Fiddler 로그</span><span class="sxs-lookup"><span data-stu-id="47e34-192">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="47e34-193">테넌트 ID( [방법 알아보기](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="47e34-193">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="47e34-194">관계.</span><span class="sxs-lookup"><span data-stu-id="47e34-194">CorrelationID.</span></span> <span data-ttu-id="47e34-195">Office 페이지 중 하나의 원본을 확인 하 고 상관 관계 ID 값을 확인 한 다음 지원에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="47e34-195">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="47e34-196">리치 클라이언트(Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="47e34-196">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="47e34-197">Charles/Fiddler 로그</span><span class="sxs-lookup"><span data-stu-id="47e34-197">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="47e34-198">클라이언트 응용 프로그램의 빌드 번호 ( **파일/계정의**스크린샷)</span><span class="sxs-lookup"><span data-stu-id="47e34-198">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

