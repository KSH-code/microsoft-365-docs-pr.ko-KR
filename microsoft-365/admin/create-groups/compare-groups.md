---
title: 그룹 비교하기
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 그룹 구성원은 대화, 파일, 일정 이벤트, Stream 및 플래너에 대한 그룹 전자 메일 및 공유 작업 영역을 가져옵니다.
ms.openlocfilehash: 038c4b9f6d9d28e62c0fb9b8f117db96ac42ddfb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903843"
---
# <a name="compare-groups"></a><span data-ttu-id="b744f-103">그룹 비교</span><span class="sxs-lookup"><span data-stu-id="b744f-103">Compare groups</span></span>

<span data-ttu-id="b744f-104">Microsoft 365 관리 센터의 **Groups** 구역에서 다음과 같은 유형의 그룹을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="b744f-105">**Microsoft 365 그룹**(이전 Office 365 그룹)은 회사 내부 및 외부의 사용자 간의 공동 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-105">**Microsoft 365 groups** (formerly Office 365 groups) are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="b744f-106">**메일 그룹** 사용자 그룹에 전자 메일 알림을 보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-106">**Distribution groups** are used for sending email notifications to a group of people.</span></span>
- <span data-ttu-id="b744f-107">**보안 그룹** 은 SharePoint 사이트와 같은 리소스에 대한 액세스 권한을 부여하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="b744f-108">**메일 사용이 가능한 보안 그룹** 은 SharePoint와 같은 리소스에 대한 액세스 권한을 부여하고 해당 사용자에게 전자 메일로 알림을 보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="b744f-109">**공유 사서함** 은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="b744f-110">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="b744f-110">Microsoft 365 groups</span></span>

<span data-ttu-id="b744f-111">Microsoft 365 그룹은 회사 내부 및 외부의 사용자 간의 공동 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="b744f-112">각 Microsoft 365 그룹에서 구성원은 대화, 파일, 일정 이벤트, Stream 및 플래너에 대한 그룹 전자 메일 및 공유 작업 영역을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, Stream and a Planner.</span></span>

<span data-ttu-id="b744f-113">[관리자에 의해 사용 가능하도록](manage-guest-access-in-groups.md) 설정한 경우 회사 외부 사용자를 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="b744f-114">외부 보낸 사람이 그룹 전자 메일 주소로 전자 메일을 보낼 수 있도록 허용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="b744f-115">Microsoft 365 그룹은 [Azure Active Directory에서 동적 구성원에 대해 구성](/azure/active-directory/users-groups-roles/groups-change-type)할 수 있습니다. 부서, 위치, 제목 등의 사용자 특성을 기반으로 그룹 구성원을 자동으로 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="b744f-116">Microsoft 365 그룹은 iOS용 Outlook 및 Android용 Outlook과 같은 모바일 앱을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="b744f-117">[관리자에 의해 사용 가능하도록](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md) 설정한 경우 그룹 구성원은 그룹 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="b744f-118">메일 그룹</span><span class="sxs-lookup"><span data-stu-id="b744f-118">Distribution groups</span></span>

<span data-ttu-id="b744f-119">[메일 그룹](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)은 사용자 그룹에 알림을 보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-119">[Distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="b744f-120">관리자에 의해 사용 가능하도록 설정한 경우 외부 전자메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="b744f-121">메일 그룹은 "A 빌딩의 사용자" 또는 "Contoso의 모든 사용자"와 같은 사용자 그룹 집합에 정보를 브로드캐스팅하는 경우에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

<span data-ttu-id="b744f-122">배포 그룹은 [Microsoft 365 groups로 업그레이드](../manage/upgrade-distribution-lists.md) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-122">Distribution groups can be [upgraded to Microsoft 365 groups](../manage/upgrade-distribution-lists.md).</span></span>

<span data-ttu-id="b744f-123">메일 그룹은 Microsoft Teams에서 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-123">Distribution groups can be added to a team in Microsoft Teams.</span></span>

## <a name="security-groups"></a><span data-ttu-id="b744f-124">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="b744f-124">Security groups</span></span>

<span data-ttu-id="b744f-125">[보안 그룹](../email/create-edit-or-delete-a-security-group.md)은 SharePoint와 같은 Microsoft 365 리소스에 대한 액세스 권한을 부여하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-125">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="b744f-126">각 리소스에 사용자를 개별적으로 추가하는 것이 아니라 그룹을 관리하기만 하면 되므로 관리를 더 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-126">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="b744f-p105">보안 그룹에는 사용자 또는 장치가 포함될 수 있습니다. 장치에 대한 보안 그룹 만들기는 Intune과 같은 모바일 장치 관리 서비스와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-p105">Security groups can contain users or devices. Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="b744f-129">보안 그룹은 [Azure Active Directory에서 동적 구성원에 대해 구성](/azure/active-directory/users-groups-roles/groups-change-type)할 수 있습니다. 부서, 위치, 제목 등의 사용자 특성이나 운영 체제 버전 등의 장치 속성을 기반으로 그룹 구성원을 자동으로 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-129">Security groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

<span data-ttu-id="b744f-130">보안 그룹을 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-130">Security groups can be added to a team.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="b744f-131">메일 사용 가능 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="b744f-131">Mail-enabled security groups</span></span>

<span data-ttu-id="b744f-132">메일 사용이 가능한 보안 그룹은 Azure Active Directory를 통해 동적으로 관리할 수 없으며 장치를 포함할 수 없는 경우를 제외하고 일반 보안 그룹과 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-132">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="b744f-133">해당 그룹의 모든 구성원에게 메일을 보낼 수 있는 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-133">They include the ability to send mail to all the members of the group.</span></span>

<span data-ttu-id="b744f-134">메일 사용이 가능한 보안 그룹을 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-134">Mail-enabled security groups can be added to a team.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="b744f-135">공유 사서함</span><span class="sxs-lookup"><span data-stu-id="b744f-135">Shared mailboxes</span></span>

<span data-ttu-id="b744f-136">[공유 사서함](../email/create-a-shared-mailbox.md)은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소, 리셉션 데스크 또는 여러 사용자에 의해 공유될 수도 있는 기타 기능)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-136">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="b744f-137">관리자가 이 기능을 사용 가능하도록 설정한 경우 공유 사서함이 외부 전자 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-137">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="b744f-138">공유 사서함에는 공동 작업에 사용할 수 있는 일정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-138">Shared mailboxes include a calendar that can be used for collaboration.</span></span>

<span data-ttu-id="b744f-139">그룹 사서함에 대한 권한이 있는 사용자는 관리자가 해당 사용자에게 권한을 부여한 경우 사서함 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-139">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="b744f-140">이 기능은 사용자가 "Contoso 지원" 또는 “A 빌딩 리셉션 데스크"에서 전자 메일을 보낼 수 있기 때문에 도움말 및 지원 사서함에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-140">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="b744f-141">Microsoft 365 그룹으로 공유 사서함을 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b744f-141">It's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> 

## <a name="related-content"></a><span data-ttu-id="b744f-142">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="b744f-142">Related content</span></span>

<span data-ttu-id="b744f-143">[Microsoft 365 그룹에 대한 자세한 정보](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)(기사)</span><span class="sxs-lookup"><span data-stu-id="b744f-143">[Learn about Microsoft 365 groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (article)</span></span>\
<span data-ttu-id="b744f-144">[Outlook에서 배포 목록을 그룹으로 업그레이드해야 하는 이유](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)(기사)</span><span class="sxs-lookup"><span data-stu-id="b744f-144">[Why you should upgrade your distribution lists to groups in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (article)</span></span>
