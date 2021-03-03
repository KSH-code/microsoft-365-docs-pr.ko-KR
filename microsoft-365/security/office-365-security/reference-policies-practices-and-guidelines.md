---
title: 참조 정책, 사례 및 지침
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft는 다양한 정책, 절차를 개발하고 사용자를 악의적, 원치 않는 또는 악의적인 전자 메일로부터 보호하기 위해 여러 업계 모범 사례를 채택했습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f53b1c36417b15e366b527dd1c12e4f23c06f632
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406599"
---
# <a name="reference-policies-practices-and-guidelines"></a><span data-ttu-id="b4b58-103">참조: 정책, 사례 및 지침</span><span class="sxs-lookup"><span data-stu-id="b4b58-103">Reference: Policies, practices, and guidelines</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b4b58-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="b4b58-104">**Applies to**</span></span>
- [<span data-ttu-id="b4b58-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b4b58-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b4b58-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="b4b58-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b4b58-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4b58-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b4b58-108">Microsoft는 웹에서 가장 신뢰할 수 있는 사용자 환경을 제공하기 위해 전념하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-108">Microsoft is dedicated to helping provide the most trusted user experience on the web.</span></span> <span data-ttu-id="b4b58-109">따라서 Microsoft는 다양한 정책, 절차를 개발하고, 악의적, 원치 않는 또는 악의적인 전자 메일로부터 사용자를 보호하기 위해 몇 가지 업계 모범 사례를 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-109">Therefore, Microsoft has developed various policies, procedures, and adopted several industry best practices to help protect our users from abusive, unwanted, or malicious email.</span></span> <span data-ttu-id="b4b58-110">사용자에게 전자 메일을 보내고자 하는 보낸 사람은 이 노력에 도움을 주며 잠재적인 배달 문제를 방지하는 데 도움이 되도록 이 문서의 지침을 완전히 이해하고 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-110">Senders attempting to send email to users should ensure they fully understand and are following the guidance in this article to help in this effort and to help avoid potential delivery issues.</span></span>

<span data-ttu-id="b4b58-111">이러한 정책 및 지침을 준수하지 않는 경우 지원 팀에서 지원을 받지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-111">If you are not in compliance with these policies and guidelines, it may not be possible for our support team to assist you.</span></span> <span data-ttu-id="b4b58-112">이 문서에 제시된 지침, 사례 및 정책을 준수하고 여전히 보내는 IP 주소에 따라 배달 문제가 발생하는 경우 단계에 따라 목록에서 요청을 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="b4b58-112">If you are adhering to the guidelines, practices, and policies presented in this article and are still experiencing delivery issues based on your sending IP address, please follow the steps to submit a delisting request.</span></span> <span data-ttu-id="b4b58-113">자세한 내용은 목록 제거 포털을 사용하여 수신 차단된 보낸 사람 목록에서 자신을 [제거를 참조하세요.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="b4b58-113">For instructions, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="general-microsoft-policies"></a><span data-ttu-id="b4b58-114">일반 Microsoft 정책</span><span class="sxs-lookup"><span data-stu-id="b4b58-114">General Microsoft policies</span></span>

<span data-ttu-id="b4b58-115">Microsoft 365 사용자에게 전송되는 전자 메일은 Microsoft 365의 전자 메일 전송 및 사용을 규정하는 모든 Microsoft 정책을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-115">Email sent to Microsoft 365 users must comply with all Microsoft policies governing email transmission and use of Microsoft 365.</span></span>

- <span data-ttu-id="b4b58-116">Microsoft 365에 적용되는 서비스 약관 특히 서비스를 사용하여 스팸을 방지하거나 맬웨어를 배포하는 금지입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-116">Terms of Services applicable to Microsoft 365; in particular, the prohibition against using the service to spam or distribute malware.</span></span>

- [<span data-ttu-id="b4b58-117">Microsoft 서비스 계약</span><span class="sxs-lookup"><span data-stu-id="b4b58-117">Microsoft Services Agreement</span></span>](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a><span data-ttu-id="b4b58-118">정부 규정</span><span class="sxs-lookup"><span data-stu-id="b4b58-118">Governmental regulations</span></span>

<span data-ttu-id="b4b58-119">Microsoft 365 사용자에게 전송되는 전자 메일은 해당 관할권의 전자 메일 통신을 규정하는 모든 관련 법률 및 규정을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-119">Email sent to Microsoft 365 users must adhere to all applicable laws and regulations governing email communications in the applicable jurisdiction.</span></span>

- [<span data-ttu-id="b4b58-120">CAN-SPAM Act: A Compliance Guide for Business</span><span class="sxs-lookup"><span data-stu-id="b4b58-120">CAN-SPAM Act: A Compliance Guide for Business</span></span>](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [<span data-ttu-id="b4b58-121">"제거" 응답 및 책임: 전자 메일 시장은 "구독 취소" 클레임의 수호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-121">"Remove Me" Responses and Responsibilities: Email Marketers Must Honor "Unsubscribe" Claims</span></span>](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a><span data-ttu-id="b4b58-122">기술 지침</span><span class="sxs-lookup"><span data-stu-id="b4b58-122">Technical guidelines</span></span>

<span data-ttu-id="b4b58-123">Microsoft 365로 전송되는 전자 메일은 아래 문서에 나열된 해당 권장 사항을 준수해야 합니다(일부 링크는 영어로만 제공).</span><span class="sxs-lookup"><span data-stu-id="b4b58-123">Email sent to Microsoft 365 should comply with the applicable recommendations listed in the documents below (some links are only available in English).</span></span>

- [<span data-ttu-id="b4b58-124">RFC 2505: SMTP MTAS에 대한 스팸 방지 권장 사항</span><span class="sxs-lookup"><span data-stu-id="b4b58-124">RFC 2505: Anti-Spam Recommendations for SMTP MTAs</span></span>](https://www.ietf.org/rfc/rfc2505.txt)

- [<span data-ttu-id="b4b58-125">RFC 2920: 명령 파이프라이너용 SMTP 서비스 확장</span><span class="sxs-lookup"><span data-stu-id="b4b58-125">RFC 2920: SMTP Service Extension for Command Pipelining</span></span>](https://www.ietf.org/rfc/rfc2920.txt)

<span data-ttu-id="b4b58-126">또한 Microsoft 365에 연결하는 전자 메일 서버는 다음 요구 사항을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-126">In addition, email servers connecting to Microsoft 365 must adhere to the following requirements:</span></span>

- <span data-ttu-id="b4b58-127">보낸 사람이 RFC 5321, RFC 5322 등을 포함하여 인터넷 사회의 IETF(Internet Engineering Task Force)에서 게시한 인터넷 전자 메일 전송에 대한 모든 기술 표준을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-127">Sender is expected to comply with all technical standards for the transmission of Internet email, as published by The Internet Society's Internet Engineering Task Force (IETF), including RFC 5321, RFC 5322, and others.</span></span>

- <span data-ttu-id="b4b58-128">500에서 599 사이의 숫자 SMTP 오류 응답 코드(영구적 배달 못지 않은 응답 또는 NDR)를 제공한 후 보낸 사람은 해당 메시지를 해당 받는 사람에게 다시 전송하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-128">After given a numeric SMTP error response code between 500 and 599 (also known as a permanent non-delivery response or NDR), the sender must not attempt to retransmit that message to that recipient.</span></span>

- <span data-ttu-id="b4b58-129">배달되지 않은 응답이 여러 개 있는 경우 보낸 사람은 해당 받는 사람에게 전자 메일을 보내기 더 이상 시도하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-129">After multiple non-delivery responses, the sender must cease further attempts to send email to that recipient.</span></span>

- <span data-ttu-id="b4b58-130">비보안 전자 메일 릴레이 또는 프록시 서버를 통해 메시지를 전송하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-130">Messages must not be transmitted through insecure email relay or proxy servers.</span></span>

- <span data-ttu-id="b4b58-131">개별 목록 또는 보낸 사람이 호스팅하는 모든 목록에서 수신을 제출하지 않는 메커니즘을 명확하게 문서화해야 받는 사람이 쉽게 찾아 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-131">The mechanism for unsubscribing, either from individual lists or all lists hosted by the sender, must be clearly documented and easy for recipients to find and use.</span></span>

- <span data-ttu-id="b4b58-132">동적 IP 공간의 연결이 수락되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-132">Connections from dynamic IP space may not be accepted.</span></span>

- <span data-ttu-id="b4b58-133">전자 메일 서버에 유효한 역방향 DNS 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-133">Email servers must have valid reverse DNS records.</span></span>

## <a name="reputation-management"></a><span data-ttu-id="b4b58-134">신뢰도 관리</span><span class="sxs-lookup"><span data-stu-id="b4b58-134">Reputation management</span></span>

<span data-ttu-id="b4b58-135">보낸 사람, ISP 및 기타 서비스 공급자는 아웃바운드 IP 주소의 신뢰도를 적극적으로 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-135">Senders, ISP's, and other service providers should actively manage the reputation of your outbound IP addresses.</span></span>

## <a name="microsoft-365-limits"></a><span data-ttu-id="b4b58-136">Microsoft 365 제한</span><span class="sxs-lookup"><span data-stu-id="b4b58-136">Microsoft 365 limits</span></span>

<span data-ttu-id="b4b58-137">보낸 사람이 Exchange Online Protection 제한에 나열된 Microsoft 365 [제한을 준수해야 합니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)</span><span class="sxs-lookup"><span data-stu-id="b4b58-137">Senders must adhere to Microsoft 365 limits listed in [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).</span></span>

## <a name="email-delivery-resources-and-organizations"></a><span data-ttu-id="b4b58-138">전자 메일 배달 리소스 및 조직</span><span class="sxs-lookup"><span data-stu-id="b4b58-138">Email delivery resources and organizations</span></span>

<span data-ttu-id="b4b58-139">Microsoft는 인터넷 및 전자 메일 에코시스템을 개선하기 위해 산업 기관 및 서비스 공급자와 적극적으로 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-139">Microsoft actively works with industry bodies and service providers in order to improve the internet and email ecosystem.</span></span> <span data-ttu-id="b4b58-140">이러한 조직은 보낸 사람이 준수할 수 있는 모범 사례 문서를 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-140">These organizations have published best practice documents that we support and recommend senders adhere to.</span></span> <span data-ttu-id="b4b58-141">이를 통해 전 세계 여러 전자 메일 서비스 공급자가 전자 메일을 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-141">This improves your ability to deliver email among several email service providers around the world.</span></span>

- [<span data-ttu-id="b4b58-142">메시징 맬웨어 모바일 남용 방지 작업 그룹</span><span class="sxs-lookup"><span data-stu-id="b4b58-142">Messaging Malware Mobile Anti-Abuse Working Group</span></span>](https://www.m3aawg.org/)

- [<span data-ttu-id="b4b58-143">Online Trust Alliance</span><span class="sxs-lookup"><span data-stu-id="b4b58-143">Online Trust Alliance</span></span>](https://www.internetsociety.org/ota/)

- [<span data-ttu-id="b4b58-144">전자 메일 보낸 & 공급자 연대</span><span class="sxs-lookup"><span data-stu-id="b4b58-144">Email Sender & Provider Coalition</span></span>](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a><span data-ttu-id="b4b58-145">남용 및 스팸 보고</span><span class="sxs-lookup"><span data-stu-id="b4b58-145">Abuse and spam reporting</span></span>

<span data-ttu-id="b4b58-146">위조, 악의적, 원치 않는 또는 악성 전자 메일을 보고하려면 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="b4b58-146">To report unlawful, abusive, unwanted or malicious email, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="b4b58-147">이러한 유형의 통신을 보내는 것은 Microsoft 정책을 위반하며 확인된 보고서에 대해 적절한 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b58-147">Sending these types of communications is a violation of Microsoft policy, and appropriate action will be taken on confirmed reports.</span></span>

## <a name="law-enforcement"></a><span data-ttu-id="b4b58-148">사법 기관</span><span class="sxs-lookup"><span data-stu-id="b4b58-148">Law enforcement</span></span>

<span data-ttu-id="b4b58-149">사법 기관의 구성원이자 Office 365에 관한 법적 문서를 Microsoft Corporation에 지원하고자 하는 경우 또는 Microsoft에 제출한 법적 문서에 대한 질문이 있는 경우 (1) (425) 722-1299로 전화하세요.</span><span class="sxs-lookup"><span data-stu-id="b4b58-149">If you are a member of law enforcement and wish to serve Microsoft Corporation with legal documentation regarding Office 365, or if you have questions regarding legal documentation you have submitted to Microsoft, please call (1) (425) 722-1299.</span></span>
