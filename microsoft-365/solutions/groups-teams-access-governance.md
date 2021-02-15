---
title: Microsoft 365 그룹, Teams 및 SharePoint의 액세스 제어
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 그룹, Teams 및 SharePoint의 액세스 제어에 대해 자세히 알아보습니다.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613469"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a><span data-ttu-id="125c5-103">Microsoft 365 그룹, Teams 및 SharePoint의 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="125c5-103">Governing access in Microsoft 365 groups, Teams, and SharePoint</span></span>

<span data-ttu-id="125c5-104">사용자가 그룹, 팀 및 SharePoint의 리소스에 액세스하는 방법을 제어할 수 있는 많은 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-104">There are many controls that enable you to govern how people access resources in groups, teams, and SharePoint.</span></span> <span data-ttu-id="125c5-105">이러한 옵션을 검토하고 비즈니스 요구에 매핑되는 방식, 데이터의 민감도 및 사용자가 공동으로 작업해야 하는 사용자의 범위를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-105">Review these options and consider how they map to your business needs, the sensitivity of your data, and the scope of people that your users need to collaborate with.</span></span>

<span data-ttu-id="125c5-106">다음 표에서는 Microsoft 365에서 사용할 수 있는 액세스 컨트롤에 대한 빠른 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-106">The following table provides a quick reference for the access controls available in Microsoft 365.</span></span> <span data-ttu-id="125c5-107">자세한 내용은 다음 섹션에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-107">Further information is provided in the following sections.</span></span>

|<span data-ttu-id="125c5-108">범주</span><span class="sxs-lookup"><span data-stu-id="125c5-108">Category</span></span>|<span data-ttu-id="125c5-109">설명</span><span class="sxs-lookup"><span data-stu-id="125c5-109">Description</span></span>|<span data-ttu-id="125c5-110">참조</span><span class="sxs-lookup"><span data-stu-id="125c5-110">Reference</span></span>|
|:-------|:----------|:--------|
|<span data-ttu-id="125c5-111">구성원</span><span class="sxs-lookup"><span data-stu-id="125c5-111">Membership</span></span>|||
||<span data-ttu-id="125c5-112">비공개 팀 검색</span><span class="sxs-lookup"><span data-stu-id="125c5-112">Discovery of private teams</span></span>|[<span data-ttu-id="125c5-113">Microsoft Teams에서 비공개 팀 검색 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-113">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||<span data-ttu-id="125c5-114">규칙을 기반으로 하는 동적 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="125c5-114">Dynamic group membership based on rules</span></span>|[<span data-ttu-id="125c5-115">Azure Active Directory에서 동적 그룹 만들기 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="125c5-115">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||<span data-ttu-id="125c5-116">파일, 폴더 및 사이트를 공유할 수 있는 사용자 제어</span><span class="sxs-lookup"><span data-stu-id="125c5-116">Control who can share files, folders, and sites.</span></span>|[<span data-ttu-id="125c5-117">액세스 요청 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-117">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|<span data-ttu-id="125c5-118">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="125c5-118">Conditional access</span></span>|||
||<span data-ttu-id="125c5-119">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="125c5-119">Multi-Factor Authentication</span></span>|[<span data-ttu-id="125c5-120">Azure AD 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="125c5-120">Azure AD Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||<span data-ttu-id="125c5-121">그룹, 팀 또는 사이트 민감도에 따라 장치 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-121">Control device access based on group, team, or site sensitivity.</span></span>|[<span data-ttu-id="125c5-122">민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기</span><span class="sxs-lookup"><span data-stu-id="125c5-122">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="125c5-123">관리되지 않는 장치에 대한 사이트 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-123">Limit site access for unmanaged devices.</span></span>|[<span data-ttu-id="125c5-124">관리되지 않는 장치에서 SharePoint 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="125c5-124">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||<span data-ttu-id="125c5-125">위치에 따라 사이트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="125c5-125">Control site access based on location</span></span>|[<span data-ttu-id="125c5-126">네트워크 위치에 따라 SharePoint 및 OneDrive 데이터에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="125c5-126">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|<span data-ttu-id="125c5-127">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="125c5-127">Guest access</span></span>|||
||<span data-ttu-id="125c5-128">지정된 도메인에서 SharePoint 공유를 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-128">Allow or block SharePoint sharing from specified domains.</span></span>|[<span data-ttu-id="125c5-129">도메인으로 SharePoint 및 OneDrive 콘텐츠 공유 제한</span><span class="sxs-lookup"><span data-stu-id="125c5-129">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||<span data-ttu-id="125c5-130">팀 또는 그룹 구성원을 지정된 도메인에서 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-130">Allow or block team or group membership from specified domains.</span></span>|[<span data-ttu-id="125c5-131">특정 조직의 B2B 사용자에 대한 초대 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="125c5-131">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||<span data-ttu-id="125c5-132">익명 공유를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-132">Prevent anonymous sharing.</span></span>|[<span data-ttu-id="125c5-133">모든 사용자 링크 해제</span><span class="sxs-lookup"><span data-stu-id="125c5-133">Turn off Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||<span data-ttu-id="125c5-134">익명 액세스 링크에 대한 사용 권한을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-134">Control the permissions for anonymous access links.</span></span>|[<span data-ttu-id="125c5-135">모든 사용자 링크에 대한 링크 권한 설정</span><span class="sxs-lookup"><span data-stu-id="125c5-135">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||<span data-ttu-id="125c5-136">익명 공유 링크의 만료를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-136">Control the expiration of anonymous sharing links.</span></span>|[<span data-ttu-id="125c5-137">모든 사용자 링크의 만료 날짜를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-137">Set an expiration date for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||<span data-ttu-id="125c5-138">기본적으로 사용자에게 표시되는 공유 링크 유형을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-138">Control the type of sharing link shown to users by default.</span></span>|[<span data-ttu-id="125c5-139">사이트의 기본 연결 종류 변경</span><span class="sxs-lookup"><span data-stu-id="125c5-139">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||<span data-ttu-id="125c5-140">외부 공유를 특정 사용자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-140">Limit external sharing to specific people.</span></span>|[<span data-ttu-id="125c5-141">외부 공유를 지정된 보안 그룹으로 제한</span><span class="sxs-lookup"><span data-stu-id="125c5-141">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||<span data-ttu-id="125c5-142">정보 민감도에 따라 그룹, 팀 또는 사이트에 대한 게스트 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-142">Control guest access to a group, team, or site based on information sensitivity.</span></span>|[<span data-ttu-id="125c5-143">민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기</span><span class="sxs-lookup"><span data-stu-id="125c5-143">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="125c5-144">공유 옵션을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-144">Turn off sharing options.</span></span>|[<span data-ttu-id="125c5-145">Microsoft 365에서의 공유 제한</span><span class="sxs-lookup"><span data-stu-id="125c5-145">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|<span data-ttu-id="125c5-146">사용자 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-146">User management</span></span>|||
||<span data-ttu-id="125c5-147">정기적으로 팀 및 그룹 구성원을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-147">Review team and group membership on a regular basis.</span></span>|[<span data-ttu-id="125c5-148">Azure AD 액세스 검토란?</span><span class="sxs-lookup"><span data-stu-id="125c5-148">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||<span data-ttu-id="125c5-149">그룹 및 팀에 대한 액세스 관리를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-149">Automate access management to groups and teams.</span></span>|[<span data-ttu-id="125c5-150">Azure AD 권리 관리란?</span><span class="sxs-lookup"><span data-stu-id="125c5-150">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||<span data-ttu-id="125c5-151">사용자가 Teams에서 비공개 채널을 만들 수 있도록 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-151">Allow or block people from creating private channels in Teams.</span></span>|[<span data-ttu-id="125c5-152">Microsoft Teams에서 비공개 채널의 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-152">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a><span data-ttu-id="125c5-153">구성원</span><span class="sxs-lookup"><span data-stu-id="125c5-153">Membership</span></span>

<span data-ttu-id="125c5-154">팀 및 그룹의 구성원은 소유자에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-154">Membership of teams and groups is controlled by owners.</span></span> <span data-ttu-id="125c5-155">구성원은 다른 구성원을 초대할 수 있지만 초대는 승인을 위해 소유자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-155">Members can invite others, but the invitations are sent to owners for approval.</span></span> <span data-ttu-id="125c5-156">공개 팀과 그룹은 조직의 모든 사람이 검색할 수 있는 반면 비공개 팀과 그룹을 검색할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-156">While public teams and groups are discoverable by anyone in the organization, you can control whether private teams and groups are discoverable:</span></span>

- [<span data-ttu-id="125c5-157">Microsoft Teams에서 비공개 팀 검색 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-157">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

<span data-ttu-id="125c5-158">부서와 같은 일부 기준에 따라 그룹 또는 팀의 구성원 자격을 동적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-158">You can manage membership of a group or team dynamically based on some criteria, such as department.</span></span> <span data-ttu-id="125c5-159">이 경우 구성원과 소유자는 팀에 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-159">In this case, members and owners cannot invite people to the team.</span></span>

- [<span data-ttu-id="125c5-160">Azure Active Directory에서 동적 그룹 만들기 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="125c5-160">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

<span data-ttu-id="125c5-161">SharePoint 사이트는 그룹 또는 팀 구성원 자격과는 별도로 소유자, 구성원 및 방문자를 추가할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-161">SharePoint sites provide the ability to add owners, members, and visitors apart from group or team membership.</span></span> <span data-ttu-id="125c5-162">요구 사항에 따라 사이트에 초대할 수 있는 사용자만 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-162">Depending on your requirements, you may want to restrict who can invite people to the site.</span></span> <span data-ttu-id="125c5-163">또한 지정한 사이트의 정보의 민감도에 따라 파일 및 폴더를 공유할 수 있는 사용자도 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-163">Also, depending on the sensitivity of the information in a given site, you may want to restrict who can share files and folder.</span></span> <span data-ttu-id="125c5-164">이러한 제한은 팀, 그룹 또는 사이트 소유자가 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-164">These restrictions are configured by the team, group, or site owner:</span></span>

- [<span data-ttu-id="125c5-165">액세스 요청 설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-165">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a><span data-ttu-id="125c5-166">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="125c5-166">Conditional access</span></span>

<span data-ttu-id="125c5-167">Microsoft 365를 사용하면 조직 내부 및 외부 사용자 모두에 대해 다단계 인증을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-167">With Microsoft 365, you can require multi-factor authentication for both people inside and outside your organization.</span></span> <span data-ttu-id="125c5-168">2단계 인증을 요청하는 상황에는 여러 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-168">There are many options for the circumstances when people are prompted for a second factor of authentication.</span></span> <span data-ttu-id="125c5-169">조직에 대해 다단계 인증을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-169">We highly recommend that you deploy multi-factor authentication for your organization:</span></span>

- [<span data-ttu-id="125c5-170">Azure AD 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="125c5-170">Azure AD Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

<span data-ttu-id="125c5-171">일부 그룹 및 팀에 중요한 정보가 있는 경우 그룹 또는 팀의 민감도 레이블에 따라 장치 관리 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-171">If you have sensitive information in some of your groups and teams, you can enforce device management policies based on a group or team's sensitivity label.</span></span> <span data-ttu-id="125c5-172">관리되지 않는 장치에서 액세스를 완전히 차단하거나 제한된 웹 전용 액세스를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-172">You can block access entirely from unmanaged devices, or allow limited, web only access:</span></span>

- [<span data-ttu-id="125c5-173">민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기</span><span class="sxs-lookup"><span data-stu-id="125c5-173">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="125c5-174">SharePoint에서는 지정된 네트워크 위치에서 사이트에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-174">In SharePoint, you can restrict access to sites from specified network locations.</span></span>

- [<span data-ttu-id="125c5-175">네트워크 위치에 따라 SharePoint 및 OneDrive 데이터에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="125c5-175">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


<span data-ttu-id="125c5-176">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="125c5-176">Additional resources:</span></span>

- [<span data-ttu-id="125c5-177">조건부 액세스 배포 계획</span><span class="sxs-lookup"><span data-stu-id="125c5-177">Plan a Conditional Access deployment</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [<span data-ttu-id="125c5-178">Microsoft Intune 개요</span><span class="sxs-lookup"><span data-stu-id="125c5-178">Microsoft Intune overview</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [<span data-ttu-id="125c5-179">관리되지 않는 장치에서 SharePoint 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="125c5-179">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a><span data-ttu-id="125c5-180">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="125c5-180">Guest access</span></span>

<span data-ttu-id="125c5-181">전자 메일 주소의 도메인에 따라 게스트를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-181">You can restrict guests based on the domain of their email address.</span></span> <span data-ttu-id="125c5-182">SharePoint는 조직 전체 및 사이트별 도메인 제한 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-182">SharePoint offers organization-wide and site-specific domain restriction settings.</span></span> <span data-ttu-id="125c5-183">그룹 및 Teams는 Azure AD에서 도메인 허용 및 거부 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-183">Groups and Teams use the domain allow and deny lists in Azure AD.</span></span> <span data-ttu-id="125c5-184">원치 않는 공유를 방지하고 일관된 사용자 환경을 보장하도록 두 설정을 모두 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-184">Be sure to configure both settings to avoid unwanted sharing and ensure a consistent user experience:</span></span>

- [<span data-ttu-id="125c5-185">도메인으로 SharePoint 및 OneDrive 콘텐츠 공유 제한</span><span class="sxs-lookup"><span data-stu-id="125c5-185">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [<span data-ttu-id="125c5-186">특정 조직의 B2B 사용자에 대한 초대 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="125c5-186">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

<span data-ttu-id="125c5-187">Microsoft 365에서는 모든 사용자 공유 링크를 사용하여 파일 및 폴더를 *익명으로* 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-187">Microsoft 365 allows anonymous sharing of files and folders by using *Anyone* sharing links.</span></span> <span data-ttu-id="125c5-188">*모든* 링크를 전달할 수 있으며 링크가 있는 모든 사람은 공유 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-188">*Anyone* links can be forwarded and anyone with the link can access the shared item.</span></span> <span data-ttu-id="125c5-189">데이터의 민감도에 따라 링크를 완전히 해제하거나  링크 권한을 읽기 전용으로 제한하거나, 링크의 만료 시간을 설정하는 등 모든 사용자 링크가 사용되는 방법을 관리하도록 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-189">Depending on the sensitivity of your data, consider governing how *Anyone* links are used - including turning them off entirely, restricting link permissions to read-only, or setting an expiration time for them:</span></span>

- [<span data-ttu-id="125c5-190">모든 사용자 링크 해제</span><span class="sxs-lookup"><span data-stu-id="125c5-190">Turn off Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [<span data-ttu-id="125c5-191">모든 사용자 링크에 대한 링크 권한 설정</span><span class="sxs-lookup"><span data-stu-id="125c5-191">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [<span data-ttu-id="125c5-192">모든 사용자 링크의 만료 날짜를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-192">Set an expiration date for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

<span data-ttu-id="125c5-193">파일 또는 폴더를 공유할 때 선택할 수 있는 여러 링크 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-193">When sharing files or folders, users have several link types to choose from.</span></span> <span data-ttu-id="125c5-194">실수로 부적절한 공유의 위험을 줄이기 위해 사용자가 공유할 때 사용자에게 제공된 기본 링크 유형을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-194">To reduce the risk of accidental inappropriate sharing, you can change the default link type presented to users when they share.</span></span> <span data-ttu-id="125c5-195">예를 들어 익명 액세스를  허용하는 모든 사용자 링크에서 기본값을 변경하면 조직 링크의 사용자에 대한 중요한 정보의 원치 않는 외부 공유 위험을 줄일 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="125c5-195">For example, changing the default from *Anyone* links - which allow anonymous access - to *People in your organization* links can reduce the risk of unwanted external sharing of sensitive information:</span></span>

- [<span data-ttu-id="125c5-196">사이트의 기본 연결 종류 변경</span><span class="sxs-lookup"><span data-stu-id="125c5-196">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

<span data-ttu-id="125c5-197">조직에 게스트와 공유해야 하는 중요한 데이터가 있지만 부적절한 공유가 우려되는 경우 파일 및 폴더의 외부 공유를 지정된 보안 그룹의 구성원으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-197">If your organization has sensitive data that you need to share with guests, but you're concerned about inappropriate sharing, you can limit external sharing of files and folders to the members of specified security groups.</span></span> <span data-ttu-id="125c5-198">이렇게 하면 특정 사용자 그룹으로 외부 공유를 제한하거나 사용자가 보안 그룹에 추가하기 전에 적절한 외부 공유에 대한 교육을 하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-198">In this way, you can restrict sharing externally to a specific group of people, or require your users to take training around appropriate external sharing before adding them to the security group:</span></span>

- [<span data-ttu-id="125c5-199">외부 공유를 지정된 보안 그룹으로 제한</span><span class="sxs-lookup"><span data-stu-id="125c5-199">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

<span data-ttu-id="125c5-200">그룹 및 Teams에는 게스트 액세스를 허용하거나 거부하는 조직 수준 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-200">Groups and Teams have organization-level setting that allow or deny guest access.</span></span> <span data-ttu-id="125c5-201">[Microsoft PowerShell을](per-group-guest-access.md)사용하여 특정 팀 또는 그룹에 대한 게스트 액세스를 제한할 수 있는 반면 민감도 레이블을 사용하여 이 작업을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-201">While you can [restrict guest access to specific teams or groups by using Microsoft PowerShell](per-group-guest-access.md), we recommend doing this by means of a sensitivity label.</span></span> <span data-ttu-id="125c5-202">민감도 레이블을 사용하면 적용된 레이블에 따라 게스트 액세스를 자동으로 허용하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-202">With sensitivity labels you can automatically allow or deny guest access based on the label applied:</span></span>

- [<span data-ttu-id="125c5-203">민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 콘텐츠 보호하기</span><span class="sxs-lookup"><span data-stu-id="125c5-203">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="125c5-204">Microsoft 365는 다양한 정보 공유 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-204">Microsoft 365 offers many different methods of sharing information.</span></span> <span data-ttu-id="125c5-205">중요한 정보가 있는 경우 공유 방법을 제한하려는 경우 공유 제한 옵션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-205">If you have sensitive information and you want to restrict how it's shared, review the options for limiting sharing:</span></span>

- [<span data-ttu-id="125c5-206">Microsoft 365에서의 공유 제한</span><span class="sxs-lookup"><span data-stu-id="125c5-206">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

<span data-ttu-id="125c5-207">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="125c5-207">Additional resources:</span></span>

- [<span data-ttu-id="125c5-208">Microsoft 365를 사용하여 안전한 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="125c5-208">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [<span data-ttu-id="125c5-209">인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례</span><span class="sxs-lookup"><span data-stu-id="125c5-209">Best practices for sharing files and folders with unauthenticated users</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [<span data-ttu-id="125c5-210">파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기</span><span class="sxs-lookup"><span data-stu-id="125c5-210">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [<span data-ttu-id="125c5-211">보안 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="125c5-211">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [<span data-ttu-id="125c5-212">B2B 외부 공동 작업을 사용하도록 설정하고 게스트를 초대할 수 있는 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-212">Enable B2B external collaboration and manage who can invite guests</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a><span data-ttu-id="125c5-213">사용자 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-213">User management</span></span>

<span data-ttu-id="125c5-214">그룹 및 팀이 조직에서 발전함에 따라 팀 및 그룹 구성원을 정기적으로 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-214">As groups and teams evolve in your organization, a good practice is to review team and group membership on a regular basis.</span></span> <span data-ttu-id="125c5-215">이는 구성원 자격이 변경된 팀과 그룹, 중요한 정보를 포함하는 그룹 또는 게스트를 포함하는 그룹에 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-215">This may be particularly useful for teams and groups with a changing membership, those that contain sensitive information, or those that include guests.</span></span> <span data-ttu-id="125c5-216">이러한 팀 및 그룹에 대한 액세스 검토를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-216">Consider setting up access reviews for these teams and groups:</span></span>

- [<span data-ttu-id="125c5-217">Azure AD 액세스 검토란?</span><span class="sxs-lookup"><span data-stu-id="125c5-217">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

<span data-ttu-id="125c5-218">많은 조직에서는 다른 조직이나 주요 공급업체와의 비즈니스 파트너 관계를 심층 협력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-218">Many organizations have business partnerships with other organizations or key vendors with whom they collaborate in depth.</span></span> <span data-ttu-id="125c5-219">이러한 시나리오에서는 사용자 관리 및 리소스 액세스가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-219">User management and access to resources can be challenging to manage in these scenarios.</span></span> <span data-ttu-id="125c5-220">일부 사용자 관리 작업을 자동화하고 일부 작업을 파트너 조직으로 전환하는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-220">Consider automating some of the user management tasks and even transitioning some of them to your partner organization:</span></span>

- [<span data-ttu-id="125c5-221">Azure AD 권리 관리란?</span><span class="sxs-lookup"><span data-stu-id="125c5-221">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

<span data-ttu-id="125c5-222">Teams의 비공개 채널은 팀 구성원의 하위 집합 간에 범위가 지정한 대화 및 파일 공유를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-222">Private channels in Teams allow for scoped conversations and file sharing between a subset of team members.</span></span> <span data-ttu-id="125c5-223">특정 비즈니스 요구에 따라 이 기능을 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125c5-223">Depending on your specific business needs, you may want to allow or block this capability.</span></span>

- [<span data-ttu-id="125c5-224">Microsoft Teams의 비공개 채널</span><span class="sxs-lookup"><span data-stu-id="125c5-224">Private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [<span data-ttu-id="125c5-225">Microsoft Teams에서 비공개 채널의 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-225">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

<span data-ttu-id="125c5-226">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="125c5-226">Additional resources:</span></span>

- [<span data-ttu-id="125c5-227">Azure Active Directory ID 거버넌스</span><span class="sxs-lookup"><span data-stu-id="125c5-227">Azure Active Directory Identity Governance</span></span>](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a><span data-ttu-id="125c5-228">관련 항목</span><span class="sxs-lookup"><span data-stu-id="125c5-228">Related topics</span></span>

[<span data-ttu-id="125c5-229">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="125c5-229">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="125c5-230">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="125c5-230">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="125c5-231">Microsoft Teams의 보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="125c5-231">Security and compliance in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[<span data-ttu-id="125c5-232">SharePoint에서 공유 설정 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-232">Manage sharing settings in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[<span data-ttu-id="125c5-233">Yammer에서 외부 네트워크 생성 및 관리</span><span class="sxs-lookup"><span data-stu-id="125c5-233">Create and manage an external network in Yammer</span></span>](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[<span data-ttu-id="125c5-234">세 가지 보호 계층으로 Teams 구성</span><span class="sxs-lookup"><span data-stu-id="125c5-234">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
