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
ms.openlocfilehash: 4ef4d4e9b8ab437c90aac434db158cfb40f066cb
ms.sourcegitcommit: 7ee256132358a86f8c6ad143816fcfdde011ca74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "37628352"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="2a080-103">높은 규제 대상 데이터에 대한 Teams</span><span class="sxs-lookup"><span data-stu-id="2a080-103">Teams for highly regulated data</span></span>

<span data-ttu-id="2a080-104">이 문서에서는 개인 팀에 대해 Teams 기능(예: 채팅, 모임 및 파일)에 대한 액세스를 Office 365 그룹의 구성원과 소유자로 차단하는 개인 팀을 Microsoft Teams에서 구성하기 위한 권장 사항과 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="2a080-105">Office 365 그룹을 기반으로 하는 개인 액세스를 넘어서, 이 문서에서는 기본 개인 SharePoint 팀 사이트를 구성하는 방법을 설명합니다. 여기서, 높은 규제 대상 데이터를 저장하는 데 필요한 추가 보안을 위해 팀 채널의 **파일** 섹션에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="2a080-106">이 SharePoint 팀 사이트에서 파일, 페이지, 공유 일정, 작업, 전자 필기장 및 목록에 저장하고 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="2a080-107">높은 규제 대상 데이터의 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="2a080-108">소유자와 구성원 사용자 계정을 포함하는 해당 Office 365 그룹을 보유하고 있는 개인 팀입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="2a080-109">팀을 위한 기본 SharePoint 사이트에 대 한 추가 보안:</span><span class="sxs-lookup"><span data-stu-id="2a080-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="2a080-110">사이트의 멤버가 다른 사람에게 액세스 권한을 부여하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="2a080-111">사이트의 멤버 이외의 사용자가 다른 사람에게 액세스 권한을 요청하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="2a080-112">보존 정책을 정의하는 기본 방법으로 사이트에 있는 새 파일에 자동으로 적용되는 기본 SharePoint 사이트의 Office 365 보존 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="2a080-113">보존 레이블을 사용하고 사용자가 조직 외부에서 파일을 공유하거나 보내지 못하도록 차단하는 DLP(데이터 손실 방지) 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="2a080-114">Office 365 민감도 레이블 또는 팀의 Office 365 그룹에 대해 암호화가 활성화되어 있고 공동 작성자 권한이 있는 높은 규제 대상 레이블의 하위 레이블.</span><span class="sxs-lookup"><span data-stu-id="2a080-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="2a080-115">Word, Excel 및 PowerPoint의 민감도 메뉴 모음 옵션에서 팀의 **파일** 섹션에 저장된 파일에 레이블이나 하위 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="2a080-116">다음은 민감도 레이블이 포함된 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-116">Here is the resulting configuration with a sensitivity label.</span></span>

![보안 팀 시나리오 구성](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="2a080-118">1단계: 고도로 규제된 데이터를 위한 팀 구성</span><span class="sxs-lookup"><span data-stu-id="2a080-118">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="2a080-119">보안 팀의 엔드 투 엔드 (End-to-end) 구성은 다음의 단계로 구성됩니다:</span><span class="sxs-lookup"><span data-stu-id="2a080-119">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="2a080-120">ID 및 장치 액세스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="2a080-121">개인 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-121">Create a project team</span></span>
3. <span data-ttu-id="2a080-122">추가 보안을 위해 기본 SharePoint 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="2a080-123">보존 레이블과 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="2a080-124">높은 규제 대상 레이블의 레이블 또는 하위 레이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="2a080-125">1단계: ID 및 디바이스 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="2a080-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="2a080-126">팀 또는 해당 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하려면 [ID 및 디바이스 액세스 정책](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) 및 권장하는 [SharePoint Online 액세스 정책](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)</span><span class="sxs-lookup"><span data-stu-id="2a080-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="2a080-127">2단계: 개인 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="2a080-127">Step 2: Create a private team</span></span>

<span data-ttu-id="2a080-128">[이 지침](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)을 사용하여 개인 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="2a080-129">개인 팀을 만들 때 기본 권한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="2a080-130">팀의 Office 365 그룹(팀 그룹)에는 그룹 소유자와 그룹 구성원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="2a080-131">팀(팀 사이트)의 기본 SharePoint 사이트:</span><span class="sxs-lookup"><span data-stu-id="2a080-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="2a080-132">사이트 모음 관리자가 팀 그룹 소유자에 대해 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="2a080-133">팀 사이트:</span><span class="sxs-lookup"><span data-stu-id="2a080-133">For the Team Site:</span></span> 
    - <span data-ttu-id="2a080-134">팀 사이트 소유자 SharePoint 그룹([모든 권한] 사용 권한 수준 포함)은 팀 그룹 소유자로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="2a080-135">팀 사이트 구성원 SharePoint 그룹(편집 사용 권한 수준 포함)은 팀 그룹 구성원으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="2a080-136">팀 사이트 방문자 SharePoint 그룹(읽기 사용 권한 수준 포함)은 그룹 또는 사용자 계정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="2a080-137">다음은 팀 사이트의 기본 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-137">Here are the default permissions for the Team Site.</span></span>

![팀 사이트의 기본 사용 권한](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="2a080-139">편집 사용 권한 수준의 \<팀 이름> 소유자 SharePoint 그룹을 보는 경우, \<팀 이름> 소유자가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="2a080-140">결과로 제공되는 권한을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="2a080-141">팀 그룹 소유자가 사이트를 관리하고 사이트 콘텐츠를 전체적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="2a080-142">팀 그룹 구성원이 사이트에서 파일을 만들고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="2a080-143">사용 권한 유지 관리는 팀 구성원 및 소유자 유지 관리와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="2a080-144">지금까지의 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-144">Here’s the resulting configuration so far.</span></span>

![보안 팀 시나리오 구성의 2단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="2a080-146">3단계: 추가 보안을 위해 기본 SharePoint 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="2a080-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="2a080-147">팀 사이트에서 이 사용 권한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="2a080-148">도구 막대에서 설정 아이콘을 클릭한 다음, **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="2a080-149">**사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-149">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="2a080-150">**사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="2a080-151">**액세스 요청 허용**을 해제한 다음, **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="2a080-152">이 설정을 사용하는 경우, 팀 그룹 구성원이 다른 구성원과 팀 사이트를 공유하거나 구성원이 아닌 사용자가 해당 팀 사이트의 액세스를 요청할 수 있는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="2a080-153">지금까지의 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-153">Here’s the resulting configuration so far.</span></span>

![보안 팀 시나리오 구성의 3단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="2a080-155">4단계: 보존 레이블 및 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="2a080-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="2a080-156">[이 지침](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp)을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="2a080-157">필요한 경우, 높은 규제 대상 데이터의 보존 레이블을 만들고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="2a080-158">1단계에서 만든 보존 레이블에 맞게 팀 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="2a080-159">2단계에서 만든 보존 레이블을 사용하고 사용자가 조직 외부에서 파일을 전송하지 못하도록 높은 규제 대상 데이터에 대한 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="2a080-160">[DLP 정책 서식 파일](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates)을 기반으로, 상태 및 재무 산업 규제에 대한 정책와 같이 추가 요구 사항에 대한 정책을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="2a080-161">지금까지의 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-161">Here’s the resulting configuration so far.</span></span>

![보안 팀 시나리오 구성의 4단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="2a080-163">5단계: 해당 레이블 또는 높은 규제 대상 레이블의 하위 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="2a080-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="2a080-164">모든 사용자가 모든 파일에 적용할 수 있는 높은 규제 대상 데이터의 민감도 레이블과 달리, 할당된 파일이 다음을 수행하려면 보안 팀에 고유한 레이블이나 하위 레이블이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="2a080-165">암호화되고 해당 암호화가 파일이 이동하는 경우에도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="2a080-166">팀 그룹의 구성원만 파일을 열 수 있도록 사용자 지정 권한을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="2a080-167">팀 사이트에 저장된 파일에 보안 수준을 추가적으로 설정하려면, 고유한 레이블 또는 높은 규제 대상 파일에 대한 일반적인 레이블의 하위 레이블인 새 민감도 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="2a080-168">팀 그룹 구성원만 레이블 목록에서 해당 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="2a080-169">전역적인 사용과 개별적 개인 팀에 소수의 레이블이 필요한 경우에는 민감도 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-169">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="2a080-170">다수의 레이블을 보유하고 있거나 높은 규제 대상 레이블 아래에 개인 팀의 레이블을 구성하려는 경우 민감도 하위 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="2a080-171">[이 지침을 사용](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)하여 다음 설정으로 개별 레이블이나 하위 레이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="2a080-172">레이블 이름에는 팀 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="2a080-173">암호화가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-173">Encryption is enabled.</span></span>
- <span data-ttu-id="2a080-174">팀 그룹에 공동 작성자 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="2a080-175">새 레이블이 포함된 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-175">Here’s the resulting configuration with the new label.</span></span>

![보안 팀 시나리오 구성의 5단계](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="2a080-177">민감도 레이블과 팀 그룹 사이의 관계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![팀 그룹과 레이블 사용 권한의 관계](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="2a080-179">사용자 정의 사용 권한에 대해 또는 만료일을 포함하여 민감도 레이블이나 하위 레이블을 구성하는 경우, Teams 또는 SharePoint에서 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="2a080-180">Office 앱을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-180">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="2a080-181">사용 권한의 사용자 지정 </span><span class="sxs-lookup"><span data-stu-id="2a080-181">Custom permissions</span></span>

<span data-ttu-id="2a080-182">팀 사이트의 사용자 지정 SharePoint 사이트 사용 권한을 구성하고, 필요한 경우 해당 민감도 레이블을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-182">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="2a080-183">다음은 이와 관련된 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-183">Here are two examples:</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="2a080-184">예제 1: SharePoint 사이트 관리 위임</span><span class="sxs-lookup"><span data-stu-id="2a080-184">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="2a080-185">팀 소유자가 SharePoint 관리 경험이 없거나 팀 사이트의 관리를 위임하려는 경우, SharePoint 관리자의 사용자 계정을 팀 소유자 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-185">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="2a080-186">그러나 SharePoint 관리자는 팀과 모든 해당 리소스에 대한 전체 액세스 권한을 갖게 되고 민감도 레이블이 적용된 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-186">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="2a080-187">권한을 초과하여 부여하지 않도록 하려면, 해당 사이트의 고급 사용 권한 설정에서 SharePoint 관리자의 사용자 계정을 팀 사이트 소유자 SharePoint 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-187">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="2a080-188">SharePoint 관리자가 사이트를 관리할 수는 있지만, 팀과 해당 리소스에 액세스할 수 없으며 민감도 레이블이 지정된 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-188">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="2a080-189">예제 2: 레이블이 지정된 파일에 대해 보기 전용 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="2a080-189">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="2a080-190">일부 직원만 팀 사이트에서 레이블이 지정된 파일의 내용을 보아야 하는 경우, 개별 사용자 계정을 </span><span class="sxs-lookup"><span data-stu-id="2a080-190">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="2a080-191">기본적으로 읽기 사용 권한이 있는 \<팀 이름 > 방문자 SharePoint 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-191">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="2a080-192">뷰어 권한이 있는 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-192">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="2a080-193">다음은 레이블의 결과 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-193">Here are the resulting permissions on the label.</span></span>

![레이블이 지정된 파일을 볼 수 있도록 사용자 지정된 권한의 예](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="2a080-195">사이트 방문자는 팀 사이트에 바로 액세스하고 하위 레이블이 적용된 파일의 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-195">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="2a080-196">그러나 팀 그룹의 구성원이 아니므로, 팀 또는 해당 리소스에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-196">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="2a080-197">2단계: 팀 구성원을 위한 사용자 채택 유도</span><span class="sxs-lookup"><span data-stu-id="2a080-197">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="2a080-198">팀이 준비되면 팀 구성원에게 팀과 추가 보안 기능의 채택을 유도할 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-198">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="2a080-199">1단계: 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="2a080-199">Step 1: Train your users</span></span>

<span data-ttu-id="2a080-200">팀 그룹의 구성원은 채팅, 모임 및 기타 앱을 포함하여 팀과 모든 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-200">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="2a080-201">채널의 **파일** 섹션에서 파일에 대한 작업을 하는 경우, 팀 그룹의 구성원이 보안 팀을 위해 만든 파일에 민감도 레이블이나 하위 레이블을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-201">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="2a080-202">다음은 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-202">Here’s an example.</span></span>

![보안 팀에서 파일에 적용된 레이블의 예](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="2a080-204">레이블이 해당 파일에 적용되는 경우, 파일이 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-204">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="2a080-205">팀 그룹의 구성원이 실시간으로 Teams에서 파일을 열고 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-205">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="2a080-206">파일이 암호화되며 팀 그룹 구성원으로 설정된 공동 작성자 권한을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-206">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="2a080-207">파일이 사이트를 떠나 악의적인 사용자에게 전달되는 경우, 파일을 열고 콘텐츠를 보려면 팀 그룹의 구성원인 사용자 계정의 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-207">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="2a080-208">팀 구성원 교육:</span><span class="sxs-lookup"><span data-stu-id="2a080-208">Train your team members:</span></span>

- <span data-ttu-id="2a080-209">채팅, 모임, 파일 및 기타 팀 사이트의 리소스를 위한 새 팀 사용의 중요성 및 높은 규제 대상의 데이터 누출 결과(예: 법적 영향, 규제 벌금, 랜섬웨어 또는 경쟁적 우위 박탈)</span><span class="sxs-lookup"><span data-stu-id="2a080-209">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="2a080-210">팀에 액세스 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2a080-210">How to access the team.</span></span>
- <span data-ttu-id="2a080-211">사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="2a080-211">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="2a080-212">DLP 정책으로 외부에서 파일을 공유하지 못하도록 차단하는 방법</span><span class="sxs-lookup"><span data-stu-id="2a080-212">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="2a080-213">팀의 사용자 지정 레이블이나 하위 레이블을 사용하여 파일에 레이블을 할당하는 방법.</span><span class="sxs-lookup"><span data-stu-id="2a080-213">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="2a080-214">파일이 사이트 외부로 누출된 경우에도 레이블 혹은 하위 레이블이 파일을 보호하는 방법.</span><span class="sxs-lookup"><span data-stu-id="2a080-214">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="2a080-215">이 교육에는 팀 구성원이 이러한 기능과 해당 결과를 경험해볼 수 있도록 하기 위해 실무 위주의 연습이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-215">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="2a080-216">2단계: 정기적인 사용 현황 검토 및 팀 구성원 피드백 처리</span><span class="sxs-lookup"><span data-stu-id="2a080-216">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="2a080-217">교육 후 몇 주 안에:</span><span class="sxs-lookup"><span data-stu-id="2a080-217">In the weeks after training:</span></span>

- <span data-ttu-id="2a080-218">팀 구성원의 피드백을 신속하게 처리하고 정책과 구성을 세부적으로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-218">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="2a080-219">팀의 사용 현황을 분석하고 예상 사용 현황과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="2a080-220">높은 규제 대상 파일에 사용자 지정 민감도 레이블 혹은 하위 레이블이 적절히 할당되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

  <span data-ttu-id="2a080-221">SharePoint에서 폴더를 보고 **열 추가**의 **열 표시/숨기기** 옵션을 통해 **민감도** 열을 추가하여 레이블이 할당된 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-221">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="2a080-222">필요에 따라 사용자를 재교육합니다.</span><span class="sxs-lookup"><span data-stu-id="2a080-222">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a080-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a080-223">See also</span></span>

[<span data-ttu-id="2a080-224">높은 규제 대상 데이터를 위한 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="2a080-224">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="2a080-225">Microsoft 365 Enterprise 워크로드 및 시나리오</span><span class="sxs-lookup"><span data-stu-id="2a080-225">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="2a080-226">[Microsoft 365 생산성 라이브러리](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="2a080-226">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="2a080-227">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="2a080-227">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
