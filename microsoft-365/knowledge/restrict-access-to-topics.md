---
title: 항목에 대한 액세스 제한
description: 항목을 검색하지 못하게 제외하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698963"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="cc7be-103">항목 환경의 항목에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="cc7be-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="cc7be-104">주제 환경의 경우 조직의 이해 관계자는 특정 항목을 검색하여 사용이 허가된 사용자에게 공개하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="cc7be-105">예를 들어 아직 정보를 노출하지 않을 프로젝트를 작업하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="cc7be-106">사이트, 파일 및 기타 리소스에 대한 Office 365 사용 권한은 Topic Experiences 사용자가 항목에서 중요한 정보를 볼 수 없는 반면 특정 항목을 검색하지 못하도록 방지하는 추가 보호책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="cc7be-107">지식 관리자는 항목 검색을 방지하기 위해 지식 네트워크 설정을 제어하는 반면, 지식 관리자 및 기타 관련자는 이러한 작업을 수행하여 공동으로 작업할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="cc7be-108">이 문서에서는 AI를 통해 항목을 식별하거나 사용자 환경에서 추가 보안 보호책으로 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="cc7be-109">항목 환경의 경우 사용자는 Office 365 권한을 통해 액세스할 수 없는 항목의 항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="cc7be-110">사용자가 항목을 볼 수 있는 경우에도 해당 파일, 사이트 및 페이지에는 볼 수 있는 Office 365 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="cc7be-111">중요한 파일에 대한 사용 권한이 올바르게 설정되어 있는지 확인하려면 기본 보안 보호책이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="cc7be-112">항목을 식별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-112">Prevent topics from being identified</span></span>

<span data-ttu-id="cc7be-113">지식 관리자는 초기 인덱싱에서 해당 항목을 찾지 못하도록 하여 특정 항목에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="cc7be-114">Microsoft 365 관리 센터의 기술 네트워크 관리 설정에는 두 가지 방법으로 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="cc7be-115">[항목 검색에서](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)제외할 SharePoint 사이트를 선택합니다. 이 설정을 사용하여 특정 SharePoint 사이트가 항목에 대해 크롤링되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="cc7be-116">[이름별](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)항목 제외: 관리자는 이 설정을 사용하여 특정 항목을 이름으로 검색하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="cc7be-117">지식 네트워크 관리 설정에서 관리자는 CSV 파일에서 제외할 항목 목록을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="cc7be-118">항목 이름과 정확히 일치하거나 부분적으로 일치하는 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="cc7be-119">특정 사용자가 항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="cc7be-120">지식 관리자는 조직에서 항목을 [볼 수 있는 사용자도 선택할 수 있습니다.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="cc7be-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="cc7be-121">이 설정을 사용하면 모든 항목을 볼 수 있는 사용이 허가된 사용자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="cc7be-122">예를 들어 파일럿 환경에서는 소수의 사용자 그룹만 항목을 볼 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="cc7be-123">항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-123">Remove topics from being viewed</span></span>

<span data-ttu-id="cc7be-124">지식 관리자는 사용자가 [](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) 더 이상 항목을 볼 수 있도록 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="cc7be-125">항목 관리 **페이지의** 항목 관리 페이지에서 기술 관리자는 특정 항목을 거부하여 항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="cc7be-126">추천 상태 또는 확인된 상태의 항목에 관계없이 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="cc7be-127">제거된 항목은 나중에 필요한 경우 다시 볼 수 있는 항목으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7be-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="cc7be-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc7be-128">See also</span></span>



  






