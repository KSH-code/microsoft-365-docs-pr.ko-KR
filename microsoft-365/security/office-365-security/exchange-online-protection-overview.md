---
title: EOP (Exchange Online Protection) 개요
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: EOP (Exchange Online Protection)를 사용 하 여 독립 실행형 및 하이브리드 환경에서 온-프레미스 전자 메일 조직을 보호 하는 방법을 알아봅니다.
ms.openlocfilehash: a3f71ea5366224465cdaf3922c6c467fcb49f3cc
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616989"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="30638-103">Exchange Online Protection 개요</span><span class="sxs-lookup"><span data-stu-id="30638-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="30638-104">EOP (Exchange Online Protection)는 스팸 및 맬웨어로부터 조직을 보호 하는 클라우드 기반 필터링 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="30638-104">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="30638-105">EOP는 Exchange Online 사서함이 있는 모든 Microsoft 365 조직에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-105">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span>

<span data-ttu-id="30638-106">하지만 EOP는 다음과 같은 온-프레미스 시나리오 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-106">But, EOP is also available in the following on-premises scenarios:</span></span>

- <span data-ttu-id="30638-107">**독립 실행형 시나리오에서**EOP는 온-프레미스 Exchange 조직 또는 기타 모든 온-프레미스 SMTP 전자 메일 솔루션에 대해 클라우드 기반 전자 메일 보호 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-107">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="30638-108">**하이브리드 배포에서**: 온-프레미스 및 클라우드 사서함을 함께 사용 하는 경우 전자 메일 환경을 보호 하 고 메일 라우팅을 제어 하도록 EOP를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-108">**In a hybrid deployment**: EOP can be configured to protect your email environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

<span data-ttu-id="30638-109">이러한 시나리오에서 EOP는 전자 메일 환경 관리를 단순화 하 고 온-프레미스 하드웨어 및 소프트웨어 유지 관리와 함께 제공 되는 많은 부담을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-109">In these scenarios, EOP can simplify the management of your email environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="30638-110">이 항목의 나머지 부분에서는 독립 실행형 및 하이브리드 환경에서 EOP가 작동 하는 방식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-110">The rest of this topic explains how EOP works in standalone and hybrid environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="30638-111">EOP의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="30638-111">How EOP works</span></span>

<span data-ttu-id="30638-112">EOP가 받는 전자 메일을 처리하는 방법을 확인하면 EOP의 작동 방식을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-112">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

![전자 메일 프로세스 다이어그램](../../media/emailprocessingineop1.png)

- <span data-ttu-id="30638-114">처음에 들어오는 메시지는 보낸 사람의 신뢰도를 확인 하 고 맬웨어가 있는지 메시지를 검사 하는 연결 필터링을 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-114">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware.</span></span> <span data-ttu-id="30638-115">대부분의 스팸이이 지점에서 중지 되 고 EOP에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-115">The majority of spam is stopped at this point and deleted by EOP.</span></span> <span data-ttu-id="30638-116">자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="30638-116">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="30638-117">메시지는 서식 파일에서 만들거나 적용 하는 사용자 지정 메일 흐름 규칙 (전송 규칙이 라고도 함)에 대해 메시지를 평가 하는 정책 필터링을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-117">Messages continue through policy filtering, where messages are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="30638-118">예를 들어 메일이 특정 보낸 사람에 게 서 도착 하면 관리자에 게 알림을 보내는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-118">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="30638-119">DLP (데이터 손실 방지) 확인은이 시점에도 수행 됩니다 (Exchange Enterprise CAL with Services).</span><span class="sxs-lookup"><span data-stu-id="30638-119">Data loss prevention (DLP) checks also occur at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="30638-120">다음으로 메시지는 스팸 방지 필터링 (콘텐츠 필터링이 라고도 함)을 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-120">Next, messages pass through anti-spam filtering (also known as content filtering).</span></span> <span data-ttu-id="30638-121">다른 옵션 들 중에서 스팸으로 확인 된 메시지를 사용자의 정크 메일 폴더 또는 격리로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-121">A message that's determined to be spam can be sent to a user's Junk Email folder or to the quarantine, among other options.</span></span> <span data-ttu-id="30638-122">자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30638-122">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="30638-123">메시지는 이러한 모든 보호 계층을 성공적으로 통과 하면 받는 사람에 게 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-123">After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>

<span data-ttu-id="30638-124">자세한 내용은 [전자 메일 보호의 주문 및 우선 순위](how-policies-and-protections-are-combined.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30638-124">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="30638-125">EOP 데이터 센터</span><span class="sxs-lookup"><span data-stu-id="30638-125">EOP datacenters</span></span>

<span data-ttu-id="30638-126">EOP는 최고 수준의 사용 가능성을 제공하도록 설계된 전 세계 데이터 센터 네트워크에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-126">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="30638-127">예를 들어 데이터 센터를 사용할 수 없더라도 서비스 중단 없이 전자 메일 메시지가 다른 데이터 센터에 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-127">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="30638-128">각 데이터 센터의 서버는 사용자 대신 메시지를 수락 하 여 조직과 인터넷을 분리 하는 계층을 제공 함으로써 서버의 부하를 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30638-128">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="30638-129">이처럼 가용성이 뛰어난 네트워크를 통해 Microsoft는 전자 메일이 제때에 조직으로 배달되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-129">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="30638-p106">EOP는 특정 지역 내에서만 데이터 센터 간 부하 분산을 수행합니다. 단일 지역에서 프로비전되는 경우에는 해당 영역에 대한 메일 라우팅을 사용하여 모든 메시지가 처리됩니다. 다음 목록에는 EOP 데이터 센터에 대한 영역 메일 라우팅의 작동 방식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-p106">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="30638-133">EMEA(유럽, 중동 및 아프리카)에서는 모든 Exchange Online 사서함이 EMEA 데이터 센터에 있으며 모든 메시지가 EOP 필터링용으로 EMEA 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-133">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="30638-134">APAC (아시아 태평양)에서는 모든 Exchange Online 사서함이 APAC 데이터 센터에 있고 메시지는 현재 EOP 필터링을 위해 APAC 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-134">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="30638-135">미주에서 모든 Exchange Online 사서함은 미국 데이터 센터에 있으며, 브라질 및 칠레 데이터 센터가 사용 되 고 캐나다의 데이터 센터가 사용 되는 경우에는 남부 아메리카를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-135">In the Americas, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used.</span></span> <span data-ttu-id="30638-136">남미 및 캐나다의 고객에 대 한 메시지를 비롯 하 여 모든 전자 메일 메시지는 EOP 필터링에 대 한 로컬 데이터 센터를 통해 라우팅됩니다. 격리 된 전자 메일은 테 넌 트가 있는 데이터 센터에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-136">All email messages, including messages for customers in South America and Canada, are routed through local datacenters for EOP filtering; quarantined email is stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="30638-137">GCC(정부 커뮤니티 클라우드)의 경우에는 모든 Exchange Online 사서함이 미국 데이터 센터에 있으며 모든 메시지는 EOP 필터링용으로 미국 데이터 센터를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="30638-137">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="30638-138">온-프레미스 전자 메일 조직에 대 한 EOP 요금제 및 기능</span><span class="sxs-lookup"><span data-stu-id="30638-138">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="30638-139">사용 가능한 EOP 구독 계획은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-139">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="30638-140">**EOP 독립 실행형**: EOP에 등록 하 여 온-프레미스 전자 메일 조직을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-140">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="30638-141">**Exchange online의 EOP 기능**: exchange online (독립 실행형 또는 Microsoft 365의 일부로)이 포함 된 모든 구독은 EOP을 사용 하 여 exchange online 사서함을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-141">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="30638-142">**Exchange ENTERPRISE cal With services**: 서비스 라이선스로 추가 EXCHANGE Enterprise cal을 구매한 온-프레미스 Exchange 조직이 있는 경우 EOP는 포함 된 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="30638-142">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="30638-143">모든 EOP 구독 계획에서 요구 사항, 중요 제한 및 기능 가용성에 대 한 자세한 내용은 [Exchange Online Protection 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30638-143">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="30638-144">온-프레미스 전자 메일 조직에 대해 EOP 설정</span><span class="sxs-lookup"><span data-stu-id="30638-144">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="30638-p108">EOP는 간단하게 설정할 수 있으며, 특히 준수 규칙이 많지 않은 소규모 조직의 경우에는 더욱 그렇습니다. 그러나 도메인이 여러 개이거나 사용자 지정 준수 규칙 또는 하이브리드 메일 흐름을 사용하는 대규모 조직의 경우에는 EOP 설정에 더 많은 시간과 계획이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-p108">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="30638-147">EOP를 이미 구입한 경우 [EOP 서비스 설정](set-up-your-eop-service.md)을 참조하여 메시징 환경을 보호하도록 EOP를 구성하는 데 필요한 모든 단계를 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="30638-147">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="30638-148">관리자를 위한 EOP 도움말</span><span class="sxs-lookup"><span data-stu-id="30638-148">EOP Help for admins</span></span>

<span data-ttu-id="30638-149">EOP 관리자의 도움말 내용은 다음과 같은 최상위 범주로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30638-149">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="30638-150">[Exchange Online Protection 개요](exchange-online-protection-overview.md): EOP가 작동 하는 방식을 소개 하 고 추가 정보에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-150">[Exchange Online Protection overview](exchange-online-protection-overview.md): Introduces how EOP works and provides links to additional information.</span></span>

- <span data-ttu-id="30638-151">[EOP 기능](eop-features.md): EOP에서 사용할 수 있는 기능 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-151">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="30638-152">[EOP Service 설정](set-up-your-eop-service.md): EOP 서비스를 설정 하는 단계와 추가 정보에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-152">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="30638-153">[Google Postini, Barracuda 스팸 및 바이러스 방화벽 또는 Cisco ironpor에서 EOP로 전환](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)다른 전자 메일 보호 제품에서 EOP로 전환 하는 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-153">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="30638-154">[독립 실행형 EOP에서 받는 사람 관리](manage-recipients-in-eop.md): EOP에서 메일 사용자 및 그룹을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-154">[Manage recipients in standalone EOP](manage-recipients-in-eop.md): Describes how to manage mail users and groups in EOP.</span></span>

- <span data-ttu-id="30638-155">[EOP의 메일 흐름](mail-flow-in-eop.md): 커넥터를 사용 하 여 사용자 지정 메일 흐름 시나리오를 구성 하는 방법, 서비스와 연결 된 도메인을 관리 하는 방법 및 DBEB (디렉터리 기반 Edge 차단) 기능을 사용 하도록 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-155">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="30638-156">[EOP 구성을 위한 모범 사례](best-practices-for-configuring-eop.md): 서비스를 설정 및 프로 비전 한 후 권장 되는 구성 설정 및 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-156">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="30638-157">[독립 실행형 EOP의 감사 보고서](auditing-reports-in-eop.md): 감사 보고서를 사용 하 여 서비스에 대 한 구성 변경 내용을 추적 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-157">[Auditing reports in standalone EOP](auditing-reports-in-eop.md): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="30638-158">[EOP의 스팸 방지 및 맬웨어 방지 보호](anti-spam-and-anti-malware-protection.md): 스팸 필터링 및 맬웨어 필터링에 대해 설명 하 고 조직의 요구에 가장 잘 맞게 사용자 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30638-158">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="30638-159">또한 관리자 및 최종 사용자가 격리된 메시지에 대해 수행할 수 있는 작업도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-159">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="30638-160">[Reporting and message trace In Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): 사용할 수 있는 보고서 및 문제 해결 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-160">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="30638-161">[독립 실행형 EOP의 Exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md): EOP 서비스를 관리 하기 위해 EAC (exchange 관리 센터) 관리 인터페이스를 액세스 하 고 탐색 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-161">[Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="30638-162">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): 명령줄에서 EOP 서비스를 관리 하는 데 사용할 수 있는 원격 PowerShell에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-162">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="30638-163">[EOP에 대한 도움말 및 지원](help-and-support-for-eop.md) 도움말 및 기술 지원 서비스를 구하는 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30638-163">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>
