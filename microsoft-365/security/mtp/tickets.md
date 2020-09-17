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
ms.openlocfilehash: b9e900baf02e9fc866fe6fe520ad1e40ccd565de
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950703"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="7cb67-104">ServiceNow 티켓을 Microsoft 365 보안 센터 및 준수 센터에 통합</span><span class="sxs-lookup"><span data-stu-id="7cb67-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7cb67-105">ServiceNow는 회사에서 엔터프라이즈 운영을 위한 디지털 워크플로를 관리 하는 데 사용할 수 있는 인기 있는 클라우드 컴퓨팅 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="7cb67-106">현재 플랫폼에는 IT 워크플로, 직원 워크플로 및 고객 워크플로가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="7cb67-107">ServiceNow에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="7cb67-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="7cb67-108">Microsoft는 IT 관리자가 두 플랫폼에서 모두 티켓과 작업을 보다 쉽게 관리할 수 있도록 ServiceNow과 제휴 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="7cb67-109">[Microsoft 365 보안 센터](overview-security-center.md) 및 [microsoft 365 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 는 ServiceNow에서 티켓을 기본적으로 만들고 추적할 수 있는 기능을 통해 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="7cb67-110">**보안 센터에서 ServiceNow 티켓 관리**</span><span class="sxs-lookup"><span data-stu-id="7cb67-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="7cb67-111">**준수 센터에서 ServiceNow 티켓 관리** (출시 예정)</span><span class="sxs-lookup"><span data-stu-id="7cb67-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7cb67-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7cb67-112">Prerequisites</span></span>

<span data-ttu-id="7cb67-113">다음을 포함 하는 Microsoft 365 보안 센터 또는 준수 센터 및 ServiceNow 인스턴스에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="7cb67-114">Kingston 이상 버전</span><span class="sxs-lookup"><span data-stu-id="7cb67-114">Kingston or higher version</span></span>
* <span data-ttu-id="7cb67-115">관리자 용 자격 증명 포함</span><span class="sxs-lookup"><span data-stu-id="7cb67-115">Have admin HI credentials</span></span>
* <span data-ttu-id="7cb67-116">대상 공급 업체 인스턴스에 대해 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="7cb67-117">ServiceNow에서는 사용자가 ServiceNow 인스턴스에 기본 설정을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="7cb67-118">사용자 지정 내용이 있으면 설치 검사 목록이 완료 되 고 Microsoft 365 보안 센터와 통합 될 때 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="7cb67-119">데이터 교환</span><span class="sxs-lookup"><span data-stu-id="7cb67-119">Data exchange</span></span>

<span data-ttu-id="7cb67-120">Microsoft 365 보안 센터 또는 준수 센터를 ServiceNow에 연결 하면 Microsoft에서 다음과 같은 추가 데이터를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="7cb67-121">ServiceNow 인스턴스 이름</span><span class="sxs-lookup"><span data-stu-id="7cb67-121">ServiceNow instance name</span></span>
* <span data-ttu-id="7cb67-122">ServiceNow 클라이언트 ID</span><span class="sxs-lookup"><span data-stu-id="7cb67-122">ServiceNow client ID</span></span>
* <span data-ttu-id="7cb67-123">ServiceNow 클라이언트 암호</span><span class="sxs-lookup"><span data-stu-id="7cb67-123">ServiceNow client secret</span></span>
* <span data-ttu-id="7cb67-124">ServiceNow 액세스 & 새로 고침 토큰</span><span class="sxs-lookup"><span data-stu-id="7cb67-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="7cb67-125">Microsoft 365 보안 센터 또는 준수 센터에서 ServiceNow 티켓을 만드는 경우 다음 데이터가 ServiceNow로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="7cb67-126">티켓 만들기를 시작 하는 사용자 ID</span><span class="sxs-lookup"><span data-stu-id="7cb67-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="7cb67-127">작업 이름</span><span class="sxs-lookup"><span data-stu-id="7cb67-127">Task name</span></span>
* <span data-ttu-id="7cb67-128">작업 설명</span><span class="sxs-lookup"><span data-stu-id="7cb67-128">Task description</span></span>
* <span data-ttu-id="7cb67-129">우선 순위</span><span class="sxs-lookup"><span data-stu-id="7cb67-129">Priority</span></span>
* <span data-ttu-id="7cb67-130">기한</span><span class="sxs-lookup"><span data-stu-id="7cb67-130">Due date</span></span>
* <span data-ttu-id="7cb67-131">권장 사항 원본 (사용자 권장 사항 또는 Microsoft 권장 사항)</span><span class="sxs-lookup"><span data-stu-id="7cb67-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="7cb67-132">추천 범주 (장치, 데이터, 앱, Id, 인프라)</span><span class="sxs-lookup"><span data-stu-id="7cb67-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="7cb67-133">ServiceNow에 연결</span><span class="sxs-lookup"><span data-stu-id="7cb67-133">Connect to ServiceNow</span></span>

<span data-ttu-id="7cb67-134">[Microsoft 365 보안 센터에서 servicenow 티켓 만들기 및 추적](tickets-security-center.md) 으로 이동 하 여 servicenow에 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="7cb67-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="7cb67-135">Microsoft 365 준수 센터에서의 연결이 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7cb67-136">문제 해결</span><span class="sxs-lookup"><span data-stu-id="7cb67-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="7cb67-137">설치 검사 목록의 첫 번째 단계에서 오류가 표시 됩니다 (OAuth 만들기).</span><span class="sxs-lookup"><span data-stu-id="7cb67-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="7cb67-138">**오류 메시지**: 테이블의 범위 간 액세스 정책으로 인해 ' x_mioms_m365ticket ' 범위에서 ' oauth_entity '에 대 한 읽기 작업이 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="7cb67-139">이 앱에서는 ServiceNow 인스턴스의 관리자가 OAuth 엔터티를 만들고 읽을 수 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="7cb67-140">이 오류는 ServiceNow 인스턴스에서 OAuth 엔터티를 만들거나 읽을 수 있는 사람을 제한 하는 사용자 지정으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-140">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="7cb67-141">**ServiceNow에서는 사용자가 기본 기능을 유지 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="7cb67-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="7cb67-142">"응용 프로그램 레지스트리" 테이블 구성을 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="7cb67-143">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="7cb67-143">Label = Application Registeries</span></span>
* <span data-ttu-id="7cb67-144">이름 = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="7cb67-144">Name = oauth_entity</span></span>
* <span data-ttu-id="7cb67-145">액세스 가능 = 모든 응용 프로그램 범위</span><span class="sxs-lookup"><span data-stu-id="7cb67-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="7cb67-146">읽을 수 있음 = 확인란 선택</span><span class="sxs-lookup"><span data-stu-id="7cb67-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7cb67-147">Microsoft 365 보안 & 준수 커넥터에 대해 만들어진 OAuth 엔터티를 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="7cb67-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="7cb67-148">ServiceNow의 응용 프로그램 레지스트리 (**Menu > System OAuth > Application Registry**)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow.</span></span> <span data-ttu-id="7cb67-149">자신에 게 할당 한 이름을 사용 하 여 만든 OAuth 엔터티를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-149">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="7cb67-150">통합 사용자로 로그인</span><span class="sxs-lookup"><span data-stu-id="7cb67-150">Signing in as the integration user</span></span>

<span data-ttu-id="7cb67-151">Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하기 전에 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-151">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="7cb67-152">개인 자격 증명은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7cb67-152">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="7cb67-153">ServiceNow의 인증 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-153">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="7cb67-154">개인 자격 증명을 사용 하 여 로그인 한 경우 오른쪽 위 모서리에서 링크 **하지 않음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-154">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="7cb67-155">설치 검사 목록에서 이전에 만든 통합 사용자로 ServiceNow에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-155">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="7cb67-156">ServiceNow 페이지에서 보안 + 준수 커넥터가 ServiceNow 계정에 연결할 수 있는지 여부를 묻는 **허용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-156">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="7cb67-157">설정 단계를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-157">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7cb67-158">Microsoft 365 보안 & 준수 커넥터에 대 한 설치 검사 목록을 사용 하 여 만든 통합 사용자의 유효성을 검사 하는 방법</span><span class="sxs-lookup"><span data-stu-id="7cb67-158">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="7cb67-159">ServiceNow에서 사용자 **> 관리 > 사용자**로 이동 하 고 자신에 게 만든 통합 사용자를 지정한 이름으로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-159">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="7cb67-160">회사에서 Microsoft 365 보안 센터를 통해 ServiceNow에 연결 하지 못하도록 하는 single sign-on을 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-160">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="7cb67-161">회사에서 single sign-on을 사용 하도록 설정 하 고 오류가 수신 되거나 로그인이 실패 하면 두 솔루션 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-161">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="7cb67-162">통합 사용자로 ServiceNow에 로그인</span><span class="sxs-lookup"><span data-stu-id="7cb67-162">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="7cb67-163">ServiceNow에서 인증 페이지로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-163">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="7cb67-164">오른쪽 위 모서리에서 링크 **하지 않음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-164">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="7cb67-165">설치 검사 목록에서 이전에 만든 통합 사용자로 ServiceNow에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-165">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="7cb67-166">ServiceNow 페이지에서 보안 + 준수 커넥터가 ServiceNow 계정에 연결할 수 있는지 여부를 묻는 **허용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-166">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="7cb67-167">설정 단계를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-167">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="7cb67-168">보안 관리자 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="7cb67-168">Create a security admin user</span></span>

1. <span data-ttu-id="7cb67-169">Azure Active Directory에서 보안 관리자 권한을 가진 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-169">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="7cb67-170">사용자는 설치 검사 목록에서 만든 통합 사용자와 이름 및 전자 메일 주소를 모두 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-170">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="7cb67-171">로그인 및 연결이 완료 되 면 보안 관리자 역할을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-171">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="7cb67-172">이 사용자로 Microsoft 365 보안 센터에 로그인 하 고 설정 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-172">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="7cb67-173">IP 필터링</span><span class="sxs-lookup"><span data-stu-id="7cb67-173">IP filtering</span></span>

<span data-ttu-id="7cb67-174">IP 필터링을 사용 하도록 설정한 경우 IP 주소를 명시적으로 허용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-174">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="7cb67-175">ServiceNow에서 IP 범위를 허용 하는 방법에 대 한 자세한 내용은 [Ip 주소 액세스 제어](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb67-175">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="7cb67-176">허용할 IP 주소 목록은 [AZURE IP 범위 및 서비스 태그-공용 클라우드](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cb67-176">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="7cb67-177">설치가 완료 되었지만 티켓이 표시 되지 않으며 공유할 수 없음</span><span class="sxs-lookup"><span data-stu-id="7cb67-177">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="7cb67-178">설치 및 설치 단계가 완료 되었지만 홈 페이지에 ServiceNow 카드가 표시 되지 않고 Microsoft 보안 점수에서 ServiceNow을 공유할 수 없는 경우에는의 프로 비전 페이지 상태를 확인 https://security.microsoft.com/ticketProvisioning 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-178">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="7cb67-179">**권한 부여** 를 선택 하 고 홈 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-179">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="7cb67-180">카드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb67-180">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="7cb67-181">리소스</span><span class="sxs-lookup"><span data-stu-id="7cb67-181">Resources</span></span>

- [<span data-ttu-id="7cb67-182">보안 센터에서 ServiceNow 티켓 관리</span><span class="sxs-lookup"><span data-stu-id="7cb67-182">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)