---
title: 메일 흐름 인텔리전스
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 관리자는 커넥터를 사용하여 메시지 배달과 연결된 오류 코드(메일 흐름 인텔리전스라고도 합니다.)에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7d4277d1ce3baeabcb5b1795b5d57583fbc8245
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029259"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="bed84-103">EOP의 메일 흐름 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="bed84-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bed84-104">Exchange Online 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에 사서함이 있는 Microsoft 365 조직에서는 일반적으로 커넥터를 사용하여 EOP에서 전자 메일 환경으로 전자 메일 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="bed84-105">커넥터를 사용하여 Microsoft 365에서 파트너 조직으로 메시지를 라우팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="bed84-106">Microsoft 365에서 커넥터를 통해 이러한 메시지를 배달할 수 없는 경우 Microsoft 365에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="bed84-107">Microsoft 365는 24시간 동안 각 메시지에 대해 배달을 계속 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="bed84-108">24시간이 지난 후 대기 중인 메시지가 만료되고, 메시지가 배달되지 않은 보고서(NDR 또는 반송 메시지라고도 알려지음)에서 원래 보낸 사람으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="bed84-109">커넥터를 사용하여 메시지를 배달할 수 없는 경우 Microsoft 365에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="bed84-110">가장 일반적인 오류 및 해당 해결 방법도 이 문서에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-110">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="bed84-111">커넥터를 통해 전송된 확인할 수 없는 메시지에 대한 큐 및 알림 오류를 통일하여 메일 흐름 인텔리전스라고 _합니다._</span><span class="sxs-lookup"><span data-stu-id="bed84-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="bed84-112">오류 코드: 450 4.4.312 DNS 쿼리 실패</span><span class="sxs-lookup"><span data-stu-id="bed84-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="bed84-113">일반적으로 이 오류는 Microsoft 365가 커넥터에 지정된 스마트 호스트에 연결하려고 했지만 스마트 호스트의 IP 주소를 찾기 위한 DNS 쿼리가 실패했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="bed84-114">이 오류의 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="bed84-115">도메인의 DNS 호스팅 서비스(도메인에 대한 권한이 있는 이름 서버를 유지 관리하는 사용자)에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="bed84-116">도메인이 최근에 만료되었습니다. 따라서 MX 레코드를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="bed84-117">도메인의 MX 레코드가 최근에 변경된 경우 DNS 서버는 도메인에 대한 이전에 DNS 정보를 캐시했습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="bed84-118">오류 코드 450 4.4.312를 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="bed84-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="bed84-119">DNS 호스팅 서비스에서 도메인 문제를 식별하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="bed84-120">파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="bed84-121">오류 코드: 450 4.4.315 연결 시간</span><span class="sxs-lookup"><span data-stu-id="bed84-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="bed84-122">일반적으로 이는 Microsoft 365가 대상 전자 메일 서버에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="bed84-123">오류 세부 정보에서 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-123">The error details will explain the problem.</span></span> <span data-ttu-id="bed84-124">예제:</span><span class="sxs-lookup"><span data-stu-id="bed84-124">For example:</span></span>

- <span data-ttu-id="bed84-125">On-premises email server is down.</span><span class="sxs-lookup"><span data-stu-id="bed84-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="bed84-126">커넥터의 스마트 호스트 설정에 오류가 있으므로 Microsoft 365가 잘못된 IP 주소에 연결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="bed84-127">오류 코드 450 4.4.315를 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="bed84-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="bed84-128">어떤 시나리오가 적용되는지 확인하여 필요한 수정을 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="bed84-129">예를 들어 메일 흐름이 올바르게 작동하고 커넥터 설정을 변경하지 않은 경우, 서버가 다운되어 있는 경우 또는 네트워크 인프라가 변경된 경우(예: 인터넷 서비스 공급자를 변경했기 때문에 IP 주소가 달라진 경우)에 대한 자세한 내용을 확인하려면 해당 전자 메일 환경을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="bed84-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="bed84-130">파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="bed84-131">오류 코드: 450 4.4.316 연결 거부</span><span class="sxs-lookup"><span data-stu-id="bed84-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="bed84-132">일반적으로 이 오류는 대상 전자 메일 서버에 연결하려고 할 때 Microsoft 365에서 연결 오류가 발생했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="bed84-133">이 오류의 원인으로는 방화벽이 Microsoft 365 IP 주소의 연결을 차단하고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="bed84-134">또는 이 오류는 Microsoft 365로 전자 메일 시스템을 완전히 마이그레이션한 후,프레미스 전자 메일 환경을 종료한 경우 디자인에 따라 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="bed84-135">오류 코드 450 4.4.316을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="bed84-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="bed84-136">프레미스 환경에 사서함이 있는 경우 TCP 포트 25의 Microsoft 365 IP 주소에서 전자 메일 서버로의 연결을 허용하도록 방화벽 설정을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="bed84-137">Microsoft 365 IP 주소 목록은 [Microsoft 365 URL](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)및 IP 주소 범위를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bed84-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="bed84-138">더 이상 메시지를 프레미스 환경으로 배달할  수 없는 경우 Microsoft 365에서 잘못된 받는 사람이 있는 메시지를 즉시 거부할 수 있도록 경고에서 지금 수정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="bed84-139">이렇게 하면 잘못된 받는 사람에 대한 조직의 할당량 초과 위험이 줄어들어 정상적인 메시지 배달에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="bed84-140">또는 다음 지침을 사용하여 문제를 수동으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="bed84-141">[EAC(Exchange](https://docs.microsoft.com/Exchange/exchange-admin-center)관리 센터)에서 Microsoft 365에서 전자 메일을 프레미스 전자 메일 환경으로 배달하는 커넥터를 사용하지 않도록 설정하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="bed84-142">EAC에서 **메일** 흐름 \> **커넥터로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="bed84-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="bed84-143">From 값 **Office 365** 및 조직의  전자  메일 서버를 값으로 하는 커넥터를 선택하고 다음 단계 중 하나를 수행합니다. </span><span class="sxs-lookup"><span data-stu-id="bed84-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="bed84-144">제거 아이콘 삭제를 **클릭하여** 커넥터 ![ 삭제](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="bed84-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="bed84-145">편집 아이콘을 클릭하고 켜기 아이콘을 선택 취소하여 커넥터를  ![ 사용하지 않도록 ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="bed84-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="bed84-146">Microsoft 365의 허용 도메인을 내부 릴레이에서 권한이 있는  전자 메일 환경과 연결된 Microsoft 365로 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="bed84-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="bed84-147">자세한 내용은 [Exchange Online에서 허용 도메인 관리를 참조하세요.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="bed84-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="bed84-148">**참고:** 일반적으로 이러한 변경 내용은 적용하는 데 30분에서 1시간 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="bed84-149">1시간이 지나면 오류가 더 이상 수신되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="bed84-150">파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="bed84-151">오류 코드: 450 4.4.317 원격 서버에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="bed84-152">일반적으로 이 오류는 대상 전자 메일 서버에 Microsoft 365가 연결되어 있지만 서버가 즉시 오류로 응답했거나 연결 요구 사항을 충족하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="bed84-153">오류 세부 정보에서 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-153">The error details will explain the problem.</span></span> <span data-ttu-id="bed84-154">예제:</span><span class="sxs-lookup"><span data-stu-id="bed84-154">For example:</span></span>

- <span data-ttu-id="bed84-155">대상 전자 메일 서버가 "서비스를 사용할 수 없습니다." 오류로 응답했습니다. 이 오류는 서버가 Microsoft 365와의 통신을 유지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="bed84-156">커넥터가 TLS를 요구하도록 구성되지만 대상 전자 메일 서버는 TLS를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="bed84-157">오류 코드 450 4.4.317을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="bed84-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="bed84-158">커넥터의 TLS 설정 및 인증서와 커넥터의 TLS 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="bed84-159">파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="bed84-160">오류 코드: 450 4.4.318 연결이 실수로 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="bed84-161">일반적으로 이 오류는 Microsoft 365가 전자 메일 환경과 통신하는 데 어려움을 겪고 있으므로 연결이 끊어졌다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="bed84-162">이 오류의 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="bed84-163">방화벽에서 SMTP 패킷 검사 규칙을 사용하며 이러한 규칙이 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="bed84-164">서비스 중단, 크래시 또는 낮은 시스템 리소스와 같은,프레미스 전자 메일 서버가 제대로 작동하지 않습니다. 이로 인해 서버의 시간이 종료되어 Microsoft 365에 대한 연결이 닫히게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="bed84-165">On-premises 환경과 Microsoft 365 간에 네트워크 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="bed84-166">오류 코드 450 4.4.318을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="bed84-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="bed84-167">어떤 시나리오가 적용되는지 확인하여 필요한 수정을 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="bed84-168">문제의 원인이 프레미스 환경과 Microsoft 365 간의 네트워크 문제인 경우 네트워크 팀에 문의하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="bed84-169">파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="bed84-170">오류 코드: 450 4.7.320 인증서 유효성 검사 실패</span><span class="sxs-lookup"><span data-stu-id="bed84-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="bed84-171">일반적으로 이 오류는 대상 전자 메일 서버의 인증서 유효성을 검사하는 동안 Microsoft 365에서 오류가 발생했다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="bed84-172">오류 세부 정보에서 오류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-172">The error details will explain the error.</span></span> <span data-ttu-id="bed84-173">예제:</span><span class="sxs-lookup"><span data-stu-id="bed84-173">For example:</span></span>

- <span data-ttu-id="bed84-174">인증서 만료</span><span class="sxs-lookup"><span data-stu-id="bed84-174">Certificate expired</span></span>

- <span data-ttu-id="bed84-175">인증서 주체 불일치</span><span class="sxs-lookup"><span data-stu-id="bed84-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="bed84-176">인증서가 더 이상 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="bed84-177">오류 코드 450 4.7.320을 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="bed84-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="bed84-178">Microsoft 365에서 대기 중인 메시지를 배달할 수 있도록 커넥터의 인증서 또는 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="bed84-179">파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="bed84-180">기타 오류 코드</span><span class="sxs-lookup"><span data-stu-id="bed84-180">Other error codes</span></span>

<span data-ttu-id="bed84-181">Microsoft 365는 메시지를 프레미스 또는 파트너 전자 메일 서버로 배달하는 데 어려움을 겪고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="bed84-182">오류의 **대상** 서버 정보를 사용하여 환경의 문제를 검사하거나 구성 오류가 있는 경우 커넥터를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="bed84-183">파트너 조직(예: 제3자 클라우드 서비스 공급자)에서 오류가 발생하면 파트너에게 문의하여 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed84-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
