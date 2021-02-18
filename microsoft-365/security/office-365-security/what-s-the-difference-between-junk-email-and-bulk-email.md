---
title: 정크 메일과 대량 전자 &apos; 메일의 차이점은 무엇입니까?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 정크 메일(스팸)과 대량 전자 메일(회색 메일)의 차이점에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290648"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="e950a-103">EOP에서 정크 메일과 대량 전자 메일의 차이점은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="e950a-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e950a-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="e950a-104">**Applies to**</span></span>
- [<span data-ttu-id="e950a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e950a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e950a-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="e950a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e950a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e950a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e950a-108">Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 고객은 "정크 메일과 대량 전자 메일의 차이점"을 물어보는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="e950a-109">이 항목에서는 차이점에 대해 설명하고 EOP에서 사용할 수 있는 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="e950a-110">**정크 메일은** 원치 않는 보편적으로 원치 않는 메시지(올바르게 식별된 경우)인 스팸입니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="e950a-111">기본적으로 EOP는 원본 전자 메일 서버의 신뢰도에 따라 스팸을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="e950a-112">메시지가 원본 IP 검사를 통과하면 스팸 필터링으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="e950a-113">메시지가 스팸 필터링을 통해 스팸으로 분류된 경우 메시지는 기본적으로 의도한 받는 사람에게 배달되어 정크 메일 폴더로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="e950a-114">스팸 필터링 판정에 대해 수행할 작업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="e950a-115">자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e950a-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="e950a-116">스팸 필터링 결과와 동의하지 않는 경우 Microsoft에 보고서 메시지 및 파일에 설명된 바와 같이 스팸 또는 스팸이 아닌 것으로 생각되는 메시지를 Microsoft에 여러 가지 방법으로 보고할 수 [있습니다.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e950a-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="e950a-117">**대량 전자** 메일(회색 _메일)은_ 분류하기가 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="e950a-118">스팸은 지속적인 위협인 반면 대량 전자 메일은 일회성 광고 또는 마케팅 메시지인 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="e950a-119">일부 사용자는 대량 전자 메일 메시지(실제로는 이를 받기 위해 고의로 등록한 경우)를 원하고 다른 사용자는 대량 전자 메일을 스팸으로 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="e950a-120">예를 들어 일부 사용자는 Contoso Corporation에서 광고 메시지를 받거나 사이버 보안에 대한 예정된 회의에 대한 초대를 받으고 다른 사용자는 이러한 동일한 메시지를 스팸으로 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="e950a-121">대량 전자 메일이 식별되는 방법에 대한 자세한 내용은 [EOP의 BCL(대량 불만 수준)을 참조하세요.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="e950a-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="e950a-122">대량 전자 메일을 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="e950a-122">How to manage bulk email</span></span>

<span data-ttu-id="e950a-123">대량 전자 메일에 대한 혼합 반응 때문에 모든 조직에 적용되는 범용 지침이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="e950a-124">스팸 방지 정책에는 대량 전자 메일을 스팸으로 식별하는 데 사용되는 기본 BCL 임계값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="e950a-125">관리자는 임계값을 늘리거나 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="e950a-126">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e950a-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="e950a-127">[EOP에서 스팸 방지 정책을 구성합니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e950a-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="e950a-128">EOP 스팸 방지 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e950a-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="e950a-129">간과하기 쉬운 또 다른 옵션: 사용자가 대량 전자 메일 수신에 대해 불만을 표시하지만 EOP에서 스팸 필터링을 통과하는 메시지를 보낸 사람이 보낸 메시지인 경우 사용자는 대량 전자 메일 메시지에서 구독 취소 옵션을 확인하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e950a-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
