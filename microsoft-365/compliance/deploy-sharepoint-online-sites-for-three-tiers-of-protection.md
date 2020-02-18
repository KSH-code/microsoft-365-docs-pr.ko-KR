---
title: 3단계 보호를 위한 SharePoint Online 사이트 배포
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: '요약: 다양한 정보 보호 수준에 맞게 SharePoint Online 팀 사이트를 만들고 구성합니다.'
ms.openlocfilehash: 1827c4a19cfd31a236dfbd58e454c610cae14477
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075536"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="1b31d-103">3단계 보호를 위한 SharePoint Online 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="1b31d-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="1b31d-p101">이 문서의 단계를 사용하여 초기, 중요 및 극비 SharePoint Online 팀 사이트를 디자인하고 배포합니다. 이러한 3계층 보호에 대한 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b31d-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="1b31d-106">초기 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="1b31d-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="1b31d-p102">초기 보호에는 공용 및 개인 팀 사이트가 모두 포함됩니다. 공용 팀 사이트는 조직의 모든 사용자가 검색하고 액세스할 수 있습니다. 개인 사이트는 팀 사이트와 연결된 Office 365 그룹의 구성원만 검색하고 액세스할 수 있습니다. 이러한 유형의 팀 사이트 모두에서는 구성원이 다른 사용자와 사이트를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="1b31d-111">공개</span><span class="sxs-lookup"><span data-stu-id="1b31d-111">Public</span></span>

<span data-ttu-id="1b31d-112">공용 액세스 및 권한이 있는 초기 SharePoint Online 팀 사이트를 만들려면 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="1b31d-113">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-113">Here is your resulting configuration.</span></span>
  
![공용 SharePoint Online 팀 사이트에 대한 기준 수준 보호입니다.](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="1b31d-115">비공개</span><span class="sxs-lookup"><span data-stu-id="1b31d-115">Private</span></span>

<span data-ttu-id="1b31d-116">개인 액세스 및 권한이 있는 초기 SharePoint Online 팀 사이트를 만들려면 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="1b31d-117">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-117">Here is your resulting configuration.</span></span>
  
![개인 SharePoint Online 팀 사이트에 대한 기준 수준의 보호입니다.](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="1b31d-119">중요 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="1b31d-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="1b31d-120">중요 SharePoint Online 팀 사이트는 개인 팀 사이트로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="1b31d-121">먼저 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)에 따라 개인 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="1b31d-122">다음으로, 새 SharePoint Online 팀 사이트에서 다음 단계를 사용하여 추가 권한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="1b31d-123">SharePoint 팀 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="1b31d-124">**사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="1b31d-125">**사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="1b31d-126">이러한 권한 설정의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="1b31d-127">구성원이 다른 구성원과 공유하는 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="1b31d-128">구성원이 아닌 사용자가 액세스를 요청하는 기능은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="1b31d-129">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-129">Here is your resulting configuration.</span></span>
  
![격리된 SharePoint Online 팀 사이트에 대한 중요한 수준의 보호입니다.](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="1b31d-131">사이트 구성원은 이제 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스에서 안전하게 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="1b31d-132">극비 SharePoint Online 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="1b31d-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="1b31d-133">극비 SharePoint Online 팀 사이트는 추가 권한 설정이 있는 개인 팀 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="1b31d-134">먼저 다음 [지침](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)에 따라 개인 SharePoint Online 팀 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="1b31d-135">다음으로, 새 SharePoint Online 팀 사이트에서 다음 단계를 사용하여 추가 권한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="1b31d-136">SharePoint 팀 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="1b31d-137">**사이트 사용 권한** 창에 있는 **공유 설정**에서 **공유 설정 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="1b31d-138">**사용 권한 공유**에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="1b31d-139">**액세스 요청 허용**을 해제한 다음, **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="1b31d-140">이러한 권한 설정의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="1b31d-141">구성원이 다른 구성원과 공유하는 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="1b31d-142">구성원이 아닌 사용자가 액세스를 요청하는 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="1b31d-143">구성 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-143">Here is your resulting configuration.</span></span>
  
![격리된 SharePoint Online 팀 사이트에 대한 높은 기밀 수준의 보호입니다.](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="1b31d-145">사이트 구성원은 이제 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스에서 안전하게 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b31d-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="1b31d-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1b31d-146">Next step</span></span>

[<span data-ttu-id="1b31d-147">Office 365 레이블 및 DLP를 사용하여 SharePoint Online 파일 보호</span><span class="sxs-lookup"><span data-stu-id="1b31d-147">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="1b31d-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b31d-148">See also</span></span>

[<span data-ttu-id="1b31d-149">정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침</span><span class="sxs-lookup"><span data-stu-id="1b31d-149">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="1b31d-150">클라우드 도입 및 하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="1b31d-150">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
