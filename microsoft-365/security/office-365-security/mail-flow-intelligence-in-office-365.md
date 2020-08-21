---
title: 메일 흐름 인텔리전스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 관리자는 커넥터를 사용하는 메시지 배달과 연결된 오류 코드에 대해 알아보세요(메일 흐름 인텔리전스라고도 함).
ms.openlocfilehash: b345b52f572efca2aca1fde6ba720d733e521cc4
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827716"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="fe8e8-103">EOP의 메일 흐름 인텔리전스</span><span class="sxs-lookup"><span data-stu-id="fe8e8-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="fe8e8-104">Exchange Online 사서함이 있는 Microsoft 365 조직에서는 일반적으로 커넥터를 사용하여 EOP에서 온-프레미스 전자 메일 환경으로 전자 메일 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="fe8e8-105">또한 커넥터를 사용하여 Microsoft 365에서 파트너 조직으로 메시지를 라우팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="fe8e8-106">Microsoft 365에서 커넥터를 통해 이러한 메시지를 배달할 수 없는 경우 Microsoft 365에서 대기하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="fe8e8-107">Microsoft 365에서 각 메시지에 대한 배달을 계속해서 24시간 동안 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="fe8e8-108">24시간 후 큐에 대기된 메시지는 만료되며, 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)에서 원래 보낸 사람에게 메시지가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="fe8e8-109">커넥터를 사용하여 메시지를 배달할 수 없는 경우 Microsoft 365에서 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="fe8e8-110">이 항목에서는 가장 일반적인 오류와 해당 해결 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="fe8e8-111">커넥터를 통해 전송된 배달할 수 없는 메시지에 대한 정적으로 큐 및 알림 오류를 정적으로 확인하는 것을 _메일 흐름 인텔리전스라고 합니다._</span><span class="sxs-lookup"><span data-stu-id="fe8e8-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="fe8e8-112">오류 코드: 450 4.4.312 DNS 쿼리 실패</span><span class="sxs-lookup"><span data-stu-id="fe8e8-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="fe8e8-113">일반적으로 이 오류는 Microsoft 365에서 커넥터에 지정된 스마트 호스트에 연결을 시도하지만 스마트 호스트의 IP 주소를 찾기 위한 DNS 쿼리가 실패함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="fe8e8-114">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="fe8e8-115">도메인의 DNS 호스팅 서비스에 문제가 있습니다(도메인에 대해 신뢰할 수 있는 이름 서버를 유지하는 파티).</span><span class="sxs-lookup"><span data-stu-id="fe8e8-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="fe8e8-116">도메인이 최근 만료되어 MX 레코드를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="fe8e8-117">도메인의 MX 레코드가 최근에 변경되었으며 DNS 서버에 도메인에 대한 이전에 캐시된 DNS 정보가 여전히 캐시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="fe8e8-118">오류 코드 450 4.4.312를 어떻게 수정하나요?</span><span class="sxs-lookup"><span data-stu-id="fe8e8-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="fe8e8-119">DNS 호스팅 서비스와 함께 도메인의 문제를 식별하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="fe8e8-120">파트너 조직에서 오류가 발생하는 경우(예: 타사 클라우드 서비스 공급자) 파트너에게 문의하여 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="fe8e8-121">오류 코드: 450 4.4.315 연결 시간이 초과되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="fe8e8-122">일반적으로 이는 Microsoft 365가 대상 전자 메일 서버에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="fe8e8-123">오류 세부 정보에서 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-123">The error details will explain the problem.</span></span> <span data-ttu-id="fe8e8-124">예제:</span><span class="sxs-lookup"><span data-stu-id="fe8e8-124">For example:</span></span>

- <span data-ttu-id="fe8e8-125">온-프레미스 전자 메일 서버의 다운.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="fe8e8-126">커넥터의 스마트 호스트 설정에 오류가 발생하여 Microsoft 365가 잘못된 IP 주소에 연결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="fe8e8-127">오류 코드 450 4.4.315를 어떻게 수정하나요?</span><span class="sxs-lookup"><span data-stu-id="fe8e8-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="fe8e8-128">각 시나리오에 적용되는 시나리오를 확인하고 필요한 부분을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="fe8e8-129">예를 들어 메일 흐름이 올바르게 작동하고 커넥터 설정을 변경하지 않은 경우 온-프레미스 전자 메일 환경에서 서버가 다운되었는지, 또는 네트워크 인프라에 변경 내용이 있거나 네트워크 인프라에 변경 사항이 있어서(예: 인터넷 서비스 공급자를 변경하여 이제 와일드키는 IP 주소가 다르기) 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="fe8e8-130">파트너 조직에서 오류가 발생하는 경우(예: 타사 클라우드 서비스 공급자) 파트너에게 문의하여 문제를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="fe8e8-131">오류 코드: 450 4.4.316 연결 거부</span><span class="sxs-lookup"><span data-stu-id="fe8e8-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="fe8e8-132">일반적으로 이 오류는 Microsoft 365에서 대상 전자 메일 서버에 연결하려고 할 때 연결 오류가 발생하라는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="fe8e8-133">방화벽에서 Microsoft 365 IP 주소의 연결을 차단하고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="fe8e8-134">또는 이 오류는 온-프레미스 전자 메일 시스템을 Microsoft 365로 완전히 마이그레이션하고 온-프레미스 전자 메일 환경을 종료한 경우에 기본적으로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="fe8e8-135">오류 코드 450 4.4.316을 어떻게 해결하나요?</span><span class="sxs-lookup"><span data-stu-id="fe8e8-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="fe8e8-136">온-프레미스 환경에 사서함이 있는 경우 TCP 포트 25의 Microsoft 365 IP 주소에서 온-프레미스 전자 메일 서버로의 연결을 허용하도록 방화벽 설정을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="fe8e8-137">Microsoft 365 IP 주소 목록은 [Microsoft 365 URL 및 IP 주소 범위를 참조하세요.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="fe8e8-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="fe8e8-138">온-프레미스 환경에 더 이상 메시지를 배달해야 **Fix now** 하는 경우 Microsoft 365에서 잘못된 받는 사람이 있는 메시지를 즉시 거부할 수 있도록 알림에 있는 지금 수정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="fe8e8-139">이렇게 하면 정상적인 메시지 배달에 영향을 줄 수 있는 잘못된 받는 사람에 대한 조직 의 할당량을 초과할 위험이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="fe8e8-140">또는 다음 지침을 사용하여 문제를 수동으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="fe8e8-141">[EAC(Exchange 관리 센터)에서,](https://docs.microsoft.com/Exchange/exchange-admin-center)Microsoft 365에서 온-프레미스 전자 메일 환경으로 전자 메일을 배달하는 커넥터를 사용하지 않도록 설정하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="fe8e8-142">EAC에서 메일 흐름 **커넥터로** \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe8e8-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="fe8e8-143">Select the From **value** **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span><span class="sxs-lookup"><span data-stu-id="fe8e8-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="fe8e8-144">제거 아이콘 삭제를 **클릭하여 커넥터** ![ 삭제](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="fe8e8-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="fe8e8-145">편집 아이콘을 클릭하고 **켜기를 지워** ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 커넥터를 사용하지 **않도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe8e8-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="fe8e8-146">온-프레미스 전자 메일 환경과 연결된 Microsoft 365에서 허용 도메인을 **내부 릴레이에서** 신뢰할 수 **있는 도메인으로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe8e8-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="fe8e8-147">자세한 내용은 [Exchange Online에서 허용 도메인 관리를 참조하세요.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="fe8e8-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="fe8e8-148">**참고:** 일반적으로 이러한 변경 내용은 적용하는 데 30분에서 1시간 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="fe8e8-149">1시간 후에 더 이상 오류를 받지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="fe8e8-150">파트너 조직에서 오류인 경우(예: 타사 클라우드 서비스 공급자) 파트너에게 문의하여 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="fe8e8-151">오류 코드: 450 4.4.317 원격 서버에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="fe8e8-152">일반적으로 이 오류는 대상 전자 메일 서버에 연결되어 있지만 서버가 즉시 오류로 응답한 또는 연결 요구 사항을 충족하지 않는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="fe8e8-153">오류 세부 정보에서 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-153">The error details will explain the problem.</span></span> <span data-ttu-id="fe8e8-154">예제:</span><span class="sxs-lookup"><span data-stu-id="fe8e8-154">For example:</span></span>

- <span data-ttu-id="fe8e8-155">대상 전자 메일 서버가 "서비스를 사용할 수 없음" 오류로 응답했습니다. 이 오류는 서버가 Microsoft 365와 통신할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="fe8e8-156">커넥터가 TLS를 요구하도록 구성되었지만 대상 전자 메일 서버는 TLS를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="fe8e8-157">오류 코드 450 4.4.317은 어떻게 수정하나요?</span><span class="sxs-lookup"><span data-stu-id="fe8e8-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="fe8e8-158">온-프레미스 전자 메일 서버에서 TLS 설정 및 인증서와 커넥터의 TLS 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="fe8e8-159">파트너 조직에서 오류인 경우(예: 타사 클라우드 서비스 공급자) 파트너에게 문의하여 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="fe8e8-160">오류 코드: 450 4.4.318 연결을 정상적으로 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="fe8e8-161">일반적으로 이 오류는 Microsoft 365에서 온-프레미스 전자 메일 환경과 통신하는 데 어려워서 연결이 삭제되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="fe8e8-162">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="fe8e8-163">방화벽에서 SMTP 패킷 검사 규칙을 사용하고 이러한 규칙이 제대로 작동하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="fe8e8-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="fe8e8-164">온-프레미스 이메일 서버가 제대로 작동하지 않는 경우(예: 서비스 분기, 크래시 또는 시스템 리소스 부적) 서버에서 시간 초과 후 Microsoft 365에 대한 연결을 닫기가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="fe8e8-165">온-프레미스 환경과 Microsoft 365에 네트워크 문제가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="fe8e8-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="fe8e8-166">오류 코드 450 4.4.318을 어떻게 수정하나요?</span><span class="sxs-lookup"><span data-stu-id="fe8e8-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="fe8e8-167">각 시나리오에 적용되는 시나리오를 확인하고 필요한 부분을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="fe8e8-168">온-프레미스 환경과 Microsoft 365 간에 네트워크 문제가 발생하는 경우, 문제를 해결 하려면 네트워크 팀에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="fe8e8-169">파트너 조직에서 오류인 경우(예: 타사 클라우드 서비스 공급자) 파트너에게 문의하여 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="fe8e8-170">오류 코드: 450 4.7.320 인증서 유효성 검사 실패</span><span class="sxs-lookup"><span data-stu-id="fe8e8-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="fe8e8-171">일반적으로 이 오류는 Microsoft 365에서 대상 전자 메일 서버의 인증서를 확인하는 동안 오류를 발생시다시니는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="fe8e8-172">오류 세부 정보에서는 오류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-172">The error details will explain the error.</span></span> <span data-ttu-id="fe8e8-173">예제:</span><span class="sxs-lookup"><span data-stu-id="fe8e8-173">For example:</span></span>

- <span data-ttu-id="fe8e8-174">인증서 만료됨</span><span class="sxs-lookup"><span data-stu-id="fe8e8-174">Certificate expired</span></span>

- <span data-ttu-id="fe8e8-175">인증서 주체 일치</span><span class="sxs-lookup"><span data-stu-id="fe8e8-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="fe8e8-176">인증서가 더 이상 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="fe8e8-177">오류 코드 450 4.7.320을 어떻게 수정하나요?</span><span class="sxs-lookup"><span data-stu-id="fe8e8-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="fe8e8-178">Microsoft 365에서 대기된 메시지를 배달할 수 있도록 커넥터에 대한 인증서 또는 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="fe8e8-179">파트너 조직에서 오류인 경우(예: 타사 클라우드 서비스 공급자) 파트너에게 문의하여 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="fe8e8-180">기타 오류 코드</span><span class="sxs-lookup"><span data-stu-id="fe8e8-180">Other error codes</span></span>

<span data-ttu-id="fe8e8-181">Microsoft 365에서는 온-프레미스 또는 파트너 전자 메일 서버로 메시지를 배달하기 어려운 오류를 해결하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="fe8e8-182">오류의 **대상** 서버 정보를 사용하여 환경의 문제를 검사하거나, 구성 오류가 발생한 경우 커넥터를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="fe8e8-183">파트너 조직에서 오류인 경우(예: 타사 클라우드 서비스 공급자) 파트너에게 문의하여 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
