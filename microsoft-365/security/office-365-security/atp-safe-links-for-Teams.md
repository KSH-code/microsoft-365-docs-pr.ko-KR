---
title: ATP 안전한 링크, safelinks, 안전한 링크, 악성 링크 차단, office 365 atp, 팀 세이프 링크, 사용자가 잘못 된 링크를 클릭 하지 못하도록 함, 악성 링크
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 이제 팀이 클릭 시에 안전한 링크에 액세스할 수 있습니다. Office 365 ATP에 대 한 구독을 갖고 있는 경우에는 채팅 1-설정 채팅, 그룹 간 또는 채널에서 탭을 사용 하는 경우에 관계 없이이 보안 기능을 사용 하도록 설정 하 고 사용할 수 있습니다.
ms.openlocfilehash: 07f20f0adf503e4592d2bd3f3bc9857d08a1e433
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "43808998"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="f8171-104">Teams의 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="f8171-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8171-105">이 기능은 Microsoft 팀 기술 채택 프로그램의 고객을 위한 **공개 미리 보기** , 2020 년 2 월 28 일 (탭핑)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="f8171-106">이 메모는 팀에 대 한 안전한 링크를 보다 광범위 하 게 사용할 수 있는 경우 문서에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="f8171-107">Microsoft 팀에서 작업을 관리 하는 Microsoft 클라우드 기반 응용 프로그램에서 이미 안전한 첨부 파일 (Office 365)을 사용 하 고 있지만 이제 사용자가 클릭 하는 시점에 안전한 링크에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="f8171-108">채팅, 그룹 채팅, 채널 또는 탭 사용 여부에 관계 없이 Office 365 ATP에 대 한 구독이 있는 경우이 안전 측정값을 사용 하도록 설정 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="f8171-109">라이선스 요구 사항에 대한 자세한 내용은 [Microsoft 365 테넌트 수준 서비스 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8171-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

<span data-ttu-id="f8171-110">작동 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-110">Here's how it works:</span></span> 

1. <span data-ttu-id="f8171-111">팀 응용 프로그램을 시작 하면 Microsoft 365에서 사용자가 Office 365 ATP가 있는 조직에 속하고, 사용자가 Microsoft 팀에 대 한 보호를 사용 하는 활성 안전한 링크 정책의 일부 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="f8171-112">위의 사항에 해당 하는 경우에는 채팅, 그룹 채팅, 채널 및 해당 사용자에 대 한 탭에서을 클릭 했을 때 Url의 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="f8171-113">사용자에 게 어떤 문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="f8171-113">What will users experience?</span></span> 

<span data-ttu-id="f8171-114">모든 보호 된 사용자는 위험한 Url에서 다음과 같은 환경을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-114">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="f8171-115">팀 대화, 그룹 채팅 또는 채널에서 링크를 클릭 한 경우 페이지가 기본 브라우저에 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="f8171-116">고정 된 탭에서 링크를 클릭 하면 해당 탭 내의 팀 GUI에 페이지가 표시 되 고 보안을 위해 브라우저에서 여는 옵션이 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="f8171-117">이 사용자는 URL의 사이트를 계속 사용할 수 없도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="f8171-118">링크를 보낸 사용자가 Office 365 ATP에 의해 보호 되지 않는 경우에는 자신의 컴퓨터에서 URL을 클릭 하 여 문제가 있는 사이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="f8171-119">이를 통해 관리자는 보호 된 사용자의 사용 가능 여부를 보다 명확 하 게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![악성 링크를 보고 하 고 페이지로의 통과를 차단 하는 팀 페이지에 대 한 안전한 링크입니다.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="f8171-121">팀에서이 페이지의 *뒤로 이동* 단추를 클릭 하면 종료 됩니다 (또는 빈 페이지 사용자가 종료 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="f8171-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="f8171-122">그러나 링크를 다시 클릭 하면 해당 사이트의 신뢰도가 reassessment이 페이지도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="f8171-123">일부 Microsoft 365 관리자는 차단 페이지에서 **계속 진행** 메시지를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="f8171-124">그러나 안전한 링크를 통해 사이트의 신뢰도를 측정 하 여 찾은 경우 더 이상 클릭 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="f8171-125">사용자가 안전 조치를 우회 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8171-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="f8171-126">계속을 사용 하도록 설정 하기 전에 다음 사항을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8171-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 
