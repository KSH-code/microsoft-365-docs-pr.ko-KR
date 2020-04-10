---
title: Office 365 ATP에 대 한 안전한 링크, safelinks, 안전한 링크, 악성 링크 차단, office 365 ATP, 팀 세이프 링크, 사용자가 잘못 된 링크를 클릭 하지 못하도록 함, 악성 링크
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
ms.openlocfilehash: 49a49bd41e71daf0afc9e7a24e79898ff98ad798
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212548"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="8b692-104">팀의 Office 365 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="8b692-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b692-105">이 기능은 Microsoft 팀 기술 채택 프로그램의 고객을 위한 **공개 미리 보기** , 2020 년 2 월 28 일 (탭핑)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="8b692-106">이 메모는 팀에 대 한 안전한 링크를 보다 광범위 하 게 사용할 수 있는 경우 문서에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="8b692-107">Microsoft 팀에서 작업을 관리 하기 위한 Office 365 클라우드 기반 응용 프로그램은 이미 Office 365의 안전한 첨부 파일을 사용 하지만, 이제 클릭 시에 안전한 링크에 액세스할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="8b692-108">Office 365 ATP에 대 한 구독을 갖고 있는 경우에는 채팅 1-1 채팅, 그룹 간 또는 채널에서 탭을 사용 하 고 있는지 여부에 상관 없이이 안전 측정값을 사용 하도록 설정 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="8b692-109">작동 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-109">Here's how it works:</span></span> 

1. <span data-ttu-id="8b692-110">팀 응용 프로그램을 시작 하면 Office 365에서 사용자가 Office 365 ATP가 있는 조직에 속하고, 사용자가 Microsoft 팀에 대 한 보호를 사용 하는 활성 안전한 링크 정책의 일부 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="8b692-111">위의 사항에 해당 하는 경우에는 채팅, 그룹 채팅, 채널 및 해당 사용자에 대 한 탭에서을 클릭 했을 때 Url의 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

> [!NOTE]
> <span data-ttu-id="8b692-112">안전한 링크는 게스트 사용자, 페더레이션 사용자, 테 넌 트 사용자가 보낸 링크의 사용자를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-112">Safe links safeguards users from links sent by Guest users, Federated users, tenant users.</span></span> <span data-ttu-id="8b692-113">로그인 한 사용자가 팀에 대 한 안전한 링크를 사용 하는 경우 안전한 링크 보호가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-113">If the user logged in has safe links for Teams enabled, then safe links protections will apply.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="8b692-114">사용자에 게 어떤 문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="8b692-114">What will users experience?</span></span> 

<span data-ttu-id="8b692-115">모든 보호 된 사용자는 위험한 Url에서 다음과 같은 환경을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-115">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="8b692-116">팀 대화, 그룹 채팅 또는 채널에서 링크를 클릭 한 경우 페이지가 기본 브라우저에 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-116">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="8b692-117">고정 된 탭에서 링크를 클릭 하면 해당 탭 내의 팀 GUI에 페이지가 표시 되 고 보안을 위해 브라우저에서 여는 옵션이 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-117">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="8b692-118">이 사용자는 URL의 사이트를 계속 사용할 수 없도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-118">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="8b692-119">링크를 보낸 사용자가 Office 365 ATP에 의해 보호 되지 않는 경우에는 자신의 컴퓨터에서 URL을 클릭 하 여 문제가 있는 사이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-119">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="8b692-120">따라서 Office 365 관리자는 보호 된 사용자의 사용 가능 여부를 확실히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-120">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![악성 링크를 보고 하 고 페이지로의 통과를 차단 하는 팀 페이지에 대 한 안전한 링크입니다.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="8b692-122">팀에서이 페이지의 *뒤로 이동* 단추를 클릭 하면 종료 됩니다 (또는 빈 페이지 사용자가 종료 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="8b692-122">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="8b692-123">그러나 링크를 다시 클릭 하면 해당 사이트의 신뢰도가 reassessment이 페이지도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-123">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="8b692-124">일부 Office 365 관리자는 차단 페이지의 **계속 해 서** 메시지를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-124">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="8b692-125">그러나 안전한 링크를 통해 사이트의 신뢰도를 측정 하 여 찾은 경우 더 이상 클릭 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-125">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="8b692-126">사용자가 안전 조치를 우회 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b692-126">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="8b692-127">계속을 사용 하도록 설정 하기 전에 다음 사항을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b692-127">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

