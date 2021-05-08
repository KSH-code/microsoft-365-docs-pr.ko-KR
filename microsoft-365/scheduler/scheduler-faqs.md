---
title: FAQ에 Microsoft 365 스케줄러
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: FAQ에 Microsoft 365 스케줄러
ms.openlocfilehash: 12c2c00761b9a10fac6c62bc4d7ff5909ac935a7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286264"
---
# <a name="scheduler-for-microsoft-365-faqs"></a><span data-ttu-id="714da-103">FAQ에 Microsoft 365 스케줄러</span><span class="sxs-lookup"><span data-stu-id="714da-103">Scheduler for Microsoft 365 FAQs</span></span>

<span data-ttu-id="714da-104">**질문:** Scheduler는 cortana for Windows, *Daily Briefing Email* 및 *Play My Emails와* 같은 다른 *Cortana* 기능과 어떻게 통합하나요?</span><span class="sxs-lookup"><span data-stu-id="714da-104">**Question:** How does Scheduler integrate with other Cortana features, such as *Cortana for Windows*, *Daily Briefing Email*, and *Play My Emails*?</span></span></br>
<span data-ttu-id="714da-105">스케줄러는 다른 Cortana 기능과는 독립적인 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="714da-105">Scheduler is an independent service from other Cortana features.</span></span> <span data-ttu-id="714da-106">다른 Cortana 기능은 테넌트 수준에서 사용하지 않도록 설정할 수 있으며, 여전히 전자 메일 주소를 사용하여 스케줄러를 cortana@yourdomain.com 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-106">Other Cortana features can be disabled at the tenant level, and Scheduler can still be enabled by using the cortana@yourdomain.com email address.</span></span> <span data-ttu-id="714da-107">현재 사용자는 전자 메일을 통해서만 스케줄러와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-107">Currently, users can only interact with Scheduler via email.</span></span>

<span data-ttu-id="714da-108">**질문:** 이 방식은 모든 작업에서만 Outlook?</span><span class="sxs-lookup"><span data-stu-id="714da-108">**Question:** Does this work only with Outlook?</span></span> <span data-ttu-id="714da-109">다른 전자 메일 제품이 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="714da-109">Are other email products supported?</span></span></br>
<span data-ttu-id="714da-110">위의 세 가지 요구 사항 이외에 라이선스가 있는 한 사용자는 모든 디바이스의 모든 전자 메일 cortana@yourdomain.com 전자 메일 클라이언트에서 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-110">As long as you have a license, Other than the three requirements above, users can email cortana@yourdomain.com from any email client on any device.</span></span>

<span data-ttu-id="714da-111">**질문:** 연락처가 OUTLOOK GAL 또는 다른 회사에 해당하는 개인 연락처 목록에 있을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="714da-111">**Question:** Can contacts be in a personal contact list on Outlook and GAL or other company equivalent?</span></span></br>
<span data-ttu-id="714da-112">모임 참석자는 회사 내부 또는 외부의 전자 메일 주소가 있는 모든 사람이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-112">Meeting attendees can be anyone with an email address inside or outside the company.</span></span> <span data-ttu-id="714da-113">안타깝게도 스케줄러는 오늘 GAL에서 이름을 찾아서 자동으로 이름을 전자 메일 주소/별칭으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-113">Unfortunately, Scheduler cannot automatically translate names to email addresses / alias by looking it up in the GAL today.</span></span>

<span data-ttu-id="714da-114">**질문:** 설치된 버전의 스케줄러(사내) 버전과 함께 스케줄러를 사용할 수 Outlook?</span><span class="sxs-lookup"><span data-stu-id="714da-114">**Question:** Can I use Scheduler with my installed version (on-premises) version of Outlook?</span></span></br>
<span data-ttu-id="714da-115">스케줄러를 사용하려면 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="714da-115">Scheduler requires Exchange Online.</span></span> <span data-ttu-id="714da-116">(On-prem) Exchange Server 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-116">Does not work with Exchange Server (On-Prem).</span></span> <span data-ttu-id="714da-117">모든 전자 메일 클라이언트, 데스크톱, Outlook, iOS, android, gmail 등에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="714da-117">Works with any email client, Outlook Desktop, OWA, iOS, android, gmail, and so on.</span></span>

<span data-ttu-id="714da-118">**질문:** 백그라운드에서 Outlook 열려야 합니까?</span><span class="sxs-lookup"><span data-stu-id="714da-118">**Question:** Does Outlook have to be open in the background?</span></span></br>
<span data-ttu-id="714da-119">Outlook 백그라운드에서 열 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-119">Outlook doesn't need to be open in the background.</span></span> <span data-ttu-id="714da-120">Cortana에 메일을 보내고 이를 통해 대량 작업을 하는 데만 Cortana를 보내면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="714da-120">All you need to do is send Cortana a mail and rely on it to do the bulk of the work.</span></span>

## <a name="frequently-asked-trust-and-privacy-questions"></a><span data-ttu-id="714da-121">자주 묻는 신뢰 및 개인 정보 관련 질문</span><span class="sxs-lookup"><span data-stu-id="714da-121">Frequently Asked Trust and Privacy Questions</span></span>

<span data-ttu-id="714da-122">**질문:** 스케줄러는 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="714da-122">**Question:** How does Scheduler work?</span></span></br>
<span data-ttu-id="714da-123">스케줄러는 휴먼 도우미로 강화된 AI(일정 인텔리전스)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="714da-123">Scheduler uses Scheduling Intelligence (AI) augmented with human assistants.</span></span> <span data-ttu-id="714da-124">AI 모델이 Cortana와의 자연스러운 통신을 지원해야 하는 경우 모임 요청은 검토 및 완료를 위해 사람으로 에스컬레이터됩니다.</span><span class="sxs-lookup"><span data-stu-id="714da-124">If AI models generate a need for support in the natural language of communication with Cortana, the meeting request escalates to a human for review and completion.</span></span>

<span data-ttu-id="714da-125">**질문:** Who 에스컬레이터 요청을 검토하는 사람이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="714da-125">**Question:** Who are the humans that review escalated requests?</span></span> </br>
<span data-ttu-id="714da-126">스케줄러 도우미는 개인 및 기밀 정보에 대해 인증된 Microsoft SSPA(공급자 보안 및 개인 정보 보호 보증)입니다.</span><span class="sxs-lookup"><span data-stu-id="714da-126">Scheduler assistants are Microsoft Supplier Security and Privacy Assurance (SSPA) certified for personal and highly confidential information.</span></span> 

<span data-ttu-id="714da-127">**질문:** SSPA 도우미는 어떤 것을 볼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="714da-127">**Question:** What can SSPA Assistants view?</span></span></br>
<span data-ttu-id="714da-128">스케줄러 및 SSPA 도우미는 Cortana로 주소가 있는 전자 메일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-128">Scheduler and the SSPA Assistants can view  the emails that are addressed to Cortana.</span></span> <span data-ttu-id="714da-129">스레드된 전자 메일 교환에서는 Cortana가 추가되기 전 스레드의 이전 전자 메일이 아니라 Cortana의 전자 메일 주소가 포함된 전자 메일만 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="714da-129">In a threaded email exchange, only the emails that include Cortana’s email address will be processed, not the previous emails in the thread before Cortana was added.</span></span>   

<span data-ttu-id="714da-130">**질문:** 고객 데이터가 스케줄러의 데이터 센터에 Flow?</span><span class="sxs-lookup"><span data-stu-id="714da-130">**Question:** Is customer data retained in the Scheduler’s Data Flow?</span></span> </br>
<span data-ttu-id="714da-131">스케줄러는 모든 고객 콘텐츠를 테넌트 경계 내에 저장하고 GDPR 지침, Microsoft 365 Trust & 개인 정보 취급 방침 및 테넌트 전자 메일 정책에 따라 데이터를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="714da-131">Scheduler stores all customer content within the tenant boundaries and retains data in accordance with GDPR guidelines, Microsoft 365 Trust & Privacy policies, and tenant email policies.</span></span>

<span data-ttu-id="714da-132">**질문:** 스케줄러는 내부 참석자에 대한 무료/사용 중 데이터를 어떻게 처리하나요?</span><span class="sxs-lookup"><span data-stu-id="714da-132">**Question:** How does Scheduler process the free/busy data of internal attendees?</span></span> </br>
<span data-ttu-id="714da-133">스케줄러의 자동화는 *findMeetingTimes* 서비스를 사용하여 참석자 및 이끌이가 함께 사용할 수 있는 시간을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="714da-133">Scheduler’s automation uses the *findMeetingTimes* service to identify times that are mutually available for attendees and the organizer.</span></span> <span data-ttu-id="714da-134">이 서비스는 Outlook 모임 양식의  추천 시간과 같은 다른 Outlook 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="714da-134">This service powers other Outlook experiences such as *Suggested Times* in the Outlook meeting form.</span></span> <span data-ttu-id="714da-135">무료/사용 중 참석자 정보는 명시적으로 사용 중이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-135">Free/busy attendee information is not consumed explicitly as free/busy blocks.</span></span> 

<span data-ttu-id="714da-136">**질문:** 스케줄러 GDPR이 규격인가요?</span><span class="sxs-lookup"><span data-stu-id="714da-136">**Question:** Is Scheduler GDPR Compliant?</span></span> </br>
<span data-ttu-id="714da-137">예.</span><span class="sxs-lookup"><span data-stu-id="714da-137">Yes.</span></span>

<span data-ttu-id="714da-138">**질문:** Who Cortana 사서함에 액세스할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="714da-138">**Question:** Who has access to the Cortana mailbox?</span></span> </br>
<span data-ttu-id="714da-139">스케줄러는 테넌트의 Cortana 사서함으로 전송되는 모임 요청 및 관련 전자 메일을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="714da-139">Scheduler processes meeting requests and associated emails that are sent to your tenant’s Cortana mailbox.</span></span> <span data-ttu-id="714da-140">Microsoft는 테넌트 관리자의 요청에 따라 Lockbox 승인을 통해서만 Cortana 사서함에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-140">Microsoft does not have any other access to the Cortana mailbox except through Lockbox approval at the request of the tenant admin.</span></span>  

<span data-ttu-id="714da-141">**질문:** 고객 데이터가 AI 모델을 교육하는 데 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="714da-141">**Question:** Is customer data used for training AI models?</span></span></br>
<span data-ttu-id="714da-142">데이터 교육 집합에 사용할 Microsoft 365 스케줄러의 고객 콘텐츠는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-142">No customer content from Scheduler for Microsoft 365 can be used for data training sets.</span></span> <span data-ttu-id="714da-143">모든 고객 콘텐츠는 고객 테넌트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714da-143">All customer content resides in the customer tenant.</span></span>  

<span data-ttu-id="714da-144">**질문:** 스케줄러가 암호화된 메일을 처리하나요?</span><span class="sxs-lookup"><span data-stu-id="714da-144">**Question:** Will Scheduler process encrypted mail?</span></span></br>
<span data-ttu-id="714da-145">아니요. 스케줄러 워크플로에서 암호화된 메일이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="714da-145">No, encrypted mail will be rejected by the Scheduler workflow.</span></span> 




