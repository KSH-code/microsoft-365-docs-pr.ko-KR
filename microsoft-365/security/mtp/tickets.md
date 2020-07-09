---
title: ServiceNow 티켓을 Microsoft 365 보안 센터 및 준수 센터에 통합
description: Microsoft 365 보안 센터 및 준수 센터에서 ServiceNow의 티켓을 만들고 추적 하는 방법에 대해 알아봅니다.
keywords: 보안, Microsoft 365, M365, 규정 준수, 준수 센터, 보안 센터, ServiceNow, 티켓, 작업, 눈, 연결
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086670"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="dfdb7-104">ServiceNow 티켓을 Microsoft 365 보안 센터 및 준수 센터에 통합</span><span class="sxs-lookup"><span data-stu-id="dfdb7-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="dfdb7-105">ServiceNow는 회사에서 엔터프라이즈 운영을 위한 디지털 워크플로를 관리 하는 데 사용할 수 있는 인기 있는 클라우드 컴퓨팅 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="dfdb7-106">현재 플랫폼에는 IT 워크플로, 직원 워크플로 및 고객 워크플로가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="dfdb7-107">ServiceNow에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="dfdb7-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="dfdb7-108">Microsoft는 IT 관리자가 두 플랫폼에서 모두 티켓과 작업을 보다 쉽게 관리할 수 있도록 ServiceNow과 제휴 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="dfdb7-109">[Microsoft 365 보안 센터](overview-security-center.md) 및 [microsoft 365 준수 센터](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) 는 ServiceNow에서 티켓을 기본적으로 만들고 추적할 수 있는 기능을 통해 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="dfdb7-110">**보안 센터에서 ServiceNow 티켓 관리**</span><span class="sxs-lookup"><span data-stu-id="dfdb7-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="dfdb7-111">**준수 센터에서 ServiceNow 티켓 관리** (출시 예정)</span><span class="sxs-lookup"><span data-stu-id="dfdb7-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dfdb7-112">전제 조건</span><span class="sxs-lookup"><span data-stu-id="dfdb7-112">Prerequisites</span></span>

<span data-ttu-id="dfdb7-113">다음을 포함 하는 Microsoft 365 보안 센터 또는 준수 센터 및 ServiceNow 인스턴스에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="dfdb7-114">Kingston 이상 버전</span><span class="sxs-lookup"><span data-stu-id="dfdb7-114">Kingston or higher version</span></span>
* <span data-ttu-id="dfdb7-115">관리자 용 자격 증명 포함</span><span class="sxs-lookup"><span data-stu-id="dfdb7-115">Have admin HI credentials</span></span>
* <span data-ttu-id="dfdb7-116">대상 공급 업체 인스턴스에 대해 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="dfdb7-117">ServiceNow에서는 사용자가 ServiceNow 인스턴스에 기본 설정을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="dfdb7-118">사용자 지정 내용이 있으면 설치 검사 목록이 완료 되 고 Microsoft 365 보안 센터와 통합 될 때 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="dfdb7-119">데이터 교환</span><span class="sxs-lookup"><span data-stu-id="dfdb7-119">Data exchange</span></span>

<span data-ttu-id="dfdb7-120">Microsoft 365 보안 센터 또는 준수 센터를 ServiceNow에 연결 하면 Microsoft에서 다음과 같은 추가 데이터를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="dfdb7-121">ServiceNow 인스턴스 이름</span><span class="sxs-lookup"><span data-stu-id="dfdb7-121">ServiceNow instance name</span></span>
* <span data-ttu-id="dfdb7-122">ServiceNow 클라이언트 ID</span><span class="sxs-lookup"><span data-stu-id="dfdb7-122">ServiceNow client ID</span></span>
* <span data-ttu-id="dfdb7-123">ServiceNow 클라이언트 암호</span><span class="sxs-lookup"><span data-stu-id="dfdb7-123">ServiceNow client secret</span></span>
* <span data-ttu-id="dfdb7-124">ServiceNow 액세스 & 새로 고침 토큰</span><span class="sxs-lookup"><span data-stu-id="dfdb7-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="dfdb7-125">Microsoft 365 보안 센터 또는 준수 센터에서 ServiceNow 티켓을 만드는 경우 다음 데이터가 ServiceNow로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="dfdb7-126">티켓 만들기를 시작 하는 사용자 ID</span><span class="sxs-lookup"><span data-stu-id="dfdb7-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="dfdb7-127">작업 이름</span><span class="sxs-lookup"><span data-stu-id="dfdb7-127">Task name</span></span>
* <span data-ttu-id="dfdb7-128">작업 설명</span><span class="sxs-lookup"><span data-stu-id="dfdb7-128">Task description</span></span>
* <span data-ttu-id="dfdb7-129">우선 순위</span><span class="sxs-lookup"><span data-stu-id="dfdb7-129">Priority</span></span>
* <span data-ttu-id="dfdb7-130">기한</span><span class="sxs-lookup"><span data-stu-id="dfdb7-130">Due date</span></span>
* <span data-ttu-id="dfdb7-131">권장 사항 원본 (사용자 권장 사항 또는 Microsoft 권장 사항)</span><span class="sxs-lookup"><span data-stu-id="dfdb7-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="dfdb7-132">추천 범주 (장치, 데이터, 앱, Id, 인프라)</span><span class="sxs-lookup"><span data-stu-id="dfdb7-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="dfdb7-133">ServiceNow에 연결</span><span class="sxs-lookup"><span data-stu-id="dfdb7-133">Connect to ServiceNow</span></span>

<span data-ttu-id="dfdb7-134">[Microsoft 365 보안 센터에서 servicenow 티켓 만들기 및 추적](tickets-security-center.md) 으로 이동 하 여 servicenow에 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="dfdb7-135">Microsoft 365 준수 센터에서의 연결이 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="dfdb7-136">문제 해결</span><span class="sxs-lookup"><span data-stu-id="dfdb7-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="dfdb7-137">설치 검사 목록의 첫 번째 단계에서 오류가 표시 됩니다 (OAuth 만들기).</span><span class="sxs-lookup"><span data-stu-id="dfdb7-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="dfdb7-138">**오류 메시지**: 테이블의 범위 간 액세스 정책으로 인해 ' x_mioms_m365ticket ' 범위에서 ' oauth_entity '에 대 한 읽기 작업이 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="dfdb7-139">이 앱에서는 ServiceNow 인스턴스의 관리자가 OAuth 엔터티를 만들고 읽을 수 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="dfdb7-140">이 오류는 ServiceNow 인스턴스의 사용자 지정으로 인해 OAuth 엔터티를 만들거나 읽을 수 있는 사용자를 제한 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="dfdb7-141">**ServiceNow에서는 사용자가 기본 기능을 유지 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="dfdb7-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="dfdb7-142">"응용 프로그램 레지스트리" 테이블 구성을 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="dfdb7-143">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="dfdb7-143">Label = Application Registeries</span></span>
* <span data-ttu-id="dfdb7-144">이름 = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="dfdb7-144">Name = oauth_entity</span></span>
* <span data-ttu-id="dfdb7-145">액세스 가능 = 모든 응용 프로그램 범위</span><span class="sxs-lookup"><span data-stu-id="dfdb7-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="dfdb7-146">읽을 수 있음 = 확인란 선택</span><span class="sxs-lookup"><span data-stu-id="dfdb7-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="dfdb7-147">Microsoft 365 보안 & 준수 커넥터에 대해 만들어진 OAuth 엔터티를 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dfdb7-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="dfdb7-148">ServiceNow에서 응용 프로그램 레지스트리 (**Menu > System OAuth > Application Registry**)로 이동 하 여 사용자가 만든 OAuth 엔터티를 할당 한 이름을 사용 하 여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="dfdb7-149">통합 사용자로 로그인</span><span class="sxs-lookup"><span data-stu-id="dfdb7-149">Logging in as the integration user</span></span>

<span data-ttu-id="dfdb7-150">Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하기 전에 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="dfdb7-151">개인 자격 증명은 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="dfdb7-152">ServiceNow의 인증 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="dfdb7-153">개인 자격 증명으로 로그인 한 경우 오른쪽 위 모서리에서 링크 **하지 않음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="dfdb7-154">설치 검사 목록에서 이전에 만든 통합 사용자로 ServiceNow에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="dfdb7-155">ServiceNow 페이지에서 보안 + 준수 커넥터가 ServiceNow 계정에 연결할 수 있는지 여부를 묻는 **허용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="dfdb7-156">설정 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="dfdb7-157">Microsoft 365 보안 & 준수 커넥터에 대 한 설치 검사 목록을 사용 하 여 만든 통합 사용자의 유효성을 검사 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dfdb7-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="dfdb7-158">ServiceNow에서 사용자 **> 관리 > 사용자**로 이동 하 고 자신에 게 만든 통합 사용자를 지정한 이름으로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="dfdb7-159">회사에서 Microsoft 365 보안 센터를 통해 ServiceNow에 연결 하지 못하도록 하는 single sign-on을 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="dfdb7-160">회사에서 single sign-on을 사용 하도록 설정 하 고 오류가 수신 되거나 로그인이 실패 하면 두 솔루션 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="dfdb7-161">통합 사용자로 ServiceNow 로그인</span><span class="sxs-lookup"><span data-stu-id="dfdb7-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="dfdb7-162">ServiceNow에서 인증 페이지로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="dfdb7-163">오른쪽 위 모서리에서 링크 **하지 않음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="dfdb7-164">설치 검사 목록에서 이전에 만든 통합 사용자로 ServiceNow에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="dfdb7-165">ServiceNow 페이지에서 보안 + 준수 커넥터가 ServiceNow 계정에 연결할 수 있는지 여부를 묻는 **허용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="dfdb7-166">설정 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="dfdb7-167">보안 관리자 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="dfdb7-167">Create a security admin user</span></span>

1. <span data-ttu-id="dfdb7-168">Azure Active Directory에서 보안 관리자 권한을 가진 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="dfdb7-169">사용자는 설치 검사 목록에서 만든 통합 사용자와 이름 및 전자 메일 주소를 모두 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="dfdb7-170">로그인 및 연결이 완료 되 면 보안 관리자 역할을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="dfdb7-171">이 사용자로 Microsoft 365 보안 센터에 로그인 하 고 설치 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="dfdb7-172">IP 필터링</span><span class="sxs-lookup"><span data-stu-id="dfdb7-172">IP filtering</span></span>

<span data-ttu-id="dfdb7-173">IP 필터링을 사용 하도록 설정한 경우 IP 주소를 명시적으로 허용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="dfdb7-174">ServiceNow에서 IP 범위를 허용 하는 방법에 대 한 자세한 내용은 [Ip 주소 액세스 제어](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="dfdb7-175">허용할 IP 주소 목록은 [AZURE IP 범위 및 서비스 태그-공용 클라우드](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="dfdb7-176">설치가 완료 되었지만 티켓이 표시 되지 않으며 공유할 수 없음</span><span class="sxs-lookup"><span data-stu-id="dfdb7-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="dfdb7-177">설치 및 설치 단계가 완료 되었지만 홈 페이지에 ServiceNow 카드가 표시 되지 않고 Microsoft 보안 점수에서 ServiceNow을 공유할 수 없는 경우에는의 프로 비전 페이지 상태를 확인 https://security.microsoft.com/ticketProvisioning 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="dfdb7-178">**권한 부여** 를 선택 하 고 홈 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="dfdb7-179">카드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfdb7-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="dfdb7-180">리소스</span><span class="sxs-lookup"><span data-stu-id="dfdb7-180">Resources</span></span>

- [<span data-ttu-id="dfdb7-181">보안 센터에서 ServiceNow 티켓 관리</span><span class="sxs-lookup"><span data-stu-id="dfdb7-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)