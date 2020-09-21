---
title: Exchange Online 관리자 역할 정보
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Exchange online 관리자는 조직의 전자 메일 및 사서함을 관리 합니다. 예를 들어 사용자 사서함에서 삭제 된 항목을 복구 합니다. '
ms.openlocfilehash: be4c8a4f1c75402d690cc705dd408c9070e40c9b
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131773"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="4a4c6-104">Exchange Online 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="4a4c6-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="4a4c6-105">Microsoft 365을 관리 하는 데 도움이 되도록 사용자에 게 [Exchange 관리 센터](https://go.microsoft.com/fwlink/p/?LinkID=271807)에서 조직의 전자 메일 및 사서함을 관리 하기 위한 사용 권한을 [할당할](assign-admin-roles.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="4a4c6-106">이렇게 하려면 Exchange 관리 역할에 해당 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="4a4c6-107">**팁**: 사용자를 Exchange 관리 역할에 할당 하는 경우 서비스 관리자 역할에 자신을 할당 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="4a4c6-108">이러한 방식으로 Microsoft 365 관리 센터에서 Exchange Online 서비스의 상태와 같은 중요 한 정보를 확인 하 고 알림 변경 및 릴리스 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4a4c6-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="4a4c6-109">Before you begin</span></span>

<span data-ttu-id="4a4c6-110">다음은 사용자가 Exchange 관리 역할에 할당 될 때 수행할 수 있는 몇 가지 주요 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="4a4c6-111">사용자 사서함에서 지운 편지함 복구 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="4a4c6-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="4a4c6-112">[조직의 사서함에 대 한 보관 및 삭제 정책을 설정](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="4a4c6-113">사서함 공유 정책과 같은 사서함 기능 설정: 사용자가 조직 외부의 다른 사용자와 일정 및 연락처 정보를 공유 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="4a4c6-114">다른 사용자의 사서함에 대해 "[다른 사람 이름으로 보내기](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" 및 "[전자 메일 보내기](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" 대리인을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on abehalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="4a4c6-115">예를 들어 중역은 도우미가 자신을 대신 하 여 메일을 보낼 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="4a4c6-116">사용자 그룹이 일반 전자 메일 주소에서 전자 메일을 모니터링 하 고 보낼 수 있도록 [공유 사서함을 만듭니다](../email/create-a-shared-mailbox.md) .</span><span class="sxs-lookup"><span data-stu-id="4a4c6-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="4a4c6-117">조직에 대 한 [스팸 방지 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) 및 맬웨어 필터를 전자 메일로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="4a4c6-118">Microsoft 365 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="4a4c6-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="4a4c6-119">Exchange Online 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="4a4c6-119">Exchange Online role groups</span></span>

<span data-ttu-id="4a4c6-120">대규모 조직이 있는 경우 Exchange 관리자가 Exchange 역할 그룹에 사용자를 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-120">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups.</span></span> <span data-ttu-id="4a4c6-121">관리자가 역할 그룹에 사용자를 추가 하면 사용자는 해당 그룹의 구성원만 수행할 수 있는 특정 비즈니스 기능을 수행 하는 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-121">When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="4a4c6-122">예를 들어 Exchange 관리자는 검색 관리 역할 그룹에 다른 사용자를 할당 하 여 특정 조건에 맞는 데이터에 대 한 사서함 검색을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-122">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria.</span></span> <span data-ttu-id="4a4c6-123">자세한 내용은 [Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 및 [역할 그룹 관리](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-123">To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-role"></a><span data-ttu-id="4a4c6-124">다른 관리 역할에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="4a4c6-124">Learn about other admin role</span></span>

- [<span data-ttu-id="4a4c6-125">Microsoft 365 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="4a4c6-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="4a4c6-126">SharePoint Online 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="4a4c6-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="4a4c6-127">비즈니스용 Skype 관리자 역할 정보</span><span class="sxs-lookup"><span data-stu-id="4a4c6-127">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="4a4c6-128">Microsoft 팀 관리자 역할 사용</span><span class="sxs-lookup"><span data-stu-id="4a4c6-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 