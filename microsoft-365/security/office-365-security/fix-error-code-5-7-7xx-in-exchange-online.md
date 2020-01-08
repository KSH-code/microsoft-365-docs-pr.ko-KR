---
title: Exchange Online에서 오류 코드 5.7.7 xx에 해당 하는 전자 메일 배달 문제 수정
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online에서 오류 코드 5.7.7 xx의 전자 메일 문제를 해결 하는 방법에 대해 알아봅니다 (테 넌 트 차단 됨).
ms.openlocfilehash: cbfff7fc0905206a0302f7e1a458718637d934b7
ms.sourcegitcommit: 8ac1b6586678035050fc422e6fb503fa478be397
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962307"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="a4f7d-103">Exchange Online에서 오류 코드 5.7.7 xx에 해당 하는 전자 메일 배달 문제 수정</span><span class="sxs-lookup"><span data-stu-id="a4f7d-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="a4f7d-104">이 항목에서는 배달 못 함 보고서 (NDR, 바운스 메시지, 배달 상태 알림 또는 DSN이 라고도 함)에 상태 코드 550 5.7.7 xx가 표시 되는 경우에 수행할 수 있는 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="a4f7d-105">테 넌 트가 단방향 이나 다른 방법으로 전자 메일을 보낼 수 없도록 제한 되 면이 자동 알림을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="a4f7d-106">이러한 오류 코드는 대개 705 또는 750로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="a4f7d-107">5.7.705: 테 넌 트가 임계값 제한을 초과 했습니다. 확인 해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="a4f7d-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="a4f7d-108">사용자가 서비스를 통해 의심 스러운 전자 메일을 보내는 경우에는 문제가 해결 될 때까지 모든 사용자가 전자 메일을 보내지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-108">Once your users (collectively, as organization) send a certain amount of suspicious email through the service, all users can be prevented from sending any email until the problem is fixed.</span></span> <span data-ttu-id="a4f7d-109">일반적으로 손상 (가장 일반적인)을 하거나 너무 많은 대량 메일을 보내는 경우이 결과가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-109">This is usually the result of a compromise (most common) or sending too much bulk mail.</span></span> <span data-ttu-id="a4f7d-110">사용자에 게 다음을 알리는 NDR이 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-110">Users will receive an NDR that states:</span></span>

`550 5.7.705 Access denied, tenant has exceeded threshold`

<span data-ttu-id="a4f7d-111">드물지만 구독을 이미 만료 한 후 갱신 하는 경우에도 이러한 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-111">In rare cases, this could also happen if you renew your subscription after it has already expired.</span></span> <span data-ttu-id="a4f7d-112">서비스가 새 구독 정보를 동기화 하는 데 시간이 걸리지만 (대개 하루 이상) 조직에서 전자 메일을 보낼 수 없도록 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-112">It takes time for the service to sync the new subscription information (typically, no more than one day), but your organization could be blocked from sending email in the meantime.</span></span> <span data-ttu-id="a4f7d-113">이를 방지 하는 가장 좋은 방법은 구독이 만료 되지 않았는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-113">The best way to prevent this is to make sure your subscription does not expire.</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="a4f7d-114">5.7.750: 등록 되지 않은 도메인 전자 메일 제한: 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="a4f7d-114">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="a4f7d-115">Office 365을 사용 하면 테 넌 트에서 Exchange Online Protection (EOP)을 통해 일부 메시지를 릴레이할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-115">Office 365 allows tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a4f7d-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-116">For example:</span></span>

- <span data-ttu-id="a4f7d-117">Office 365 사서함은 외부 보낸 사람 으로부터 전자 메일을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-117">An Office 365 mailbox receives email from an external sender.</span></span> <span data-ttu-id="a4f7d-118">메일 전달은 Office 365 사서함에서 구성 되므로 메시지가 사용자의 외부 전자 메일 주소로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-118">Mail forwarding is configured on the Office 365 mailbox, so the message goes back out to the user's external email address.</span></span> <span data-ttu-id="a4f7d-119">이 시나리오는 학생 들이 자신의 개인 전자 메일 계정을 사용 하 여 학교 관련 메시지를 볼 수 있도록 하려는 교육 환경에서 가장 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-119">This scenario is most common in education environments where students want to use their personal email accounts to view school-related messages.</span></span>

- <span data-ttu-id="a4f7d-120">EOP를 통해 보내는 메일을 보내는 온-프레미스 전자 메일 서버가 있는 하이브리드 envrionments</span><span class="sxs-lookup"><span data-stu-id="a4f7d-120">Hybrid envrionments that have on-premises email servers that send outgoing mail through EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="a4f7d-121">등록 되지 않은 도메인 문제</span><span class="sxs-lookup"><span data-stu-id="a4f7d-121">Problems with unregistered domains</span></span>

<span data-ttu-id="a4f7d-122">문제는 온-프레미스 전자 메일 서버가 EOP를 통해 대용량의 스팸을 릴레이할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-122">The problem is when compromised on-premises email servers relay a large volume of spam through EOP.</span></span> <span data-ttu-id="a4f7d-123">거의 모든 경우에 커넥터는 제대로 설정 되지만 등록 되지 않은 도메인 (구축 되지 않음)에서 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-123">In almost all cases, the connectors are set up correctly, but email is being sent from unregistered (also known as unprovisioned) domains.</span></span> <span data-ttu-id="a4f7d-124">Office 365에서는 등록 되지 않은 도메인에서 적절 한 전자 메일을 받을 수 있지만, 전자 메일을 보내는 데 사용 하는 모든 도메인을 허용 도메인으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-124">Office 365 allows a reasonable amount of email from unregistered domains, but you should configure every domain that you use to send email as an accepted domain.</span></span>

<span data-ttu-id="a4f7d-125">일단 손상 되 면 테 넌 트가 등록 되지 않은 도메인에서 아웃 바운드 전자 메일을 보낼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-125">Once compromised, tenants will be prevented from sending outbound email for unregistered domains.</span></span> <span data-ttu-id="a4f7d-126">사용자에 게 다음을 알리는 NDR이 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-126">Users will receive an NDR that states:</span></span>

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="a4f7d-127">다시 보내기 위해 테 넌 트의 차단을 해제 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a4f7d-127">How to unblocking tenant in order to send again</span></span>

<span data-ttu-id="a4f7d-128">테 넌 트가 전자 메일을 보내지 못하도록 차단 된 경우에는 몇 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-128">There are several things you need to do if your tenant is blocked from sending email:</span></span>

1. <span data-ttu-id="a4f7d-129">모든 전자 메일 도메인이 등록 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-129">Verify that all of your email domains are registered.</span></span> <span data-ttu-id="a4f7d-130">자세한 내용은 Exchange Online에서 [Office 365에 도메인 추가](https://docs.microsoft.com/office365/admin/setup/add-domain) 및 [허용 도메인 관리](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) and [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="a4f7d-131">비정상적인 [커넥터](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-131">Look for unusual [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> <span data-ttu-id="a4f7d-132">악의적인 행위자는 종종 Office 365 조직에서 새 인바운드 커넥터를 만들어 스팸을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-132">Malicious actors will often create new inbound connectors in your Office 365 organization to send spam.</span></span> <span data-ttu-id="a4f7d-133">기존 커넥터를 보려면 [Office 365에서 커넥터 유효성 검사](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-133">To view your existing connectors, see [Validate connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).</span></span>

3. <span data-ttu-id="a4f7d-134">[Office 365에서 손상 된 전자 메일 계정에 응답 하는](responding-to-a-compromised-email-account.md)것으로 설명 되어 있는 사용자가 손상 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-134">Check for compromised users as described in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

4. <span data-ttu-id="a4f7d-135">Office 365 조 직의 모든 관리자에 대해 [MFA를 사용 하도록 설정](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-135">[Enable MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) for all admins in your Office 365 organization.</span></span>

5. <span data-ttu-id="a4f7d-136">온-프레미스 전자 메일 서버를 잠그고 해당 서버가 손상 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-136">Lock down your on-premises email servers and verify that they are not compromised.</span></span>

   > [!TIP]
   > <span data-ttu-id="a4f7d-137">특히 타사 서버를 사용 하는 경우에는 여러 가지 요인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-137">There are many factors here, especially if you're using third-party servers.</span></span> <span data-ttu-id="a4f7d-138">모든 경우에는 이제 모든 보내는 전자 메일이 합법적 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-138">Regardless, you'll need to verify that all of your outgoing email is now legitimate.</span></span>

6. <span data-ttu-id="a4f7d-139">Microsoft 지원 서비스에 문의 하 여 등록 되지 않은 도메인에서 다시 보내기 위해 테 넌 트의 차단을 해제 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-139">Call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span> <span data-ttu-id="a4f7d-140">오류 코드가 도움이 되지만 사용자 환경에 대 한 보안이 유지 되 고 스팸 메일을 보낼 수 없다는 사실을 입증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-140">The error code is helpful, but you'll need to prove that your environment has been secured and is incapable of sending spam.</span></span> <span data-ttu-id="a4f7d-141">지원 사례를 열려면 [비즈니스 제품에 대 한 지원 문의-관리자 도움말](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-141">To open a support case, see [Contact support for business products - Admin Help](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a4f7d-142">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="a4f7d-142">For more information</span></span>

[<span data-ttu-id="a4f7d-143">Office 365의 전자 메일 스팸 방지 및 보호</span><span class="sxs-lookup"><span data-stu-id="a4f7d-143">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="a4f7d-144">Exchange Online 서비스 설명의 보내는 제한 섹션에 있는 대량 메일 지침</span><span class="sxs-lookup"><span data-stu-id="a4f7d-144">Bulk Mail guidance in the sending limits section of the Exchange Online service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[<span data-ttu-id="a4f7d-145">Office 365의 전자 메일 배달 못 함 보고서(NDR)</span><span class="sxs-lookup"><span data-stu-id="a4f7d-145">Email non-delivery reports in Office 365</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[<span data-ttu-id="a4f7d-146">사서함의 전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="a4f7d-146">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="a4f7d-147">Office 365를 사용하여 전자 메일을 보내도록 다기능 장치 또는 응용 프로그램을 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="a4f7d-147">How to set up a multifunction device or application to send email using Office 365</span></span>](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

<span data-ttu-id="a4f7d-148">[Exchange Online에서 허용 도메인을 관리](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f7d-148">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
