---
title: 격리 된 전자 메일 메시지
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
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 관리자는 잠재적으로 위험한 또는 원치 않는 메시지를 포함 하는 EOP (Exchange Online Protection)의 격리에 대해 자세히 알아볼 수 있습니다.
ms.openlocfilehash: 74f420dd1d37acb9949aae2e1f01688c44e5b1bc
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430874"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="4e9cc-103">EOP에서 격리 된 전자 메일 메시지</span><span class="sxs-lookup"><span data-stu-id="4e9cc-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4e9cc-104">Exchange online 사서함이 없는 Microsoft 365 조직의 EOP (독립 실행형 Exchange Online 보호) 조직에서 격리를 사용 하 여 잠재적으로 위험할 수도 있고 원치 않는 메시지를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="4e9cc-105">맬웨어를 포함 하 *는 첨부 파일이 있는 경우* 맬웨어 방지 정책은 메시지를 자동으로 격리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="4e9cc-106">자세한 내용은 [EOP에서 맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="4e9cc-107">기본적으로 스팸 방지 정책은 피싱 메시지를 격리 하 고 사용자의 정크 메일 폴더에 스팸 및 대량 전자 메일 메시지를 배달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="4e9cc-108">그러나 스팸 방지 정책을 만들고 사용자 지정 하 여 스팸을 격리 하 고 대량 전자 메일 메시지를 격리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="4e9cc-109">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="4e9cc-110">사용자와 관리자가 격리 된 메시지를 사용 하 여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="4e9cc-111">관리자는 모든 사용자에 대해 격리 된 모든 유형의 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="4e9cc-112">관리자만이 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)의 결과로 격리 된 메시지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="4e9cc-113">자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="4e9cc-114">메시지가 스팸으로, 대량 전자 메일 또는 (4 월 2020) 피싱 메일로 격리 된 경우 사용자는 격리 된 메시지를 사용 하 여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="4e9cc-115">자세한 내용은 [EOP의 사용자로 격리 된 메시지 찾기 및 릴리스](find-and-release-quarantined-messages-as-a-user.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="4e9cc-116">사용자가 격리 된 자체 피싱 메시지를 관리 하지 못하도록 하기 위해 관리자는 스팸 방지 정책에서 **피싱 전자 메일** 필터링 결과에 대해 다른 작업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="4e9cc-117">자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="4e9cc-118">관리자 및 사용자는 차단 되는 Microsoft에 가양성을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="4e9cc-119">격리에 대 한 자세한 내용은 [격리 FAQ](quarantine-faq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e9cc-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
