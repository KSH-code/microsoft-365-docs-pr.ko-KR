---
title: DLP 정책 만들기, 테스트 및 조정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 이 문서에서는 조직의 요구에 따라 DLP 정책을 만들고 테스트하고 조정하는 방법을 배우게 됩니다.
ms.openlocfilehash: e252c7328c59c246f739caf4b70acd44de010e42
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532521"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="76c23-103">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="76c23-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="76c23-104">DLP(데이터 손실 방지)를 사용하면 중요한 정보가 실수로 공유되거나 의도치 않은 공유를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-104">Data loss prevention (DLP) helps you prevent the unintentional or accidental sharing of sensitive information.</span></span>

<span data-ttu-id="76c23-105">DLP는 전자 메일 메시지와 파일에 신용 카드 번호와 같은 중요한 정보를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-105">DLP examines email messages and files for sensitive information, like a credit card number.</span></span> <span data-ttu-id="76c23-106">DLP를 사용하면 중요한 정보를 검색하고 다음 작업을 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-106">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="76c23-107">감사 목적으로 이벤트 기록</span><span class="sxs-lookup"><span data-stu-id="76c23-107">Log the event for auditing purposes</span></span>
- <span data-ttu-id="76c23-108">전자 메일을 보내거나 파일을 공유하는 최종 사용자에게 경고 표시</span><span class="sxs-lookup"><span data-stu-id="76c23-108">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="76c23-109">전자 메일 또는 파일 공유가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-109">Actively block the email or file sharing from taking place</span></span>

## <a name="permissions"></a><span data-ttu-id="76c23-110">권한</span><span class="sxs-lookup"><span data-stu-id="76c23-110">Permissions</span></span>

<span data-ttu-id="76c23-111">DLP 정책을 만드는 규정 준수 팀 구성원에게는 준수 센터에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-111">Members of your compliance team who will create DLP policies need permissions to the Compliance Center.</span></span> <span data-ttu-id="76c23-112">기본적으로 테넌트 관리자는 규정 준수 관리자 및 기타 사용자 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-112">By default, your tenant admin will have access can give compliance officers and other people access.</span></span> <span data-ttu-id="76c23-113">다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="76c23-113">Follow these steps:</span></span>
  
1. <span data-ttu-id="76c23-114">Microsoft 365에서 그룹을 생성하고 규정 준수 책임자를 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="76c23-114">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="76c23-115">보안 &amp; 준수 센터의 **사용 권한** 페이지에서 역할 그룹을 생성하십시오.</span><span class="sxs-lookup"><span data-stu-id="76c23-115">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="76c23-116">역할 그룹을 만드는 동안  역할 선택 섹션을 사용하여 역할 그룹에 DLP 준수 관리 역할을 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="76c23-116">While creating the role group, use the **Choose Roles** section to add the following role to the role group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="76c23-117">**구성원 선택** 섹션을 사용하여 이전에 만든 Microsoft 365 그룹을 역할 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-117">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="76c23-118">보기 전용 **DLP 준수 관리** 역할을 사용하여 DLP 정책 및 DLP 보고서에 대한 보기 전용 권한이 있는 역할 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-118">Use the **View-Only DLP Compliance Management** role to create role group with view-only privileges to the DLP policies and DLP reports.</span></span>

<span data-ttu-id="76c23-119">더 자세한 내용은 [Office 365 준수 센터 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="76c23-119">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="76c23-120">이러한 사용 권한은 정책을 적용하지 않는 DLP 정책을 만들고 적용하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-120">These permissions are required to create and apply a DLP policy not to enforce policies.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="76c23-121">DLP에서 중요한 정보를 검색하는 방법</span><span class="sxs-lookup"><span data-stu-id="76c23-121">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="76c23-122">DLP는 특정 키워드와 일치하는 패턴에 대한 근접성 같은 다른 지표와 함께 정규식(RegEx) 패턴 일치를 통해 중요한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-122">DLP finds sensitive information by regular expression (RegEx) pattern matching, in combination with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="76c23-123">예를 들어 VISA 신용 카드 번호는 16자리입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-123">For example, a VISA credit card number has 16 digits.</span></span> <span data-ttu-id="76c23-124">그러나 이러한 숫자는 1111-1111-1111-1111, 1111 1111 1111 또는 111111111111111111111111111111111111111과 같은 다양한 방식으로 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-124">But, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="76c23-125">16자리 문자열은 반드시 신용 카드 번호가 아니며 지원 센터 시스템의 티켓 번호 또는 하드웨어 일련 번호일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-125">Any 16-digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="76c23-126">신용 카드 번호와 무해한 16자리 문자열 간의 차이를 확인하기 위해 다양한 신용 카드 브랜드의 알려진 패턴과 일치하는지 확인하는 계산(체크 um)이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-126">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="76c23-127">DLP가 신용 카드 만료 날짜일 수 있는 "VISA" 또는 "AMEX"과 같은 키워드를 찾을 경우 DLP는 해당 데이터를 사용하여 문자열이 신용 카드 번호인지 여부를 결정하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-127">If DLP finds keywords such as "VISA" or "AMEX", near date values that might be the credit card expiry date, DLP also uses that data to help it decide whether the string is a credit card number or not.</span></span>

<span data-ttu-id="76c23-128">즉, DLP는 전자 메일에서 이러한 두 텍스트 문자열 간의 차이를 인식할 수 있을 만큼 스마트합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-128">In other words, DLP is smart enough to recognize the difference between these two strings of text in an email:</span></span>

- <span data-ttu-id="76c23-129">"새 노트북을 주문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-129">"Can you order me a new laptop.</span></span> <span data-ttu-id="76c23-130">내 VISA 번호 1111-1111-1111-1111, 만료 11/22를 사용하여 예상 배달 날짜를 보낼 수 있습니다."</span><span class="sxs-lookup"><span data-stu-id="76c23-130">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it."</span></span>
- <span data-ttu-id="76c23-131">"내 노트북 일련 번호는 2222-2222-2222-2222이고 2010년 11월에 구입했습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-131">"My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="76c23-132">제 여행비가 아직 승인되지 않았나요?"</span><span class="sxs-lookup"><span data-stu-id="76c23-132">By the way, is my travel visa approved yet?"</span></span>

<span data-ttu-id="76c23-133">각 [정보 유형이](sensitive-information-type-entity-definitions.md) 검색되는 방법을 설명하는 중요한 정보 유형 엔터티 정의를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76c23-133">See [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="76c23-134">데이터 손실 방지로 시작하는 위치</span><span class="sxs-lookup"><span data-stu-id="76c23-134">Where to start with data loss prevention</span></span>

<span data-ttu-id="76c23-135">데이터 누출 위험이 완전히 명확하지 않은 경우 DLP 구현을 정확히 어디서 시작해야 하는지 해결하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-135">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="76c23-136">다행히 DLP 정책을 "테스트 모드"로 실행하여 켜기 전에 효율성과 정확성을 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-136">Fortunately, DLP policies can be run in "test mode", allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="76c23-137">사용자에 대한 DLP Exchange Online 관리 센터를 통해 관리할 Exchange 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-137">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="76c23-138">그러나 보안 및 준수 센터를 통해 모든 & DLP 정책을 구성할 수 있으므로 이 문서의 데모에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-138">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="76c23-139">보안 및 & 센터에서 데이터 손실 방지 정책 아래에 DLP **정책을 찾을 수**  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="76c23-139">In the Security & Compliance Center, you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="76c23-140">정책 **만들기를 선택하면** 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-140">Choose **Create a policy** to start.</span></span>

<span data-ttu-id="76c23-141">Microsoft 365 정책을 만드는 데 사용할 수 있는 [다양한 DLP](what-the-dlp-policy-templates-include.md) 정책 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-141">Microsoft 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create policies.</span></span> <span data-ttu-id="76c23-142">오스트레일리아 비즈니스를 하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-142">Let's say that you're an Australian business.</span></span> <span data-ttu-id="76c23-143">오스트레일리아에서 템플릿을 필터링하고 재무, 의료 및 건강 및 개인 정보를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-143">You can filter the templates on Australia, and choose Financial, Medical and Health, and Privacy.</span></span>

![국가 또는 지역 선택 옵션](../media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="76c23-145">이 데모에서는 오스트레일리아 세금 파일 번호(TFN) 및 운전 면허 번호의 정보 유형을 포함하는 오스트레일리아 PII(개인 식별 정보) 데이터를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-145">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![정책 템플릿 선택 옵션](../media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="76c23-147">새 DLP 정책에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-147">Give your new DLP policy a name.</span></span> <span data-ttu-id="76c23-148">기본 이름은 DLP 정책 템플릿과 일치하지만 동일한 템플릿에서 여러 정책을 만들 수 있기 때문에 보다 설명적인 이름을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-148">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![정책 이름을 지정하는 옵션](../media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="76c23-150">정책을 적용할 위치를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="76c23-150">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="76c23-151">DLP 정책은 온라인, Exchange Online, SharePoint 정책에 적용할 비즈니스용 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="76c23-151">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="76c23-152">이 정책을 모든 위치에 적용하도록 구성한 그대로 두도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="76c23-152">I am going to leave this policy configured to apply to all locations.</span></span>

![모든 위치를 선택하는 옵션](../media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="76c23-154">첫 번째 **정책** 설정 지금은 기본값을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-154">At the first **Policy Settings** step, just accept the defaults for now.</span></span> <span data-ttu-id="76c23-155">DLP 정책을 사용자 지정할 수 있지만 기본값은 시작할 수 있는 좋은 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-155">You can customize DLP policies, but the defaults are a fine place to start.</span></span>

![보호할 콘텐츠 형식을 사용자 지정하는 옵션](../media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="76c23-157">다음을 클릭하면 추가 사용자 지정 옵션이 있는  추가 정책 설정 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-157">After clicking Next,\*\* you'll be presented with an additional **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="76c23-158">방금 테스트하는 정책의 경우 조정을 시작할 수 있는 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-158">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="76c23-159">지금은 정책 팁을 해제했습니다. 이 단계는 단지 테스트만 하고 사용자에게 아무것도 표시하지 않고 싶지 않은 경우 취할 적절한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-159">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="76c23-160">정책 팁은 DLP 정책을 위반할 것 같은 경고를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-160">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="76c23-161">예를 들어 Outlook 파일에 신용 카드 번호가 포함되어 있으며 전자 메일이 거부될 것 같은 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-161">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="76c23-162">정책 팁의 목표는 비규준 행동이 발생하기 전에 중지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-162">The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="76c23-163">또한 인스턴스 수를 10에서 1로 줄이면 이 정책은 데이터의 대량 공유가 아니라 오스트레일리아 PII 데이터 공유를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-163">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="76c23-164">또한 문제 보고서 전자 메일에 다른 받는 사람을 추가하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-164">I've also added another recipient to the incident report email.</span></span>

![추가 정책 설정](../media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="76c23-166">마지막으로 이 정책을 처음에 테스트 모드에서 실행하도록 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-166">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="76c23-167">테스트 모드에서 정책 팁을 사용하지 않도록 설정하는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-167">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="76c23-168">이렇게 하면 정책에서 정책 팁을 사용할 수 있는 유연성을 제공하지만 테스트 중에 정책 팁을 표시하거나 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-168">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![정책을 먼저 테스트하는 옵션](../media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="76c23-170">마지막 검토 화면에서 만들기를 **클릭하여** 정책 만들기를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-170">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="76c23-171">DLP 정책 테스트</span><span class="sxs-lookup"><span data-stu-id="76c23-171">Test a DLP policy</span></span>

<span data-ttu-id="76c23-172">새 DLP 정책은 약 1시간 이내에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-172">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="76c23-173">정상적인 사용자 활동에 의해 트리거될 때까지 기다리거나 직접 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-173">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="76c23-174">이전에서는 DLP [](sensitive-information-type-entity-definitions.md)일치를 트리거하는 방법에 대한 정보를 제공하는 중요한 정보 유형 엔터티 정의에 연결했습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-174">Earlier I linked to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="76c23-175">예를 들어 이 문서에 대해 만든 DLP 정책은 오스트레일리아 세금 파일 번호(TFN)를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-175">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="76c23-176">설명서에 따라 일치는 다음 조건을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-176">According to the documentation, the match is based on the following criteria.</span></span>

![오스트레일리아 세금 파일 번호에 대한 설명서](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="76c23-178">TFN 검색을 다소 흐리게 보여 주기 위해 "세금 파일 번호"와 근접한 9자리 문자열이 있는 전자 메일은 문제 없이 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-178">To demonstrate TFN detection in a rather blunt manner, an email with the words "Tax file number" and a 9 digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="76c23-179">DLP 정책이 트리거되지 않는 이유는 9자리 문자열이 무해한 숫자 문자열이 아니라 유효한 TFN을 나타내는 체크um을 전달해야 하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-179">The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![체크 아웃을 통과하지 않는 오스트레일리아 세금 파일 번호](../media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="76c23-181">이에 비해 "Tax file number"라는 단어와 체크 체크 um을 전달하는 유효한 TFN이 있는 전자 메일은 정책을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-181">In comparison, an email with the words "Tax file number" and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="76c23-182">여기서 사용하는 레코드의 경우 사용 중이던 TFN은 유효하지만 정품이 아닌 TFN을 생성하는 웹 사이트에서 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-182">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="76c23-183">이러한 사이트는 DLP 정책을 테스트할 때 가장 일반적인 실수 중 하나는 유효하지 않은 위조 번호를 사용하고 체크 um을 통과하지 못하므로 정책을 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-183">Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![체크 아웃을 통과하는 오스트레일리아 세금 파일 번호](../media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="76c23-185">인시던트 보고서 전자 메일에는 검색된 중요한 정보의 유형, 검색된 인스턴스 수 및 검색의 신뢰 수준이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-185">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![감지된 세금 파일 번호를 표시하는 인시던트 보고서](../media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="76c23-187">테스트 모드에서 DLP 정책을 그대로 두고 문제 보고서 전자 메일을 분석하는 경우 DLP 정책의 정확성과 DLP 정책이 적용될 때의 효율성에 대한 느낌을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-187">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="76c23-188">문제 보고서 외에도 [DLP](view-the-dlp-reports.md) 보고서를 사용하여 테넌트 전체의 정책 일치에 대한 집계된 보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-188">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="76c23-189">DLP 정책 조정</span><span class="sxs-lookup"><span data-stu-id="76c23-189">Tune a DLP policy</span></span>

<span data-ttu-id="76c23-190">정책 적중을 분석할 때 정책의 행동 방법을 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-190">As you analyze your policy hits you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="76c23-191">간단한 예로, 전자 메일의 한 TFN이 문제가 아니라고 판단할 수 있지만(데모를 위해 이 TFN을 사용하겠지만) 두 개 이상의 인스턴스가 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-191">As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem.</span></span> <span data-ttu-id="76c23-192">여러 인스턴스는 직원이 HR 데이터베이스에서 외부 파티로 CSV 내보내기(예: 외부 회계 서비스)를 전자 메일로 전송하는 위험한 시나리오일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-192">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="76c23-193">확실히 감지하고 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-193">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="76c23-194">보안 및 & 센터에서 기존 정책을 편집하여 행동을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-194">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![정책 편집 옵션](../media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="76c23-196">정책이 특정 워크로드 또는 특정 사이트 및 계정에만 적용될 수 있도록 위치 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-196">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![특정 위치를 선택하는 옵션](../media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="76c23-198">또한 정책 설정을 조정하고 요구 사항에 맞게 규칙을 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-198">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![규칙 편집 옵션](../media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="76c23-200">DLP 정책 내에서 규칙을 편집할 때 다음을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-200">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="76c23-201">규칙을 트리거할 중요한 데이터의 인스턴스 유형 및 수를 비롯한 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-201">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="76c23-202">콘텐츠에 대한 액세스 제한과 같은 수행되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-202">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="76c23-203">사용자 알림 - 전자 메일 클라이언트 또는 웹 브라우저에서 사용자에게 표시되는 정책 팁입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-203">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="76c23-204">사용자 오버라이드는 사용자가 전자 메일 또는 파일 공유를 계속할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-204">User overrides determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="76c23-205">관리자에게 알리기 위해 문제 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-205">Incident reports, to notify administrators.</span></span>

![규칙의 일부를 편집하는 옵션](../media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="76c23-207">이 데모의 경우 정책에 사용자 알림을 추가하고(적절한 사용자 인식 교육 없이 이 작업을 수행하도록 주의) 사용자가 업무 정당성으로 또는 가음성으로 태그를 지정하여 정책을 다시 정당화할 수 있도록 허용했습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-207">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="76c23-208">조직의 정책에 대한 추가 정보를 포함하거나 사용자에게 질문이 있는 경우 지원에 문의하라는 메시지를 표시하려는 경우 전자 메일 및 정책 팁 텍스트를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-208">Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![사용자 알림 및 오버라이드에 대한 옵션](../media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="76c23-210">이 정책에는 볼륨과 볼륨이 낮은 볼륨을 처리하는 두 가지 규칙이 포함되어 있으므로 원하는 작업으로 두 규칙을 모두 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-210">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="76c23-211">특성에 따라 사례를 다르게 처리하기 위한 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-211">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="76c23-212">예를 들어 볼륨이 낮은 위반에 대해 다시 시야를 허용하지만 볼륨 위반이 많은 경우 다시 정당화는 허용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-212">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![볼륨이 큰 규칙 1개 및 볼륨이 적은 규칙 1개](../media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="76c23-214">또한 정책을 위반하는 콘텐츠에 대한 액세스를 실제로 차단하거나 제한하려면 규칙에 대한 작업을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-214">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![콘텐츠에 대한 액세스를 제한하는 옵션](../media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="76c23-216">이러한 변경 내용을 정책 설정에 저장한 후 정책의 기본 설정 페이지로 돌아가서 정책이 테스트 모드에 있는 동안 사용자에게 정책 팁을 표시하는 옵션도 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-216">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="76c23-217">이는 최종 사용자에게 DLP 정책을 도입하고 생산성에 영향을 미치는 너무 많은 오판정을 위험에 노출하지 않고 사용자 인식 교육을 하는 효과적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-217">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![테스트 모드에서 정책 팁을 표시하는 옵션](../media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="76c23-219">서버 쪽(또는 원하는 경우 클라우드 쪽)에서는 다양한 처리 간격으로 인해 변경이 즉시 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-219">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="76c23-220">사용자에게 새 정책 팁을 표시하는 DLP 정책을 변경하는 경우 사용자가 24시간마다 정책 변경을 검사하는 Outlook 클라이언트에서 변경 내용이 즉시 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-220">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="76c23-221">테스트 속도를 향상하려면 이 레지스트리 수정을 사용하여 [PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)키에서 마지막 다운로드 타임스탬프를 지우면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-221">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="76c23-222">Outlook 다음에 다시 시작하고 전자 메일 메시지 작성을 시작할 때 최신 정책 정보를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-222">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="76c23-223">정책 팁을 사용하도록 설정한 경우 사용자는 정책 팁을 Outlook 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-223">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![가짓 긍정 보고 옵션이 있는 정책 팁](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="76c23-225">가짓 긍정 조사</span><span class="sxs-lookup"><span data-stu-id="76c23-225">Investigate false positives</span></span>

<span data-ttu-id="76c23-226">DLP 정책 템플릿이 바로 완벽한 것은 아니며,</span><span class="sxs-lookup"><span data-stu-id="76c23-226">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="76c23-227">사용자 환경에서 발생하는 일부 오판정이 발견될 가능성이 높기 때문에 정책을 적절하게 테스트하고 조정하는 데 시간을 들이고 DLP 배포를 쉽게 하는 것이 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-227">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="76c23-228">다음은 가짓 긍정의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-228">Here's an example of a false positive.</span></span> <span data-ttu-id="76c23-229">이 전자 메일은 무해합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-229">This email is quite harmless.</span></span> <span data-ttu-id="76c23-230">사용자가 자신의 휴대폰 번호를 다른 사람에게 제공하며 전자 메일 서명을 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-230">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![가짓 긍정 정보를 표시하는 전자 메일](../media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="76c23-232">그러나 사용자에게 전자 메일에 중요한 정보, 특히 오스트레일리아 운전 면허 번호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-232">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![정책 팁에서 가짓 긍정 보고 옵션](../media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="76c23-234">사용자는 가짓 긍정을 보고할 수 있으며, 관리자가 발생한 이유를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-234">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="76c23-235">문제 보고서 전자 메일에서 전자 메일은 가짓 긍정으로 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-235">In the incident report email, the email is flagged as a false positive.</span></span>

![가짓 긍정을 표시하는 문제 보고서](../media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="76c23-237">이 드라이버의 라이선스 사례는 한 가지 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-237">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="76c23-238">이러한 가양성 발생의 원인은 "호주 운전 면허증" 유형이 "10자리 문자열의 일부인 문자열도 포함되는 9자리 문자열"에 의해 트리거되는 것이기 때문에 키워드 "sydney nsw"(대/없이)와의 근접성은 300자 이내입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-238">The reason this false positive has occurred is that the "Australian Driver's License" type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords "sydney nsw" (not case sensitive).</span></span> <span data-ttu-id="76c23-239">따라서 사용자가 시드니에 있기 때문에 전화 번호와 전자 메일 서명에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-239">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>


<span data-ttu-id="76c23-240">한 가지 옵션은 정책에서 오스트레일리아 운전 면허 정보 유형을 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-240">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="76c23-241">이 템플릿은 DLP 정책 템플릿의 일부이기 때문에 이 템플릿에 있지만 강제로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-241">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="76c23-242">세금 파일 번호에만 관심이 있으며 운전 면허증이 아닌 경우 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-242">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="76c23-243">예를 들어 정책의 낮은 볼륨 규칙에서 제거하 고 볼륨 규칙에 그대로 두면 여러 드라이버 라이선스 목록이 계속 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-243">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>
 
<span data-ttu-id="76c23-244">또 다른 옵션은 인스턴스 수를 늘려 인스턴스가 여러 개 있을 때만 적은 볼륨의 드라이버 라이선스가 검색될 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-244">Another option is to increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![인스턴스 수 편집 옵션](../media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="76c23-246">인스턴스 수를 변경하는 것 외에도 일치 정확도(또는 신뢰도)를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-246">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="76c23-247">중요한 정보 유형에 여러 패턴이 있는 경우 규칙이 특정 패턴과만 일치하도록 규칙에서 일치 정확도를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-247">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="76c23-248">예를 들어 가짓 긍정을 줄이기 위해 신뢰 수준이 가장 높은 패턴만 일치하게 규칙의 일치 정확도를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-248">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="76c23-249">신뢰 수준에 대한 자세한 내용은 신뢰 수준을 사용하여 규칙을 조정하는 [방법을 참조하세요.](data-loss-prevention-policies.md#match-accuracy)</span><span class="sxs-lookup"><span data-stu-id="76c23-249">For more information on confidence levels, see [How to use confidence level to tune your rules](data-loss-prevention-policies.md#match-accuracy).</span></span>

<span data-ttu-id="76c23-250">마지막으로 좀 더 고급화하려는 경우 중요한 정보 유형을 사용자 지정할 수 있습니다. 예를 들어 호주 운전 면허 번호에 대한 [](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)키워드 목록에서 "Sydney NSW"를 제거하여 위에 트리거된 가긍성 문제를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-250">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australia driver's license number](sensitive-information-type-entity-definitions.md#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="76c23-251">XML 및 PowerShell을 사용하여 이 작업을 하는 방법에 대한 자세한 내용은 기본 제공 중요한 정보 유형 사용자 [지정을 참조하세요.](customize-a-built-in-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="76c23-251">To learn how to do this by using XML and PowerShell, see [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-on-a-dlp-policy"></a><span data-ttu-id="76c23-252">DLP 정책 켜기</span><span class="sxs-lookup"><span data-stu-id="76c23-252">Turn on a DLP policy</span></span>

<span data-ttu-id="76c23-253">DLP 정책이 중요한 정보 유형을 정확하고 효과적으로 감지하고 최종 사용자가 적용되고 있는 정책을 사용할 준비가 된 것이 만족스러우면 정책을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-253">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![정책을 켜는 옵션](../media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="76c23-255">정책이 언제 적용될지 기다리는 경우 보안 커넥트 준수 센터 [PowerShell로](/powershell/exchange/connect-to-scc-powershell) & [Get-DlpCompliancePolicy cmdlet을](/powershell/module/exchange/get-dlpcompliancepolicy) 실행하여 DistributionStatus를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-255">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the [Get-DlpCompliancePolicy cmdlet](/powershell/module/exchange/get-dlpcompliancepolicy) to see the DistributionStatus.</span></span>

![PowerShell에서 cmdlet 실행](../media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="76c23-257">DLP 정책을 켜고 나면 원하는 최종 테스트를 실행하여 예상되는 정책 작업이 발생하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-257">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="76c23-258">신용 카드 데이터와 같은 정보를 테스트하려는 경우 체크 아웃을 통과하고 정책을 트리거하는 샘플 신용 카드 또는 기타 개인 정보를 생성하는 방법에 대한 정보가 있는 웹 사이트가 온라인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-258">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="76c23-259">사용자 다시 설정이 허용되는 정책은 정책 팁의 일부로 사용자에게 해당 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-259">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![사용자 오버라이드를 허용하는 정책 팁](../media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="76c23-261">콘텐츠를 제한하는 정책은 정책 팁의 일부로 사용자에게 경고를 표시하고 전자 메일을 보내지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-261">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![콘텐츠가 제한되는 정책 팁](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="76c23-263">요약</span><span class="sxs-lookup"><span data-stu-id="76c23-263">Summary</span></span>

<span data-ttu-id="76c23-264">데이터 손실 방지 정책은 모든 유형의 조직에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-264">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="76c23-265">일부 DLP 정책 테스트는 정책 팁, 최종 사용자 다시 설정 및 인시던트 보고서와 같은 제어로 인해 위험 수준이 낮은 연습입니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-265">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports.</span></span> <span data-ttu-id="76c23-266">일부 DLP 정책을 조용히 테스트하여 조직에서 이미 발생하는 위반 유형을 확인한 다음 가음성 비율이 낮은 정책을 만들어 사용자에게 허용 및 허용되지 않는 내용을 교육한 다음 DLP 정책을 조직에 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c23-266">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>