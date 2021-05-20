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
description: 이 문서에서는 조직의 필요에 따라 DLP 정책을 만들고 테스트하고 튜닝하는 방법을 배웁니다.
ms.openlocfilehash: 3b7f74605c8a825bb03244f3a861ad3cca8f550d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572576"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="4fb2a-103">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="4fb2a-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="4fb2a-104">DLP(데이터 손실 방지)를 사용하면 중요한 정보의 의도하지 않거나 우발적인 공유를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-104">Data loss prevention (DLP) helps you prevent the unintentional or accidental sharing of sensitive information.</span></span>

<span data-ttu-id="4fb2a-105">DLP는 신용 카드 번호와 같은 중요한 정보를 위해 이메일 메시지와 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-105">DLP examines email messages and files for sensitive information, like a credit card number.</span></span> <span data-ttu-id="4fb2a-106">DLP를 사용하면 중요한 정보를 감지하고 다음과 같은 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-106">Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="4fb2a-107">감사 목적으로 이벤트 로그기록</span><span class="sxs-lookup"><span data-stu-id="4fb2a-107">Log the event for auditing purposes</span></span>
- <span data-ttu-id="4fb2a-108">이메일을 보내거나 파일을 공유하는 최종 사용자에게 경고 표시</span><span class="sxs-lookup"><span data-stu-id="4fb2a-108">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="4fb2a-109">전자 메일 또는 파일 공유가 진행되는 것을 적극적으로 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-109">Actively block the email or file sharing from taking place</span></span>

## <a name="permissions"></a><span data-ttu-id="4fb2a-110">권한</span><span class="sxs-lookup"><span data-stu-id="4fb2a-110">Permissions</span></span>

<span data-ttu-id="4fb2a-111">DLP 정책을 만드는 규정 준수 팀 구성원에게는 준수 센터에 대한 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-111">Members of your compliance team who will create DLP policies need permissions to the Compliance Center.</span></span> <span data-ttu-id="4fb2a-112">기본적으로 테넌트 관리자는 규정 준수 담당자 및 기타 사용자에게 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-112">By default, your tenant admin will have access can give compliance officers and other people access.</span></span> <span data-ttu-id="4fb2a-113">다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-113">Follow these steps:</span></span>
  
1. <span data-ttu-id="4fb2a-114">Microsoft 365에서 그룹을 생성하고 규정 준수 책임자를 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-114">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="4fb2a-115">보안 &amp; 준수 센터의 **사용 권한** 페이지에서 역할 그룹을 생성하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-115">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="4fb2a-116">역할 그룹을 만드는 동안 **역할 선택** 섹션을 사용하여 역할 그룹에 다음 역할을 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="4fb2a-116">While creating the role group, use the **Choose Roles** section to add the following role to the role group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="4fb2a-117">**구성원 선택** 섹션을 사용하여 이전에 만든 Microsoft 365 그룹을 역할 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-117">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="4fb2a-118">보기 **전용 DLP 규정 준수 관리** 역할을 사용하여 DLP 정책 및 DLP 보고서에 대한 보기 전용 권한이 있는 역할 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-118">Use the **View-Only DLP Compliance Management** role to create role group with view-only privileges to the DLP policies and DLP reports.</span></span>

<span data-ttu-id="4fb2a-119">더 자세한 내용은 [Office 365 준수 센터 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-119">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="4fb2a-120">이러한 권한은 정책을 적용하지 않는 DLP 정책을 만들고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-120">These permissions are required to create and apply a DLP policy not to enforce policies.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="4fb2a-121">DLP에 의해 민감한 정보를 감지하는 방법</span><span class="sxs-lookup"><span data-stu-id="4fb2a-121">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="4fb2a-122">DLP는 특정 키워드가 일치하는 패턴에 근접하는 것과 같은 다른 지표와 함께 정규 식(RegEx) 패턴 일치로 중요한 정보를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-122">DLP finds sensitive information by regular expression (RegEx) pattern matching, in combination with other indicators such as the proximity of certain keywords to the matching patterns.</span></span> <span data-ttu-id="4fb2a-123">예를 들어 VISA 신용 카드 번호는 16자리입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-123">For example, a VISA credit card number has 16 digits.</span></span> <span data-ttu-id="4fb2a-124">그러나 이러한 숫자는 1111-1111-1111-1111, 1111 1111 1111 또는 11111111111111111111111111111111111111과 같은 다양한 방식으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-124">But, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="4fb2a-125">모든 16 자리 문자열은 반드시 신용 카드 번호, 그것은 헬프 데스크 시스템에서 티켓 번호, 또는 하드웨어의 일련 번호가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-125">Any 16-digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware.</span></span> <span data-ttu-id="4fb2a-126">신용 카드 번호와 무해한 16자리 문자열의 차이를 구별하기 위해, 숫자가 다양한 신용 카드 브랜드의 알려진 패턴과 일치하는지 확인하기 위해 계산(checksum)이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-126">To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="4fb2a-127">DLP가 신용 카드 만료 날짜가 될 수 있는 날짜 값에 가까운 "VISA" 또는 "AMEX"와 같은 키워드를 발견한 경우 DLP는 해당 데이터를 사용하여 문자열이 신용 카드 번호인지 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-127">If DLP finds keywords such as "VISA" or "AMEX", near date values that might be the credit card expiry date, DLP also uses that data to help it decide whether the string is a credit card number or not.</span></span>

<span data-ttu-id="4fb2a-128">즉, DLP는 전자 메일의 이 두 문자열 간의 차이점을 인식할 수 있을 만큼 똑똑합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-128">In other words, DLP is smart enough to recognize the difference between these two strings of text in an email:</span></span>

- <span data-ttu-id="4fb2a-129">"새 노트북을 주문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-129">"Can you order me a new laptop.</span></span> <span data-ttu-id="4fb2a-130">비자 번호 1111-1111-1111-1111을 사용 하 여 11/22 만료 하 고 예상 배달 날짜를 보내 드립니다."</span><span class="sxs-lookup"><span data-stu-id="4fb2a-130">Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it."</span></span>
- <span data-ttu-id="4fb2a-131">"내 노트북 일련 번호는 2222-2222-2222-2222이며 2010 년 11 월에 구입했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-131">"My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010.</span></span> <span data-ttu-id="4fb2a-132">그런데, 내 여행 비자는 아직 승인?"</span><span class="sxs-lookup"><span data-stu-id="4fb2a-132">By the way, is my travel visa approved yet?"</span></span>

<span data-ttu-id="4fb2a-133">각 [정보 형식이 검색되는](sensitive-information-type-entity-definitions.md) 방법을 설명하는 중요한 정보 유형 엔터티 정의를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-133">See [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="4fb2a-134">데이터 손실 방지로 시작하는 위치</span><span class="sxs-lookup"><span data-stu-id="4fb2a-134">Where to start with data loss prevention</span></span>

<span data-ttu-id="4fb2a-135">데이터 유출의 위험이 완전히 명확하지 않을 때DLP 구현을 정확히 어디서부터 시작해야 하는지 알아내기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-135">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP.</span></span> <span data-ttu-id="4fb2a-136">다행히 DLP 정책은 "테스트 모드"에서 실행될 수 있으므로 켜기 전에 효율성과 정확성을 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-136">Fortunately, DLP policies can be run in "test mode", allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="4fb2a-137">Exchange Online 대한 DLP 정책은 Exchange 관리 센터를 통해 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-137">DLP policies for Exchange Online can be managed through the Exchange admin center.</span></span> <span data-ttu-id="4fb2a-138">그러나 보안 & 규정 준수 센터를 통해 모든 워크로드에 대해 DLP 정책을 구성할 수 있으므로 이 문서의 데모에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-138">But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article.</span></span> <span data-ttu-id="4fb2a-139">보안 & 규정 준수 **센터에서데이터 손실 방지** 정책에 따라 DLP 정책을 찾을 수  >  있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-139">In the Security & Compliance Center, you'll find the DLP policies under **Data loss prevention** > **Policy**.</span></span> <span data-ttu-id="4fb2a-140">시작할 **정책 만들기를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-140">Choose **Create a policy** to start.</span></span>

<span data-ttu-id="4fb2a-141">Microsoft 365 정책을 만드는 데 사용할 수 있는 다양한 [DLP 정책 템플릿을](what-the-dlp-policy-templates-include.md) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-141">Microsoft 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create policies.</span></span> <span data-ttu-id="4fb2a-142">당신이 호주 의 사업이라고 가정 해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-142">Let's say that you're an Australian business.</span></span> <span data-ttu-id="4fb2a-143">오스트레일리아의 템플릿을 필터링하고 재무, 의료 및 건강 및 개인 정보를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-143">You can filter the templates on Australia, and choose Financial, Medical and Health, and Privacy.</span></span>

![국가 또는 지역을 선택하는 옵션](../media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="4fb2a-145">이 데모에서는 호주 세금 파일 번호(TFN)와 운전 면허증 번호의 정보 유형을 포함하는 호주 개인 식별 정보(PII) 데이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-145">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![정책 템플릿을 선택하는 옵션](../media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="4fb2a-147">새 DLP 정책에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-147">Give your new DLP policy a name.</span></span> <span data-ttu-id="4fb2a-148">기본 이름은 DLP 정책 템플릿과 일치하지만 동일한 템플릿에서 여러 정책을 만들 수 있으므로 고유한 이름을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-148">The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![정책 이름을 지정하는 옵션](../media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="4fb2a-150">정책이 적용되는 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-150">Choose the locations that the policy will apply to.</span></span> <span data-ttu-id="4fb2a-151">DLP 정책은 Exchange Online, SharePoint 온라인 및 비즈니스용 OneDrive 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-151">DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="4fb2a-152">모든 위치에 적용하도록 구성된 이 정책을 떠날 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-152">I am going to leave this policy configured to apply to all locations.</span></span>

![모든 위치를 선택하는 옵션](../media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="4fb2a-154">첫 번째 **정책 설정** 단계에서는 현재의 기본 값을 수락하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-154">At the first **Policy Settings** step, just accept the defaults for now.</span></span> <span data-ttu-id="4fb2a-155">DLP 정책을 사용자 지정할 수 있지만 기본값은 시작하기에 좋은 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-155">You can customize DLP policies, but the defaults are a fine place to start.</span></span>

![보호할 콘텐츠 유형을 사용자 지정하는 옵션](../media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="4fb2a-157">다음을 클릭하면 더 많은 사용자 지정 옵션이 있는 정책 **설정** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-157">After clicking Next,\*\* you'll be presented with an more **Policy Settings** page with more customization options.</span></span> <span data-ttu-id="4fb2a-158">테스트하는 정책의 경우 몇 가지 조정을 시작할 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-158">For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="4fb2a-159">지금은 정책 팁을 끄었는데, 이는 단지 테스트 중이고 아직 사용자에게 아무것도 표시하고 싶지 않다면 취할 수있는 합리적인 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-159">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet.</span></span> <span data-ttu-id="4fb2a-160">정책 팁에는 DLP 정책을 위반하려는 사용자에게 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-160">Policy tips display warnings to users that they're about to violate a DLP policy.</span></span> <span data-ttu-id="4fb2a-161">예를 들어 Outlook 사용자는 첨부한 파일에 신용 카드 번호가 포함되어 있으며 전자 메일이 거부된다는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-161">For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected.</span></span> <span data-ttu-id="4fb2a-162">정책 팁의 목표는 비준수 동작이 발생하기 전에 중지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-162">The goal of policy tips is to stop the non-compliant behavior before it happens.</span></span>
- <span data-ttu-id="4fb2a-163">또한 인스턴스 수를 10개에서 1개로 줄였기 때문에 이 정책은 데이터의 대량 공유뿐만 아니라 호주 PII 데이터의 공유를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-163">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="4fb2a-164">또한 인시던트 보고서 이메일에 다른 수신자를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-164">I've also added another recipient to the incident report email.</span></span>

![추가 정책 설정](../media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="4fb2a-166">마지막으로 이 정책을 처음에 테스트 모드에서 실행하도록 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-166">Finally, I've configured this policy to run in test mode initially.</span></span> <span data-ttu-id="4fb2a-167">테스트 모드에서 정책 팁을 사용하지 않도록 설정하는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-167">Notice there's also an option here to disable policy tips while in test mode.</span></span> <span data-ttu-id="4fb2a-168">이렇게 하면 정책에 정책 팁을 활성화할 수 있는 유연성을 제공하지만 테스트 중에 정책 팁을 표시하거나 억제할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-168">This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![먼저 정책을 테스트하는 옵션](../media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="4fb2a-170">최종 검토 화면에서 **만들기를** 클릭하여 정책 만들기를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-170">On the final review screen, click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="4fb2a-171">DLP 정책 테스트</span><span class="sxs-lookup"><span data-stu-id="4fb2a-171">Test a DLP policy</span></span>

<span data-ttu-id="4fb2a-172">새 DLP 정책은 약 1시간 이내에 발효되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-172">Your new DLP policy will begin to take effect within about 1 hour.</span></span> <span data-ttu-id="4fb2a-173">앉아서 정상적인 사용자 활동에 의해 트리거될 때까지 기다리거나 직접 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-173">You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself.</span></span> <span data-ttu-id="4fb2a-174">이전에는 DLP 일치 항목을 트리거하는 방법에 대한 정보를 제공하는 [중요한 정보 유형 엔터티 정의에](sensitive-information-type-entity-definitions.md)연결했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-174">Earlier I linked to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="4fb2a-175">예를 들어 이 문서에서 만든 DLP 정책은 호주 세금 파일 번호(TFN)를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-175">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN).</span></span> <span data-ttu-id="4fb2a-176">문서에 따르면 경기는 다음 기준을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-176">According to the documentation, the match is based on the following criteria.</span></span>

![오스트레일리아 세금 파일 번호에 대한 문서](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="4fb2a-178">TFN 탐지를 다소 무딘 방식으로 입증하기 위해 "세금 파일 번호"라는 단어와 근접한 9자리 문자열이 있는 이메일은 아무런 문제없이 항해합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-178">To demonstrate TFN detection in a rather blunt manner, an email with the words "Tax file number" and a nine digit string in close proximity will sail through without any issues.</span></span> <span data-ttu-id="4fb2a-179">DLP 정책을 트리거하지 않는 이유는 9자리 문자열이 유효한 TFN이며 무해한 숫자 문자열임을 나타내는 체크섬을 통과해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-179">The reason it does not trigger the DLP policy is that the nine digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![체크섬을 통과하지 않는 호주 세금 파일 번호](../media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="4fb2a-181">이에 비해 "세금 파일 번호"라는 단어가 있는 전자 메일과 체크섬을 통과하는 유효한 TFN이 정책을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-181">In comparison, an email with the words "Tax file number" and a valid TFN that passes the checksum will trigger the policy.</span></span> <span data-ttu-id="4fb2a-182">여기에 레코드의 경우, 내가 사용하는 TFN은 유효하지만 정품이 아닌 정품 TfN을 생성하는 웹 사이트에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-182">For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs.</span></span> <span data-ttu-id="4fb2a-183">이러한 사이트는 DLP 정책을 테스트할 때 가장 일반적인 실수 중 하나가 유효하지 않고 체크섬을 통과하지 못하는 가짜 번호를 사용하는 것이므로 유용합니다(따라서 정책을 트리거하지 않음).</span><span class="sxs-lookup"><span data-stu-id="4fb2a-183">Such sites are useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![체크섬을 통과하는 호주 세금 파일 번호](../media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="4fb2a-185">인시던트 보고서 이메일에는 감지된 중요한 정보의 유형, 검색된 인스턴스 수 및 검색의 신뢰 도제가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-185">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![세금 파일 번호가 감지된 사고 보고서](../media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="4fb2a-187">DLP 정책을 테스트 모드로 두고 인시던트 보고서 이메일을 분석하는 경우 DLP 정책의 정확성과 적용 시 얼마나 효과적인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-187">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced.</span></span> <span data-ttu-id="4fb2a-188">인시던트 보고서 외에도 [DLP 보고서를 사용하여](view-the-dlp-reports.md) 테넌트 전체에서 정책 일치항목의 집계보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-188">In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="4fb2a-189">DLP 정책 조정</span><span class="sxs-lookup"><span data-stu-id="4fb2a-189">Tune a DLP policy</span></span>

<span data-ttu-id="4fb2a-190">정책 조회를 분석할 때 정책의 행동 방식을 일부 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-190">As you analyze your policy hits, you might want to make some adjustments to how the policies behave.</span></span> <span data-ttu-id="4fb2a-191">간단한 예로, 이메일의 하나의 TFN이 문제가 아니라고 판단할 수 있습니다(아직 는 여전히 생각하지만 데모를 위해 그것으로 가자)는 두 개 이상의 인스턴스가 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-191">As a simple example, you might determine that one TFN in an email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances are a problem.</span></span> <span data-ttu-id="4fb2a-192">CSV 내보내기를 HR 데이터베이스에서 외부 당사자로 전자 메일로 보내는 직원과 같은 여러 인스턴스는 외부 회계 서비스와 같은 위험한 시나리오일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-192">Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service.</span></span> <span data-ttu-id="4fb2a-193">확실히 뭔가 감지 하 고 차단 하는 것을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-193">Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="4fb2a-194">규정 준수 센터에서 기존 정책을 편집하여 동작을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-194">In the Compliance Center you can edit an existing policy to adjust the behavior.</span></span>

![정책 편집 옵션](../media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="4fb2a-196">정책이 특정 워크로드또는 특정 사이트 및 계정에만 적용되도록 위치 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-196">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![특정 위치를 선택하는 옵션](../media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="4fb2a-198">또한 정책 설정을 조정하고 필요에 맞게 규칙을 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-198">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![규칙을 편집하는 옵션](../media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="4fb2a-200">DLP 정책 내에서 규칙을 편집할 때 다음을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-200">When editing a rule within a DLP policy, you can change:</span></span>

- <span data-ttu-id="4fb2a-201">규칙을 트리거하는 중요한 데이터의 형식 및 인스턴스 수를 포함하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-201">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="4fb2a-202">콘텐츠에 대한 액세스를 제한하는 등의 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-202">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="4fb2a-203">이메일 클라이언트 또는 웹 브라우저에서 사용자에게 표시되는 정책 팁인 사용자 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-203">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="4fb2a-204">사용자 재정의는 사용자가 어쨌든 이메일 또는 파일 공유를 진행하도록 선택할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-204">User overrides determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="4fb2a-205">관리자에게 알리기 위해 인시던트 보고서를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-205">Incident reports, to notify administrators.</span></span>

![규칙의 일부를 편집하는 옵션](../media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="4fb2a-207">이 데모에서는 정책에 사용자 알림을 추가하고(적절한 사용자 인식 교육 없이 이 작업을 수행하십시오) 사용자가 비즈니스 명분으로 정책을 재정의하거나 거짓 긍정으로 표시하여 정책을 재정의할 수 있도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-207">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive.</span></span> <span data-ttu-id="4fb2a-208">조직의 정책에 대한 추가 정보를 포함하거나 사용자가 질문이 있는 경우 사용자에게 문의하라는 메시지를 표시하려는 경우 이메일 및 정책 팁 텍스트를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-208">You can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![사용자 알림 및 재정의에 대한 옵션](../media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="4fb2a-210">이 정책에는 대량 및 낮은 볼륨 처리를 위한 두 가지 규칙이 포함되어 있으므로 원하는 작업으로 모두 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-210">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want.</span></span> <span data-ttu-id="4fb2a-211">이것은 케이스의 특성에 따라 다르게 취급할 수 있는 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-211">This is an opportunity to treat cases differently depending on their characteristics.</span></span> <span data-ttu-id="4fb2a-212">예를 들어 볼륨이 적은 위반에 대한 재정의를 허용할 수 있지만 대량 위반에 대한 재정의는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-212">For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![대용량에 대한 하나의 규칙과 낮은 볼륨에 대한 하나의 규칙](../media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="4fb2a-214">또한 정책을 위반하는 콘텐츠에 대한 액세스를 실제로 차단하거나 제한하려면 규칙에 대한 작업을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-214">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![콘텐츠에 대한 액세스를 제한하는 옵션](../media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="4fb2a-216">이러한 변경 내용을 정책 설정에 저장한 후 정책의 기본 설정 페이지로 돌아가 정책이 테스트 모드에 있는 동안 사용자에게 정책 팁을 표시하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-216">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode.</span></span> <span data-ttu-id="4fb2a-217">이는 생산성에 영향을 미치는 거짓 긍정이 너무 많아도 위험없이 최종 사용자에게 DLP 정책을 도입하고 사용자 인식 교육을 수행하는 효과적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-217">This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![테스트 모드에서 정책 팁을 표시하는 옵션](../media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="4fb2a-219">서버 측(또는 원하는 경우 클라우드 측)에서는 다양한 처리 간격으로 인해 변경이 즉시 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-219">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals.</span></span> <span data-ttu-id="4fb2a-220">사용자에게 새 정책 팁을 표시하는 DLP 정책을 변경하는 경우 사용자는 변경 사항이 24시간마다 정책 변경을 확인하는 Outlook 클라이언트에서 즉시 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-220">If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours.</span></span> <span data-ttu-id="4fb2a-221">테스트를 위해 속도를 높이려면 이 레지스트리 수정 프로그램을 사용하여 [PolicyNudges 키에서 마지막 다운로드 타임스탬프를 지울](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-221">If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451).</span></span> <span data-ttu-id="4fb2a-222">Outlook 다음에 다시 시작할 때 최신 정책 정보를 다운로드하고 전자 메일 메시지 작성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-222">Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="4fb2a-223">정책 팁을 사용하도록 설정한 경우 사용자는 Outlook 팁을 보기 시작하고 잘못된 긍정이 발생할 때 사용자에게 잘못된 긍정을 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-223">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![거짓 긍정신고 옵션이 있는 정책 팁](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="4fb2a-225">거짓 긍정 조사</span><span class="sxs-lookup"><span data-stu-id="4fb2a-225">Investigate false positives</span></span>

<span data-ttu-id="4fb2a-226">DLP 정책 템플릿은 즉시 상자 밖으로 완벽하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-226">DLP policy templates are not perfect straight out of the box.</span></span> <span data-ttu-id="4fb2a-227">사용자 환경에서 발생하는 일부 거짓 긍정을 발견할 수 있으므로 정책을 적절하게 테스트하고 조정하는 데 시간을 할애하여 DLP 배포에 쉽게 참여하는 것이 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-227">It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="4fb2a-228">다음은 거짓 긍정의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-228">Here's an example of a false positive.</span></span> <span data-ttu-id="4fb2a-229">이 이메일은 매우 무해합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-229">This email is quite harmless.</span></span> <span data-ttu-id="4fb2a-230">사용자는 다른 사람에게 자신의 휴대 전화 번호를 제공하고, 자신의 이메일 서명을 포함.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-230">The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![거짓 긍정 정보를 보여주는 이메일](../media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="4fb2a-232">그러나 사용자는 이메일에 중요한 정보, 특히 호주 운전 면허증 번호가 포함되어 있음을 경고하는 정책 팁을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-232">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![정책 팁에서 거짓 긍정을 신고하는 옵션](../media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="4fb2a-234">사용자는 거짓 긍정을 보고할 수 있으며 관리자는 가짜 가발생한 이유를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-234">The user can report the false positive, and the administrator can look into why it has occurred.</span></span> <span data-ttu-id="4fb2a-235">인시던트 보고서 이메일에서 이메일은 거짓 긍정으로 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-235">In the incident report email, the email is flagged as a false positive.</span></span>

![거짓 긍정을 보여주는 사건 보고서](../media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="4fb2a-237">이 운전 면허증 케이스는 파고 들 기 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-237">This driver's license case is a good example to dig into.</span></span> <span data-ttu-id="4fb2a-238">이 거짓 긍정이 발생한 이유는 "호주 운전 면허증"유형이 키워드 "시드니 nsw"(케이스에 민감한 것이 아님)에 근접한 300자 이내의 9자리 문자열(10자리 문자열의 일부인 문자열)에 의해 트리거되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-238">The reason this false positive has occurred is that the "Australian Driver's License" type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords "Sydney nsw" (not case sensitive).</span></span> <span data-ttu-id="4fb2a-239">따라서 사용자가 시드니에 있기 때문에 전화 번호와 이메일 서명에 의해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-239">So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>


<span data-ttu-id="4fb2a-240">한 가지 옵션은 정책에서 호주 운전 면허증 정보 유형을 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-240">One option is to remove the Australian driver's license information type from the policy.</span></span> <span data-ttu-id="4fb2a-241">DLP 정책 템플릿의 일부이기 때문에 거기에 있지만 강제로 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-241">It's in there because it's part of the DLP policy template, but we're not forced to use it.</span></span> <span data-ttu-id="4fb2a-242">운전 면허증이 아닌 세금 파일 번호에만 관심이 있다면 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-242">If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it.</span></span> <span data-ttu-id="4fb2a-243">예를 들어 정책의 낮은 볼륨 규칙에서 제거할 수 있지만 여러 드라이버 라이센스 목록이 계속 검색되도록 대량 규칙에 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-243">For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>
 
<span data-ttu-id="4fb2a-244">또 다른 옵션은 인스턴스 수를 늘리므로 적은 양의 운전 면허증이 여러 인스턴스가 있는 경우에만 감지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-244">Another option is to increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![인스턴스 수를 편집하는 옵션](../media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="4fb2a-246">인스턴스 수를 변경하는 것 외에도 일치 정확도(또는 신뢰 수준)를 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-246">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level).</span></span> <span data-ttu-id="4fb2a-247">중요한 정보 유형에 여러 패턴이 있는 경우 규칙의 일치 정확도를 조정하여 규칙이 특정 패턴과만 일치되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-247">If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns.</span></span> <span data-ttu-id="4fb2a-248">예를 들어, 거짓 긍정을 줄이기 위해 규칙의 일치 정확도를 설정하여 패턴만 최고 신뢰수준과 일치하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-248">For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level.</span></span> <span data-ttu-id="4fb2a-249">신뢰 수준에 대한 자세한 내용은 [신뢰 도서 수준을 사용하여 규칙을 조정하는 방법을](data-loss-prevention-policies.md#match-accuracy)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-249">For more information on confidence levels, see [How to use confidence level to tune your rules](data-loss-prevention-policies.md#match-accuracy).</span></span>

<span data-ttu-id="4fb2a-250">마지막으로, 좀 더 진보하려면 중요한 정보 유형을 사용자 지정할 수 있습니다( 예를 [들어, 호주 운전 면허증 번호의](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)키워드 목록에서 "시드니 NSW"를 제거하여 위에서 트리거된 거짓 긍정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-250">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australia driver's license number](sensitive-information-type-entity-definitions.md#australia-drivers-license-number), to eliminate the false positive triggered above.</span></span> <span data-ttu-id="4fb2a-251">XML 및 PowerShell을 사용하여 이 작업을 수행하는 방법을 알아보려면 [기본 제공 에 민감한 정보 유형을 사용자 지정하는 방법을](customize-a-built-in-sensitive-information-type.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-251">To learn how to do this by using XML and PowerShell, see [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-on-a-dlp-policy"></a><span data-ttu-id="4fb2a-252">DLP 정책 켜기</span><span class="sxs-lookup"><span data-stu-id="4fb2a-252">Turn on a DLP policy</span></span>

<span data-ttu-id="4fb2a-253">DLP 정책이 중요한 정보 유형을 정확하고 효과적으로 감지하고 최종 사용자가 해당 정책을 처리할 준비가 되어 있다는 사실에 만족하면 정책을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-253">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![정책을 켜는 옵션](../media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="4fb2a-255">정책이 언제 적용될지 기다리는 경우 [보안 & 규정 준수 센터 PowerShell에 커넥트](/powershell/exchange/connect-to-scc-powershell) [Get-DlpCompliancePolicy cmdlet을](/powershell/module/exchange/get-dlpcompliancepolicy) 실행하여 배포 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-255">If you're waiting to see when the policy will take effect, [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the [Get-DlpCompliancePolicy cmdlet](/powershell/module/exchange/get-dlpcompliancepolicy) to see the DistributionStatus.</span></span>

![파워쉘에서 cmdlet 실행](../media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="4fb2a-257">DLP 정책을 켠 후 예상 된 정책 작업이 발생하는지 확인하기 위해 자체의 몇 가지 최종 테스트를 실행해야합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-257">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring.</span></span> <span data-ttu-id="4fb2a-258">신용 카드 데이터와 같은 것을 테스트하려는 경우 체크섬을 통과하고 정책을 트리거할 샘플 신용 카드 또는 기타 개인 정보를 생성하는 방법에 대한 정보가 있는 온라인 웹 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-258">If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="4fb2a-259">사용자 재정의를 허용하는 정책은 정책 팁의 일부로 사용자에게 해당 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-259">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![사용자가 재정의할 수 있는 정책 팁](../media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="4fb2a-261">콘텐츠를 제한하는 정책은 정책 팁의 일부로 사용자에게 경고를 표시하고 전자 메일을 보내지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-261">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![콘텐츠가 제한되는 정책 팁](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="4fb2a-263">요약</span><span class="sxs-lookup"><span data-stu-id="4fb2a-263">Summary</span></span>

<span data-ttu-id="4fb2a-264">데이터 손실 방지 정책은 모든 유형의 조직에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-264">Data loss prevention policies are useful for organizations of all types.</span></span> <span data-ttu-id="4fb2a-265">일부 DLP 정책을 테스트하는 것은 정책 팁, 최종 사용자 재정의 및 인시던트 보고서와 같은 컨트롤로 인해 위험이 낮은 운동입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-265">Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end-user overrides, and incident reports.</span></span> <span data-ttu-id="4fb2a-266">일부 DLP 정책을 조용히 테스트하여 조직에서 이미 발생하는 위반 유형을 확인하고 거짓 긍정 률이 낮은 정책을 만들고 사용자에게 허용 및 허용되지 않는 것을 교육한 다음 DLP 정책을 조직에 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb2a-266">You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>