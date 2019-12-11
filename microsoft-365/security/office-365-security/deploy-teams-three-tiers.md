---
title: 파일의 3단계 보호를 위한 Teams 배포
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 파일에 대한 다양한 정보 보호 수준에 맞게 Microsoft Teams를 사용하여 팀을 만들고 구성합니다.
ms.openlocfilehash: 263a787eb7f1fa8289a127816c6f8df60960feda
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925843"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="067ab-103">파일의 3단계 보호를 위한 Teams 배포</span><span class="sxs-lookup"><span data-stu-id="067ab-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="067ab-104">이 문서의 단계를 사용하여 초기, 중요 및 극비 팀을 디자인하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="067ab-105">이러한 3계층 보호에 대한 자세한 내용은 [Microsoft Teams에서의 파일 보호](secure-files-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="067ab-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-files-in-teams.md).</span></span>
  
## <a name="baseline-teams"></a><span data-ttu-id="067ab-106">기준 팀</span><span class="sxs-lookup"><span data-stu-id="067ab-106">Baseline teams</span></span>

<span data-ttu-id="067ab-107">초기 보호에는 공용 및 비공개 팀이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-107">Baseline protection includes both public and private team sites.</span></span> <span data-ttu-id="067ab-108">공개 팀은 조직의 모든 사용자가 검색하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-108">Public team sites can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="067ab-109">개인 사이트는 팀과 연결된 Office 365 그룹의 구성원만 검색하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site.</span></span> <span data-ttu-id="067ab-110">이러한 유형의 팀은 모두 구성원이 다른 사용자와 사이트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-110">Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="067ab-111">공개</span><span class="sxs-lookup"><span data-stu-id="067ab-111">Public</span></span>

<span data-ttu-id="067ab-112">[이 문서](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)의 지침에 따라 공용 액세스 및 사용 권한이 있는 기준 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-112">Follow the instructions in [this article](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with public access and permissions.</span></span>

<span data-ttu-id="067ab-113">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-113">Here is your resulting configuration.</span></span>
  
![공개 팀에 대한 기준 수준 보호.](../media/baseline-public-team.png)
  
### <a name="private"></a><span data-ttu-id="067ab-115">비공개</span><span class="sxs-lookup"><span data-stu-id="067ab-115">Private</span></span>

<span data-ttu-id="067ab-116">[이 문서](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)의 지침에 따라 개인 액세스 및 사용 권한이 있는 기준 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-116">Follow the instructions in [this article](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with private access and permissions.</span></span>

<span data-ttu-id="067ab-117">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-117">Here is your resulting configuration.</span></span>

![비공개 팀에 대한 기준 수준 보호.](../media/baseline-private-team.png)
  
## <a name="sensitive-teams"></a><span data-ttu-id="067ab-119">중요 팀</span><span class="sxs-lookup"><span data-stu-id="067ab-119">Sensitive teams</span></span>

<span data-ttu-id="067ab-120">중요한 팀의 경우 먼저 [비공개 팀 만들기](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-120">For a sensitive team, you start by [creating a private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="067ab-121">다음으로, 팀 구성원이 공유하지 못하도록 기본 SharePoint 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1.  <span data-ttu-id="067ab-122">팀의 도구 막대에서 **파일**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-122">In the tool bar for the team, click **Files**.</span></span>
2.  <span data-ttu-id="067ab-123">줄임표를 클릭한 다음 **SharePoint에서 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
3.  <span data-ttu-id="067ab-124">기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-124">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
4.  <span data-ttu-id="067ab-125">**사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
5.  <span data-ttu-id="067ab-126">**사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

<span data-ttu-id="067ab-127">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-127">Here is your resulting configuration.</span></span>
  
![팀에 대한 중요 보호](../media/sensitive-team.png)
 

## <a name="highly-confidential-teams"></a><span data-ttu-id="067ab-129">극비 팀</span><span class="sxs-lookup"><span data-stu-id="067ab-129">Highly confidential teams</span></span>

<span data-ttu-id="067ab-130">극비 팀의 경우 먼저 [비공개 팀 만들기](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-130">With a highly confidential team, you start by [creating a private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="067ab-131">다음으로, 팀 구성원이 공유하고 팀 구성원이 아닌 사용자가 액세스 요청을 못하도록 기본 SharePoint 사이트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1.  <span data-ttu-id="067ab-132">팀의 도구 막대에서 **파일**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-132">In the tool bar for the team, click **Files**.</span></span>
2.  <span data-ttu-id="067ab-133">줄임표를 클릭한 다음 **SharePoint에서 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
3.  <span data-ttu-id="067ab-134">기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-134">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
4.  <span data-ttu-id="067ab-135">**사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
5.  <span data-ttu-id="067ab-136">**사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
6.  <span data-ttu-id="067ab-137">**액세스 요청 허용**을 해제한 다음, **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="067ab-138">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="067ab-138">Here is your resulting configuration.</span></span>
  
![팀에 대한 극비 보호](../media/highly-confidential-team.png)  
  
## <a name="next-step"></a><span data-ttu-id="067ab-140">다음 단계</span><span class="sxs-lookup"><span data-stu-id="067ab-140">Next step</span></span>

[<span data-ttu-id="067ab-141">보존 레이블 및 DLP를 사용하여 팀에서 파일을 보호</span><span class="sxs-lookup"><span data-stu-id="067ab-141">Protect SharePoint Online files with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="067ab-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="067ab-142">See also</span></span>

[<span data-ttu-id="067ab-143">Microsoft Teams에서의 파일 보호</span><span class="sxs-lookup"><span data-stu-id="067ab-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="067ab-144">클라우드 도입 및 하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="067ab-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
