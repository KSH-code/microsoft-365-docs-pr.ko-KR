---
title: EOP(Exchange Online Protection) 개요
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
description: EOP(Exchange Online Protection)가 독립 실행형 및 하이브리드 환경에서 전자 메일 조직을 보호하는 데 어떻게 도움이 될 수 있는지 알아보십시오.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b84ac26333163caec6117cf042044b9bbfad0a4f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165466"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="e53bb-103">Exchange Online Protection 개요</span><span class="sxs-lookup"><span data-stu-id="e53bb-103">Exchange Online Protection overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e53bb-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="e53bb-104">**Applies to**</span></span>
- [<span data-ttu-id="e53bb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e53bb-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
-    [<span data-ttu-id="e53bb-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="e53bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
-    [<span data-ttu-id="e53bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e53bb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="e53bb-108">EOP(Exchange Online Protection)는 스팸 및 맬웨어로부터 조직을 보호하는 데 도움이 되는 클라우드 기반 필터링 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-108">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="e53bb-109">EOP는 Exchange Online 사서함이 있는 모든 Microsoft 365 조직에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-109">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="e53bb-110">그러나 EOP는 다음과 같은 On-premises 시나리오에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-110">However, EOP is also available in the following on-premises scenarios:</span></span>

- <span data-ttu-id="e53bb-111">**독립 실행형** 시나리오: EOP는 클라우드 기반 전자 메일 보호를 제공합니다. EOP는 다른 모든온-프레미스 SMTP 전자 메일 솔루션에 대해 클라우드 기반 전자 메일 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-111">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="e53bb-112">**하이브리드 배포에서**: 전자 메일 환경을 보호하고, 전자 메일 사서함과 클라우드 사서함이 혼합되어 있는 경우 메일 라우팅을 제어하도록 EOP를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-112">**In a hybrid deployment**: EOP can be configured to protect your email environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

<span data-ttu-id="e53bb-113">이러한 시나리오에서 EOP는 전자 메일 환경의 관리를 간소화하고 온-프레미스 하드웨어 및 소프트웨어 유지 관리 시의 많은 부담을 덜어 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-113">In these scenarios, EOP can simplify the management of your email environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="e53bb-114">이 항목의 나머지에서는 EOP가 독립 실행형 및 하이브리드 환경에서 작동하는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-114">The rest of this topic explains how EOP works in standalone and hybrid environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="e53bb-115">EOP의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="e53bb-115">How EOP works</span></span>

<span data-ttu-id="e53bb-116">EOP가 받는 전자 메일을 처리하는 방법을 확인하면 EOP의 작동 방식을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-116">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="EOP로 전달되는 인터넷 또는 고객 의견 및 연결, 맬웨어 방지, 메일 흐름 규칙-슬래시 정책 필터링 및 콘텐츠 필터링을 통해 정크 메일 또는 차단 또는 최종 사용자 메일 배달이 판결되기 전에 전송되는 전자 메일의 그래픽입니다.":::

- <span data-ttu-id="e53bb-118">들어오는 메시지가 EOP에 들어오면 처음에는 연결 필터링을 통해 전달되어 보낸 사람 신뢰도도 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-118">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="e53bb-119">대부분의 스팸은 이 시점에서 중지된 후 EOP에서 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-119">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="e53bb-120">자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e53bb-120">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="e53bb-121">그런 다음 메시지에서 맬웨어의 징후를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-121">Then the message is inspected for signs of malware.</span></span> <span data-ttu-id="e53bb-122">메시지 또는 첨부 파일에서 맬웨어가 발견된 경우 메시지는 관리자 전용 저장소로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-122">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="e53bb-123">맬웨어 방지 구성에 대한 자세한 내용은 여기에서 자세히 [알아보십시오.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e53bb-123">You can learn more about configuring anti-malware [here](configure-anti-malware-policies.md).</span></span>

- <span data-ttu-id="e53bb-124">메시지는 정책 필터링을 계속 진행하여 템플릿에서 만들거나 적용하는 사용자 지정 메일 흐름 규칙(전송 규칙)에 대해 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-124">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="e53bb-125">예를 들어 특정 보낸 사람으로부터 메일이 도착할 때 관리자에게 알림을 보내는 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-125">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="e53bb-126">DLP(데이터 손실 방지) 검사도 이 시점에서(Exchange Enterprise CAL with Services)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-126">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="e53bb-127">다음으로 메시지는 콘텐츠 필터링(스팸 방지라고도 합니다)을 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-127">Next, the message passes through content filtering (also known as Anti-spam).</span></span> <span data-ttu-id="e53bb-128">이 필터에서 스팸 또는 피싱으로 확인되는 메시지는 여러 옵션 중에서 스팸 또는 피싱을 차단하거나 사용자의 정크 메일 폴더로 보낼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="e53bb-128">A message that this filter determines to be spam *or phish* can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="e53bb-129">자세한 내용은 스팸 [방지](configure-your-spam-filter-policies.md) 정책 구성 및 피싱 방지 [정책 구성을 참조하십시오.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="e53bb-129">For more information see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="e53bb-130">이러한 모든 보호 계층을 성공적으로 전달하는 모든 메시지는 받는 사람에게 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-130">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="e53bb-131">자세한 내용은 전자 메일 보호의 [순서 및 우선 순위를 참조하세요.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="e53bb-131">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="e53bb-132">EOP 계획 및 기능-프레미스 전자 메일 조직</span><span class="sxs-lookup"><span data-stu-id="e53bb-132">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="e53bb-133">사용 가능한 EOP 구독 계획은 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-133">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="e53bb-134">**EOP 독립 실행형 : EOP에** 등록하여온-프레미스 전자 메일 조직을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-134">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="e53bb-135">**Exchange Online의 EOP** 기능: Exchange Online을 포함하는 모든 구독(독립 실행형 또는 Microsoft 365의 일부)은 EOP를 사용하여 Exchange Online 사서함을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-135">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="e53bb-136">**Exchange Enterprise CAL with Services:** Exchange Enterprise CAL with Services 라이선스를 추가로 구입한 Exchange 조직이 있는 경우 EOP는 포함된 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-136">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="e53bb-137">모든 EOP 구독 계획의 요구 사항, 중요한 제한 및 기능 가용성에 대한 자세한 내용은 Exchange Online Protection 서비스 [설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="e53bb-137">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="e53bb-138">전자 메일 조직에 대해 EOP 설정</span><span class="sxs-lookup"><span data-stu-id="e53bb-138">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="e53bb-p106">EOP는 간단하게 설정할 수 있으며, 특히 준수 규칙이 많지 않은 소규모 조직의 경우에는 더욱 그렇습니다. 그러나 도메인이 여러 개이거나 사용자 지정 준수 규칙 또는 하이브리드 메일 흐름을 사용하는 대규모 조직의 경우에는 EOP 설정에 더 많은 시간과 계획이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-p106">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="e53bb-141">EOP를 이미 구입한 경우 [EOP 서비스 설정](set-up-your-eop-service.md)을 참조하여 메시징 환경을 보호하도록 EOP를 구성하는 데 필요한 모든 단계를 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="e53bb-141">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="e53bb-142">EOP 데이터 센터</span><span class="sxs-lookup"><span data-stu-id="e53bb-142">EOP datacenters</span></span>

<span data-ttu-id="e53bb-143">EOP는 최고 수준의 사용 가능성을 제공하도록 설계된 전 세계 데이터 센터 네트워크에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-143">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="e53bb-144">예를 들어 데이터 센터를 사용할 수 없더라도 서비스 중단 없이 전자 메일 메시지가 다른 데이터 센터에 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-144">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="e53bb-145">각 데이터 센터의 서버는 사용자 대신 메시지를 수락하여 조직과 인터넷을 분리하는 계층을 제공함으로써 서버에 대한 부하를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-145">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="e53bb-146">이처럼 가용성이 뛰어난 네트워크를 통해 Microsoft는 전자 메일이 제때에 조직으로 배달되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-146">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="e53bb-p108">EOP는 특정 지역 내에서만 데이터 센터 간 부하 분산을 수행합니다. 단일 지역에서 프로비전되는 경우에는 해당 영역에 대한 메일 라우팅을 사용하여 모든 메시지가 처리됩니다. 다음 목록에는 EOP 데이터 센터에 대한 영역 메일 라우팅의 작동 방식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-p108">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="e53bb-150">EMEA(유럽, 중동 및 아프리카)에서는 모든 Exchange Online 사서함이 EMEA 데이터 센터에 있으며 모든 메시지가 EOP 필터링용으로 EMEA 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-150">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="e53bb-151">APAC(Asia-Pacific)에서는 모든 Exchange Online 사서함이 APAC 데이터 센터에 있으며 메시지는 현재 EOP 필터링을 위해 APAC 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-151">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="e53bb-152">미국에서는 서비스가 다음 위치에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-152">In the Americas, services are distributed in the following locations:</span></span>

  - <span data-ttu-id="e53bb-153">남미: Exchange Online 사서함은 브라질 및 칠레의 데이터 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-153">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="e53bb-154">모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-154">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="e53bb-155">Quarantined 메시지는 테넌트가 있는 데이터 센터에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-155">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="e53bb-156">캐나다: Exchange Online 사서함은 캐나다의 데이터 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-156">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="e53bb-157">모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-157">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="e53bb-158">Quarantined 메시지는 테넌트가 있는 데이터 센터에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-158">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="e53bb-159">미국: Exchange Online 사서함은 미국 데이터 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-159">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="e53bb-160">모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-160">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="e53bb-161">Quarantined 메시지는 테넌트가 있는 데이터 센터에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-161">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="e53bb-162">GCC(정부 커뮤니티 클라우드)의 경우에는 모든 Exchange Online 사서함이 미국 데이터 센터에 있으며 모든 메시지는 EOP 필터링용으로 미국 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-162">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="e53bb-163">관리자를 위한 EOP 도움말</span><span class="sxs-lookup"><span data-stu-id="e53bb-163">EOP Help for admins</span></span>

<span data-ttu-id="e53bb-164">EOP 관리자의 도움말 내용은 다음과 같은 최상위 범주로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-164">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="e53bb-165">[Microsoft Defender for Office 365 관리자용 EOP 구성: Office 365용 Microsoft Defender의](protect-against-threats.md)핵심에서 EOP 보호 및 검색 도구 구성</span><span class="sxs-lookup"><span data-stu-id="e53bb-165">[Configure EOP, Day 1, for Microsoft Defender for Office 365 admins](protect-against-threats.md): Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="e53bb-166">[EOP 기능: EOP에서](eop-features.md)사용할 수 있는 기능 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-166">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="e53bb-167">[EOP 서비스](set-up-your-eop-service.md)설정: EOP 서비스를 설정하는 단계와 추가 정보에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-167">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="e53bb-168">[Google Postini, Barracuda Spam and Virus Firewall 또는 Cisco IronPort에서 EOP로](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)전환: 다른 전자 메일 보호 제품에서 EOP로 전환하는 프로세스를 설명</span><span class="sxs-lookup"><span data-stu-id="e53bb-168">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="e53bb-169">[독립 실행형 EOP에서](manage-recipients-in-eop.md)받는 사람 관리 : EOP에서 메일 사용자 및 그룹을 관리하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-169">[Manage recipients in standalone EOP](manage-recipients-in-eop.md): Describes how to manage mail users and groups in EOP.</span></span>

- <span data-ttu-id="e53bb-170">[EOP의 메일](mail-flow-in-eop.md)흐름 : 커넥터를 사용하여 사용자 지정 메일 흐름 시나리오를 구성하는 방법, 서비스에 연결된 도메인을 관리하는 방법 및 DBEB(디렉터리 기반 Edge 차단) 기능을 사용하도록 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-170">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="e53bb-171">[EOP](best-practices-for-configuring-eop.md)구성 모범 사례: 서비스를 설정하고 프로비전한 후의 권장 구성 설정 및 고려 사항을 설명</span><span class="sxs-lookup"><span data-stu-id="e53bb-171">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="e53bb-172">[독립 실행형 EOP의](auditing-reports-in-eop.md)감사 보고서: 감사 보고서를 사용하여 서비스에 대한 구성 변경 내용을 추적하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-172">[Auditing reports in standalone EOP](auditing-reports-in-eop.md): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="e53bb-173">[EOP의](anti-spam-and-anti-malware-protection.md)스팸 방지 및 맬웨어 방지 보호 : 스팸 필터링 및 맬웨어 필터링에 대해 설명하고 조직의 요구 사항을 가장 잘 충족할 수 있도록 사용자 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-173">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="e53bb-174">또한 관리자 및 최종 사용자가 격리된 메시지에 대해 수행할 수 있는 작업도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-174">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="e53bb-175">[Exchange Online Protection의](reporting-and-message-trace-in-exchange-online-protection.md)보고 및 메시지 추적: 사용 가능한 보고서 및 문제 해결 도구에 대해 설명</span><span class="sxs-lookup"><span data-stu-id="e53bb-175">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="e53bb-176">[독립 실행형 EOP의 Exchange](exchange-admin-center-in-exchange-online-protection-eop.md)관리 센터: EAC(Exchange 관리 센터) 관리 인터페이스를 액세스하고 탐색하여 EOP 서비스를 관리하는 방법을 설명</span><span class="sxs-lookup"><span data-stu-id="e53bb-176">[Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="e53bb-177">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): 명령줄에서 EOP 서비스를 관리할 수 있는 원격 PowerShell에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-177">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="e53bb-178">[EOP에 대한 도움말 및 지원](help-and-support-for-eop.md) 도움말 및 기술 지원 서비스를 구하는 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e53bb-178">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>
