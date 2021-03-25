---
title: 권장 Teams 정책 - 엔터프라이즈용 Microsoft 365 | Microsoft Docs
description: Teams 통신 및 파일 액세스를 보호하는 방법에 대한 Microsoft 권장 정책에 대해 설명
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206436"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="30883-103">Teams 채팅, 그룹 및 파일 보안에 대한 정책 권장 사항</span><span class="sxs-lookup"><span data-stu-id="30883-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="30883-104">이 문서에서는 권장 ID 및 장치 액세스 정책을 구현하여 Microsoft Teams 채팅, 그룹 및 파일 및 일정과 같은 콘텐츠를 보호하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="30883-105">이 지침은 일반적인 [ID](identity-access-policies.md)및 장치 액세스 정책 에 Teams 관련 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="30883-106">Teams는 다른 제품과 통합됩니다. [또한 SharePoint](sharepoint-file-access-policies.md) 사이트 및 파일 보안에 대한 정책 권장 사항 및 전자 메일 보안에 대한 정책 권장 사항도 [참조하세요.](secure-email-recommended-policies.md)</span><span class="sxs-lookup"><span data-stu-id="30883-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="30883-107">이러한 권장 사항은 요구의 세분성에 따라 적용할 수 있는 Teams에 대한 세 가지 보안 및 보호 계층(기준, 중요 및 높은 규제)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="30883-108">이러한 보안 계층 및 ID 및 장치 액세스 구성에서 이러한 권장 사항에서 참조하는 권장 정책에 대해 자세히 확인할 [수 있습니다.](microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="30883-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="30883-109">조직 외부 사용자를 비롯한 특정 인증 상황을 다루기 위해 Teams 배포와 관련한 추가 권장 사항이 이 문서에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-109">More recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="30883-110">완전한 보안 환경을 위해 이 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="30883-111">다른 종속 서비스 전에 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="30883-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="30883-112">Microsoft Teams를 시작하려면 종속 서비스를 사용하도록 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="30883-113">이러한 서비스는 모두 "작동"합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-113">These services will all "just work."</span></span> <span data-ttu-id="30883-114">그러나 다음과 같은 서비스 관련 요소를 관리할 수 있도록 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-114">However, you do need to be prepared to manage the following service-related elements:</span></span>

- <span data-ttu-id="30883-115">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="30883-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="30883-116">SharePoint 팀 사이트</span><span class="sxs-lookup"><span data-stu-id="30883-116">SharePoint team sites</span></span>
- <span data-ttu-id="30883-117">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="30883-117">OneDrive for Business</span></span>
- <span data-ttu-id="30883-118">Exchange 사서함</span><span class="sxs-lookup"><span data-stu-id="30883-118">Exchange mailboxes</span></span>
- <span data-ttu-id="30883-119">비디오 스트림 및 Planner 계획(이러한 서비스가 활성화된 경우)</span><span class="sxs-lookup"><span data-stu-id="30883-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="30883-120">Teams를 포함하기 위해 일반적인 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="30883-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="30883-121">Teams에서 채팅, 그룹 및 콘텐츠를 보호하기 위해 다음 다이어그램은 공통 ID 및 장치 액세스 정책에서 업데이트할 정책을 보여 주는 다이어그램입니다.</span><span class="sxs-lookup"><span data-stu-id="30883-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="30883-122">업데이트할 각 정책에 대해 Teams 및 종속 서비스가 클라우드 앱 할당에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="30883-123">[![Teams 및 해당 종속 서비스에 대한 액세스를 보호하기 위한 정책 업데이트 요약](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="30883-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

<span data-ttu-id="30883-124">이러한 서비스는 Teams용 클라우드 앱 할당에 포함할 종속 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="30883-124">These services are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="30883-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30883-125">Microsoft Teams</span></span>
- <span data-ttu-id="30883-126">SharePoint 및 비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="30883-126">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="30883-127">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="30883-127">Exchange Online</span></span>
- <span data-ttu-id="30883-128">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="30883-128">Skype for Business Online</span></span>
- <span data-ttu-id="30883-129">Microsoft Stream(모임 녹음/녹화)</span><span class="sxs-lookup"><span data-stu-id="30883-129">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="30883-130">Microsoft Planner(Planner 작업 및 데이터 계획)</span><span class="sxs-lookup"><span data-stu-id="30883-130">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="30883-131">이 표에는 재시도해야 하는 정책과 모든 Office 응용 프로그램에 대해 더 광범위한 정책이 설정된 공통 [ID](identity-access-policies.md)및 장치 액세스 정책의 각 정책에 대한 링크가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-131">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="30883-132">보호 수준</span><span class="sxs-lookup"><span data-stu-id="30883-132">Protection level</span></span>|<span data-ttu-id="30883-133">정책</span><span class="sxs-lookup"><span data-stu-id="30883-133">Policies</span></span>|<span data-ttu-id="30883-134">Teams 구현에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="30883-134">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="30883-135">**기준**</span><span class="sxs-lookup"><span data-stu-id="30883-135">**Baseline**</span></span>|[<span data-ttu-id="30883-136">로그인 위험이 중간 또는 높음인 경우 MFA *필요*</span><span class="sxs-lookup"><span data-stu-id="30883-136">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="30883-137">Teams 및 종속 서비스가 앱 목록에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-137">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="30883-138">Teams에는 게스트 액세스 및 외부 액세스 규칙도 고려해야 합니다. 이러한 규칙에 대한 자세한 내용은 이 문서 의 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-138">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span>|
||[<span data-ttu-id="30883-139">최신 인증을 지원하지 않는 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="30883-139">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="30883-140">클라우드 앱 할당에 Teams 및 종속 서비스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-140">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="30883-141">위험이 높은 사용자는 암호를 변경해야 함</span><span class="sxs-lookup"><span data-stu-id="30883-141">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="30883-142">계정에 대해 높은 위험 활동이 감지된 경우 Teams 사용자가 로그인할 때 암호를 강제로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-142">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="30883-143">Teams 및 종속 서비스가 앱 목록에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-143">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="30883-144">APP 데이터 보호 정책 적용</span><span class="sxs-lookup"><span data-stu-id="30883-144">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="30883-145">Teams 및 종속 서비스가 앱 목록에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-145">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="30883-146">각 플랫폼(iOS, Android, Windows)에 대한 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-146">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="30883-147">장치 준수 정책 정의</span><span class="sxs-lookup"><span data-stu-id="30883-147">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="30883-148">이 정책에 Teams 및 종속 서비스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-148">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="30883-149">호환 PC 필요</span><span class="sxs-lookup"><span data-stu-id="30883-149">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="30883-150">이 정책에 Teams 및 종속 서비스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-150">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="30883-151">**중요**</span><span class="sxs-lookup"><span data-stu-id="30883-151">**Sensitive**</span></span>|[<span data-ttu-id="30883-152">로그인 위험이 낮거나 보통 또는 *높을* 때 MFA *필요*</span><span class="sxs-lookup"><span data-stu-id="30883-152">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="30883-153">Teams에는 게스트 액세스 및 외부 액세스 규칙도 고려해야 합니다. 이러한 규칙에 대한 자세한 내용은 이 문서 의 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-153">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span> <span data-ttu-id="30883-154">이 정책에 Teams 및 종속 서비스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-154">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="30883-155">호환 PC 및 *모바일* 장치 필요</span><span class="sxs-lookup"><span data-stu-id="30883-155">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="30883-156">이 정책에 Teams 및 종속 서비스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-156">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="30883-157">**매우 엄격한 규제**</span><span class="sxs-lookup"><span data-stu-id="30883-157">**Highly regulated**</span></span>|[<span data-ttu-id="30883-158">*항상* MFA 필요</span><span class="sxs-lookup"><span data-stu-id="30883-158">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="30883-159">사용자 ID에 관계없이 조직에서 MFA가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30883-159">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="30883-160">이 정책에 Teams 및 종속 서비스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-160">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="30883-161">Teams 종속 서비스 아키텍처</span><span class="sxs-lookup"><span data-stu-id="30883-161">Teams dependent services architecture</span></span>

<span data-ttu-id="30883-162">참조를 위해 다음 다이어그램은 Teams가 사용하는 서비스를 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30883-162">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="30883-163">자세한 정보와 그림은 IT 설계자용 [Microsoft 365의 Microsoft Teams](../../solutions/productivity-illustrations.md)및 관련 생산성 서비스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30883-163">For more information and illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="30883-164">[![SharePoint, 비즈니스용 OneDrive 및 Exchange에 대한 Teams 종속성 표시 다이어그램](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="30883-164">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="30883-165">이 이미지의 더 큰 버전 참조</span><span class="sxs-lookup"><span data-stu-id="30883-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="30883-166">Teams의 게스트 및 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="30883-166">Guest and external access for Teams</span></span>

<span data-ttu-id="30883-167">Microsoft Teams는 다음과 같은 액세스 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-167">Microsoft Teams defines the following access types:</span></span>

- <span data-ttu-id="30883-168">**게스트 액세스는** 팀의 구성원으로 추가할 수 있으며 팀의 통신 및 리소스에 대한 모든 권한을 가지는 게스트 또는 외부 사용자에 대해 Azure AD B2B 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-168">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="30883-169">**외부 액세스는** Azure AD B2B 계정이 없는 외부 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30883-169">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="30883-170">외부 액세스에는 초대 및 통화, 채팅 및 모임 참가가 포함할 수 있지만 팀 구성원 자격 및 팀 리소스 액세스는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-170">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="30883-171">조건부 액세스 정책은 해당 Azure AD B2B 계정이 있기 때문에 Teams의 게스트 액세스에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30883-171">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="30883-172">Azure AD B2B 계정이 있는 게스트 및 외부 사용자에 대한 액세스를 허용하는 권장 정책은 게스트 및 외부 B2B 계정 액세스를 허용하는 [정책을 참조하세요.](identity-access-policies-guest-access.md)</span><span class="sxs-lookup"><span data-stu-id="30883-172">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="30883-173">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="30883-173">Guest access in Teams</span></span>

<span data-ttu-id="30883-174">관리자는 비즈니스 또는 조직 내부의 사용자에 대한 정책 외에도 게스트 액세스를 허용하여 비즈니스 또는 조직 외부의 사용자가 Teams 리소스에 액세스하고 그룹 대화, 채팅 및 모임과 같은 내부 사용자와 상호 작용할 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-174">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="30883-175">게스트 액세스 및 게스트 액세스 구현 방법에 대한 자세한 내용은 Teams 게스트 액세스를 [참조하세요.](/microsoftteams/guest-access)</span><span class="sxs-lookup"><span data-stu-id="30883-175">For more information about guest access and how to implement it, see  [Teams guest access](/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="30883-176">Teams의 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="30883-176">External access in Teams</span></span>

<span data-ttu-id="30883-177">외부 액세스는 게스트 액세스와 혼동되는 경우도 있으므로 이러한 두 가지 비 내부 액세스 메커니즘이 서로 다른 액세스 유형임이 명확히 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-177">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are different types of access.</span></span>

<span data-ttu-id="30883-178">외부 액세스는 전체 외부 도메인의 Teams 사용자가 Teams에서 사용자와 모임을 찾고, 통화하고, 채팅하고, 설정할 수 있는 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="30883-178">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="30883-179">Teams 관리자는 조직 수준에서 외부 액세스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-179">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="30883-180">자세한 내용은 [Microsoft Teams에서 외부 액세스 관리를 참조하세요.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="30883-180">For more information, see [Manage external access in Microsoft Teams](/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="30883-181">외부 액세스 사용자는 게스트 액세스를 통해 추가된 개인보다 액세스 및 기능이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-181">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="30883-182">예를 들어 외부 액세스 사용자는 Teams를 사용하여 내부 사용자와 채팅할 수 있지만 팀 채널, 파일 또는 기타 리소스에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-182">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="30883-183">외부 액세스는 Azure AD B2B 사용자 계정을 사용하지 않습니다. 따라서 조건부 액세스 정책을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-183">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="30883-184">Teams 정책</span><span class="sxs-lookup"><span data-stu-id="30883-184">Teams policies</span></span>

<span data-ttu-id="30883-185">위에 나열된 일반 정책 외부에는 다양한 Teams 기능을 관리하도록 구성할 수 있는 Teams 관련 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-185">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="30883-186">Teams 및 채널 정책</span><span class="sxs-lookup"><span data-stu-id="30883-186">Teams and channels policies</span></span>

<span data-ttu-id="30883-187">Teams와 채널은 Microsoft Teams에서 일반적으로 사용되는 두 가지 요소로, 사용자가 팀과 채널을 사용할 때 할 수 있는 작업을 제어할 수 있는 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-187">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="30883-188">전역 팀을 만들 수 있는 반면 조직에 사용자가 5,000명 이하인 경우 조직 요구에 따라 특정 목적을 위해 소규모 팀과 채널을 구성하는 것이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-188">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="30883-189">기본 정책을 변경하거나 사용자 지정 정책을 만드는 것이 좋습니다. 정책 관리에 대한 자세한 내용은 Microsoft Teams에서 팀 정책 관리 링크를 통해 자세히 볼 [수 있습니다.](/microsoftteams/teams-policies)</span><span class="sxs-lookup"><span data-stu-id="30883-189">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="30883-190">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="30883-190">Messaging policies</span></span>

<span data-ttu-id="30883-191">메시징 또는 채팅은 기본 글로벌 정책 또는 사용자 지정 정책을 통해 관리할 수도 있으며, 이를 통해 사용자가 조직에 적합한 방식으로 서로 통신하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-191">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="30883-192">이 정보는 Teams에서 메시징 정책 [관리에서 검토할 수 있습니다.](/microsoftteams/messaging-policies-in-teams)</span><span class="sxs-lookup"><span data-stu-id="30883-192">This information can be reviewed at [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="30883-193">모임 정책</span><span class="sxs-lookup"><span data-stu-id="30883-193">Meeting policies</span></span>

<span data-ttu-id="30883-194">Teams 모임에 대한 정책을 계획하고 구현하지 않으면 Teams에 대한 논의가 완료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-194">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="30883-195">모임은 Teams의 필수 구성 요소로, 사용자가 한에 공식적으로 만나서 여러 사용자에게 발표하고 모임과 관련된 콘텐츠를 공유할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-195">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, and to share content relevant to the meeting.</span></span> <span data-ttu-id="30883-196">모임과 관련한 조직에 적합한 정책을 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-196">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="30883-197">자세한 내용은 [Teams에서 모임 정책 관리를 참조하세요.](/microsoftteams/meeting-policies-in-teams)</span><span class="sxs-lookup"><span data-stu-id="30883-197">For more information, review [Manage meeting policies in Teams](/microsoftteams/meeting-policies-in-teams).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="30883-198">앱 사용 권한 정책</span><span class="sxs-lookup"><span data-stu-id="30883-198">App permission policies</span></span>

<span data-ttu-id="30883-199">Teams를 사용하면 채널 또는 개인 채팅과 같은 다양한 장소에서 앱을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30883-199">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="30883-200">앱을 추가 및 사용할 수 있는 내용 및 안전한 콘텐츠가 풍부한 환경을 유지 관리하는 데 필요한 위치와 관련한 정책을 유지하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="30883-200">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="30883-201">앱 사용 권한 정책에 대한 자세한 내용은 Microsoft Teams에서 앱 권한 [정책 관리를 확인할 수 있습니다.](/microsoftteams/teams-app-permission-policies)</span><span class="sxs-lookup"><span data-stu-id="30883-201">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="30883-202">다음 단계</span><span class="sxs-lookup"><span data-stu-id="30883-202">Next steps</span></span>

![4단계: Microsoft 365 클라우드 앱에 대한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="30883-204">조건부 액세스 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="30883-204">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="30883-205">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="30883-205">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="30883-206">SharePoint</span><span class="sxs-lookup"><span data-stu-id="30883-206">SharePoint</span></span>](sharepoint-file-access-policies.md)