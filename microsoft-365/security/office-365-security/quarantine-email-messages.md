---
title: 격리된 전자 메일 메시지
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 위험할 수 있거나 원치 않는 메시지를 보유하는 격리 방법에 대해 알아질 수 있습니다.
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826804"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="a17d5-103">EOP에서 격리된 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="a17d5-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="a17d5-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 위험할 가능성이 있거나 원치 않는 메시지를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="a17d5-105">맬웨어 방지 정책은 첨부 파일이 맬웨어를 포함하는지를 *확인하는* 경우 자동으로 메시지를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="a17d5-106">자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a17d5-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="a17d5-107">기본적으로 스팸 방지 정책은 피싱 메시지를 격리하고 사용자의 정크 메일 폴더로 스팸 및 대량 전자 메일 메시지를 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="a17d5-108">그러나 스팸 방지 정책을 만들고 사용자 지정하여 스팸 및 대량 전자 메일 메시지를 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="a17d5-109">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a17d5-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a17d5-110">사용자와 관리자는 격리된 메시지를 사용하여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="a17d5-111">관리자는 모든 사용자에 대해 모든 유형의 격리된 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="a17d5-112">관리자만 맬웨어로 격리된 메시지, 높은 신뢰도의 피싱 또는 메일 흐름 규칙(전송 규칙이라고도 함)의 결과로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a17d5-113">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a17d5-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="a17d5-114">사용자는 메시지가 스팸, 대량 전자 메일 또는 (2020년 4월에 의해) 피싱으로 격리된 경우 받는 사람인 격리된 메시지로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="a17d5-115">자세한 내용은 [EOP에서 사용자로 격리된 메시지 찾기 및 릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="a17d5-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="a17d5-116">사용자가 자신의 격리된 피싱 메시지를 관리하지 못하도록 하기 위해 관리자는 스팸 방지 정책의 **피싱 전자** 메일 필터링 결과에 대해 다른 작업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="a17d5-117">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a17d5-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="a17d5-118">관리자 및 사용자는 격리된 상태에서 가양성을 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17d5-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="a17d5-119">격리에 대한 자세한 내용은 격리 [FAQ를 참조하세요.](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="a17d5-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
