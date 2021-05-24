---
title: Exchange Online Protection(EOP) 개요
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection)가 독립 실행형 및 하이브리드 환경에서 어떻게 프레미스 전자 메일 조직을 보호할 수 있도록 하는지 알아보십시오.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624731"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="16e1f-103">Exchange Online Protection 개요</span><span class="sxs-lookup"><span data-stu-id="16e1f-103">Exchange Online Protection overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="16e1f-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="16e1f-104">**Applies to**</span></span>
- [<span data-ttu-id="16e1f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="16e1f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="16e1f-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="16e1f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="16e1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16e1f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="16e1f-108">Exchange Online Protection(EOP)는 스팸, 맬웨어 및 기타 전자 메일 위협으로부터 조직을 보호하는 데 도움이 되는 클라우드 기반 필터링 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-108">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam, malware, and other email threats.</span></span> <span data-ttu-id="16e1f-109">EOP는 사서함이 있는 모든 Microsoft 365 조직에 Exchange Online 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-109">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span>

<span data-ttu-id="16e1f-110">이 문서의 나머지부분에서는 EOP의 작동 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-110">The rest of this article explains how EOP works.</span></span>

> [!NOTE]
> <span data-ttu-id="16e1f-111">EOP는 자체적으로만 사용할 수 있으며, 하이브리드 환경에서는 사서함을 보호할 수 있으며, 하이브리드 환경에서도 EOP를 통해 사서함을 보호할 Exchange 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-111">EOP is also available by itself to protect on-premises mailboxes and in hybrid environments to protect on-premises Exchange mailboxes.</span></span> <span data-ttu-id="16e1f-112">자세한 내용은 독립 실행형 을 [Exchange Online Protection.](/exchange/standalone-eop/standaonline-eop)</span><span class="sxs-lookup"><span data-stu-id="16e1f-112">For more information, see [Standalone Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="16e1f-113">EOP의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="16e1f-113">How EOP works</span></span>

<span data-ttu-id="16e1f-114">EOP가 받는 전자 메일을 처리하는 방법을 확인하면 EOP의 작동 방식을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-114">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="정크 메일 또는 정크 메일 또는 최종 사용자 메일 배달에 대한 판결이 나기 전에 EOP, 연결, 맬웨어 방지, 메일 흐름 규칙 슬래시 정책 필터링 및 콘텐츠 필터링을 통해 전달되는 인터넷 또는 고객 피드백의 그래픽입니다.":::

- <span data-ttu-id="16e1f-116">들어오는 메시지가 EOP에 들어오면 처음에는 연결 필터링을 통과하여 보낸 사람 신뢰도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-116">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="16e1f-117">대부분의 스팸은 이 시점에서 중지된 후 EOP에서 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-117">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="16e1f-118">자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16e1f-118">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="16e1f-119">그런 다음 메시지에서 맬웨어를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-119">Then the message is inspected for malware.</span></span> <span data-ttu-id="16e1f-120">메시지 또는 첨부 파일에서 맬웨어가 발견된 경우 메시지는 관리자만 검사 저장소로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-120">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="16e1f-121">맬웨어 보호에 대한 자세한 내용은 [EOP의 맬웨어 방지 보호를 참조합니다.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="16e1f-121">To learn more about malware protection, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

- <span data-ttu-id="16e1f-122">메시지는 정책 필터링을 통해 계속 진행됩니다. 여기서 템플릿에서 만들거나 적용하는 사용자 지정 메일 흐름 규칙(전송 규칙)에 대해 메시지가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-122">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="16e1f-123">예를 들어 특정 보낸 사람으로부터 메일이 도착하면 관리자에게 알림을 보내는 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-123">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="16e1f-124">DLP(데이터 손실 방지) 검사도 이 시점(EXCHANGE ENTERPRISE CAL with Services)에도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-124">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="16e1f-125">다음으로, 메시지가 스팸, 피싱 또는 대량 전자 메일을 검사하는 스팸 방지 필터링을 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-125">Next, the message passes through anti-spam filtering where the message is check for spam, phishing, or bulk email.</span></span> <span data-ttu-id="16e1f-126">검색된 메시지는 다른 옵션 중에서 검지 또는 사용자의 정크 메일 폴더로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-126">Detected messages can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="16e1f-127">자세한 내용은 [Configure anti-spam policies](configure-your-spam-filter-policies.md) 및 [Configure anti-phishing policies을 참조하십시오.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="16e1f-127">For more information see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="16e1f-128">이러한 모든 보호 계층을 성공적으로 전달하는 메시지는 받는 사람에게 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-128">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="16e1f-129">자세한 내용은 전자 메일 보호의 순서 및 [우선 순위를 참조하세요.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="16e1f-129">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="16e1f-130">EOP 계획 및 사내 전자 메일 조직용 기능</span><span class="sxs-lookup"><span data-stu-id="16e1f-130">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="16e1f-131">사용 가능한 EOP 구독 계획은 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-131">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="16e1f-132">**EOP 독립 실행형: EOP에** 등록하여온-프레미스 전자 메일 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-132">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="16e1f-133">**Exchange Online EOP 기능:** Exchange Online(독립 실행형 또는 Microsoft 365의 일부분)를 포함하는 모든 구독은 EOP를 사용하여 Exchange Online 사서함을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-133">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="16e1f-134">**Exchange Enterprise CAL with Services:** Exchange CAL with Services 라이선스를 추가로 구입한 Exchange Enterprise 조직이 있는 경우 EOP는 포함된 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-134">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="16e1f-135">모든 EOP 구독 계획의 요구 사항, 중요한 제한 및 기능 가용성에 대한 자세한 내용은 Exchange Online Protection [서비스 설명을 참조하세요.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="16e1f-135">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="16e1f-136">사서함이 포함된 Microsoft 365 Office 365 구독이 있는 Exchange Online EOP가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-136">If you have a Microsoft 365 or Office 365 subscription that includes Exchange Online mailboxes, you have EOP.</span></span> <span data-ttu-id="16e1f-137">구독에서 EOP 보안 기능을 설정하는 단계 및 추가된 보안에 대한 정보는 Office 365 Microsoft Defender를 통해 위협으로부터 보호를 [참조하세요.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="16e1f-137">For steps to set up EOP security features in your subscription, and information on the added security a Microsoft Defender for Office 365 subscription can give you, see [protect against threats](protect-against-threats.md).</span></span> <span data-ttu-id="16e1f-138">설치에 대한 EOP 기능에 대한 권장 설정은 EOP 및 보안용 [Microsoft Defender에](recommended-settings-for-eop-and-office365.md)대한 권장 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-138">The recommended settings for EOP feature for setup can be found in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="16e1f-139">전자 메일 조직에 대해 EOP 설정</span><span class="sxs-lookup"><span data-stu-id="16e1f-139">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="16e1f-p108">EOP는 간단하게 설정할 수 있으며, 특히 준수 규칙이 많지 않은 소규모 조직의 경우에는 더욱 그렇습니다. 그러나 도메인이 여러 개이거나 사용자 지정 준수 규칙 또는 하이브리드 메일 흐름을 사용하는 대규모 조직의 경우에는 EOP 설정에 더 많은 시간과 계획이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-p108">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="16e1f-142">EOP를 이미 구입한 경우 [EOP 서비스 설정](/exchange/standalone-eop/set-up-your-eop-service)을 참조하여 메시징 환경을 보호하도록 EOP를 구성하는 데 필요한 모든 단계를 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="16e1f-142">If you've already purchased EOP, see [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="16e1f-143">EOP 데이터 센터</span><span class="sxs-lookup"><span data-stu-id="16e1f-143">EOP datacenters</span></span>

<span data-ttu-id="16e1f-144">EOP는 최고 수준의 사용 가능성을 제공하도록 설계된 전 세계 데이터 센터 네트워크에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-144">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="16e1f-145">예를 들어 데이터 센터를 사용할 수 없더라도 서비스 중단 없이 전자 메일 메시지가 다른 데이터 센터에 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-145">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="16e1f-146">각 데이터 센터의 서버는 사용자 대신 메시지를 수락하여 조직과 인터넷을 분리하는 계층을 제공함으로써 서버에 대한 부하를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-146">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="16e1f-147">이처럼 가용성이 뛰어난 네트워크를 통해 Microsoft는 전자 메일이 제때에 조직으로 배달되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-147">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="16e1f-p110">EOP는 특정 지역 내에서만 데이터 센터 간 부하 분산을 수행합니다. 단일 지역에서 프로비전되는 경우에는 해당 영역에 대한 메일 라우팅을 사용하여 모든 메시지가 처리됩니다. 다음 목록에는 EOP 데이터 센터에 대한 영역 메일 라우팅의 작동 방식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-p110">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="16e1f-151">EMEA(유럽, 중동 및 아프리카)에서는 모든 Exchange Online 사서함이 EMEA 데이터 센터에 있으며 모든 메시지가 EOP 필터링용으로 EMEA 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-151">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
- <span data-ttu-id="16e1f-152">APAC(Asia-Pacific)에서 모든 Exchange Online 사서함은 APAC 데이터 센터에 있으며 메시지는 현재 EOP 필터링을 위해 APAC 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-152">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>
- <span data-ttu-id="16e1f-153">미국에서는 서비스가 다음 위치에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-153">In the Americas, services are distributed in the following locations:</span></span>
  - <span data-ttu-id="16e1f-154">남미: Exchange Online 사서함은 브라질과 칠레의 데이터 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-154">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="16e1f-155">모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-155">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="16e1f-156">Quarantined messages are stored in the datacenter where the tenant is located.</span><span class="sxs-lookup"><span data-stu-id="16e1f-156">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
  - <span data-ttu-id="16e1f-157">캐나다: Exchange Online 사서함은 캐나다의 데이터 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-157">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="16e1f-158">모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-158">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="16e1f-159">Quarantined messages are stored in the datacenter where the tenant is located.</span><span class="sxs-lookup"><span data-stu-id="16e1f-159">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
  - <span data-ttu-id="16e1f-160">미국: Exchange Online 사서함은 미국 데이터 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-160">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="16e1f-161">모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-161">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="16e1f-162">Quarantined messages are stored in the datacenter where the tenant is located.</span><span class="sxs-lookup"><span data-stu-id="16e1f-162">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
- <span data-ttu-id="16e1f-163">GCC(정부 커뮤니티 클라우드)의 경우에는 모든 Exchange Online 사서함이 미국 데이터 센터에 있으며 모든 메시지는 EOP 필터링용으로 미국 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-163">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="16e1f-164">관리자를 위한 EOP 도움말</span><span class="sxs-lookup"><span data-stu-id="16e1f-164">EOP Help for admins</span></span>

<span data-ttu-id="16e1f-165">EOP 관리자의 도움말 내용은 다음과 같은 최상위 범주로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-165">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="16e1f-166">[Office 365 관리자용 Microsoft Defender에 대해 EOP, 1일차](protect-against-threats.md)구성: Microsoft Defender의 핵심에서 EOP 보호 및 검색 Office 365.</span><span class="sxs-lookup"><span data-stu-id="16e1f-166">[Configure EOP, Day 1, for Microsoft Defender for Office 365 admins](protect-against-threats.md): Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="16e1f-167">[EOP 기능: EOP에서](eop-features.md)사용할 수 있는 기능 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-167">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="16e1f-168">[EOP 서비스](/exchange/standalone-eop/set-up-your-eop-service)설정: EOP 서비스를 설정하는 단계와 추가 정보에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-168">[Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="16e1f-169">[Google Postini, Barracuda Spam and Virus Firewall 또는 Cisco IronPort에서 EOP로](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)전환: 다른 전자 메일 보호 제품에서 EOP로 전환하는 프로세스에 대해 설명</span><span class="sxs-lookup"><span data-stu-id="16e1f-169">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="16e1f-170">[독립 실행형 EOP에서](/exchange/standalone-eop/manage-recipients-in-eop)받는 사람 관리: 독립 실행형 EOP에서 메일 사용자 및 그룹을 관리하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-170">[Manage recipients in standalone EOP](/exchange/standalone-eop/manage-recipients-in-eop): Describes how to manage mail users and groups in standalone EOP.</span></span>

- <span data-ttu-id="16e1f-171">[EOP의](mail-flow-in-eop.md)메일 흐름: 커넥터를 사용하여 사용자 지정 메일 흐름 시나리오를 구성하는 방법, 서비스에 연결된 도메인을 관리하는 방법 및 DBEB(디렉터리 기반 Edge 차단) 기능을 사용하도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-171">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="16e1f-172">[EOP 및 Office 365 보안용 Microsoft Defender에](recommended-settings-for-eop-and-office365.md)대한 권장 설정: 서비스를 설정하고 프로비전한 후의 권장 구성 설정 및 고려 사항을 설명</span><span class="sxs-lookup"><span data-stu-id="16e1f-172">[Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="16e1f-173">[Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)감사 보고서: 감사 보고서를 사용하여 서비스의 구성 변경 내용을 추적하는 방법에 대해 설명</span><span class="sxs-lookup"><span data-stu-id="16e1f-173">[Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="16e1f-174">[EOP의](anti-spam-and-anti-malware-protection.md)스팸 방지 및 맬웨어 방지 보호: 스팸 필터링 및 맬웨어 필터링에 대해 설명하고 조직의 요구 사항을 가장 잘 충족할 수 있도록 사용자 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-174">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="16e1f-175">또한 관리자 및 최종 사용자가 격리된 메시지에 대해 수행할 수 있는 작업도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-175">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="16e1f-176">[Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)보고 및 메시지 추적 : 사용 가능한 보고서 및 문제 해결 도구에 대해 설명</span><span class="sxs-lookup"><span data-stu-id="16e1f-176">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="16e1f-177">[Exchange](/exchange/exchange-admin-center) [EOP의](/exchange/standalone-eop/exchange-admin-center-eop)Exchange Online 또는 Exchange 관리 센터: 관련 EOP 기능을 관리하기 위해 EAC(Exchange 관리 센터) 관리 인터페이스를 액세스하고 탐색하는 방법에 대해 설명</span><span class="sxs-lookup"><span data-stu-id="16e1f-177">[Exchange admin center in Exchange Online](/exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](/exchange/standalone-eop/exchange-admin-center-eop): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage related EOP features.</span></span>

- <span data-ttu-id="16e1f-178">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): 명령줄에서 EOP 서비스를 관리할 수 있는 원격 PowerShell에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-178">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="16e1f-179">[EOP에 대한 도움말 및 지원](help-and-support-for-eop.md) 도움말 및 기술 지원 서비스를 구하는 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16e1f-179">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>