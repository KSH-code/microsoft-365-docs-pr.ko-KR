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
ms.openlocfilehash: 50e4e8ef912a8f19f379bba29b328a5a27358b5c
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256906"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="2256e-103">Canvas에서 Microsoft Teams 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="2256e-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2256e-104">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2256e-105">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2256e-106">Microsoft Teams 클래스는 교사와 학생이 LMS(Learning Management System) 및 LMS(Learning 관리 시스템) 사이를 쉽게 탐색하는 데 도움이 되는 LTI(Learning 도구 상호 운영성) 앱입니다Teams.</span><span class="sxs-lookup"><span data-stu-id="2256e-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="2256e-107">사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="2256e-108">Microsoft Office 365 관리자</span><span class="sxs-lookup"><span data-stu-id="2256e-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="2256e-109">Instructure Canvas 내에서 Microsoft Teams 통합을 관리하기 전에 Canvas 관리자 설정을 완료하기 전에 캔버스의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱을 Microsoft Office 365 Microsoft Azure 테넌트에서 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="2256e-110">Canvas에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-110">Sign in to Canvas.</span></span>

2. <span data-ttu-id="2256e-111">전역 **탐색에서** 관리자 링크를 선택한 다음 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="2256e-112">관리자 탐색에서 설정 **링크를** 선택한 다음 **통합 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="2256e-113">토글을 Microsoft Teams 동기화를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="2256e-113">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="2256e-115">Microsoft 테넌트 이름 및 로그인 특성을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-115">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="2256e-116">Login 특성은 Canvas 사용자를 사용자와 연결하기 위해 Azure Active Directory 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-116">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="2256e-117">한 **번 설정** 업데이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-117">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="2256e-118">Canvas의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱에 대한 액세스를 승인하려면 테넌트 액세스 권한 부여 **링크를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-118">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="2256e-119">Microsoft Identity Platform 관리자 동의 끝점으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-119">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![사용 권한](media/permissions.png)

8. <span data-ttu-id="2256e-121">**수락을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2256e-121">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="2256e-122">Canvas Admin</span><span class="sxs-lookup"><span data-stu-id="2256e-122">Canvas Admin</span></span>

<span data-ttu-id="2256e-123">LTI Microsoft Teams 1.3 통합을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="2256e-124">Canvas 관리자는 사용자 환경 내에 Microsoft Teams 클래스 LTI 앱을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="2256e-125">앱에 대한 LTI 클라이언트 ID를 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="2256e-126">Microsoft Teams 클래스 - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="2256e-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="2256e-127">관리자 **설정 앱에**  >  **액세스합니다.**</span><span class="sxs-lookup"><span data-stu-id="2256e-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="2256e-128">**+ 앱을 선택하여** LTI Teams 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-128">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="2256e-130">구성 **유형으로 클라이언트 ID를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-130">Select **By Client ID** for configuration type.</span></span>

   ![앱 추가](media/add-app.png)

4. <span data-ttu-id="2256e-132">제공된 클라이언트 ID를 입력한 다음 제출을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2256e-132">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="2256e-133">확인을 위해 클라이언트 Microsoft Teams 클래스 LTI 앱 이름을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="2256e-134">**설치** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-134">Select **Install**.</span></span>

   <span data-ttu-id="2256e-135">LTI Microsoft Teams 클래스가 외부 앱 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2256e-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
