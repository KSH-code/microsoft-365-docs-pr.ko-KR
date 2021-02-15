---
title: Microsoft Viva 항목의 항목에 대한 액세스 제한
description: 항목을 검색하지 못하게 제외하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107161"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="7ffbe-103">Microsoft Viva 항목의 항목에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="7ffbe-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="7ffbe-104">Microsoft Viva에서 조직의 관련자는 특정 항목을 검색하여 사용이 허가된 사용자에게 공개하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="7ffbe-105">예를 들어 아직 정보를 노출하지 않을 프로젝트를 작업하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="7ffbe-106">사이트, 파일 및 기타 리소스에 대한 Office 365 사용 권한은 항목 환경 사용자가 항목의 중요한 정보를 볼 수 없는 반면 특정 항목을 검색하지 못하도록 방지하는 추가 보호책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="7ffbe-107">지식 관리자는 항목 검색을 방지하기 위해 지식 네트워크 설정을 제어하는 반면, 기술 관리자 및 기타 이해 관계자는 공동 작업할 수 있도록 작업 수행 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="7ffbe-108">이 문서에서는 AI를 통해 항목을 식별하거나 사용자 환경에서 추가 보안 보호책으로 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="7ffbe-109">Viva 항목에서는 사용자가 Office 365 권한을 통해 액세스할 수 없는 항목의 항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="7ffbe-110">사용자가 항목을 볼 수 있는 경우에도 해당 파일, 사이트 및 페이지에는 볼 수 있는 Office 365 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="7ffbe-111">중요한 파일에 대한 사용 권한이 올바르게 설정되어 있는지 확인하려면 기본 보안 보호책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="7ffbe-112">항목을 식별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-112">Prevent topics from being identified</span></span>

<span data-ttu-id="7ffbe-113">지식 관리자는 초기 인덱싱에서 해당 항목을 찾지 못하도록 하여 특정 항목에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="7ffbe-114">Microsoft 365 관리 센터의 기술 네트워크 관리 설정에는 두 가지 방법으로 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="7ffbe-115">[항목 검색에서](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)제외할 SharePoint 사이트를 선택합니다. 이 설정을 사용하여 특정 SharePoint 사이트가 항목에 대해 크롤링되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="7ffbe-116">[이름별](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)항목 제외: 관리자는 이 설정을 사용하여 특정 항목을 이름으로 검색하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="7ffbe-117">지식 네트워크 관리 설정에서 관리자는 CSV 파일에서 제외할 항목 목록을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="7ffbe-118">항목 이름과 정확히 일치하거나 부분적으로 일치하는 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="7ffbe-119">특정 사용자가 항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="7ffbe-120">지식 관리자는 조직에서 항목을 [볼 수 있는 사용자도 선택할 수 있습니다.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="7ffbe-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="7ffbe-121">이 설정을 사용하면 모든 항목을 볼 수 있는 사용이 허가된 사용자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="7ffbe-122">예를 들어 파일럿 환경에서는 소수의 사용자 그룹만 항목을 볼 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="7ffbe-123">항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-123">Remove topics from being viewed</span></span>

<span data-ttu-id="7ffbe-124">지식 관리자는 사용자가 [](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) 더 이상 항목을 볼 수 있도록 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="7ffbe-125">항목 관리 **페이지의** 항목 관리 페이지에서 기술 관리자는 특정 항목을 거부하여 항목을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="7ffbe-126">추천 상태 또는 확인된 상태의 항목에 관계없이 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="7ffbe-127">제거된 항목은 나중에 필요한 경우 다시 볼 수 있는 항목으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="7ffbe-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ffbe-128">See also</span></span>



  






