---
title: 격리 FAQ
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 이 항목에서는 호스팅되는 격리에 대한 질문과 대답을 제공합니다.
ms.openlocfilehash: b4112bf785a6ee2f4c833ab08d2c199388585093
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598665"
---
# <a name="quarantine-faq"></a><span data-ttu-id="9da54-103">격리 FAQ</span><span class="sxs-lookup"><span data-stu-id="9da54-103">Quarantine FAQ</span></span>

<span data-ttu-id="9da54-p101">이 항목에서는 호스팅되는 격리에 대한 질문과 대답을 제공합니다. 대답은 Microsoft Exchange Online 및 Exchange Online Protection 고객에게 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>

 <span data-ttu-id="9da54-106">**Q. 격리에서 맬웨어 격리 메시지를 관리 하려면 어떻게 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="9da54-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>

<span data-ttu-id="9da54-107">격리로 전송 된 메시지를 보고 작업 하려면 맬웨어를 포함 하므로 보안 & 준수 센터를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-107">You need to use the Security & Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware.</span></span> <span data-ttu-id="9da54-108">자세한 내용은 [Office 365에서 전자 메일 메시지 격리](quarantine-email-messages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9da54-108">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

 <span data-ttu-id="9da54-109">**질문. 스팸으로 격리된 메시지를 격리로 보내도록 서비스를 구성하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="9da54-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>

<span data-ttu-id="9da54-110">대답.</span><span class="sxs-lookup"><span data-stu-id="9da54-110">A.</span></span> <span data-ttu-id="9da54-111">기본적으로 콘텐츠가 필터링된 메시지는 받는 사람의 정크 메일 폴더로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-111">By default, content-filtered messages are sent to the recipients Junk Email folder.</span></span> <span data-ttu-id="9da54-112">그러나 관리자는 스팸으로 격리된 메시지를 격리로 대신 보내도록 콘텐츠 필터 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-112">However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead.</span></span> <span data-ttu-id="9da54-113">콘텐츠가 필터링 된 메시지에 대해 수행할 수 있는 다양 한 작업에 대 한 자세한 내용은 [스팸 필터 정책 구성을](configure-your-spam-filter-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9da54-113">For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="9da54-114">**질문. 서비스에서 스팸으로 격리된 메시지를 관리자 및 최종 사용자가 관리할 수 있는 기능을 제공합니까?**</span><span class="sxs-lookup"><span data-stu-id="9da54-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>

<span data-ttu-id="9da54-115">대답.</span><span class="sxs-lookup"><span data-stu-id="9da54-115">A.</span></span> <span data-ttu-id="9da54-116">관리자는 SCC (보안 및 준수 센터)에서 격리 된 모든 전자 메일 메시지에 대 한 세부 정보를 검색 하 고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-116">As an admin, you can search for and view details about all quarantined email messages in the Security and Compliance Center (SCC).</span></span> <span data-ttu-id="9da54-117">메시지를 찾은 후 특정 사용자에게 릴리스하고 원하는 경우 Microsoft 스팸 분석 팀에 가양성(정크 메일 아님)으로 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-117">After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="9da54-118">자세한 내용은 [Office 365에서 격리 된 메시지 및 파일 관리로 관리자](manage-quarantined-messages-and-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9da54-118">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="9da54-119">최종 사용자는 다음을 통해 스팸 격리된 메시지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-119">As an end user, you can manage your own spam-quarantined messages via:</span></span>

- <span data-ttu-id="9da54-120">스팸 격리 사용자 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-120">The spam quarantine user interface.</span></span> <span data-ttu-id="9da54-121">자세한 내용은 [Office 365의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9da54-121">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

 <span data-ttu-id="9da54-122">**Q. 최종 사용자의 격리에 대 한 액세스 권한을 부여 하려면 어떻게 해야 합니까?**</span><span class="sxs-lookup"><span data-stu-id="9da54-122">**Q. How do I grant access to quarantine for my end users?**</span></span>

<span data-ttu-id="9da54-123">대답.</span><span class="sxs-lookup"><span data-stu-id="9da54-123">A.</span></span> <span data-ttu-id="9da54-124">최종 사용자 스팸 격리에 액세스 하려면 최종 사용자에 게 유효한 Office 365 사용자 ID 및 암호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-124">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="9da54-125">온-프레미스 사서함을 보호 하는 EOP 고객은 디렉터리 동기화 또는 EAC를 통해 만든 유효한 전자 메일 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-125">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="9da54-126">사용자를 관리 하는 방법에 대 한 자세한 내용은 EOP 관리자가 [EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-126">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="9da54-127">EOP 독립 실행형 고객의 경우 디렉터리 동기화 및 디렉터리 기반 Edge 차단을 사용 하는 것이 좋습니다. 자세한 내용은 [디렉터리 기반 Edge 차단을 사용 하 여 잘못 된 받는 사람에 게 보낸 메시지 거부](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9da54-127">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

 <span data-ttu-id="9da54-128">**Q. 사용자가 격리에서 액세스할 수 있는 메시지는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="9da54-128">**Q. What messages can end users access in quarantine?**</span></span>

<span data-ttu-id="9da54-129">대답.</span><span class="sxs-lookup"><span data-stu-id="9da54-129">A.</span></span> <span data-ttu-id="9da54-130">최종 사용자는 자신의 피싱, 스팸 및 대량 메일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-130">End users can access their own phish, spam, and bulk mail.</span></span> <span data-ttu-id="9da54-131">최종 사용자는 자신의 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)과 일치 하는 메시지에 액세스할 수 없습니다. 관리자 격리 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-131">End users can't access their own malware, high confidence phish, or messages that matched a mail flow rule (also known as a transport rule); these are only available in the admin quarantine.</span></span> 

 <span data-ttu-id="9da54-132">**질문. 메시지는 얼마 동안 격리에 보관됩니까?**</span><span class="sxs-lookup"><span data-stu-id="9da54-132">**Q. For how long are messages kept in the quarantine?**</span></span>

<span data-ttu-id="9da54-133">대답.</span><span class="sxs-lookup"><span data-stu-id="9da54-133">A.</span></span> <span data-ttu-id="9da54-134">기본적으로 스팸 격리 메시지는 30 일 동안 격리 된 상태로 유지 되지만, 메일 흐름 규칙과 일치 하는 격리 된 메시지는 기본 콘텐츠 필터 정책에 설정 된 보존 기간을 기준으로 최대 30 일 동안 격리에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-134">By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for up to 30 days based on the retention period set in your default content filter policy.</span></span> <span data-ttu-id="9da54-135">이 기간 후에 메시지는 삭제되며 검색할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-135">After this period of time the messages are deleted and are not retrievable.</span></span> <span data-ttu-id="9da54-136">메일 흐름 규칙과 일치 하는 격리 된 메시지의 보존 기간은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-136">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="9da54-137">그렇지만 스팸 격리 메시지의 보존 기간은 콘텐츠 필터 정책의 **스팸 보존 기간(일)** 설정을 통해 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-137">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="9da54-138">자세한 내용은 [스팸 필터 정책 구성을](configure-your-spam-filter-policies.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9da54-138">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="9da54-139">**Q. 한 번에 2개 이상의 격리된 메시지를 해제하거나 보고할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="9da54-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>

<span data-ttu-id="9da54-140">A.</span><span class="sxs-lookup"><span data-stu-id="9da54-140">A.</span></span> <span data-ttu-id="9da54-141">예, 격리 포털에서 한 번에 최대 100 개의 메시지를 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-141">Yes, up to 100 messages can be released at one time in the Quarantine portal.</span></span> <span data-ttu-id="9da54-142">또한 관리자는이 작업을 수행 하는 원격 Windows PowerShell 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-142">In addition, admins can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="9da54-143">[Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet을 사용하여 메시지를 검색하고 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet을 사용하여 메시지를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-143">Use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for messages, and the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet to release them.</span></span>

 <span data-ttu-id="9da54-144">**질문. 격리된 메시지 검색 시 와일드카드가 지원됩니까? 특정 도메인에 대해 격리된 메시지를 검색할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="9da54-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>

<span data-ttu-id="9da54-p110">대답. Exchange 관리 센터에서 검색 조건을 지정할 때는 와일드카드가 지원되지 않습니다. 예를 들어 보낸 사람을 검색할 때는 전체 전자 메일 주소를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>

<span data-ttu-id="9da54-148">원격 Windows PowerShell을 통해 관리자는 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet을 지정하여 contoso.com과 같은 특정 도메인에 대해 격리된 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="9da54-p111">이 결과는 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet으로 전달될 수 있습니다. 메시지를 모든 받는 사람에게 릴리스하려면 -ReleaseToAll 매개 변수를 포함합니다. 메시지를 릴리스한 후에는 다시 릴리스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9da54-p111">The results can be passed to the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
