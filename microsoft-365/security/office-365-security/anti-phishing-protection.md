---
title: 피싱 방지 보호 기능
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
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365용 Microsoft Defender의 피싱 방지 보호 기능에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a100e28ddee1629b2fe35e28742a43b891d13e57
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570615"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="30ec9-103">Microsoft 365의 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="30ec9-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="30ec9-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="30ec9-104">**Applies to**</span></span>
- [<span data-ttu-id="30ec9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="30ec9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="30ec9-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="30ec9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="30ec9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30ec9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="30ec9-108">*피싱은* 합법적인 보낸 사람이나 신뢰할 수 있는 보낸 사람이 보낸 것으로 나타나는 메시지의 중요한 정보를 도용하는 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="30ec9-109">특정 범주의 피싱이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-109">There are specific categories of phishing.</span></span> <span data-ttu-id="30ec9-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-110">For example:</span></span>

- <span data-ttu-id="30ec9-111">**스피어 피싱은** 대상 받는 사람(일반적으로 공격자가 받는 사람을 정정한 후)에 맞게 특별히 조정된 포커스가 있는 사용자 지정 콘텐츠를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="30ec9-112">**래링은** 최대 효과를 위해 조직 내의 임원 또는 기타 높은 가치의 대상을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="30ec9-113">**BEC(비즈니스** 전자 메일 손상)는 신뢰할 수 있는 보낸 사람(재무 책임자, 고객, 신뢰할 수 있는 파트너 등)을 사용하여 받는 사람을 속여 지급을 수령하거나 자금을 이체하거나 고객 데이터를 노출하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span> <span data-ttu-id="30ec9-114">자세한 내용은 이 비디오를 [시청합니다.](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)</span><span class="sxs-lookup"><span data-stu-id="30ec9-114">Learn more by watching [this video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).</span></span>

- <span data-ttu-id="30ec9-115">**데이터를 암호화하고** 암호를 해독하기 위해 지급을 요구하는 랜섬웨어는 거의 항상 피싱 메시지에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-115">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="30ec9-116">피싱 방지 보호는 암호화된 파일의 암호를 해독하는 데 도움이 될 수 없지만 랜섬웨어 캠페인과 연결된 초기 피싱 메시지를 검색하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-116">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="30ec9-117">랜섬웨어 공격으로부터 복구하는 데 대한 자세한 내용은 [Microsoft 365의 랜섬웨어 공격에서 복구를 참조하세요.](recover-from-ransomware.md)</span><span class="sxs-lookup"><span data-stu-id="30ec9-117">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="30ec9-118">공격의 복잡성이 증가함에 따라 학습된 사용자가 정교한 피싱 메시지를 식별하기도 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-118">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="30ec9-119">다행히 EOP(Exchange Online Protection)와 Office 365용 Microsoft Defender의 추가 기능은 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-119">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="30ec9-120">EOP의 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="30ec9-120">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="30ec9-121">EOP(즉, Office 365용 Microsoft Defender가 없는 Microsoft 365 조직)에는 피싱 위협으로부터 조직을 보호하는 데 도움이 되는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-121">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="30ec9-122">**스푸핑 인텔리전스**: 내부 및 외부 도메인의 보낸 사람으로부터 스푸핑된 메시지를 검토하고 해당 보낸 사람을 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-122">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="30ec9-123">자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="30ec9-123">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="30ec9-124">**EOP의** 피싱 방지 정책: 스푸핑 인텔리전스를 켜거나 끄고, Outlook에서 확인되지 않은 보낸 사람 ID를 켜거나 끄고, 차단된 스푸핑된 보낸 사람에 대한 작업(정크 메일 폴더 또는 정크 메일 폴더로 이동)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-124">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="30ec9-125">자세한 내용은 EOP에서 피싱 방지 [정책 구성을 참조하세요.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="30ec9-125">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="30ec9-126">**암시적** 전자 메일 인증: EOP는 보낸 사람 신뢰도, 보낸 사람 기록, 받는 사람 기록, 동작 분석 및 위조된 보낸 사람을 식별하는 데 도움이 되는 기타 고급 기술을 사용하여 인바운드 전자 [메일(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC)에](use-dmarc-to-validate-email.md)대한 표준 전자 메일 인증 검사를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-126">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="30ec9-127">자세한 내용은 [Microsoft 365의 전자 메일 인증](email-validation-and-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30ec9-127">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="30ec9-128">Office 365용 Microsoft Defender의 추가 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="30ec9-128">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="30ec9-129">Office 365용 Microsoft Defender에는 추가 고급 피싱 방지 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-129">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="30ec9-130">**Microsoft Defender for Office 365의** 피싱 방지 정책: 새 사용자 지정 정책을 만들고, 가장 방지 설정(사용자 및 도메인을 가장으로부터 보호), 사서함 인텔리전스 설정 및 조정 가능한 고급 피싱 임계값을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-130">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="30ec9-131">자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30ec9-131">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="30ec9-132">EOP의 피싱 방지 정책과 Office 365용 Defender의 피싱 방지 정책 간의 차이점에 대한 자세한 내용은 [Microsoft 365의](set-up-anti-phishing-policies.md)피싱 방지 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30ec9-132">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="30ec9-133">**캠페인 보기:** 기계 학습 및 기타추론은 전체 서비스 및 조직에 대한 피싱 공격과 관련된 메시지를 식별하고 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-133">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="30ec9-134">자세한 내용은 [Office 365용 Microsoft Defender의 캠페인 보기를 참조하세요.](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="30ec9-134">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="30ec9-135">**공격 시뮬레이터:** 관리자는 가짜 피싱 메시지를 만들어 교육 도구로 내부 사용자에게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30ec9-135">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="30ec9-136">자세한 내용은 [Microsoft Defender for Office 365의 공격 시뮬레이터를 참조하세요.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="30ec9-136">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="30ec9-137">기타 피싱 방지 리소스</span><span class="sxs-lookup"><span data-stu-id="30ec9-137">Other anti-phishing resources</span></span>

- <span data-ttu-id="30ec9-138">최종 사용자의 경우: 피싱 스키마 및 기타 형태의 온라인 사기로부터 자신을 [보호합니다.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="30ec9-138">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="30ec9-139">[Microsoft 365에서](how-office-365-validates-the-from-address.md)피싱을 방지하기 위해 시작 주소의 유효성을 검사하는 방법</span><span class="sxs-lookup"><span data-stu-id="30ec9-139">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
