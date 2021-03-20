---
title: Microsoft 365로 전송한 문제 해결 메일
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft 365 고객에게 대량 메일을 보내기 위한 모범 & Microsoft 365의 받은 편지함으로 전자 메일을 보내는 데 문제가 있는 경우의 문제 해결 정보를 제공합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5cebb5ab3f5f4adf321e9c7992fcc5efe40ac2a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908153"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="728e8-103">Microsoft 365로 전송한 문제 해결 메일</span><span class="sxs-lookup"><span data-stu-id="728e8-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="728e8-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="728e8-104">**Applies to**</span></span>
- [<span data-ttu-id="728e8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="728e8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="728e8-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="728e8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="728e8-107">이 문서에서는 Microsoft 365의 받은 편지함으로 전자 메일을 보내려고 할 때 문제가 발생하는 보낸 사람에 대한 문제 해결 정보와 고객에게 대량 메일링을 위한 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="728e8-108">IP 및 도메인의 전송 신뢰도 관리 중입니까?</span><span class="sxs-lookup"><span data-stu-id="728e8-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="728e8-109">EOP 필터링 기술은 Microsoft 365뿐만 아니라 Microsoft 365 및 기타 Microsoft 제품에 대한 스팸 방지 보호 기능을 제공하도록 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="728e8-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="728e8-110">또한 SPF, DKIM 및 DMARC를 활용합니다. 전자 메일을 보내는 도메인이 스푸핑 및 피싱 문제를 해결할 수 있도록 하는 전자 메일 인증 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="728e8-111">EOP 필터링은 보내는 IP, 도메인, 인증, 목록 정확도, 불만 비율, 콘텐츠 등 다양한 요소의 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="728e8-112">이 중 보낸 사람 신뢰도와 전자 메일을 배달할 수 있는 능력의 주된 요인 중 하나는 정크 메일 불만 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="728e8-113">새 IP 주소에서 전자 메일을 보내나요?</span><span class="sxs-lookup"><span data-stu-id="728e8-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="728e8-114">이전에 전자 메일을 보내는 데 사용되지 않은 IP 주소는 일반적으로 시스템에 구축된 신뢰도에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-114">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="728e8-115">따라서 새 IP의 전자 메일에 배달 문제가 있을 가능성이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-115">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="728e8-116">IP가 스팸을 보내지 않는 신뢰도로 구축된 경우 EOP는 일반적으로 더 나은 전자 메일 배달 환경을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-116">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="728e8-117">기존 SPF 레코드에 따라 인증된 도메인에 대해 추가되는 새 IP는 일반적으로 도메인의 보내는 신뢰도 중 일부를 상속할 때의 추가 이점을 경험합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-117">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="728e8-118">도메인의 전송 평판이 좋은 경우 새 IP가 빠른 램프 시간을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-118">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="728e8-119">새 IP는 볼륨, 목록 정확도 및 정크 메일 불만 비율에 따라 몇 주 이내에 완전히 증가할 것으로 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-119">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="728e8-120">DNS가 올바르게 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="728e8-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="728e8-121">메일 라우팅에 필요한 MX 레코드를 포함하여 DNS 레코드를 만들고 유지 관리하는 방법에 대한 지침은 DNS 호스팅 공급자에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="728e8-122">라우팅할 수 없는 IP로 자신을 보급하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="728e8-123">역방향 DNS 쿼리에 실패한 보낸 사람이 보낸 전자 메일을 수락하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-123">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="728e8-124">경우에 따라 합법적인 보낸 사람이 EOP에 대한 연결을 열려고 할 때 인터넷에 라우팅할 수 없는 IP로 잘못 보급하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-124">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="728e8-125">개인(라우팅할 수 없는) 네트워킹에 예약된 IP 주소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-125">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="728e8-126">192.168.0.0/16(또는 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="728e8-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="728e8-127">10.0.0.0/8(또는 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="728e8-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="728e8-128">172.16.0.0/11(또는 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="728e8-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="728e8-129">Office 365에서 사용자에게 전자 메일을 보낼 때 NDR(배달되지 않은 보고서)을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="728e8-130">일부 배달 문제는 Microsoft에서 보낸 사람 IP 주소가 차단되거나 사용자 계정이 이전 스팸 활동으로 인해 금지된 보낸 사람으로 식별된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-130">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="728e8-131">NDR을 오류로 수신했다고 생각되면 먼저 NDR 메시지의 지침을 따라 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-131">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="728e8-132">받은 오류에 대한 자세한 내용은 Exchange Online의 전자 메일 배달되지 않은 보고서의 오류 코드 [목록을 참조하세요.](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="728e8-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="728e8-133">예를 들어 다음 NDR을 받으면 보내는 IP 주소가 Microsoft에 의해 차단된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="728e8-134">이 목록에서 제거를 요청하려면 목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 자신을 [제거할 수 있습니다.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="728e8-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="728e8-135">받는 사람의 정크 메일 폴더에 있는 내 전자 메일</span><span class="sxs-lookup"><span data-stu-id="728e8-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="728e8-136">EOP에서 메시지가 스팸으로 잘못 식별된 경우 받는 사람과 함께 이 가짓 긍정 메시지를 Microsoft 스팸 분석 팀에 제출하여 메시지를 평가하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="728e8-137">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="728e8-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="728e8-138">내 IP 주소의 트래픽이 EOP에 의해 스로틀됩니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="728e8-139">EOP에서 IP 주소가 EOP에 의해 스로틀되고 있는 것을 나타내는 NDR을 받는 경우 다음을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="728e8-140">IP 주소에서 의심스러운 활동이 검색되어 추가 평가가 진행되는 동안 일시적으로 제한되어 NDR을 수신했습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-140">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="728e8-141">평가를 통해 의혹이 제거될 경우 이 제한이 곧 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-141">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="728e8-142">Microsoft 365에서 보낸 사람으로부터 전자 메일을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="728e8-143">사용자로부터 메시지를 받으기 위해 네트워크에서 EOP가 데이터 센터에서 사용하는 IP 주소로부터의 연결을 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="728e8-144">자세한 내용은 [Exchange Online Protection IP 주소 를 참조하세요.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="728e8-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="728e8-145">Microsoft 365 사용자에게 대량 전자 메일 보내기 모범 사례</span><span class="sxs-lookup"><span data-stu-id="728e8-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="728e8-146">Microsoft 365 사용자에게 대량 전자 메일 캠페인을 자주 수행하고 전자 메일이 안전하고 시기 적절한 방식으로 도착하도록 하려는 경우 이 섹션의 팁을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="728e8-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="728e8-147">보낸 사람 이름에 메시지를 보내는 사람이 반영되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="728e8-148">제목은 메시지의 내용을 간략하게 요약한 것이고 메시지 본문은 제품, 서비스 또는 제품의 대상을 명확하고 간결하게 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-148">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="728e8-149">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-149">For example:</span></span>

<span data-ttu-id="728e8-150">정확함:</span><span class="sxs-lookup"><span data-stu-id="728e8-150">Correct:</span></span>

> <span data-ttu-id="728e8-151">From: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="728e8-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="728e8-152">제목: 성탄절에 대한 카탈로그가 업데이트되었습니다!</span><span class="sxs-lookup"><span data-stu-id="728e8-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="728e8-153">정확하지 않음:</span><span class="sxs-lookup"><span data-stu-id="728e8-153">Incorrect:</span></span>

> <span data-ttu-id="728e8-154">From: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="728e8-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="728e8-155">제목: 카탈로그</span><span class="sxs-lookup"><span data-stu-id="728e8-155">Subject: Catalogs</span></span>

<span data-ttu-id="728e8-156">사람들이 사용자와 수행하고 있는 작업을 보다 쉽게 알 수 있도록 함으로써 대부분의 스팸 필터를 통해 전달하는 데 어려움을 덜 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="728e8-157">캠페인 전자 메일에 구독 취소 옵션 항상 포함</span><span class="sxs-lookup"><span data-stu-id="728e8-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="728e8-158">마케팅 전자 메일( 특히 뉴스레터)에는 항상 향후 전자 메일의 구독을 해지하는 방법이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-158">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="728e8-159">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-159">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="728e8-160">일부 보낸 사람은 받는 사람이 제목에 "구독 취소"가 포함된 특정 별칭으로 전자 메일을 보내야 하여 이 옵션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-160">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="728e8-161">이 예제는 위의 한 번 클릭 예제보다는 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-161">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="728e8-162">받는 사람이 메일을 보내야 하도록 선택한 경우 링크를 클릭할 때 필요한 모든 필드가 미리 채워지는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-162">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="728e8-163">마케팅 전자 메일 또는 뉴스레터 등록에 이중 옵트인 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="728e8-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="728e8-164">회사에서 제품 또는 서비스에 액세스하기 위해 사용자에게 연락처 정보를 등록하도록 요구하거나 권장하는 경우 이 업계 모범 사례를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-164">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="728e8-165">일부 회사에서는 등록 프로세스 중에 마케팅 전자 메일 또는 전자 뉴스레터에 사용자를 자동으로 등록하는 것이 관행이지만 이는 전자 메일 필터링 세계에서 의심스러우는 마케팅 사례로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-165">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="728e8-166">등록 프로세스 중에 "예, 뉴스레터 보내기" 또는 "예, 특별 혜택 보내기" 확인란이 기본적으로 선택되어 있는 경우, 주의를 기울이지 않는 사용자는 원치 않는 마케팅 전자 메일 또는 뉴스레터에 의도치 않은 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="728e8-167">대신 이중 옵트인 옵션을 사용하는 것이 좋습니다. 즉, 마케팅 전자 메일 또는 뉴스레터의 확인란은 기본적으로 선택되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-167">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="728e8-168">또한 등록 양식이 제출되면 사용자가 마케팅 전자 메일을 받을지 확인할 수 있는 URL이 있는 확인 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-168">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="728e8-169">이렇게 하면 마케팅 전자 메일을 받으 원하는 사용자만 전자 메일에 등록하여 의심이 많은 전자 메일 마케팅 사례를 보내는 회사를 지우는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="728e8-170">전자 메일 메시지 콘텐츠가 투명하고 추적 가능하도록 보장</span><span class="sxs-lookup"><span data-stu-id="728e8-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="728e8-171">전자 메일이 전송되는 방식만큼 중요한 것은 포함된 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-171">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="728e8-172">전자 메일 콘텐츠를 만들 때 다음과 같은 모범 사례를 사용하여 전자 메일에 전자 메일 필터링 서비스에 의해 플래그가 지정되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-172">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="728e8-173">전자 메일 메시지에서 받는 사람이 주소장에 보낸 사람을 추가하게 요청하는 경우 이러한 작업은 배달 보장이 아 없다고 명확하게 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="728e8-174">메시지 본문에 포함된 리디렉션은 유사하고 일관적일 수 있으며 여러 개가 아니며 다양해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-174">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="728e8-175">이 컨텍스트의 리디렉션은 링크 및 문서와 같이 메시지에서 멀어진 모든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-175">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="728e8-176">광고 또는 구독 취소 링크가 많거나 프로필 링크 업데이트가 있는 경우 모두 동일한 도메인을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-176">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="728e8-177">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-177">For example:</span></span>

  <span data-ttu-id="728e8-178">맞습니다(모든 도메인이 동일).</span><span class="sxs-lookup"><span data-stu-id="728e8-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="728e8-179">올바르지 않습니다(모든 도메인이 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="728e8-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="728e8-180">큰 이미지 및 첨부 파일이 있는 콘텐츠나 이미지로만 구성된 메시지는 피합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="728e8-181">공개 개인 정보 또는 P3P 설정은 추적 픽셀(웹 버그 또는 비콘)의 존재를 명확하게 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="728e8-182">데이터베이스에서 잘못된 전자 메일 별칭 제거</span><span class="sxs-lookup"><span data-stu-id="728e8-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="728e8-183">반송을 만드는 데이터베이스의 전자 메일 별칭은 불필요하며 아웃바운드 전자 메일은 전자 메일 필터링 서비스로 추가적으로 관리해야 할 위험에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-183">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="728e8-184">전자 메일 데이터베이스를 최신으로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="728e8-184">Ensure that your email database is up-to-date.</span></span>