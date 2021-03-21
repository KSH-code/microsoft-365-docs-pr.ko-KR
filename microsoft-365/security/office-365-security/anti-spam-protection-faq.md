---
title: 스팸 방지 보호 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 스팸 방지 보호에 대한 질문과 대답을 볼 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc1aa26832830dce4f529566a589cb8bf3e1df01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925223"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="77245-103">스팸 방지 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="77245-103">Anti-spam protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="77245-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="77245-104">**Applies to**</span></span>
- [<span data-ttu-id="77245-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="77245-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="77245-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="77245-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="77245-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77245-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="77245-108">이 항목에서는 Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직을 위한 맬웨어 방지 보호에 대한 질문과 대답을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-108">This topic provides frequently asked questions and answers about anti-malware protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="77245-109">격리에 대한 질문과 대답은 [격리 FAQ](quarantine-faq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77245-109">For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>

<span data-ttu-id="77245-110">맬웨어 방지 보호에 대한 질문과 대답은 맬웨어 방지 보호 [FAQ 를 참조하세요.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="77245-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="77245-111">스푸핑 방지 보호에 대한 질문과 대답은 스푸핑 방지 보호 [FAQ를 참조하세요.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="77245-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="by-default-what-happens-to-a-spam-detected-message"></a><span data-ttu-id="77245-112">스팸으로 검색된 메시지에 대해 기본적으로 수행되는 작업은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="77245-112">By default, what happens to a spam-detected message?</span></span>

<span data-ttu-id="77245-113">**인바운드 메시지의 경우:** 스팸은 대부분 원본 전자 메일 서버의 IP 주소를 기반으로 하는 연결 필터링을 통해 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-113">**For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the source email server.</span></span> <span data-ttu-id="77245-114">스팸 방지 정책(스팸 필터 정책 또는 콘텐츠 필터 정책)은 메시지를 스팸, 대량 또는 피싱으로 검사하고 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-114">Anti-spam policies (also known as spam filter policies or content filter policies) inspect and classify messages as spam, bulk, or phishing.</span></span> <span data-ttu-id="77245-115">기본적으로 스팸 또는 대량으로 분류된 메시지는 받는 사람의 정크 메일 폴더로 배달되는 반면 피싱으로 분류된 메시지는 스팸으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-115">By default, messages that are classified as spam or bulk are delivered to the recipient's Junk Email folder, while messages classified as phishing are quarantined.</span></span> <span data-ttu-id="77245-116">기본 스팸 방지 정책을 수정하거나(모든 받는 사람에게 적용) 특정 사용자 그룹에 대해 더 엄격한 설정을 사용하여 사용자 지정 스팸 방지 정책을 만들 수 있습니다(예: 임원에게 전송된 스팸을 검지할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="77245-116">You can modify the default anti-spam policy (applies to all recipients), or you can create custom anti-spam policies with stricter settings for specific groups of users (for example, you can quarantine spam that's sent to executives).</span></span> <span data-ttu-id="77245-117">자세한 내용은 [스팸](configure-your-spam-filter-policies.md) 방지 정책 구성 및 권장되는 스팸 [방지 정책 설정 을 참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="77245-117">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Recommended anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77245-118">EOP가 사내 사서함을 보호하는 하이브리드 배포에서는 메시지에 추가된 EOP 스팸 필터링 헤더를 검색하도록 두 개의 Exchange 메일 흐름 규칙(전송 규칙)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-118">In hybrid deployments where EOP protects on-premises mailboxes, you need to configure two Exchange mail flow rules (also known as transport rules) in your on-premises Exchange organization to detect the EOP spam filtering headers that are added to messages.</span></span> <span data-ttu-id="77245-119">자세한 내용은 [하이브리드 환경에서 스팸을 정크 메일 폴더로 배달하도록 독립 실행형 EOP 구성하기](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77245-119">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

 <span data-ttu-id="77245-120">**아웃바운드 메시지의 경우:** 이 메시지는 위험이 높은 [](high-risk-delivery-pool-for-outbound-messages.md) 배달 풀을 통해 라우팅되거나 배달되지 않은 보고서(NDR 또는 반송 메시지라고도 알려지음)에서 보낸 사람으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-120">**For outbound messages:** The message is either routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) or is returned to the sender in a non-delivery report (also known as an NDR or bounce message).</span></span> <span data-ttu-id="77245-121">아웃바운드 스팸 보호에 대한 자세한 내용은 [아웃바운드 스팸 컨트롤을 참조하세요.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="77245-121">For more information about outbound spam protection, see [Outbound spam controls](outbound-spam-controls.md).</span></span>

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a><span data-ttu-id="77245-122">제로 데이 스팸 변형이란 무엇일까요? 이 변형은 서비스에서 어떻게 처리하나요?</span><span class="sxs-lookup"><span data-stu-id="77245-122">What's a zero-day spam variant and how is it handled by the service?</span></span>

<span data-ttu-id="77245-123">제로 데이 스팸 변형은 이전에 알 수 없는 1세대의 스팸 변형으로 캡처 또는 분석되지 않았기 때문에 스팸 방지 필터는 이를 검색하는 데 사용할 수 있는 정보가 아직 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-123">A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our anti-spam filters don't yet have any information available for detecting it.</span></span> <span data-ttu-id="77245-124">스팸 분석가가 제로 데이 스팸 샘플을 캡처하고 분석한 후 스팸 분류 기준을 충족하면 스팸 방지 필터가 검색하기 위해 업데이트되고 더 이상 "제로 데이"로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-124">After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our anti-spam filters are updated to detect it, and it's no longer considered "zero-day."</span></span>

<span data-ttu-id="77245-125">**참고:** 제로 데이 스팸 변형일 수 있는 메시지를 받으면 서비스를 개선하는 데 도움이 될 수 있도록 Microsoft에 메시지 및 파일 보고에 설명된 방법 중 하나를 사용하여 [Microsoft에](report-junk-email-messages-to-microsoft.md)메시지를 제출하십시오.</span><span class="sxs-lookup"><span data-stu-id="77245-125">**Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a><span data-ttu-id="77245-126">스팸 방지 보호 기능을 제공하도록 서비스를 구성해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="77245-126">Do I need to configure the service to provide anti-spam protection?</span></span>

<span data-ttu-id="77245-127">서비스에 등록하고 도메인을 추가하면 스팸 필터링이 자동으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-127">After you sign up for the service and add your domain, spam filtering is automatically enabled.</span></span> <span data-ttu-id="77245-128">기본적으로 스팸 필터링은 추가 구성 없이 보호됩니다(하이브리드 환경의 독립 실행형 EOP 독립 실행형 고객의 경우 이전에 언급한 예외 제외).</span><span class="sxs-lookup"><span data-stu-id="77245-128">By default, spam filtering is tuned to protect you without needing any additional configuration (aside from the previously noted exception for standalone EOP standalone customers in hybrid environments).</span></span> <span data-ttu-id="77245-129">관리자는 조직의 요구 사항을 가장 잘 충족하기 위해 기본 스팸 필터링 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-129">As an admin, you can edit the default spam filtering settings to best meet the needs of your organization.</span></span> <span data-ttu-id="77245-130">세분성을 강화하기 위해 조직의 지정된 사용자, 그룹 또는 도메인에 적용되는 스팸 방지 정책 및 아웃바운드 스팸 방지 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-130">For greater granularity, you can also create anti-spam policies and outbound anti-spam policies that are applied to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="77245-131">사용자 지정 정책은 항상 기본 정책보다 우선하지만 사용자 지정 정책의 우선 순위(즉, 실행 순서)를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-131">Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>

<span data-ttu-id="77245-132">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77245-132">For more information, see the following topics:</span></span>

[<span data-ttu-id="77245-133">EOP 및 Office 365용 Microsoft Defender 보안에 대한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="77245-133">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

[<span data-ttu-id="77245-134">EOP에서 연결 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="77245-134">Configure connection filtering in EOP</span></span>](configure-the-connection-filter-policy.md)

[<span data-ttu-id="77245-135">EOP에서 스팸 방지 정책 구성하기</span><span class="sxs-lookup"><span data-stu-id="77245-135">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="77245-136">아웃바운드 스팸 정책 구성</span><span class="sxs-lookup"><span data-stu-id="77245-136">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a><span data-ttu-id="77245-137">스팸 방지 정책을 변경하는 경우 저장한 변경 내용이 적용될 때까지 시간이 얼마나 걸립니까?</span><span class="sxs-lookup"><span data-stu-id="77245-137">If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?</span></span>

<span data-ttu-id="77245-138">변경 내용이 적용되기까지 최대 1시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-138">It may take up to 1 hour for the changes to take effect.</span></span>

## <a name="is-bulk-email-filtering-automatically-enabled"></a><span data-ttu-id="77245-139">대량 전자 메일 필터링은 자동으로 사용하도록 설정됩니까?</span><span class="sxs-lookup"><span data-stu-id="77245-139">Is bulk email filtering automatically enabled?</span></span>

<span data-ttu-id="77245-140">예.</span><span class="sxs-lookup"><span data-stu-id="77245-140">Yes.</span></span> <span data-ttu-id="77245-141">대량 전자 메일에 대한 자세한 내용은 정크 메일과 대량 전자 메일의 [차이점을 참조하세요.](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="77245-141">For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

## <a name="does-the-service-provide-url-filtering"></a><span data-ttu-id="77245-142">서비스에서 URL 필터링 기능을 제공합니까?</span><span class="sxs-lookup"><span data-stu-id="77245-142">Does the service provide URL filtering?</span></span>

<span data-ttu-id="77245-143">예. 서비스에는 메시지 내의 URL을 검사하는 URL 필터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-143">Yes, the service has a URL filter that checks for URLs within messages.</span></span> <span data-ttu-id="77245-144">알려진 스팸 또는 악의적인 콘텐츠와 연결된 URL이 검색되면 메시지가 스팸으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-144">If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a><span data-ttu-id="77245-145">서비스를 사용하는 고객이 거짓 부정(스팸) 및 가양성(스팸 아님) 메시지를 Microsoft로 보내려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="77245-145">How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?</span></span>

<span data-ttu-id="77245-146">스팸 및 스팸이 아닌 메시지는 분석을 위해 여러 가지 방법으로 Microsoft에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-146">Spam and non-spam messages can be submitted to Microsoft for analysis in several ways.</span></span> <span data-ttu-id="77245-147">자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77245-147">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="can-i-get-spam-reports"></a><span data-ttu-id="77245-148">스팸 보고서를 확인할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="77245-148">Can I get spam reports?</span></span>

<span data-ttu-id="77245-149">예, 예를 들어 Microsoft 365 관리 센터에서 스팸 검색 보고서를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-149">Yes, for example you can get a spam detection report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="77245-150">이 보고서에는 스팸 볼륨이 고유한 메시지 수로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-150">This report shows spam volume as a count of unique messages.</span></span> <span data-ttu-id="77245-151">보고에 대한 자세한 내용은 다음 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="77245-151">For more information about reporting, see the following links:</span></span>

<span data-ttu-id="77245-152">Exchange Online 고객: [Exchange Online의 모니터링,](/exchange/monitoring/monitoring) 보고 및 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="77245-152">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](/exchange/monitoring/monitoring)</span></span>

<span data-ttu-id="77245-153">독립 실행형 EOP 고객: [Exchange Online Protection의](reporting-and-message-trace-in-exchange-online-protection.md) 보고 및 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="77245-153">Standalone EOP customers: [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)</span></span>

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a><span data-ttu-id="77245-154">누군가 메시지를 보냈기만 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-154">Someone sent me a message and I can't find it.</span></span> <span data-ttu-id="77245-155">스팸으로 검색된 것으로 의심합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-155">I suspect that it may have been detected as spam.</span></span> <span data-ttu-id="77245-156">찾을 수 있는 도구가 있나요?</span><span class="sxs-lookup"><span data-stu-id="77245-156">Is there a tool that I can use to find out?</span></span>

<span data-ttu-id="77245-157">예. 메시지 추적 도구를 사용하면 서비스를 통과할 때 전자 메일 메시지를 추적하여 해당 메시지에 어떤 일이 발생하게 났는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-157">Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them.</span></span> <span data-ttu-id="77245-158">메시지 추적 도구를 사용하여 메시지가 스팸으로 표시된 이유를 찾는 방법에 대한 자세한 내용은 메시지가 스팸으로 [표시되어 있나요?를 참조하세요.](/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span><span class="sxs-lookup"><span data-stu-id="77245-158">For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam?](/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span></span>

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a><span data-ttu-id="77245-159">사용자가 아웃바운드 스팸을 보내는 경우 서비스에서 메일을 제한하나요(속도 제한)</span><span class="sxs-lookup"><span data-stu-id="77245-159">Will the service throttle (rate limit) my mail if my users send outbound spam?</span></span>

<span data-ttu-id="77245-160">특정 기간(예: 시간당)에 서비스를 통해 사용자가 보낸 메일의 절반 이상이 EOP에서 스팸으로 확인되면 사용자는 메시지 보내기 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-160">If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by EOP, the user will be blocked from sending messages.</span></span> <span data-ttu-id="77245-161">대부분의 경우 아웃바운드 메시지가 스팸으로 확인되면 일반 아웃바운드 IP 풀이 차단 목록에 추가될 가능성이 줄어든 고위험 배달 풀을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-161">In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>

<span data-ttu-id="77245-162">보낸 사람이 아웃바운드 스팸을 보낼 수 없도록 차단된 경우 지정된 전자 메일 주소로 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-162">You can send a notification to a specified email address when a sender is blocked sending outbound spam.</span></span> <span data-ttu-id="77245-163">이 설정에 대한 자세한 내용은 [Configure the outbound spam policy을 참조하십시오.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="77245-163">For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a><span data-ttu-id="77245-164">타사 스팸 방지 및 맬웨어 방지 공급자와 Exchange Online을 함께 사용할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="77245-164">Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?</span></span>

<span data-ttu-id="77245-165">예.</span><span class="sxs-lookup"><span data-stu-id="77245-165">Yes.</span></span> <span data-ttu-id="77245-166">MX 레코드를 Microsoft를 설정하는 것이 좋습니다. 그러나 먼저 전자 메일을 Microsoft가 다른 곳으로 라우팅해야 하는 합법적인 비즈니스 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-166">Although we recommend that you point your MX record to Microsoft, we realize that there are legitimate business reasons to route your email to somewhere other than Microsoft first.</span></span>

- <span data-ttu-id="77245-167">**인바운드:** 타사 공급자를 지점으로 MX 레코드를 변경한 다음 추가 처리를 위해 메시지를 EOP로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-167">**Inbound**: Change your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing.</span></span> <span data-ttu-id="77245-168">자세한 내용은 Exchange Online의 커넥터에 대한 향상된 [필터링을 참조하세요.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="77245-168">For more information, see [Enhanced Filtering for connectors in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="77245-169">**아웃바운드:** Microsoft 365에서 대상 타사 공급자로의 스마트 호스트 라우팅을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-169">**Outbound**: Configure smart host routing from Microsoft 365 to the destination third-party provider.</span></span>

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a><span data-ttu-id="77245-170">Microsoft에 피싱 메일로부터 자기 자신을 보호할 수 있는 방법에 대한 설명서가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="77245-170">Does Microsoft have any documentation about how I can protect myself from phishing scams?</span></span>

<span data-ttu-id="77245-171">예.</span><span class="sxs-lookup"><span data-stu-id="77245-171">Yes.</span></span> <span data-ttu-id="77245-172">자세한 내용은 [인터넷에서 개인 정보 보호를 참조하세요.](https://support.microsoft.com/help/4091455)</span><span class="sxs-lookup"><span data-stu-id="77245-172">For more information, see [Protect your privacy on the internet](https://support.microsoft.com/help/4091455)</span></span>

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a><span data-ttu-id="77245-173">스팸 및 맬웨어 메시지의 경우 보낸 사람을 조사하거나 법 집행 기관으로 전송됩니까?</span><span class="sxs-lookup"><span data-stu-id="77245-173">Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?</span></span>

<span data-ttu-id="77245-174">이 서비스는 스팸 및 맬웨어 감지 및 제거에 중점을 두지만 경우에 따라 특히 위험하거나 손상된 스팸 또는 공격 캠페인을 조사하고 가해자 추격을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-174">The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators.</span></span> <span data-ttu-id="77245-175">여기에는 법률 및 디지털 범죄 단위와 협력하여 스패머 봇넷을 무단으로 삭제하고, 스패머가 서비스를 사용하지 못하도록 차단하고(아웃바운드 전자 메일을 보내는 데 사용하는 경우), 사법 기관에 범죄 기소를 위한 정보를 전달하는 과정이 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-175">This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a><span data-ttu-id="77245-176">메일 배달을 보장할 수 있는 가장 좋은 아웃바운드 메일 보내기 방법은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="77245-176">What are a set of best outbound mailing practices that will ensure that my mail is delivered?</span></span>

<span data-ttu-id="77245-177">아래에 나와 있는 지침이 아웃바운드 전자 메일 메시지를 보내는 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="77245-177">The guidelines presented below are best practices for sending outbound email messages.</span></span>

- <span data-ttu-id="77245-178">**원본 전자 메일 도메인이 DNS에서 확인됩니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-178">**The source email domain should resolve in DNS.**</span></span>

  <span data-ttu-id="77245-179">예를 들어 보낸 사람이 user@fabrikam fabrikam 도메인은 IP 주소 192.0.43.10으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-179">For example, if the sender is user@fabrikam, the domain fabrikam resolves to the IP address 192.0.43.10.</span></span>

  <span data-ttu-id="77245-180">보내는 도메인의 A 레코드와 MX 레코드가 DNS에 없으면 서비스에서는 메시지 내용이 스팸인지 여부에 관계없이 위험성이 높은 배달 풀을 통하여 해당 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-180">If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam.</span></span> <span data-ttu-id="77245-181">위험도가 높은 배달 풀에 대한 자세한 내용은 아웃바운드 메시지에 대한 위험도가 높은 [배달 풀을 참조하세요.](high-risk-delivery-pool-for-outbound-messages.md)</span><span class="sxs-lookup"><span data-stu-id="77245-181">For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="77245-182">**아웃바운드 메일 서버에는 역방향 DNS(PTR) 항목이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-182">**Outbound mail eserver should have a reverse DNS (PTR) entry.**</span></span>

  <span data-ttu-id="77245-183">예를 들어 전자 메일 원본 IP 주소가 192.0.43.10인 경우 역방향 DNS 항목은 `43-10.any.icann.org` .'</span><span class="sxs-lookup"><span data-stu-id="77245-183">For example, if the email source IP address is 192.0.43.10, the reverse DNS entry would be `43-10.any.icann.org`.\`</span></span>

- <span data-ttu-id="77245-184">**HELO/EHLO 및 MAIL FROM 명령은 일관성이 있어야 하며 IP 주소가 아닌 도메인 이름 형식으로 지정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-184">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>

  <span data-ttu-id="77245-185">HELO/EHLO 명령은 보내는 IP 주소의 역방향 DNS와 일치하도록 구성해야 합니다. 그래야 메시지 헤더의 여러 부분에서 도메인이 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="77245-185">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>

- <span data-ttu-id="77245-186">**DNS에서 적절한 SPF 레코드를 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-186">**Ensure that proper SPF records are set up in DNS.**</span></span>

  <span data-ttu-id="77245-p119">SPF 레코드는 도메인에서 전송된 메일이 실제로 해당 도메인에서 보낸 것이며 스푸핑되지 않았음을 검사하는 메커니즘입니다. SPF 레코드에 대한 자세한 내용은 다음 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="77245-p119">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>

  [<span data-ttu-id="77245-189">스푸핑을 방지할 수 있도록 SPF 설정</span><span class="sxs-lookup"><span data-stu-id="77245-189">Set up SPF to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [<span data-ttu-id="77245-190">도메인 FAQ</span><span class="sxs-lookup"><span data-stu-id="77245-190">Domains FAQ</span></span>](../../admin/setup/domains-faq.yml#how-can-i-validate-spf-records-for-my-domain)

- <span data-ttu-id="77245-191">**DKIM으로 전자 메일에 서명을 하는 경우 낮은 수준의 정규화로 서명합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-191">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>

  <span data-ttu-id="77245-p120">보낸 사람은 DKIM(Domain Keys Identified Mail)을 사용하여 메시지에 서명을 하고 서비스를 통해 아웃바운드 메일을 보내려는 경우 낮은 수준의 헤더 정규화 알고리즘을 사용하여 서명해야 합니다. 엄격한 헤더 정규화를 사용하여 서명을 하면 메시지가 서비스를 통과할 때 서명이 무효화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-p120">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>

- <span data-ttu-id="77245-194">**도메인 소유자는 WHOIS 데이터베이스에 정확한 정보를 포함해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-194">**Domain owners should have accurate information in the WHOIS database.**</span></span>

  <span data-ttu-id="77245-195">이렇게 하면 고정된 모회사, 담당자 및 이름 서버를 입력함으로써 도메인 소유자 및 소유자에게 연락하는 방법을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-195">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>

- <span data-ttu-id="77245-196">**대량 메일러의 경우 보낸 사람: 이름이 메시지를 보내는 사람을 반영해야 하며 메시지의 제목 줄은 메시지 내용에 대한 간략한 요약을 포함해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-196">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>

  <span data-ttu-id="77245-p121">메시지 본문에는 제공 사항, 서비스 또는 제품이 명확하게 표시되어 있어야 합니다. 예를 들어 보낸 사람이 Contoso라는 회사를 위해 대량의 메일을 보내는 경우 전자 메일의 보낸 사람 및 제목은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-p121">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>

  > <span data-ttu-id="77245-199">보낸 사람: marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="77245-199">From: marketing@contoso.com</span></span> <br> <span data-ttu-id="77245-200">제목: 업데이트된 크리스마스 시즌용 신규 카탈로그!</span><span class="sxs-lookup"><span data-stu-id="77245-200">Subject: New updated catalog for the Christmas season!</span></span>

  <span data-ttu-id="77245-201">다음은 대량 메일임을 충분히 설명하지 않으므로 부적합한 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="77245-201">The following is an example of what not to do because it is not descriptive:</span></span>

  > <span data-ttu-id="77245-202">보낸 사람: user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="77245-202">From: user@hotmail.com</span></span> <br> <span data-ttu-id="77245-203">제목: 카탈로그</span><span class="sxs-lookup"><span data-stu-id="77245-203">Subject: Catalogs</span></span>

- <span data-ttu-id="77245-204">**뉴스레터 형식의 메시지를 많은 수의 받는 사람에게 대량 메일로 보내는 경우에는 메시지 아래쪽에 구독을 취소할 수 있는 수단이 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-204">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>

  <span data-ttu-id="77245-205">다음과 같은 구독 취소 옵션을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-205">The unsubscribe option should resemble the following:</span></span>

  > <span data-ttu-id="77245-206">이 메시지는 sender@fabrikam.com에서 example.@contoso.com으로 전송된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="77245-206">This message was sent to example@contoso.com by sender@fabrikam.com.</span></span> <span data-ttu-id="77245-207">프로필/전자 메일 주소 | **SafeUnsubscribe를** 통해 즉시 &trade; | 개인 정보 취급 방침</span><span class="sxs-lookup"><span data-stu-id="77245-207">Update Profile/Email Address | Instant removal with **SafeUnsubscribe**&trade; | Privacy Policy</span></span>

- <span data-ttu-id="77245-208">**대량 전자 메일을 보내는 경우에는 이중 옵트인(opt in)을 통해 목록을 확보해야 합니다. 이중 옵트인(opt in)은 대량 메일러에 대한 업계 모범 사례입니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-208">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>

  <span data-ttu-id="77245-209">이중 옵트인(opt in)은 사용자가 마케팅 메일을 신청할 때 두 가지 작업을 수행하도록 요구하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="77245-209">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>

  1. <span data-ttu-id="77245-210">먼저, 사용자는 이전에는 선택하지 않았던 확인란을 클릭하여 마케팅 업체의 서비스 또는 전자 메일 메시지를 계속 받도록 옵트인(opt in)합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-210">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>

  2. <span data-ttu-id="77245-211">다음으로, 사용자가 입력한 전자 메일 주소로 마케팅 업체가 확인 전자 메일을 보내 사용자가 일정 시간 이내에 링크를 클릭하여 확인을 완료하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-211">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>

  <span data-ttu-id="77245-212">이중 옵트인(opt in)을 사용하는 경우 대량 전자 메일 보낸 사람의 신뢰도가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="77245-212">Using double opt-in builds a good reputation for bulk email senders.</span></span>

- <span data-ttu-id="77245-213">**대량 전자 메일 보낸 사람은 책임질 수 있는 명확한 콘텐츠를 작성해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-213">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>

  1. <span data-ttu-id="77245-214">받는 사람이 보낸 사람을 주소록에 추가하도록 요청하는 장문의 메시지에서는 해당 작업을 수행해도 배달이 보장되지는 않음을 명확하게 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-214">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>

  2. <span data-ttu-id="77245-215">메시지 본문에 리디렉션을 구성하는 경우에는 일관성 있는 링크 스타일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-215">When constructing redirects in the body of the message, use a consistent link style.</span></span>

  3. <span data-ttu-id="77245-216">큰 이미지나 첨부 파일, 또는 이미지로만 구성된 메시지를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-216">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>

  4. <span data-ttu-id="77245-217">추적 픽셀(웹 버그 또는 탐지 장치)을 사용할 때는 공개 개인 정보 또는 P3P 설정에서 그러한 항목이 있음을 명기합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-217">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>

- <span data-ttu-id="77245-218">**아웃바운드 반송 메시지의 서식을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-218">**Format outbound bounce messages.**</span></span>

  <span data-ttu-id="77245-219">배달 상태 알림 메시지(배달하지 않는 보고서, NDRs 또는 반송 메시지라고도 알려지음)를 생성하는 경우 보낸 사람이 [RFC 3464에](https://www.ietf.org/rfc/rfc3464.txt)지정된 바운스 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77245-219">When generating delivery status notification messages (also known as non-delivery reports, NDRs, or bounce messages), senders should follow the format of a bounce as specified in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).</span></span>

- <span data-ttu-id="77245-220">**존재하지 않는 사용자의 반송된 전자 메일 주소를 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-220">**Remove bounced email addresses for non-existent users.**</span></span>

  <span data-ttu-id="77245-p123">전자 메일 주소가 더 이상 사용되지 않음을 나타내는 NDR을 받으면 존재하지 않는 전자 메일 별칭을 목록에서 제거합니다. 전자 메일 주소는 시간이 지남에 따라 변경되며, 주소를 삭제하는 사용자도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77245-p123">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>

- <span data-ttu-id="77245-223">**Hotmail의 SNDS(Smart Network Data Services) 프로그램을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="77245-223">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>

  <span data-ttu-id="77245-p124">Hotmail에서는 최종 사용자가 전송한 불만 사항을 보낸 사람이 확인할 수 있도록 하는 Smart Network Data Services라는 프로그램을 사용합니다. SNDS는 Hotmail에 대한 배달 문제 해결을 위한 기본 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="77245-p124">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>