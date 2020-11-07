---
title: Office 365에서 기본적으로 보안
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 조직의 전자 메일 보안 보고서를 찾아서 사용 하는 방법에 대해 알아봅니다. 보안 & 준수 센터에서 전자 메일 보안 보고서를 사용할 수 있습니다.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944546"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="d9df9-104">Office 365에서 기본적으로 보안</span><span class="sxs-lookup"><span data-stu-id="d9df9-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d9df9-105">"기본적으로 보안"은 최대한 안전한 기본 설정을 정의 하는 데 사용 되는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="d9df9-106">그러나 보안을 생산성과 균형 있게 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="d9df9-107">여기에는 다음과 같은 분산이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-107">This can include balancing across:</span></span>
- <span data-ttu-id="d9df9-108">유용성: 설정이 사용자 생산성을 유지 하는 방식으로 제공 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="d9df9-109">위험: 보안은 중요 한 작업을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="d9df9-110">레거시 설정: 이전 제품 및 기능에 대 한 일부 구성은 새로운 최신 설정이 향상 되더라도 비즈니스 상의 이유로 유지 관리 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="d9df9-111">Exchange Online 사서함이 있는 Microsoft 365 조직은 EOP (Exchange Online Protection)를 통해 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d9df9-112">이 보호에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-112">This  protection includes:</span></span>
1. <span data-ttu-id="d9df9-113">의심 스러운 맬웨어가 있는 전자 메일은 자동으로 격리 되 고 받는 사람에 게 알림이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="d9df9-114">[EOP에서 맬웨어 방지 정책 구성을](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9df9-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="d9df9-115">"높은 신뢰도"로 식별 된 피싱 전자 메일은 스팸 방지 정책 작업에 따라 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="d9df9-116">[EOP에서 스팸 방지 정책 구성을](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9df9-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="d9df9-117">Microsoft는 고객에 게 기본적으로 보안을 유지 하려고 하기 때문에 일부 테 넌 트 재정의는 맬웨어 또는 높은 신뢰도 피싱 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="d9df9-118">이러한 재정의에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-118">These overrides include:</span></span>
- <span data-ttu-id="d9df9-119">허용 된 보낸 사람 목록 또는 허용 된 도메인 목록 (스팸 방지 정책)</span><span class="sxs-lookup"><span data-stu-id="d9df9-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="d9df9-120">Outlook 수신 허용-보낸 사람</span><span class="sxs-lookup"><span data-stu-id="d9df9-120">Outlook Safe senders</span></span>
- <span data-ttu-id="d9df9-121">IP 허용 목록 (연결 필터링)</span><span class="sxs-lookup"><span data-stu-id="d9df9-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="d9df9-122">이러한 재정의에 대 한 자세한 내용은 [수신 허용-보낸 사람 목록 만들기](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="d9df9-123">기본적으로 보안은 설정 또는 해제할 수 있는 설정이 아니며, 필터링이 상자에서 작동 하 여 위험할 수도 있고 원치 않는 메시지를 사서함에서 제외 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="d9df9-124">맬웨어 및 높은 신뢰도 피싱을 격리로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="d9df9-125">관리자만이 맬웨어 또는 높은 자신감 피싱 메일로 격리 된 메시지를 관리할 수 있으며, Microsoft에 가양성을 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="d9df9-126">자세한 내용은 [격리 된 메시지 및 파일을 관리자 권한으로 EOP에서 관리](manage-quarantined-messages-and-files.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9df9-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="d9df9-127">예외</span><span class="sxs-lookup"><span data-stu-id="d9df9-127">Exceptions</span></span>
<span data-ttu-id="d9df9-128">모든 필터를 무시 하는 재정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="d9df9-129">Exchange 전송 규칙 (ETR)/메일 흐름 규칙</span><span class="sxs-lookup"><span data-stu-id="d9df9-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="d9df9-130">메일 흐름 규칙을 사용 하 여 EOP의 메시지에 SCL (스팸 지 수)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="d9df9-131">테 넌 트 허용/차단 목록: 테 넌 트 허용/차단 목록에서 Url 및 파일을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="d9df9-132">이러한 유형의 재정의는 다음과 같은 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="d9df9-133">피싱 시뮬레이션: 시뮬레이션 된 공격은 실제 공격이 조직에 영향을 주는 이전에 취약 한 사용자를 식별 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="d9df9-134">Security/SecOps 사서함: 보안 팀에서 필터링 되지 않은 메시지를 가져오는 데 사용 하는 전용 사서함입니다 (정상 및 불량).</span><span class="sxs-lookup"><span data-stu-id="d9df9-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="d9df9-135">그런 다음 팀이 악성 콘텐츠가 포함 되어 있는지 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="d9df9-136">타사 필터: 타사 필터는 메일 필터링을 관리 하기 때문에 제 3 자 공급 업체가 EOP (SCL =-1)를 해제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="d9df9-137">Office 365 용 Defender에는 EOP as EOP이 필요 하므로이 기능을 해제 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="d9df9-138">가양성: 여전히 [관리자 제출을 통해](admin-submission.md)Microsoft가 분석 중인 특정 메시지를 허용 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="d9df9-139">모든 재정의와 마찬가지로 임시적으로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9df9-139">As with all overrides, it is recommended that they are temporary.</span></span>
