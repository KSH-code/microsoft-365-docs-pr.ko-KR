---
title: 관리자를 위한 Office 365 그룹 개요
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: v-teflor
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Office 365 그룹에 대해 알아봅니다.
ms.openlocfilehash: e7a65c41d4ecdbc91e163d9a84241ae549a2f9ec
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245412"
---
# <a name="overview-of-office-365-groups-for-administrators"></a><span data-ttu-id="734ae-103">관리자를 위한 Office 365 그룹 개요</span><span class="sxs-lookup"><span data-stu-id="734ae-103">Overview of Office 365 Groups for administrators</span></span>

<span data-ttu-id="734ae-104">Office 365 그룹은 모든 팀 작업를 Microsoft 365에서 구동 하는 기본 멤버 자격 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-104">Office 365 Groups is the foundational membership service that drives all teamwork across Microsoft 365.</span></span> <span data-ttu-id="734ae-105">Office 365 그룹을 사용 하는 경우 사용자 그룹에 게 해당 사용자가 공유할 공동 작업 자원 모음에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-105">With Office 365 Groups, you can give a group of people access to a collection of collaboration resources for those people to share.</span></span> <span data-ttu-id="734ae-106">이러한 리소스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-106">These resources include:</span></span>

- <span data-ttu-id="734ae-107">공유 Outlook 받은 편지함</span><span class="sxs-lookup"><span data-stu-id="734ae-107">A shared Outlook inbox</span></span>
- <span data-ttu-id="734ae-108">공유 일정</span><span class="sxs-lookup"><span data-stu-id="734ae-108">A shared calendar</span></span>
- <span data-ttu-id="734ae-109">SharePoint 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="734ae-109">A SharePoint document library</span></span>
- <span data-ttu-id="734ae-110">Planner</span><span class="sxs-lookup"><span data-stu-id="734ae-110">A Planner</span></span>
- <span data-ttu-id="734ae-111">Power BI</span><span class="sxs-lookup"><span data-stu-id="734ae-111">Power BI</span></span>
- <span data-ttu-id="734ae-112">Yammer (그룹이 Yammer에서 만들어진 경우)</span><span class="sxs-lookup"><span data-stu-id="734ae-112">Yammer (if the group was created from Yammer)</span></span>
- <span data-ttu-id="734ae-113">팀 (그룹이 팀에서 만든 경우)</span><span class="sxs-lookup"><span data-stu-id="734ae-113">A Team (if the group was created from Teams)</span></span>
- <span data-ttu-id="734ae-114">로드맵 (웹에 대 한 Project가 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="734ae-114">Roadmap (if you have Project for the web )</span></span>

<span data-ttu-id="734ae-115">Office 365 그룹에서는 구성원을 그룹에 추가 하면 해당 그룹에서 제공 하는 도구에 필요한 사용 권한을 자동으로 부여 하므로 이러한 각 리소스에 사용 권한을 수동으로 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-115">With an Office 365 group, you don’t have to manually assign permissions to each of these resources, because adding members to the group automatically gives them the permissions they need to the tools that the group provides.</span></span>

<span data-ttu-id="734ae-116">[그룹 만들기를 특정 사용자 집합으로 제한](manage-creation-of-groups.md)하지 않으면 모든 Office 365 사용자가 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-116">Any Office 365 user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md).</span></span> <span data-ttu-id="734ae-117">그룹 만들기를 제한 하는 경우 그룹을 만들 수 없는 사용자는 SharePoint 사이트, 계획 또는 팀을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-117">Note that if you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams.</span></span> <span data-ttu-id="734ae-118">이러한 서비스는 사용자 컨텍스트를 사용 하 여 그룹을 만들 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-118">These services need to be able to create a group using the user context.</span></span> <span data-ttu-id="734ae-119">사용자가 그룹의 구성원 인 경우 Planner에서 작업을 만들거나 Outlook의 대화에 응답할 때와 같은 그룹 작업에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-119">Users can still participate in group activities, such as creating tasks in Planner or responding to conversations in Outlook, provided they are a member of the group.</span></span>

<span data-ttu-id="734ae-120">그룹에는 다음과 같은 역할이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-120">Groups have the following roles:</span></span>

- <span data-ttu-id="734ae-121">**소유자** -그룹 소유자는 구성원을 추가 또는 제거할 수 있으며 공유 받은 편지함에서 대화를 삭제 하거나 그룹에 대 한 서로 다른 설정을 변경 하는 기능과 같은 고유한 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-121">**Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group.</span></span> <span data-ttu-id="734ae-122">그룹 소유자는 그룹 이름을 바꾸고 설명 또는 사진 등을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-122">Group owners can rename the group, update the description or picture and more.</span></span>
- <span data-ttu-id="734ae-123">**구성원** -구성원은 그룹의 모든 항목에 액세스할 수 있지만 그룹 설정은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-123">**Members** - Members can access everything in the group, but can't change group settings.</span></span>
- <span data-ttu-id="734ae-124">**게스트** 그룹 게스트는 조직 외부의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-124">**Guests** - Group guests are members who are from outside your organization.</span></span> <span data-ttu-id="734ae-125">기본적으로 그룹 구성원은 그룹에 참가 하도록 게스트를 초대할 수 있지만 [해당 설정을 제어할](manage-guest-access-in-groups.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-125">By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).</span></span>

<span data-ttu-id="734ae-126">전역 관리자 및 사용자 관리 관리자만 관리 센터에서 그룹을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-126">Only global admins and user management admins can create and manage groups in the admin center.</span></span> <span data-ttu-id="734ae-127">위임된 관리자는 그룹을 만들 수 없습니다(예: 관리자를 대신하여 활동하는 컨설턴트).</span><span class="sxs-lookup"><span data-stu-id="734ae-127">You can't be a delegated admin (for example, a consultant who is an admin on behalf of).</span></span>

<span data-ttu-id="734ae-128">관리자는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-128">As an administrator, you can:</span></span>

- [<span data-ttu-id="734ae-129">그룹을 만들 수 있는 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="734ae-129">Specify who can create groups</span></span>](manage-creation-of-groups.md)
- [<span data-ttu-id="734ae-130">조직의 그룹에 대 한 명명 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="734ae-130">Create a naming policy for groups in your organization</span></span>](groups-naming-policy.md)
- [<span data-ttu-id="734ae-131">그룹을 만들 때 사용할 도메인 선택</span><span class="sxs-lookup"><span data-stu-id="734ae-131">Choose which domain to use when creating a group</span></span>](choose-domain-to-create-groups.md)
- [<span data-ttu-id="734ae-132">그룹에 대 한 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="734ae-132">Manage guest access to groups</span></span>](manage-guest-access-in-groups.md)
- <span data-ttu-id="734ae-133">[삭제 된 그룹 복구](restore-deleted-group.md) (삭제 후 30 일 이내)</span><span class="sxs-lookup"><span data-stu-id="734ae-133">[Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)</span></span>

<span data-ttu-id="734ae-134">Office 365 그룹의 수명 주기를 보다 자동화 된 방식으로 관리 하려면 만료 정책을 사용 하 여 특정 시간 간격으로 그룹을 만료 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-134">If you prefer a more automated way to manage the lifecycle of your Office 365 Groups you can use expiration policies to expire groups at a specific time interval.</span></span> <span data-ttu-id="734ae-135">그룹 소유자는 그룹 만료를 위해 30, 15, 1 일 전에 전자 메일을 받게 되며,이는 여전히 필요한 경우 그룹을 쉽게 갱신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-135">The group's owners will get an email 30, 15 and 1 day before the group expiration that allows them to easily renew the group if it's still needed.</span></span> <span data-ttu-id="734ae-136">자세한 내용은 [Office 365 그룹 만료 정책을](office-365-groups-expiration-policy.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="734ae-136">See: [Office 365 Group Expiration Policy](office-365-groups-expiration-policy.md).</span></span>

<span data-ttu-id="734ae-137">Microsoft 365 관리 센터에서 또는 [PowerShell을 사용](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)하 여 그룹을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-137">You can administer your groups from the Microsoft 365 admin center or [by using PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

<span data-ttu-id="734ae-138">대기업 또는 기업 등의 사용자가 많은 경우 다양 한 용도로 그룹을 만드는 사용자가 여러 명 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-138">If you have a lot of users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes.</span></span> <span data-ttu-id="734ae-139">모범 사례를 보려면 [Office 365 그룹의 거 버 넌 스 계획](plan-for-groups-governance.md) 을 검토 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-139">We highly recommend that you review [Plan for governance in Office 365 Groups](plan-for-groups-governance.md) for best practices.</span></span>

## <a name="group-limits"></a><span data-ttu-id="734ae-140">그룹 제한</span><span class="sxs-lookup"><span data-stu-id="734ae-140">Group limits</span></span>

<span data-ttu-id="734ae-141">Office 365 그룹에는 다음과 같은 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-141">The following limits apply to Office 365 Groups:</span></span>

|<span data-ttu-id="734ae-142">최대 ...</span><span class="sxs-lookup"><span data-stu-id="734ae-142">Maximum...</span></span>|<span data-ttu-id="734ae-143">값</span><span class="sxs-lookup"><span data-stu-id="734ae-143">Value</span></span>|
|:---------|:----|
|<span data-ttu-id="734ae-144">Owners per group</span><span class="sxs-lookup"><span data-stu-id="734ae-144">Owners per group</span></span>|<span data-ttu-id="734ae-145">100</span><span class="sxs-lookup"><span data-stu-id="734ae-145">100</span></span>|
|<span data-ttu-id="734ae-146">Groups a user can create</span><span class="sxs-lookup"><span data-stu-id="734ae-146">Groups a user can create</span></span>|<span data-ttu-id="734ae-147">250</span><span class="sxs-lookup"><span data-stu-id="734ae-147">250</span></span>|
|<span data-ttu-id="734ae-148">관리자가 만들 수 있는 그룹</span><span class="sxs-lookup"><span data-stu-id="734ae-148">Groups an admin can create</span></span>|<span data-ttu-id="734ae-149">최대 기본 테 넌 트 제한인 500K</span><span class="sxs-lookup"><span data-stu-id="734ae-149">Up to default tenant limit of 500K</span></span>|
|<span data-ttu-id="734ae-150">구성원 수</span><span class="sxs-lookup"><span data-stu-id="734ae-150">Number of members</span></span>|<span data-ttu-id="734ae-151">1000 이상이 며 1000만 그룹 대화에 동시에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-151">More than 1,000, though only 1,000 can access the Group conversations concurrently.</span></span> <br><span data-ttu-id="734ae-152">Outlook에서 매우 큰 그룹의 일정 및 대화에 액세스할 때 지연이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-152">Users might notice delays when accessing the calendar and conversations in very large groups in Outlook.</span></span>|
|<span data-ttu-id="734ae-153">사용자가 구성원으로 속해 있을 수 있는 그룹 수</span><span class="sxs-lookup"><span data-stu-id="734ae-153">Number of Groups a user can be a member of</span></span>|<span data-ttu-id="734ae-154">1,000</span><span class="sxs-lookup"><span data-stu-id="734ae-154">1,000</span></span>|
|<span data-ttu-id="734ae-155">파일 저장소</span><span class="sxs-lookup"><span data-stu-id="734ae-155">File storage</span></span>|<span data-ttu-id="734ae-156">1 테라바이트 + 10 g b 구독 된 사용자 당 및 구매한 추가 저장소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-156">1 Terabyte + 10 GB per subscribed user + any additional storage purchased.</span></span> <span data-ttu-id="734ae-157">무제한의 추가 저장소를 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-157">You can purchase an unlimited amount of additional storage.</span></span>|
|<span data-ttu-id="734ae-158">그룹 사서함 크기</span><span class="sxs-lookup"><span data-stu-id="734ae-158">Group Mailbox size</span></span>|<span data-ttu-id="734ae-159">50GB</span><span class="sxs-lookup"><span data-stu-id="734ae-159">50 GB</span></span>|

<span data-ttu-id="734ae-160">Office 365 조직이 보유할 수 있는 기본 최대 Office 365 그룹 그룹 수는 현재 500,000개이지만, 요청으로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-160">The default maximum number of Office 365 Groups that an Office 365 organization can have is currently 500,000, but can be increased by request.</span></span> <span data-ttu-id="734ae-161">Office 365 그룹 제한에 대 한 자세한 내용은 [office 365 그룹-관리자 도움말](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="734ae-161">For more information on Office 365 Groups limits, see [Office 365 Groups - Admin help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)</span></span>

<span data-ttu-id="734ae-162">사용자가 그룹 사용에 대 한 정보를 사용할 수 있는 경우 Office 365 그룹을 관리 하는 것이 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-162">Managing your Office 365 Groups is more effective when you have actionable information about Groups usage.</span></span> <span data-ttu-id="734ae-163">Microsoft 365 관리 센터에는 저장소 사용, 보유 하 고 있는 활성 그룹 수 및 사용자가 그룹을 사용 하는 방법에 대 한 작업을 볼 수 있는 보고 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-163">The Microsoft 365 Admin Center has a reporting tool that can let you see things such as storage use, how many active Groups you have and even how your users are using the Groups.</span></span> <span data-ttu-id="734ae-164">자세한 내용은 [관리 센터의 Office 365 보고서](../activity-reports/office-365-groups.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="734ae-164">See: [Office 365 Reports in the admin center](../activity-reports/office-365-groups.md) for more information.</span></span>

## <a name="which-office-365-plans-include-groups"></a><span data-ttu-id="734ae-165">어떤 Office 365 계획에 그룹이 포함 되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="734ae-165">Which Office 365 plans include Groups?</span></span>

<span data-ttu-id="734ae-166">Exchange Online 및 SharePoint Online이 포함 된 모든 Office 365 구독은 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-166">Any Office 365 subscription that has Exchange Online and SharePoint Online will support groups.</span></span> <span data-ttu-id="734ae-167">여기에는 Business Essentials 및 Business Premium 요금제와 Enterprise E1, E3 및 E5 요금제가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-167">That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3 and E5 plans.</span></span> <span data-ttu-id="734ae-168">그룹은 그룹을 만든 사용자 (그룹의 "이끌이" 라고도 함)를 사용 하 여 라이선스를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-168">The Group takes on the licensing of the person who creates the Group (also known as the "organizer" of the Group).</span></span> <span data-ttu-id="734ae-169">이끌이는 그룹에 포함 하려는 모든 기능에 적합 한 라이선스를가지고 있으면 해당 라이선스가 그룹에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-169">As long as the organizer has the proper license for whatever features you want the Group to have, that license will convey to the Group.</span></span>

> [!NOTE]
> <span data-ttu-id="734ae-170">Office 365 서비스 제품군 및 계획에 대 한 자세한 내용은 [office 365 계획 옵션](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="734ae-170">For more details about Office 365 service families and plans, please check [Office 365 plan options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span></span>

<span data-ttu-id="734ae-171">Exchange 전용 요금제가 있는 경우에도 Outlook에서 공유 받은 편지함 및 공유 일정 기능을 가져올 수는 있지만 문서 라이브러리, Planner 또는 기타 기능은 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-171">If you have an Exchange-only plan you can still get the shared Inbox and shared Calendar features of groups in Outlook but you won’t get the document library, Planner or any of the other capabilities.</span></span>

<span data-ttu-id="734ae-172">Office 365 그룹은 AAD (Azure Active Directory)에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-172">Office 365 Groups works with Azure Active Directory (AAD).</span></span> <span data-ttu-id="734ae-173">얻을 수 있는 그룹 기능은 사용 하는 Azure Active Directory 구독 및 그룹 구성 도우미에 할당 된 라이선스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-173">The Groups features you get depends on which Azure Active Directory subscription you have, and what license(s) is assigned to the organizer of the Group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="734ae-174">모든 그룹 기능에서 Azure AD Premium 구독을 사용 하는 경우 사용자는 AAD P1 라이선스가 할당 되어 있는지 여부에 관계 없이 그룹에 가입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-174">For all the Groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them.</span></span> <span data-ttu-id="734ae-175">라이선스가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-175">Licensing isn't enforced.</span></span>
> <span data-ttu-id="734ae-176">정기적으로 사용 현황 보고서를 생성 하 여 라이선스가 누락 된 사용자를 확인 하 고, 라이선스 요구 사항을 충족 하기 위해 할당 해야 하는 것이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-176">Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements.</span></span> <span data-ttu-id="734ae-177">예를 들어 사용자에 게 라이선스가 없고 명명 정책이 적용 되는 그룹에 추가 된다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-177">For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced.</span></span> <span data-ttu-id="734ae-178">보고서는 라이선스가 필요 하다 고 사용자에 게 플래그를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="734ae-178">The report will flag for you that they need a license.</span></span>

## <a name="related-articles"></a><span data-ttu-id="734ae-179">관련 문서</span><span class="sxs-lookup"><span data-stu-id="734ae-179">Related articles</span></span>

[<span data-ttu-id="734ae-180">Office 365 그룹에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="734ae-180">Learn about Office 365 Groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="734ae-181">Office 365 그룹으로 메일 그룹 업그레이드</span><span class="sxs-lookup"><span data-stu-id="734ae-181">Upgrade distribution lists to Office 365 Groups</span></span>](../manage/upgrade-distribution-lists.md)

[<span data-ttu-id="734ae-182">PowerShell을 사용하여 Office 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="734ae-182">Manage Office 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[<span data-ttu-id="734ae-183">SharePoint Online 제한 사항</span><span class="sxs-lookup"><span data-stu-id="734ae-183">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
