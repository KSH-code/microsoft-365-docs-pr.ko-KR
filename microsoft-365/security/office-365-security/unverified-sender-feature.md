---
title: 확인 되지 않은 보낸 사람
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 피싱 메시지가 사서함에 도착 하지 않도록 하기 위해 웹에서 Outlook.com 및 Outlook은 보낸 사람이 누구 인지를 확인 하 고 의심 스러운 메시지를 정크 메일로 표시 합니다.
ms.openlocfilehash: 0dd8b54d2c8153b4200336d8c0e439f278f7ae77
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598135"
---
# <a name="unverified-sender"></a><span data-ttu-id="d39c6-103">확인 되지 않은 보낸 사람</span><span class="sxs-lookup"><span data-stu-id="d39c6-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="d39c6-104">이러한 업데이트는 현재 롤아웃 중 이며, 아직 모든 사용자에 대해 사용이 가능 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-104">These updates are rolling out now, and might not be available yet for all users.</span></span> <span data-ttu-id="d39c6-105">이 기능은 Enterprise outlook.com 사용자에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-105">This feature is supported for Enterprise outlook.com users.</span></span> <span data-ttu-id="d39c6-106">현재 소비자 outlook.com는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-106">It is not currently available for consumer outlook.com.</span></span>

<span data-ttu-id="d39c6-107">피싱 메시지가 사서함에 도착 하지 않도록 하기 위해 웹에서 Outlook.com 및 Outlook은 보낸 사람이 누구 인지를 확인 하 고 의심 스러운 메시지를 정크 메일로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-107">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d39c6-108">메시지가 피싱 사기로 표시 되 면 Outlook.com 및 웹용 Outlook의 페이지 맨 위에 경고가 표시 되지만 메시지의 모든 링크는 계속 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-108">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="d39c6-109">받은 편지함에서 의심 스러운 메시지를 어떻게 확인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d39c6-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="d39c6-110">Outlook.com and Outlook에서 메시지를 보낸 사람이 식별 되지 않거나 id가 보낸 사람 주소에 표시 되는 내용과 다를 때 나타나는 지표를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-110">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="d39c6-111">보낸 사람 이미지에 '? '가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="d39c6-112">Outlook.com 및 웹용 Outlook에서 전자 메일 인증 기술을 사용 하 여 보낸 사람의 id를 확인할 수 없는 경우 보낸 사람 사진에 '? '가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-112">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![메시지가 확인 통과 되지 않음](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="d39c6-114">인증에 실패 한 모든 메시지는 악성이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="d39c6-115">그러나 보낸 사람을 인식 하지 못하는 경우 인증을 받지 않는 메시지와 상호 작용할 때는 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="d39c6-116">또는 일반적으로 보낸 사람 이미지에 '? '가 포함 되지 않는 보낸 사람을 인식할 수 있지만이를 갑자기 보면 보낸 사람이 위장 중 이라고 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="d39c6-117">확인 되지 않은 보낸 사람 처리를 수신 하는 메시지를 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="d39c6-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="d39c6-118">Office 365 고객 인 경우 Office 365 보안 & 준수 센터를 통해이 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="d39c6-119">보안 & 준수 센터에서 전역 또는 보안 관리자는 피싱 정책 아래의 스푸핑 방지를 통해이 기능을 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="d39c6-120">또한 Exchange Online PowerShell에서 **AntiPhishPolicy** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="d39c6-121">자세한 내용은 [Office 365 및 AntiPhishPolicy의 피싱 방지 보호](anti-phishing-protection.md) 를 참조 [](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)하세요.</span><span class="sxs-lookup"><span data-stu-id="d39c6-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![그래픽 인터페이스에서 인증 되지 않은 보낸 사람 편집](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="d39c6-123">관리자가 가양성을 식별 했 고 보낸 사람이 확인 되지 않은 보낸 사람 처리를 수신 하지 않아야 하는 경우 다음 작업 중 하나를 수행 하 여 위장 인텔리전스 스푸핑 허용 목록에 보낸 사람을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="d39c6-124">스푸핑 인텔리전스 이해를 통해 도메인 쌍을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="d39c6-125">자세한 내용은 [연습용: 스푸핑 인텔리전스 이해](walkthrough-spoof-intelligence-insight.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39c6-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="d39c6-126">Exchange Online PowerShell에서 **get-phishfilterpolicy** cmdlet을 통해 도메인 쌍을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="d39c6-127">자세한 내용은 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) 및 [set UP Office 365 ATP 안티 피싱 및 피싱 방지 정책을](set-up-anti-phishing-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39c6-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="d39c6-128">또한 메일 흐름 규칙 (전송 규칙이 라고도 함), 안전한 도메인 목록 (스팸 방지 정책) 또는 수신 허용-보낸 사람 목록을 통해 메시지가 받은 편지 함으로 배달 된 경우에는 확인 되지 않은 보낸 사람 처리를 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules), Safe Domain List (Anti-Spam Policy), or Safe Sender List.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d39c6-129">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="d39c6-129">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="d39c6-130">Outlook.com 및 웹용 Outlook에서 '? ' 및 ' via ' 속성을 추가 하는 데 사용 하는 기준은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d39c6-130">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="d39c6-131">보낸 사람 이미지의 '? ': Outlook.com가 SPF 또는 DKIM 인증을 통과 하 고 dmarc 전달을 수신 하거나, Office 365 스푸핑 인텔리전스에서 복합 인증을 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-131">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="d39c6-132">자세한 내용은 [office 365에서 스푸핑 방지](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 및 [Dkim을 사용 하 여 사용자 지정 365 도메인에서 전송 되는 아웃 바운드 전자 메일의 유효성을 검사 하](use-dkim-to-validate-outbound-email.md)는 데 도움을 주는 방법에 SPF 설정를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d39c6-132">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="d39c6-133">Via 태그의 경우: 보낸 사람 주소에 있는 도메인이 DKIM 서명 또는 SMTP 메일에서 보낸 도메인과 다른 경우 Outlook.com는 해당 두 필드 중 하나에 도메인을 표시 합니다 (DKIM 서명 우선).</span><span class="sxs-lookup"><span data-stu-id="d39c6-133">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="d39c6-134">'? '를 제거 하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="d39c6-134">How do I remove the '?'</span></span>

<span data-ttu-id="d39c6-135">보낸 사람 이미지의 '? '에 대해 보낸 사람으로 서 SPF 또는 DKIM 중 하나를 사용 하 여 메시지를 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="d39c6-136">Via 태그: 보낸 사람으로 서, DKIM 서명 또는 SMTP 메일의 도메인은 From 주소에 있는 도메인과 같거나 그 하위 도메인 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="d39c6-137">Outlook.com 및 웹용 Outlook에서 인증을 통과 하지 않는 모든 메시지를 표시 하나요?</span><span class="sxs-lookup"><span data-stu-id="d39c6-137">Does Outlook.com and Outlook on the web show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="d39c6-138">꼭 필요 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-138">Not necessarily.</span></span> <span data-ttu-id="d39c6-139">Outlook.com 및 웹용 Outlook의 메시지에는 보낸 사람을 인증 하기 위한 다른 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39c6-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d39c6-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d39c6-140">Related topics</span></span>

[<span data-ttu-id="d39c6-141">Outlook.com 전자 메일 계정 보호</span><span class="sxs-lookup"><span data-stu-id="d39c6-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="d39c6-142">Outlook.com의 피싱 또는 스푸핑 처리</span><span class="sxs-lookup"><span data-stu-id="d39c6-142">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="d39c6-143">웹용 Outlook에서 정크 메일 및 스팸 필터링</span><span class="sxs-lookup"><span data-stu-id="d39c6-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
