---
title: Canvas에서 Microsoft Teams 모임 사용
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 캔버스 Microsoft Teams 통합
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454676"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="ed511-103">Canvas에서 Microsoft Teams 모임 사용</span><span class="sxs-lookup"><span data-stu-id="ed511-103">Use Microsoft Teams meetings with Canvas</span></span>

<span data-ttu-id="ed511-104">Microsoft Teams 모임은 교육자 및 학생이 LMS(Learning Management System) 및 LMS(Learning 관리 시스템) 사이를 쉽게 탐색하는 데 도움이 되는 LTI(Learning 도구 상호 운영성) Teams.</span><span class="sxs-lookup"><span data-stu-id="ed511-104">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="ed511-105">사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="ed511-106">Microsoft Office 365 관리자</span><span class="sxs-lookup"><span data-stu-id="ed511-106">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="ed511-107">Instructure Canvas 내에서 Microsoft Teams 통합을 관리하기 전에 Canvas 관리자 설정을 완료하기 전에 캔버스의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱을 Microsoft Office 365 Microsoft Azure 테넌트에서 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-107">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="ed511-108">Canvas에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-108">Sign in to Canvas.</span></span>

2. <span data-ttu-id="ed511-109">전역 **탐색에서** 관리자 링크를 선택한 다음 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-109">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="ed511-110">관리자 탐색에서 설정 **링크를** 선택한 다음 **통합 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-110">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="ed511-111">Microsoft 테넌트 이름 및 로그인 특성을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-111">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="ed511-112">Login 특성은 Canvas 사용자를 사용자와 연결하기 위해 Azure Active Directory 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-112">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="ed511-113">한 **번 설정** 업데이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-113">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="ed511-114">Canvas의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱에 대한 액세스를 승인하려면 테넌트 액세스 권한 부여 **링크를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-114">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="ed511-115">Microsoft Identity Platform 관리자 동의 끝점으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-115">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![사용 권한](media/permissions.png)

7. <span data-ttu-id="ed511-117">**수락을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed511-117">Select **Accept**.</span></span>

8. <span data-ttu-id="ed511-118">토글을 Microsoft Teams 동기화할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-118">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="ed511-120">Canvas Admin</span><span class="sxs-lookup"><span data-stu-id="ed511-120">Canvas Admin</span></span>

<span data-ttu-id="ed511-121">LTI Microsoft Teams 1.3 통합을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-121">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="ed511-122">Canvas 관리자는 사용자 환경 내에서 Microsoft Teams 모임 LTI 앱을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-122">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="ed511-123">앱에 대한 LTI 클라이언트 ID를 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-123">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="ed511-124">Microsoft Teams 모임 - 1700000000000703</span><span class="sxs-lookup"><span data-stu-id="ed511-124">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="ed511-125">관리자 **설정 앱에**  >  **액세스합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed511-125">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="ed511-126">**+ 앱을 선택하여** LTI Teams 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-126">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="ed511-128">구성 **유형으로 클라이언트 ID를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-128">Select **By Client ID** for configuration type.</span></span>

   ![앱 추가](media/add-app.png)

4. <span data-ttu-id="ed511-130">제공된 클라이언트 ID를 입력한 다음 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed511-130">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="ed511-131">확인을 위해 Microsoft Teams 모임 LTI 앱 이름을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-131">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="ed511-132">**설치** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-132">Select **Install**.</span></span>

   <span data-ttu-id="ed511-133">모임 Microsoft Teams LTI 앱이 외부 앱 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-133">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="ed511-134">Canvas 과정 사용</span><span class="sxs-lookup"><span data-stu-id="ed511-134">Enable for Canvas Courses</span></span>

<span data-ttu-id="ed511-135">과정 내에서 LTI를 사용하려면 Canvas 과정의 강사는 통합 동기화를 사용하도록 설정해야 합니다. 해당 강사가 각 강의를 사용하도록 설정해야 해당 Teams 수 있습니다. 전역 메커니즘을 만들 수 Teams 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-135">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="ed511-136">이는 원치 않는 사용자가 생성되지 않도록 Teams 않도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed511-136">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="ed511-137">강사에게 각 [](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) 과정에 대한 LTI를 사용하도록 설정하고 통합 설정을 완료하려면 강사 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed511-137">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
