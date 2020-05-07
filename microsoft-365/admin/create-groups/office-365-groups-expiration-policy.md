---
title: 그룹 만료 정책
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
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
description: Microsoft 365 그룹 만료 정책에 대해 자세히 알아봅니다.
ms.openlocfilehash: 0cb67b87a542d021387365802bd5969f4c4332b8
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064824"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="04040-103">Microsoft 365 그룹 만료 정책</span><span class="sxs-lookup"><span data-stu-id="04040-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="04040-104">Microsoft 365 그룹의 사용이 증가 함에 의해 관리자와 사용자는 사용 되지 않은 그룹을 정리할 수 있는 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-104">With the increase in usage of Microsoft 365 groups, administrators and users need a way to clean up unused groups.</span></span> <span data-ttu-id="04040-105">만료 정책은 시스템에서 비활성 그룹을 제거 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-105">Expiration policies can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="04040-106">그룹이 만료 되 면 관련 된 모든 서비스 (사서함, Planner, SharePoint 사이트, 팀 등)도 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="04040-107">그룹이 만료 되 면 "일시 삭제"가 되어 최대 30 일 동안 복구할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="04040-108">관리자는 만료 기간을 지정할 수 있으며 해당 기간 끝에 도달 하 고 갱신 되지 않은 비활성 그룹은 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="04040-109">만료 기간은 그룹을 만들 때 또는 마지막으로 갱신 된 날짜에 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-109">The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="04040-110">그룹 소유자는 만료 되기 전에 자동으로 전자 메일을 보내 다른 만료 간격으로 그룹을 갱신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="04040-111">팀 사용자는 팀에 영구 알림을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="04040-112">현재 사용 중인 그룹은 자동으로 갱신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="04040-113">다음 작업 중 하나를 수행 하면 그룹이 자동으로 갱신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="04040-114">SharePoint-파일을 보고, 편집 하 고, 다운로드 하거나, 이동 하거나, 공유 하거나, 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-114">SharePoint - view, edit, download, move, share, or upload files.</span></span>
- <span data-ttu-id="04040-115">Outlook-그룹에서 그룹 메시지를 읽거나 메시지를 작성 합니다 (예를 들어, 웹에서 Outlook).</span><span class="sxs-lookup"><span data-stu-id="04040-115">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="04040-116">팀-팀 채널을 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-116">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04040-117">만료 정책을 변경 하면 서비스에서 각 그룹의 만료 날짜를 다시 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-117">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="04040-118">항상 그룹을 만든 날짜부터 계산을 시작 하 고 새 만료 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-118">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="04040-119">만료는 기본적으로 꺼져 있다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-119">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="04040-120">관리자가 사용 하려는 조직에 대해이를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-120">Administrators will have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="04040-121">Microsoft 365 그룹에 대 한 만료 정책을 구성 하 고 사용 하려면 만료 정책이 적용 되는 모든 그룹의 구성원에 대해 Azure AD Premium 라이선스를 소유 하 고 반드시 할당 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="04040-121">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="04040-122">자세한 내용은 [Azure Active Directory Premium 시작을](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04040-122">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="04040-123">Microsoft 365 groups 만료 정책을 구성 하 고 사용할 수 있는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="04040-123">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="04040-124">역할</span><span class="sxs-lookup"><span data-stu-id="04040-124">Role</span></span>|<span data-ttu-id="04040-125">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="04040-125">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="04040-126">전역 관리자 (Azure, 회사 관리자), 사용자 관리자</span><span class="sxs-lookup"><span data-stu-id="04040-126">Global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="04040-127">Microsoft 365 groups 만료 정책 설정을 만들거나, 읽거나, 업데이트 하거나, 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-127">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="04040-128">사용자</span><span class="sxs-lookup"><span data-stu-id="04040-128">User</span></span>|<span data-ttu-id="04040-129">자신이 소유한 Microsoft 365 그룹 갱신 또는 [복원](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)</span><span class="sxs-lookup"><span data-stu-id="04040-129">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="04040-130">만료 정책을 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="04040-130">How to set the expiration policy</span></span>

<span data-ttu-id="04040-131">위에서 설명한 것 처럼 만료는 기본적으로 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-131">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="04040-132">관리자는 만료 정책을 사용 하도록 설정 하 고 속성을 설정 해야 해당 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-132">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="04040-133">이 기능을 사용 하도록 설정 > 하려면 **AAD (Azure Active Directory)\*\*\*\*그룹** > **만료**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-133">To enable it go to **Azure Active Directory (AAD)** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="04040-134">여기에서 기본 그룹 수명을 설정 하 고 첫 번째 및 두 번째 만료 알림이 그룹 소유자에 게 이동 하기 전 까지의 간격을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-134">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="04040-135">그룹 수명은 일 단위로 지정 되며 180, 365 또는 지정한 사용자 지정 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-135">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="04040-136">사용자 지정 값은 30 일 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-136">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="04040-137">그룹에 소유자가 없으면 만료 전자 메일이 지정 된 관리자에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-137">If the group does not have an owner, the expiration emails will go to a specified administrator.</span></span>

<span data-ttu-id="04040-138">모든 그룹에 대 한 정책, 선택한 그룹만 설정할 수 있으며, **없음 (없음**)을 선택 하 여 완전히 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-138">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="04040-139">현재 다른 그룹에 대해 서로 다른 정책을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-139">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory의 그룹 만료 설정 스크린샷](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="04040-141">보존 정책에서 만료 작동 방식</span><span class="sxs-lookup"><span data-stu-id="04040-141">How expiry works with the retention policy</span></span>

<span data-ttu-id="04040-142">그룹에 대 한 보안 및 준수 센터의 설치 보존 정책을 사용 하는 경우 만료 정책이 보존 정책과 함께 원활 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="04040-142">If you have setup retention policy in Security and Compliance center for groups, expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="04040-143">그룹이 만료 되 면 메일 상자의 그룹 대화와 그룹 사이트의 파일은 보존 정책에 정의 된 특정 기간 (일) 동안 보존 컨테이너에 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-143">When a group expires, the group's conversations in mail box and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="04040-144">그러나 만료 후에는 사용자에 게 그룹이 나 해당 콘텐츠가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-144">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="04040-145">그룹이 만료 되는 경우 그룹 소유자가 학습 하는 방식 및 시기</span><span class="sxs-lookup"><span data-stu-id="04040-145">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="04040-146">그룹 소유자는 전자 메일을 통해서만 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-146">Group owners will only be notified via email.</span></span> <span data-ttu-id="04040-147">Planner, SharePoint 또는 다른 앱을 통해 그룹을 만든 경우에는 항상 전자 메일을 통해 만료 알림이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-147">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="04040-148">팀을 통해 그룹을 만든 경우 그룹 소유자는 활동 섹션을 통해 갱신 하 라는 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-148">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="04040-149">그룹 소유자에 게 유효한 전자 메일 주소가 없는 경우에는 그룹에서 만료를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-149">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="04040-150">30 일 동안 그룹이 만료 되는 경우 그룹 소유자 (또는 소유자가 없는 그룹에 대해 지정한 전자 메일 주소)는 그룹을 쉽게 갱신할 수 있도록 전자 메일을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-150">30 days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="04040-151">갱신 하지 않으면 만료 되기 15 일 전에 다른 갱신 전자 메일이 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-151">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="04040-152">아직 갱신 하지 않은 경우에는 만료 되기 전에 하루 동안 전자 메일 알림을 한 번 더 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04040-152">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="04040-153">어떤 이유로 든 소유자 또는 관리자가 만료 되기 전에 그룹을 갱신 하지 않을 경우 관리자는 만료 후 최대 30 일 동안 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04040-153">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="04040-154">자세한 내용은 [삭제 된 Microsoft 365 그룹 복원을](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04040-154">For details see: [Restore a deleted Microsoft 365 group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

## <a name="related-articles"></a><span data-ttu-id="04040-155">관련 문서</span><span class="sxs-lookup"><span data-stu-id="04040-155">Related articles</span></span>

[<span data-ttu-id="04040-156">보존 정책 개요</span><span class="sxs-lookup"><span data-stu-id="04040-156">Overview of retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[<span data-ttu-id="04040-157">분리된 그룹에 새 소유자 할당</span><span class="sxs-lookup"><span data-stu-id="04040-157">Assign a new owner to an orphaned group</span></span>](https://support.microsoft.com/en-us/office/assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)

<span data-ttu-id="04040-158">[Microsoft 365 그룹 만료 구성](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '</span><span class="sxs-lookup"><span data-stu-id="04040-158">[Configure Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '</span></span>
