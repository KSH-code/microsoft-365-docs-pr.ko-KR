---
title: 격리된 SharePoint Online 팀 사이트 배포
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 이 단계별 배포 가이드를 사용 하 여 Microsoft Office 365에서 격리 된 SharePoint Online 팀 사이트를 만들고 구성 합니다.
ms.openlocfilehash: 3465ec28db8c2045bad6e6c48112861818629524
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308418"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="8876f-103">격리된 SharePoint Online 팀 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="8876f-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="8876f-104">**요약:** 다음 단계별 지침을 사용 하 여 격리 된 SharePoint Online 팀 사이트를 새로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="8876f-105">이 문서는 Microsoft Office 365에서 격리 된 SharePoint Online 팀 사이트를 만들고 구성 하기 위한 단계별 배포 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="8876f-106">이러한 단계에서는 각 액세스 수준에 대해 단일 Azure Active Directory (AD) 기반 액세스 그룹을 사용 하 여 세 가지 기본 SharePoint 그룹 및 해당 사용 권한 수준을 사용할 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="8876f-107">1 단계: 팀 사이트 액세스 그룹 만들기 및 채우기</span><span class="sxs-lookup"><span data-stu-id="8876f-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="8876f-108">이 단계에서는 세 가지 기본 SharePoint 그룹에 대 한 세 개의 Azure AD 기반 액세스 그룹을 만들고 적절 한 사용자 계정으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8876f-109">다음 단계에서는 필요한 모든 사용자 계정이 이미 있고 해당 라이선스가 할당 된 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="8876f-110">그렇지 않은 경우 1 단계를 진행 하기 전에 추가 하 고 라이선스를 할당 하세요.</span><span class="sxs-lookup"><span data-stu-id="8876f-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="8876f-111">1 단계: 사이트에 대 한 SharePoint Online 관리자 나열</span><span class="sxs-lookup"><span data-stu-id="8876f-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="8876f-112">격리 된 팀 사이트에 대 한 SharePoint Online 관리자에 해당 하는 사용자 계정 집합을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="8876f-113">Microsoft 365을 통해 사용자 계정 및 그룹을 관리 하는 경우 Windows PowerShell을 사용 하려면 upn (사용자 계정 이름) 목록 (예: belindan@contoso.com)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="8876f-114">2 단계: 사이트 구성원 나열</span><span class="sxs-lookup"><span data-stu-id="8876f-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="8876f-115">사이트 내에 저장 된 리소스에 대해 공동으로 작업할 격리 된 팀 사이트의 구성원에 해당 하는 사용자 계정 집합을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="8876f-116">Microsoft 365을 통해 사용자 계정 및 그룹을 관리 하는 경우 PowerShell을 사용 하려면 Upn 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="8876f-117">사이트 구성원이 많은 경우에는 Upn 목록을 텍스트 파일에 저장 하 고 모두 단일 PowerShell 명령을 사용 하 여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="8876f-118">3 단계: 사이트에 대 한 보는 사람 나열</span><span class="sxs-lookup"><span data-stu-id="8876f-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="8876f-119">격리 된 팀 사이트의 보는 사람에 해당 하는 사용자 계정 집합 (사이트에 저장 된 리소스를 볼 수는 있지만 수정 하거나 콘텐츠를 직접 공동으로 작업 하지는 않는 경우)을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="8876f-120">Microsoft 365을 통해 사용자 계정 및 그룹을 관리 하는 경우 PowerShell을 사용 하려면 Upn 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="8876f-121">사이트 구성원이 많은 경우에는 Upn 목록을 텍스트 파일에 저장 하 고 모두 단일 PowerShell 명령을 사용 하 여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="8876f-122">사이트 보기에는 임원 관리, 법률 자문 위원 또는 부서별 부서 간 이해 관계자가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="8876f-123">4 단계: Azure AD에서 사이트에 대 한 세 개의 액세스 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="8876f-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="8876f-124">Azure AD에서 다음 액세스 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="8876f-125">사이트 관리자 (1 단계에서 목록이 포함 됨)</span><span class="sxs-lookup"><span data-stu-id="8876f-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="8876f-126">사이트 구성원 (2 단계에서 목록이 포함 됨)</span><span class="sxs-lookup"><span data-stu-id="8876f-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="8876f-127">사이트 뷰어 (3 단계의 목록이 포함 됨)</span><span class="sxs-lookup"><span data-stu-id="8876f-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="8876f-128">브라우저에서 Azure 포털로 이동한 [https://portal.azure.com](https://portal.azure.com) 후 사용자 관리 관리자 또는 회사 관리자 역할로 할당 된 계정의 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="8876f-129">Azure Portal에서 **Azure Active Directory > 그룹**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="8876f-130">**그룹 - 모든 그룹** 블레이드에서 **+ 새 그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="8876f-131">**새 그룹** 블레이드에서 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="8876f-132">**그룹 유형**에서 **보안**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="8876f-133">**이름**에 그룹 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="8876f-134">그룹 **설명**에 그룹에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="8876f-135">**멤버 유형**에서 **할당됨**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="8876f-136">**만들기**를 클릭한 다음 **그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="8876f-137">추가 그룹에 대해 3-5 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8876f-138">Office 기능을 사용 하도록 설정 하려면 Azure portal을 사용 하 여 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="8876f-139">SharePoint Online 격리 된 사이트가 파일을 암호화 하 고 특정 그룹에 사용 권한을 할당 하기 위해 Azure Information Protection 레이블을 사용 하 여 고도로 기밀 사이트로 구성 된 경우에는 허용 되는 그룹이 Office 기능을 사용 하도록 설정 된 상태로 만들어져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="8876f-140">Azure AD 그룹을 만든 후에는 Office 기능 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="8876f-141">다음은 세 개의 사이트 액세스 그룹이 포함 된 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![격리 된 SharePoint Online 사이트 배포에 대 한 세 가지 액세스 그룹](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="8876f-143">5단계.</span><span class="sxs-lookup"><span data-stu-id="8876f-143">Step 5.</span></span> <span data-ttu-id="8876f-144">액세스 그룹에 사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="8876f-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="8876f-145">이 단계에서는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="8876f-146">1 단계의 사용자 목록을 site admins 액세스 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="8876f-147">2 단계의 사용자 목록을 사이트 구성원 액세스 그룹에 추가</span><span class="sxs-lookup"><span data-stu-id="8876f-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="8876f-148">3 단계의 사용자 목록을 사이트 뷰어 액세스 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="8876f-149">AD DS (Active Directory 도메인 서비스)를 통해 사용자 계정 및 그룹을 관리 하는 경우에는 일반 AD DS 사용자 및 그룹 관리 절차를 사용 하 여 해당 액세스 그룹에 사용자를 추가 하 고 Microsoft 365 구독에 대 한 동기화를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="8876f-150">Office 365을 통해 사용자 계정 및 그룹을 관리 하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="8876f-151">액세스 그룹의 그룹 이름이 중복 된 경우 Microsoft 365 관리 센터를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="8876f-152">Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당 된 사용자 계정으로 로그인 하 고 그룹을 사용 하 여 적절 한 액세스 그룹에 적절 한 사용자 계정 및 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="8876f-153">PowerShell의 경우 먼저 [Graph 모듈에 대 한 Azure Active Directory PowerShell을 사용 하 여 연결](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="8876f-154">다음으로, 다음 명령 블록을 사용 하 여 액세스 그룹에 개별 사용자 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="8876f-155">텍스트 파일의 액세스 그룹에 대 한 사용자 계정의 Upn을 저장 한 경우 다음 PowerShell 명령 블록을 사용 하 여 모든 항목을 한 번에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="8876f-156">PowerShell의 경우 다음 명령 블록을 사용 하 여 액세스 그룹에 개별 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="8876f-157">결과는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-157">The results should be the following:</span></span>
  
- <span data-ttu-id="8876f-158">Site admins Azure AD 그룹에는 사이트 관리자 사용자 계정 또는 그룹이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="8876f-159">사이트 구성원 Azure AD 그룹에는 사이트 구성원 사용자 계정 또는 그룹이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="8876f-160">사이트 뷰어 Azure AD 그룹에는 사이트 콘텐츠만 볼 수 있는 사용자 계정 또는 그룹이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="8876f-161">다음 PowerShell 명령 블록을 사용 하거나 Microsoft 365 관리 센터를 사용 하 여 각 액세스 그룹의 그룹 구성원 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="8876f-162">다음은 사용자 계정이 나 그룹으로 채워진 3 개의 사이트 액세스 그룹이 포함 된 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![세 개의 액세스 그룹은 사용자 계정으로 채워집니다.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="8876f-164">2 단계: 격리 된 팀 사이트 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="8876f-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="8876f-165">이 단계에서는 격리 된 SharePoint Online 사이트를 만들고 기본 SharePoint Online 권한 수준에 대 한 사용 권한을 구성 하 여 새 Azure AD 기반 액세스 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="8876f-166">기본적으로 새 팀 사이트에는 Microsoft 365 그룹 및 기타 관련 리소스가 포함 되어 있지만이 경우 Microsoft 365 그룹 없이 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="8876f-167">이렇게 하면 SharePoint를 통해 사용 권한을 완전히 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="8876f-168">먼저 다음 단계를 사용 하 여 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="8876f-169">SharePoint Online 팀 사이트를 관리 하는 데 사용할 계정 (SharePoint Online 관리자)을 사용 하 여 Microsoft 365 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="8876f-170">도움을 받으려면 [Office 365에 로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8876f-170">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="8876f-171">Microsoft 365 관리 센터의 **관리 센터**에서 **SharePoint**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="8876f-172">SharePoint 관리 센터에서 **사이트** 를 확장 하 고 **활성 사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="8876f-173">**만들기**를 클릭 한 다음 **기타 옵션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="8876f-174">**서식 파일 선택** 목록에서 **팀 사이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="8876f-175">**사이트 이름**에 팀 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="8876f-176">**기본 관리자**에서 로그인 한 계정을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="8876f-177">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-177">Click **Finish**.</span></span>
    
<span data-ttu-id="8876f-178">다음으로, 새 SharePoint Online 팀 사이트에서 사용 권한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="8876f-179">도구 모음에서 설정 아이콘을 클릭한 다음, **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="8876f-180">**사이트 공유**에서 구성원의 **공유 방법을 변경**합니다 .를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="8876f-181">**사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="8876f-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="8876f-182">**액세스 허용 요청** 을 **해제**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="8876f-183">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="8876f-184">**사용 권한** 창에서 **고급 사용 권한 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="8876f-185">브라우저의 **사용 권한** 탭에 있는 목록에서 \*\* \<site name> 구성원\*\* 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="8876f-186">**사용자 및 그룹**에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="8876f-187">**공유** 대화 상자에서 사이트 구성원 액세스 그룹의 이름을 입력 하 고,이를 선택한 다음, **공유**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="8876f-188">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="8876f-189">목록에서 \*\* \<site name> 소유자\*\* 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="8876f-190">**사용자 및 그룹**에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="8876f-191">**공유** 대화 상자에서 site admins 액세스 그룹의 이름을 입력 하 고,이를 선택한 다음, **공유**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="8876f-192">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="8876f-193">목록에서 \*\* \<site name> 방문자\*\* 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="8876f-194">**사용자 및 그룹**에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="8876f-195">**공유** 대화 상자에서 사이트 뷰어 액세스 그룹의 이름을 입력 하 고,이를 선택한 다음, **공유**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="8876f-196">브라우저의 **권한** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="8876f-197">이러한 권한 설정의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="8876f-198">\*\* \<site name> 소유자\*\* SharePoint 그룹에 **는 모든 구성원이 모든 권한 수준을** 갖는 사이트 관리자 액세스 그룹이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="8876f-199">\*\* \<site name> Members\*\* SharePoint 그룹에는 모든 구성원이 **편집** 권한 수준을 갖는 사이트 구성원 액세스 그룹이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="8876f-200">\*\* \<site name> 방문자\*\* SharePoint 그룹에는 모든 구성원이 **읽기** 권한 수준을 갖는 사이트 뷰어 액세스 그룹이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="8876f-201">구성원이 다른 구성원을 초대 하거나 구성원이 아닌 사람에 게 액세스를 요청 하는 기능은 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="8876f-202">다음은 사용자 계정 또는 Azure AD 그룹으로 채워지는 세 개의 액세스 그룹을 사용 하도록 구성 된 사이트에 대 한 세 가지 SharePoint 그룹의 구성 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![액세스 그룹과 사용자 계정을 사용 하는 격리 된 SharePoint Online 사이트의 최종 구성](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="8876f-204">액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 구성원은 이제 사이트의 리소스를 사용 하 여 공동 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8876f-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="8876f-205">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8876f-205">Next step</span></span>

<span data-ttu-id="8876f-206">사이트 액세스 그룹 구성원 자격을 변경 하거나 사용자 지정 사용 권한이 있는 문서 폴더를 만들려면 [격리 된 SharePoint Online 팀 사이트 관리](manage-an-isolated-sharepoint-online-team-site.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8876f-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8876f-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8876f-207">See Also</span></span>

[<span data-ttu-id="8876f-208">격리된 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="8876f-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="8876f-209">격리된 SharePoint Online 팀 사이트 디자인</span><span class="sxs-lookup"><span data-stu-id="8876f-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="8876f-210">격리된 SharePoint Online 팀 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="8876f-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



