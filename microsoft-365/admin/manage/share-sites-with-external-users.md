---
title: 게스트 사용자와 사이트 및 파일 공유
f1.keywords: NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 89502322-bfbb-43d6-9207-4030f8ce26e0
ROBOTS: NOINDEX
description: '조직 외부의 사용자와 사이트 및 파일을 공유하는 방법을 학습합니다. '
ms.openlocfilehash: 585034580fd18d9584b4df3d0bec7026cf207f50
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915040"
---
# <a name="share-sites-and-files-with-guest-users"></a><span data-ttu-id="0fdfd-103">게스트 사용자와 사이트 및 파일 공유</span><span class="sxs-lookup"><span data-stu-id="0fdfd-103">Share sites and files with guest users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0fdfd-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-104">The admin center is changing.</span></span> <span data-ttu-id="0fdfd-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="0fdfd-106">조직 외부의 사용자와 공동 작업을 위해 외부에서 전체 사이트 또는 특정 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-106">To collaborate with people outside your organization, you can share entire sites or specific files externally.</span></span> <span data-ttu-id="0fdfd-107">공유 설정으로 바로 이동하려면 사용하려는 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-107">If you want to get straight to setting up sharing, choose the scenario you want to enable:</span></span>

- [<span data-ttu-id="0fdfd-108">게스트와 문서에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="0fdfd-108">Collaborate with guests on a document</span></span>](../../solutions/collaborate-on-documents.md)
- [<span data-ttu-id="0fdfd-109">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="0fdfd-109">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="0fdfd-110">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="0fdfd-110">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)
  
## <a name="deciding-how-to-share-your-content"></a><span data-ttu-id="0fdfd-111">콘텐츠 공유 방법 결정</span><span class="sxs-lookup"><span data-stu-id="0fdfd-111">Deciding how to share your content</span></span>

<span data-ttu-id="0fdfd-112">콘텐츠를 외부와 공유할지 여부와 그 방법을 결정할 때는 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-112">When considering if and how you want to share content externally, think about the following:</span></span>
  
- <span data-ttu-id="0fdfd-113">사이트 및 하위 사이트의 콘텐츠에 대한 액세스 권한을 부여할 사용자와 해당 콘텐츠에 대해 어떤 권한을 부여할 것인가?</span><span class="sxs-lookup"><span data-stu-id="0fdfd-113">To whom do you want to grant access to content on the site and any subsites, and what do you want them to be able to do?</span></span>
    
- <span data-ttu-id="0fdfd-114">조직에서 콘텐츠를 외부와 공유할 수 있는 권한이 부여되는 사용자는 누구입니까?</span><span class="sxs-lookup"><span data-stu-id="0fdfd-114">To whom in your organization do you want to grant permission to share content externally?</span></span> 
    
- <span data-ttu-id="0fdfd-115">조직 외부의 사람들에게 절대 보여주지 말아야 할 콘텐츠가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="0fdfd-115">Is there content you want to ensure is never available to be viewed by people external to your organization?</span></span>
    
<span data-ttu-id="0fdfd-116">이러한 질문은 콘텐츠 공유 전략을 계획하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-116">The answers to these questions will help you plan your strategy for content sharing.</span></span>
  
|<span data-ttu-id="0fdfd-117">**실행할 작업**</span><span class="sxs-lookup"><span data-stu-id="0fdfd-117">**Try this:**</span></span>|<span data-ttu-id="0fdfd-118">**원하는 작업**</span><span class="sxs-lookup"><span data-stu-id="0fdfd-118">**If you need to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0fdfd-119">그룹에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="0fdfd-119">Add a guest to a group</span></span>  <br/> |<span data-ttu-id="0fdfd-120">조직 외부의 사용자에게 팀 사이트의 정보 및 콘텐츠에 대한 지속적인 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-120">Provide someone outside your organization with ongoing access to information and content on a team site.</span></span> <span data-ttu-id="0fdfd-121">사이트의 정식 사용자처럼 콘텐츠를 만들고 편집하고 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-121">They need the ability to perform like a full user of your site and create, edit, and view content.</span></span>  <br/> |
|<span data-ttu-id="0fdfd-122">문서를 공유하고 게스트에게 인증을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-122">Share a document and require guests to authenticate.</span></span>  <br/> |<span data-ttu-id="0fdfd-123">조직 외부의 특정 사용자에게 검토 또는 공동 작업을 위해 문서에 안전하게 액세스할 수 있도록 하지만 이러한 사용자에게는 사이트의 다른 콘텐츠에 액세스할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-123">Provide specific people outside your organization with secure access to a document for review or collaboration, but these people do not require access to other content on the site.</span></span>  <br/> |
|<span data-ttu-id="0fdfd-124">문서를 공유하지만 인증은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-124">Share a document, but don't require authentication.</span></span>  <br/> |<span data-ttu-id="0fdfd-125">중요하지 않거나 기밀이 아닌 문서에 대한 링크를 조직 외부의 사람과 공유하여 이들이 해당 문서를 보고 자신의 의견을 문서에 업데이트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-125">Share a link to a non-sensitive or non-confidential document with people outside your organization so that they can either view it or update it with feedback.</span></span> <span data-ttu-id="0fdfd-126">이러한 사용자들은 사이트의 콘텐츠에 액세스할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-126">These people do not require access to content on the site.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="0fdfd-127">외부 공유를 사용하지 않도록 설정하면 현재 액세스 권한이 있는 조직 외부의 사용자가 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-127">When you disable external sharing, people outside the organization who currently have access will no longer have access.</span></span> <span data-ttu-id="0fdfd-128">나중에 외부 공유를 다시 설정하면 이러한 사용자에 대한 액세스가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-128">If you later turn external sharing back on, access will be restored for these people.</span></span> <span data-ttu-id="0fdfd-129">사용자가 공유 콘텐츠에 액세스하지 못하도록 방지하려면 [Microsoft 365](/office365/admin/create-groups/add-or-remove-members-from-groups)그룹에서 공유 콘텐츠를 제거하거나 사이트에서 사용 권한을 제거하거나 파일 또는 폴더와의 공유를 [중지합니다.](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-129">To prevent a user from accessing a shared content, [remove them from the Microsoft 365 group](/office365/admin/create-groups/add-or-remove-members-from-groups), remove their permissions from the site, or [stop sharing the file or folder with them](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323).</span></span> 
  
## <a name="enable-external-sharing-at-the-organization-level"></a><span data-ttu-id="0fdfd-130">조직 수준에서 외부 공유를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="0fdfd-130">Enable external sharing at the organization level</span></span>

<span data-ttu-id="0fdfd-131">외부 공유는 조직 수준에서 기본적으로 설정되지만 모든 새 사이트에는 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-131">External sharing is turned on by default at the organization level, but not for all new sites.</span></span> <span data-ttu-id="0fdfd-132">자세한 내용은 외부 공유 [개요를 참조하세요.](/sharepoint/external-sharing-overview)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-132">For info, see [External sharing overview](/sharepoint/external-sharing-overview).</span></span> 

> [!NOTE]
>  <span data-ttu-id="0fdfd-133">모든 사이트에 대해 외부 공유를 허용하려면 조직 수준에서 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-133">To allow external sharing for any site, you need to allow it at the organization level.</span></span> 
  
1. <span data-ttu-id="0fdfd-134">관리 [센터의](https://go.microsoft.com/fwlink/p/?linkid=2024339)홈 페이지의 검색 상자에 "external"을 입력하고 사이트 외부 공유 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0fdfd-134">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), type "external" in the search box on the Home page, and choose **Sites external sharing**.</span></span>
  
2. <span data-ttu-id="0fdfd-135">페이지가 열리면 사용자가 기존 게스트만, 신규 및 기존 게스트 또는 모든 사용자와 공유할 수 있는지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-135">On the page that opens, choose whether users can share with existing guests only, new and existing guests, or anyone.</span></span> 
    
3. <span data-ttu-id="0fdfd-136">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-136">Select **Save**.</span></span>
    
<span data-ttu-id="0fdfd-137">조직 수준에서 외부 공유를 사용하도록 설정한 후 특정 사이트에 대해 외부 공유를 사용하지 않도록 공유 설정을 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-137">After you enable external sharing at the organization level, you can fine tune your sharing settings to disable external sharing for particular sites.</span></span> <span data-ttu-id="0fdfd-138">자세한 내용은 사이트에 대한 외부 공유 설정 또는 [해제를 참조하세요.](/sharepoint/change-external-sharing-site)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-138">For info, see [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
  

  

