---
title: 피싱 방지 보호 기능
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection) 및 Office 365 Advanced Threat Protection (Office 365 ATP)의 피싱 방지 보호 기능에 대해 알아볼 수 있습니다.
ms.openlocfilehash: c1b9332fc35997dfe1cbfdfbef79e2d7beed736f
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208974"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="2366c-103">Microsoft 365의 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="2366c-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="2366c-104">*피싱* 적법 한 보낸 사람 으로부터 온 것 처럼 보이는 메시지의 중요 한 정보를 도용 하는 전자 메일 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-104">*Phishing* an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="2366c-105">특정 종류의 피싱이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-105">There are specific categories of phishing.</span></span> <span data-ttu-id="2366c-106">예시:</span><span class="sxs-lookup"><span data-stu-id="2366c-106">For example:</span></span>

- <span data-ttu-id="2366c-107">**스피어 피싱은** 특히 대상 지정 된 받는 사람에 맞게 특별히 조정 된 콘텐츠 (일반적으로 공격자가 받는 사람을 검사 한 후)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="2366c-108">**Whaling** 은 최대의 효과를 위해 임원 또는 조직 내의 다른 높은 가치 표적에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="2366c-109">**BEC (비즈니스 전자 메일 손상)** 은 위조 된 보낸 사람 (금융 관리자, 고객, 신뢰할 수 있는 파트너 등)을 사용 하 여 대금을 지불 하 고 자금을 전송 하거나 고객 데이터를 공개 하기 위한 노력을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="2366c-110">데이터를 암호화 하 고 해당 암호를 해독 하기 위한 지불을 요청 하는 **랜 섬 웨어** 는 피싱 메시지에서 거의 항상 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="2366c-111">피싱 방지 보호는 암호화 된 파일의 암호를 해독 하는 데 도움이 되지만, 랜 섬 웨어 캠페인과 연결 된 초기 피싱 메시지를 검색 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="2366c-112">랜 섬 웨어 공격에서 복구 하는 방법에 대 한 자세한 내용은 [Microsoft 365에서 랜 섬 웨어 공격 으로부터 복구](recover-from-ransomware.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2366c-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="2366c-113">공격에 대 한 복잡성이 증가 함에 따른 숙련 된 사용자가 복잡 한 피싱 메시지를 식별 하기는 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="2366c-114">다행 스럽게도 EOP (Exchange Online Protection)와 Office 365 Advanced Threat Protection (Office 365 ATP)의 추가 기능은 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="2366c-115">EOP의 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="2366c-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="2366c-116">EOP (즉, ATP가 없는 Microsoft 365 조직)에는 피싱 위협 으로부터 조직을 보호 하는 데 도움이 되는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="2366c-117">**스푸핑 인텔리전스**: 내부 및 외부 도메인의 보낸 사람으로부터 스푸핑된 메시지를 검토하고 해당 보낸 사람을 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="2366c-118">자세한 내용은 [Configure 스푸핑이 intelligence IN EOP](learn-about-spoof-intelligence.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2366c-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="2366c-119">**EOP의 피싱 방지 정책**: 스푸핑 인텔리전스를 설정 하거나 해제 하 고, Outlook에서 인증 되지 않은 보낸 사람 id를 설정/해제 하 고, 차단 된 스푸핑된 보낸 사람 (정크 메일 폴더 또는 격리로 이동)에 대 한 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="2366c-120">자세한 내용은 [EOP에서 피싱 방지 정책 구성을](configure-anti-phishing-policies-eop.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2366c-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="2366c-121">**암시적 전자 메일 인증**:[EOP에서는 위조](set-up-spf-in-office-365-to-help-prevent-spoofing.md)된 보낸 사람을 식별 하는 데 도움이 되는 보낸 [DMARC](use-dmarc-to-validate-email.md)사람 신뢰도, 보낸 사람 기록, 받는 사람 기록, 행태 분석 및 기타 고급 기법을 사용 하 여 인바운드 전자 메일에 대 한 표준 전자 메일 인증 [확인을 향상](use-dkim-to-validate-outbound-email.md)시킵니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="2366c-122">자세한 내용은 [Microsoft 365의 전자 메일 인증](email-validation-and-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2366c-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="2366c-123">Office 365 ATP의 추가 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="2366c-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="2366c-124">Office 365 ATP에는 추가 및 보다 고급 피싱 방지 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="2366c-125">**ATP 피싱 방지 정책**: 새 사용자 지정 정책을 만들고, 가장 설정을 구성 합니다 (가장에서 사용자 및 도메인 보호), 사서함 인텔리전스 설정 및 조정 가능한 고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="2366c-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="2366c-126">자세한 내용은 [Microsoft 365에서 ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2366c-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="2366c-127">피싱 방지 정책 및 ATP 피싱 방지 정책 간의 차이점에 대 한 자세한 내용은 [Microsoft 365에서 피싱 방지 정책을](set-up-anti-phishing-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2366c-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="2366c-128">**캠페인 보기**: 기계 학습 및 기타 휴리스틱 전체 서비스 및 조직에 대해 통합 된 피싱 공격과 관련 된 메시지를 식별 하 고 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="2366c-129">자세한 내용은 [Office 365 ATP의 캠페인 보기](campaigns.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2366c-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="2366c-130">**Attack 시뮬레이터**: 관리자는 가짜 피싱 메시지를 만들고 교육 도구로 내부 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="2366c-131">자세한 내용은 [Office 365 ATP의 Attack 시뮬레이터](attack-simulator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2366c-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="2366c-132">기타 피싱 방지 리소스</span><span class="sxs-lookup"><span data-stu-id="2366c-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="2366c-133">최종 사용자의 경우: [피싱 체계 및 기타 형태의 온라인 사기 행위 로부터 자신을 보호](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)합니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span></span>

- <span data-ttu-id="2366c-134">[Microsoft 365에서 보낸 사람 주소의 유효성을 검사 하 여 피싱을 방지 하는 방법](how-office-365-validates-the-from-address.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="2366c-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
