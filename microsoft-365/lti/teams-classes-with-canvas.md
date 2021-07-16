---
title: Canvas에서 Microsoft Teams 클래스 사용
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
description: Canvas Microsoft Teams 클래스 통합
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454688"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="0b9c1-103">Canvas에서 Microsoft Teams 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="0b9c1-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="0b9c1-104">Microsoft Teams 클래스는 교사와 학생이 LMS(Learning Management System) 및 LMS(Learning 관리 시스템) 사이를 쉽게 탐색하는 데 도움이 되는 LTI(Learning 도구 상호 운영성) 앱입니다Teams.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="0b9c1-105">사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="0b9c1-106">배포 전의 선행 구성</span><span class="sxs-lookup"><span data-stu-id="0b9c1-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="0b9c1-107">현재 클래스 Teams LTI는 Canvas 사용자와 제한된 범위의 AAD(Microsoft Azure Active Directory) 동기화만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="0b9c1-108">테넌트는 Canvas 필드(전자 메일, 사용자 ID 또는 SIS ID)와 Microsoft AAD의 UPN 간에 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="0b9c1-109">동기화 기능에 대한 유연성을 확장하기 위해 작업 중이지만, 그 동안 Canvas의 사용자가 AAD의 UPN과 일치하지 않는 사용자는 Canvas와 동기화된 Teams 클래스에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="0b9c1-110">Canvas와 Microsoft 간에 사용자를 매핑하는 데는 단일 Microsoft 테넌트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="0b9c1-111">그룹이 중복되는 것을 방지하기 위해 Class Teams LTI를 사용하기 전에 SDS를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="0b9c1-112">Microsoft Office 365 관리자</span><span class="sxs-lookup"><span data-stu-id="0b9c1-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="0b9c1-113">Instructure Canvas 내에서 Microsoft Teams 통합을 관리하기 전에 Canvas 관리자 설정을 완료하기 전에 캔버스의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱을 Microsoft Office 365 Microsoft Azure 테넌트에서 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="0b9c1-114">Canvas에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="0b9c1-115">전역 **탐색에서** 관리자 링크를 선택한 다음 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="0b9c1-116">관리자 탐색에서 설정 **링크를** 선택한 다음 **통합 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="0b9c1-117">토글을 Microsoft Teams 동기화를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="0b9c1-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="0b9c1-119">Microsoft 테넌트 이름 및 로그인 특성을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="0b9c1-120">Login 특성은 Canvas 사용자를 사용자와 연결하기 위해 Azure Active Directory 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="0b9c1-121">한 **번 설정** 업데이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="0b9c1-122">Canvas의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱에 대한 액세스를 승인하려면 테넌트 액세스 권한 부여 **링크를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="0b9c1-123">Microsoft Identity Platform 관리자 동의 끝점으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![사용 권한](media/permissions.png)

8. <span data-ttu-id="0b9c1-125">**수락을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b9c1-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="0b9c1-126">Canvas Admin</span><span class="sxs-lookup"><span data-stu-id="0b9c1-126">Canvas Admin</span></span>

<span data-ttu-id="0b9c1-127">LTI Microsoft Teams 1.3 통합을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="0b9c1-128">Canvas 관리자는 사용자 환경 내에 Microsoft Teams 클래스 LTI 앱을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="0b9c1-129">앱에 대한 LTI 클라이언트 ID를 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="0b9c1-130">Microsoft Teams 클래스 - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="0b9c1-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="0b9c1-131">관리자 **설정 앱에**  >  **액세스합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b9c1-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="0b9c1-132">**+ 앱을 선택하여** LTI Teams 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="0b9c1-134">구성 **유형으로 클라이언트 ID를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-134">Select **By Client ID** for configuration type.</span></span>

   ![앱 추가](media/add-app.png)

4. <span data-ttu-id="0b9c1-136">제공된 클라이언트 ID를 입력한 다음 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b9c1-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="0b9c1-137">확인을 위해 클라이언트 Microsoft Teams 클래스 LTI 앱 이름을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="0b9c1-138">**설치** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-138">Select **Install**.</span></span>

   <span data-ttu-id="0b9c1-139">LTI Microsoft Teams 클래스가 외부 앱 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="0b9c1-140">Canvas에 대한 LTI 앱 사용 과정</span><span class="sxs-lookup"><span data-stu-id="0b9c1-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="0b9c1-141">과정 내에서 LTI 앱을 사용하려면 Canvas 과정의 강사는 통합 동기화를 사용하도록 설정해야 합니다. 각 강사는 해당 팀을 만들 수 있어야 합니다. 팀을 만들기 위한 전역 메커니즘은 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="0b9c1-142">이는 원치 않는 팀이 만들어지지 않도록 예방 조치로 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="0b9c1-143">각 과정에 대해 [](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) LTI 앱을 사용하도록 설정하고 통합 설정을 완료하려면 강사 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b9c1-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
