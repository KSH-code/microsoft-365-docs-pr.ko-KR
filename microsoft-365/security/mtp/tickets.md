---
title: ServiceNow를 통한 티켓 만들기 및 추적
description: Microsoft 365 보안 센터는 ServiceNow에서 기본적으로 티켓을 작성 하 고 추적할 수 있는 기능을 통해 향상 되었습니다. 이를 통해 보안 관리자는 보안 점수 추천을 ServiceNow에 직접 전송 하 고 티켓을 만들 수 있습니다.
keywords: 보안, Microsoft 365, M365, 보안 점수, 보안 센터, ServiceNow, 티켓, 작업
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350336"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="b5f0a-105">ServiceNow를 통한 티켓 관리</span><span class="sxs-lookup"><span data-stu-id="b5f0a-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="b5f0a-106">Microsoft 365 보안 센터는 ServiceNow에서 기본적으로 티켓을 작성 하 고 추적할 수 있는 기능을 통해 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="b5f0a-107">이를 통해 보안 관리자는 [Microsoft 보안 점수](microsoft-secure-score.md) 향상 작업을 ServiceNow로 직접 전송 하 고 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="b5f0a-108">인시던트 관리 및 변경 관리 티켓을 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5f0a-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b5f0a-109">Prerequisites</span></span>

<span data-ttu-id="b5f0a-110">다음을 포함 하는 Microsoft 365 보안 센터 및 ServiceNow 인스턴스에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="b5f0a-111">Kingston 이상 버전</span><span class="sxs-lookup"><span data-stu-id="b5f0a-111">Kingston or higher version</span></span>
* <span data-ttu-id="b5f0a-112">관리자 용 자격 증명 포함</span><span class="sxs-lookup"><span data-stu-id="b5f0a-112">Have admin HI credentials</span></span>
* <span data-ttu-id="b5f0a-113">대상 공급 업체 인스턴스에 대해 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="b5f0a-114">ServiceNow에서는 사용자가 ServiceNow 인스턴스에서 기본 설정을 유지할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="b5f0a-115">사용자 지정 내용이 있으면 설치 검사 목록이 완료 되 고 Microsoft 365 보안 센터와 통합 되는 데 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="b5f0a-116">데이터 교환</span><span class="sxs-lookup"><span data-stu-id="b5f0a-116">Data exchange</span></span>

<span data-ttu-id="b5f0a-117">Microsoft 365 보안 센터를 ServiceNow에 연결 하면 Microsoft는 다음과 같은 추가 데이터를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="b5f0a-118">ServiceNow 인스턴스 이름</span><span class="sxs-lookup"><span data-stu-id="b5f0a-118">ServiceNow instance name</span></span>
* <span data-ttu-id="b5f0a-119">ServiceNow 클라이언트 ID</span><span class="sxs-lookup"><span data-stu-id="b5f0a-119">ServiceNow client ID</span></span>
* <span data-ttu-id="b5f0a-120">ServiceNow 클라이언트 암호</span><span class="sxs-lookup"><span data-stu-id="b5f0a-120">ServiceNow client secret</span></span>
* <span data-ttu-id="b5f0a-121">ServiceNow 액세스 & 새로 고침 토큰</span><span class="sxs-lookup"><span data-stu-id="b5f0a-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="b5f0a-122">Microsoft 365 보안 센터에서 ServiceNow 티켓을 만드는 경우 다음 데이터가 ServiceNow로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="b5f0a-123">티켓 만들기를 시작 하는 사용자 ID</span><span class="sxs-lookup"><span data-stu-id="b5f0a-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="b5f0a-124">작업 이름</span><span class="sxs-lookup"><span data-stu-id="b5f0a-124">Task name</span></span>
* <span data-ttu-id="b5f0a-125">작업 설명</span><span class="sxs-lookup"><span data-stu-id="b5f0a-125">Task description</span></span>
* <span data-ttu-id="b5f0a-126">우선 순위</span><span class="sxs-lookup"><span data-stu-id="b5f0a-126">Priority</span></span>
* <span data-ttu-id="b5f0a-127">기한</span><span class="sxs-lookup"><span data-stu-id="b5f0a-127">Due date</span></span>
* <span data-ttu-id="b5f0a-128">권장 사항 원본 (사용자 권장 사항 또는 Microsoft 권장 사항)</span><span class="sxs-lookup"><span data-stu-id="b5f0a-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="b5f0a-129">추천 범주 (장치, 데이터, 앱, Id, 인프라)</span><span class="sxs-lookup"><span data-stu-id="b5f0a-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="b5f0a-130">ServiceNow에 Microsoft 365 보안 센터 연결</span><span class="sxs-lookup"><span data-stu-id="b5f0a-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="b5f0a-131">ServiceNow을 사용할 것인지 묻는 카드를 볼 수 있는 Microsoft 365 보안 센터 홈 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![ServiceNow 사용](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="b5f0a-133">여기에서 Microsoft 365 커넥터 앱에 대 한 권한을 부여 하는 지침을 따라 ServiceNow 설정 페이지에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="b5f0a-134">Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하는 경우에는 개인 자격 증명이 아닌 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="b5f0a-135">연결에 대 한 지침을 읽고 인증을 승인 하면 Microsoft 365 보안 센터 연결 페이지와 ServiceNow Microsoft 365 티켓 커넥터 앱 환경 모두에서 연결 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="b5f0a-136">이제 작업 만들기를 시작 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="b5f0a-137">작업 만들기 및 ServiceNow에 공유</span><span class="sxs-lookup"><span data-stu-id="b5f0a-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="b5f0a-138">통합이 설정 되 면 특정 Microsoft 보안 점수 향상 작업을 기반으로 ServiceNow 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="b5f0a-139">Microsoft 365 보안 센터 포털의 보안 점수에 있는 개선 작업으로 이동한 후 "공유" 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="b5f0a-140">드롭다운 옵션 중 하나는 ServiceNow입니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-140">One of the dropdown options is ServiceNow.</span></span>

![보안 점수의 ServiceNow 공유](../images/servicenow-share.png)

<span data-ttu-id="b5f0a-142">그런 다음 우선 순위를 설정 하 고 이름, 설명 또는 기한을 편집할 수 있는 작업을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="b5f0a-143">필수 필드를 모두 입력 한 후에는 해당 작업을 ServiceNow로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="b5f0a-144">이 작업은 Microsoft 365 보안 및 구성 변경 요청으로 ServiceNow에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="b5f0a-145">티켓 추적</span><span class="sxs-lookup"><span data-stu-id="b5f0a-145">Track tickets</span></span>

<span data-ttu-id="b5f0a-146">ServiceNow 변경 관리 및 인시던트 관리 티켓이 만들어지면 Microsoft 365 보안 센터 홈 페이지에 카드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="b5f0a-147">이러한 카드에서 티켓을 만들거나, 모든 티켓을 보거나, ServiceNow 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 변경 관리 티켓](../images/change-management-375.png)  ![ServiceNow 인시던트 관리 티켓](../images/incident-management-375.png)

<span data-ttu-id="b5f0a-150">Microsoft 365 보안 센터에서 ServiceNow 통합을 다시 구축 하거나 관리 하려면 카드 중 하나에서 **servicenow 구성 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="b5f0a-151">여기에서 현재 ServiceNow 연결을 제거 하 고 티켓 상태 이름을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="b5f0a-152">Microsoft 365 보안 센터에 ServiceNow 티켓이 표시 되 면 작업이 다른 보안 대시보드 항목과 함께 추적 하 고 작업을 수행할 수 있는 위치에 살고 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b5f0a-153">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="b5f0a-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="b5f0a-154">설치 검사 목록의 첫 번째 단계에서 오류가 발생 함 (OAuth 만들기)</span><span class="sxs-lookup"><span data-stu-id="b5f0a-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="b5f0a-155">**오류 메시지**: 테이블의 범위 간 액세스 정책으로 인해 ' x_mioms_m365ticket ' 범위의 ' oauth_entity '에 대 한 읽기 작업이 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="b5f0a-156">이 앱에서는 ServiceNow 인스턴스의 관리자가 OAuth 엔터티를 만들고 읽을 수 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="b5f0a-157">이 오류는 ServiceNow 인스턴스의 사용자 지정으로 인해 OAuth 엔터티를 만들거나 읽을 수 있는 사용자를 제한 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="b5f0a-158">ServiceNow에서는 사용자가 기본 기능을 그대로 유지할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="b5f0a-159">"응용 프로그램 레지스트리" 테이블 구성을 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="b5f0a-160">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="b5f0a-160">Label = Application Registeries</span></span>
* <span data-ttu-id="b5f0a-161">이름 = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="b5f0a-161">Name = oauth_entity</span></span>
* <span data-ttu-id="b5f0a-162">액세스 가능 = 모든 응용 프로그램 범위</span><span class="sxs-lookup"><span data-stu-id="b5f0a-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="b5f0a-163">읽을 수 있음 = 확인란 선택</span><span class="sxs-lookup"><span data-stu-id="b5f0a-163">Can read = check box selected</span></span>

<span data-ttu-id="b5f0a-164">**ServiceNow에서는 사용자가 기본 기능을 그대로 유지할 것을 권장 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b5f0a-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="b5f0a-165">Microsoft 365 보안 & 준수 커넥터에 대해 만들어진 OAuth 엔터티를 확인 하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="b5f0a-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="b5f0a-166">ServiceNow에서 응용 프로그램 레지스트리 (Menu > System OAuth > Application Registry)로 이동 하 여 사용자가 만든 OAuth 엔터티 (할당 한 이름)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="b5f0a-167">Microsoft 365 보안 & 준수 커넥터에 대 한 설치 검사 목록 2 단계에서 만든 통합 사용자의 유효성을 검사 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b5f0a-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="b5f0a-168">ServiceNow에서 사용자 > 관리 > 사용자로 이동 하 여 만든 통합 사용자 (할당 한 이름)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="b5f0a-169">Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하는 경우에는 개인 자격 증명이 아닌 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="b5f0a-170">설치를 완료 하 고 단계를 설정 했지만 홈 페이지에서 ServiceNow 카드를 볼 수 없으며 Microsoft 보안 점수에 공유 아이콘이 표시 되지 않음</span><span class="sxs-lookup"><span data-stu-id="b5f0a-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="b5f0a-171">로 https://security.microsoft.com/ticketProvisioning이동 하 여 프로 비전 페이지의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="b5f0a-172">**저장** 을 선택 하 고 홈 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="b5f0a-173">카드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5f0a-173">The cards should appear.</span></span>
