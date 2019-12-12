---
title: ServiceNow를 통한 티켓 만들기 및 추적
description: Microsoft 365 보안 센터는 ServiceNow에서 기본적으로 티켓을 작성 하 고 추적할 수 있는 기능을 통해 향상 되었습니다. 보안 관리자는 보안 점수 추천을 ServiceNow에 직접 전송 하 고 티켓을 만들 수 있습니다.
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
ms.openlocfilehash: e67ff2b28a6dec741b2ad7af5179dca226fb86ad
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962575"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="41350-105">ServiceNow를 통해 티켓 관리</span><span class="sxs-lookup"><span data-stu-id="41350-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="41350-106">Microsoft 365 보안 센터는 ServiceNow에서 기본적으로 티켓을 작성 하 고 추적할 수 있는 기능을 통해 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="41350-107">보안 관리자는 [Microsoft 보안 점수](microsoft-secure-score.md) 향상 작업을 ServiceNow로 바로 전송 하 고 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="41350-108">인시던트 관리 및 변경 관리 티켓을 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41350-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="41350-109">Prerequisites</span></span>

<span data-ttu-id="41350-110">다음을 포함 하는 Microsoft 365 보안 센터 및 ServiceNow 인스턴스에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="41350-111">Kingston 이상 버전</span><span class="sxs-lookup"><span data-stu-id="41350-111">Kingston or higher version</span></span>
* <span data-ttu-id="41350-112">관리자 용 자격 증명 포함</span><span class="sxs-lookup"><span data-stu-id="41350-112">Have admin HI credentials</span></span>
* <span data-ttu-id="41350-113">대상 공급 업체 인스턴스에 대해 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="41350-114">ServiceNow에서는 사용자가 ServiceNow 인스턴스에 기본 설정을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="41350-115">사용자 지정 내용이 있으면 설치 검사 목록이 완료 되 고 Microsoft 365 보안 센터와 통합 될 때 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="41350-116">데이터 교환</span><span class="sxs-lookup"><span data-stu-id="41350-116">Data exchange</span></span>

<span data-ttu-id="41350-117">Microsoft 365 보안 센터를 ServiceNow에 연결 하면 Microsoft에서 다음과 같은 추가 데이터를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41350-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="41350-118">ServiceNow 인스턴스 이름</span><span class="sxs-lookup"><span data-stu-id="41350-118">ServiceNow instance name</span></span>
* <span data-ttu-id="41350-119">ServiceNow 클라이언트 ID</span><span class="sxs-lookup"><span data-stu-id="41350-119">ServiceNow client ID</span></span>
* <span data-ttu-id="41350-120">ServiceNow 클라이언트 암호</span><span class="sxs-lookup"><span data-stu-id="41350-120">ServiceNow client secret</span></span>
* <span data-ttu-id="41350-121">ServiceNow 액세스 & 새로 고침 토큰</span><span class="sxs-lookup"><span data-stu-id="41350-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="41350-122">Microsoft 365 보안 센터에서 ServiceNow 티켓을 만들면 다음 데이터가 ServiceNow로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41350-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="41350-123">티켓 만들기를 시작 하는 사용자 ID</span><span class="sxs-lookup"><span data-stu-id="41350-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="41350-124">작업 이름</span><span class="sxs-lookup"><span data-stu-id="41350-124">Task name</span></span>
* <span data-ttu-id="41350-125">작업 설명</span><span class="sxs-lookup"><span data-stu-id="41350-125">Task description</span></span>
* <span data-ttu-id="41350-126">우선 순위</span><span class="sxs-lookup"><span data-stu-id="41350-126">Priority</span></span>
* <span data-ttu-id="41350-127">기한</span><span class="sxs-lookup"><span data-stu-id="41350-127">Due date</span></span>
* <span data-ttu-id="41350-128">권장 사항 원본 (사용자 권장 사항 또는 Microsoft 권장 사항)</span><span class="sxs-lookup"><span data-stu-id="41350-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="41350-129">추천 범주 (장치, 데이터, 앱, Id, 인프라)</span><span class="sxs-lookup"><span data-stu-id="41350-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="41350-130">ServiceNow에 Microsoft 365 보안 센터 연결</span><span class="sxs-lookup"><span data-stu-id="41350-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="41350-131">Microsoft 365 보안 센터 홈 페이지로 이동 하 여 ServiceNow 연결 카드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![ServiceNow 사용](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="41350-133">"ServiceNow에 연결"을 선택 하 여 ServiceNow 설정 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="41350-134">지침에 따라 Microsoft 365 커넥터 앱에 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="41350-135">Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하기 전에 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="41350-136">개인 자격 증명은 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="41350-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="41350-137">지침을 따르고 연결에 대 한 인증을 받은 후 Microsoft 365 보안 센터 연결 페이지와 ServiceNow Microsoft 365 티켓 커넥터 앱 환경에서 연결 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="41350-138">이제 작업 만들기를 시작 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="41350-139">작업 만들기 및 ServiceNow에 공유</span><span class="sxs-lookup"><span data-stu-id="41350-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="41350-140">통합이 설정 되 면 특정 Microsoft 보안 점수 향상 작업을 기반으로 ServiceNow 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41350-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="41350-141">Microsoft 365 보안 센터 포털의 보안 점수에 있는 개선 작업으로 이동한 후 "공유" 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="41350-142">드롭다운 옵션 중 하나는 ServiceNow입니다.</span><span class="sxs-lookup"><span data-stu-id="41350-142">One of the dropdown options is ServiceNow.</span></span>

![보안 점수의 ServiceNow 공유](../images/servicenow-share.png)

<span data-ttu-id="41350-144">우선 순위를 설정 하 고 이름, 설명 또는 기한을 편집할 수 있는 작업이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41350-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="41350-145">필수 필드를 모두 입력 한 후에는 해당 작업을 ServiceNow로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="41350-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="41350-146">이 작업은 Microsoft 365 보안 및 구성 변경 요청으로 ServiceNow에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41350-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="41350-147">티켓 추적</span><span class="sxs-lookup"><span data-stu-id="41350-147">Track tickets</span></span>

<span data-ttu-id="41350-148">ServiceNow 변경 관리 및 인시던트 관리 티켓이 만들어지면 Microsoft 365 보안 센터 홈 페이지의 명함에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41350-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="41350-149">이러한 카드에서 티켓을 만들거나, 모든 티켓을 보거나, ServiceNow 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 변경 관리 티켓](../images/change-management-375.png)  ![ServiceNow 인시던트 관리 티켓](../images/incident-management-375.png)

<span data-ttu-id="41350-152">Microsoft 365 보안 센터에서 ServiceNow 통합을 다시 구축 하거나 관리 하려면 카드 중 하나에서 **servicenow 구성 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="41350-153">현재 ServiceNow 연결을 제거 하 고 티켓 상태 이름을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="41350-154">Microsoft 365 보안 센터에 ServiceNow 티켓이 표시 되 면 작업은 다른 보안 대시보드 항목과 함께 추적 하 고 작동할 수 있는 위치에 살고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="41350-155">문제 해결</span><span class="sxs-lookup"><span data-stu-id="41350-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="41350-156">설치 검사 목록의 첫 번째 단계에서 오류가 표시 됩니다 (OAuth 만들기).</span><span class="sxs-lookup"><span data-stu-id="41350-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="41350-157">**오류 메시지**: 테이블의 범위 간 액세스 정책으로 인해 ' x_mioms_m365ticket ' 범위에서 ' oauth_entity '에 대 한 읽기 작업이 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="41350-158">이 앱에서는 ServiceNow 인스턴스의 관리자가 OAuth 엔터티를 만들고 읽을 수 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="41350-159">이 오류는 ServiceNow 인스턴스의 사용자 지정으로 인해 OAuth 엔터티를 만들거나 읽을 수 있는 사용자를 제한 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="41350-160">**ServiceNow에서는 사용자가 기본 기능을 유지 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="41350-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="41350-161">"응용 프로그램 레지스트리" 테이블 구성을 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-161">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="41350-162">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="41350-162">Label = Application Registeries</span></span>
* <span data-ttu-id="41350-163">이름 = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="41350-163">Name = oauth_entity</span></span>
* <span data-ttu-id="41350-164">액세스 가능 = 모든 응용 프로그램 범위</span><span class="sxs-lookup"><span data-stu-id="41350-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="41350-165">읽을 수 있음 = 확인란 선택</span><span class="sxs-lookup"><span data-stu-id="41350-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="41350-166">Microsoft 365 보안 & 준수 커넥터에 대해 만들어진 OAuth 엔터티를 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="41350-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="41350-167">ServiceNow에서 응용 프로그램 레지스트리 (Menu > System OAuth > Application Registry)로 이동 하 여 사용자가 만든 OAuth 엔터티 (할당 한 이름)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-167">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="41350-168">Microsoft 365 보안 & 준수 커넥터에 대 한 설치 검사 목록을 사용 하 여 만든 통합 사용자의 유효성을 검사 하는 방법</span><span class="sxs-lookup"><span data-stu-id="41350-168">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="41350-169">ServiceNow에서 사용자 > 관리 > 사용자로 이동 하 여 만든 통합 사용자 (할당 한 이름)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-169">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="41350-170">Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하기 전에 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-170">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="41350-171">개인 자격 증명은 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="41350-171">Do not use your personal credentials.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="41350-172">설치가 완료 되었지만 티켓이 표시 되지 않으며 공유할 수 없음</span><span class="sxs-lookup"><span data-stu-id="41350-172">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="41350-173">설치 및 설치 단계가 완료 되었지만 홈 페이지에 ServiceNow 카드가 표시 되지 않고 Microsoft 보안 점수에서 ServiceNow을 공유할 수 없는 경우에 https://security.microsoft.com/ticketProvisioning는의 프로 비전 페이지 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-173">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="41350-174">**저장** 을 선택 하 고 홈 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="41350-174">Select **Save** and return to the home page.</span></span> <span data-ttu-id="41350-175">카드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-175">The cards should appear.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="41350-176">회사에서 Microsoft 365 보안 센터를 통해 ServiceNow에 연결 하지 못하도록 하는 single sign-on을 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-176">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="41350-177">회사에서 single sign-on을 사용 하도록 설정 하 고 오류가 수신 되거나 로그인이 실패 하면 두 솔루션 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-177">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="logging-into-servicenow-as-the-integration-user"></a><span data-ttu-id="41350-178">통합 사용자로 ServiceNow에 로그인</span><span class="sxs-lookup"><span data-stu-id="41350-178">Logging into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="41350-179">ServiceNow에서 인증 페이지로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-179">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="41350-180">오른쪽 위 모서리에서 링크 **하지 않음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-180">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="41350-181">설치 검사 목록에서 이전에 만든 통합 사용자로 ServiceNow에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-181">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="41350-182">ServiceNow 페이지에서 보안 + 준수 커넥터가 ServiceNow 계정에 연결할 수 있는지 여부를 묻는 **허용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-182">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="41350-183">설정 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-183">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="41350-184">보안 관리자 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="41350-184">Create a security admin user</span></span>

1. <span data-ttu-id="41350-185">Azure Active Directory에서 보안 관리자 권한을 가진 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41350-185">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="41350-186">사용자는 설치 검사 목록에서 만든 통합 사용자와 이름 및 전자 메일 주소를 모두 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41350-186">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="41350-187">로그인 및 연결이 완료 되 면 보안 관리자 역할을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41350-187">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="41350-188">이 사용자로 Microsoft 365 보안 센터에 로그인 하 고 설치 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="41350-188">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>
