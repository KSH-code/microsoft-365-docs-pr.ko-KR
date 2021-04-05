---
title: Microsoft 365 그룹 만료 정책
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Microsoft 365 그룹 만료 정책에 대해 자세히 알아보습니다.
ms.openlocfilehash: fdef06918ec2c35547c084e5f431aa7bef8d6a8c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587626"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="85e0f-103">Microsoft 365 그룹 만료 정책</span><span class="sxs-lookup"><span data-stu-id="85e0f-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="85e0f-104">Microsoft 365 그룹 및 Microsoft Teams의 사용이 증가하면 관리자와 사용자는 사용되지 않는 그룹 및 팀을 정리하는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-104">With the increase in usage of Microsoft 365 groups and Microsoft Teams, administrators and users need a way to clean up unused groups and teams.</span></span> <span data-ttu-id="85e0f-105">Microsoft 365 그룹 만료 정책은 시스템에서 비활성 그룹을 제거하고 더 깔끔하게 만드는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-105">A Microsoft 365 groups expiration policy can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="85e0f-106">그룹이 만료되면 연결된 모든 서비스(사서함, Planner, SharePoint 사이트, 팀 등)도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="85e0f-107">그룹이 만료되면 최대 30일 동안 복구할 수 있는 "소프트 삭제"됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="85e0f-108">관리자는 만료 기간 및 해당 기간이 끝나는 비활성 그룹을 지정할 수 있으며 갱신되지 않은 그룹은 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="85e0f-109">보관된 팀이 포함됩니다. 만료 기간은 그룹이 만들어지거나 마지막으로 갱신된 날짜부터 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-109">(This includes archived teams.) The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="85e0f-110">만료되기 전에 그룹 소유자가 다른 만료 간격으로 그룹을 갱신할 수 있는 전자 메일이 자동으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="85e0f-111">Teams 사용자는 Teams에서 지속적인 알림을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="85e0f-112">적극적으로 사용되고 있는 그룹은 자동으로 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="85e0f-113">다음 작업을 수행하면 그룹이 자동으로 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="85e0f-114">SharePoint - 파일을 보기, 편집, 다운로드, 이동, 공유 또는 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-114">SharePoint - view, edit, download, move, share, or upload files.</span></span> <span data-ttu-id="85e0f-115">(SharePoint 페이지 보기는 자동 갱신 작업으로 계산되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="85e0f-115">(Viewing a SharePoint page does not count as an action for automatic renewal.)</span></span>
- <span data-ttu-id="85e0f-116">Outlook - 그룹에 가입하거나 그룹에서 그룹 메시지를 읽거나 쓰며 메시지(웹용 Outlook)처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-116">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="85e0f-117">Teams - 팀 채널 방문</span><span class="sxs-lookup"><span data-stu-id="85e0f-117">Teams - visiting a teams channel.</span></span>

<span data-ttu-id="85e0f-118">자동 그룹 갱신을 트리거하는 Yammer 활동은 커뮤니티 내에서 SharePoint로 문서를 업로드하는 것뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-118">Note that the only Yammer activity which will trigger an automatic group renewal is the upload of a document to SharePoint within the community.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85e0f-119">만료 정책을 변경하면 서비스에서 각 그룹의 만료 날짜를 다시 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-119">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="85e0f-120">항상 그룹이 만들어진 날짜부터 계산을 시작한 다음 새 만료 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-120">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="85e0f-121">만료는 기본적으로 해제되어 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-121">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="85e0f-122">관리자는 조직에서 사용할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-122">Administrators have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="85e0f-123">Microsoft 365 그룹에 대한 만료 정책을 구성하고 사용하려면 소유해야 하지만 만료 정책이 적용되는 모든 그룹의 구성원에게 Azure AD Premium 라이선스를 할당할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-123">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="85e0f-124">자세한 내용은 [Azure Active Directory Premium 시작을 참조하세요.](/azure/active-directory/active-directory-get-started-premium)</span><span class="sxs-lookup"><span data-stu-id="85e0f-124">For more information see [Getting started with Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="85e0f-125">Microsoft 365 그룹 만료 정책을 구성하고 사용할 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="85e0f-125">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="85e0f-126">역할</span><span class="sxs-lookup"><span data-stu-id="85e0f-126">Role</span></span>|<span data-ttu-id="85e0f-127">이러한 사용자들이 할 수 있는 일</span><span class="sxs-lookup"><span data-stu-id="85e0f-127">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="85e0f-128">Office 365 전역 관리자(Azure, 회사 관리자), 사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="85e0f-128">Office 365 global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="85e0f-129">Microsoft 365 그룹 만료 정책 설정을 만들거나, 읽거나, 업데이트하거나, 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-129">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="85e0f-130">사용자</span><span class="sxs-lookup"><span data-stu-id="85e0f-130">User</span></span>|<span data-ttu-id="85e0f-131">소유한 [](/azure/active-directory/users-groups-roles/groups-restore-deleted) Microsoft 365 그룹 갱신 또는 복원</span><span class="sxs-lookup"><span data-stu-id="85e0f-131">Renew or [restore](/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="85e0f-132">만료 정책을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="85e0f-132">How to set the expiration policy</span></span>

<span data-ttu-id="85e0f-133">위에서 설명한 대로 만료는 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-133">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="85e0f-134">관리자는 만료 정책을 사용하도록 설정하고 해당 정책이 적용될 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-134">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="85e0f-135">이를 사용하도록 설정하려면 **Azure Active Directory 그룹** 만료  >  **로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="85e0f-135">To enable it, go to **Azure Active Directory** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="85e0f-136">여기서 기본 그룹 수명을 설정하고 첫 번째 및 두 번째 만료 알림이 그룹 소유자에게 얼마나 미리 전송될지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-136">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="85e0f-137">그룹 수명은 일로 지정하며 180, 365 또는 지정한 사용자 지정 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-137">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="85e0f-138">사용자 지정 값은 30일 이상을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-138">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="85e0f-139">그룹에 소유자가 없는 경우 만료 전자 메일은 지정된 관리자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-139">If the group does not have an owner, the expiration emails will go to the specified administrator.</span></span>

<span data-ttu-id="85e0f-140">모든 그룹에 대한 정책을 설정하고 선택한 그룹(최대 500개)만 설정하거나 없음을 선택하여 완전히 해제할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="85e0f-140">You can set the policy for all of your groups, only selected groups (up to 500), or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="85e0f-141">현재 다른 그룹에 대해 다른 정책을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-141">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory의 그룹 만료 설정 스크린샷](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="85e0f-143">보존 정책에 만료가 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="85e0f-143">How expiry works with the retention policy</span></span>

<span data-ttu-id="85e0f-144">보안 및 준수 센터에서 그룹에 대한 보존 정책을 설정한 경우 만료 정책은 보존 정책과 원활하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-144">If you have set up a retention policy for groups in the Security and Compliance center, the expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="85e0f-145">그룹이 만료되면 그룹 사이트의 사서함 대화 및 파일은 보존 정책에 정의된 특정 일 수 동안 보존 컨테이너에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-145">When a group expires, the group's mailbox conversations and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="85e0f-146">그러나 만료 후 사용자는 그룹 또는 해당 콘텐츠를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-146">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="85e0f-147">그룹 소유자가 그룹이 만료될지 알아보는 방법 및 시간</span><span class="sxs-lookup"><span data-stu-id="85e0f-147">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="85e0f-148">그룹 소유자는 전자 메일을 통해서만 알림을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-148">Group owners will only be notified via email.</span></span> <span data-ttu-id="85e0f-149">그룹이 Planner, SharePoint 또는 다른 앱을 통해 만들어진 경우 만료 알림은 항상 전자 메일을 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-149">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="85e0f-150">Teams를 통해 그룹을 만든 경우 그룹 소유자는 활동 섹션을 통해 갱신할 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-150">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="85e0f-151">그룹 소유자가 유효한 전자 메일 주소가 없는 경우 그룹에서 만료를 사용하도록 설정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-151">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="85e0f-152">그룹이 만료되기 30일 전에 그룹 소유자(또는 소유자가 없는 그룹에 대해 지정한 전자 메일 주소)는 그룹을 쉽게 갱신할 수 있는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-152">Thirty days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="85e0f-153">갱신하지 않는 경우 만료 15일 전에 다른 갱신 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-153">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="85e0f-154">아직 갱신하지 않은 경우 만료 전날에 전자 메일 알림을 한 번 더 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-154">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="85e0f-155">어떤 이유로 인해 소유자나 관리자가 만료되기 전에 그룹을 갱신하지 않은 경우 관리자는 만료 후 최대 30일 동안 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85e0f-155">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="85e0f-156">자세한 내용은 삭제된 [Microsoft 365 그룹 복원을 참조합니다.](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)</span><span class="sxs-lookup"><span data-stu-id="85e0f-156">For details see: [Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span></span>

## <a name="archiving-group-contents"></a><span data-ttu-id="85e0f-157">보관 그룹 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="85e0f-157">Archiving group contents</span></span>

<span data-ttu-id="85e0f-158">더 이상 사용할 계획이 없는 그룹이 있지만 해당 콘텐츠를 보존하려는 경우 보관 [그룹,](end-life-cycle-groups-teams-sites-yammer.md) 팀 및 Yammer 그룹 서비스에서 정보를 내보내는 방법에 대한 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85e0f-158">If you have a group that you no longer plan to use, but you want to retain its content, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information about how to export information from the different groups services.</span></span>

## <a name="related-topics"></a><span data-ttu-id="85e0f-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="85e0f-159">Related topics</span></span>

[<span data-ttu-id="85e0f-160">공동 작업 거버넌스 계획 단계별</span><span class="sxs-lookup"><span data-stu-id="85e0f-160">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="85e0f-161">공동 작업 거버넌스 계획 만들기</span><span class="sxs-lookup"><span data-stu-id="85e0f-161">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="85e0f-162">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="85e0f-162">Overview of retention policies</span></span>](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[<span data-ttu-id="85e0f-163">분리된 그룹에 새 소유자 할당</span><span class="sxs-lookup"><span data-stu-id="85e0f-163">Assign a new owner to an orphaned group</span></span>](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="85e0f-164">Microsoft 365 그룹 만료 구성</span><span class="sxs-lookup"><span data-stu-id="85e0f-164">Configure Microsoft 365 groups expiration</span></span>](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
