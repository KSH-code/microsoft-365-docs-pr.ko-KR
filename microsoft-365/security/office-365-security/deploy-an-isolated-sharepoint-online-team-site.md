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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 이 단계별 배포 가이드를 사용하여 365에서 격리된 SharePoint Online 팀 사이트를 Microsoft Office 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165502"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="21d82-103">격리된 SharePoint Online 팀 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="21d82-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="21d82-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="21d82-104">**Applies to**</span></span>
- [<span data-ttu-id="21d82-105">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="21d82-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="21d82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21d82-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="21d82-107">**요약:** 이러한 단계별 지침에 따라 격리된 새 SharePoint Online 팀 사이트를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="21d82-108">이 문서는 365에서 격리된 SharePoint Online 팀 사이트를 만들고 구성하기 위한 단계별 Microsoft Office 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-108">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="21d82-109">이러한 단계에서는 세 가지 기본 SharePoint 그룹 및 해당 권한 수준을 각 액세스 수준에 대해 단일 Azure AD(Active Directory) 기반 액세스 그룹과 함께 사용하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-109">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="21d82-110">1단계: 팀 사이트 액세스 그룹 만들기 및 채우기</span><span class="sxs-lookup"><span data-stu-id="21d82-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="21d82-111">이 단계에서는 세 가지 기본 SharePoint 그룹에 대해 세 개의 Azure AD 기반 액세스 그룹을 만들고 적절한 사용자 계정으로 채우습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="21d82-112">다음 단계에서는 필요한 모든 사용자 계정이 이미 있으며 적절한 라이선스가 할당되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-112">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="21d82-113">그렇지 않은 경우 1단계를 진행하기 전에 라이선스를 추가하고 라이선스를 할당하십시오.</span><span class="sxs-lookup"><span data-stu-id="21d82-113">If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="21d82-114">1단계: 사이트의 SharePoint Online 관리자 나열</span><span class="sxs-lookup"><span data-stu-id="21d82-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="21d82-115">격리된 팀 사이트의 SharePoint Online 관리자에 해당하는 사용자 계정 집합을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="21d82-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="21d82-116">Microsoft 365를 통해 사용자 계정 및 그룹을 관리하고 Windows PowerShell 사용하려는 경우 UPN(사용자 계정 이름)(예: UPN: belindan@contoso.com) 목록을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="21d82-117">2단계: 사이트의 구성원 나열</span><span class="sxs-lookup"><span data-stu-id="21d82-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="21d82-118">격리된 팀 사이트의 구성원, 사이트 내에 저장된 리소스에 대해 공동 작업할 구성원에 해당하는 사용자 계정 집합을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="21d82-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="21d82-119">Microsoft 365를 통해 사용자 계정 및 그룹을 관리하고 PowerShell을 사용하려는 경우 해당 UPNS 목록을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="21d82-120">사이트 구성원이 많은 경우 텍스트 파일에 UPNS 목록을 저장하고 모두 단일 PowerShell 명령으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="21d82-121">3단계: 사이트의 뷰어 나열</span><span class="sxs-lookup"><span data-stu-id="21d82-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="21d82-122">격리된 팀 사이트의 뷰어에 해당하는 사용자 계정 집합, 사이트에 저장된 리소스를 볼 수 있지만 해당 리소스를 수정하거나 콘텐츠에 대해 직접 공동 작업할 수 없는 사용자 계정 집합을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="21d82-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="21d82-123">Microsoft 365를 통해 사용자 계정 및 그룹을 관리하고 PowerShell을 사용하려는 경우 해당 UPNS 목록을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="21d82-124">사이트 구성원이 많은 경우 텍스트 파일에 UPNS 목록을 저장하고 모두 단일 PowerShell 명령으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="21d82-125">사이트의 뷰어에는 임원 관리, 법률 자문가 또는 부서 간 이해 관계자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="21d82-126">4단계: Azure AD에서 사이트에 대한 세 가지 액세스 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="21d82-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="21d82-127">Azure AD에서 다음 액세스 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="21d82-128">사이트 관리자(1단계의 목록 포함)</span><span class="sxs-lookup"><span data-stu-id="21d82-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="21d82-129">사이트 구성원(2단계의 목록 포함)</span><span class="sxs-lookup"><span data-stu-id="21d82-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="21d82-130">사이트 뷰어(3단계의 목록 포함)</span><span class="sxs-lookup"><span data-stu-id="21d82-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="21d82-131">브라우저에서 Azure Portal로 이동하여 사용자 관리 관리자 또는 회사 관리자 역할로 할당된 계정의 자격 증명으로 <https://portal.azure.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="21d82-132">Azure Portal에서 **Azure Active Directory > 그룹** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="21d82-133">**그룹 - 모든 그룹** 블레이드에서 **+ 새 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="21d82-134">새 **그룹 블레이드에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="21d82-135">**그룹 유형** 에서 **보안** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="21d82-136">이름에 그룹 이름을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="21d82-137">그룹 설명에 그룹에 대한 **설명을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="21d82-138">**멤버 유형** 에서 **할당됨** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="21d82-139">**만들기** 를 클릭한 다음 **그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="21d82-140">추가 그룹에 대해 3-5단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="21d82-141">Office 기능을 사용하도록 설정하려면 Azure Portal을 사용하여 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="21d82-142">격리된 SharePoint Online 사이트가 나중에 파일을 암호화하고 특정 그룹에 권한을 할당하기 위해 Azure Information Protection 레이블이 있는 기밀 사이트로 구성되는 경우 허용된 그룹은 Office 기능을 사용하도록 설정하여 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="21d82-143">Azure AD 그룹이 만들어진 후 Office 기능 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="21d82-144">다음은 세 개의 사이트 액세스 그룹을 구성한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-144">Here is your resulting configuration with the three site access groups.</span></span>

![격리된 SharePoint Online 사이트 배포를 위한 세 가지 액세스 그룹](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="21d82-146">5단계.</span><span class="sxs-lookup"><span data-stu-id="21d82-146">Step 5.</span></span> <span data-ttu-id="21d82-147">액세스 그룹에 사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="21d82-147">Add the user accounts to the access groups</span></span>

<span data-ttu-id="21d82-148">이 단계에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-148">In this step, do the following:</span></span>

1. <span data-ttu-id="21d82-149">1단계의 사용자 목록을 사이트 관리자 액세스 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="21d82-150">2단계의 사용자 목록을 사이트 구성원 액세스 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="21d82-151">3단계의 사용자 목록을 사이트 뷰어 액세스 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="21d82-152">AD DS(Active Directory 도메인 서비스)를 통해 사용자 계정 및 그룹을 관리하는 경우 일반 AD DS 사용자 및 그룹 관리 절차를 사용하여 적절한 액세스 그룹에 사용자를 추가하고 Microsoft 365 구독과의 동기화를 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="21d82-153">Office 365를 통해 사용자 계정 및 그룹을 관리하는 경우 Microsoft 365 관리 센터 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="21d82-154">액세스 그룹에 대해 그룹 이름이 중복된 경우 Microsoft 365 관리 센터를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="21d82-155">Microsoft 365 관리 센터의 경우 사용자 계정 관리자 또는 회사 관리자 역할이 할당된 사용자 계정으로 로그인하고 그룹을 사용하여 적절한 액세스 그룹에 적절한 사용자 계정 및 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="21d82-156">PowerShell의 경우 먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결합니다.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="21d82-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="21d82-157">다음으로, 다음 명령 블록을 사용하여 액세스 그룹에 개별 사용자 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="21d82-158">액세스 그룹의 UPNS를 텍스트 파일에 저장한 경우 다음 PowerShell 명령 블록을 사용하여 모두 한 번씩 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="21d82-159">PowerShell의 경우 다음 명령 블록을 사용하여 액세스 그룹에 개별 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="21d82-160">결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-160">The results should be the following:</span></span>

- <span data-ttu-id="21d82-161">사이트 관리자 Azure AD 그룹에 사이트 관리자 사용자 계정 또는 그룹이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="21d82-162">사이트 구성원 Azure AD 그룹에는 사이트 구성원 사용자 계정 또는 그룹이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="21d82-163">사이트 뷰어 Azure AD 그룹에는 사이트 콘텐츠만 볼 수 있는 사용자 계정 또는 그룹이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="21d82-164">Microsoft 365 관리 센터 또는 다음 PowerShell 명령 블록을 사용하여 각 액세스 그룹에 대한 그룹 구성원 목록의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="21d82-165">다음은 사용자 계정 또는 그룹으로 채워진 세 개의 사이트 액세스 그룹을 구성한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![사용자 계정으로 채워진 세 개의 액세스 그룹](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="21d82-167">2단계: 격리된 팀 사이트 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="21d82-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="21d82-168">이 단계에서는 격리된 SharePoint Online 사이트를 만들고 새 Azure AD 기반 액세스 그룹을 사용하도록 기본 SharePoint Online 권한 수준에 대한 사용 권한을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="21d82-169">기본적으로 새 팀 사이트에는 Microsoft 365 그룹 및 기타 관련 리소스가 포함되어 있지만, 이 경우 Microsoft 365 그룹 없이 팀 사이트를 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="21d82-170">따라서 SharePoint를 통해 사용 권한을 전적으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="21d82-171">먼저 다음 단계를 사용하여 SharePoint Online 팀 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="21d82-172">SharePoint Online 팀 사이트(SharePoint Online 관리자)를 관리하는 데 사용할 계정으로 Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="21d82-173">도움을 받으려면 [Office 365에 로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21d82-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="21d82-174">Microsoft 365 관리 센터의 **관리** 센터에서 **SharePoint를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="21d82-175">SharePoint 관리 센터에서 사이트를 **확장하고** 활성 **사이트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="21d82-176">만들기를 클릭한 다음 다른 **옵션을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="21d82-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="21d82-177">서식 **파일 선택 목록에서** 팀 **사이트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="21d82-178">사이트 **이름에** 팀 사이트의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="21d82-179">기본 **관리자에서** 로그인한 계정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="21d82-180">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-180">Click **Finish**.</span></span>

<span data-ttu-id="21d82-181">그런 다음 새 SharePoint Online 팀 사이트에서 사용 권한을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="21d82-182">도구 모음에서 설정 아이콘을 클릭한 다음, **사이트 사용 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="21d82-183">사이트 **공유에서** 구성원이 공유할 **수 있는 방법 변경을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="21d82-184">사이트 **소유자만 파일,** 폴더 및 사이트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="21d82-185">액세스 **허용 요청을 해제로** **설정**</span><span class="sxs-lookup"><span data-stu-id="21d82-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="21d82-186">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-186">Click **Save**.</span></span>

6. <span data-ttu-id="21d82-187">사용 권한 **창에서** 고급 사용 **권한 설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="21d82-188">브라우저의 **사용** 권한 탭에서 **\<site name> 목록의 구성원을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="21d82-189">**사용자 및 그룹** 에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="21d82-190">공유 **대화** 상자에서 사이트 구성원 액세스 그룹의 이름을 입력하고 선택한 다음 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="21d82-191">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="21d82-192">목록에서 **\<site name> 소유자를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="21d82-193">**사용자 및 그룹** 에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="21d82-194">공유 **대화** 상자에 사이트 관리자 액세스 그룹의 이름을 입력하고 해당 이름을 선택한 다음 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="21d82-195">브라우저에서 뒤로 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="21d82-196">목록에서 **\<site name> 방문자를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="21d82-197">**사용자 및 그룹** 에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="21d82-198">공유 **대화** 상자에 사이트 뷰어 액세스 그룹의 이름을 입력하고 선택한 다음 공유를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="21d82-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="21d82-199">브라우저의 **권한** 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="21d82-200">이러한 권한 설정의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="21d82-201">**\<site name> Owners** SharePoint 그룹에는 모든 구성원이 모든 권한 수준을 가지는 사이트 관리자 액세스 **그룹이** 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="21d82-202">Members **\<site name>** SharePoint 그룹에는 모든 구성원이 편집 권한 수준을 가지는 사이트 구성원 액세스 **그룹이** 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="21d82-203">**\<site name> Visitors** SharePoint 그룹에는 모든 구성원이 읽기 권한 수준을 가지는 사이트 뷰어 액세스 **그룹이** 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="21d82-204">구성원이 다른 구성원을 초대하거나 구성원이 아닌 구성원이 액세스를 요청하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="21d82-205">사용자 계정 또는 Azure AD 그룹으로 채워지는 세 가지 액세스 그룹을 사용하도록 구성된 사이트에 대한 세 개의 SharePoint 그룹이 있는 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![액세스 그룹 및 사용자 계정을 통해 격리된 SharePoint Online 사이트의 최종 구성](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="21d82-207">이제 사용자와 사이트 구성원은 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스를 사용하여 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d82-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="21d82-208">다음 단계</span><span class="sxs-lookup"><span data-stu-id="21d82-208">Next step</span></span>

<span data-ttu-id="21d82-209">사이트 액세스 그룹 구성원을 변경하거나 사용자 지정 권한이 있는 문서 폴더를 만들어야 하는 경우 격리된 SharePoint Online 팀 사이트 관리를 [참조하세요.](manage-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="21d82-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21d82-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21d82-210">See Also</span></span>

[<span data-ttu-id="21d82-211">격리된 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="21d82-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="21d82-212">격리된 SharePoint Online 팀 사이트 디자인</span><span class="sxs-lookup"><span data-stu-id="21d82-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="21d82-213">격리된 SharePoint Online 팀 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="21d82-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
