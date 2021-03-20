---
title: 사용자 전자 메일 설정
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 03083fdf-bc52-409a-b2ac-2a5f5c308fa0
description: 이 문서에서는 사용자를 위한 설정을 관리하는 방법에 대한 정보를 제공합니다.
ms.openlocfilehash: db7a7f01fdd5a6bd657bb04f9aaf4491959e0558
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915725"
---
# <a name="user-email-settings"></a><span data-ttu-id="4a8dd-103">사용자 전자 메일 설정</span><span class="sxs-lookup"><span data-stu-id="4a8dd-103">User email settings</span></span>

<span data-ttu-id="4a8dd-104">조직의 관리자에게는 사용자와 관련하여 관리할 수 있는 전자 메일 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-104">As the admin of an organization, there are email settings you can manage on your users.</span></span> <span data-ttu-id="4a8dd-105">이 문서에서는 이러한 설정을 관리하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-105">This article gives you information on managing these settings.</span></span>

## <a name="summary-of-email-settings"></a><span data-ttu-id="4a8dd-106">전자 메일 설정 요약</span><span class="sxs-lookup"><span data-stu-id="4a8dd-106">Summary of email settings</span></span>

<span data-ttu-id="4a8dd-107">이 표에서는 Microsoft 365에서 사용자에 대해 변경할 수 있는 여러 가지 전자 메일 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-107">This table explains the various email settings you can change for a user in Microsoft 365.</span></span>


|<span data-ttu-id="4a8dd-108">메일 설정</span><span class="sxs-lookup"><span data-stu-id="4a8dd-108">Mail setting</span></span>|<span data-ttu-id="4a8dd-109">설명</span><span class="sxs-lookup"><span data-stu-id="4a8dd-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4a8dd-110">사서함 사용 권한</span><span class="sxs-lookup"><span data-stu-id="4a8dd-110">Mailbox permissions</span></span>| <span data-ttu-id="4a8dd-111">**읽기 및 관리** 는 사용자가 다른 사용자의 사서함을 읽고 관리할 수 있는지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-111">**Read and manage** allows you to set whether people can read and manage other people's mailboxes.</span></span> <span data-ttu-id="4a8dd-112">개인의 **다른 사람 이름으로 보내기** 및 **대신 보내기** 권한을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-112">You can also set **Send as** and **Send on behalf** permissions for a person.</span></span> <span data-ttu-id="4a8dd-113">자세한 내용은 [Microsoft 365에서 다른 사용자에게 사서함 사용 권한 부여 - 관리자 도움말](../add-users/give-mailbox-permissions-to-another-user.md)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-113">Check out [Give mailbox permissions to another user in Microsoft 365 - Admin Help](../add-users/give-mailbox-permissions-to-another-user.md) for more details.</span></span> |
|<span data-ttu-id="4a8dd-114">전자 메일 앱</span><span class="sxs-lookup"><span data-stu-id="4a8dd-114">Email apps</span></span>| <span data-ttu-id="4a8dd-115">전자 메일 앱을 사용하여 사용자가 Microsoft 전자 메일에 액세스하는 데 사용할 수 있는 앱을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-115">Email apps allows you to choose the apps a user can use to access their Microsoft email.</span></span> |
|<span data-ttu-id="4a8dd-116">전체 주소 목록에 표시</span><span class="sxs-lookup"><span data-stu-id="4a8dd-116">Show in global address list</span></span>| <span data-ttu-id="4a8dd-117">전체 주소 목록에 표시를 사용하여 조직의 주소 목록에 있는 사용자의 사서함 표시 여부를 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-117">Show in global address list allows you to enable or disable the visibility of the user's mailbox in the organization's address list.</span></span> |
|<span data-ttu-id="4a8dd-118">전자 메일 전달</span><span class="sxs-lookup"><span data-stu-id="4a8dd-118">Email forwarding</span></span>|<span data-ttu-id="4a8dd-119">전자 메일을 전달을 사용하면 사용자가 전달 전자 메일 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-119">Email forwarding allows you to add a forwarding email address to a user.</span></span> <span data-ttu-id="4a8dd-120">해당 사용자에게 전자 메일 주소가 여러 개 있고 모든 전자 메일 주소로 전자 메일을 받을 수 있도록 하려면 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-120">You might want to do this if the person has multiple email addresses and they want to receive emails at all their email addresses.</span></span> <span data-ttu-id="4a8dd-121">자세한 내용은 [Microsoft 365에서 전자 메일 전달 구성](configure-email-forwarding.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-121">Check out [Configure email forwarding in Microsoft 365](configure-email-forwarding.md) for more details.</span></span>|
|<span data-ttu-id="4a8dd-122">자동 회신</span><span class="sxs-lookup"><span data-stu-id="4a8dd-122">Automatic replies</span></span>|<span data-ttu-id="4a8dd-123">자동 회신을 사용하여 다른 사람이 사용자의 전자 메일 주소로 전자 메일을 보내는 경우 자동 회신을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-123">Automatic replies allows you to set an automatic reply when someone sends an email to the person's email address.</span></span> <span data-ttu-id="4a8dd-124">직원이 회사를 떠나 전자 메일 보내는 사람에게 알리려는 경우 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-124">You might want to do this if an employee leaves your company and you want to let the email sender know.</span></span>|
|<span data-ttu-id="4a8dd-125">기타 작업</span><span class="sxs-lookup"><span data-stu-id="4a8dd-125">More actions</span></span>| <span data-ttu-id="4a8dd-126">**공유 사서함으로 변환** 을 사용하면 사용자의 사서함을 공유 사서함으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-126">**Convert to shared mailbox** allows you to convert the user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="4a8dd-127">직원이 조직에서 나갈 때 사서함 데이터를 한동안 유지하려는 경우 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-127">You might do this if the person leaves your organization and you want to keep their mailbox data around for a while.</span></span> <span data-ttu-id="4a8dd-128">[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md) 및 [공유 사서함 열기 및 사용](https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-128">Check out [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) and [Open and use a shared mailbox](https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd).</span></span></br><span data-ttu-id="4a8dd-129">**Exchange 속성 편집** 을 사용하여 Exchange 관리 센터를 사용하여 추가 Exchange Online 작업을 관리할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="4a8dd-129">**Edit Exchange properties** allows you to manage additional Exchange Online tasks using the Exchange admin center.</span></span> <span data-ttu-id="4a8dd-130">[Exchange Online에서 사용자 사서함 관리](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)에 대해 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-130">Read about [managing user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span>|

> [!NOTE]
>
> <span data-ttu-id="4a8dd-131"><sup>1</sup> Microsoft 365에서 완전히 호스트되는 사서함에 대한 전자 메일 앱만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-131"><sup>1</sup> You can only manage email apps for mailboxes that are hosted fully in Microsoft 365.</span></span> <span data-ttu-id="4a8dd-132">온 프레미스에서 호스트되는 사서함에 대한 전자 메일 앱을 관리하기 위해 이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-132">You cannot use this feature to manage email apps for mailboxes that are hosted on-premises.</span></span>