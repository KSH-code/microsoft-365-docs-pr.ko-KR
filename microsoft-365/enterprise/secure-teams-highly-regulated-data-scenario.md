---
title: 높은 규제 대상 데이터에 대한 Teams
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 안전한 팀을 만들어 중요하고 민감한 파일을 저장할 수 있습니다.
ms.openlocfilehash: 5117d310ccd877a7377e6e538e7fba13daaad4ef
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617266"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="f15c7-103">높은 규제 대상 데이터에 대한 Teams</span><span class="sxs-lookup"><span data-stu-id="f15c7-103">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="f15c7-104">이 문서에서는 개인 팀에 대해 Teams 기능(예: 채팅, 모임 및 파일)에 대한 액세스를 Office 365 그룹의 구성원과 소유자로 차단하는 개인 팀을 Microsoft Teams에서 구성하기 위한 권장 사항과 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="f15c7-105">Office 365 그룹을 기반으로 하는 개인 액세스를 넘어서, 이 문서에서는 기본 개인 SharePoint 팀 사이트를 구성하는 방법을 설명합니다. 여기서, 높은 규제 대상 데이터를 저장하는 데 필요한 추가 보안을 위해 팀 채널의 **파일** 섹션에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="f15c7-106">이 SharePoint 팀 사이트에서 파일, 페이지, 공유 일정, 작업, 전자 필기장 및 목록에 저장하고 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="f15c7-107">높은 규제 대상 데이터의 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="f15c7-108">소유자와 구성원 사용자 계정을 포함하는 해당 Office 365 그룹을 보유하고 있는 개인 팀입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="f15c7-109">팀을 위한 기본 SharePoint 사이트에 대 한 추가 보안:</span><span class="sxs-lookup"><span data-stu-id="f15c7-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="f15c7-110">사이트의 멤버가 다른 사람에게 액세스 권한을 부여하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="f15c7-111">사이트의 멤버 이외의 사용자가 다른 사람에게 액세스 권한을 요청하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="f15c7-112">보존 정책을 정의하는 기본 방법으로 사이트에 있는 새 파일에 자동으로 적용되는 기본 SharePoint 사이트의 Office 365 보존 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="f15c7-113">보존 레이블을 사용하고 사용자가 조직 외부에서 파일을 공유하거나 보내지 못하도록 차단하는 DLP(데이터 손실 방지) 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="f15c7-114">Office 365 민감도 레이블 또는 팀의 Office 365 그룹에 대해 암호화가 활성화되어 있고 공동 작성자 권한이 있는 높은 규제 대상 레이블의 하위 레이블.</span><span class="sxs-lookup"><span data-stu-id="f15c7-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="f15c7-115">Word, Excel 및 PowerPoint의 민감도 메뉴 모음 옵션에서 팀의 **파일** 섹션에 저장된 파일에 레이블이나 하위 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="f15c7-116">다음은 민감도 레이블이 포함된 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-116">Here is the resulting configuration with a sensitivity label.</span></span>

![보안 팀 시나리오 구성](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="configuration"></a><span data-ttu-id="f15c7-118">구성</span><span class="sxs-lookup"><span data-stu-id="f15c7-118">Configuration</span></span>

<span data-ttu-id="f15c7-119">보안 팀의 종단 간 구성은 다음 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-119">The end-to-end configuration of a secure team consists of these steps:</span></span>

1. <span data-ttu-id="f15c7-120">ID 및 디바이스 액세스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="f15c7-121">개인 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-121">Create a project team</span></span>
3. <span data-ttu-id="f15c7-122">추가 보안을 위해 기본 SharePoint 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="f15c7-123">보존 레이블과 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="f15c7-124">높은 규제 대상 레이블의 레이블 또는 하위 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="f15c7-125">1단계: ID 및 디바이스 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="f15c7-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="f15c7-126">팀 또는 해당 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하려면 [ID 및 디바이스 액세스 정책](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) 및 권장하는 [SharePoint Online 액세스 정책](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)</span><span class="sxs-lookup"><span data-stu-id="f15c7-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="f15c7-127">2단계: 개인 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="f15c7-127">Step 2: Create a private team</span></span>

<span data-ttu-id="f15c7-128">[이 지침](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)을 사용하여 개인 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="f15c7-129">개인 팀을 만들 때 기본 권한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="f15c7-130">팀의 Office 365 그룹(팀 그룹)에는 그룹 소유자와 그룹 구성원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="f15c7-131">팀(팀 사이트)의 기본 SharePoint 사이트:</span><span class="sxs-lookup"><span data-stu-id="f15c7-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="f15c7-132">사이트 모음 관리자가 팀 그룹 소유자에 대해 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="f15c7-133">팀 사이트:</span><span class="sxs-lookup"><span data-stu-id="f15c7-133">For the Team Site:</span></span> 
    - <span data-ttu-id="f15c7-134">팀 사이트 소유자 SharePoint 그룹([모든 권한] 사용 권한 수준 포함)은 팀 그룹 소유자로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="f15c7-135">팀 사이트 구성원 SharePoint 그룹(편집 사용 권한 수준 포함)은 팀 그룹 구성원으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="f15c7-136">팀 사이트 방문자 SharePoint 그룹(읽기 사용 권한 수준 포함)은 그룹 또는 사용자 계정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="f15c7-137">다음은 팀 사이트의 기본 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-137">Here are the default permissions for the Team Site.</span></span>

![팀 사이트의 기본 사용 권한](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="f15c7-139">편집 사용 권한 수준의 \<팀 이름> 소유자 SharePoint 그룹을 보는 경우, \<팀 이름> 소유자가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="f15c7-140">결과로 제공되는 권한을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="f15c7-141">팀 그룹 소유자가 사이트를 관리하고 사이트 콘텐츠를 전체적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="f15c7-142">팀 그룹 구성원이 사이트에서 파일을 만들고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="f15c7-143">사용 권한 유지 관리는 팀 구성원 및 소유자 유지 관리와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="f15c7-144">지금까지의 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-144">Here’s the resulting configuration so far.</span></span>

![보안 팀 시나리오 구성의 2단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="f15c7-146">3단계: 추가 보안을 위해 기본 SharePoint 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="f15c7-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="f15c7-147">팀 사이트에서 이 사용 권한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="f15c7-148">도구 모음에서 설정 아이콘을 클릭한 다음, **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="f15c7-149">**사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-149">In the **Site permissions** pane,, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="f15c7-150">**공유 사용 권한**에서 **사이트 소유자만 파일, 폴더 및 사이트 공유**를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="f15c7-151">**액세스 요청 허용**을 해제한 다음, **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="f15c7-152">이 설정을 사용하는 경우, 팀 그룹 구성원이 다른 구성원과 팀 사이트를 공유하거나 구성원이 아닌 사용자가 해당 팀 사이트의 액세스를 요청할 수 있는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="f15c7-153">지금까지의 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-153">Here’s the resulting configuration so far.</span></span>

![보안 팀 시나리오 구성의 3단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="f15c7-155">4단계: 보존 레이블 및 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f15c7-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="f15c7-156">[이 지침](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp)을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="f15c7-157">필요한 경우, 높은 규제 대상 데이터의 보존 레이블을 만들고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="f15c7-158">1단계에서 만든 보존 레이블에 맞게 팀 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="f15c7-159">2단계에서 만든 보존 레이블을 사용하고 사용자가 조직 외부에서 파일을 전송하지 못하도록 높은 규제 대상 데이터에 대한 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="f15c7-160">[DLP 정책 서식 파일](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates)을 기반으로, 상태 및 재무 산업 규제에 대한 정책와 같이 추가 요구 사항에 대한 정책을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="f15c7-161">지금까지의 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-161">Here’s the resulting configuration so far.</span></span>

![보안 팀 시나리오 구성의 4단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="f15c7-163">5단계: 해당 레이블 또는 높은 규제 대상 레이블의 하위 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="f15c7-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="f15c7-164">모든 사용자가 모든 파일에 적용할 수 있는 높은 규제 대상 데이터의 민감도 레이블과 달리, 할당된 파일이 다음을 수행하려면 보안 팀에 고유한 레이블이나 하위 레이블이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="f15c7-165">암호화되고 해당 암호화가 파일이 이동하는 경우에도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="f15c7-166">팀 그룹의 구성원만 파일을 열 수 있도록 사용자 지정 권한을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="f15c7-167">팀 사이트에 저장된 파일에 보안 수준을 추가적으로 설정하려면, 고유한 레이블 또는 높은 규제 대상 파일에 대한 일반적인 레이블의 하위 레이블인 새 민감도 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="f15c7-168">팀 그룹 구성원만 레이블 목록에서 해당 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="f15c7-169">전역 사용과 개별 개인 팀에 적은 수의 레이블이 필요한 경우에는 민감도 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-169">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="f15c7-170">다수의 레이블을 보유하고 있거나 높은 규제 대상 레이블 아래에 개인 팀의 레이블을 구성하려는 경우 민감도 하위 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="f15c7-171">[이 지침을 사용](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)하여 다음 설정으로 개별 레이블이나 하위 레이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="f15c7-172">레이블 이름에는 팀 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="f15c7-173">암호화가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-173">Encryption is enabled.</span></span>
- <span data-ttu-id="f15c7-174">팀 그룹에 공동 작성자 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="f15c7-175">새 레이블이 포함된 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-175">Here’s the resulting configuration with the new label.</span></span>

![보안 팀 시나리오 구성의 5단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="f15c7-177">민감도 레이블과 팀 그룹 사이의 관계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![팀 그룹과 레이블 사용 권한의 관계](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="f15c7-179">사용자 정의 사용 권한에 대해 또는 만료일을 포함하여 민감도 레이블이나 하위 레이블을 구성하는 경우, Teams 또는 SharePoint Online에서 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint Online.</span></span> <span data-ttu-id="f15c7-180">Office 앱을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-180">You must use an Office app.</span></span>
>

## <a name="using-the-team-and-a-sensitivity-label"></a><span data-ttu-id="f15c7-181">팀과 민감도 레이블 사용</span><span class="sxs-lookup"><span data-stu-id="f15c7-181">Using the team and a sensitivity label</span></span>

<span data-ttu-id="f15c7-182">팀 그룹의 구성원은 채팅, 모임 및 기타 앱을 포함하여 팀과 모든 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-182">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="f15c7-183">채널의 **파일** 섹션에서 파일에 대한 작업을 하는 경우, 팀 그룹의 구성원이 보안 팀을 위해 만든 파일에 민감도 레이블이나 하위 레이블을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-183">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="f15c7-184">다음은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-184">Here’s an example.</span></span>

![보안 팀에서 파일에 적용된 레이블의 예](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="f15c7-186">레이블이 해당 파일에 적용되는 경우, 파일이 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-186">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="f15c7-187">팀 그룹의 구성원이 실시간으로 Teams에서 파일을 열고 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-187">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="f15c7-188">파일이 암호화되며 팀 그룹 구성원으로 설정된 공동 작성자 권한을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-188">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="f15c7-189">파일이 사이트를 떠나 악의적인 사용자에게 전달되는 경우, 파일을 열고 콘텐츠를 보려면 팀 그룹의 구성원인 사용자 계정의 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-189">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="f15c7-190">SharePoint Online에서 폴더를 보고 **열 추가**의 **열 표시/숨기기** 옵션을 통해 **민감도** 열을 추가하여 레이블이 할당된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-190">You can see which files have a label assigned by viewing a folder in SharePoint Online and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

## <a name="custom-permissions"></a><span data-ttu-id="f15c7-191">사용자 지정 권한</span><span class="sxs-lookup"><span data-stu-id="f15c7-191">Custom permissions</span></span>

<span data-ttu-id="f15c7-192">팀 사이트의 사용자 지정 SharePoint 사이트 사용 권한을 구성하고, 필요한 경우 해당 민감도 레이블을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-192">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="f15c7-193">다음은 이와 관련된 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-193">Here are two examples:</span></span>

### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="f15c7-194">예제 1: SharePoint 사이트 관리 위임</span><span class="sxs-lookup"><span data-stu-id="f15c7-194">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="f15c7-195">팀 소유자가 SharePoint 관리 경험이 없거나 팀 사이트의 관리를 위임하려는 경우, SharePoint 관리자의 사용자 계정을 팀 소유자 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-195">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="f15c7-196">그러나 SharePoint 관리자는 팀과 모든 해당 리소스에 대한 전체 액세스 권한을 갖게 되고 민감도 레이블이 적용된 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-196">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="f15c7-197">권한을 초과하여 부여하지 않도록 하려면, 해당 사이트의 고급 사용 권한 설정에서 SharePoint 관리자의 사용자 계정을 팀 사이트 소유자 SharePoint 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-197">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="f15c7-198">SharePoint 관리자가 사이트를 관리할 수는 있지만, 팀과 해당 리소스에 액세스할 수 없으며 민감도 레이블이 지정된 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-198">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="f15c7-199">예제 2: 레이블이 지정된 파일에 대해 보기 전용 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="f15c7-199">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="f15c7-200">일부 직원만 팀 사이트에서 레이블이 지정된 파일의 내용을 보아야 하는 경우, 개별 사용자 계정을 </span><span class="sxs-lookup"><span data-stu-id="f15c7-200">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="f15c7-201">기본적으로 읽기 사용 권한이 있는 \<팀 이름 > 방문자 SharePoint 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-201">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="f15c7-202">뷰어 권한이 있는 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-202">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="f15c7-203">다음은 레이블의 결과 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-203">Here are the resulting permissions on the label.</span></span>

![레이블이 지정된 파일을 볼 수 있도록 사용자 지정된 권한의 예](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="f15c7-205">사이트 방문자는 팀 사이트에 바로 액세스하고 하위 레이블이 적용된 파일의 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-205">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="f15c7-206">그러나 팀 그룹의 구성원이 아니므로, 팀 또는 해당 리소스에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f15c7-206">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="f15c7-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f15c7-207">See also</span></span>

[<span data-ttu-id="f15c7-208">높은 규제 대상 데이터를 위한 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="f15c7-208">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="f15c7-209">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="f15c7-209">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
