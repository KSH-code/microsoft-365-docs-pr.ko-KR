---
title: 스팸 방지 보호 FAQ
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
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 스팸 방지 보호 기능에 대한 질문과 대답을 볼 수 있습니다.
ms.openlocfilehash: ed871990cf5f8fc4e15995987312fc6814ab8296
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825176"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="81862-103">스팸 방지 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="81862-103">Anti-spam protection FAQ</span></span>

<span data-ttu-id="81862-104">이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직의 맬웨어 방지 보호 기능과 관련한 질문과 답변을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-104">This topic provides frequently asked questions and answers about anti-malware protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="81862-105">격리에 대한 질문과 대답은 [격리 FAQ](quarantine-faq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81862-105">For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>

<span data-ttu-id="81862-106">맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 [방지 보호 FAQ를 참조하세요.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="81862-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="81862-107">스푸핑 방지 보호 기능에 대한 질문과 대답은 [스푸핑 방지 보호 기능 FAQ를 참조하세요.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="81862-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="by-default-what-happens-to-a-spam-detected-message"></a><span data-ttu-id="81862-108">스팸으로 검색된 메시지에 대해 기본적으로 수행되는 작업은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="81862-108">By default, what happens to a spam-detected message?</span></span>

<span data-ttu-id="81862-109">**인바운드 메시지의 경우:** 스팸은 대다수가 원본 전자 메일 서버의 IP 주소를 기반으로 하는 연결 필터링을 통해 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-109">**For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the source email server.</span></span> <span data-ttu-id="81862-110">스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)은 메시지를 스팸, 대량 또는 피싱으로 분류하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-110">Anti-spam policies (also known as spam filter policies or content filter policies) inspect and classify messages as spam, bulk, or phishing.</span></span> <span data-ttu-id="81862-111">기본적으로 스팸 또는 대량으로 분류되는 메시지는 받는 사람의 정크 메일 폴더로 배달되지만 피싱으로 분류된 메시지는 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-111">By default, messages that are classified as spam or bulk are delivered to the recipient's Junk Email folder, while messages classified as phishing are quarantined.</span></span> <span data-ttu-id="81862-112">기본 스팸 방지 정책을 수정하거나(모든 받는 사람에게 적용) 특정 사용자 그룹의 더 빠른 설정을 사용하여 사용자 지정 스팸 방지 정책을 만들 수 있습니다(예: 중역에게 전송되는 스팸을 격리할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="81862-112">You can modify the default anti-spam policy (applies to all recipients), or you can create custom anti-spam policies with stricter settings for specific groups of users (for example, you can quarantine spam that's sent to executives).</span></span> <span data-ttu-id="81862-113">자세한 내용은 스팸 [방지 정책 구성 및 권장 스팸](configure-your-spam-filter-policies.md) 방지 정책 [설정을 참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="81862-113">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Recommended anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81862-114">EOP가 온-프레미스 사서함을 보호하는 하이브리드 배포에서는 메시지에 추가된 EOP 스팸 필터링 헤더를 검색하도록 온-프레미스 Exchange 조직에서 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)을 두 개 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-114">In hybrid deployments where EOP protects on-premises mailboxes, you need to configure two Exchange mail flow rules (also known as transport rules) in your on-premises Exchange organization to detect the EOP spam filtering headers that are added to messages.</span></span> <span data-ttu-id="81862-115">자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81862-115">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

 <span data-ttu-id="81862-116">**아웃바운드 메시지의 경우:** 메시지는 고위험 배달 [풀을 통해 라우팅되거나](high-risk-delivery-pool-for-outbound-messages.md) 배달 못 함 보고서(NDR 또는 반송 메시지라고도 함)의 보낸 사람에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-116">**For outbound messages:** The message is either routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) or is returned to the sender in a non-delivery report (also known as an NDR or bounce message).</span></span> <span data-ttu-id="81862-117">아웃바운드 스팸 보호 기능에 대한 자세한 내용은 아웃바운드 스팸 [컨트롤을 참조하세요.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="81862-117">For more information about outbound spam protection, see [Outbound spam controls](outbound-spam-controls.md).</span></span>

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a><span data-ttu-id="81862-118">제로 데이 스팸 변형이란 무엇이며 서비스에서 어떻게 처리되나요?</span><span class="sxs-lookup"><span data-stu-id="81862-118">What's a zero-day spam variant and how is it handled by the service?</span></span>

<span data-ttu-id="81862-119">제로 데일 스팸 변형은 1세대, 이전에 캡처 또는 분석되지 않은, 스팸을 알 수 없는 일반 변형으로, 스팸 방지 필터에는 검색에 사용할 수 있는 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-119">A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our anti-spam filters don't yet have any information available for detecting it.</span></span> <span data-ttu-id="81862-120">스팸 분석가가 0일 스팸 샘플을 캡처 및 분석한 후 스팸 분류 기준을 충족하는 경우 스팸 방지 필터가 이를 검색하도록 업데이트되며 더 이상 "제로 데일"로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-120">After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our anti-spam filters are updated to detect it, and it's no longer considered "zero-day."</span></span>

<span data-ttu-id="81862-121">**참고:** 서비스 개선을 위해 제로 데이 스팸 변형이 될 수 있는 메시지를 받은 경우 Microsoft에 등의 방법 중 하나를 사용하여 [Microsoft에 메시지를 제출하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="81862-121">**Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a><span data-ttu-id="81862-122">스팸 방지 보호 기능을 제공하도록 서비스를 구성해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="81862-122">Do I need to configure the service to provide anti-spam protection?</span></span>

<span data-ttu-id="81862-123">서비스에 등록하고 도메인을 추가하고 고면 스팸 필터링이 자동으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-123">After you sign up for the service and add your domain, spam filtering is automatically enabled.</span></span> <span data-ttu-id="81862-124">기본적으로 스팸 필터링은 추가 구성 없이도 사용자를 보호할 수 있도록 모니터링됩니다(이전에 하이브리드 환경에서 독립 실행형 EOP 독립 실행형 고객의 경우 주목해야 할 예외와 달리).</span><span class="sxs-lookup"><span data-stu-id="81862-124">By default, spam filtering is tuned to protect you without needing any additional configuration (aside from the previously noted exception for standalone EOP standalone customers in hybrid environments).</span></span> <span data-ttu-id="81862-125">관리자는 조직의 요구 사항에 가장 잘 맞게 기본 스팸 필터링 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-125">As an admin, you can edit the default spam filtering settings to best meet the needs of your organization.</span></span> <span data-ttu-id="81862-126">세분성을 크게 위해 조직의 지정된 사용자, 그룹 또는 도메인에 적용되는 스팸 방지 정책 및 아웃바운드 스팸 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-126">For greater granularity, you can also create anti-spam policies and outbound anti-spam policies that are applied to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="81862-127">사용자 지정 정책은 항상 기본 정책보다 우선하지만 사용자 지정 정책의 우선 순위(즉, 실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-127">Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>

<span data-ttu-id="81862-128">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81862-128">For more information, see the following topics:</span></span>

[<span data-ttu-id="81862-129">EOP 및 Office 365 ATP 보안에 대한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="81862-129">Recommended settings for EOP and Office 365 ATP security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

[<span data-ttu-id="81862-130">EOP에서 연결 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="81862-130">Configure connection filtering in EOP</span></span>](configure-the-connection-filter-policy.md)

[<span data-ttu-id="81862-131">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="81862-131">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="81862-132">아웃바운드 스팸 정책 구성</span><span class="sxs-lookup"><span data-stu-id="81862-132">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a><span data-ttu-id="81862-133">스팸 방지 정책을 변경하는 경우 저장한 변경 내용이 적용될 때까지 시간이 얼마나 걸립니까?</span><span class="sxs-lookup"><span data-stu-id="81862-133">If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?</span></span>

<span data-ttu-id="81862-134">변경 내용이 적용되기까지 최대 1시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-134">It may take up to 1 hour for the changes to take effect.</span></span>

## <a name="is-bulk-email-filtering-automatically-enabled"></a><span data-ttu-id="81862-135">대량 전자 메일 필터링은 자동으로 사용하도록 설정됩니까?</span><span class="sxs-lookup"><span data-stu-id="81862-135">Is bulk email filtering automatically enabled?</span></span>

<span data-ttu-id="81862-136">예.</span><span class="sxs-lookup"><span data-stu-id="81862-136">Yes.</span></span> <span data-ttu-id="81862-137">대량 전자 메일에 대한 자세한 내용은 정크 메일과 대량 전자 메일의 [차이점을 확인하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="81862-137">For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

## <a name="does-the-service-provide-url-filtering"></a><span data-ttu-id="81862-138">서비스에서 URL 필터링 기능을 제공합니까?</span><span class="sxs-lookup"><span data-stu-id="81862-138">Does the service provide URL filtering?</span></span>

<span data-ttu-id="81862-139">예. 서비스에는 메시지 내의 URL을 확인하는 URL 필터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-139">Yes, the service has a URL filter that checks for URLs within messages.</span></span> <span data-ttu-id="81862-140">URL이 알려진 스팸이나 악성 콘텐츠에 연결된 경우 메시지는 스팸으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-140">If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a><span data-ttu-id="81862-141">서비스를 사용하는 고객이 거짓 부정(스팸) 및 가양성(스팸 아님) 메시지를 Microsoft로 보내려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="81862-141">How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?</span></span>

<span data-ttu-id="81862-142">스팸 및 스팸이 아닌 메시지는 분석을 위해 여러 가지 방법으로 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-142">Spam and non-spam messages can be submitted to Microsoft for analysis in several ways.</span></span> <span data-ttu-id="81862-143">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81862-143">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="can-i-get-spam-reports"></a><span data-ttu-id="81862-144">스팸 보고서를 확인할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="81862-144">Can I get spam reports?</span></span>

<span data-ttu-id="81862-145">예를 들어 Microsoft 365 관리 센터에서 스팸 검색 보고서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-145">Yes, for example you can get a spam detection report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="81862-146">이 보고서에는 스팸 볼륨이 고유한 메시지의 수로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-146">This report shows spam volume as a count of unique messages.</span></span> <span data-ttu-id="81862-147">보고에 대한 자세한 내용은 다음 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81862-147">For more information about reporting, see the following links:</span></span>

<span data-ttu-id="81862-148">Exchange Online [고객: Exchange Online의 모니터링, 보고 및 메시지 추적](https://docs.microsoft.com/exchange/monitoring/monitoring)</span><span class="sxs-lookup"><span data-stu-id="81862-148">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)</span></span>

<span data-ttu-id="81862-149">독립 실행형 EOP 고객: [Exchange Online Protection의 보고 및 메시지 추적](reporting-and-message-trace-in-exchange-online-protection.md)</span><span class="sxs-lookup"><span data-stu-id="81862-149">Standalone EOP customers: [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)</span></span>

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a><span data-ttu-id="81862-150">전송된 메시지를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-150">Someone sent me a message and I can't find it.</span></span> <span data-ttu-id="81862-151">스팸으로 검색된 되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-151">I suspect that it may have been detected as spam.</span></span> <span data-ttu-id="81862-152">로그아웃하는 데 사용할 수 있는 도구가 있나요?</span><span class="sxs-lookup"><span data-stu-id="81862-152">Is there a tool that I can use to find out?</span></span>

<span data-ttu-id="81862-153">예. 메시지 추적 도구를 사용하면 서비스를 통과하는 전자 메일 메시지를 추적하여 메시지에 수행된 작업을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-153">Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them.</span></span> <span data-ttu-id="81862-154">메시지 추적 도구를 사용하여 메시지가 스팸으로 표시된 이유를 확인하는 방법에 대한 자세한 내용은 [메시지가 스팸으로 표시되었습니까?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span><span class="sxs-lookup"><span data-stu-id="81862-154">For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span></span>

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a><span data-ttu-id="81862-155">사용자가 아웃바운드 스팸을 보내면 서비스에서 메일을 제한합니까(속도 제한)</span><span class="sxs-lookup"><span data-stu-id="81862-155">Will the service throttle (rate limit) my mail if my users send outbound spam?</span></span>

<span data-ttu-id="81862-156">특정 시간 내에 서비스를 통해 서비스를 통해 전송된 메일의 1/0/2페이지보다 많은 메일이 EOP의 스팸으로 확인되는 경우 사용자는 메시지 보내기가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-156">If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by EOP, the user will be blocked from sending messages.</span></span> <span data-ttu-id="81862-157">대부분의 경우 아웃바운드 메시지가 스팸으로 확인되면 위험성이 높은 배달 풀을 통해 라우팅되므로 일반 아웃바운드 IP 풀이 차단 목록에 추가될 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="81862-157">In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>

<span data-ttu-id="81862-158">보낸 사람이 아웃바운드 스팸을 보낼 수 없도록 차단된 경우 지정된 전자 메일 주소로 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-158">You can send a notification to a specified email address when a sender is blocked sending outbound spam.</span></span> <span data-ttu-id="81862-159">이 설정에 대한 자세한 내용은 아웃바운드 [스팸 정책 구성을 참조하세요.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="81862-159">For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a><span data-ttu-id="81862-160">타사 스팸 방지 및 맬웨어 방지 공급자와 Exchange Online을 함께 사용할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="81862-160">Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?</span></span>

<span data-ttu-id="81862-161">예.</span><span class="sxs-lookup"><span data-stu-id="81862-161">Yes.</span></span> <span data-ttu-id="81862-162">MX 레코드는 Microsoft를 가리키는 것이 권장되지만 전자 메일을 Microsoft 이외의 다른 위치로 라우팅할 수 있는 합법한 업무상의 이유가 있다는 사실을 인식하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-162">Although we recommend that you point your MX record to Microsoft, we realize that there are legitimate business reasons to route your email to somewhere other than Microsoft first.</span></span>

- <span data-ttu-id="81862-163">**인바운드:** 타사 공급자를 가리키도록 MX 레코드를 변경한 다음 추가 처리를 위해 EOP로 메시지를 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-163">**Inbound**: Change your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing.</span></span> <span data-ttu-id="81862-164">자세한 내용은 [Exchange Online에서 커넥터에 대한 향상된 필터링을 참조하세요.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="81862-164">For more information, see [Enhanced Filtering for connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="81862-165">**아웃바운드:** Microsoft 365에서 대상 타사 공급자로스마트 호스트 라우팅을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-165">**Outbound**: Configure smart host routing from Microsoft 365 to the destination third-party provider.</span></span>

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a><span data-ttu-id="81862-166">Microsoft에 피싱 메일로부터 자기 자신을 보호할 수 있는 방법에 대한 설명서가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="81862-166">Does Microsoft have any documentation about how I can protect myself from phishing scams?</span></span>

<span data-ttu-id="81862-167">예.</span><span class="sxs-lookup"><span data-stu-id="81862-167">Yes.</span></span> <span data-ttu-id="81862-168">자세한 내용은 [인터넷에서의 개인 정보 보호를 참조하세요.](https://support.microsoft.com/help/4091455)</span><span class="sxs-lookup"><span data-stu-id="81862-168">For more information, see [Protect your privacy on the internet](https://support.microsoft.com/help/4091455)</span></span>

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a><span data-ttu-id="81862-169">스팸 및 맬웨어 메시지의 경우 보낸 사람을 조사하거나 법 집행 기관으로 전송됩니까?</span><span class="sxs-lookup"><span data-stu-id="81862-169">Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?</span></span>

<span data-ttu-id="81862-170">이 서비스는 스팸 및 맬웨어 감지 및 제거에 중점을 두고 있습니다. 하지만 가까운 위험하거나 스팸 또는 공격 캠페인을 조사하여 영구력을 피할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-170">The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators.</span></span> <span data-ttu-id="81862-171">이 작업에는 법률 및 디지털 범근 단위로 작업하여 스패머 봇을 취하고, 스패머가 서비스를 사용하지 못하도록 차단(아웃바운드 전자 메일을 보내는 데 사용하는 경우)하고, 법적 프로스트에 정보를 제공하여 법적으로 출시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-171">This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a><span data-ttu-id="81862-172">메일 배달을 보장할 수 있는 가장 좋은 아웃바운드 메일 보내기 방법은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="81862-172">What are a set of best outbound mailing practices that will ensure that my mail is delivered?</span></span>

<span data-ttu-id="81862-173">아래에 나와 있는 지침이 아웃바운드 전자 메일 메시지를 보내는 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="81862-173">The guidelines presented below are best practices for sending outbound email messages.</span></span>

- <span data-ttu-id="81862-174">**DNS에서 원본 전자 메일 도메인을 확인해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-174">**The source email domain should resolve in DNS.**</span></span>

  <span data-ttu-id="81862-175">예를 들어 보낸 사람이 조직user@fabrikam fabrikam이 IP 주소 192.0.43.10으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-175">For example, if the sender is user@fabrikam, the domain fabrikam resolves to the IP address 192.0.43.10.</span></span>
  
  <span data-ttu-id="81862-176">보내는 도메인의 A 레코드와 MX 레코드가 DNS에 없으면 서비스에서는 메시지 내용이 스팸인지 여부에 관계없이 위험성이 높은 배달 풀을 통하여 해당 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-176">If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam.</span></span> <span data-ttu-id="81862-177">위험성이 배달 풀에 대한 자세한 내용은 아웃바운드 [메시지에 대한 위험성이 높은 배달 풀을 참조하세요.](high-risk-delivery-pool-for-outbound-messages.md)</span><span class="sxs-lookup"><span data-stu-id="81862-177">For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="81862-178">**아웃바운드 메일 전자 메일 전자 메일에는 역방향 DNS(PTR) 항목이 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-178">**Outbound mail eserver should have a reverse DNS (PTR) entry.**</span></span>

  <span data-ttu-id="81862-179">예를 들어 전자 메일 원본 IP 주소가 192.0.43.10이면 역방향 DNS 항목이 `43-10.any.icann.org` .'인 경우</span><span class="sxs-lookup"><span data-stu-id="81862-179">For example, if the email source IP address is 192.0.43.10, the reverse DNS entry would be `43-10.any.icann.org`.\`</span></span>

- <span data-ttu-id="81862-180">**HELO/EHLO 및 MAIL FROM 명령은 일관성이 있어야 하며 IP 주소가 아닌 도메인 이름 형식으로 지정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-180">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>

  <span data-ttu-id="81862-181">HELO/EHLO 명령은 보내는 IP 주소의 역방향 DNS와 일치하도록 구성해야 합니다. 그래야 메시지 헤더의 여러 부분에서 도메인이 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="81862-181">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>

- <span data-ttu-id="81862-182">**DNS에서 적절한 SPF 레코드를 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-182">**Ensure that proper SPF records are set up in DNS.**</span></span>

  <span data-ttu-id="81862-p119">SPF 레코드는 도메인에서 전송된 메일이 실제로 해당 도메인에서 보낸 것이며 스푸핑되지 않았음을 검사하는 메커니즘입니다. SPF 레코드에 대한 자세한 내용은 다음 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81862-p119">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>

  [<span data-ttu-id="81862-185">스푸핑을 방지할 수 있도록 SPF 설정</span><span class="sxs-lookup"><span data-stu-id="81862-185">Set up SPF to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [<span data-ttu-id="81862-186">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="81862-186">Domains FAQ</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- <span data-ttu-id="81862-187">**DKIM으로 전자 메일에 서명을 하는 경우 낮은 수준의 정규화로 서명합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-187">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>

  <span data-ttu-id="81862-p120">보낸 사람은 DKIM(Domain Keys Identified Mail)을 사용하여 메시지에 서명을 하고 서비스를 통해 아웃바운드 메일을 보내려는 경우 낮은 수준의 헤더 정규화 알고리즘을 사용하여 서명해야 합니다. 엄격한 헤더 정규화를 사용하여 서명을 하면 메시지가 서비스를 통과할 때 서명이 무효화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-p120">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>

- <span data-ttu-id="81862-190">**도메인 소유자는 WHOIS 데이터베이스에 정확한 정보를 포함해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-190">**Domain owners should have accurate information in the WHOIS database.**</span></span>

  <span data-ttu-id="81862-191">이렇게 하면 고정된 모회사, 담당자 및 이름 서버를 입력함으로써 도메인 소유자 및 소유자에게 연락하는 방법을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-191">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>

- <span data-ttu-id="81862-192">**대량 메일러의 경우 보낸 사람: 이름이 메시지를 보내는 사람을 반영해야 하며 메시지의 제목 줄은 메시지 내용에 대한 간략한 요약을 포함해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-192">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>

  <span data-ttu-id="81862-p121">메시지 본문에는 제공 사항, 서비스 또는 제품이 명확하게 표시되어 있어야 합니다. 예를 들어 보낸 사람이 Contoso라는 회사를 위해 대량의 메일을 보내는 경우 전자 메일의 보낸 사람 및 제목은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-p121">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>

  > <span data-ttu-id="81862-195">보낸 사람: marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="81862-195">From: marketing@contoso.com</span></span> <br/> <span data-ttu-id="81862-196">제목: 업데이트된 크리스마스 시즌용 신규 카탈로그!</span><span class="sxs-lookup"><span data-stu-id="81862-196">Subject: New updated catalog for the Christmas season!</span></span>

  <span data-ttu-id="81862-197">다음은 대량 메일임을 충분히 설명하지 않으므로 부적합한 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="81862-197">The following is an example of what not to do because it is not descriptive:</span></span>

  > <span data-ttu-id="81862-198">보낸 사람: user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="81862-198">From: user@hotmail.com</span></span> <br/> <span data-ttu-id="81862-199">제목: 카탈로그</span><span class="sxs-lookup"><span data-stu-id="81862-199">Subject: Catalogs</span></span>

- <span data-ttu-id="81862-200">**뉴스레터 형식의 메시지를 많은 수의 받는 사람에게 대량 메일로 보내는 경우에는 메시지 아래쪽에 구독을 취소할 수 있는 수단이 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-200">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>

  <span data-ttu-id="81862-201">다음과 같은 구독 취소 옵션을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-201">The unsubscribe option should resemble the following:</span></span>

  > <span data-ttu-id="81862-202">이 메시지는 sender@fabrikam.com에서 example.@contoso.com으로 전송된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81862-202">This message was sent to example@contoso.com by sender@fabrikam.com.</span></span> <span data-ttu-id="81862-203">프로필/전자 메일 주소 업데이트 | **SafeUnsubscribe로 즉시 제거** &trade; | 개인 정보 취급 방침</span><span class="sxs-lookup"><span data-stu-id="81862-203">Update Profile/Email Address | Instant removal with **SafeUnsubscribe**&trade; | Privacy Policy</span></span>

- <span data-ttu-id="81862-204">**대량 전자 메일을 보내는 경우에는 이중 옵트인(opt in)을 통해 목록을 확보해야 합니다. 이중 옵트인(opt in)은 대량 메일러에 대한 업계 모범 사례입니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-204">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>

  <span data-ttu-id="81862-205">이중 옵트인(opt in)은 사용자가 마케팅 메일을 신청할 때 두 가지 작업을 수행하도록 요구하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="81862-205">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>

  1. <span data-ttu-id="81862-206">먼저, 사용자는 이전에는 선택하지 않았던 확인란을 클릭하여 마케팅 업체의 서비스 또는 전자 메일 메시지를 계속 받도록 옵트인(opt in)합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-206">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>

  2. <span data-ttu-id="81862-207">다음으로, 사용자가 입력한 전자 메일 주소로 마케팅 업체가 확인 전자 메일을 보내 사용자가 일정 시간 이내에 링크를 클릭하여 확인을 완료하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-207">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>

  <span data-ttu-id="81862-208">이중 옵트인(opt in)을 사용하는 경우 대량 전자 메일 보낸 사람의 신뢰도가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="81862-208">Using double opt-in builds a good reputation for bulk email senders.</span></span>

- <span data-ttu-id="81862-209">**대량 전자 메일 보낸 사람은 책임질 수 있는 명확한 콘텐츠를 작성해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-209">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>

  1. <span data-ttu-id="81862-210">받는 사람이 보낸 사람을 주소록에 추가하도록 요청하는 장문의 메시지에서는 해당 작업을 수행해도 배달이 보장되지는 않음을 명확하게 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-210">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>

  2. <span data-ttu-id="81862-211">메시지 본문에 리디렉션을 구성하는 경우에는 일관성 있는 링크 스타일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-211">When constructing redirects in the body of the message, use a consistent link style.</span></span>

  3. <span data-ttu-id="81862-212">큰 이미지나 첨부 파일, 또는 이미지로만 구성된 메시지를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-212">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>

  4. <span data-ttu-id="81862-213">추적 픽셀(웹 버그 또는 탐지 장치)을 사용할 때는 공개 개인 정보 또는 P3P 설정에서 그러한 항목이 있음을 명기합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-213">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>

- <span data-ttu-id="81862-214">**아웃바운드 반송 메시지 형식을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-214">**Format outbound bounce messages.**</span></span>

  <span data-ttu-id="81862-215">배달 상태 알림 메시지(배달 못 함 보고서, NDR 또는 반송 메시지라고도 함)를 생성할 때 보낸 사람은 [RFC 3464에](https://www.ietf.org/rfc/rfc3464.txt)지정된 반송 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81862-215">When generating delivery status notification messages (also known as non-delivery reports, NDRs, or bounce messages), senders should follow the format of a bounce as specified in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).</span></span>

- <span data-ttu-id="81862-216">**존재하지 않는 사용자의 반송된 전자 메일 주소를 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-216">**Remove bounced email addresses for non-existent users.**</span></span>

  <span data-ttu-id="81862-p123">전자 메일 주소가 더 이상 사용되지 않음을 나타내는 NDR을 받으면 존재하지 않는 전자 메일 별칭을 목록에서 제거합니다. 전자 메일 주소는 시간이 지남에 따라 변경되며, 주소를 삭제하는 사용자도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81862-p123">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>

- <span data-ttu-id="81862-219">**Hotmail의 SNDS(Smart Network Data Services) 프로그램을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="81862-219">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>

  <span data-ttu-id="81862-p124">Hotmail에서는 최종 사용자가 전송한 불만 사항을 보낸 사람이 확인할 수 있도록 하는 Smart Network Data Services라는 프로그램을 사용합니다. SNDS는 Hotmail에 대한 배달 문제 해결을 위한 기본 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="81862-p124">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>
