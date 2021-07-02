---
title: LTI 앱 개요
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman, sovaish
ms.date: 06/15/2021
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- M365-modern-desktop
localization_priority: None
description: M365의 Learning LTI(Learning Tools Interoperability) Office 및 Office 앱을 LMS(Learning Management System)에 통합할 때 교육자들에게 도움이 되는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 4fd7b25b6463eec4f681e3090bb65db8b00351a8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256685"
---
# <a name="integrating-microsoft-products-with-your-learning-management-system-lms"></a><span data-ttu-id="f6d8c-103">LMS(Learning 관리 시스템)와 Microsoft 제품 통합</span><span class="sxs-lookup"><span data-stu-id="f6d8c-103">Integrating Microsoft products with your Learning Management System (LMS)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6d8c-104">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f6d8c-105">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

- [<span data-ttu-id="f6d8c-106">OneDrive 캔버스가 있는 LTI</span><span class="sxs-lookup"><span data-stu-id="f6d8c-106">OneDrive LTI with Canvas</span></span>](#onedrive-lti-with-canvas)
- [<span data-ttu-id="f6d8c-107">Teams Canvas를 통해 모임 LTI</span><span class="sxs-lookup"><span data-stu-id="f6d8c-107">Teams Meetings LTI with Canvas</span></span>](#teams-meetings-lti-with-canvas)
- [<span data-ttu-id="f6d8c-108">Teams 클래스 LTI</span><span class="sxs-lookup"><span data-stu-id="f6d8c-108">Teams Classes LTI</span></span>](#teams-classes-lti)

<span data-ttu-id="f6d8c-109">Microsoft Education 및 타사 파트너는 교육 및 학습의 흐름이 솔루션 경계를 넘고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-109">Microsoft Education and our third-party partners understand that the flow of teaching and learning invariably crosses solution boundaries.</span></span> <span data-ttu-id="f6d8c-110">당사는 도구를 전환하지 않고도 교육자 및 학습자들이 목표에 집중하도록 보다 원활한 환경을 제공하기 위해 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-110">We're working on providing more seamless experiences, keeping educators and learners focused on their goals, rather than having to juggle tools.</span></span> <span data-ttu-id="f6d8c-111">Microsoft는 LMS(관리 시스템) 내부 및 그와 함께 교육 및 학습이 Learning 통합하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-111">We're integrating Microsoft products wherever teaching and learning occurs, including within and alongside Learning Management Systems (LMS).</span></span> <span data-ttu-id="f6d8c-112">Microsoft는 LMS 파트너와 협력하여 Microsoft를 LMS에 직접 활용하는 Learning [Tools Interoperability(LTI)](https://www.imsglobal.org/activity/learning-tools-interoperability) 표준을 사용하여 도구 제품군을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-112">We've worked with our LMS partners to create a suite of tools using the [Learning Tools Interoperability (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) that brings the best of Microsoft directly into your LMS.</span></span>

<span data-ttu-id="f6d8c-113">이러한 도구에는 새로운 OneDrive LTI 앱, 새 Teams 모임 LTI 앱 및 새 클래스 Teams 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-113">These tools include a new OneDrive LTI app, a new Teams Meetings LTI app, and a new Class Teams LTI app.</span></span> <span data-ttu-id="f6d8c-114">이러한 새 도구는 LTI 1.3 및 LTI Advantage 표준과 매우 안전하고 완벽하게 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-114">These new tools are highly secure and fully compatible with LTI 1.3 and LTI Advantage standards.</span></span> <span data-ttu-id="f6d8c-115">OneDrive LTI 앱을 사용하면 강사와 학생이 OneDrive 클라우드 저장소 및 Office 365 파일을 LMS 내의 과제 및 콘텐츠 만들기 워크플로로 직접 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-115">The OneDrive LTI app allows educators and students to bring OneDrive cloud storage and Office 365 files directly into assignment and content creation workflows within an LMS.</span></span> <span data-ttu-id="f6d8c-116">Teams 모임 LTI 앱을 사용하면 강사와 학생이 LMS의 모임 허브 내에서 Teams 모임을 관리, 예약 및 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-116">The Teams Meetings LTI app allows educators and students to manage, schedule, and access their Teams Meetings from within a meetings hub in their LMS.</span></span> <span data-ttu-id="f6d8c-117">수업 Teams LTI 앱을 사용하면 강사는 일별 로스터 업데이트가 있는 LMS 과정 로스터를 사용하여 LMS 내에서 과정에 대한 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-117">The Class Teams LTI app allows educators to create a team for their course within their LMS using the LMS course roster with daily roster updates.</span></span> <span data-ttu-id="f6d8c-118">그런 다음 학생은 LMS 내에서 바로 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-118">Students can then access the team right from within the LMS.</span></span> <span data-ttu-id="f6d8c-119">이러한 새로운 도구를 고객에게 제공하게 하여 여러분의 의견에 따라 솔루션을 계속 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-119">We are excited to bring these new tools to customers and continue to improve our solutions according to your feedback.</span></span>

## <a name="onedrive-lti-with-canvas"></a><span data-ttu-id="f6d8c-120">OneDrive 캔버스가 있는 LTI</span><span class="sxs-lookup"><span data-stu-id="f6d8c-120">OneDrive LTI with Canvas</span></span>

<span data-ttu-id="f6d8c-121">자세한 내용은 Microsoft OneDrive LMS(Learning 관리 시스템)를 사용하여 자세히 알아보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-121">Learn more about using Microsoft OneDrive with your Learning Management System (LMS).</span></span>

- <span data-ttu-id="f6d8c-122">**워크플로에 Microsoft Office 365 직접 연결**</span><span class="sxs-lookup"><span data-stu-id="f6d8c-122">**Brings Microsoft Office 365 directly into your workflows**</span></span>

<span data-ttu-id="f6d8c-123">이 Microsoft OneDrive LTI 앱은 LMS와 통합되어 다음을 Microsoft OneDrive Microsoft Office 365 워크플로에 직접 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-123">The Microsoft OneDrive LTI app integrates with your LMS to bring Microsoft OneDrive and Microsoft Office 365 directly into your most important workflows that include:</span></span>

- <span data-ttu-id="f6d8c-124">리소스 연결 및 콘텐츠 구성</span><span class="sxs-lookup"><span data-stu-id="f6d8c-124">Attaching resources and organizing content.</span></span>
- <span data-ttu-id="f6d8c-125">공동 작업 문서 시작</span><span class="sxs-lookup"><span data-stu-id="f6d8c-125">Starting collaborative documents.</span></span>
- <span data-ttu-id="f6d8c-126">배정 만들기 및 그라데이트</span><span class="sxs-lookup"><span data-stu-id="f6d8c-126">Creating and grading assignments.</span></span>

- <span data-ttu-id="f6d8c-127">**최신 LTI 표준을 안전하고 완벽하게 준수**</span><span class="sxs-lookup"><span data-stu-id="f6d8c-127">**Secure and fully compliant with latest LTI standards**</span></span>

<span data-ttu-id="f6d8c-128">이 Microsoft OneDrive LTI 앱은 LTI 1.3 및 LTI 이점과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-128">The Microsoft OneDrive LTI App is compatible with LTI 1.3 and LTI Advantage.</span></span> <span data-ttu-id="f6d8c-129">이러한 이점을 통해 보안이 강화되고 긴밀하게 통합된 사용자 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-129">This advantage allows for a highly secure and tightly integrated user experience.</span></span>

- <span data-ttu-id="f6d8c-130">**현대적이고 풍부한 사용자 환경**</span><span class="sxs-lookup"><span data-stu-id="f6d8c-130">**Modern and Rich User Experience**</span></span>

<span data-ttu-id="f6d8c-131">LTI Microsoft OneDrive LMS 환경으로 Microsoft의 최고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-131">The Microsoft OneDrive LTI App brings the best of Microsoft right into your LMS experience.</span></span> <span data-ttu-id="f6d8c-132">LMS의 기존 Office 365 통합을 개선하고 있으며, 새로운 확장된 Microsoft OneDrive 파일 선택기 및 Office 파일을 위한 더 풍부한 편집 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-132">We're improving upon the existing Office 365 integration in your LMS by delivering a more modern user experience, complete with a new and expanded Microsoft OneDrive file picker and richer editing experiences for Office files.</span></span> <span data-ttu-id="f6d8c-133">또한 Microsoft는 앞으로 Microsoft OneDrive LTI 앱을 완전히 소유합니다. 즉, 항상 Microsoft에서 최신 및 가장 좋은 앱을 자동으로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-133">Microsoft will also fully own the Microsoft OneDrive LTI App going forward, which means you’ll always get the latest and greatest from Microsoft automatically.</span></span>

<span data-ttu-id="f6d8c-134">LTI Microsoft OneDrive 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-134">The Microsoft OneDrive LTI App allows you to:</span></span>

- <span data-ttu-id="f6d8c-135">Word Office 365, 프레젠테이션, 프레젠테이션 PowerPoint 등의 Excel 파일을 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-135">Attach Office 365 files including Word documents, PowerPoint presentations, and Excel from the Rich Content Editor.</span></span>
- <span data-ttu-id="f6d8c-136">클라우드 Office 365 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-136">Distribute Office 365 cloud assignments.</span></span>
- <span data-ttu-id="f6d8c-137">개인 및 과정 파일을 보고 Microsoft OneDrive 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-137">View and organize your personal and course Microsoft OneDrive files.</span></span>
- <span data-ttu-id="f6d8c-138">과정 구성원이 공유 문서에서 실시간으로 공동 작업할 수 있는 공동 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-138">Create collaborations where course members can work together on shared documents in real time.</span></span>
- <span data-ttu-id="f6d8c-139">개인 및 Microsoft OneDrive 계정을 포함하여 여러 사용자 계정에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-139">Access multiple Microsoft OneDrive accounts, including personal and school accounts.</span></span>
- <span data-ttu-id="f6d8c-140">교육 Office 365 모듈과 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-140">Integrate Office 365 files with your course modules.</span></span>
- <span data-ttu-id="f6d8c-141">LMS와의 Single Sign-On에 Microsoft 계정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-141">Use your Microsoft account for single sign-on with your LMS.</span></span>

<span data-ttu-id="f6d8c-142">구성 단계는 [Canvas와 Microsoft OneDrive LTI 사용을 참조하세요.](use-onedrive-with-lms.md)</span><span class="sxs-lookup"><span data-stu-id="f6d8c-142">For configuration steps, see [Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md).</span></span>

## <a name="teams-lti-apps"></a><span data-ttu-id="f6d8c-143">Teams LTI 앱</span><span class="sxs-lookup"><span data-stu-id="f6d8c-143">Teams LTI apps</span></span>

### <a name="teams-meetings-lti-with-canvas"></a><span data-ttu-id="f6d8c-144">Teams Canvas를 통해 모임 LTI</span><span class="sxs-lookup"><span data-stu-id="f6d8c-144">Teams Meetings LTI with Canvas</span></span>

<span data-ttu-id="f6d8c-145">Microsoft Teams LTI 앱은 관리자가 Teams 교육 기관의 LMS 과정에 통합하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-145">Microsoft Teams meetings LTI app helps admins incorporate Teams meetings into their educational institution's LMS course.</span></span> <span data-ttu-id="f6d8c-146">교육자 및 학생은 LMS 내에서 과거 및 예정된 모임을 보고, 개별 또는 재발 모임을 예약하고, 과정과 관련된 팀 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-146">Educators and students can view past and upcoming meetings, schedule individual or recurring meetings, and join team meetings related to the course, all from within their LMS.</span></span>

<span data-ttu-id="f6d8c-147">구성 단계는 Canvas와 함께 Microsoft Teams [사용을 참조하세요.](teams-meetings-with-canvas.md)</span><span class="sxs-lookup"><span data-stu-id="f6d8c-147">For configuration steps, see [Use Microsoft Teams meetings with Canvas](teams-meetings-with-canvas.md).</span></span>

### <a name="teams-classes-lti"></a><span data-ttu-id="f6d8c-148">Teams 클래스 LTI</span><span class="sxs-lookup"><span data-stu-id="f6d8c-148">Teams Classes LTI</span></span>

<span data-ttu-id="f6d8c-149">Microsoft Teams 클래스 LTI 앱은 강사와 학생이 LMS와 LMS를 탐색하는 데 Teams.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-149">The Microsoft Teams classes LTI app helps educators and students navigate between their LMS and Teams.</span></span> <span data-ttu-id="f6d8c-150">사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-150">Users can access their class teams associated with their course directly from within their LMS.</span></span> <span data-ttu-id="f6d8c-151">구성 단계는 아래에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6d8c-151">You can find configuration steps below:</span></span>

- <span data-ttu-id="f6d8c-152">**Teams 클래스 LTI는 Canvas와** [Microsoft Teams 클래스를 사용하세요.](teams-classes-with-canvas.md)</span><span class="sxs-lookup"><span data-stu-id="f6d8c-152">**Teams Classes LTI with Canvas** [Use Microsoft Teams classes with Canvas](teams-classes-with-canvas.md).</span></span>
