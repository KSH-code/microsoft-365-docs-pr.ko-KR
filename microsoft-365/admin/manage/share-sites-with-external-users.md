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
description: '조직 외부의 사용자와 사이트 및 파일을 공유 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 79760f662ec68d2ac9089586fd9cbf38b0bd9897
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780052"
---
# <a name="share-sites-and-files-with-guest-users"></a><span data-ttu-id="5b6b7-103">게스트 사용자와 사이트 및 파일 공유</span><span class="sxs-lookup"><span data-stu-id="5b6b7-103">Share sites and files with guest users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5b6b7-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-104">The admin center is changing.</span></span> <span data-ttu-id="5b6b7-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="5b6b7-106">조직 외부의 사용자와 공동 작업을 하려면 전체 사이트 또는 특정 파일을 외부에서 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-106">To collaborate with people outside your organization, you can share entire sites or specific files externally.</span></span> <span data-ttu-id="5b6b7-107">공유 설정으로 바로 이동하려면 사용하려는 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-107">If you want to get straight to setting up sharing, choose the scenario you want to enable:</span></span>

- [<span data-ttu-id="5b6b7-108">게스트와 문서에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="5b6b7-108">Collaborate with guests on a document</span></span>](../../solutions/collaborate-on-documents.md)
- [<span data-ttu-id="5b6b7-109">게스트와 현장에서 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="5b6b7-109">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="5b6b7-110">게스트와 팀으로 공동 작업하기</span><span class="sxs-lookup"><span data-stu-id="5b6b7-110">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)
  
## <a name="deciding-how-to-share-your-content"></a><span data-ttu-id="5b6b7-111">콘텐츠 공유 방법 결정</span><span class="sxs-lookup"><span data-stu-id="5b6b7-111">Deciding how to share your content</span></span>

<span data-ttu-id="5b6b7-112">콘텐츠를 외부와 공유할지 여부와 그 방법을 결정할 때는 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-112">When considering if and how you want to share content externally, think about the following:</span></span>
  
- <span data-ttu-id="5b6b7-113">사이트의 콘텐츠에 대 한 액세스 권한을 부여 하려는 사람 및 하위 사이트가 무엇을 할 수 있도록 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="5b6b7-113">To whom do you want to grant access to content on the site and any subsites, and what do you want them to be able to do?</span></span>
    
- <span data-ttu-id="5b6b7-114">조직에서 콘텐츠를 외부와 공유할 수 있는 권한이 부여되는 사용자는 누구입니까?</span><span class="sxs-lookup"><span data-stu-id="5b6b7-114">To whom in your organization do you want to grant permission to share content externally?</span></span> 
    
- <span data-ttu-id="5b6b7-115">조직 외부의 사람들에게 절대 보여주지 말아야 할 콘텐츠가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="5b6b7-115">Is there content you want to ensure is never available to be viewed by people external to your organization?</span></span>
    
<span data-ttu-id="5b6b7-116">이러한 질문은 콘텐츠 공유 전략을 계획하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-116">The answers to these questions will help you plan your strategy for content sharing.</span></span>
  
|<span data-ttu-id="5b6b7-117">**실행할 작업**</span><span class="sxs-lookup"><span data-stu-id="5b6b7-117">**Try this:**</span></span>|<span data-ttu-id="5b6b7-118">**원하는 작업**</span><span class="sxs-lookup"><span data-stu-id="5b6b7-118">**If you need to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b6b7-119">그룹에 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="5b6b7-119">Add a guest to a group</span></span>  <br/> |<span data-ttu-id="5b6b7-120">조직 외부의 사용자에 게 팀 사이트의 정보 및 콘텐츠에 대 한 지속적인 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-120">Provide someone outside your organization with ongoing access to information and content on a team site.</span></span> <span data-ttu-id="5b6b7-121">사이트의 정식 사용자처럼 콘텐츠를 만들고 편집하고 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-121">They need the ability to perform like a full user of your site and create, edit, and view content.</span></span>  <br/> |
|<span data-ttu-id="5b6b7-122">문서를 공유 하 고 게스트가 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-122">Share a document and require guests to authenticate.</span></span>  <br/> |<span data-ttu-id="5b6b7-123">조직 외부의 특정 사용자에 게 검토 또는 공동 작업을 위해 문서에 대 한 보안 액세스 권한을 제공 하지만 이러한 사용자는 사이트의 다른 콘텐츠에 액세스할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-123">Provide specific people outside your organization with secure access to a document for review or collaboration, but these people do not require access to other content on the site.</span></span>  <br/> |
|<span data-ttu-id="5b6b7-124">문서를 공유 하 되 인증은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-124">Share a document, but don't require authentication.</span></span>  <br/> |<span data-ttu-id="5b6b7-125">중요하지 않거나 기밀이 아닌 문서에 대한 링크를 조직 외부의 사람과 공유하여 이들이 해당 문서를 보고 자신의 의견을 문서에 업데이트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-125">Share a link to a non-sensitive or non-confidential document with people outside your organization so that they can either view it or update it with feedback.</span></span> <span data-ttu-id="5b6b7-126">이러한 사용자는 사이트의 콘텐츠에 액세스할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-126">These people do not require access to content on the site.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="5b6b7-127">외부 공유를 사용 하지 않도록 설정 하면 현재 액세스 권한이 있는 조직 외부의 사용자에 게 더 이상 액세스 권한이 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-127">When you disable external sharing, people outside the organization who currently have access will no longer have access.</span></span> <span data-ttu-id="5b6b7-128">나중에 외부 공유를 다시 켜면 이러한 사용자에 대 한 액세스가 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-128">If you later turn external sharing back on, access will be restored for these people.</span></span> <span data-ttu-id="5b6b7-129">사용자가 공유 콘텐츠에 액세스 하지 못하도록 하려면 [Microsoft 365 그룹에서](/office365/admin/create-groups/add-or-remove-members-from-groups)해당 콘텐츠를 제거 하 고, 사이트에서 사용 권한을 제거 하거나, [파일 또는 폴더를 공유를 중지](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-129">To prevent a user from accessing a shared content, [remove them from the Microsoft 365 group](/office365/admin/create-groups/add-or-remove-members-from-groups), remove their permissions from the site, or [stop sharing the file or folder with them](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323).</span></span> 
  
## <a name="enable-external-sharing-at-the-organization-level"></a><span data-ttu-id="5b6b7-130">조직 수준에서 외부 공유를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="5b6b7-130">Enable external sharing at the organization level</span></span>

<span data-ttu-id="5b6b7-131">외부 공유는 기본적으로 조직 수준에서 설정 되지만 모든 새 사이트에 대해 사용 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-131">External sharing is turned on by default at the organization level, but not for all new sites.</span></span> <span data-ttu-id="5b6b7-132">자세한 내용은 [외부 공유 개요](/sharepoint/external-sharing-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-132">For info, see [External sharing overview](/sharepoint/external-sharing-overview).</span></span> 

> [!NOTE]
>  <span data-ttu-id="5b6b7-133">모든 사이트에 대해 외부 공유를 허용 하려면 조직 수준에서 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-133">To allow external sharing for any site, you need to allow it at the organization level.</span></span> 
  
1. <span data-ttu-id="5b6b7-134">[관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339)에서 홈 페이지의 검색 상자에 "외부"를 입력 하 고 **사이트 외부 공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-134">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), type "external" in the search box on the Home page, and choose **Sites external sharing**.</span></span>
  
2. <span data-ttu-id="5b6b7-135">페이지가 열리면 사용자가 기존 guests, 신규 및 기존 손님, 누구나 공유할 수 있는지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-135">On the page that opens, choose whether users can share with existing guests only, new and existing guests, or anyone.</span></span> 
    
3. <span data-ttu-id="5b6b7-136">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-136">Select **Save**.</span></span>
    
<span data-ttu-id="5b6b7-137">조직 수준에서 외부 공유를 사용 하도록 설정한 후에는 특정 사이트에 대해 외부 공유를 사용 하지 않도록 설정 하 여 공유 설정을 세부적으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-137">After you enable external sharing at the organization level, you can fine tune your sharing settings to disable external sharing for particular sites.</span></span> <span data-ttu-id="5b6b7-138">자세한 내용은 [사이트에 대 한 외부 공유 설정 또는 해제](/sharepoint/change-external-sharing-site)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b6b7-138">For info, see [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
  

  

    

