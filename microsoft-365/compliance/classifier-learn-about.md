---
title: 학습 가능한 분류자에 대한 자세한 정보
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 학습 가능한 분류자에서는 다양한 유형의 콘텐츠를 인식할 수 있는 도구로, 볼 양성 및 부정 샘플을 제공합니다. 분류자 학습이 이행되면 결과가 정확한지 확인할 수 있습니다. 그런 다음 조직의 콘텐츠를 검색하여 보존 또는 민감도 레이블을 적용하거나 DLP(데이터 손실 방지) 또는 보존 정책에 포함하기 위해 이를 분류합니다.
ms.openlocfilehash: 0e5f712b76af2fba3d456997a47352773d92d766
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759902"
---
# <a name="learn-about-trainable-classifiers"></a><span data-ttu-id="236ad-105">학습 가능한 분류자에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="236ad-105">Learn about trainable classifiers</span></span>

<span data-ttu-id="236ad-106">콘텐츠를 적절히 보호하고 처리할 수 있도록 콘텐츠를 분류하고 레이블을 지정하는 것은 정보 보호 분야를 위한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="236ad-107">Microsoft 365에는 콘텐츠를 분류하는 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="236ad-108">수동으로</span><span class="sxs-lookup"><span data-stu-id="236ad-108">Manually</span></span>

<span data-ttu-id="236ad-109">이 방법을 사용하려면 사람의 판단과 조치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-109">This method requires human judgment and action.</span></span> <span data-ttu-id="236ad-110">관리자는 기존 레이블 및 중요한 정보 유형을 사용하거나 자체 레이블을 만든 다음 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="236ad-111">사용자와 관리자는 콘텐츠를 접할 때 해당 콘텐츠를 콘텐츠에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="236ad-112">그런 다음 콘텐츠를 보호하고 해당 콘텐츠를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="236ad-113">자동화된 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="236ad-113">Automated pattern matching</span></span>

<span data-ttu-id="236ad-114">이 분류 메커니즘 범주에는 다음을 통해 콘텐츠를 찾는 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="236ad-115">키워드 또는 메타데이터 값(키워드 쿼리 언어)</span><span class="sxs-lookup"><span data-stu-id="236ad-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="236ad-116">사회 보장, 신용 카드 또는 은행 계좌 번호(중요한 정보 유형 엔터티 정의)와 같은 이전에 식별된 중요한 정보 패턴을 [사용합니다.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="236ad-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="236ad-117">서식 파일(문서 손가락 인쇄)의 변형이기 때문에 항목을 [인식합니다.](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="236ad-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="236ad-118">정확한 문자열(정확한 데이터 [일치)이 있는 경우.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="236ad-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="236ad-119">그런 다음 민감도 및 보존 레이블을 자동으로 적용하여 [콘텐츠를 DLP(데이터](data-loss-prevention-policies.md) 손실 방지)에 사용할 수 있도록 설정하고 보존 레이블에 대한 정책을 자동으로 적용할 [수 있습니다.](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="236ad-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="236ad-120">분류자</span><span class="sxs-lookup"><span data-stu-id="236ad-120">Classifiers</span></span>

<span data-ttu-id="236ad-121">이 분류 방법은 수동 또는 자동화된 패턴 일치 방법으로 쉽게 식별되지 않는 콘텐츠에 특히 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="236ad-122">이 분류 방법은 항목의 요소(패턴 일치)가 아니라 항목의 항목을 기준으로 항목을 식별하기 위해 분류자를 교육하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="236ad-123">분류기는 분류에 관심 있는 콘텐츠의 수백 가지 예제를 확인하여 콘텐츠 형식을 식별하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="236ad-124">먼저 범주에 있는 예제를 공급합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="236ad-125">이를 처리하고 나면 일치하는 예제와 일치하지 않는 예제를 모두 조합하여 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="236ad-126">그런 다음 분류기는 주어진 항목이 구축하는 범주에 속하는지 여부를 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="236ad-127">그런 다음 결과를 확인하여 참 긍정, 참 부정, 가긍성 및 거짓 부정을 정렬하여 예측 정확도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="236ad-128">분류기를 게시할 때 SharePoint Online, Exchange 및 OneDrive와 같은 위치의 항목을 정렬하고 콘텐츠를 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="236ad-129">분류기를 게시한 후 초기 교육 프로세스와 유사한 피드백 프로세스를 사용하여 분류자 교육을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="236ad-130">학습 가능한 분류자 사용 위치</span><span class="sxs-lookup"><span data-stu-id="236ad-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="236ad-131">기본 제공 분류자 및 학습 가능한 분류자 모두 민감도 레이블이 있는 [Office](apply-sensitivity-label-automatically.md)자동 레이블 [지정,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 조건 및 통신 준수에 따라 보존 레이블 정책 자동 적용에 대한 조건으로 사용할 수 [있습니다.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="236ad-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="236ad-132">민감도 레이블은 분류기를 조건으로 사용할 수 있습니다. 콘텐츠에 자동으로 민감도 [레이블 적용을 참조하세요.](apply-sensitivity-label-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="236ad-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="236ad-133">분류기는 암호화되지 않은 영어 항목에서만 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="236ad-134">분류자 유형</span><span class="sxs-lookup"><span data-stu-id="236ad-134">Types of classifiers</span></span>

- <span data-ttu-id="236ad-135">**사전 교육된** 분류자 - Microsoft는 교육 없이 사용할 수 있는 여러 분류자들을 생성하고 사전 교육했습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="236ad-136">이러한 분류자는 의 상태와 함께 `Ready to use` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="236ad-137">**사용자** 지정 분류자 - 사전 학습된 분류자에서 다루는 것 이상으로 확장되는 분류 요구가 있는 경우 자체 분류기를 만들고 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="236ad-138">사전 학습된 분류자</span><span class="sxs-lookup"><span data-stu-id="236ad-138">Pre-trained classifiers</span></span>

<span data-ttu-id="236ad-139">Microsoft 365는 사전 학습된 5개의 분류자와 함께 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="236ad-140">가양성의 수가  높게 생성되고 있기 때문에 공격 언어 사전 학습 분류자 사용이 더는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="236ad-141">사용하지 말고 현재 사용 중인 경우 비즈니스 프로세스를 해당 프로세스에서 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="236ad-142">위협, 괴롭히기 및 괴롭히기 사전 학습된 분류자 대신 사용하는 것이 좋습니다.  </span><span class="sxs-lookup"><span data-stu-id="236ad-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="236ad-143">**이력서**: 신청자의 개인, 교육, 전문 자격, 작업 환경 및 기타 개인 식별 정보의 텍스트 계정인 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="236ad-144">**소스 코드:** GitHub에서 사용된 상위 25개 컴퓨터 프로그래밍 언어로 작성된 지침 및 문 집합이 포함된 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="236ad-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="236ad-145">ActionScript</span></span>
    - <span data-ttu-id="236ad-146">C</span><span class="sxs-lookup"><span data-stu-id="236ad-146">C</span></span>
    - <span data-ttu-id="236ad-147">C #</span><span class="sxs-lookup"><span data-stu-id="236ad-147">C#</span></span>
    - <span data-ttu-id="236ad-148">C++</span><span class="sxs-lookup"><span data-stu-id="236ad-148">C++</span></span>
    - <span data-ttu-id="236ad-149">클로루어</span><span class="sxs-lookup"><span data-stu-id="236ad-149">Clojure</span></span>
    - <span data-ttu-id="236ad-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="236ad-150">CoffeeScript</span></span>
    - <span data-ttu-id="236ad-151">Go</span><span class="sxs-lookup"><span data-stu-id="236ad-151">Go</span></span>
    - <span data-ttu-id="236ad-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="236ad-152">Haskell</span></span>
    - <span data-ttu-id="236ad-153">Java</span><span class="sxs-lookup"><span data-stu-id="236ad-153">Java</span></span>
    - <span data-ttu-id="236ad-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="236ad-154">JavaScript</span></span>
    - <span data-ttu-id="236ad-155">Lua</span><span class="sxs-lookup"><span data-stu-id="236ad-155">Lua</span></span>
    - <span data-ttu-id="236ad-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="236ad-156">MATLAB</span></span>
    - <span data-ttu-id="236ad-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="236ad-157">Objective-C</span></span>
    - <span data-ttu-id="236ad-158">Perl</span><span class="sxs-lookup"><span data-stu-id="236ad-158">Perl</span></span>
    - <span data-ttu-id="236ad-159">PHP</span><span class="sxs-lookup"><span data-stu-id="236ad-159">PHP</span></span>
    - <span data-ttu-id="236ad-160">Python</span><span class="sxs-lookup"><span data-stu-id="236ad-160">Python</span></span>
    - <span data-ttu-id="236ad-161">R</span><span class="sxs-lookup"><span data-stu-id="236ad-161">R</span></span>
    - <span data-ttu-id="236ad-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="236ad-162">Ruby</span></span>
    - <span data-ttu-id="236ad-163">스칼라</span><span class="sxs-lookup"><span data-stu-id="236ad-163">Scala</span></span>
    - <span data-ttu-id="236ad-164">셸</span><span class="sxs-lookup"><span data-stu-id="236ad-164">Shell</span></span>
    - <span data-ttu-id="236ad-165">Swift</span><span class="sxs-lookup"><span data-stu-id="236ad-165">Swift</span></span>
    - <span data-ttu-id="236ad-166">텍스</span><span class="sxs-lookup"><span data-stu-id="236ad-166">Tex</span></span>
    - <span data-ttu-id="236ad-167">Vim 스크립트</span><span class="sxs-lookup"><span data-stu-id="236ad-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="236ad-168">소스 코드는 대량의 텍스트가 소스 코드인 경우를 감지하기 위해 교육됩니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="236ad-169">일반 텍스트와 교차하는 소스 코드 텍스트를 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="236ad-170">**괴롭기:** 경인도, 인종, 종교, 국적, 성별, 성적 취향, 연령, 장애 등 한 명 또는 여러 개인을 대상으로 하는 공격적인 행동과 관련된 특정 범주의 공격적 언어 텍스트 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="236ad-171">**비방:** 대부분의 사용자에 대해 당황하는 식을 포함하는 특정 범주의 비방 언어 텍스트 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="236ad-172">**위협:** 위협을 가하거나 사람 또는 속성에 대한 물리적 손해나 손상을 가하기 위한 위협과 관련된 공격적인 언어 텍스트 항목의 특정 범주를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="236ad-173">이러한 분류는 **Microsoft 365** 규정 준수 센터의 상태와 함께 교육 가능한 분류자 보기에  >    >   `Ready to use` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-173">These appear in the **Microsoft 365 compliance center** > **Data classification** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![classifiers-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="236ad-175">공격적인 언어, 괴롭음, 괴롭음 및 위협 분류자만 검색 가능한 텍스트로만 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="236ad-176">또한 언어 및 문화 표준은 지속적으로 변경되고 이러한 현실을 토대하여 Microsoft는 재량에 따라 분류자 업데이트할 수 있는 권리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="236ad-177">분류자는 공격적 언어 및 사용되는 기타 언어를 모니터링하는 데 도움이 될 수 있는 반면, 분류자는 해당 언어의 결과를 해결하지는 않습니다. 이러한 언어의 사용에 대한 모니터링 또는 응답을 조직에서 전적으로 제공하는 것은 아니며,</span><span class="sxs-lookup"><span data-stu-id="236ad-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="236ad-178">Microsoft 또는 해당 자회사가 아닌 조직은 사전 학습된 분류자에 의해 식별된 콘텐츠의 모니터링, 적용, 차단, 제거 및 보존과 관련된 모든 결정에 대한 책임을 져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="236ad-179">사용자 지정 분류자</span><span class="sxs-lookup"><span data-stu-id="236ad-179">Custom classifiers</span></span>

<span data-ttu-id="236ad-180">사전 학습된 분류자들이 요구 사항을 충족하지 않는 경우 자체 분류자들을 만들고 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="236ad-181">자신만의 작업을 만드는 데 관련된 작업도 훨씬 더 많지만 조직 요구에 훨씬 더 잘 맞게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="236ad-182">예를 들어 다음에 대해 학습 가능한 분류기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="236ad-183">법률 문서 - 변호사 클라이언트 권한, 닫는 집합, 작업 설명 등의</span><span class="sxs-lookup"><span data-stu-id="236ad-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="236ad-184">전략적 비즈니스 문서 - 보도 자료, 인수, 거래, 비즈니스 또는 마케팅 계획, 지적 재산권, 디자인 문서 등</span><span class="sxs-lookup"><span data-stu-id="236ad-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="236ad-185">가격 정보 - 송장, 가격 견적, 작업 주문, 매입 문서 등</span><span class="sxs-lookup"><span data-stu-id="236ad-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="236ad-186">재무 정보 - 조직 투자, 분기별 또는 연간 결과 등</span><span class="sxs-lookup"><span data-stu-id="236ad-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="236ad-187">사용자 지정 분류자 만들기 위한 프로세스 흐름</span><span class="sxs-lookup"><span data-stu-id="236ad-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="236ad-188">보존 정책 및 통신 감독과 같은 규정 준수 솔루션에서 사용할 분류자 만들기 및 게시는 이 흐름을 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="236ad-189">학습 가능한 사용자 지정 분류자 만들기에 대한 자세한 내용은 사용자 지정 분류자 [만들기를 참조합니다.](classifier-get-started-with.md)</span><span class="sxs-lookup"><span data-stu-id="236ad-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![프로세스 흐름 사용자 지정 분류자](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="236ad-191">분류자 재시도</span><span class="sxs-lookup"><span data-stu-id="236ad-191">Retraining classifiers</span></span>

<span data-ttu-id="236ad-192">수행한 분류의 정확성에 대한 피드백을 제공하여 모든 사용자 지정 분류자 및 사전 학습된 분류자의 정확도를 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="236ad-193">이를 재조정이라고 합니다. 이 워크플로를 따르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="236ad-193">This is called retraining and follow this workflow.</span></span>

![분류자 재조정 워크플로](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="236ad-195">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="236ad-195">See also</span></span>

- [<span data-ttu-id="236ad-196">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="236ad-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="236ad-197">DLP(데이터 손실 방지)</span><span class="sxs-lookup"><span data-stu-id="236ad-197">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="236ad-198">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="236ad-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="236ad-199">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="236ad-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="236ad-200">문서 손가락 인쇄</span><span class="sxs-lookup"><span data-stu-id="236ad-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="236ad-201">정확한 데이터 일치</span><span class="sxs-lookup"><span data-stu-id="236ad-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
