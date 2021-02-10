---
title: Quarantined email messages
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 관리자는 위험할 수 있는 메시지나 원치 않는 메시지를 보유하는 EOP(Exchange Online Protection)의 검역에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b111ea0d07453ef4280ec9e57247c8215420074
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167410"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="3faca-103">EOP에서 Quarantined email messages(EOP에서 전자 메일 메시지)</span><span class="sxs-lookup"><span data-stu-id="3faca-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3faca-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3faca-104">**Applies to**</span></span>
- [<span data-ttu-id="3faca-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3faca-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
-   [<span data-ttu-id="3faca-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="3faca-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
-   [<span data-ttu-id="3faca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3faca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3faca-108">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 위험하거나 원치 않는 메시지를 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="3faca-109">맬웨어 방지 정책은 맬웨어가 포함된 첨부 파일이 있는 경우 메시지를 자동으로 차단합니다. </span><span class="sxs-lookup"><span data-stu-id="3faca-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="3faca-110">자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을 참조하세요.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3faca-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="3faca-111">기본적으로 스팸 방지 정책은 피싱 메시지를 차단하고 스팸 및 대량 전자 메일 메시지를 사용자의 정크 메일 폴더로 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="3faca-112">그러나 스팸 방지 정책을 만들고 사용자 지정하여 스팸 및 대량 전자 메일 메시지를 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="3faca-113">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3faca-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3faca-114">사용자와 관리자는 모두 다음을 통해 분리된 메시지로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="3faca-115">관리자는 모든 사용자에 대해 모든 유형의 고지된 메시지로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="3faca-116">관리자만 맬웨어, 높은 신뢰도 피싱으로 인해 또는 메일 흐름 규칙(전송 규칙)의 결과로 탐지된 메시지로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="3faca-117">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3faca-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="3faca-118">사용자는 메시지가 스팸, 대량 전자 메일 또는 (2020년 4월 현재) 피싱으로 스팸으로 분류된 경우 받는 사람인 분리된 메시지로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="3faca-119">자세한 내용은 EOP에서 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="3faca-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="3faca-120">사용자가 자체적으로 분리된 피싱 메시지를 관리하지 못하도록 관리자는 스팸 방지 정책에서  피싱 전자 메일 필터링 판정에 대해 다른 작업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="3faca-121">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3faca-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="3faca-122">관리자와 사용자는 Microsoft에 가짓 긍정을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faca-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="3faca-123">자세한 내용은 [Quarantine FAQ를 참조하십시오.](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="3faca-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
